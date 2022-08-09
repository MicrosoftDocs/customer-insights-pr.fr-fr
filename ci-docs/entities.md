---
title: Entités dans Customer Insights
description: Affichez les données sur la page Entités.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183548"
---
# <a name="entities-in-customer-insights"></a>Entités dans Customer Insights

Après la [configuration de vos sources de données](data-sources.md), accédez à la page **Entités** pour évaluer la qualité des données ingérées. Les entités sont considérées comme des ensembles de données. Plusieurs fonctionnalités de Dynamics 365 Customer Insights sont basées sur ces entités. Un examen approfondi peut vous aider à valider les résultats de ces fonctionnalités.

Lorsque vous travaillez dans Customer Insights pour enrichir vos données ou créer des segments, des mesures et des activités, les entités créées à partir de ces actions s’affichent sur la page **Entités**.

## <a name="view-a-list-of-entities"></a>Afficher une liste d’entités

Accédez à **Données** > **Entités** pour afficher une liste d’entités. Les informations suivantes s’affichent pour chaque entité.

- **Nom** : nom de l’entité de données. Si vous voyez un symbole d’avertissement en regard de l’entité, cela signifie que les données de cette entité n’ont pas été chargées correctement.
- **Source** : type de la source de données qui a ingéré l’entité.
- **Mis à jour** : heure de la dernière mise à jour de l’entité.
- **Statut** : détails sur la dernière mise à jour de l’entité.

## <a name="explore-a-specific-entitys-data"></a>Explorer les données d’une entité spécifique

1. Accédez à **Données** > **Entités**.
1. Sélectionnez une entité pour ouvrir la page des détails.  
1. Explorez les différents champs et enregistrements inclus pour cette entité.

- L’onglet **Attributs** est sélectionné par défaut et affiche les détails de l’entité sélectionnée, tels que les noms des champs, les types de données et les types. La colonne **Type** affiche les types associés à Common Data Model, qui sont soit identifiés automatiquement par le système, soit [mappés manuellement](map-entities.md) par les utilisateurs. Ces types sont des types sémantiques qui peuvent différer des types de données des attributs. Par exemple, le champ *E-mail* ci-dessous a le type de données *Chaîne* mais son type Common Data Model (sémantique) peut-être *E-mail*, *Adresse e-mail* ou *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Table Champs.":::

   > [!NOTE]
   > Cette page n’affiche qu’un exemple des données de votre entité. Pour afficher le jeu de données complet, accédez à la page **Sources de données**, sélectionnez une entité d’intérêt, sélectionnez **Modifier**, puis affichez les données de cette entité dans l’éditeur Power Query, comme décrit dans [Sources de données](data-sources.md).

   Pour en savoir plus sur les données ingérées dans l’entité, la colonne **Résumé** fournit certaines caractéristiques importantes de données, telles que les valeurs nulles, les valeurs manquantes, les valeurs uniques, les nombres et les distributions, selon vos besoins. Sélectionnez l’icône de graphique pour voir un récapitulatif des données.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Table Résumé des données":::

- L’onglet **Données** affiche les détails des enregistrements individuels de l’entité. Les détails répertoriés dépendent du type de données de l’entité.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Sélectionnez une entité.":::

- L’onglet **Rapports** (disponible pour certaines entités) vous permet de visualiser vos données en créant un rapport, qui comprend ces colonnes :

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

Accédez à **Données** > **Entités** et recherchez les entités corrompues dans la section **Système**. Schéma d’affectation de nom des entités endommagées : « DataSourceName_EntityName_corrupt ». Sélectionnez une entité corrompue pour identifier les champs corrompus et la raison au niveau de l’enregistrement individuel.

   :::image type="content" source="media/corruption-reason.png" alt-text="Raison de la corruption.":::

Customer Insights traite toujours les enregistrements endommagés. Cependant, ils peuvent causer des problèmes lors de l’utilisation des données unifiées.

Les vérifications suivantes s’exécutent sur les données ingérées pour exposer les enregistrements endommagés :

- La valeur d’un champ ne correspond pas au type de données de sa colonne.
- Les champs contiennent des caractères qui font que les colonnes ne correspondent pas au schéma attendu. Par exemple : guillemets mal formatés, guillemets sans échappement ou caractères de nouvelle ligne.
- S’il existe des colonnes datetime/date/datetimeoffset, leur format doit être spécifié dans le modèle s’il ne respecte pas le format ISO standard.

[!INCLUDE [footer-include](includes/footer-banner.md)]
