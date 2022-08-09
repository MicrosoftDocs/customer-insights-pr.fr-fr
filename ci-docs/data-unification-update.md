---
title: Mettre à jour les paramètres d’unification
description: Mettez à jour les règles de duplication, les règles de correspondance ou les champs unifiés dans les paramètres d’unification.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 1af7f018abd412c833ff22b3880f0e4508ff4953
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139576"
---
# <a name="update-the-unification-settings"></a>Mettre à jour les paramètres d’unification

Pour revoir ou modifier les paramètres d’unification une fois qu’un profil unifié a été créé, procédez comme suit.

1. Accédez à **Données** > **Unifier**.

   :::image type="content" source="media/m3_unified.png" alt-text="Capture d’écran de la page Données unifiées après l’unification des données.":::

   > [!TIP]
   > La vignette **Conditions de mise en correspondance** s’affiche uniquement si plusieurs entités ont été sélectionnées.

1. Choisissez ce que vous voulez mettre à jour :
   - [Champs source](#edit-source-fields) pour ajouter des entités ou des attributs ou modifier les types d’attributs.
   - [Enregistrements en double](#manage-deduplication-rules) pour gérer les règles de déduplication ou les préférences de fusion.
   - [Conditions de correspondance](#manage-match-rules) pour mettre à jour les règles de correspondance entre deux ou plusieurs entités.
   - [Champs client unifiés](#manage-unified-fields) pour combiner ou exclure des champs. Vous pouvez également regrouper des profils associés dans des clusters.

1. Après avoir apporté vos modifications, choisissez l’option suivante :

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Capture d’écran de la page Données unifiées avec les options Unifier en surbrillance.":::

   - [Exécuter les conditions de correspondance](#run-matching-conditions) pour évaluer rapidement la qualité de vos conditions de correspondance (déduplication et règles de correspondance) sans mettre à jour le profil unifié. L’option **Exécuter les conditions de correspondance uniquement** ne s’affiche pas pour une seule entité.
   - [Unifier les profils clients](#run-updates-to-the-unified-customer-profile) pour exécuter des conditions et mettre à jour l'entité de profil client unifié sans affecter les dépendances (telles que les enrichissements, les segments ou les mesures). Les processus dépendants ne sont pas exécutés, mais seront actualisés au fur et à mesure comme [défini dans le calendrier d’actualisation](system.md#schedule-tab).
   - [Unifier les profils clients et les dépendances](#run-updates-to-the-unified-customer-profile) pour exécuter des conditions et mettre à jour l'entité de profil client unifié et toutes les dépendances (telles que les enrichissements, les segments ou les mesures). Tous les processus sont réexécutés automatiquement.

## <a name="edit-source-fields"></a>Modifier les champs source

Vous ne pouvez pas supprimer un attribut ou une entité s’ils ont déjà été unifiés.

1. Sélectionnez **Modifier** sur la vignette **Champs source**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Capture d’écran de la page Champs source indiquant le nombre de clés primaires, les champs mappés et non mappés":::

   Le nombre de champs mappés et non mappés s’affiche.

1. Sélectionnez **Sélectionner des entités et des champs** pour ajouter d’autres attributs ou entités. Utilisez la recherche ou faites défiler la liste des attributs et des entités qui vous intéressent. Cliquez sur **Appliquer**.

1. Vous pouvez, si vous le souhaitez, modifier la clé primaire d’une entité, les types d’attributs et activer ou désactiver le **Mappage intelligent**. Pour plus d’informations, voir [Sélectionner la clé primaire et le type sémantique des attributs](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Sélectionnez **Suivant** pour apporter des modifications aux règles de déduplication, ou sélectionnez **Enregistre et fermer** pour revenir dans [Mettre à jour les paramètres d’unification](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Gérer les règles de déduplication

1. Sélectionnez **Modifier** sur la vignette **Enregistrements en double**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Capture d’écran de la page Enregistrements en double indiquant le nombre d’enregistrements en double" lightbox="media/m3_duplicates_edit.png":::

   Le nombre d’enregistrements en double trouvés s’affiche sous **Doublons**. La colonne **Enregistrements dédupliqués** indique quelles entités avaient des enregistrements en double et le pourcentage d’enregistrements en double.

1. Si vous avez ajouté une entité enrichie, sélectionnez **Utiliser les entités enrichies**. Pour plus d’informations, voir [Enrichissement des sources de données](data-sources-enrichment.md).

1. Pour gérer les règles de déduplication, choisissez l’une des options suivantes :
   - **Créer une nouvelle règle** : Sélectionnez **Ajouter une règle** sous l’entité appropriée. Pour plus d’informations, consultez [Définir des règles de déduplication](remove-duplicates.md#define-deduplication-rules).
   - **Modifier les conditions des règles** : Sélectionnez la règle, puis **Modifier**. Modifiez les champs, ajoutez ou supprimez des conditions, ou ajoutez ou supprimez des exceptions.
   - **Aperçu** : Sélectionnez la règle puis **Aperçu** pour afficher les résultats de la dernière exécution de cette règle.
   - **Désactiver une règle** : Sélectionnez la règle, puis **Désactiver** pour conserver une règle de déduplication tout en l’excluant du processus de mise en correspondance.
   - **Dupliquer une règle** : Sélectionnez la règle, puis **Dupliquer** pour créer une règle similaire avec des modifications.
   - **Supprimer une règle** : Sélectionnez la règle, puis **Supprimer**.

1. Pour modifier les préférences de fusion, sélectionnez l’entité. Vous ne pouvez modifier les préférences que si une règle est créée.
   1. Sélectionnez **Modifier les préférences de fusion** et changez l’option **Enregistrement à conserver**.
   1. Pour modifier les préférences de fusion des attributs individuels d’une entité, sélectionnez **Avancé** et apporter les modifications nécessaires.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Capture d’écran des préférences de fusion avancées affichant les e-mails les plus récents et l’adresse la plus complète":::

   1. Cliquez sur **Terminé**.

1. Sélectionnez **Suivant** pour apporter des modifications aux conditions de correspondance, ou sélectionnez **Enregistre et fermer** pour revenir dans [Mettre à jour les paramètres d’unification](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Gérer les règles de correspondance

Vous pouvez reconfigurer et affiner la plupart des paramètres de correspondance. Vous ne pouvez pas ajouter ou supprimer d’entités. Les règles de correspondance ne s’appliquent pas à une seule entité.

1. Sélectionnez **Modifier** sur la vignette **Conditions de correspondance**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Capture d’écran de la page Règles et conditions de correspondance avec des statistiques." lightbox="media/m3_match_edit.png":::

   La page affiche l’ordre de correspondance et les règles définies, ainsi que les statistiques suivantes :
   - **Enregistrements source uniques** indique le nombre d’enregistrements source individuels qui ont été traités lors de la dernière mise en correspondance.
   - **Enregistrements correspondants et non correspondants** met en évidence le nombre d’enregistrements uniques restants après le traitement des règles de correspondance.
   - **Enregistrements correspondants uniquement** affiche le nombre de correspondances sur toutes vos paires de correspondances.

1. Pour afficher les résultats de toutes les règles et leurs scores, sélectionnez **Afficher la dernière exécution**. Les résultats s’affichent, y compris les autres ID de contact. Vous pouvez télécharger les résultats.

1. Pour afficher les résultats et les scores d’une règle particulière, sélectionnez la règle, puis **Aperçu**. Les résultats s’affichent. Vous pouvez télécharger les résultats.

1. Pour afficher les résultats d’une condition particulière, sélectionnez la règle, puis **Modifier**. Dans le volet Modifier, sélectionnez **Aperçu** sous la condition. Vous pouvez télécharger les résultats.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Représentation graphique des enregistrements avec et sans correspondance, y compris la liste des données.":::

1. Si vous avez ajouté une entité enrichie, sélectionnez **Utiliser les entités enrichies**. Pour plus d’informations, voir [Enrichissement des sources de données](data-sources-enrichment.md).

1. Pour gérer des règles, choisissez l’une des options suivantes :
   - **Créer une nouvelle règle** : Sélectionnez **Ajouter une règle** sous l’entité appropriée. Pour plus d’informations, voir [Définir des règles pour les paires de correspondance](match-entities.md#define-rules-for-match-pairs).
   - **Modifier l’ordre de vos règles** : si vous avez défini plusieurs règles : faites glisser et déposez les règles dans l’ordre souhaité. Pour plus d’informations, voir [Spécifier l’ordre de correspondance](match-entities.md#specify-the-match-order).
   - **Modifier les conditions des règles** : Sélectionnez la règle, puis **Modifier**. Modifiez les champs, ajoutez ou supprimez des conditions, ou ajoutez ou supprimez des exceptions.
   - **Désactiver une règle** : Sélectionnez la règle, puis **Désactiver** pour conserver une règle de correspondance tout en l’excluant du processus de mise en correspondance.
   - **Dupliquer une règle** : Sélectionnez la règle, puis **Dupliquer** pour créer une règle similaire avec des modifications.
   - **Supprimer une règle** : Sélectionnez la règle, puis **Supprimer**.

1. Sélectionnez **Suivant** pour apporter des modifications aux champs unifiés ou sélectionnez **Enregistre et fermer** pour revenir dans [Mettre à jour les paramètres d’unification](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Gérer les champs unifiés

1. Sélectionnez **Modifier** sur la vignette **Champs clients unifiés**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Capture d’écran des champs client unifiés":::

1. Passez en revue les champs combinés et exclus et apportez les modifications nécessaires. Ajoutez ou modifiez la clé CustomerID ou les profils de groupe dans des clusters. Pour plus d’informations, voir [Unifier les champs clients](merge-entities.md).

1. Sélectionnez **Suivant** pour revoir les paramètres d’unification et [mettre à jour le profil unifié et les dépendances](#run-updates-to-the-unified-customer-profile), ou sélectionnez **Enregistrer et fermer** pour revenir dans [Mettre à jour les paramètres d’unification](#update-the-unification-settings) pour faire plus de changements.

## <a name="run-matching-conditions"></a>Exécuter les conditions de correspondance

Exécutez les conditions de correspondance exécute uniquement les règles de déduplication et de correspondance et met à jour les entités *Deduplication_* et *ConflationMatchPair*.

1. Dans la page **Données** > **Unifier**, sélectionnez **Exécuter les conditions correspondantes uniquement**.

   Les vignettes **Enregistrements en double** et **Conditions de correspondance** indiquent le statut **Mis en file d’attente** ou **Actualisation en cours**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Lorsque le processus de correspondance est terminé, sélectionnez **Modifier** sur la vignette **Conditions de correspondance**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Capture d’écran recadrée des mesures clés de la page Mise en correspondance avec chiffres et détails.":::

1. Pour apporter des modifications, consultez [Gérer les règles de déduplication](#manage-deduplication-rules) ou alors [Gérer les règles de correspondance](#manage-match-rules).

1. Exécutez à nouveau le processus de correspondance ou [exécutez les mises à jour du profil client](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Exécuter les mises à jour du profil client unifié

1. À partir de la page **Données** > **Unifier**, sélectionnez :

   - **Unifier les profils clients** : Exécute des conditions et met à jour l'entité de profil client unifié sans affecter les dépendances (telles que les enrichissements, les segments ou les mesures). Les processus dépendants ne sont pas exécutés, mais seront actualisés au fur et à mesure comme [défini dans le calendrier d’actualisation](system.md#schedule-tab).

   - **Unifier les profils clients et les dépendances** : Exécute les conditions correspondantes et met à jour le profil unifié et toutes les dépendances. Tous les processus sont réexécutés automatiquement. Une fois tous les processus en aval terminés, le profil client reflète les données mises à jour.

   Les vignettes **Enregistrements en double**, **Conditions de correspondance** et **Champs clients unifiés** indiquent le statut **Mis en file d’attente** ou **Actualisation en cours**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Les résultats d’une exécution réussie s’affichent sur la page **Unifier** qui indique le nombre de profils clients unifiés.
