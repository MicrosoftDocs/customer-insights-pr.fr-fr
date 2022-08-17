---
title: Vue d’ensemble des sources de données
description: Découvrez comment importer ou ingérer des données à partir de diverses sources.
ms.date: 07/26/2022
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
ms.openlocfilehash: 591353bf1ba2f9ca05ddd137e1cf29dc0b0fba97
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245646"
---
# <a name="data-sources-overview"></a>Vue d’ensemble des sources de données

Dynamics 365 Customer Insights fournit des connexions pour apporter des données à partir d'un large éventail de sources. La connexion à une source de données est souvent appelée processus d’*ingestion de données*. Après avoir ingéré les données, vous pouvez [unifier](data-unification.md), générer des informations et activer les données pour créer des expériences personnalisées.

## <a name="add-or-edit-data-sources"></a>Ajouter ou modifier des sources de données

Vous pouvez joindre ou importer des sources de données dans Customer Insights. Les liens ci-dessous fournissent des instructions sur l’ajout et la modification des sources de données.

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

## <a name="manage-existing-data-sources"></a>Gérer les sources de données existantes

Accédez à **Données** > **Source de données** pour afficher le nom de chaque source de données ingérée, son statut, ainsi que la dernière fois que les données ont été actualisées pour cette source. Vous pouvez trier la liste des sources de données par colonne ou utiliser la zone de recherche pour trouver la source de données que vous souhaitez gérer.

Sélectionnez une source de données pour afficher les actions disponibles.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Source de données ajoutée.":::

- [**Modifier**](#add-or-edit-data-sources) la source de données pour modifier ses propriétés.
- [**Actualiser**](#refresh-data-sources) la source de données pour inclure les dernières données.
- [**Enrichir**](data-sources-enrichment.md) la source de données avant l’unification.
- **Supprimer** la source de données. Une source de données ne peut être supprimée que si les données ne sont utilisées dans aucun traitement tel que l'unification, les informations, les activations ou les exportations.

## <a name="refresh-data-sources"></a>Actualiser les sources de données

Les sources de données peuvent être actualisées selon un calendrier automatique ou actualisées manuellement à la demande. Les [Sources de données sur site](connect-power-query.md#add-data-from-on-premises-data-sources) s'actualisent selon leurs propres horaires qui sont configurés lors de l'ingestion de données. Pour les sources de données attachées, l'ingestion de données utilise les dernières données disponibles à partir de ce source de données.

Accédez à **Administrateur** > **Système** > [**Programme**](schedule-refresh.md) pour configurer les actualisations planifiées par le système de vos sources de données ingérées.

Pour actualiser une source de données à la demande :

1. Accédez à **Données** > **Sources de données**.

1. Sélectionnez la source de données que vous souhaitez actualiser et sélectionnez **Actualiser**. La source de données est maintenant déclenchée pour une actualisation manuelle. Si vous actualisez une source de données, à la fois le schéma de l’entité et les données seront mis à jour pour toutes les entités spécifiées dans la source de données.

1. Sélectionnez le statut pour ouvrir le volet **Détails de la progression** et afficher la progression. Pour annuler la tâche, sélectionnez **Annuler la tâche** en bas du volet.

[!INCLUDE [footer-include](includes/footer-banner.md)]
