---
title: Utiliser des sources de données pour ingérer des données
description: Découvrez comment importer des données depuis des sources diverses.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: e22977107565a0b28b74f41576a1c7ccc74f6dc1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011746"
---
# <a name="data-sources-overview"></a>Vue d’ensemble des sources de données

Dynamics 365 Customer Insights fournit des connexions pour apporter des données à partir d'un large éventail de sources. La connexion à une source de données est souvent appelée processus d’*ingestion de données*. Après avoir ingéré les données, vous pouvez [unifier](data-unification.md), générer des informations et activer les données pour créer des expériences personnalisées.

## <a name="add-data-sources"></a>Ajouter des sources de données

Vous pouvez joindre ou importer des sources de données dans Customer Insights. Les liens ci-dessous fournissent des instructions sur l'ajout de sources de données.

**Joindre une source de données**

Si vous avez des données préparées dans l'un des services de données Azure de Microsoft, Customer Insights peut facilement se connecter au source de données sans avoir à réingérer les données. Sélectionnez l’une des options suivantes :
- [Azure Data Lake Storage (fichiers csv ou parquet dans un dossier Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics (Bases de données Data Lake)](connect-synapse.md)
- [Lac de données Microsoft Dataverse](connect-dataverse-managed-lake.md)

**Importer et transformer**

Si vous utilisez des sources de données sur site, Microsoft ou des données tierces, importez et transformez les données à l'aide de connecteurs Power Query.
- [Connecteurs Power Query](connect-power-query.md)

## <a name="review-data-sources"></a>Évaluer les sources de données

Si votre environnement a été configuré pour utiliser le stockage Customer Insights et que vous utilisez des sources de données sur site, vous utilisez les flux de données Power Platform. Avec les flux de données Power Platform, vous pouvez afficher les sources de données partagées et les sources de données gérées par d'autres. La page **Source de données** répertorie les sources de données en trois sections :
- **Partagé** : sources de données qui peuvent être gérées par tous les administrateurs Customer Insights. Les flux de données Power Platform, votre propre compte de stockage et la connexion à un lac de données géré par Dataverse sont des exemples de sources de données partagées.
- **Géré par moi** : flux de données Power Platform créés et gérés que par vous. Les autres administrateurs Customer Insights peuvent uniquement visualiser ces flux de données, mais pas les modifier, les actualiser ou les supprimer.
- **Géré par d’autres** : flux de données Power Platform créés par d’autres administrateurs. Vous ne pouvez que les visualiser. Elle répertorie le propriétaire du flux de données à contacter pour obtenir de l’aide.
> [!NOTE]
> Toutes les entités peuvent être visualisées et utilisées par d’autres utilisateurs. Alors que les sources de données appartiennent à l'utilisateur qui les a créées, les entités résultant de l'ingestion de données peuvent être utilisées par chaque utilisateur de Customer Insights.

Si votre environnement n'utilise pas les flux de données Power Platform, la page **Source d'information** contient uniquement une liste de toutes les sources de données. Aucune section affichée.

Accédez à **Données** > **Source de données** pour afficher le nom de chaque source de données ingérée, son statut, ainsi que la dernière fois que les données ont été actualisées pour cette source. Vous pouvez trier la liste des sources de données par colonne.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Source de données ajoutée.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Le chargement des données peut prendre du temps. Après une actualisation réussie, les données ingérées peuvent être consultées à partir de la page **Entités**. Pour plus d’informations, voir [Entités](entities.md).

## <a name="refresh-data-sources"></a>Actualiser les sources de données

Les sources de données peuvent être actualisées selon un calendrier automatique ou actualisées manuellement à la demande. Les [Sources de données sur site](connect-power-query.md#add-data-from-on-premises-data-sources) s'actualisent selon leurs propres horaires qui sont configurés lors de l'ingestion de données. Pour les sources de données attachées, l'ingestion de données utilise les dernières données disponibles à partir de ce source de données.

Accédez à **Administrateur** > **Système** > [**Programme**](system.md#schedule-tab) pour configurer les actualisations planifiées par le système de vos sources de données ingérées.

Pour actualiser une source de données à la demande, procédez comme suit :

1. Accédez à **Données** > **Sources de données**.

1. Sélectionnez les points de suspension verticaux (&vellip;) en regard de la source de données à actualiser et sélectionnez **Actualiser** dans la liste déroulante. La source de données est maintenant déclenchée pour une actualisation manuelle. Si vous actualisez une source de données, à la fois le schéma de l’entité et les données seront mis à jour pour toutes les entités spécifiées dans la source de données.

1. Sélectionnez **Arrêtez l’actualisation** si vous souhaitez annuler une actualisation existante et rétablir le dernier statut d’actualisation de la source de données.

## <a name="delete-a-data-source"></a>Supprimer une source de données

Une source de données ne peut être supprimée que si les données ne sont utilisées dans aucun traitement tel que l'unification, les informations, les activations ou les exportations.

1. Accédez à **Données** > **Sources de données**.

2. Sélectionnez les points de suspension verticaux (&vellip;) en regard de la source de données à supprimer et sélectionnez **Supprimer** dans le menu déroulant.

3. Confirmez votre suppression.


[!INCLUDE [footer-include](includes/footer-banner.md)]
