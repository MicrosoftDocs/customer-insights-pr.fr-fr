---
title: Supprimer les doublons avant d’unifier les données
description: La deuxième étape du processus d’unification consiste à sélectionner l’enregistrement à conserver lorsque des doublons sont détectés.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a838fbdabdb3bfffc6d3835a3f0e97306a43964a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139426"
---
# <a name="remove-duplicates-before-unifying-data"></a>Supprimer les doublons avant d’unifier les données

Cette étape de l’unification vous permet, si vous le souhaitez, de définir des règles de gestion des enregistrements en double au sein d’une entité. La règle de *déduplication* identifie les enregistrements en double et les fusionne en un seul enregistrement. Les enregistrements sources sont liés à l’enregistrement fusionné avec d’autres identifiants. Si aucune règle n’est configurée, les règles définies par le système sont appliquées.

## <a name="include-enriched-entities-preview"></a>Inclure les entités enrichies (version préliminaire)

Si vous avez enrichi des entités au niveau source de données pour améliorer vos résultats d’unification, sélectionnez-les. Pour plus d’informations, voir [Enrichissement des sources de données](data-sources-enrichment.md).

1. Sur la page **Enregistrements en double**, sélectionnez **Utiliser les entités enrichies** en haut de la page.

1. Dans le volet **Utiliser les entités enrichies**, choisissez une ou plusieurs entités enrichies.

1. Cliquez sur **Terminé**.

## <a name="define-deduplication-rules"></a>Définir des règles de déduplication

1. Sur la page **Enregistrements en double**, sélectionnez une entité, puis **Ajouter une règle** pour définir les règles de déduplication.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Capture d’écran de la page Enregistrements en double avec Afficher plus en surbrillance":::

   1. Entrez les informations suivantes dans le volet **Ajouter une règle** :
      - **Sélectionner un champ** : Choisissez l’entité dont vous souhaitez vérifier les doublons dans la liste des champs disponibles. Choisissez des champs susceptibles d’être uniques pour chaque client. Par exemple, une adresse e-mail ou la combinaison du nom, de la ville et du numéro de téléphone.
      - **Normaliser** : Sélectionnez l’une des options de normalisation suivantes pour les attributs sélectionnés.
        - **Valeurs numériques** : convertit d’autres systèmes numériques, tels que les chiffres romains, en chiffres arabes. *VIII* devient *8*.
        - **Symboles** : supprime tous les symboles et caractères spéciaux. *Head&Shoulder* devient *HeadShoulder*.
        - **Texte en minuscules : Convertit tous les caractères en minuscules**. *TOUT EN MAJUSCULE et Casse du titre* devient *tout en majuscule et casse du titre*.
        - **Type (Téléphone, Nom, Adresse, Organisation)**  : Normalise les noms, les fonctions, les numéros de téléphone, les adresses, etc.
        - **Unicode en ASCII** : convertit la notation Unicode en caractères ASCII. */u00B2* devient *2*.
        - **Espace blanc** : supprime tous les espaces. *Hello   World* devient *HelloWorld*.
      - **Précision** : Définissez le niveau de précision à appliquer pour cette condition.
        - **De base** : Choisissez parmi : *Faible (30 %)*, *Moyen (60 %)*, *Élevé (80 %)* et *Exact (100 %)*. Sélectionnez **Exact** pour faire correspondre uniquement les enregistrements qui correspondent à 100 %.
        - **Personnalisé** : Définissez un pourcentage auquel les enregistrements doivent correspondre. Le système ne fera correspondre que les enregistrements dépassant ce seuil.
      - **Nom** : Le nom de la règle.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Capture d’écran du volet Ajouter une règle pour supprimer les doublons.":::

   1. Vous pouvez, si vous le souhaitez, sélectionner **Ajouter** > **Ajouter une condition** pour ajouter plus de conditions à la règle. Les conditions sont connectées avec un opérateur ET logique et ne sont donc exécutées que si toutes les conditions sont remplies.

   1. Vous pouvez, si vous le souhaitez, sélectionner **Ajouter** > **Ajouter une exception** pour [ajouter des exceptions à la règle](match-entities.md#add-exceptions-to-a-rule). Les exceptions sont utilisées pour traiter les rares cas de faux positifs et de faux négatifs.

   1. Sélectionnez **Terminé** pour créer la règle.

1. Vous pouvez également [ajouter d’autres règles](#define-deduplication-rules).

1. Sélectionnez une entité, puis **Modifier les préférences de fusion**.

1. Dans le volet **Préférences de fusion** :
   1. Choisissez l’une des trois options pour déterminer quel enregistrement conserver si un doublon est détecté :
      - **Les plus remplis** : identifie l’enregistrement avec les champs d’attributs les plus remplis comme enregistrement gagnant. C’est l’option de fusion par défaut.
      - **Les plus récents** : identifie l’enregistrement gagnant en fonction du plus récent. Nécessite une date ou un champ numérique pour définir l’ancienneté.
      - **Les moins récents** : identifie l’enregistrement gagnant en fonction du moins récent. Nécessite une date ou un champ numérique pour définir l’ancienneté.
      
      En cas d’égalité, l’enregistrement gagnant est celui avec le MAX(PK) ou la plus grande valeur de clé primaire.
      
   1. Vous pouvez aussi définir des préférences de fusion sur des attributs individuels d’une entité, pour cela sélectionnez **Avancé** en bas du volet. Par exemple, vous pouvez choisir de conserver l’e-mail le plus récent ET l’adresse la plus complète de différents enregistrements. Développez l’entité pour voir tous ses attributs et définissez l’option à utiliser pour les attributs individuels. Si vous choisissez une option basée sur la récence, vous devez également spécifier un champ de date/heure qui définit la récence.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Volet des préférences de fusion avancées affichant les e-mails récents et l’adresse complète":::

   1. Sélectionnez **Terminé** pour appliquer vos préférences de fusion.

1. Après avoir défini les règles de déduplication et les préférences de fusion, sélectionnez **Suivant**.
  
> [!div class="nextstepaction"]
> [Étape suivante pour une seule entité : Unifier les champs](merge-entities.md)

> [!div class="nextstepaction"]
> [Étape suivante pour plusieurs entités : Conditions de correspondance](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Sortie de déduplication en tant qu’entité

Le processus de déduplication crée une nouvelle entité dédupliquée pour chacune des entités source. Ces entités peuvent être trouvées avec **ConflationMatchPairs:CustomerInsights** dans la section **Système** de la page **Entités**, avec le nom **Deduplication_DataSource_Entity**.

Une entité de sortie de déduplication contient les informations suivantes :

- ID/clés
  - Champs Clé primaire et ID secondaire. Le champ ID secondaire comprend tous les ID secondaires identifiés pour un enregistrement.
  - Le champ Deduplication_GroupId affiche le groupe ou le cluster identifié dans une entité qui regroupe tous les enregistrements similaires en fonction des champs de déduplication spécifiés. Il est utilisé à des fins de traitement du système. Si aucune règle de déduplication manuelle n’est spécifiée et que les règles de déduplication définies par le système s’appliquent, vous ne trouverez peut-être pas ce champ dans l’entité de sortie de déduplication.
  - Deduplication_WinnerId : ce champ contient l’ID gagnant des groupes ou clusters identifiés. Si Deduplication_WinnerId est identique à la valeur de clé primaire d’un enregistrement, cela signifie que l’enregistrement est l’enregistrement gagnant.
- Champs utilisés pour définir les règles de déduplication.
- Champs de règle et de score pour indiquer les règles de déduplication appliquées et le score renvoyé par l’algorithme de correspondance.

[!INCLUDE[footer-include](includes/footer-banner.md)]
