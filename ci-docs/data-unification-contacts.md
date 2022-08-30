---
title: Créer un profil de contact unifié (aperçu)
description: Suivez le processus d’unification des données pour créer un seul jeu de données maître de contacts.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305031"
---
# <a name="create-a-unified-contact-profile-preview"></a>Créer un profil de contact unifié (aperçu)

Après avoir [unifié les comptes professionnels](map-entities.md), vous pouvez éventuellement unifier les contacts de ces comptes et lier les contacts unifiés aux comptes unifiés. Le processus d’unification des contacts mappe les données de contact à partir de plusieurs sources de données, supprime les doublons, fait correspondre les données entre les entités, configure le mappage sémantique, crée des relations entre les contacts et les comptes, puis crée un profil de contact unifié.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Les premières étapes sont identiques aux étapes d’unification des comptes.

## <a name="prerequisites"></a>Conditions préalables

Les enregistrements de compte et de contact doivent avoir une clé unique (appelée clé étrangère) qui les relie. Par exemple, un ID de compte qui existe dans l’enregistrement de compte et l’enregistrement de contact qui lie le compte et le contact ensemble.

## <a name="preview-limitations"></a>Limitations de la préversion

- Les contacts sans lien vers un compte sont supprimés.
- Si un compte est dédupliqué, un enregistrement gagnant est identifié en fonction des préférences de fusion. Les enregistrements perdants ne sont pas sélectionnés et sont donc supprimés. Les contacts associés aux enregistrements perdants sont supprimés.
- Un compte peut avoir plusieurs contacts, mais un contact est lié à un seul compte.
- Les attributs de contact mappés à l’étape de mappage sémantique sont les seuls attributs pouvant s’afficher sur la fiche client. Cependant, 17 attributs sont disponibles.

## <a name="select-source-fields"></a>Sélectionner les champs source

1. Sous **Unifier les contacts (aperçu)**, sélectionnez **Démarrer**.

1. [Sélectionnez les entités et les champs](map-entities.md) pour vos sources de données de contact, y compris les clés primaires et les types d’attributs.

1. Cliquez sur **Suivant**.

## <a name="remove-duplicate-records"></a>Supprimer les enregistrements dupliqués

1. Vous pouvez, si vous le souhaitez, [définir des règles de déduplication](remove-duplicates.md) pour vos entités sélectionnées.

1. Cliquez sur **Suivant**.

## <a name="match-conditions"></a>Conditions de correspondance

1. [Définir l’ordre et les règles de correspondance](match-entities.md) pour les correspondances entre entités.

1. Cliquez sur **Suivant**.

## <a name="unify-contact-fields"></a>Unifier les champs de contact

1. [Combiner et exclure des champs de contact](merge-entities.md).

1. Cliquez sur **Suivant**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Définir les champs sémantiques pour les contacts unifiés

Cette étape du processus d’unification associe vos champs de contact unifiés à des types sémantiques. En B-to-B, les fiches clients affichent les comptes. Lorsque la carte est sélectionnée, tous les contacts associés au compte s’affichent. Les champs que vous mappez à cette étape sont les champs qui s’afficheront sur les cartes.

1. Sélectionnez le type sémantique mappé à chaque champ unifié. Sélectionnez **Aucun** si un type sémantique n’est pas disponible.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Capture d’écran de la page Champs sémantiques pour définir les types sémantiques." lightbox="media/semantic_mapping.png":::

1. Après avoir mappé tous les champs unifiés, sélectionnez **Suivant**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Définir la relation entre les contacts et les comptes

Cette étape du processus d’unification relie vos données de contact aux données de compte correspondantes.

1. Pour chaque entité, saisissez les informations suivantes :

   - **Clé étrangère de l’entité de contact** : choisissez l’attribut qui relie votre entité de contact au compte.
   - **Vers l’entité de contact** : choisissez l’entité de compte associée au contact.

   :::image type="content" source="media/contact_relationship.png" alt-text="Capture d’écran de la page Relation pour relier les entités de contact et de compte.":::

1. Cliquez sur **Suivant**.

## <a name="review-contact-unification"></a>Examiner l’unification des contacts

Passez en revue le résumé des modifications, créez le profil unifié et examinez les résultats.

### <a name="review-and-create-contact-profiles"></a>Vérifier et créer des profils de contact

Cette dernière étape du processus d’unification affiche un résumé des étapes du processus et offre la possibilité d’apporter des modifications avant de créer le profil de contact unifié.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Capture d’écran de la page Examiner et créer des profils de contact.":::

1. Sélectionnez **Modifier** sur l’une des étapes d’unification des contacts pour examiner et apporter des modifications.

1. Si vous êtes satisfait de vos sélections, sélectionnez **Créer des profils de contact**. La page **Unifier** s’affiche pendant la création du profil de contact unifié.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Capture d’écran de la page Unifier les contacts avec des vignettes indiquant En file d’attente ou Actualisation en cours.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

La création de l’algorithme d’unification prend un certain temps et vous ne pouvez pas modifier la configuration tant qu’il n’est pas terminé.

### <a name="view-the-results-of-contact-unification"></a>Afficher les résultats de l’unification des données

Après l’unification, la page **Données** > **Unifier** indique le nombre de profils de contact unifiés. Les résultats de chaque étape du processus d’unification s’affichent sur chaque vignette. Par exemple, la vignette **Champs source** affiche le nombre d’attributs mappés (champs) et la vignette **Enregistrements en double** affiche le nombre d’enregistrements en double trouvés.

:::image type="content" source="media/unified_contacts.png" alt-text="Capture d’écran de la page Données unifiées après l’unification des contacts.":::

> [!TIP]
> La vignette **Conditions de mise en correspondance** s’affiche uniquement si plusieurs entités ont été sélectionnées.

Nous vous recommandons d’examiner les résultats, en particulier la qualité de vos [règles de correspondance](data-unification-update.md#manage-match-rules) et de les affiner si nécessaire.

Si nécessaire, [apportez des modifications aux paramètres d’unification des contacts](data-unification-update.md) et réexécutez le profil unifié.

### <a name="verify-output-entities-from-data-unification"></a>Vérifier les entités de sortie à partir de l’unification des données

Accédez à **Données** > **Entités** pour vérifier les entités de sortie.

L’entité de profil de contact unifié, appelée *ContactProfile*, s’affiche dans la section **Entités sémantiques**. La première exécution d’unification réussie crée l’entité *ContactProfile*. Toutes les exécutions suivantes développent cette entité.

L’entité *ContactsCustomer* (aperçu) est créée et s’affiche dans la section **Profils**. Cette entité contient les données de contact sans les liens vers les comptes. Cette entité est utilisée comme entrée dans les étapes de mappage sémantique et de relation de l’unification des contacts.

Les entités de déduplication et de fusion sont créées et s’affichent dans la section **Système**. Une entité dédupliquée pour chacune des entités source est créée, avec le nom **Deduplication_DataSource_Entity**. L’entité **ContactsConflationMatchPairs** contient des informations sur les correspondances inter-entités.

Une entité de sortie de déduplication contient les informations suivantes :
- ID/clés
  - Champs Clé primaire et ID secondaire. Le champ ID secondaire comprend tous les ID secondaires identifiés pour un enregistrement.
  - Le champ Deduplication_GroupId affiche le groupe ou le cluster identifié dans une entité qui regroupe tous les enregistrements similaires en fonction des champs de déduplication spécifiés. Il est utilisé à des fins de traitement du système. Si aucune règle de déduplication manuelle n’est spécifiée et que les règles de déduplication définies par le système s’appliquent, vous ne trouverez peut-être pas ce champ dans l’entité de sortie de déduplication.
  - Deduplication_WinnerId : ce champ contient l’ID gagnant des groupes ou clusters identifiés. Si Deduplication_WinnerId est identique à la valeur de clé primaire d’un enregistrement, cela signifie que l’enregistrement est l’enregistrement gagnant.
- Champs utilisés pour définir les règles de déduplication.
- Champs de règle et de score pour indiquer les règles de déduplication appliquées et le score renvoyé par l’algorithme de correspondance.

## <a name="next-step"></a>Étape suivante

Pour plus d’informations sur vos contacts, configurez les [activités](activities.md), l’[enrichissement](enrichment-hub.md) ou les [relations](relationships.md).
