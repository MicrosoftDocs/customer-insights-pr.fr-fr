---
title: Afficher et créer des mesures
description: Création, modification et suppression de mesures.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: e220e53ced2f731a21aa7100bad0ad0577910b86
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555580"
---
# <a name="view-and-create-metrics"></a>Afficher et créer des mesures

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Les mesures aident à comprendre le comportement de vos visiteurs. Elles agrègent les propriétés des événements et mesurent les statistiques et les performances de vos propriétés web.  

Supposons que vous organisiez une promotion marketing sur votre site web. Vous pouvez utiliser des mesures pour suivre le nombre de visiteurs ou d'utilisateurs uniques qui sont venus sur votre site web pendant la promotion. L'analyse des mesures vous aide à mieux comprendre l'audience de votre site web. Le fait de combiner des mesures avec des [dimensions](dimensions.md) sur un [rapport personnalisé](custom-reports.md) vous permet de mesurer le comportement pour comprendre vos utilisateurs. Par exemple, vous pouvez séparer les visiteurs en deux catégories, les nouveaux et ceux qui reviennent, pour identifier les différences d'intérêt et d'intention entre les groupes.

## <a name="view-metrics"></a>Afficher les mesures

Les informations sur l'engagement incluent des agrégations de propriétés d'événement couramment utilisées en tant que mesures système : 

- Visiteurs
- Visites
- Vues de pages
- Clics

Ces mesures système sont basées sur les propriétés d'événement existantes dans les événements de base.

1. Accédez à **Données** dans le volet de navigation de gauche. 
1. Sélectionnez l'onglet **Mesures** pour afficher une liste de toutes les mesures dans l'espace de travail. 
   > [!NOTE]
   > Les mesures générées par le système sont en lecture seule. Vous ne pouvez pas les modifier ni les supprimer. Vous ne pouvez créer et modifier que des mesures personnalisées.

## <a name="create-a-metric"></a>Créer une mesure

Les administrateurs d'environnement et d'espace de travail peuvent créer des mesures. Les propriétés d'événement doivent être envoyées à l'espace de travail avant qu'une mesure soit créée. Vous pouvez créer des mesures basées sur les propriétés d'événement envoyées par les événements de base ou utiliser le SDK web pour [envoyer des propriétés d'événement personnalisées](advanced-SDK-implementation.md).

1. Accédez à **Données** > **Mesures**.
1. Sélectionnez **Nouvelle mesure**.

   :::image type="content" source="media/new-metric.png" alt-text="Ajouter une mesure à un événement.":::

1. Pour le format, sélectionnez le type de données **Entier** ou **Double**. Entier est un nombre entier. Pour Double, vous pouvez choisir entre une et trois décimales.
1. Dans le volet **Bibliothèque de ressources**, recherchez la propriété d'événement sur laquelle baser la mesure.
1. Sélectionnez le **signe plus (+)** à côté de la propriété pour l'utiliser dans la formule. Vous ne pouvez créer qu'une formule basée sur une seule propriété. 
1. Choisissez l'une des fonctions d’agrégation suivantes : 

   - Somme : le total arithmétique de toutes les valeurs 
   - Moyenne : la moyenne de toutes les valeurs
   - Nombre : le nombre total de valeurs
   - Nombre distinct : le nombre total de valeurs distinctes

   Après avoir défini la mesure, vous voyez un aperçu de l'activité de la mesure au cours de l'heure qui vient de s'écouler.

1. Sélectionnez **Enregistrer**. 
1. Entrez un nom pour la mesure et sélectionnez **Enregistrer**.

Une minute peut être nécessaire avant que vous puissiez utiliser la mesure pour [créer des rapports personnalisés](custom-reports.md).

## <a name="edit-a-metric"></a>Modifier une métrique

1. Accédez à **Données** > **Mesures**.
1. Sélectionnez la mesure dans la liste.
1. Modifier la définition de la mesure
1. Sélectionnez **Enregistrer**.

## <a name="change-the-name-of-a-metric"></a>Modifier le nom d’une mesure

1. Accédez à **Données** > **Mesures**.
1. Sélectionnez **Plus [...]** pour une mesure et choisissez **Modifier le nom**.
1. Changez le nom. 
1. Sélectionnez **Renommer**.

## <a name="delete-a-metric"></a>Supprimer une mesure

1. Accédez à **Données** > **Mesures**.
1. Sélectionnez **Plus [...]** pour une mesure et choisissez **Supprimer**.

   :::image type="content" source="media/delete-metric.png" alt-text="Supprimer une mesure d'un événement.":::

1. Sélectionnez **Supprimer** pour confirmer la suppression.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
