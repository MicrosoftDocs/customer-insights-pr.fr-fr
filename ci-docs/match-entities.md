---
title: Mettre en correspondance des entités pour l’unification des données
description: Mettez en correspondance des données pour créer des profils clients unifiés.
recommendations: false
ms.date: 05/05/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: bc470dd932c2c981adc5840bb52d60f8dfe0de61
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740946"
---
# <a name="match-conditions"></a>Conditions de correspondance

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Cette étape de l’unification définit l’ordre de correspondance et les règles pour la mise en correspondance entre entités. Cette étape nécessite au moins deux entités.

> [!NOTE]
> Une fois que vous avez créé vos conditions de correspondance et sélectionné **Suivant**, vous ne pouvez pas supprimer une entité ou un attribut sélectionné. Si nécessaire, sélectionnez **Retour** pour passer en revue les entités et les attributs sélectionnés avant de continuer.

## <a name="include-enriched-entities-preview"></a>Inclure les entités enrichies (version préliminaire)

Si vous avez enrichi des entités au niveau source de données pour améliorer vos résultats d’unification, sélectionnez-les. Pour plus d’informations, voir [Enrichissement des sources de données](data-sources-enrichment.md). Si vous avez sélectionné des entités enrichies sur la page **Enregistrements en double**, vous n’avez pas besoin de les sélectionner à nouveau.

1. Sur la page **Conditions de correspondance**, sélectionnez **Utiliser les entités enrichies** en haut de la page.

1. Dans le volet **Utiliser les entités enrichies**, choisissez une ou plusieurs entités enrichies.

1. Cliquez sur **Terminé**.

## <a name="specify-the-match-order"></a>Indiquer l’ordre de mise en correspondance

Chaque correspondance unifie deux entités ou plus en une seule entité consolidée. Dans le même temps, elle conserve les enregistrements de client uniques. L’ordre de correspondance indique l’ordre dans lequel le système essaie de faire correspondre les enregistrements.

> [!IMPORTANT]
> La première entité de la liste s’appelle l’entité principale. L’entité principale sert de base à votre jeu de données de profils unifié. Les entités supplémentaires sélectionnées seront ajoutées à cette entité.
>
> Remarques importantes :
>
> - Choisissez l’entité ayant les données de profil les plus complètes et les plus fiables sur vos clients comme entité principale.
> - Choisissez l’entité ayant plusieurs attributs en commun avec d’autres entités (par exemple, nom, numéro de téléphone ou adresse de messagerie) comme entité principale.

1. Sur la page **Conditions de correspondance**, utilisez les flèches de déplacement vers le haut et vers le bas pour déplacer les entités dans l’ordre que vous souhaitez, ou faites-les glisser et déposez-les. Par exemple, sélectionnez **Contacts:eCommerce** en tant qu’entité principale et **CustomerLoyalty:Loyalty** comme deuxième entité.

1. Pour chaque enregistrement de l’entité comme client unique (qu’une correspondance soit trouvée ou non), sélectionnez **Inclure tous les enregistrements**. Tous les enregistrements de cette entité qui ne correspondent pas aux enregistrements d’autres entités sont inclus dans le profil unifié. Les enregistrements qui n’ont pas de correspondance sont appelés singletons.
  
L’entité principale *Contacts:eCommerce* correspond à l’entité suivante *CustomerLoyalty:Loyalty*. Le jeu de données issue de la première étape de correspondance est mis en correspondance avec l’entité suivante si vous avez plus de deux entités.

:::image type="content" source="media/m3_match.png" alt-text="Capture d’écran de l’ordre de correspondance sélectionné pour les entités." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Définir les règles pour les paires de correspondance

Les règles de correspondance spécifient la logique par laquelle une paire spécifique d’entités sera mise en correspondance. Une règle se compose d’une ou plusieurs conditions.

L’avertissement à côté d’un nom d’entité signifie qu’aucune règle de correspondance n’est définie pour une paire de correspondance.

1. Sélectionner **Ajouter une règle** pour une paire d’entités afin de définir des règles de correspondance.

1. Dans le volet **Ajouter une règle**, configurez les conditions de la règle.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Capture d’écran du volet Ajouter une règle.":::

   - **Sélectionner Entité/Champ (première ligne)**  : choisissez une entité associée et un attribut pour spécifier une propriété d’enregistrement susceptible d’être unique pour un client. Par exemple, un numéro de téléphone ou une adresse e-mail. Évitez de faire correspondre par attributs du type Activité. Par exemple, un ID d’achat ne trouvera probablement aucune correspondance dans d’autres types d’enregistrement.

   - **Sélectionner Entité/Champ (deuxième ligne)**  : choisissez un attribut lié à l’attribut de l’entité spécifiée dans la première ligne.

   - **Normaliser** : Sélectionnez l’une des options de normalisation suivantes pour les attributs sélectionnés.
     - **Valeurs numériques** : convertit d’autres systèmes numériques, tels que les chiffres romains, en chiffres arabes. *VIII* devient *8*.
     - **Symboles** : supprime tous les symboles et caractères spéciaux. *Head&Shoulder* devient *HeadShoulder*.
     - **Texte en minuscules** : Convertit tous les caractères en minuscules. *TOUT EN MAJUSCULE et Casse du titre* devient *tout en majuscule et casse du titre*.
     - **Type (Téléphone, Nom, Adresse, Organisation)**  : Normalise les noms, les fonctions, les numéros de téléphone, les adresses, et les organisations.
     - **Unicode en ASCII** : convertit la notation Unicode en caractères ASCII. */u00B2* devient *2*.
     - **Espace blanc** : supprime tous les espaces. *Hello   World* devient *HelloWorld*.

   - **Précision** : Définissez le niveau de précision à appliquer pour cette condition.
     - **De base** : Choisissez parmi : *Faible (30 %)*, *Moyen (60 %)*, *Élevé (80 %)* et *Exact (100 %)*. Sélectionnez **Exact** pour faire correspondre uniquement les enregistrements qui correspondent à 100 %.
     - **Personnalisé** : Définissez un pourcentage auquel les enregistrements doivent correspondre. Le système ne fera correspondre que les enregistrements dépassant ce seuil.

   - **Nom** : Le nom de la règle.

1. Pour faire correspondre les entités uniquement si les attributs remplissent plusieurs conditions, sélectionnez **Ajouter** > **Ajouter une condition** pour ajouter plus de conditions à une règle de correspondance. Les conditions sont connectées avec un opérateur ET logique et ne sont donc exécutées que si toutes les conditions sont remplies.

1. Vous pouvez, si vous le souhaitez, choisir des options avancées telles que [exceptions](#add-exceptions-to-a-rule) ou [conditions de correspondance personnalisées](#specify-custom-match-conditions).

1. Sélectionnez **Terminé** pour finaliser la règle.

1. Vous pouvez également [ajouter d’autres règles](#add-rules-to-a-match-pair).

1. Cliquez sur **Suivant**.

> [!div class="nextstepaction"]
> [Étape suivante : Unifier les champs](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Ajouter des règles à une paire de correspondance

Les règles de correspondance représentent des ensembles de conditions. Pour faire correspondre des entités en fonction de conditions basées sur plusieurs attributs, ajoutez d’autres règles.

1. Sélectionnez **Ajouter une règle** sur l’entité à laquelle vous souhaitez ajouter des règles.

1. Suivez les étapes de la section [Définir les règles pour les paires de correspondance](#define-rules-for-match-pairs).

> [!NOTE]
> L’ordre des règles est important. L’algorithme de mise en correspondance tente d’effectuer une mise en correspondance en fonction d’un enregistrement de client sur la base de la première règle et passe à la seconde règle si aucune correspondance n’est identifiée en vertu de la première règle.

## <a name="advanced-options"></a>Options avancées

### <a name="add-exceptions-to-a-rule"></a>Ajouter des exceptions à une règle

Dans la plupart des cas, la mise en correspondance des entités conduit à des profils client uniques avec des données consolidées. Pour traiter dynamiquement les rares cas de faux positifs et de faux négatifs, vous pouvez définir des exceptions pour une règle de correspondance. Les exceptions sont appliquées après le traitement des règles de correspondance et évitent la correspondance de tous les enregistrements qui répondent aux critères d’exception.

Par exemple, si votre règle de correspondance combine le nom, la ville et la date de naissance, le système identifiera les jumeaux portant le même nom qui vivent dans la même ville que le même profil. Vous pouvez spécifier une exception qui ne correspond pas aux profils si les prénoms des entités que vous combinez ne sont pas les mêmes.

1. Dans le volet **Modifier la règle**, sélectionnez **Ajouter** > **Ajouter une exception**.

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

1. Sélectionnez **Personnalisé**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Bouton personnalisé":::

1. Choisissez le **Type personnalisé** et sélectionnez **Télécharger le modèle**. Vous avez besoin d’un modèle distinct pour chaque option de correspondance.

1. Ouvrez le fichier de modèle téléchargé et remplissez les détails. Le modèle contient des champs pour spécifier l’entité et les valeurs de clé primaire d’entité à utiliser dans la correspondance personnalisée. Par exemple, si vous souhaitez que la clé primaire *12345* de l’entité *Ventes* corresponde toujours à la clé primaire *34567* de l’entité *Contact*, remplissez le modèle :
    - Entité 1 : Ventes
    - Clé d’entité 1 : 12345
    - Entité 2 : Contact
    - Clé d’entité 2 : 34567

   Le même fichier modèle peut spécifier des enregistrements de correspondance personnalisés à partir de plusieurs entités.

   Si vous souhaitez spécifier une correspondance personnalisée pour la déduplication sur une entité, fournissez la même entité que Entity1 et Entity2 et définissez les différentes valeurs de clé primaire.

1. Après avoir ajouté tous les remplacements, enregistrez le modèle de fichier.

1. Accédez à **Données** > **Sources de données** et ingérez les fichiers de modèle en tant que nouvelles entités.

1. Après avoir téléchargé les fichiers, sélectionnez à nouveau l’option **Personnalisé**. Sélectionnez les entités requises dans le menu déroulant et sélectionnez **Terminé**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Capture d’écran de la boîte de dialogue pour choisir les remplacements pour un scénario de correspondance personnalisée.":::

1. L’application de la correspondance personnalisée dépend de l’option de correspondance que vous souhaitez utiliser.

   - Pour **Toujours correspondre** ou **Jamais correspondre**, passez à l’étape suivante.
   - Pour **Contournement** ou **Mappage d’alias**, sélectionnez **Modifier** sur une règle de correspondance existante ou créez une règle. Dans la liste déroulante Standardisations, choisissez l’option **Contournement personnalisé** ou **Mappage d’alias** et sélectionnez **Terminé**.

1. Sélectionnez **Terminé** sur le volet **Personnalisé** pour appliquer la configuration de correspondance personnalisée.

> [!div class="nextstepaction"]
> [Étape suivante : Unifier les champs](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
