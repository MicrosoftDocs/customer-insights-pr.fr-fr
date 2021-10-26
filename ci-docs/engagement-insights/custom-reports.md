---
title: À propos des rapports personnalisés
description: Découvrez comment créer et personnaliser des rapports.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3fa801bfc8b0aee65c21b90de2423a3d5d5e4e26
ms.sourcegitcommit: d9965f4bfc09391698a34042f6b44367e53819e3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "7582874"
---
# <a name="create-and-edit-custom-reports"></a>Créer et modifier des rapports personnalisés

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Outre les rapports prédéfinis, vous pouvez créer un rapport personnalisé avec des visualisations de graphiques et de tables pour vous aider à comprendre le comportement de l’utilisateur. Cet article explique comment créer un rapport avec les données dont vous avez besoin à l'aide de visualisations de tableau et de graphique. Pour plus d’informations sur les rapports prédéfinis, consultez [Afficher les rapports](view-reports.md).

## <a name="create-a-custom-report"></a>Créer un rapport personnalisé

1. Allez dans **Analyser** > **Personnaliser** pour accéder à la liste des rapports personnalisés.

1. Sélectionnez **Nouveau rapport** pour commencer à créer un rapport personnalisé.

   :::image type="content" source="media/new-custom-report.png" alt-text="Nouveaux rapports personnalisés.":::

1. Choisissez le type de rapport à créer :

    - Sélectionnez **Ajouter un visuel** dans la barre de commandes pour créer une visualisation de table par défaut.
    - Vous pouvez également sélectionner une colonne, une barre, une ligne, une zone, un secteur, un anneau ou une visualisation de table dans le volet **Éditeur de rapport**.

1. Dans la section **Données** du volet **Éditeur de la visualisation**, choisissez l’une des options disponibles (par exemple, consultations de pages) dans le menu déroulant **Métriques**. Vous pouvez également ajouter **Dimensions** (par exemple, pays) à afficher sur la visualisation. Pour plus d’informations, consultez [Afficher et créer des métriques](metrics.md) et [Afficher et créer des dimensions](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Choisissez une métrique pour votre rapport.":::

1. Sélectionnez la section **Conception** du volet **Éditeur de visualisation** pour ajouter le **Texte du titre** et activez ou désactivez le **Titre**.  Vous pouvez également modifier le type de visualisation en sélectionnant un autre graphique, tel qu’un **graphique en secteurs**.

1. Pour modifier la taille et la position d’une visualisation :
   - Sélectionnez la visualisation, puis faites glisser l'un des coins ou des bordures pour ajuster sa taille.
   - Sélectionnez la visualisation et déplacez-la vers une nouvelle position. Vous pouvez également utiliser les touches fléchées pour modifier la position.
1. Pour ajouter une autre visualisation, sélectionnez **Ajouter un effet visuel** dans la barre de commandes.
1. Après avoir ajouté les visualisations souhaitées pour le rapport, sélectionnez **Enregistrer** dans la barre de commandes.

1. Donnez un nom au rapport personnalisé et sélectionnez **Enregistrer** pour le créer.
 
## <a name="filter-a-custom-report"></a>Filtrer un rapport personnalisé

Vous pouvez sélectionner le délai d’exécution ou une plage de dates dans un rapport personnalisé pour vous concentrer sur une valeur ou une période.

Pour sélectionner un délai d’exécution, dans le coin supérieur droit de la vue du rapport, sélectionnez une valeur dans la liste déroulante du rapport. Vous pouvez également choisir une **Plage de dates fixe*.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Filtrez par période ou plage de dates.":::

Pour la plupart des rapports, sélectionnez **+ Ajouter une condition**, pour choisir une dimension ou un segment pour filtrer le rapport. Pour plus d’informations, consultez [Afficher et créer des segments](segments.md).

## <a name="edit-a-custom-report"></a>Modifier un rapport personnalisé

1. Allez dans **Analyser** > **Personnaliser** pour accéder à la liste des rapports personnalisés.

1. Dans la liste des rapports personnalisés, sélectionnez **Plus [...]** 

1. Choisissez **Modifier le nom** pour changer le nom du rapport.

1. Sélectionnez le nom du rapport et utilisez les options **+ Ajouter un visuel** et **Modifier** pour ajouter, supprimer, repositionner ou redimensionner les visualisations.

1. Pour modifier les propriétés d’une visualisation, sélectionnez le visuel, sélectionnez **...**, puis **Modifier le visuel**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Modification des propriétés de graphique pour les rapports personnalisés.":::

1. Après avoir modifié le rapport, sélectionnez **Enregistrer** pour appliquer vos modifications. 

## <a name="delete-a-custom-report"></a>Supprimer un rapport personnalisé

1. Allez dans **Analyser** > **Personnaliser** pour accéder à la liste des rapports personnalisés.

1. Dans la liste des rapports personnalisés, sélectionnez **...**

1. Choisissez **Supprimer** pour supprimer le rapport.

1. Confirmez votre suppression pour supprimer définitivement le rapport.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
