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
ms.openlocfilehash: edd2cf488b52cef87b09b90336e48fdc7f470a68
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597416"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="995eb-103">Utiliser des modèles basés sur Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="995eb-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="995eb-104">Les données unifiées dans Dynamics 365 Customer Insights sont une source pour créer des modèles Machine Learning qui peuvent générer des informations métier supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="995eb-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="995eb-105">Customer Insights s’intègre à Machine Learning Studio (classique) et à Azure Machine Learning pour utiliser vos propres modèles personnalisés.</span><span class="sxs-lookup"><span data-stu-id="995eb-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="995eb-106">Consultez [Expériences Machine Learning Studio (classique)](machine-learning-studio-experiments.md) pour voir des exemples d’expériences reposant sur Machine Learning Studio (classique).</span><span class="sxs-lookup"><span data-stu-id="995eb-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="995eb-107">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="995eb-107">Prerequisites</span></span>

- <span data-ttu-id="995eb-108">Accéder à Customer Insights</span><span class="sxs-lookup"><span data-stu-id="995eb-108">Access to Customer Insights</span></span>
- <span data-ttu-id="995eb-109">Activer l’abonnement Azure Enterprise</span><span class="sxs-lookup"><span data-stu-id="995eb-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="995eb-110">Profils client unifiés</span><span class="sxs-lookup"><span data-stu-id="995eb-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="995eb-111">[Exportation d’entité vers le stockage Blob Azure](export-azure-blob-storage.md) configurée</span><span class="sxs-lookup"><span data-stu-id="995eb-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="995eb-112">Configurer l’espace de travail Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="995eb-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="995eb-113">Consultez [Créer un espace de travail Azure Machine Learning](/azure/machine-learning/concept-workspace#-create-a-workspace) pour voir les différentes options de création de l’espace de travail.</span><span class="sxs-lookup"><span data-stu-id="995eb-113">See [create a Azure Machine Learning workspace](/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="995eb-114">Pour optimiser les performances, créez l’espace de travail dans une région Azure qui est géographiquement la plus proche de votre environnement Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="995eb-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="995eb-115">Accédez à votre espace de travail via [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="995eb-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="995eb-116">Vous pouvez [interagir](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) avec votre espace de travail de plusieurs façons.</span><span class="sxs-lookup"><span data-stu-id="995eb-116">There are several [ways to interact](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="995eb-117">Utiliser le concepteur Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="995eb-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="995eb-118">Le concepteur Azure Machine Learning fournit un canevas visuel dans lequel vous pouvez glisser-déplacer des ensembles de données et des modules, similaires à Machine Learning Studio (classique).</span><span class="sxs-lookup"><span data-stu-id="995eb-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="995eb-119">Un pipeline par lots créé à partir du concepteur peut être intégré dans Customer Insights s’il est configuré en conséquence.</span><span class="sxs-lookup"><span data-stu-id="995eb-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="995eb-120">Utilisation du SDK Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="995eb-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="995eb-121">Les scientifiques de données et les développeurs de l’IA utilisent le [SDK Azure Machine Learning](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) pour créer des workflows Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="995eb-121">Data scientists and AI developers use the [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) to build machine learning workflows.</span></span> <span data-ttu-id="995eb-122">Actuellement, les modèles entraînés à l’aide du SDK ne peuvent pas être intégrés directement à Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="995eb-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="995eb-123">Un pipeline d’inférence par lots qui utilise ce modèle est nécessaire pour l’intégration avec Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="995eb-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="995eb-124">Exigences du pipeline par lots pour l’intégration avec Customer Insights</span><span class="sxs-lookup"><span data-stu-id="995eb-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="995eb-125">Configuration de l’ensemble de données</span><span class="sxs-lookup"><span data-stu-id="995eb-125">Dataset Configuration</span></span>

<span data-ttu-id="995eb-126">Vous devez créer des ensembles de données pour utiliser les données d’entité de Customer Insights dans votre pipeline d’inférence par lots.</span><span class="sxs-lookup"><span data-stu-id="995eb-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="995eb-127">Ces ensembles de données doivent être enregistrés dans l’espace de travail.</span><span class="sxs-lookup"><span data-stu-id="995eb-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="995eb-128">Actuellement, nous ne prenons en charge que les [ensembles de données tabulaires](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) au format .csv.</span><span class="sxs-lookup"><span data-stu-id="995eb-128">Currently, we only support [tabular datasets](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="995eb-129">Les ensembles de données correspondant aux données d’entité doivent être paramétrés en tant que paramètre de pipeline.</span><span class="sxs-lookup"><span data-stu-id="995eb-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="995eb-130">Paramètres de l’ensemble de données dans le concepteur</span><span class="sxs-lookup"><span data-stu-id="995eb-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="995eb-131">Dans le concepteur, ouvrez **Sélectionner des colonnes dans l’ensemble de données**, sélectionnez **Définir comme paramètre de pipeline** et indiquez un nom pour le paramètre.</span><span class="sxs-lookup"><span data-stu-id="995eb-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="995eb-132">![Paramétrage de l’ensemble de données dans le concepteur](media/intelligence-designer-dataset-parameters.png "Paramétrage de l’ensemble de données dans le concepteur")</span><span class="sxs-lookup"><span data-stu-id="995eb-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="995eb-133">Paramètres de l’ensemble de données dans le SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="995eb-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="995eb-134">Pipeline d’inférence par lots</span><span class="sxs-lookup"><span data-stu-id="995eb-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="995eb-135">Dans le concepteur, un pipeline de formation peut être utilisé pour créer ou mettre à jour un pipeline d’inférence.</span><span class="sxs-lookup"><span data-stu-id="995eb-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="995eb-136">Actuellement, seuls les pipelines d’inférence par lots sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="995eb-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="995eb-137">À l’aide du SDK, vous pouvez publier le pipeline dans un point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="995eb-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="995eb-138">Actuellement, Customer Insights s’intègre au pipeline par défaut dans un point de terminaison du pipeline par lots de l’espace de travail Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="995eb-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="995eb-139">Importer les données du pipeline dans Customer Insights</span><span class="sxs-lookup"><span data-stu-id="995eb-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="995eb-140">Le concepteur fournit le [Module d’exportation de données](/azure/machine-learning/algorithm-module-reference/export-data) qui permet d’exporter la sortie d’un pipeline vers le stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="995eb-140">The designer provides the [Export Data module](/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="995eb-141">Actuellement, le module doit utiliser le type de magasin de données **Stockage Blob Azure** et paramétrer le **Magasin de données** et le **Chemin d’accès** relatif.</span><span class="sxs-lookup"><span data-stu-id="995eb-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="995eb-142">Customer Insights remplace ces deux paramètres lors de l’exécution du pipeline par un magasin de données et un chemin d’accès accessible au produit.</span><span class="sxs-lookup"><span data-stu-id="995eb-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="995eb-143">![Configuration du module d’exportation de données](media/intelligence-designer-importdata.png "Configuration du module d’exportation de données")</span><span class="sxs-lookup"><span data-stu-id="995eb-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="995eb-144">Lors de l’écriture de la sortie d’inférence à l’aide de code, vous pouvez charger la sortie dans le chemin d’accès d’un *magasin de données enregistré* de l’espace de travail.</span><span class="sxs-lookup"><span data-stu-id="995eb-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="995eb-145">Si le chemin d’accès et le magasin de données sont paramétrés dans le pipeline, Customer insights pourra lire et importer la sortie d’inférence.</span><span class="sxs-lookup"><span data-stu-id="995eb-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="995eb-146">Actuellement, une seule sortie tabulaire au format csv est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="995eb-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="995eb-147">Le chemin d’accès doit inclure le répertoire et le nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="995eb-147">The path must include the directory and filename.</span></span>

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