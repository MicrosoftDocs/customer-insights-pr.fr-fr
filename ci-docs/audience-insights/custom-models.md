---
title: Modèles personnalisés Machine Learning | Microsoft Docs
description: Utilisez des modèles personnalisés de Azure Machine Learning dans Dynamics 365 Customer Insights.
ms.date: 12/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 460b68e1e65b3033af0a03d1bcc27e718c79d7aa
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355072"
---
# <a name="custom-machine-learning-models"></a>Modèles personnalisés Machine Learning

> [!NOTE]
> Le support pour Machine Learning Studio (classique) prendra fin le 31 août 2024. Nous vous recommandons de passer à [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning) d’ici cette date.
>
> À compter du 1er décembre 2021, vous ne pourrez plus créer de nouvelles ressources Machine Learning Studio (classique). Jusqu’au 31 août 2024, vous pouvez continuer à utiliser les ressources Machine Learning Studio (classique) existantes. Pour plus d’informations, consultez [Migrer vers Azure Machine Learning](/azure/machine-learning/migrate-overview).


**Intelligence** > **Modèles personnalisés** vous permet de gérer des flux de travail basés sur les modèles Azure Machine Learning. Les workflows vous aident à choisir les données à partir desquelles vous souhaitez générer des informations, et à mapper les résultats à vos données client unifiées. Pour plus d’informations sur la création de modèles ML personnalisés, consultez [Utiliser les modèles basés sur Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>IA responsable

Les prédictions offrent des fonctionnalités pour créer de meilleures expériences client, améliorer les fonctionnalités métier et les flux de revenus. Nous vous recommandons fortement d’équilibrer la valeur de votre prédiction par rapport à son impact et aux tendances qui peuvent être introduites de manière éthique. En savoir plus sur la manière dont Microsoft [gère l’IA responsable](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Vous pouvez également découvrir les [techniques et processus pour un apprentissage automatique responsable](/azure/machine-learning/concept-responsible-ml) spécifique à Azure Machine Learning.

## <a name="prerequisites"></a>Conditions préalables

- Cette fonctionnalité prend en charge les services Web publiés via les [Pipelines par lots Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).

- Un compte de stockage Azure Data Lake Gen2 doit être associé à votre instance Azure Studio pour utiliser cette fonctionnalité. Pour plus d’informations, voir [Créer un compte de stockage Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Pour les espaces de travail Azure Machine Learning avec pipelines, vous avez besoin des autorisations d’administrateur pour l’accès propriétaire ou utilisateur sur l’espace de travail Azure Machine Learning.

   > [!NOTE]
   > Les données sont transférées entre vos instances Customer Insights et les pipelines ou les services web Azure sélectionnés dans le workflow. Lorsque vous transférez des données vers un service Azure, assurez-vous que le service est configuré pour traiter les données comme il se doit et à partir de l’emplacement requis afin de respecter les exigences légales ou réglementaires pour votre entreprise.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

## <a name="add-a-new-workflow"></a>Ajouter un nouveau workflow

1. Accédez à **Intelligence** > **Modèles personnalisés** et sélectionnez **Nouveau workflow**.

1. Donnez un nom reconnaissable à votre modèle personnalisé dans le champ **Nom**.

   > [!div class="mx-imgBorder"]
   > ![Capture d’écran du volet Nouveau workflow.](media/new-workflowv2.png "Capture d’écran du volet Nouveau workflow")

1. Sélectionnez l’organisation qui contient le service Web dans **Client contenant votre service Web**.

1. Si votre abonnement Azure Machine Learning se trouve dans un client différent de Customer Insights, sélectionnez **Se connecter** avec vos informations d’identification pour l’organisation sélectionnée.

1. Sélectionnez les **Espaces de travail** associés à votre service web. 

1. Choisissez le pipeline Azure Machine Learning dans la liste déroulante **Service Web contenant votre modèle**. Ensuite, cliquez sur **Suivant**.    
   En savoir plus sur la [publication d’un pipeline dans Azure Machine Learning à l’aide du concepteur](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ou du [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Votre pipeline doit être publié dans un [point de terminaison de pipeline](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Pour chaque **Entrée du service web**, sélectionnez l’**Entité** correspondante dans les informations sur l’audience et sélectionnez **Suivant**.
   > [!NOTE]
   > Le workflow du modèle personnalisé appliquera une heuristique pour mapper les champs d’entrée du service web aux attributs d’entité en fonction du nom et du type de données du champ. Vous verrez une erreur si un champ de service web ne peut pas être mappé à une entité.

   > [!div class="mx-imgBorder"]
   > ![Configurez un workflow.](media/intelligence-screen2-updated.png "Configurer un workflow")

1. Dans l’étape **Paramètres de sortie du modèle**, définissez les propriétés suivantes :
      1. Entrez le **Nom de l’entité** de sortie dans laquelle vous voulez envoyer les résultats de sortie du pipeline.
      1. Sélectionnez le **Nom du paramètre du magasin de données de sortie** de votre pipeline par lots dans la liste déroulante.
      1. Sélectionnez le **Nom du paramètre du chemin d’accès de sortie** de votre pipeline par lots dans la liste déroulante.

      > [!div class="mx-imgBorder"]
      > ![Volet des paramètres de sortie du modèle.](media/intelligence-screen3-outputparameters.png "Volet des paramètres de sortie du modèle")

1. Sélectionnez l’attribut correspondant dans la liste déroulante **ID de client dans les résultats** qui identifie les clients et sélectionnez **Enregistrer**.

   > [!div class="mx-imgBorder"]
   > ![Associez les résultats au volet Données client.](media/intelligence-screen4-relatetocustomer.png "Associer les résultats au volet Données client")

1. L’écran **Workflow enregistré** avec des détails sur le workflow s’affiche alors.    
   Si vous avez configuré un workflow pour un pipeline Azure Machine Learning, les informations sur l’audience seront associées à l’espace de travail contenant le pipeline. Les informations sur l’audience obtiendront un rôle de **Contributeur** dans l’espace de travail Azure.

1. Cliquez sur **Terminé**.

1. Vous pouvez maintenant exécuter le workflow à partir de la page **Modèles personnalisés**.

## <a name="edit-a-workflow"></a>Modifier un workflow

1. Sur la page **Modèles personnalisés**, sélectionnez les points de suspension dans la colonne **Actions** en regard d’un workflow que vous avez créé précédemment, puis sélectionnez **Modifier**.

1. Vous pouvez mettre à jour le nom reconnaissable de votre workflow dans le champ **Nom complet**, mais vous ne pouvez pas modifier le service web ou le pipeline configuré. Cliquez sur **Suivant**.

1. Pour chaque **Entrée du service web**, vous pouvez mettre à jour l’**Entité** correspondante dans les informations sur l’audience. Ensuite, cliquez sur **Suivant**.

1. Dans l’étape **Paramètres de sortie du modèle**, définissez les propriétés suivantes :
      1. Entrez le **Nom de l’entité** de sortie dans laquelle vous voulez envoyer les résultats de sortie du pipeline.
      1. Sélectionnez le **Nom du paramètre du magasin de données de sortie** pour votre pipeline de test.
      1. Sélectionnez le **Nom du paramètre du chemin d’accès de sortie** pour votre pipeline de test.

1. Sélectionnez l’attribut correspondant dans la liste déroulante **ID de client dans les résultats** qui identifie les clients et sélectionnez **Enregistrer**.
   Choisissez un attribut dans la sortie d’inférence avec des valeurs similaires à la colonne ID de client de l’entité Client. Si cette colonne n’est pas présente dans votre ensemble de données, choisissez un attribut qui identifie de manière unique la ligne.

## <a name="run-a-workflow"></a>Exécuter un workflow

1. Sur la page **Modèles personnalisés**, sélectionnez les points de suspension dans la colonne **Actions** en regard d’un workflow que vous avez créé précédemment, puis sélectionnez Modifier.

1. Sélectionnez **Exécuter**.

Votre workflow s’exécute également automatiquement à chaque actualisation planifiée. En savoir plus sur la [configuration des actualisations programmées](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Supprimer un flux de travail

1. Sur la page **Modèles personnalisés**, sélectionnez les points de suspension dans la colonne **Actions** en regard d’un workflow que vous avez créé précédemment, puis sélectionnez Modifier.

1. Sélectionnez **Supprimer**, puis confirmez votre suppression.

Votre workflow sera supprimé. L’[entité](entities.md) qui a été créée lorsque vous avez créé le workflow persiste et peut être consultée à partir de la page **Entités**.

## <a name="results"></a>Résultats

Les résultats d’un workflow sont stockés dans l’entité configurée lors de la phase Paramètres de sortie du modèle. Vous pouvez accéder à ces données à partir de la [page des entités](entities.md) ou avec l’[accès API](apis.md).

### <a name="api-access"></a>Accès API

Pour que la requête OData spécifique récupère les données d’une entité de modèle personnalisé, utilisez le format suivant :

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Remplacez `<your instance id>` par l’ID de votre environnement Customer Insights, qui se situe dans la barre d’adresse de votre navigateur lorsque vous accédez à Customer Insights.

1. Remplacez `<custom model output entity>` par le nom d’entité que vous avez fourni lors de l’étape Paramètres de sortie du modèle de la configuration du modèle personnalisé.

1. Remplacez `<guid value>` par l’ID client du client pour lequel vous souhaitez accéder à l’enregistrement. Vous pouvez généralement trouver cet ID sur la [page des profils clients](customer-profiles.md) dans le champ CustomerID.

## <a name="frequently-asked-questions"></a>Forums Aux Questions

- Pourquoi ne puis-je pas voir mon pipeline lors de la configuration d’un workflow de modèle personnalisé ?    
  Ce problème est souvent causé par un problème de configuration dans le pipeline. Assurez-vous que le [paramètre d’entrée est configuré](azure-machine-learning-experiments.md#dataset-configuration), et que [le magasin de données de sortie et les paramètres du chemin](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) sont également configurés.

- Que signifie l’erreur « Impossible d’enregistrer le workflow d’intelligence » ?    
  Les utilisateurs voient généralement ce message d’erreur s’ils ne disposent pas des privilèges d’administrateur pour l’accès propriétaire ou utilisateur sur l’espace de travail. L’utilisateur a besoin d’un niveau d’autorisations plus élevé pour permettre à Customer Insights de traiter le workflow en tant que service plutôt que d’utiliser les informations d’identification de l’utilisateur pour les exécutions suivantes du workflow.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
