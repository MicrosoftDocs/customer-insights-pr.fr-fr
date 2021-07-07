---
title: Fusionner des entités pour l’unification des données
description: Fusionnez des données pour créer des profils clients unifiés.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305631"
---
# <a name="merge-entities"></a>Fusionner des entités

La fusion est la dernière phase du processus d’unification des données. Son objectif consiste à rapprocher les données conflictuelles. Des exemples de données en conflit sont le nom d’un client qui réside dans deux de vos jeux de données, avec une petite différence (« Martin Lucas » au lieu de « Martin »), ou un format de numéro de téléphone légèrement différent (06-78-03-09-1X et 067803091X). Fusionner ces points de données en conflit s’effectue d’une manière attribut par attribut.

:::image type="content" source="media/merge-fields-page.png" alt-text="Page de fusion dans le processus d’unification des données affichant une table avec des champs fusionnés qui définissent le profil client unifié.":::

Après avoir terminé la [phase de mise en correspondance](match-entities.md), vous pouvez entamer la phase de fusion en sélectionnant la vignette **Fusionner** sur la page **Unifier**.

## <a name="review-system-recommendations"></a>Examiner les recommandations système

Sur **Données** > **Unifier** > **Fusionner**, vous choisissez et excluez les attributs à fusionner au sein de votre entité de profil client unifiée. Le profil client unifié est le résultat du processus d’unification des données. Certains attributs sont automatiquement fusionnés par le système.

Pour afficher les attributs inclus dans l’un de vos attributs fusionnés automatiquement, sélectionnez cet attribut fusionné dans l’onglet **Champs client** de la table. Les attributs qui composent cet attribut fusionné s’affichent dans deux nouvelles lignes en dessous de l’attribut fusionné.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Séparer, renommer, exclure et modifier les champs fusionnés

Vous pouvez modifier la façon dont le système traite les attributs fusionnés pour générer le profil client unifié. Sélectionnez **Afficher plus** et choisissez ce que vous voulez changer.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Options du menu déroulant Afficher plus pour gérer les attributs fusionnés.":::

Pour plus d’informations, consultez les sections suivantes.

## <a name="separate-merged-fields"></a>Champs fusionnés séparés

Pour séparer des champs fusionnés, recherchez l’attribut dans la table. Les champs séparés s’affichent sous forme de points de données individuels sur le profil client unifié. 

1. Sélectionnez le champ fusionné.
  
1. Sélectionnez **Afficher plus** et choisissez **Séparer les champs**.
 
1. Confirmez la séparation.

1. Cliquez sur **Enregistrer**, puis sur **Exécuter** pour traiter les modifications.

## <a name="rename-merged-fields"></a>Renommer les champs fusionnés

Modifiez le nom d’affichage des attributs fusionnés. Vous ne pouvez pas modifier le nom de l’entité de sortie.

1. Sélectionnez le champ fusionné.
  
1. Sélectionnez **Afficher plus** et choisissez **Renommer**.

1. Confirmez le nom d’affichage modifié. 

1. Cliquez sur **Enregistrer**, puis sur **Exécuter** pour traiter les modifications.

## <a name="exclude-merged-fields"></a>Exclure les champs fusionnés

Excluez un attribut du profil client unifié. Si le champ est utilisé dans d’autres processus, par exemple dans un segment, supprimez-le de ces processus avant de l’exclure du profil client. 

1. Sélectionnez le champ fusionné.
  
1. Sélectionnez **Afficher plus** et choisissez **Exclure**.

1. Confirmez l’exclusion.

1. Cliquez sur **Enregistrer**, puis sur **Exécuter** pour traiter les modifications. 

Sur la page **Fusionner**, sélectionnez **Champs exclus** pour voir la liste de tous les champs exclus. Ce volet vous permet d’ajouter à nouveau des champs exclus.

## <a name="manually-combine-fields"></a>Combiner manuellement des champs

Spécifiez un attribut fusionné manuellement. 

1. Sur la page **Fusionner**, sélectionnez **Combiner les champs**.

1. Fournissez un **Nom** et un **Nom du champ de sortie**.

1. Choisissez un champ à ajouter. Sélectionnez **Ajouter des champs** pour combiner plus de champs.

1. Confirmez l’exclusion.

1. Cliquez sur **Enregistrer**, puis sur **Exécuter** pour traiter les modifications. 

## <a name="change-the-order-of-fields"></a>Modifier l’ordre des champs

Certaines entités contiennent plus de détails que d’autres. Si une entité inclut les dernières données concernant un champ, vous pouvez lui donner priorité par rapport aux autres entités lors de la fusion des valeurs.

1. Sélectionnez le champ fusionné.
  
1. Sélectionnez **Afficher plus** et choisissez **Modifier**.

1. Dans le volet **Combiner des champs**, sélectionnez **Monter/descendre** pour définir l’ordre ou faites-les glisser et déposez-les dans la position souhaitée.

1. Confirmez la modification.

1. Cliquez sur **Enregistrer**, puis sur **Exécuter** pour traiter les modifications.

## <a name="run-your-merge"></a>Exécuter la fusion

Que vous fusionniez manuellement les attributs ou laissiez le système le faire pour vous, à ce stade vous pouvez toujours exécuter votre fusion. Sélectionnez **Exécuter** sur la page **Fusionner** pour démarrer le processus.

> [!div class="mx-imgBorder"]
> ![Fusion des données - Enregistrer et exécuter](media/configure-data-merge-save-run.png "Fusion des données - Enregistrer et exécuter")

Choisissez **Exécuter uniquement une fusion** si vous souhaitez uniquement voir la sortie reflétée dans l’entité client unifiée. Les processus en aval seront actualisés comme [défini dans le calendrier d’actualisation](system.md#schedule-tab).

Choisissez **Exécuter les processus de fusion et en aval** pour actualiser le système avec vos modifications. Tous les processus, y compris l’enrichissement, les segments et les mesures, seront réexécutés automatiquement. Une fois tous les processus en aval terminés, les profils client reflètent toutes les modifications que vous avez apportées.

Pour apporter d’autres modifications et réexécuter l’étape, vous pouvez annuler une fusion en cours. Sélectionnez **Actualisation en cours...** et sélectionnez **Annuler la tâche** dans le volet latéral qui s’affiche.

> [!TIP]
> Il existe [six types de statuts](system.md#status-types) pour les tâches/processus. En outre, la plupart des processus [dépendent d’autres processus en aval](system.md#refresh-policies). Vous pouvez sélectionner le statut d’un processus pour afficher des détails sur la progression de toute la tâche. Après avoir sélectionné **Voir les détails** pour l’une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.

## <a name="next-step"></a>Étape suivante

Pour plus d'informations sur vos clients, configurez les [activités](activities.md), l'[enrichissement](enrichment-hub.md) ou les [relations](relationships.md).

Si vous avez déjà configuré des activités, un enrichissement ou des segments, ils seront traités automatiquement pour utiliser les dernières données client.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
