---
title: Mettre en correspondance des entités pour l’unification des données
description: Mettez en correspondance des données pour créer des profils clients unifiés.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267475"
---
# <a name="match-entities"></a>Mettre en correspondance des entités

Une fois la phase de mise en correspondance terminée, vous êtes prêt à mettre vos entités en correspondance. La phase de correspondance spécifie comment combiner vos ensembles de données dans un jeu de données de profil client unifié. La phase de mise en correspondance nécessite au moins [deux entités mappées](map-entities.md).

## <a name="specify-the-match-order"></a>Indiquer l’ordre de mise en correspondance

Allez à **Données** > **Unifier** > **Mettre en correspondance** et sélectionnez **Définir l’ordre** pour démarrer la phase de mise en correspondance.

Chaque correspondance unifie deux ou plusieurs entités en une seule, tout en conservant chaque enregistrement unique d’un client. Dans l’exemple suivant, l’utilisateur a sélectionné trois entités : **ContactCSV : TestData** comme entité **Principale**, **WebAccountCSV : TestData** comme **Entité 2**, et **CallRecordSmall : TestData** comme **Entité 3**. Le schéma au-dessus de ces sélections illustre comment l’ordre de mise en correspondance sera exécuté.

> [!div class="mx-imgBorder"]
> ![Modifier l’ordre de correspondance des données](media/configure-data-match-order-edit-page.png "Modifier l’ordre de correspondance des données")
  
L’entité **Principale** est associée à **Entité 2**. Le jeu de données résultant de la première correspondance est mis en correspondance avec l’**Entité 3**.
Dans cet exemple, nous n’avons sélectionné que deux correspondances, mais le système peut en prendre davantage en charge.

> [!IMPORTANT]
> L’entité que vous choisissez comme votre entité **Principale** servira de base pour votre jeu de données principal unifié. Toutes les futures entités qui seront sélectionnées au cours de la phase de mise en correspondance seront ajoutées à cette entité. En même temps, cela ne signifie pas que l’entité unifiée comprendra *toutes* les données incluses dans cette entité.
>
> Deux considérations peuvent vous aider à choisir la hiérarchie de vos entités :
>
> - Quelle entité considérez-vous posséder les données les plus complètes et fiables sur vos clients ?
> - L’entité qui vous venez d’identifier a-t-elle des attributs qui sont partagés par d’autres entités (par exemple, nom, numéro de téléphone ou adresse de messagerie) ? Si ce n’est pas le cas, sélectionnez la deuxième entité la plus fiable.

Sélectionnez **Terminé** pour enregistrer votre ordre de correspondance.

## <a name="define-rules-for-your-first-match-pair"></a>Définir les règles pour la première paire de correspondance

Après avoir spécifié l’ordre des correspondances, vous verrez les correspondances définies sur la page **Correspondance**. Les vignettes en haut de l’écran seront vides jusqu’à vous exécutiez votre ordre de correspondance.

> [!div class="mx-imgBorder"]
> ![Définir des règles](media/configure-data-match-need-rules.png "Définir les règles")

L’avertissement **Nécessite des règles** suggère qu’aucune règle de correspondance n’est définie pour une paire de correspondance. Les règles de correspondance spécifient la logique par laquelle une paire spécifique d’entités sera mise en correspondance.

1. Pour définir votre première règle, ouvrez le volet **Définition de règle** en sélectionnant la ligne correspondante dans la table de correspondances (1) puis en sélectionnant **Créer une nouvelle règle** (2).

   > [!div class="mx-imgBorder"]
   > ![Créer une règle](media/configure-data-match-new-rule2.png "Créer une règle")

2. Dans le volet **Modifier la règle**, configurez les conditions de cette règle. Chaque condition est représentée par deux lignes qui contiennent des sélections obligatoires.

   > [!div class="mx-imgBorder"]
   > ![Volet Nouvelle règle](media/configure-data-match-new-rule-condition.png "Volet Nouvelle règle")

   Entité/Champ (En premier) - Un attribut qui sera utilisé pour mettre en correspondance à partir de la première entité de la paire de correspondance. Les exemples peuvent inclure un numéro de téléphone ou une adresse e-mail. Choisissez un attribut susceptible d’être unique pour le client.

   > [!TIP]
   > Évitez de faire correspondre la base des attributs du type Activité. En d’autres termes, si un attribut semble être une activité, il peut être un critère de correspondance médiocre.  

   Entité/Champ (En deuxième) - Un attribut qui sera utilisé pour mettre en correspondance à partir de la deuxième entité de la paire de correspondance.

   Normaliser - **Méthode de normalisation** : Diverses options de normalisation sont disponibles pour les attributs sélectionnés. Par exemple, supprimer la ponctuation ou supprimer les espaces

   Pour la normalisation du nom de l’organisation (préversion), vous pouvez également sélectionner **Type (téléphone, nom, organisation)**

   > [!div class="mx-imgBorder"]
   > ![Normalisation - B2B](media/match-normalization-b2b.png "Normalisation - B2B")

   Niveau de précision - Le niveau de précision qui sera utilisé pour cette condition. La définition d’un niveau de précision pour une condition de correspondance peut avoir deux types : **De base** et **Personnalisé**.  
   - De base : vous propose quatre options parmi lesquelles choisir : Faible, Moyen, Élevé et Exact. Sélectionnez **Exact** pour ne faire correspondre que les enregistrements qui correspondent à 100 %. Sélectionnez un des autres niveaux pour mettre en correspondance les enregistrements qui ne sont pas identiques à 100 pour cent.
   - Personnalisé : utilisez le curseur pour définir le pourcentage personnalisé auquel les enregistrements doivent correspondre ou entrez une valeur dans le champ **Personnalisé**. Le système ne fera correspondre que les enregistrements dépassant ce seuil sous forme de paires de correspondances. Les valeurs du curseur sont comprises entre 0 et 1. 0,64 représente donc 64 %.

3. Sélectionnez **Terminé** pour enregistrer la règle.

### <a name="add-multiple-conditions"></a>Ajouter plusieurs conditions

Pour mettre en correspondance vos entités que si plusieurs conditions sont réunies, ajoutez d’autres conditions qui sont liées par un opérateur ET.

1. Dans le volet **Modifier la règle**, sélectionnez **Ajouter une condition**. Vous pouvez également supprimer des conditions en sélectionnant le bouton Supprimer à côté d’une condition existante.

2. Sélectionnez **Terminé** pour enregistrer la règle.

## <a name="add-multiple-rules"></a>Ajouter plusieurs règles

Chaque condition s’applique à une seule paire d’attributs, lorsque les règles représentent des ensembles de conditions. Pour que vos entités correspondent à différents ensembles d’attributs, vous pouvez ajouter d’autres règles.

1. Dans les informations sur l’audience, accédez à **Données** > **Unifier** > **Mettre en correspondance**.

2. Sélectionnez l’entité à mettre à jour, puis sélectionnez **Ajouter des règles**.

3. Suivez la procédure décrite dans [Définir les règles pour la première paire de correspondance](#define-rules-for-your-first-match-pair).

> [!NOTE]
> L’ordre des règles est important. L’algorithme de correspondance tente d’effectuer une mise en correspondance sur la base de votre première règle et passe à la deuxième règle uniquement si aucune correspondance n’a été identifiée avec la première règle.

## <a name="define-deduplication-on-a-match-entity"></a>Définir la déduplication d’une entité de mise en correspondance

En plus de spécifier les règles de mise en correspondance entre entités comme indiqué dans les sections ci-dessus, vous pouvez également spécifier des règles de déduplication. La *Déduplication* est un processus. Elle identifie les enregistrements en double, les fusionne en un seul enregistrement et lie tous les enregistrements sources à cet enregistrement fusionné avec d’autres ID de l’enregistrement fusionné.

Une fois qu’un enregistrement dédupliqué est identifié, cet enregistrement sera utilisé dans le processus de mise en correspondance entre entités. La déduplication est mise en œuvre au niveau de l’entité et peut être appliquée à chaque entité utilisée dans le processus de mise en correspondance.

### <a name="add-deduplication-rules"></a>Ajouter des règles de déduplication

1. Dans les informations sur l’audience, accédez à **Données** > **Unifier** > **Mettre en correspondance**.

1. Dans la section **Doublons fusionnés**, sélectionnez **Définir les entités**.

1. Dans la section **Préférences de fusion**, sélectionnez les entités auxquelles vous souhaitez appliquer la déduplication.

1. Spécifiez comment fusionner les enregistrements en double et choisissez l’une des trois options de fusion :
   - *Les plus remplis* : identifie l’enregistrement avec les attributs les plus remplis comme enregistrement gagnant. Il s’agit de l’option de fusion par défaut.
   - *Les plus récents* : identifie l’enregistrement gagnant en fonction du plus récent. Nécessite une date ou un champ numérique pour définir la récence.
   - *Les moins récents* : identifie l’enregistrement gagnant en fonction du moins récent. Nécessite une date ou un champ numérique pour définir la récence.
 
   > [!div class="mx-imgBorder"]
   > ![Étape 1 des règles de déduplication](media/match-selfconflation.png "Étape 1 des règles de déduplication")
 
1. Une fois les entités sélectionnées et leur préférence de fusion définie, sélectionnez **Créer une nouvelle règle** pour définir les règles de déduplication au niveau de l’entité.
   - **Sélectionner un champ** répertorie tous les champs disponibles de l’entité sur laquelle vous souhaitez dédupliquer les données sources.
   - Spécifiez les paramètres de normalisation et de précision de la même façon que dans le processus de mise en correspondance entre entités.
   - Vous pouvez définir des conditions supplémentaires en sélectionnant **Ajouter une condition**.
 
   > [!div class="mx-imgBorder"]
   > ![Étape 2 des règles de déduplication](media/match-selfconflation-rules.png "Étape 2 des règles de déduplication")

  Vous pouvez créer plusieurs règles de déduplication pour une entité. 

1. L’exécution du processus de mise en correspondance regroupe maintenant les enregistrements en fonction des conditions définies dans les règles de déduplication. Une fois les enregistrements regroupés, la stratégie de fusion est appliquée pour identifier l’enregistrement gagnant.

1. Cet enregistrement gagnant est ensuite transmis à la mise en correspondance entre entités, avec les enregistrements non gagnants (par exemple, les autres ID) pour améliorer la qualité de la correspondance.

1. Toutes les règles de mise en correspondance personnalisées définies pour toujours correspondre et ne jamais correspondre remplacent les règles de déduplication. Si une règle de déduplication identifie des enregistrements correspondants et si une règle de mise en correspondance personnalisée est définie pour ne jamais correspondre à ces enregistrements, ces deux enregistrements ne seront pas mis en correspondance.

1. Une fois le processus de mise en correspondance exécuté, vous verrez les statistiques de déduplication.
   
> [!NOTE]
> La spécification des règles de déduplication n’est pas obligatoire. Si aucune règle de ce type n’est configurée, les règles définies par le système sont appliquées. Elles regroupent tous les enregistrements qui partagent la même combinaison de valeurs (correspondance exacte) à partir de la clé primaire et les champs des règles de mise en correspondance en un seul enregistrement avant de transmettre les données d’entité au processus de mise en correspondance entre entités pour améliorer les performances et l’intégrité du système.

## <a name="run-your-match-order"></a>Exécuter votre ordre de mise en correspondance

Une fois les règles de mise en correspondance définies, notamment les règles de mise en correspondance entre entités et de déduplication, vous pouvez exécuter l’ordre de mise en correspondance. Sur la page **Mettre en correspondance**, sélectionnez **Exécuter** pour démarrer le processus. L’exécution de l’algorithme de correspondance peut prendre un certain temps. Vous ne pouvez pas modifier les propriétés de la page **Mettre en correspondance** tant que le processus n’est pas terminé. Vous trouverez l’entité de profil client unifiée qui a été créée sur la page **Entités**. Votre entité client unifiée est appelée **ConflationMatchPairs : CustomerInsights**.

Pour apporter des modifications supplémentaires et réexécuter l’étape, vous pouvez annuler une mise en correspondance en cours. Sélectionnez le texte **Actualisation en cours...** et sélectionnez **Annuler la tâche** en bas du volet latéral qui s’affiche.

Une fois le processus de mise en correspondance terminé, le texte **Actualisation en cours...** est modifié en **Opération réussie**. Vous pouvez alors utiliser à nouveau toutes les fonctionnalités de la page.

La première correspondance entraîne la création d’une entité principale unifiée. Toutes les correspondances suivantes entraînent l’expansion de cette entité.

> [!TIP]
> Il existe [six types de statuts](system.md#status-types) pour les tâches/processus. En outre, la plupart des processus [dépendent d’autres processus en aval](system.md#refresh-policies). Vous pouvez sélectionner le statut d’un processus pour afficher des détails sur la progression de toute la tâche. Après avoir sélectionné **Voir les détails** pour l’une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.

## <a name="deduplication-output-as-an-entity"></a>Sortie de déduplication en tant qu’entité
En plus de l’entité maître principale créée dans le cadre de la mise en correspondance entre entités, le processus de déduplication génère également une nouvelle entité pour chaque entité à partir de l’ordre de correspondance afin d’identifier les enregistrements dédupliqués. Ces entités peuvent être trouvées avec **ConflationMatchPairs:CustomerInsights** dans la section **Système** de la page **Entités**, avec le nom **Deduplication_Datasource_Entity**.

Une entité de sortie de déduplication contient les informations suivantes :
- ID/clés
  - Champ de clé primaire et son champ d’ID de remplacement. Le champ ID de remplacement comprend tous les ID de remplacement identifiés pour un enregistrement.
  - Le champ Deduplication_GroupId affiche le groupe ou le cluster identifié dans une entité qui regroupe tous les enregistrements similaires en fonction des champs de déduplication spécifiés. Il est utilisé à des fins de traitement du système. Si aucune règle de déduplication manuelle n’est spécifiée et que les règles de déduplication définies par le système s’appliquent, vous ne trouverez peut-être pas ce champ dans l’entité de sortie de déduplication.
  - Deduplication_WinnerId : ce champ contient l’ID gagnant des groupes ou clusters identifiés. Si Deduplication_WinnerId est identique à la valeur de clé primaire d’un enregistrement, cela signifie que l’enregistrement est l’enregistrement gagnant.
- Champs utilisés pour définir les règles de déduplication.
- Champs de règle et de score pour indiquer les règles de déduplication appliquées et le score renvoyé par l’algorithme de correspondance.

## <a name="review-and-validate-your-matches"></a>Examiner et valider vos correspondances

Évaluer la qualité de vos paires de correspondance et les améliorer :

- Sur la page **Mettre en correspondance**, vous trouverez deux vignettes montrant les informations initiales sur vos données.

  - **Clients uniques** : affiche le nombre des profils uniques que le système a identifiés.
  - **Enregistrements mis en correspondance** : affiche le nombre de correspondances sur toutes vos paires de correspondances.

- Dans la table **Ordre de correspondance**, vous pouvez évaluer les résultats de chaque paire de correspondance en comparant le nombre d’enregistrements qui sont sortis de cette entité de paire de correspondance par rapport au pourcentage des enregistrements mis en correspondance avec succès.

- Dans la section **Règles** d’une entité dans la table **Ordre de correspondance**, vous trouverez le pourcentage d’enregistrements correctement mis en correspondance au niveau de la règle. En sélectionnant le symbole de table à côté d’une règle, vous pouvez afficher tous ces enregistrements au niveau de la règle. Nous vous recommandons de consulter un sous-ensemble des enregistrements pour vérifier qu’ils correspondent bien.

- Vous pouvez faire des expériences avec différents seuils de précision autour de vos conditions afin d’identifier la valeur optimale.

  1. Sélectionnez les points de suspension (...) pour la règle de paire de correspondance que vous souhaitez expérimenter et sélectionnez **Modifier**.

  2. Sélectionnez la condition que vous souhaitez expérimenter. Chaque critère est représenté par une ligne dans le volet **Règle de correspondance**.

  3. Ce que vous verrez sur la page **Aperçu des critères** dépend du niveau de précision que vous avez sélectionné pour une condition. Recherchez le nombre d’enregistrements concordants et non concordants pour la condition sélectionnée.

     Vous pouvez comprendre dans le détail les effets des différents seuils. Vous pouvez comparer le nombre d’enregistrements qui sont mis en correspondance en fonction de chaque seuil, ainsi qu’afficher les enregistrements sous chaque option. Sélectionnez chacune des vignettes et consultez les données dans la section de tableau.

## <a name="optimize-your-matches"></a>Optimiser vos correspondances

Augmentez la qualité en reconfigurant certains de vos paramètres de correspondance :

- **Modifier l’ordre de correspondance** en sélectionnant **Modifier** et modifiez les champs d’ordre de correspondance.

  > [!div class="mx-imgBorder"]
  > ![Modifier l’ordre de correspondance des données](media/configure-data-match-order-edit.png "Modifier l’ordre de correspondance des données")

- **Modifier l’ordre de vos règles** si vous avez défini plusieurs règles. Vous pouvez réorganiser les règles de correspondance en sélectionnant les options **Déplacer vers le haut** et **Déplacer vers le bas** de la grille des règles de correspondance.

  > [!div class="mx-imgBorder"]
  > ![Modifier l’ordre des règles](media/configure-data-change-rule-order.png "Modifier l’ordre des règles")

- **Dupliquer vos règles** si vous avez défini une règle de correspondance et souhaitez créer une règle similaire avec des modifications. Faites-le en sélectionnant **Dupliquer**.

  > [!div class="mx-imgBorder"]
  > ![Dupliquer une règle](media/configure-data-duplicate-rule.png "Dupliquer une règle")

- **Désactiver une règle** pour conserver une règle de correspondance tout en l’excluant du processus de correspondance.

  > [!div class="mx-imgBorder"]
  > ![Désactiver une règle](media/configure-data-deactivate-rule.png "Désactiver une règle")

- **Modifiez vos règles** en sélectionnant le symbole **Modifier**. Vous pouvez appliquer les modifications suivantes :

  - Modifier les attributs d’une condition : sélectionnez de nouveaux attributs dans la ligne de condition spécifique.
  - Modifier le seuil d’une condition : ajustez le curseur de précision.
  - Modifier la méthode de normalisation d’une condition : mettez à jour la méthode de normalisation.

## <a name="specify-your-custom-match-records"></a>Spécifier vos enregistrements de correspondance personnalisés

Vous pouvez spécifier des conditions pour que certains enregistrements doivent toujours correspondre ou ne jamais correspondre. Ces règles peuvent être téléchargées en bloc dans le processus de correspondance.

1. Sélectionnez l’option **Correspondance personnalisée** dans l’écran **Ordre de correspondance**.

   > [!div class="mx-imgBorder"]
   > ![Créer une correspondance personnalisée](media/custom-match-create.png "Créer une correspondance personnalisée")

2. Si vous n’avez aucune entité téléchargée, vous verrez une nouvelle boîte de dialogue **Correspondance personnalisée** qui vous oblige à remplir certains détails. Si vous avez fourni ces informations plus tôt, passez à l’étape 8.

   > [!div class="mx-imgBorder"]
   > ![Boîte de dialogue Nouvelle correspondance personnalisée](media/custom-match-new-dialog-box.png "Boîte de dialogue Nouvelle correspondance personnalisée")

3. Sélectionnez **Remplir le modèle** pour obtenir un fichier modèle qui peut spécifier les enregistrements à partir desquels les entités doivent toujours correspondre ou ne jamais correspondre. Vous devez renseigner séparément les "enregistrements qui doivent toujours correspondre" et les "enregistrements qui ne doivent jamais correspondre" dans deux fichiers différents.

4. Le modèle contient des champs pour spécifier l’entité et les valeurs de clé primaire d’entité à utiliser dans la correspondance personnalisée. Par exemple, si vous souhaitez que la clé primaire 12345 de l’entité Ventes corresponde toujours à la clé primaire 34567 de l’entité Contact, vous devrez spécifier comme suit :
    - Entité 1 : Ventes
    - Clé d’entité 1 : 12345
    - Entité 2 : Contact
    - Clé d’entité 2 : 34567

   Le même fichier modèle peut spécifier des enregistrements de correspondance personnalisés à partir de plusieurs entités.
   
   Si vous souhaitez spécifier une correspondance personnalisée pour la déduplication sur une entité, fournissez la même entité que Entity1 et Entity2 et définissez les différentes valeurs de clé primaire.

5. Après avoir ajouté tous les remplacements que vous souhaitez appliquer, enregistrez le fichier modèle.

6. Accédez à **Données** > **Sources de données** et ingérez les fichiers de modèle en tant que nouvelles entités. Une fois ingérés, vous pouvez les utiliser pour spécifier la configuration de correspondance.

7. Une fois le téléchargement des fichiers et des entités disponibles, sélectionnez à nouveau l’option **Correspondance personnalisée**. Vous verrez des options pour spécifier les entités que vous souhaitez inclure. Sélectionnez les entités requises dans le menu déroulant.

   > [!div class="mx-imgBorder"]
   > ![Remplacements de correspondance personnalisés](media/custom-match-overrides.png "Remplacements de correspondance personnalisés")

8. Sélectionnez les entités que vous souhaitez utiliser pour **Toujours correspondre** et **Ne jamais correspondre**, sélectionnez **Terminé**.

9. Sélectionnez **Enregistrer** sur la page **Correspondance** pour la configuration de correspondance personnalisée que vous venez de définir.

10. Sélectionnez **Exécuter** sur la page **Correspondance** pour démarrer le processus de correspondance et la configuration de correspondance personnalisée sera prise en compte. Toutes les règles système correspondantes sont remplacées par le jeu de configuration.

11. Une fois la correspondance terminée, vous pouvez vérifier **ConflationMatchPair** pour confirmer que les remplacements sont appliqués dans les correspondances de confusion.

## <a name="next-step"></a>Étape suivante

Une fois que vous avez terminé le processus de correspondance pour au moins une paire de correspondance, vous êtes prêt à résoudre les contradictions possibles dans vos données en vous rendant à la rubrique [**Fusionner**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]