---
title: Entités et ensembles de données
description: Affichez les données sur la page Entités.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 00c5ee50fb9f0906622c91699852ffba0acb5c15
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900424"
---
# <a name="entities-in-audience-insights"></a>Entités dans les informations sur l’audience

Après la [configuration de vos sources de données](data-sources.md), accédez à la page **Entités** pour évaluer la qualité des données ingérées. Les entités sont considérées comme des ensembles de données. Plusieurs fonctionnalités de Dynamics 365 Customer Insights sont basées sur ces entités. Un examen approfondi peut vous aider à valider les résultats de ces fonctionnalités.

La page **Entités** répertorie les entités et comprend ces colonnes :

- **Nom** : nom de l’entité de données. Si vous voyez un symbole d’avertissement en regard de l’entité, cela signifie que les données de cette entité n’ont pas été chargées correctement.
- **Source** : type de la source de données qui a ingéré l’entité.
- **Mis à jour** : heure de la dernière mise à jour de l’entité.
- **Statut** : détails sur la dernière mise à jour de l’entité.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Explorer les données d’une entité spécifique

1. Dans les informations sur l’audience, accédez à **Données** > **Entités**.
1. Dans la page **Entités**, sélectionnez une entité pour ouvrir la page des détails.  
1. Explorez les différents champs et enregistrements inclus pour cette entité.

- L’onglet **Attributs** est sélectionné par défaut et affiche un tableau pour examiner les détails de l’entité sélectionnée, tels que les noms des champs, les types de données et les types. La colonne **Type** affiche les types associés à Common Data Model, qui sont soit identifiés automatiquement par le système, soit [mappés manuellement](map-entities.md) par les utilisateurs. Ces types sont des types sémantiques qui peuvent différer des types de données des attributs. Par exemple, le champ *E-mail* ci-dessous contient un type de données *Texte*, mais ce type Common Data Model (sémantique) pourrait être *E-mail* ou *Adresse e-mail*.

> [!div class="mx-imgBorder"]
> ![Table Champs.](media/data-manager-entities-fields.PNG "Table Champs")

> [!NOTE]
> Cette page n’affiche qu’un exemple des données de votre entité. Pour afficher le jeu de données complet, accédez à la page **Sources de données**, sélectionnez une entité d’intérêt, sélectionnez **Modifier**, puis affichez les données de cette entité dans l’éditeur Power Query, comme décrit dans [Sources de données](data-sources.md).

Pour en savoir plus sur les données ingérées dans l’entité, la colonne **Résumé** vous fournit quelques caractéristiques importantes des données, telles que les valeurs nulles, les valeurs manquantes, les valeurs uniques, les nombres et les distributions, selon vos données. Sélectionnez l’icône de graphique pour voir un récapitulatif des données.

> [!div class="mx-imgBorder"]
> ![Symbole récapitulatif.](media/data-manager-entities-summary.png "Table Résumé des données")

- L’onglet **Données** affiche un tableau répertoriant les détails des enregistrements individuels de l’entité. Les détails répertoriés dépendent du type de données de l’entité.

> [!div class="mx-imgBorder"]
> ![Sélectionnez une entité.](media/data-manager-entities-data.png "Sélectionner une entité")

- L’onglet **Rapports** (disponible pour certaines entités) vous permet de visualiser vos données en créant un rapport, et comprend ces colonnes :

  - **Nom du rapport :** nom du rapport.
  - **Créé par** : nom de la personne qui a créé l’entité.
  - **Créé** : date et heure de création de l’entité.
  - **Modifié par** : nom de la personne qui a modifié l’entité.
  - **Modifié** : date et heure de modification de l’entité. 

## <a name="entity-specific-information"></a>Informations propres à une entité

La section suivante fournit des informations sur certaines entités créées par le système.

### <a name="corrupted-data-sources"></a>Sources de données endommagée

Les champs d’une source de données ingérées peuvent contenir des données endommagées. Les enregistrements avec des champs endommagés sont exposés dans des entités créées par le système. Connaître les enregistrements endommagés vous aide à identifier les données à examiner et à mettre à jour sur le système source. Après la prochaine actualisation de la source de données, les enregistrements corrigés sont ingérés dans Customer Insights et transmis aux processus en aval. 

Par exemple, une colonne « anniversaire » a le type de données défini comme « date ». La date de naissance d’un enregistrement client est le « 01/01/19777 ». Le système marque cet enregistrement comme endommagé. Quelqu’un peut maintenant changer l’anniversaire dans le système source avec « 1977 ». Après une actualisation automatique des sources de données, le champ a désormais un format valide et l’enregistrement est supprimé de l’entité endommagée. 

Accédez à **Données** > **Entités** et recherchez les entités corrompues dans la section **Système**. Schéma d’affectation de nom des entités endommagées : « DataSourceName_EntityName_corrupt ».

Customer Insights traite toujours les enregistrements endommagés. Cependant, ils peuvent causer des problèmes lors de l’utilisation des données unifiées.

Les vérifications suivantes s’exécutent sur les données ingérées pour exposer les enregistrements endommagés : 

- La valeur d’un champ ne correspond pas au type de données de sa colonne.
- Les champs contiennent des caractères qui font que les colonnes ne correspondent pas au schéma attendu. Par exemple : guillemets mal formatés, guillemets sans échappement ou caractères de nouvelle ligne.
- S’il existe des colonnes datetime/date/datetimeoffset, leur format doit être spécifié dans le modèle s’il ne respecte pas le format ISO standard.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
