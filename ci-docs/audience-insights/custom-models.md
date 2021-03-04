---
title: Modèles personnalisés Machine Learning | Microsoft Docs
description: Utilisez des modèles personnalisés de Azure Machine Learning dans Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267231"
---
# <a name="custom-machine-learning-models"></a>Modèles personnalisés Machine Learning

**Intelligence** > **Modèles personnalisés** vous permet de gérer des flux de travail basés sur les modèles Azure Machine Learning. Les workflows vous aident à choisir les données à partir desquelles vous souhaitez générer des informations, et à mapper les résultats à vos données client unifiées. Pour plus d’informations sur la création de modèles ML personnalisés, consultez [Utiliser les modèles basés sur Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>IA responsable

Les prédictions offrent des fonctionnalités pour créer de meilleures expériences client, améliorer les fonctionnalités métier et les flux de revenus. Nous vous recommandons fortement d’équilibrer la valeur de votre prédiction par rapport à son impact et aux tendances qui peuvent être introduites de manière éthique. En savoir plus sur la manière dont Microsoft [gère l’IA responsable](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Vous pouvez également découvrir les [techniques et processus pour un apprentissage automatique responsable](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) spécifique à Azure Machine Learning.

## <a name="prerequisites"></a>Conditions préalables

- Actuellement, cette fonctionnalité prend en charge les services web publiés via [Machine Learning Studio (classique)](https://studio.azureml.net) et les [Pipelines par lots Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Un compte de stockage Azure Data Lake Gen2 doit être associé à votre instance Azure Studio pour utiliser cette fonctionnalité. Pour plus d’informations, voir [Créer un compte de stockage Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Ajouter un nouveau workflow

1. Accédez à **Intelligence** > **Modèles personnalisés** et sélectionnez **Nouveau workflow**.

1. Donnez un nom reconnaissable à votre modèle personnalisé dans le champ **Nom**.

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran du volet Nouveau workflow](media/new-workflowv2.png "Capture d’écran du volet Nouveau workflow")

1. Sélectionnez l’organisation qui contient le service Web dans **Client contenant votre service Web**.

1. Si votre abonnement Azure Machine Learning se trouve dans un client différent de Customer Insights, sélectionnez **Se connecter** avec vos informations d’identification pour l’organisation sélectionnée.

1. Sélectionnez les **Espaces de travail** associés à votre service web. Deux sections sont répertoriées, une pour Azure Machine Learning v1 (Machine Learning Studio (classique)) et une pour Azure Machine Learning v2 (Azure Machine Learning). Si vous ne savez pas quel espace de travail est approprié pour votre service web Machine Learning Studio (classique), sélectionnez **Tout**.

1. Choisissez le service web Machine Learning Studio (classique) ou le pipeline Azure Machine Learning dans la liste déroulante **Service web contenant votre modèle**. Ensuite, cliquez sur **Suivant**.
   - En savoir plus sur la [publication d’un service web dans Machine Learning Studio (classique)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - En savoir plus sur la [publication d’un pipeline dans Azure Machine Learning à l’aide du concepteur](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ou du [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Votre pipeline doit être publié dans un [point de terminaison de pipeline](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Pour chaque **Entrée du service web**, sélectionnez l’**Entité** correspondante dans les informations sur l’audience et sélectionnez **Suivant**.
   > [!NOTE]
   > Le workflow du modèle personnalisé appliquera une heuristique pour mapper les champs d’entrée du service web aux attributs d’entité en fonction du nom et du type de données du champ. Vous verrez une erreur si un champ de service web ne peut pas être mappé à une entité.

   > [!div class="mx-imgBorder"]
   > ![Configurer un workflow](media/intelligence-screen2-updated.png "Configurer un workflow")
   
1. Dans l’étape **Paramètres de sortie du modèle**, définissez les propriétés suivantes :
   - Machine Learning Studio (classique)
      1. Entrez le **Nom de l’entité** de sortie dans laquelle vous voulez envoyer les résultats de sortie du service web.
   - Azure Machine Learning
      1. Entrez le **Nom de l’entité** de sortie dans laquelle vous voulez envoyer les résultats de sortie du pipeline.
      1. Sélectionnez le **Nom du paramètre du magasin de données de sortie** de votre pipeline par lots dans la liste déroulante.
      1. Sélectionnez le **Nom du paramètre du chemin d’accès de sortie** de votre pipeline par lots dans la liste déroulante.
      
      > [!div class="mx-imgBorder"]
      > ![Volet des paramètres de sortie du modèle](media/intelligence-screen3-outputparameters.png "Volet des paramètres de sortie du modèle")

1. Sélectionnez l’attribut correspondant dans la liste déroulante **ID de client dans les résultats** qui identifie les clients, puis sélectionnez **Enregistrer**.
   
   > [!div class="mx-imgBorder"]
   > ![Associer les résultats au volet Données client](media/intelligence-screen4-relatetocustomer.png "Associer les résultats au volet Données client")

1. L’écran **Workflow enregistré** avec des détails sur le workflow s’affiche alors.    
   Si vous avez configuré un workflow pour un pipeline Azure Machine Learning, les informations sur l’audience seront associées à l’espace de travail contenant le pipeline. Les informations sur l’audience obtiendront un rôle de **Contributeur** dans l’espace de travail Azure.

1. Cliquez sur **Terminé**.

1. Vous pouvez maintenant exécuter le workflow à partir de la page **Modèles personnalisés**.

## <a name="edit-a-workflow"></a>Modifier un workflow

1. Sur la page **Modèles personnalisés**, sélectionnez les points de suspension dans la colonne **Actions** en regard d’un workflow que vous avez créé précédemment, puis sélectionnez **Modifier**.

1. Vous pouvez mettre à jour le nom reconnaissable de votre workflow dans le champ **Nom complet**, mais vous ne pouvez pas modifier le service web ou le pipeline configuré. Cliquez sur **Suivant**.

1. Pour chaque **Entrée du service web**, vous pouvez mettre à jour l’**Entité** correspondante dans les informations sur l’audience. Ensuite, cliquez sur **Suivant**.

1. Dans l’étape **Paramètres de sortie du modèle**, définissez les propriétés suivantes :
   - Machine Learning Studio (classique)
      1. Entrez le **Nom de l’entité** de sortie dans laquelle vous voulez envoyer les résultats de sortie du service web.
   - Azure Machine Learning
      1. Entrez le **Nom de l’entité** de sortie dans laquelle vous voulez envoyer les résultats de sortie du pipeline.
      1. Sélectionnez le **Nom du paramètre du magasin de données de sortie** pour votre pipeline de test.
      1. Sélectionnez le **Nom du paramètre du chemin d’accès de sortie** pour votre pipeline de test.

1. Sélectionnez l’attribut correspondant dans la liste déroulante **ID de client dans les résultats** qui identifie les clients, puis sélectionnez **Enregistrer**.
   Vous devez choisir un attribut dans la sortie d’inférence avec des valeurs similaires à la colonne ID de client de l’entité Client. Si cette colonne n’est pas présente dans votre ensemble de données, choisissez un attribut qui identifie de manière unique la ligne.

## <a name="run-a-workflow"></a>Exécuter un workflow

1. Sur la page **Modèles personnalisés**, sélectionnez les points de suspension dans la colonne **Actions** en regard d’un workflow que vous avez créé précédemment, puis sélectionnez Modifier.

1. Sélectionnez **Exécuter**.

Votre workflow s’exécute également automatiquement à chaque actualisation planifiée. En savoir plus sur la [configuration des actualisations programmées](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Supprimer un flux de travail

1. Sur la page **Modèles personnalisés**, sélectionnez les points de suspension dans la colonne **Actions** en regard d’un workflow que vous avez créé précédemment, puis sélectionnez Modifier.

1. Sélectionnez **Supprimer**, puis confirmez votre suppression.

Votre workflow sera supprimé. L’[entité](entities.md) qui a été créée lorsque vous avez créé le workflow persiste et peut être consultée à partir de la page **Entités**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]