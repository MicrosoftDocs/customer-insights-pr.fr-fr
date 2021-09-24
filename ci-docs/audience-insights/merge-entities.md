---
title: Fusionner des entités pour l’unification des données
description: Fusionnez des données pour créer des profils clients unifiés.
ms.date: 09/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b038cd3f5b433fedf918d34bbfaf2261e11c5c17
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494316"
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

1. Sélectionnez un champ fusionné.
  
1. Sélectionnez **Afficher plus** et choisissez **Exclure**.

1. Confirmez l’exclusion.

1. Cliquez sur **Enregistrer**, puis sur **Exécuter** pour traiter les modifications. 

Sur la page **Fusionner**, sélectionnez **Champs exclus** pour voir la liste de tous les champs exclus. Ce volet vous permet d’ajouter à nouveau des champs exclus.

## <a name="edit-a-merged-field"></a>Modifier un champ fusionné

1.  Sélectionnez un champ fusionné.

1.  Sélectionnez **Afficher plus** et choisissez **Modifier**.

1.  Spécifiez comment combiner ou fusionner les champs de l’une des trois options :
    - **Importance** : identifie la valeur gagnante en fonction du rang d’importance spécifié pour les champs participants. C’est l’option de fusion par défaut. Sélectionnez **Monter/Descendre** pour définir le classement par importance.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Option Importance dans la boîte de dialogue de champs de fusion."::: 
    - **Le plus récent** : identifie la valeur gagnante en fonction de l’ancienneté la plus faible. Nécessite une date ou un champ numérique pour chaque entité participante dans la portée des champs de fusion pour définir la récence.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Option Récence dans la boîte de dialogue de champs de fusion.":::
    - **Le moins récent** : identifie la valeur gagnante en fonction de l’ancienneté la plus grande. Nécessite une date ou un champ numérique pour chaque entité participante dans la portée des champs de fusion pour définir la récence.

1.  Vous pouvez ajouter des champs supplémentaires pour participer au processus de fusion.

1.  Vous pouvez renommer le champ fusionné.

1. Sélectionnez **Terminé** pour appliquer vos modifications.

1. Cliquez sur **Enregistrer**, puis sur **Exécuter** pour traiter les modifications. 

## <a name="manually-combine-fields"></a>Combiner manuellement des champs

Spécifiez un attribut fusionné manuellement. 

1. Sur la page **Fusionner**, sélectionnez **Combiner les champs**.

1. Spécifiez la stratégie gagnante de fusion dans le menu déroulant **Combiner les champs par**.

1. Choisissez un champ à ajouter. Sélectionnez **Ajouter des champs** pour combiner plus de champs.

1. Fournissez un **Nom** et un **Nom du champ de sortie**.

1. Sélectionnez **Terminé** pour appliquer les modifications.

1. Cliquez sur **Enregistrer**, puis sur **Exécuter** pour traiter les modifications. 

## <a name="change-the-order-of-fields"></a>Modifier l’ordre des champs

Certaines entités contiennent plus de détails que d’autres. Si une entité inclut les dernières données concernant un champ, vous pouvez lui donner priorité par rapport aux autres entités lors de la fusion des valeurs.

1. Sélectionnez le champ fusionné.
  
1. Sélectionnez **Afficher plus** et choisissez **Modifier**.

1. Dans le volet **Combiner des champs**, sélectionnez **Monter/descendre** pour définir l’ordre ou faites-les glisser et déposez-les dans la position souhaitée.

1. Confirmez la modification.

1. Cliquez sur **Enregistrer**, puis sur **Exécuter** pour traiter les modifications.

## <a name="configure-customer-id-generation"></a>Configurer la génération de l’ID client 

Après avoir configuré les champs de fusion, vous pouvez définir comment générer les valeurs CustomerId, les identificateurs uniques du profil client. L’étape de fusion du processus d’unification des données génère l’identificateur unique du profil client. L’identificateur est le CustomerId de l’entité *Client* qui résulte du processus d’unification des données. 

Le CustomerId de l’entité Client est basé sur un hachage de la première valeur des clés primaires gagnantes non nulles. Ces clés proviennent des entités utilisées dans la phase de correspondance et de fusion et sont influencées par l’ordre de correspondance. Ainsi, le CustomerID généré peut changer lorsqu’une valeur de clé primaire change dans l’entité principale de l’ordre de correspondance. Par conséquent, il se peut que la valeur de la clé primaire ne représente pas toujours le même client.

La configuration d’un ID client stable vous permet d’éviter ce comportement.

**Configurer un ID client unique**

1. Accédez à **Unifier** > **Fusionner**.

1. Sur la page **Fusionner**, sélectionnez l’onglet **Clés**. 

1. Pointez sur la ligne **CustomerId** et sélectionnez l’option **Configurer**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Contrôle pour personnaliser la génération de l’ID.":::

1. Sélectionnez jusqu’à cinq champs qui comprennent un ID client unique et sont plus stables. Les enregistrements qui ne correspondent pas à votre configuration utilisent un ID configuré par le système à la place.  

1. Sélectionnez **Terminé** et exécutez le processus de fusion pour appliquer vos modifications.

## <a name="run-your-merge"></a>Exécuter la fusion

Que vous fusionniez manuellement les attributs ou laissiez le système le faire pour vous, à ce stade vous pouvez toujours exécuter votre fusion. Sélectionnez **Exécuter** sur la page **Fusionner** pour démarrer le processus.

> [!div class="mx-imgBorder"]
> ![Fusion des données - Enregistrez et exécutez.](media/configure-data-merge-save-run.png "Fusion des données - Enregistrer et exécuter")

Choisissez **Exécuter uniquement une fusion** si vous souhaitez uniquement voir la sortie reflétée dans l’entité client unifiée. Les processus en aval seront actualisés comme [défini dans le calendrier d’actualisation](system.md#schedule-tab).

Choisissez **Exécuter les processus de fusion et en aval** pour actualiser le système avec vos modifications. Tous les processus, y compris l’enrichissement, les segments et les mesures, seront réexécutés automatiquement. Une fois tous les processus en aval terminés, les profils client reflètent toutes les modifications que vous avez apportées.

Pour apporter d’autres modifications et réexécuter l’étape, vous pouvez annuler une fusion en cours. Sélectionnez **Actualisation en cours...** et sélectionnez **Annuler la tâche** dans le volet latéral qui s’affiche.

> [!TIP]
> Après avoir exécuté le processus de fusion, sélectionnez le statut du processus pour ouvrir le volet **Détails de la tâche**. Il donne un aperçu du temps de traitement, de la dernière date de traitement et de toutes les erreurs et avertissements associés à la tâche. Sélectionnez **Voir les détails** pour voir quelles entités ont participé au processus de correspondance, si la résolution du conflit est une réussite et si les mises à jour ont été publiées avec succès.  
> Il existe [six types de statuts](system.md#status-types) pour les tâches/processus. En outre, la plupart des processus [dépendent d’autres processus en aval](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Chemin d’accès permettant d’explorer les détails du processus à partir du lien de statut de la tâche.":::

## <a name="next-step"></a>Étape suivante

Pour plus d'informations sur vos clients, configurez les [activités](activities.md), l'[enrichissement](enrichment-hub.md) ou les [relations](relationships.md).

Si vous avez déjà configuré des activités, un enrichissement ou des segments, ils seront traités automatiquement pour utiliser les dernières données client.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
