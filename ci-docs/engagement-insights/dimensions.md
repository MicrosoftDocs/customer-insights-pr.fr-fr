---
title: Afficher et créer des dimensions
description: Comment créer, modifier et supprimer des dimensions.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: d35c72f73d2f3e202ae3c5a5ef26e9db89360084
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226300"
---
# <a name="view-and-create-dimensions"></a>Afficher et créer des dimensions

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Une dimension est un attribut d'un événement qui peut décrire, filtrer et regrouper des données. Si vous organisez une promotion marketing sur votre site web, vous pouvez utiliser des dimensions pour trier les visiteurs par utilisateurs nouveaux et utilisateurs existants.  

Les informations sur l’engagement incluent des dimensions prêtes à l’emploi pour les propriétés de l’événement. Voici des exemples :

- Nom du navigateur
- Nom de la page
- Modèle du périphérique
- Système d’exploitation
- Pays

## <a name="view-dimensions"></a>Afficher les dimensions

Les dimensions sont basées sur les propriétés d'événement existantes. Lorsque vous utilisez le code de suivi pour les informations sur l'engagement, les dimensions du système sont automatiquement créées.

1. Accédez à **Données** dans le volet de navigation de gauche. 
1. Sélectionnez **Dimensions** pour afficher une liste de toutes les dimensions de l'espace de travail. 
   > [!NOTE]
   > Les dimensions générées par le système sont en lecture seule. Vous ne pouvez pas les modifier. Vous pouvez uniquement créer et modifier des dimensions personnalisées.

## <a name="create-a-dimension"></a>Créer une dimension

En plus des dimensions générées par le système, les administrateurs de l'environnement et de l'espace de travail peuvent créer des dimensions personnalisées. Les dimensions personnalisées sont basées sur les propriétés par défaut des événements de base ou peuvent utiliser les [propriétés personnalisées d'un événement](advanced-SDK-implementation.md).

1. Accédez à **Données** > **Dimensions**.
1. Sélectionnez **Nouvelle dimension**.

   :::image type="content" source="media/add-dimension.png" alt-text="Ajouter une dimension à un événement.":::

1. Dans le volet **Créer une dimension**, sélectionnez une propriété sur laquelle baser la dimension. La liste des propriétés affichera toutes les propriétés de l'espace de travail non affectées à une dimension.
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="Créez une dimension.":::
      
3. Entrez un nom descriptif dans la zone **Nom d'affichage**. Vous pouvez également ajouter une **Description**.
4. Sélectionnez **Créer** pour enregistrer la dimension. Cela peut prendre jusqu'à une minute avant que vous puissiez utiliser la dimension dans un [rapport personnalisé](custom-reports.md) ou dans un [segment](segments.md). 

## <a name="edit-a-dimension"></a>Modifier une dimension

Vous pouvez modifier le nom et la description d'une dimension. Vous ne pouvez modifier que les dimensions créées par l’utilisateur, mais vous ne pouvez pas modifier les dimensions système.


1. Accédez à **Données** > **Dimensions**.
1. Sélectionnez la dimension à supprimer.
1. Dans le volet **Modifier la dimension**, mettez à jour la dimension.
1. Sélectionnez **Appliquer** pour appliquer vos modifications.

## <a name="delete-a-dimension"></a>Supprimer une dimension

Vous ne pouvez supprimer que les dimensions créées par l'utilisateur, mais vous ne pouvez pas supprimer les dimensions du système.

La suppression d'une dimension est définitive. Les rapports et les segments qui utilisent une dimension supprimée ne fonctionneront plus. 

1. Accédez à **Données** > **Dimensions**.
1. Sélectionnez la dimension à supprimer.
1. Dans le volet **Modifier la dimension**, sélectionnez **Supprimer la dimension**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Supprimer une dimension d'un événement.":::

1. Saisissez **CONFIRMER LA SUPPRESSION** (en majuscules) pour confirmer la suppression. 
1. Sélectionnez **Supprimer**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
