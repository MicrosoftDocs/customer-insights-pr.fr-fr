---
title: Mettre en correspondance des entités pour l’unification des données
description: Faites correspondre des entités pour combiner des jeux de données et créer des profils client unifiés.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
ms.openlocfilehash: cabeddbc9d485108d166e6355175a01721b75a55
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732631"
---
# <a name="match-entities"></a>Mettre en correspondance des entités

La phase de correspondance spécifie comment combiner vos ensembles de données dans un jeu de données de profil client unifié. Après avoir terminé la [phase de correspondance](map-entities.md) dans le processus d’unification des données, vous êtes prêt à mettre vos entités en correspondance. La phase de mise en correspondance nécessite au moins deux entités mappées.

La page de mise en correspondance se compose de trois sections : 
- Mesures clés qui résument le nombre d’enregistrements correspondants
- Ordre de correspondance et règles de correspondance entre entités
- Règles de déduplication des entités de correspondance

## <a name="specify-the-match-order"></a>Indiquer l’ordre de mise en correspondance

Allez à **Données** > **Unifier** > **Mettre en correspondance** et sélectionnez **Définir l’ordre** pour démarrer la phase de mise en correspondance.

Chaque correspondance unifie deux entités ou plus en une seule entité consolidée. Dans le même temps, elle conserve les enregistrements de client uniques. Par exemple, nous avons sélectionné deux entités : **eCommerce:eCommerceContacts** comme entité principale et **LoyaltyScheme:loyCustomers** comme deuxième entité. L’ordre des entités spécifie dans quel ordre le système essaiera de faire correspondre les enregistrements.

:::image type="content" source="media/match-page.png" alt-text="Capture d’écran de la page Mise en correspondance dans la zone Unifier du processus d’unification des données.":::
  
L’entité principale *eCommerce:eCommerceContacts* correspond à l’entité suivante *LoyaltyScheme:loyCustomers*. Le jeu de données qui résulte de la première étape de correspondance est mis en correspondance avec l’entité suivante si vous avez plusieurs entités.

> [!IMPORTANT]
> L’entité que vous choisissez comme entité principale servira de base pour votre jeu de données de profils unifié. Toutes les futures entités qui seront sélectionnées au cours de la phase de mise en correspondance seront ajoutées à cette entité. Cela ne signifie pas que l’entité unifiée comprendra *toutes* les données incluses dans cette entité.
>
> Deux considérations peuvent vous aider à choisir la hiérarchie de vos entités :
>
> - Choisissez l’entité avec les données de profil les plus complètes et les plus fiables sur vos clients en tant qu’entité principale.
> - Choisissez l’entité qui a plusieurs attributs en commun avec d’autres entités (par exemple, nom, numéro de téléphone ou adresse e-mail) comme entité principale.

Après avoir spécifié l’ordre de correspondance, vous verrez les paires de correspondance définies dans la section **Détails des enregistrements correspondants** dans **Données** > **Unifier** > **Mettre en correspondance**. Les mesures clés seront vides jusqu’à la fin du processus de correspondance.

## <a name="define-rules-for-match-pairs"></a>Définir les règles pour les paires de correspondance

Les règles de correspondance spécifient la logique par laquelle une paire spécifique d’entités sera mise en correspondance.

L’avertissement **Nécessite des règles** situé en regard d’un nom d’entité suggère qu’aucune règle de correspondance n’est définie pour une paire de correspondance. 

:::image type="content" source="media/match-rule-add.png" alt-text="Capture d’écran de la section Détails des enregistrements correspondants avec contrôle pour ajouter des règles en surbrillance.":::

1. Sélectionnez **Ajouter des règles** sous une entité dans la section **Détails des enregistrements correspondants** pour définir les règles de correspondance.

1. Dans le volet **Créer une règle**, configurez les conditions de la règle.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Capture d’écran d’une règle de correspondance ouverte avec conditions ajoutées.":::

   - **Entité/Champ (première ligne)**  : Choisissez une entité associée et un attribut pour spécifier une propriété d’enregistrement susceptible d’être unique pour un client. Par exemple, un numéro de téléphone ou une adresse e-mail. Évitez de faire correspondre par attributs du type Activité. Par exemple, un ID d’achat ne trouvera probablement aucune correspondance dans d’autres types d’enregistrement.

   - **Entité/Champ (deuxième ligne)**  : Choisissez un attribut lié à l’attribut de l’entité spécifié dans la première ligne.

   - **Normaliser** : Sélectionnez l’une des options de normalisation suivantes pour les attributs sélectionnés. 
     - Espace blanc : supprime tous les espaces. *Hello   World* devient *HelloWorld*.
     - Symboles : supprime tous les symboles et caractères spéciaux. *Head&Shoulder* devient *HeadShoulder*.
     - Texte en minuscules : convertit tous les caractères en minuscules. *TOUT EN MAJUSCULE et Casse du titre* devient *tout en majuscule et casse du titre*.
     - Unicode en ASCII : convertit la notation Unicode en caractères ASCII. */u00B2* devient *2*.
     - Chiffres : convertit d’autres systèmes numériques, tels que les chiffres romains, en chiffres arabes. *VIII* devient *8*.
     - Types sémantiques : standardise les noms, les titres, les numéros de téléphone, les adresses, etc. 

   - **Précision** : Définissez le niveau de précision à appliquer pour cette condition. 
     - **De base** : Choisissez l’une des options disponibles : *Faible*, *Moyen*, *Élevé* et *Exact*. Sélectionnez **Exact** pour ne faire correspondre que les enregistrements qui correspondent à 100 %. Sélectionnez un des autres niveaux pour mettre en correspondance les enregistrements qui ne sont pas identiques à 100 pour cent.
     - **Personnalisé** : Définissez un pourcentage auquel les enregistrements doivent correspondre. Le système ne fera correspondre que les enregistrements dépassant ce seuil.

1. Fournissez un **Nom** pour la règle.

1. [Ajoutez d’autres conditions](#add-conditions-to-a-rule) ou sélectionnez **Terminé** pour finaliser la règle.

1. Vous pouvez également [ajouter d’autres règles](#add-rules-to-a-match-pair).

1. Sélectionnez **Enregistrer** pour appliquer vos modifications.

### <a name="add-conditions-to-a-rule"></a>Ajouter des conditions à une règle

Pour faire correspondre des entités uniquement si les attributs remplissent plusieurs conditions, ajoutez d’autres conditions à une règle de correspondance. Les conditions sont connectées avec un opérateur ET logique et ne sont donc exécutées que si toutes les conditions sont remplies.

1. Accédez à **Données** > **Unifier** > **Mise en correspondance** et sélectionnez **Modifier** sur la règle à laquelle vous souhaitez ajouter des conditions.

1. Dans le volet **Modifier la règle**, sélectionnez **Ajouter une condition**.

1. Sélectionnez **Terminé** pour enregistrer la règle.

### <a name="add-rules-to-a-match-pair"></a>Ajouter des règles à une paire de correspondance

Les règles de correspondance représentent des ensembles de conditions. Pour faire correspondre des entités en fonction de conditions basées sur plusieurs attributs, ajoutez d’autres règles

1.  Accédez à **Données** > **Unifier** > **Mise en correspondance** et sélectionnez **Ajouter une règle** sur l’entité à laquelle vous souhaitez ajouter des règles.

2. Suivez les étapes de la section [Définir les règles pour les paires de correspondance](#define-rules-for-match-pairs).

> [!NOTE]
> L’ordre des règles est important. L’algorithme de correspondance tente d’effectuer une mise en correspondance sur la base de votre première règle et passe à la deuxième règle uniquement si aucune correspondance n’a été identifiée avec la première règle.

### <a name="change-the-entity-order-in-match-rules"></a>Modifier l’ordre des entités dans les règles de correspondance

Vous pouvez réorganiser les entités pour les règles de correspondance afin de modifier l’ordre dans lequel elles sont traitées. Les règles qui sont en conflit en raison d’un ordre modifié seront supprimées. Vous devez recréer les règles supprimées avec une configuration mise à jour.

1. Accédez à **Données** > **Unifier** > **Mettre en correspondance** et sélectionnez **Modifier**.

1. Dans le volet **Modifier la règle**, sélectionnez le contrôle **Monter/descendre** ou faites glisser et déposez des entités pour modifier l’ordre.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Options pour modifier l’ordre dans lequel les entités sont traitées dans la phase de correspondance.":::

1. Sélectionnez **Terminé** pour enregistrer la règle.

## <a name="define-deduplication-on-a-match-entity"></a>Définir la déduplication d’une entité de mise en correspondance

En plus des [règles de correspondance entre entités](#define-rules-for-match-pairs), vous pouvez également spécifier des règles de déduplication. La *déduplication* est un autre processus de mise en correspondance des enregistrements. Il consiste à identifier les enregistrements en double et à les fusionner en un seul enregistrement. Les enregistrements sources sont liés à l’enregistrement fusionné avec d’autres identifiants.

Les enregistrements dédupliqués seront utilisés dans le processus de mise en correspondance des entités. La déduplication se produit sur des entités distinctes et peut être configurée pour chaque entité utilisée dans les paires en correspondance.

La spécification de règles de déduplication n’est pas obligatoire. Si aucune règle de ce type n’est configurée, les règles définies par le système sont appliquées. Elles combinent tous les enregistrements en un seul enregistrement avant de transmettre les données d’entité à la correspondance entre entités pour améliorer les performances.

### <a name="add-deduplication-rules"></a>Ajouter des règles de déduplication

1. Accédez à **Données** > **Unifier** > **Mise en correspondance**.

1. Dans la section **Doublons fusionnés**, sélectionnez **Définir les entités**. Si des règles de déduplication sont déjà créées, sélectionnez **Modifier**.

1. Dans le volet **Préférences de fusion**, choisissez les entités pour lesquelles vous souhaitez exécuter la déduplication.

1. Spécifiez comment combiner les enregistrements en double et choisissez l’une des trois options :
   - **Les plus remplis** : identifie l’enregistrement avec les champs d’attributs les plus remplis comme enregistrement gagnant. C’est l’option de fusion par défaut.
   - **Les plus récents** : identifie l’enregistrement gagnant en fonction du plus récent. Nécessite une date ou un champ numérique pour définir l’ancienneté.
   - **Les moins récents** : identifie l’enregistrement gagnant en fonction du moins récent. Nécessite une date ou un champ numérique pour définir l’ancienneté.
 
   > [!div class="mx-imgBorder"]
   > ![Étape 1 des règles de déduplication.](media/match-selfconflation.png "Étape 1 des règles de déduplication")
 
1. Une fois les entités sélectionnées et leur préférence de fusion définie, sélectionnez **Ajouter une règle** pour définir les règles de déduplication au niveau de l’entité.
   - **Sélectionner un champ** répertorie tous les champs disponibles de cette entité. Choisissez le champ dans lequel vous souhaitez rechercher les doublons. Choisissez des champs susceptibles d’être uniques pour chaque client. Par exemple, une adresse e-mail ou la combinaison du nom, de la ville et du numéro de téléphone.
   - Spécifiez les paramètres de normalisation et de précision.
   - Définissez d’autres conditions en sélectionnant **Ajouter une condition**.
 
   > [!div class="mx-imgBorder"]
   > ![Étape 2 des règles de déduplication.](media/match-selfconflation-rules.png "Étape 2 des règles de déduplication")

  Vous pouvez créer plusieurs règles de déduplication pour une entité. 

1. L’exécution du processus de mise en correspondance regroupe maintenant les enregistrements en fonction des conditions définies dans les règles de déduplication. Une fois les enregistrements regroupés, la stratégie de fusion est appliquée pour identifier l’enregistrement gagnant.

1. Cet enregistrement gagnant est ensuite transmis à la mise en correspondance entre entités, avec les enregistrements non gagnants (par exemple, les autres ID) pour améliorer la qualité de la correspondance.

1. Toutes les règles de correspondance personnalisées définies remplacent les règles de déduplication. Si une règle de déduplication identifie des enregistrements correspondants et si une règle de mise en correspondance personnalisée est définie pour ne jamais correspondre à ces enregistrements, ces deux enregistrements ne seront pas mis en correspondance.

1. Après [l’exécution du processus de mise en correspondance](#run-the-match-process), vous verrez les statistiques de déduplication dans les vignettes de mesures clés.

### <a name="deduplication-output-as-an-entity"></a>Sortie de déduplication en tant qu’entité

Le processus de déduplication crée une nouvelle entité pour chaque entité à partir des paires de correspondance afin d’identifier les enregistrements dédupliqués. Ces entités peuvent être trouvées avec **ConflationMatchPairs:CustomerInsights** dans la section **Système** de la page **Entités**, avec le nom **Deduplication_DataSource_Entity**.

Une entité de sortie de déduplication contient les informations suivantes :
- ID/clés
  - Champ de clé primaire et son champ d’ID de remplacement. Le champ ID de remplacement comprend tous les ID de remplacement identifiés pour un enregistrement.
  - Le champ Deduplication_GroupId affiche le groupe ou le cluster identifié dans une entité qui regroupe tous les enregistrements similaires en fonction des champs de déduplication spécifiés. Il est utilisé à des fins de traitement du système. Si aucune règle de déduplication manuelle n’est spécifiée et que les règles de déduplication définies par le système s’appliquent, vous ne trouverez peut-être pas ce champ dans l’entité de sortie de déduplication.
  - Deduplication_WinnerId : ce champ contient l’ID gagnant des groupes ou clusters identifiés. Si Deduplication_WinnerId est identique à la valeur de clé primaire d’un enregistrement, cela signifie que l’enregistrement est l’enregistrement gagnant.
- Champs utilisés pour définir les règles de déduplication.
- Champs de règle et de score pour indiquer les règles de déduplication appliquées et le score renvoyé par l’algorithme de correspondance.
   
## <a name="run-the-match-process"></a>Exécuter le processus de mise en correspondance

Avec les règles de mise en correspondance définies, notamment les règles de mise en correspondance entre entités et de déduplication, vous pouvez exécuter le processus de mise en correspondance. 

Accédez à **Données** > **Unifier** > **Mise en correspondance** et sélectionnez **Exécuter** pour démarrer le processus. L’algorithme de correspondance prend un certain temps et vous ne pouvez pas modifier la configuration tant qu’il n’est pas terminé. Pour apporter des modifications, vous pouvez annuler l’exécution. Sélectionnez le statut de la tâche et sélectionnez **Annuler la tâche** sur le volet **Détails de la progression**.

Vous trouverez le résultat d’une exécution réussie, l’entité de profil client unifiée, sur la page **Entités**. Votre entité client unifiée est appelée **Clients** dans la section **Profils**. La première exécution de la mise en correspondance réussie crée l’entité *Client* unifiée. Toutes les correspondances suivantes développent cette entité.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>Examiner et valider vos correspondances

Accédez à **Données** > **Unifier** > **Mise en correspondance** pour évaluer la qualité de vos paires de correspondance et les affiner si nécessaire.

Les vignettes en haut de la page affichent les mesures clés, résumant le nombre d’enregistrements correspondants et de doublons.

:::image type="content" source="media/match-KPIs.png" alt-text="Capture d’écran recadrée des mesures clés de la page Mise en correspondance avec chiffres et détails.":::

- **Enregistrements source uniques** indique le nombre d’enregistrements source individuels qui ont été traités lors de la dernière mise en correspondance.
- **Enregistrements correspondants et non correspondants** met en évidence le nombre d’enregistrements uniques restants après le traitement des règles de correspondance.
- **Enregistrements correspondants uniquement** affiche le nombre de correspondances sur toutes vos paires de correspondances.

Vous pouvez évaluer les résultats de chaque paire de correspondance et ses règles dans le tableau **Détails des enregistrements correspondants**. Comparez le nombre d’enregistrements provenant d’une paire de correspondance avec le pourcentage d’enregistrements correctement mis en correspondance.

Passez en revue les règles d’une paire de correspondance pour voir le pourcentage d’enregistrements correctement mis en correspondance au niveau de la règle. Sélectionnez les points de suspension (...), puis sélectionnez **Aperçu de la correspondance** pour afficher tous ces enregistrements au niveau de la règle. Nous vous recommandons de consulter certains des enregistrements pour vérifier qu’ils correspondent bien.

Essayez différents seuils de précision sur les conditions pour trouver la valeur optimale.

  1. Sélectionnez les points de suspension (...) pour la règle que vous souhaitez expérimenter et sélectionnez **Modifier**.

  2. Modifiez les valeurs de précision dans les conditions que vous souhaitez réviser.

  3. Sélectionnez **Aperçu** pour consulter le nombre d’enregistrements correspondants et non correspondants pour la condition sélectionnée.

## <a name="manage-match-rules"></a>Gérer les règles de correspondance

Vous pouvez reconfigurer et affiner la plupart des paramètres de correspondance.

:::image type="content" source="media/match-rules-management.png" alt-text="Capture d’écran du menu déroulant avec les options de la règle de correspondance.":::

- **Modifier l’ordre de vos règles** si vous avez défini plusieurs règles. Vous pouvez réorganiser les règles de correspondance en sélectionnant les options **Déplacer vers le haut** et **Déplacer vers le bas** ou par glisser-déplacer.

- **Modifiez les conditions des règles** en sélectionnant **Modifier** et choisissez différents champs.

- **Désactiver une règle** pour conserver une règle de correspondance tout en l’excluant du processus de correspondance.

- **Dupliquez vos règles** si vous avez défini une règle de correspondance et souhaitez créer une règle similaire avec des modifications, sélectionnez **Dupliquer**.

- **Supprimez une règle** en sélectionnant le symbole **de suppression**.

## <a name="specify-custom-match-conditions"></a>Spécifier des conditions de correspondance personnalisées

Vous pouvez spécifier des conditions pour que certains enregistrements doivent toujours correspondre ou ne jamais correspondre. Ces règles peuvent être téléchargées pour remplacer le processus de correspondance standard. Par exemple, s’il y a John Doe I et John Doe II dans nos enregistrements, le système peut les associer comme une même personne. Les règles de correspondance personnalisées vous permettent de spécifier que leurs profils font référence à différentes personnes. 

1. Accédez à **Données** > **Unifier** > **Mise en correspondance** et sélectionnez **Correspondance personnalisée** dans la section **Détails des enregistrements correspondants**.

  :::image type="content" source="media/custom-match-create.png" alt-text="Capture d’écran de la section des règles de correspondance avec le contrôle Correspondance personnalisée mis en surbrillance.":::

1. Si vous n’avez pas défini de règles de correspondance personnalisée, un nouveau volet **Correspondance personnalisée** affiche plus de détails.

1. Sélectionnez **Remplir le modèle** pour obtenir un fichier modèle qui peut spécifier les enregistrements à partir desquels les entités doivent toujours correspondre ou ne jamais correspondre. Vous devez renseigner séparément les "enregistrements qui doivent toujours correspondre" et les "enregistrements qui ne doivent jamais correspondre" dans deux fichiers différents.

1. Le modèle contient des champs pour spécifier l’entité et les valeurs de clé primaire d’entité à utiliser dans la correspondance personnalisée. Par exemple, si vous souhaitez que la clé primaire *12345* de l’entité *Ventes* corresponde toujours à la clé primaire *34567* de l’entité *Contact*, remplissez le modèle :
    - Entité 1 : Ventes
    - Clé d’entité 1 : 12345
    - Entité 2 : Contact
    - Clé d’entité 2 : 34567

   Le même fichier modèle peut spécifier des enregistrements de correspondance personnalisés à partir de plusieurs entités.
   
   Si vous souhaitez spécifier une correspondance personnalisée pour la déduplication sur une entité, fournissez la même entité que Entity1 et Entity2 et définissez les différentes valeurs de clé primaire.

1. Après avoir ajouté tous les remplacements que vous souhaitez appliquer, enregistrez le fichier modèle.

1. Accédez à **Données** > **Sources de données** et ingérez les fichiers de modèle en tant que nouvelles entités. Une fois ingérés, vous pouvez les utiliser pour spécifier la configuration de correspondance.

1. Une fois le téléchargement des fichiers et des entités disponibles, sélectionnez à nouveau l’option **Correspondance personnalisée**. Vous verrez des options pour spécifier les entités que vous souhaitez inclure. Sélectionnez les entités requises dans le menu déroulant.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Capture d’écran de la boîte de dialogue pour choisir les remplacements pour un scénario de correspondance personnalisée.":::

1. Sélectionnez les entités que vous souhaitez utiliser pour **Toujours correspondre** et **Ne jamais correspondre**, sélectionnez **Terminé**.

1. Sélectionnez **Enregistrer** sur la page **Correspondance** pour appliquer la configuration de correspondance personnalisée.

1. Sélectionnez **Exécuter** sur la page **Mettre en correspondance** pour démarrer le processus. Les autres règles de correspondance spécifiées sont remplacées par la configuration de correspondance personnalisée.

> [!TIP]
> Accédez à **Données** > **Entités** et passez en revue l’entité **ConflationMatchPair** pour confirmer que les remplacements sont appliqués.

## <a name="next-step"></a>Étape suivante

Une fois que vous avez terminé le processus de correspondance pour au moins une paire de correspondance, vous êtes prêt à résoudre les contradictions possibles dans vos données en vous rendant à la rubrique [**Fusionner**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
