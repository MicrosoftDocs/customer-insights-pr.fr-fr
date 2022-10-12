---
title: Modèles personnalisés Machine Learning | Microsoft Docs
description: Utilisez des modèles personnalisés de Azure Machine Learning dans Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609743"
---
# <a name="custom-machine-learning-models"></a>Modèles personnalisés Machine Learning

> [!NOTE]
> Le support pour Machine Learning Studio (classique) prendra fin le 31 août 2024. Nous vous recommandons de passer à [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning) d’ici cette date.
>
> À compter du 1er décembre 2021, vous ne pourrez plus créer de nouvelles ressources Machine Learning Studio (classique). Jusqu’au 31 août 2024, vous pouvez continuer à utiliser les ressources Machine Learning Studio (classique) existantes. Pour plus d’informations, consultez [Migrer vers Azure Machine Learning](/azure/machine-learning/migrate-overview).

Les modèles personnalisés vous permettent de gérer les workflows basés sur les modèles Azure Machine Learning. Les workflows vous aident à choisir les données à partir desquelles vous souhaitez générer des informations, et à mapper les résultats à vos données client unifiées. Pour plus d’informations sur la création de modèles ML personnalisés, consultez [Utiliser les modèles basés sur Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Conditions préalables

- Services Web publiés via les [Pipelines par lots Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).
- Le pipeline doit être publié dans un [point de terminaison de pipeline](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- Compte de stockage [Azure Data Lake Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account) associé à votre instance Azure Studio.
- Pour les espaces de travail Azure Machine Learning avec pipelines, autorisations administrateur pour l’accès propriétaire ou utilisateur à l’espace de travail Azure Machine Learning.

  > [!NOTE]
  > Les données sont transférées entre vos instances Customer Insights et les pipelines ou les services web Azure sélectionnés dans le workflow. Lorsque vous transférez des données vers un service Azure, assurez-vous que le service est configuré pour traiter les données comme il se doit et à partir de l’emplacement requis afin de respecter les exigences légales ou réglementaires pour votre entreprise.

## <a name="add-a-new-workflow"></a>Ajouter un nouveau workflow

1. Accédez à **Intelligence** > **Modèles personnalisés** et sélectionnez **Nouveau workflow**.

1. Fournissez un **Nom** reconnaissable.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Capture d’écran du volet Nouveau workflow.":::

1. Sélectionnez l’organisation qui contient le service Web dans **Client contenant votre service Web**.

1. Si votre abonnement Azure Machine Learning se trouve dans un client différent de Customer Insights, sélectionnez **Se connecter** avec vos informations d’identification pour l’organisation sélectionnée.

1. Sélectionnez les **Espaces de travail** associés à votre service web.

1. Choisissez le pipeline Azure Machine Learning dans la liste déroulante **Service Web contenant votre modèle**. Ensuite, cliquez sur **Suivant**.
   En savoir plus sur la [publication d’un pipeline dans Azure Machine Learning à l’aide du concepteur](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ou du [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Pour chaque **Entrée du service Web**, sélectionnez l’**Entité** correspondante dans Customer Insights. Ensuite, cliquez sur **Suivant**.
   > [!NOTE]
   > Le workflow du modèle personnalisé appliquera une heuristique pour mapper les champs d’entrée du service web aux attributs d’entité en fonction du nom et du type de données du champ. Vous verrez une erreur si un champ de service web ne peut pas être mappé à une entité.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Configurez un workflow.":::

1. Pour les **Paramètres de sortie du modèle**, définissez les propriétés suivantes :
   - **Nom de l’entité** pour les résultats de sortie du pipeline
   - **Nom du paramètre du magasin de données de sortie** de votre pipeline par lots
   - **Nom du paramètre du chemin de sortie** de votre pipeline par lots

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Volet des paramètres de sortie du modèle.":::

1. Sélectionnez l’attribut correspondant dans **ID de client dans les résultats** qui identifie les clients; puis sélectionnez **Enregistrer**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Associez les résultats au volet Données client.":::

   L’écran **Workflow enregistré** affiche des détails sur le workflow. Si vous avez configuré un flux de travail pour un pipeline Azure Machine Learning, Customer Insights l’associe à l’espace de travail contenant le pipeline. Customer Insights obtiendra un rôle de **Contributeur** dans l’espace de travail Azure.

1. Cliquez sur **Terminé**. La page **Modèles personnalisés** s’affiche.

1. Sélectionnez les points de suspension verticaux (&vellip;) pour le workflow et sélectionnez **Exécuter**. Votre workflow s’exécute également automatiquement à chaque [actualisation planifiée](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Gérer un workflow existant

Accédez à **Intelligence** > **Modèles personnalisés** pour afficher les workflows que vous avez créés.

Sélectionnez un workflow pour voir les actions disponibles.

- **Modifier** un workflow
- **Exécuter** un workflow
- [**Supprimer**](#delete-a-workflow) un workflow

### <a name="edit-a-workflow"></a>Modifier un workflow

1. Accédez à **Intelligence** > **Modèles personnalisés**.

1. En regard du workflow que vous souhaitez mettre à jour, sélectionnez les points de suspension verticaux (&vellip;) et sélectionnez **Modifier**.

1. Modifiez le **Nom complet** si nécessaire, puis sélectionnez **Suivant**.

1. Pour chaque **Entrée du service Web**, mettez à jour l’**Entité** correspondante dans Customer Insights, si nécessaire. Ensuite, cliquez sur **Suivant**.

1. Pour **Paramètres de sortie du modèle**, modifiez l’une des valeurs suivantes :
   - **Nom de l’entité** pour les résultats de sortie du pipeline
   - **Nom du paramètre du magasin de données de sortie** de votre pipeline par lots
   - **Nom du paramètre du chemin de sortie** de votre pipeline par lots

1. Modifiez l’attribut correspondant dans **ID de client dans les résultats** pour identifier les clients. Choisissez un attribut dans la sortie d’inférence avec des valeurs similaires à la colonne ID de client de l’entité Client. Si cette colonne n’est pas présente dans votre ensemble de données, choisissez un attribut qui identifie de manière unique la ligne.

1. Sélectionnez **Enregistrer**

### <a name="delete-a-workflow"></a>Supprimer un flux de travail

1. Accédez à **Intelligence** > **Modèles personnalisés**.

1. En regard du workflow que vous souhaitez supprimer, sélectionnez les points de suspension verticaux (&vellip;) et sélectionnez **Supprimer**.

1. Confirmez votre suppression.

Votre workflow sera supprimé. L’[entité](entities.md) qui a été créée lorsque vous avez créé le workflow persiste et peut être visualisée à partir de la page **Données** > **Entités**.

## <a name="view-the-results"></a>Afficher les résultats

Les résultats d’un workflow sont stockés dans le nom de l’entité défini pour les **Paramètres de sortie du modèle**. Accédez à ces données à partir de la page [**Données** > **Entités**](entities.md) ou avec l’[accès de l’API](apis.md).

### <a name="api-access"></a>Accès API

Pour que la requête OData spécifique récupère les données d’une entité de modèle personnalisé, utilisez le format suivant :

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Remplacez `<your instance id>` par l’ID de votre environnement Customer Insights, qui s’affiche dans la barre d’adresse de votre navigateur lorsque vous accédez à Customer Insights.

1. Remplacez `<custom model output entity>` par le nom d’entité que vous avez fourni pour les **Paramètres de sortie du modèle**.

1. Remplacez `<guid value>` par l’ID du client auquel vous souhaitez accéder. Cet ID s’affiche sur la [page des profils client](customer-profiles.md) dans le champ CustomerID.

## <a name="frequently-asked-questions"></a>Forums Aux Questions

- Pourquoi ne puis-je pas voir mon pipeline lors de la configuration d’un workflow de modèle personnalisé ?
  Ce problème est souvent causé par un problème de configuration dans le pipeline. Assurez-vous que le [paramètre d’entrée est configuré](azure-machine-learning-experiments.md#dataset-configuration), et que [le magasin de données de sortie et les paramètres du chemin](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) sont également configurés.

- Que signifie l’erreur « Impossible d’enregistrer le workflow d’intelligence » ? 
  Les utilisateurs voient généralement ce message d’erreur s’ils ne disposent pas des privilèges d’administrateur pour l’accès propriétaire ou utilisateur sur l’espace de travail. L’utilisateur a besoin d’un niveau d’autorisations plus élevé pour permettre à Customer Insights de traiter le workflow en tant que service plutôt que d’utiliser les informations d’identification de l’utilisateur pour les exécutions suivantes du workflow.

- Un point de terminaison privé/lien privé pour mon workflow de modèle personnalisé est-il pris en charge ?
  Customer Insights ne prend pas actuellement en charge le point de terminaison privé pour les modèles personnalisés prédéfinis, mais une solution de contournement manuelle est disponible. Contactez le support pour obtenir des détails.

## <a name="responsible-ai"></a>IA responsable

Les prédictions offrent des fonctionnalités pour créer de meilleures expériences client, améliorer les fonctionnalités métier et les flux de revenus. Nous vous recommandons fortement d’équilibrer la valeur de votre prédiction par rapport à son impact et aux tendances qui peuvent être introduites de manière éthique. En savoir plus sur la manière dont Microsoft [gère l’IA responsable](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Vous pouvez également découvrir les [techniques et processus pour un apprentissage automatique responsable](/azure/machine-learning/concept-responsible-ml) spécifique à Azure Machine Learning.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
