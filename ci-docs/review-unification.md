---
title: Examiner l’unification des données
description: Passer en revue les étapes d’unification des données, créer des profils client unifiés et examiner les résultats
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 0f7b2e9af65796c4d304dbd9893a21617e847620
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844083"
---
# <a name="review-data-unification"></a>Examiner l’unification des données

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Cette dernière étape du processus d’unification affiche un résumé des étapes du processus et offre la possibilité d’apporter des modifications avant de créer le profil unifié.

:::image type="content" source="media/m3_review.png" alt-text="Capture d’écran de la page Examiner et créer des profils clients.":::

## <a name="review-the-data-unification-steps"></a>Passer en revue les étapes d’unification des données

1. Sélectionnez **Modifier** sur l’une des étapes d’unification des données pour examiner et apporter des modifications.

1. Si vous êtes satisfait de vos sélections, sélectionnez **Créer des profils clients**. La page **Unifier** s’affiche pendant la création du profil client unifié. Tous les carreaux sauf **Champs sources** affichent le statut **En file d'attente** ou **Actualisation en cours**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Capture d'écran de la page Unify avec des vignettes indiquant En file d'attente ou Actualisation en cours.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

La création de l’algorithme d’unification prend un certain temps et vous ne pouvez pas modifier la configuration tant qu’il n’est pas terminé. Une fois le processus d’unification terminé, l’entité de profil client unifiée, appelée *Client*, est répertoriée sur la page **Entités** de la section **Profils**. La première exécution d’unification réussie crée l’entité *Client*. Toutes les exécutions suivantes développent cette entité.

## <a name="review-the-results-of-data-unification"></a>Passer en revue les résultats de l’unification des données

Après l’unification, la page **Données** > **Unifier** indique le nombre de profils client unifiés. Les résultats de chaque étape du processus d’unification s’affichent sur chaque vignette. Par exemple, la vignette **Champs source** affiche le nombre d’attributs mappés (champs) et la vignette **Enregistrements en double** affiche le nombre d’enregistrements en double trouvés.

:::image type="content" source="media/m3_unified.png" alt-text="Capture d’écran de la page Données unifiées après l’unification des données.":::

> [!TIP]
> La vignette **Conditions de mise en correspondance** s’affiche uniquement si plusieurs entités ont été sélectionnées.

Nous vous recommandons d’examiner les résultats, en particulier la qualité de vos [règles de correspondance](data-unification-update.md#manage-match-rules) et de les affiner si nécessaire.

Si nécessaire, [apportez des modifications aux paramètres d’unification](data-unification-update.md) et réexécutez le profil unifié.

## <a name="next-step"></a>Étape suivante

Configurez les [activités](activities.md), l’[enrichissement](enrichment-hub.md), les [relations](relationships.md), ou les [mesures](measures.md) pour obtenir plus d’informations sur vos clients.

[!INCLUDE[footer-include](includes/footer-banner.md)]
