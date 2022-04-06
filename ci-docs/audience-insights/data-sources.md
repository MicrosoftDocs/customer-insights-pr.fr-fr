---
title: Utiliser des sources de données pour ingérer des données
description: Découvrez comment importer des données depuis des sources diverses.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 9cf97c3e30d7501ba1f188a0e25a1a103299aa7f
ms.sourcegitcommit: a8e99cf8b23ccc00d76c1dee22afd808a160a5c8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2022
ms.locfileid: "8464046"
---
# <a name="data-sources-overview"></a>Vue d’ensemble des sources de données



La fonctionnalité d’informations sur l’audience de Dynamics 365 Customer Insights se connecte aux données d’un large éventail de sources. La connexion à une source de données est souvent appelée processus d’*ingestion de données*. Après avoir ingéré les données, vous pouvez les [unifier](data-unification.md) et agir dessus.

## <a name="add-a-data-source"></a>Ajouter une source de données

Consultez les articles détaillés pour savoir comment ajouter une source de données, en fonction de l’option que vous choisissez.

Vous pouvez ajouter les sources de données suivantes :

- [Parmi des dizaines de connecteurs Power Query](connect-power-query.md)
- [À partir d’un dossier Common Data Model](connect-common-data-model.md)
- [À partir de votre propre lac Microsoft Dataverse](connect-dataverse-managed-lake.md)
- [À partir d’une base de données Azure Synapse Analytics](connect-synapse.md)

> [!NOTE]
> Si vous utilisez la version d’essai, la section des méthodes d’importation comprend une option **Bibliothèque de données Customer Insights**. Choisissez cette option pour sélectionner un exemple de jeu de données disponible pour divers secteurs d’activité. Pour plus d’informations, consultez [Version d’essai de Dynamics 365 Customer Insights](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Ajouter des données de sources de données locales

L’ingestion de données à partir de sources de données locales dans Audience Insights est prise en charge en fonction des flux de données Microsoft Power Platform. Vous pouvez activer les flux de données dans Customer Insights en [fournissant l’URL de l’environnement Microsoft Dataverse](create-environment.md) lors de la configuration de l’environnement.

Les sources de données créées après avoir associé un environnement Dataverse à Customer Insights utilisent les [flux de données Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) par défaut. Les flux de données prennent en charge la connectivité locale à l’aide de la passerelle de données. Vous pouvez supprimer et recréer des sources de données qui existaient avant l’association d’un environnement Dataverse [en utilisant les passerelles de données locales](/data-integration/gateway/service-gateway-app).

Les passerelles de données d’un environnement Power BI ou Power Apps existant seront visibles et vous pourrez les réutiliser dans Customer Insights. La page des sources de données affiche des liens pour accéder à l’environnement Microsoft Power Platform dans lequel vous pouvez afficher et configurer les passerelles de données locales.

> [!IMPORTANT]
> Assurez-vous que vos passerelles sont mises à jour vers la version la plus récente. Vous pouvez installer une mise à jour et reconfigurer une passerelle à partir d’une invite affichée sur l’écran de la passerelle directement ou [télécharger la version la plus récente](https://powerapps.microsoft.com/downloads/). Si vous n’utilisez pas la version la plus récente de la passerelle, l’actualisation du flux de données échoue avec des messages d’erreur comme **Le mot clé n’est pas pris en charge : propriétés de configuration. Nom du paramètre : mot clé**.

## <a name="review-ingested-data"></a>Évaluer les données ingérées
Si votre environnement contient des flux de données Power Platform, la page **Sources de données** répertorie trois sections : 
- **Partagé** : sources de données qui peuvent être gérées par tous les administrateurs Customer Insights. Les flux de données Power BI, votre propre compte de stockage et la connexion à un lac de données géré par Dataverse sont des exemples de sources de données partagées.
- **Géré par moi** : flux de données Power Platform créés qui ne peuvent être gérés que par vous. Les autres administrateurs Customer Insights peuvent uniquement visualiser ces flux de données, mais pas les modifier, les actualiser ou les supprimer.
- **Géré par d’autres** : flux de données Power Platform créés par d’autres administrateurs. Vous ne pouvez que les visualiser. Elle répertorie le propriétaire du flux de données à contacter pour obtenir de l’aide.
> [!NOTE]
> Toutes les entités peuvent être visualisées et utilisées par d’autres utilisateurs. La contextualité de l’utilisateur s’applique uniquement aux sources de données et non aux entités qui résultent de ces flux de données.

Si aucun flux de données Power Platform n’est utilisé, vous ne verrez aucun groupe ni section. La page **Sources de données** contient uniquement une liste de toutes les sources de données.

Vous avez accès au nom de chaque source de données ingérée, à son statut et à la dernière date d’actualisation des données pour cette source de données. Vous pouvez trier la liste des sources de données par colonne.

> [!div class="mx-imgBorder"]
> ![Source de données ajoutée.](media/configure-data-datasource-added.png "Source de données ajoutée")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Le chargement des données peut prendre du temps. Après une actualisation réussie, les données ingérées peuvent être consultées à partir de la page **Entités**. Pour plus d’informations, voir [Entités](entities.md).

## <a name="refresh-a-data-source"></a>Actualiser une source de données

Les sources de données peuvent être actualisées selon un calendrier automatique ou actualisées manuellement à la demande. 

Accédez à **Administration** > **Système** > [**Planification**](system.md#schedule-tab) pour configurer des actualisations programmées de toutes vos sources de données ingérées.

Pour actualiser une source de données à la demande, procédez comme suit :

1. Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.

2. Sélectionnez les points de suspension verticaux en regard de la source de données que vous souhaitez actualiser et sélectionnez **Actualiser** dans la liste déroulante.

3. La source de données est maintenant déclenchée pour une actualisation manuelle. Si vous actualisez une source de données, à la fois le schéma de l’entité et les données seront mis à jour pour toutes les entités spécifiées dans la source de données.

4. Sélectionnez **Arrêtez l’actualisation** si vous souhaitez annuler une actualisation existante et rétablir le dernier statut d’actualisation de la source de données.

## <a name="delete-a-data-source"></a>Supprimer une source de données

1. Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.

2. Sélectionnez les points de suspension verticaux en regard de la source de données que vous souhaitez supprimer et sélectionnez **Supprimer** dans le menu déroulant.

3. Confirmez votre suppression.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
