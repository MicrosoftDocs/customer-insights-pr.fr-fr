---
title: Mettre en correspondance des entités pour l’unification des données
description: Mettez en correspondance des données pour créer des profils clients unifiés.
ms.date: 02/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: ab4ab0dba1bd91b1893cd4b16b8d51381d5b6ef8
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376919"
---
# <a name="match-entities"></a>Mettre en correspondance des entités

La phase de correspondance spécifie comment combiner vos ensembles de données dans un jeu de données de profil client unifié. Après avoir terminé la [phase de correspondance](map-entities.md) dans le processus d’unification des données, vous êtes prêt à mettre vos entités en correspondance. La phase de mise en correspondance nécessite au moins deux entités mappées.

La page de mise en correspondance se compose de trois sections : 
- Mesures clés qui résument le nombre d’enregistrements correspondants
- Ordre de correspondance et règles de correspondance entre entités
- Règles de déduplication des entités de correspondance

## <a name="specify-the-match-order"></a>Indiquer l’ordre de mise en correspondance

Chaque correspondance unifie deux entités ou plus en une seule entité consolidée. Dans le même temps, elle conserve les enregistrements de client uniques. L'ordre de correspondance indique l'ordre dans lequel le système essaie de faire correspondre les enregistrements.

> [!IMPORTANT]
> L’entité que vous choisissez comme entité principale servira de base pour votre jeu de données de profils unifié. Toutes les futures entités qui seront sélectionnées au cours de la phase de mise en correspondance seront ajoutées à cette entité. Cela ne signifie pas que l’entité unifiée comprendra *toutes* les données incluses dans cette entité.
>
> Deux considérations peuvent vous aider à choisir la hiérarchie de vos entités :
>
> - Choisissez l’entité avec les données de profil les plus complètes et les plus fiables sur vos clients en tant qu’entité principale.
> - Choisissez l’entité qui a plusieurs attributs en commun avec d’autres entités (par exemple, nom, numéro de téléphone ou adresse de messagerie) comme entité principale.

1. Allez à **Données** > **Unifier** > **Mettre en correspondance** et sélectionnez **Définir l’ordre** pour démarrer la phase de mise en correspondance.
1. Sélectionnez **Ordre de l'entité**. Par exemple, sélectionnez **eCommerce:eCommerceContacts** en tant qu'entité principale et **LoyaltyScheme:loyCustomers** comme deuxième entité. 
1. Pour chaque enregistrement de l’entité comme client unique et mis en correspondance avec chaque entité suivante, cliquez sur **Inclure tout**.
1. Cliquez sur **Terminé**. 

Après avoir spécifié l'ordre de correspondance, les paires de correspondance définies s'affichent dans la section **Détails des enregistrements correspondants** sur **Données** > **Unifier** > **Mettre en correspondance**. Les métriques clés sont vides jusqu'à ce que le processus de correspondance soit terminé.

:::image type="content" source="media/match-page.png" alt-text="Capture d’écran de la page Mise en correspondance dans la zone Unifier du processus d’unification des données.":::
  
L’entité principale *eCommerce:eCommerceContacts* correspond à l’entité suivante *LoyaltyScheme:loyCustomers*. Le jeu de données issue de la première étape de correspondance est mis en correspondance avec l’entité suivante si vous avez plus de deux entités.

## <a name="define-rules-for-match-pairs"></a>Définir les règles pour les paires de correspondance

Les règles de correspondance spécifient la logique par laquelle une paire spécifique d’entités sera mise en correspondance.

L’avertissement **Nécessite des règles** situé en regard d’un nom d’entité suggère qu’aucune règle de correspondance n’est définie pour une paire de correspondance. 

:::image type="content" source="media/match-rule-add.png" alt-text="Capture d’écran de la section Détails des enregistrements correspondants avec contrôle pour ajouter des règles en surbrillance.":::

1. Sélectionnez **Ajouter une règle** sous une entité dans la section **Détails des enregistrements correspondants** pour définir les règles de correspondance.

1. Dans le volet **Créer une règle**, configurez les conditions de la règle.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Capture d’écran d’une règle de correspondance ouverte avec conditions ajoutées.":::

   - **Entité/Champ (première ligne)**  : Choisissez une entité associée et un attribut pour spécifier une propriété d’enregistrement susceptible d’être unique pour un client. Par exemple, un numéro de téléphone ou une adresse e-mail. Évitez de faire correspondre par attributs du type Activité. Par exemple, un ID d’achat ne trouvera probablement aucune correspondance dans d’autres types d’enregistrement.

   - **Entité/Champ (deuxième ligne)**  : Choisissez un attribut lié à l’attribut de l’entité spécifié dans la première ligne.

   - **Normaliser** : Sélectionnez l’une des options de normalisation suivantes pour les attributs sélectionnés. 
     - Chiffres : convertit d’autres systèmes numériques, tels que les chiffres romains, en chiffres arabes. *VIII* devient *8*.
     - Symboles : supprime tous les symboles et caractères spéciaux. *Head&Shoulder* devient *HeadShoulder*.
     - Texte en minuscules : convertit tous les caractères en minuscules. *TOUT EN MAJUSCULE et Casse du titre* devient *tout en majuscule et casse du titre*.
     - Type (Téléphone, Nom, Adresse, Organisation) : Normalise les noms, les titres, les numéros de téléphone, les adresses, etc. 
     - Unicode en ASCII : convertit la notation Unicode en caractères ASCII. */u00B2* devient *2*.
     - Espace blanc : supprime tous les espaces. *Hello   World* devient *HelloWorld*.

   - **Précision** : Définissez le niveau de précision à appliquer pour cette condition. 
     - **De base** : Choisissez l’une des options disponibles : *Faible*, *Moyen*, *Élevé* et *Exact*. Sélectionnez **Exact** pour faire correspondre uniquement les enregistrements qui correspondent à 100 %. Sélectionnez un des autres niveaux pour mettre en correspondance les enregistrements qui ne sont pas identiques à 100 pour cent.
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

Les règles de correspondance représentent des ensembles de conditions. Pour faire correspondre des entités en fonction de conditions basées sur plusieurs attributs, ajoutez d’autres règles.

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

Les enregistrements dédupliqués sont utilisés dans le processus de mise en correspondance des entités. La déduplication se produit sur des entités distinctes et peut être configurée pour chaque entité utilisée dans les paires en correspondance.

La spécification de règles de déduplication n’est pas obligatoire. Si aucune règle de ce type n’est configurée, les règles définies par le système sont appliquées. Elles combinent tous les enregistrements en un seul enregistrement avant de transmettre les données d’entité à la correspondance entre entités pour améliorer les performances.

### <a name="add-deduplication-rules"></a>Ajouter des règles de déduplication

1. Accédez à **Données** > **Unifier** > **Mise en correspondance**.

1. Dans la section **Détails des enregistrements dédupliqués**, sélectionnez **Définir les entités**. Si des règles de déduplication sont déjà créées, sélectionnez **Modifier**.

1. Dans le volet **Préférences de fusion**, choisissez les entités pour lesquelles vous souhaitez exécuter la déduplication.

   1. Spécifiez comment combiner les enregistrements en double et choisissez l’une des trois options :
      - **Les plus remplis** : identifie l’enregistrement avec les champs d’attributs les plus remplis comme enregistrement gagnant. C’est l’option de fusion par défaut.
      - **Les plus récents** : identifie l’enregistrement gagnant en fonction du plus récent. Nécessite une date ou un champ numérique pour définir l’ancienneté.
      - **Les moins récents** : identifie l’enregistrement gagnant en fonction du moins récent. Nécessite une date ou un champ numérique pour définir l’ancienneté.

   1. Pour définir des règles de déduplication sur les attributs individuels d’une entité, vous pouvez aussi sélectionner **Avancé**. Par exemple, vous pouvez choisir de conserver l’e-mail le plus récent ET l’adresse la plus complète de différents enregistrements. Développez l’entité pour voir tous ses attributs et définissez l’option à utiliser pour les attributs individuels. Si vous choisissez une option basée sur la récence, vous devez également spécifier un champ de date/heure qui définit la récence. 
 
      > [!div class="mx-imgBorder"]
      > ![Étape 1 des règles de déduplication.](media/match-selfconflation.png "Étape 1 des règles de déduplication")

   1. Sélectionnez **Fait** pour appliquer vos préférences de fusion pour la déduplication.
 
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

1. Après [avoir exécuté le processus de correspondance](#run-the-match-process), vous verrez les statistiques de déduplication dans les vignettes de métriques clés.

### <a name="deduplication-output-as-an-entity"></a>Sortie de déduplication en tant qu’entité

Le processus de déduplication crée une nouvelle entité pour chaque entité à partir des paires de correspondance afin d’identifier les enregistrements dédupliqués. Ces entités peuvent être trouvées avec **ConflationMatchPairs:CustomerInsights** dans la section **Système** de la page **Entités**, avec le nom **Deduplication_DataSource_Entity**.

Une entité de sortie de déduplication contient les informations suivantes :
- ID/clés
  - Champ de clé primaire et son champ d’ID de remplacement. Le champ ID de remplacement comprend tous les ID de remplacement identifiés pour un enregistrement.
  - Le champ Deduplication_GroupId affiche le groupe ou le cluster identifié dans une entité qui regroupe tous les enregistrements similaires en fonction des champs de déduplication spécifiés. Il est utilisé à des fins de traitement du système. Si aucune règle de déduplication manuelle n’est spécifiée et que les règles de déduplication définies par le système s’appliquent, vous ne trouverez peut-être pas ce champ dans l’entité de sortie de déduplication.
  - Deduplication_WinnerId : ce champ contient l’ID gagnant des groupes ou clusters identifiés. Si Deduplication_WinnerId est identique à la valeur de clé primaire d’un enregistrement, cela signifie que l’enregistrement est l’enregistrement gagnant.
- Champs utilisés pour définir les règles de déduplication.
- Champs de règle et de score pour indiquer les règles de déduplication appliquées et le score renvoyé par l’algorithme de correspondance.
 
## <a name="include-enriched-entities-preview"></a>Inclure les entités enrichies (version préliminaire)

Si vous avez enrichi des entités au niveau de la source de données, sélectionnez-les avant d’exécuter le processus de correspondance. Les entités enrichies peuvent améliorer vos résultats d’unification. Pour plus d’informations, voir [Enrichissement des sources de données](data-sources-enrichment.md). 

L’entité enrichie contient les champs de source de données originaux et les champs enrichis. Ainsi, si vous choisissez de travailler avec l’entité enrichie, la configuration existante n’est pas impactée. Cependant, vous devrez peut-être mettre à jour les règles de correspondance pour utiliser les champs enrichis à la place.

1. Allez dans **Données** > **Unifier** > **Correspondance** et sélectionnez **Utiliser les entités enrichies** en haut de la page.

1. Dans le volet **Utiliser les entités enrichies**, choisissez une ou plusieurs entités enrichies.

1. Cliquez sur **Terminé**. Partout où l’entité source est utilisée (telle que l’ordre de correspondance ou les règles), elle est automatiquement remplacée par l’entité enrichie.
  
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

## <a name="advanced-options"></a>Options avancées

### <a name="add-exceptions-to-a-rule"></a>Ajouter des exceptions à une règle

Dans la plupart des cas, la mise en correspondance des entités conduit à des profils d’utilisateurs uniques avec des données consolidées. Pour traiter dynamiquement les rares cas de faux positifs et de faux négatifs, vous pouvez définir des exceptions pour une règle de correspondance. Les exceptions sont appliquées après le traitement des règles de correspondance et évitent la correspondance de tous les enregistrements qui répondent aux critères d’exception.

Par exemple, si votre règle de correspondance combine le nom, la ville et la date de naissance, le système identifiera les jumeaux portant le même nom qui vivent dans la même ville que le même profil. Vous pouvez spécifier une exception qui ne correspond pas aux profils si les prénoms des entités que vous combinez ne sont pas les mêmes.

1. Accédez à **Données** > **Unifier** > **Mise en correspondance** et sélectionnez **Modifier** sur la règle à laquelle vous souhaitez ajouter des conditions.

1. Dans le volet **Modifier la règle**, sélectionnez **Ajouter une exception**.

1. Spécifiez les critères d’exception. 

1. Sélectionnez **Terminé** pour enregistrer la règle.

### <a name="specify-custom-match-conditions"></a>Spécifier des conditions de correspondance personnalisées

Vous pouvez spécifier des conditions qui remplacent la logique de correspondance par défaut. Il existe quatre options disponibles : 

|Option  |Description |Exemple  |
|---------|---------|---------|
|Toujours correspondre     | Définit des valeurs qui correspondent toujours.         |  Toujours correspondre *Mike* et *MikeR*.       |
|Jamais correspondre     | Définit des valeurs qui ne correspondent jamais.        | Jamais correspondre *John* et *Jonathan*.        |
|Contournement personnalisé     | Définit les valeurs que le système doit toujours ignorer dans la phase de correspondance. |  Ignorer les valeurs *11111* et *Inconnu* pendant la correspondance.        |
|Mise en correspondance d’alias    | Définir des valeurs que le système doit considérer comme identiques.         | Considérer *Joe* comme égal à *Joseph*.        |

1. Accédez à **Données** > **Unifier** > **Mise en correspondance** et sélectionnez **Correspondance personnalisée** dans la section **Détails des enregistrements correspondants**.

   :::image type="content" source="media/custom-match-create.png" alt-text="Capture d’écran de la section des règles de correspondance avec le contrôle Correspondance personnalisée mis en surbrillance.":::

1. Dans le volet **Personnalisé**, accédez à l’onglet **Enregistrements**.

1. Choisissez l’option de correspondance personnalisée dans la liste déroulante **Type personnalisé** et sélectionnez **Télécharger le modèle**. Vous avez besoin d’un modèle distinct pour chaque option de correspondance.

1. Ouvrez le fichier de modèle téléchargé et remplissez les détails. Le modèle contient des champs pour spécifier l’entité et les valeurs de clé primaire d’entité à utiliser dans la correspondance personnalisée. Par exemple, si vous souhaitez que la clé primaire *12345* de l’entité *Ventes* corresponde toujours à la clé primaire *34567* de l’entité *Contact*, remplissez le modèle :
    - Entité 1 : Ventes
    - Clé d’entité 1 : 12345
    - Entité 2 : Contact
    - Clé d’entité 2 : 34567

   Le même fichier modèle peut spécifier des enregistrements de correspondance personnalisés à partir de plusieurs entités.
   
   Si vous souhaitez spécifier une correspondance personnalisée pour la déduplication sur une entité, fournissez la même entité que Entity1 et Entity2 et définissez les différentes valeurs de clé primaire.

1. Après avoir ajouté tous les remplacements, enregistrez le modèle de fichier.

1. Accédez à **Données** > **Sources de données** et ingérez les fichiers de modèle en tant que nouvelles entités.

1. Une fois le téléchargement des fichiers et des entités disponibles, sélectionnez à nouveau l’option **Correspondance personnalisée**. Vous verrez des options pour spécifier les entités que vous souhaitez inclure. Sélectionnez les entités requises dans le menu déroulant et sélectionnez **Terminé**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Capture d’écran de la boîte de dialogue pour choisir les remplacements pour un scénario de correspondance personnalisée.":::

1. L’application de la correspondance personnalisée dépend de l’option de correspondance que vous souhaitez utiliser. 

   - Pour **Toujours correspondre** ou **Jamais correspondre**, passez à l’étape suivante.
   - Pour **Contournement personnalisé** ou **Mappage d’alias**, sélectionnez **Modifier** sur une règle de correspondance existante ou créez une règle. Dans la liste déroulante Standardisations, choisissez l’option **Contournement personnalisé** ou **Mappage d’alias** et sélectionnez **Terminé**.

1. Sélectionnez **Enregistrer** sur la page **Correspondance** pour appliquer la configuration de correspondance personnalisée.

1. Sélectionnez **Exécuter** sur la page **Mettre en correspondance** pour démarrer le processus. Les autres règles de correspondance spécifiées sont remplacées par la configuration de correspondance personnalisée.

#### <a name="known-issues"></a>Problèmes connus

- L’appariement autonome n’affiche pas les données standardisées dans les entités de déduplication. Cependant, il applique la standardisation en interne lors de la déduplication. Il concerne toutes les standardisations à dessein. 
- Si le paramètre de type sémantique est supprimé dans la phase **Mappage** lorsqu’une règle de correspondance utilise Mappage d’alias ou Contournement personnalisé, la standardisation ne sera pas appliquée. Cela ne se produit que si vous effacez le type sémantique après avoir configuré la standardisation dans la règle de correspondance, car le type sémantique sera inconnu.


## <a name="next-step"></a>Étape suivante

Après avoir terminé le processus de correspondance pour au moins une paire de correspondances, passez à l’étape [**Fusionner**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
