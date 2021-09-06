---
title: Expériences Azure Machine Learning
description: Utilisez des modèles basés sur Azure Machine Learning dans Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4c04a1d08aba152ce91d452ae2300c1ce0fc79e5d6980ac506dc40d9914c9fca
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033169"
---
# <a name="use-azure-machine-learning-based-models"></a>Utiliser des modèles basés sur Azure Machine Learning

Les données unifiées dans Dynamics 365 Customer Insights sont une source pour créer des modèles Machine Learning qui peuvent générer des informations métier supplémentaires. Customer Insights s’intègre à Machine Learning Studio (classique) et à Azure Machine Learning pour utiliser vos propres modèles personnalisés. Consultez [Expériences Machine Learning Studio (classique)](machine-learning-studio-experiments.md) pour voir des exemples d’expériences reposant sur Machine Learning Studio (classique). 

## <a name="prerequisites"></a>Conditions préalables

- Accéder à Customer Insights
- Activer l’abonnement Azure Enterprise
- [Profils client unifiés](data-unification.md)
- [Exportation d’entité vers le stockage Blob Azure](export-azure-blob-storage.md) configurée

## <a name="set-up-azure-machine-learning-workspace"></a>Configurer l’espace de travail Azure Machine Learning

1. Consultez [Créer un espace de travail Azure Machine Learning](/azure/machine-learning/concept-workspace#-create-a-workspace) pour voir les différentes options de création de l’espace de travail. Pour optimiser les performances, créez l’espace de travail dans une région Azure qui est géographiquement la plus proche de votre environnement Customer Insights.

1. Accédez à votre espace de travail via [Azure Machine Learning Studio](https://ml.azure.com/). Vous pouvez [interagir](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) avec votre espace de travail de plusieurs façons.

## <a name="work-with-azure-machine-learning-designer"></a>Utiliser le concepteur Azure Machine Learning

Le concepteur Azure Machine Learning fournit un canevas visuel dans lequel vous pouvez glisser-déplacer des ensembles de données et des modules, similaires à Machine Learning Studio (classique). Un pipeline par lots créé à partir du concepteur peut être intégré dans Customer Insights s’il est configuré en conséquence. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Utilisation du SDK Azure Machine Learning

Les scientifiques de données et les développeurs de l’IA utilisent le [SDK Azure Machine Learning](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) pour créer des workflows Machine Learning. Actuellement, les modèles entraînés à l’aide du SDK ne peuvent pas être intégrés directement à Customer Insights. Un pipeline d’inférence par lots qui utilise ce modèle est nécessaire pour l’intégration avec Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Exigences du pipeline par lots pour l’intégration avec Customer Insights

### <a name="dataset-configuration"></a>Configuration de l’ensemble de données

Vous devez créer des ensembles de données pour utiliser les données d’entité de Customer Insights dans votre pipeline d’inférence par lots. Ces ensembles de données doivent être enregistrés dans l’espace de travail. Actuellement, nous ne prenons en charge que les [ensembles de données tabulaires](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) au format .csv. Les ensembles de données correspondant aux données d’entité doivent être paramétrés en tant que paramètre de pipeline.
   
* Paramètres de l’ensemble de données dans le concepteur
   
     Dans le concepteur, ouvrez **Sélectionner des colonnes dans l’ensemble de données**, sélectionnez **Définir comme paramètre de pipeline** et indiquez un nom pour le paramètre.

     > [!div class="mx-imgBorder"]
     > ![Paramétrage de l’ensemble de données dans le concepteur.](media/intelligence-designer-dataset-parameters.png "Paramétrage de l’ensemble de données dans le concepteur")
   
* Paramètres de l’ensemble de données dans le SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Pipeline d’inférence par lots
  
* Dans le concepteur, un pipeline de formation peut être utilisé pour créer ou mettre à jour un pipeline d’inférence. Actuellement, seuls les pipelines d’inférence par lots sont pris en charge.

* À l’aide du SDK, vous pouvez publier le pipeline dans un point de terminaison. Actuellement, Customer Insights s’intègre au pipeline par défaut dans un point de terminaison du pipeline par lots de l’espace de travail Machine Learning.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Importer les données du pipeline dans Customer Insights

* Le concepteur fournit le [Module d’exportation de données](/azure/machine-learning/algorithm-module-reference/export-data) qui permet d’exporter la sortie d’un pipeline vers le stockage Azure. Actuellement, le module doit utiliser le type de magasin de données **Stockage Blob Azure** et paramétrer le **Magasin de données** et le **Chemin d’accès** relatif. Customer Insights remplace ces deux paramètres lors de l’exécution du pipeline par un magasin de données et un chemin d’accès accessible au produit.
   > [!div class="mx-imgBorder"]
   > ![Configuration du module d’exportation de données.](media/intelligence-designer-importdata.png "Configuration du module d’exportation de données")
   
* Lors de l’écriture de la sortie d’inférence à l’aide de code, vous pouvez charger la sortie dans le chemin d’accès d’un *magasin de données enregistré* de l’espace de travail. Si le chemin d’accès et le magasin de données sont paramétrés dans le pipeline, Customer insights pourra lire et importer la sortie d’inférence. Actuellement, une seule sortie tabulaire au format csv est prise en charge. Le chemin d’accès doit inclure le répertoire et le nom du fichier.

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]