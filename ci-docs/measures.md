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
ms.openlocfilehash: 880c06bffcfa269151d96cb4c597eed4832fc61b
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081206"
---
# <a name="measures-overview"></a>Vue d’ensemble des mesures

Les mesures vous aident à mieux comprendre les comportements des clients et les performances commerciales. Elles examinent les valeurs pertinentes des [profils unifiés](data-unification.md). Par exemple, une entreprise veut voir les *des dépenses totales par client* pour comprendre l’historique des achats d’un client individuel ou mesurer les *ventes totales de l’entreprise* pour comprendre les revenus au niveau agrégé dans l’ensemble de l’entreprise.  

Les mesures sont créées [à l’aide du générateur de mesures](measure-builder.md), une plateforme de requête de données avec divers opérateurs et des options de mappage simples. Elle vous permet de filtrer les données, de regrouper les résultats, de détecter les [chemins d’accès aux relations d’entités](relationships.md) et prévisualisez la sortie. Vous pouvez [utiliser des modèles prédéfinis](measure-templates.md) pour configurer efficacement les mesures couramment utilisées.

Utilisez le générateur de mesures pour planifier les activités commerciales en interrogeant les données client et en extrayant des informations. Par exemple, créer une mesure de *total des dépenses par client* et de *total des retours par client* aide à identifier un groupe de clients avec des dépenses élevées mais un rendement élevé. Vous pouvez [créer un segment](segments.md) sur la base de ces mesures pour orienter les prochaines meilleures actions.

## <a name="manage-your-measures"></a>Gérer vos mesures

Vous trouverez la liste des mesures sur la page **Mesures**.

Vous trouverez des informations sur le type de mesure, le créateur, la date de création, le statut et l’état. Lorsque vous sélectionnez une mesure dans la liste, vous pouvez prévisualiser la sortie et télécharger un fichier CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Actions pour gérer des mesures uniques."lightbox="media/measures-actions.png":::

Les actions suivantes sont disponibles lorsque vous sélectionnez une mesure :

- **Modifier** la configuration de la mesure.
- **Dupliquer** une mesure. Vous pouvez choisir de modifier ses propriétés immédiatement ou simplement d’enregistrer le doublon.
- **Actualisez** la mesure basée sur les dernières données. Pour actualiser toutes vos mesures en même temps, sélectionnez toutes les mesures, puis **Actualiser**.
- **Renommer** la mesure.
- **Activer** ou **Désactiver**. Les mesures inactives ne seront pas actualisées pendant une [actualisation programmée](system.md#schedule-tab).
- **Étiquette** pour [gérer les étiquettes](work-with-tags-columns.md#manage-tags) du segment.
- **Supprimer** la mesure.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Étape suivante

Vous pouvez utiliser des mesures existantes pour créer un [segment de clients](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
