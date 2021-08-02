---
title: Afficher et créer des segments
description: Comment créer, modifier et supprimer des segments et où les utiliser.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 47d9635e02a855606cf0cdf0d4422220c97c5d32
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305843"
---
# <a name="view-and-create-segments"></a>Afficher et créer des segments

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Les segments vous permettent d'identifier des sous-ensembles de visiteurs en fonction de caractéristiques ou d'interactions avec le site web. Les segments vous permettent d'appliquer des filtres et d'analyser ces sous-ensembles. L'analyse peut aider à examiner et à répondre aux tendances de votre entreprise. 

:::image type="content" source="media/segments-page.png" alt-text="Capture d'écran de l'application des informations sur l’engagement affichant la liste des segments existants dans un espace de travail.":::

## <a name="view-segments"></a>Afficher les segments

1. Accédez à **Données** dans le volet de navigation de gauche. 

1. Sélectionnez l'onglet **Segments** pour afficher une liste de tous les segments de l'espace de travail. 

## <a name="create-a-segment"></a>Créer un segment

Les segments sont constitués de règles et de conditions liées à des opérateurs logiques. Les conditions appliquent des filtres à une dimension sélectionnée. Chaque segment peut utiliser jusqu'à cinq dimensions.

L'exemple suivant montre un segment avec deux conditions dans une seule règle. Il filtre tous les événements du site web pour lesquels le navigateur est Chrome et les systèmes d'exploitation sont iOS ou Android.

:::image type="content" source="media/segment-sample.png" alt-text="Exemples de segments avec deux conditions dans une règle pour filtrer les événements de site web.":::

Cette section décrit comment créer un *segment vide* à partir de zéro.

1. Accédez à **Données** > **Segments**.

1. Sélectionnez **Nouveau segment**.

1. Dans la **Bibliothèque de ressources**, choisissez l'attribut qui servira pour le filtre. Actuellement, vous pouvez créer uniquement des segments basés sur des dimensions.

1. Choisissez un opérateur et une valeur pour l’attribut sélectionné. Les opérations suivantes sont prise en charge.
   - **est** : nécessite une correspondance exacte pour inclure les valeurs. Utilise **égal à** pour une valeur unique ou **n'importe quel** pour inclure plusieurs valeurs.
   - **n'est pas** : nécessite une correspondance exacte pour exclure les valeurs. Utilise **égal à** pour une valeur unique ou **n'importe quel** pour inclure plusieurs valeurs.
   - **commence par** : chaîne par laquelle commencent les valeurs correspondantes.
   - **se termine par** : chaîne par laquelle se terminent les valeurs correspondantes.
   - **contient** : chaîne contenue dans les valeurs correspondantes.

1. Pour ajouter d'autres conditions à un groupe, vous pouvez utiliser deux opérateurs logiques. Les attributs projetés sont pris en compte lors de l’utilisation d’opérateurs définis.
   - Opérateur **ET** : Les deux conditions doivent être remplies dans le cadre du processus de segmentation. Cette option est particulièrement utile lorsque vous définissez des conditions sur différentes entités.
   - Opérateur **OU** : L’une ou l’autre des conditions doit être satisfaite dans le cadre de le processus de segmentation. Cette option est très utile lorsque vous définissez plusieurs conditions pour la même entité.

1. Sélectionnez **Enregistrer** et nommez le segment. 

Le segment sera répertorié sur la page Segments et vous pourrez l'appliquer à tous les rapports et synthèses de conversion de l'espace de travail.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Utiliser un segment dans un rapport ou une synthèse

Vous pouvez appliquer des segments à un rapport ou à une synthèse pour les filtrer en fonction des conditions du segment. Cependant, vous ne pouvez pas appliquer de segments au rapport d'utilisation en temps réel.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Rapport de vues de page avec une liste déroulante développée pour choisir les segments à appliquer.":::

Pour appliquer un segment, ouvrez le rapport ou la synthèse. Sélectionnez **Ajouter une condition** et choisissez **Filtrer par segment**. Choisissez le segment dans la liste que vous souhaitez appliquer. Le segment est appliqué au rapport. Si un graphique ne prend pas en charge le segment, une erreur s'affiche.
 
Vous pouvez appliquer *jusqu'à trois segments* à un rapport ou à une synthèse.

## <a name="edit-a-segment"></a>Modifier un segment

1. Accédez à **Données** > **Segments**.
1. Sélectionnez le segment dans la liste pour l'ouvrir. 
1. Modifiez ou ajoutez des valeurs selon vos besoins.
1. Sélectionnez **Enregistrer** pour appliquer vos modifications.

## <a name="change-the-name-of-a-segment"></a>Modifier le nom d’un segment

1. Accédez à **Données** > **Segments**.
1. Dans la liste des segments, sélectionnez **Plus [...]**. 
1. Dans la liste déroulante, choisissez **Modifier le nom**.
1. Entrez le nouveau nom et sélectionnez **Renommer**.

## <a name="delete-a-segment"></a>Supprimer un segment

1. Accédez à **Données** > **Segments**.
1. Dans la liste des segments, sélectionnez **Plus [...]**. 
1. Dans la liste déroulante, choisissez **Supprimer**.
1. Sélectionnez **Supprimer** pour confirmer.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
