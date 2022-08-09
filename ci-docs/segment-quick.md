---
title: Créer des segments simples avec des segments rapides
description: Créez des segments simples de clients pour les regrouper en fonction de divers attributs.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171132"
---
# <a name="create-simple-segments-with-quick-segments"></a>Créer des segments simples avec des segments rapides

Les segments rapides vous permettent de créer rapidement des segments simples avec un seul opérateur pour des informations plus rapides. Les segments rapides ne sont pris en charge que dans les environnements pour les **clients particuliers**.

## <a name="create-a-new-segment-with-quick-segments"></a>Créer un nouveau segment avec des segments rapides

1. Accédez à **Segments**.

1. Sélectionnez **Nouveau** > **Créer à partir de**.
   - Sélectionnez l’option **Profils** pour créer un segment basé sur l’entité *client unifié*.
   - Sélectionnez l’option **Mesures** pour créer un segment autour des mesures que vous avez précédemment créées.
   - Sélectionnez l’option **Intelligence** pour créer un segment autour de l’une des entités de sortie que vous avez générées à l’aide des fonctionnalités **Prédictions** ou **Modèles personnalisés**.

1. Dans la boîte de dialogue **Nouveau segment rapide**, sélectionnez un attribut dans la liste déroulante **Champ**. En fonction de votre sélection, le système propose différentes valeurs.
   - Pour les champs de catégorie, les 10 meilleurs clients sont affichés. Choisissez une **Valeur** et sélectionnez **Réviser**.
   - Pour un attribut numérique, le système affiche la valeur d’attribut correspondant au centile de chaque utilisateur. Choisissez un **Opérateur** et une **Valeur**, puis sélectionnez **Réviser**.

1. Le système fournit une **taille estimée du segment**. Choisissez de générer le segment que vous avez défini ou revenez en arrière pour choisir un autre champ.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nom et estimation pour un segment rapide.":::

1. Fournissez un **Nom** et un **Nom de l’entité de sortie** pour votre segment. Si nécessaire, ajoutez des [étiquettes](work-with-tags-columns.md#manage-tags).

1. Sélectionnez **Enregistrer** pour créer votre segment. La page **Segments** s’affiche.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Étapes suivantes

[Exportez un segment](export-destinations.md) et explorez l’[intégration de la carte client](customer-card-add-in.md) pour utiliser les segments dans d’autres applications.

[!INCLUDE [footer-include](includes/footer-banner.md)]
