---
title: Examiner l’unification des données
description: Passer en revue les étapes d’unification des données, créer des profils client unifiés et examiner les résultats
ms.date: 08/12/2022
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
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303964"
---
# <a name="review-data-unification"></a>Examiner l’unification des données

Passez en revue le résumé des modifications, créez le profil unifié et examinez les résultats.

## <a name="review-and-create-customer-profiles"></a>Examiner et créer des profils clients

Cette dernière étape du processus d’unification affiche un résumé des étapes du processus et offre la possibilité d’apporter des modifications avant de créer le profil unifié.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Capture d’écran de la page Examiner et créer des profils clients.":::

1. Sélectionnez **Modifier** sur l’une des étapes d’unification des données pour examiner et apporter des modifications.

1. Si vous êtes satisfait de vos sélections, sélectionnez **Créer des profils clients** (ou **Créer des profils de compte** pour le B-to-B). La page **Unifier** s’affiche pendant la création du profil client unifié.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Capture d'écran de la page Unify avec des vignettes indiquant En file d'attente ou Actualisation en cours.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

La création de l’algorithme d’unification prend un certain temps et vous ne pouvez pas modifier la configuration tant qu’il n’est pas terminé.

## <a name="view-the-results-of-data-unification"></a>Afficher les résultats de l’unification des données

Après l’unification, la page **Données** > **Unifier** indique le nombre de profils client unifiés (ou profils de compte pour B-to-B). Les résultats de chaque étape du processus d’unification s’affichent sur chaque vignette. Par exemple, la vignette **Champs source** affiche le nombre d’attributs mappés (champs) et la vignette **Enregistrements en double** affiche le nombre d’enregistrements en double trouvés.

:::image type="content" source="media/m3_unified.png" alt-text="Capture d’écran de la page Données unifiées après l’unification des données.":::

> [!TIP]
> La vignette **Conditions de mise en correspondance** s’affiche uniquement si plusieurs entités ont été sélectionnées.

Nous vous recommandons d’examiner les résultats, en particulier la qualité de vos [règles de correspondance](data-unification-update.md#manage-match-rules) et de les affiner si nécessaire.

Si nécessaire, [apportez des modifications aux paramètres d’unification](data-unification-update.md) et réexécutez le profil unifié.

### <a name="verify-output-entities-from-data-unification"></a>Vérifier les entités de sortie à partir de l’unification des données

Accédez à **Données** > **Entités** pour vérifier les entités de sortie.

L’entité de profil client unifié, dénommée *Client*, s’affiche dans la section **Profils**. La première exécution d’unification réussie crée l’entité *Client*. Toutes les exécutions suivantes développent cette entité.

Les entités de déduplication et de fusion sont créées et s’affichent dans la section **Système**. Une entité dédupliquée pour chacune des entités source est créée, avec le nom **Deduplication_DataSource_Entity**. L’entité **ConflationMatchPairs** contient des informations sur les correspondances inter-entités.

Une entité de sortie de déduplication contient les informations suivantes :
- ID/clés
  - Champs Clé primaire et ID secondaire. Le champ ID secondaire comprend tous les ID secondaires identifiés pour un enregistrement.
  - Le champ Deduplication_GroupId affiche le groupe ou le cluster identifié dans une entité qui regroupe tous les enregistrements similaires en fonction des champs de déduplication spécifiés. Il est utilisé à des fins de traitement du système. Si aucune règle de déduplication manuelle n’est spécifiée et que les règles de déduplication définies par le système s’appliquent, vous ne trouverez peut-être pas ce champ dans l’entité de sortie de déduplication.
  - Deduplication_WinnerId : ce champ contient l’ID gagnant des groupes ou clusters identifiés. Si Deduplication_WinnerId est identique à la valeur de clé primaire d’un enregistrement, cela signifie que l’enregistrement est l’enregistrement gagnant.
- Champs utilisés pour définir les règles de déduplication.
- Champs de règle et de score pour indiquer les règles de déduplication appliquées et le score renvoyé par l’algorithme de correspondance.

## <a name="next-step"></a>Étape suivante

- Pour le B-to-B, vous pouvez, si vous le souhaitez, procéder à une [unification des contacts](data-unification-contacts.md).

- Pour le B-to-C, configurez les [activités](activities.md), les [enrichissements](enrichment-hub.md), les [relations](relationships.md), ou les [mesures](measures.md) pour obtenir plus d’informations sur vos clients.

[!INCLUDE[footer-include](includes/footer-banner.md)]
