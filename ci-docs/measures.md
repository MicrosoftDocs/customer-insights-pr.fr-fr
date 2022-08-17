---
title: Vue d’ensemble des mesures
description: Découvrez comment les mesures permettent d’analyser et de révéler les performances de votre entreprise.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245370"
---
# <a name="measures-overview"></a>Vue d’ensemble des mesures

Les mesures vous aident à mieux comprendre les comportements des clients et les performances commerciales. Elles examinent les valeurs pertinentes des [profils unifiés](data-unification.md). Par exemple, une entreprise veut voir les *des dépenses totales par client* pour comprendre l’historique des achats d’un client individuel ou mesurer les *ventes totales de l’entreprise* pour comprendre les revenus au niveau agrégé dans l’ensemble de l’entreprise.

Créez des mesures pour planifier les activités commerciales en interrogeant les données client et en extrayant des informations. Par exemple, créer une mesure de *total des dépenses par client* et de *total des retours par client* permet d’identifier un groupe de clients avec des dépenses élevées mais un rendement élevé. Ensuite, [créez un segment](segments.md) sur la base de ces mesures pour orienter les prochaines meilleures actions.

## <a name="create-a-measure"></a>Créer une mesure

Choisissez comment créer une mesure basée sur votre audience cible.

# <a name="individual-consumers-b-to-c"></a>[Consommateurs individuels (B-to-C)](#tab/b2c)

- À partir de rien avec le créateur de mesures : [créez le vôtre](measure-builder.md).
- À partir de mesure couramment utilisées : [utilisez des modèles prédéfinis](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Comptes d’entreprise (B-to-B)](#tab/b2b)

À partir de rien avec le créateur de mesures : [créez le vôtre](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Gérer les mesures existantes

Accédez à la page **Mesures** pour afficher les mesures que vous avez créées, leur état, le type de mesure et la dernière fois que les données ont été actualisées. Vous pouvez trier la liste des mesures par colonne ou utiliser la zone de recherche pour trouver la mesure que vous souhaitez gérer.

Sélectionnez en regard d’une mesure pour afficher les actions disponibles. Sélectionnez le nom de la mesure pour prévisualiser la sortie et télécharger un fichier CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Actions pour gérer des mesures uniques."lightbox="media/measures-actions.png":::

- **Modifier** la mesure pour modifier ses propriétés.
- **Actualiser** la mesure pour inclure les dernières données.
- **Renommer** la mesure.
- **Activer** ou **Désactiver** la mesure. Les mesures inactives ne seront pas actualisées pendant une [actualisation planifiée](schedule-refresh.md) et auront le **statut** **Ignoré**, indiquant qu’aucune actualisation n’a été tentée.
- **Étiquette** pour [gérer les étiquettes](work-with-tags-columns.md#manage-tags) de la mesure.
- **Supprimer** la mesure.
- **Colonnes** pour [personnaliser les colonnes](work-with-tags-columns.md#customize-columns) qui s’affichent.
- **Filtrer** pour [filtrer selon les étiquettes](work-with-tags-columns.md#filter-on-tags).
- **Rechercher un nom** pour effectuer une recherche par nom de mesure.

## <a name="refresh-measures"></a>Actualiser les mesures

Les mesures peuvent être actualisées selon un calendrier automatique ou actualisées manuellement à la demande. Pour actualiser manuellement un ou plusieurs mesures, sélectionnez-les et choisissez **Actualiser**. Pour [planifier une actualisation automatique](schedule-refresh.md), accédez à **Administrateur** > **Système** > **Planification**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
