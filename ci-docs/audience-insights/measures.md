---
title: Comprendre et gérer les mesures
description: Découvrez comment les mesures permettent d’analyser et de révéler les performances de votre entreprise.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359775"
---
# <a name="measures-overview"></a>Vue d’ensemble des mesures

Les mesures vous aident à mieux comprendre les comportements des clients et les performances commerciales. Elles examinent les valeurs pertinentes des [profils unifiés](data-unification.md). Par exemple, une entreprise veut voir les *des dépenses totales par client* pour comprendre l’historique des achats d’un client individuel ou mesurer les *ventes totales de l’entreprise* pour comprendre les revenus au niveau agrégé dans l’ensemble de l’entreprise.  

Les mesures sont créées [à l’aide du générateur de mesures](measure-builder.md), une plateforme de requête de données avec divers opérateurs et des options de mappage simples. Elle vous permet de filtrer les données, de regrouper les résultats, de détecter les [chemins d’accès aux relations d’entités](relationships.md) et prévisualisez la sortie. Vous pouvez [utiliser des modèles prédéfinis](measure-templates.md) pour configurer efficacement les mesures couramment utilisées.

Utilisez le générateur de mesures pour planifier les activités commerciales en interrogeant les données client et en extrayant des informations. Par exemple, créer une mesure de *total des dépenses par client* et de *total des retours par client* aide à identifier un groupe de clients avec des dépenses élevées mais un rendement élevé. Vous pouvez [créer un segment](segments.md) sur la base de ces mesures pour orienter les prochaines meilleures actions. 

## <a name="manage-your-measures"></a>Gérer vos mesures

Vous trouverez la liste des mesures sur la page **Mesures**.

Vous trouverez des informations sur le type de mesure, le créateur, la date de création, le statut et l’état. Lorsque vous sélectionnez une mesure dans la liste, vous pouvez prévisualiser la sortie et télécharger un fichier CSV.

Pour actualiser toutes vos mesures en même temps, sélectionnez **Actualiser tout** sans sélectionner une mesure spécifique.

:::image type="content" source="media/measure-actions.png" alt-text="Actions pour gérer des mesures uniques.":::

Choisissez une mesure parmi la liste des options suivantes :

- Sélectionner le nom de la mesure pour afficher ses détails.
- **Modifier** la configuration de la mesure.
- **Actualisez** la mesure basée sur les dernières données.
- **Renommer** la mesure.
- **Supprimer** la mesure.
- **Activer** ou **Désactiver**. Les mesures inactives ne seront pas actualisées pendant une [actualisation programmée](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Étape suivante

Vous pouvez utiliser des mesures existantes pour créer un [segment de clients](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
