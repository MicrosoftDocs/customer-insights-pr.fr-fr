---
title: Entités et ensembles de données
description: Affichez les données sur la page Entités.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269373"
---
# <a name="entities-in-audience-insights"></a>Entités dans les informations sur l’audience

Après la [configuration de vos sources de données](data-sources.md), accédez à la page **Entités** pour évaluer la qualité des données ingérées. Les entités sont considérées comme des ensembles de données. Plusieurs fonctionnalités de Dynamics 365 Customer Insights sont basées sur ces entités. Un examen approfondi peut vous aider à valider les résultats de ces fonctionnalités.

La page **Entités** répertorie les entités et comprend plusieurs colonnes :

- **Nom** : Le nom de vos entités de données. Si vous voyez un symbole d’avertissement en regard de l’entité, cela signifie que les données de cette entité n’ont pas été chargées correctement.
- **Source** : le type de source de données qui a ingéré l’entité
- **Créée par** : Le nom de l’utilisateur qui a créé l’entité.
- **Créée** : La date et l’heure de création de l’entité
- **Mise à jour par** : Le nom de l’utilisateur qui a mis à jour l’entité.
- **Dernière mise à jour** : La date et l’heure de la dernière mise à jour de l’entité
- **Dernière actualisation** : La date et l’heure de la dernière actualisation des données

## <a name="exploring-a-specific-entitys-data"></a>Explorer les données d’une entité spécifique

Sélectionnez une entité pour explorer les différents champs et enregistrements inclus dans cette entité.

> [!div class="mx-imgBorder"]
> ![Sélectionner une entité](media/data-manager-entities-data.png "Sélectionner une entité")

- L’onglet **Données** est sélectionné par défaut et affiche un tableau répertoriant les détails des enregistrements individuels de l’entité.

> [!div class="mx-imgBorder"]
> ![Table Champs](media/data-manager-entities-fields.PNG "Table Champs")

- L’onglet **Champs** permet d’examiner les détails de l’entité sélectionnée, comme le nom des champs, les types de données, et les types. La colonne **Type** affiche les types associés à Common Data Model, qui sont soit identifiés automatiquement par le système, soit [mappés manuellement](map-entities.md) par les utilisateurs. Il s’agit de types sémantiques qui peuvent différer des types de données des attributs (par exemple, le champ *E-mail* ci-dessous contient un type de données *Texte*, mais ce type Common Data Model (sémantique) pourrait être *E-mail* ou *Adresse e-mail*) :

> [!NOTE]
> Les deux tableaux affichent uniquement un échantillon des données de votre entité. Pour afficher le jeu de données complet, accédez à la page **Sources de données**, sélectionnez une entité d’intérêt, sélectionnez **Modifier**, puis affichez les données de cette entité dans l’éditeur Power Query, comme décrit dans [Sources de données](data-sources.md).

Pour en savoir plus sur les données ingérées dans l’entité, la colonne **Résumé** vous fournit quelques caractéristiques importantes des données, telles que les valeurs nulles, les valeurs manquantes, les valeurs uniques, les nombres et les distributions, selon vos données.

Sélectionnez l’icône de graphique pour voir un récapitulatif des données.

> [!div class="mx-imgBorder"]
> ![Symbole récapitulatif](media/data-manager-entities-summary.png "Table Résumé des données")

### <a name="next-step"></a>Étape suivante

Consultez la rubrique [Unifier](data-unification.md) pour apprendre à *mapper*, *faire correspondre* et *fusionner* les données ingérées.


[!INCLUDE[footer-include](../includes/footer-banner.md)]