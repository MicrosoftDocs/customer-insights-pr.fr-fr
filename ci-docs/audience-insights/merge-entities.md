---
title: Fusionner des entités pour l’unification des données
description: Fusionnez des données pour créer des profils clients unifiés.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597830"
---
# <a name="merge-entities"></a>Fusionner des entités

La fusion est la dernière phase du processus d’unification des données. Son objectif consiste à rapprocher les données conflictuelles. Des exemples de données en conflit sont le nom d’un client qui réside dans deux de vos jeux de données, avec une petite différence (« Martin Lucas » au lieu de « Martin »), ou un format de numéro de téléphone légèrement différent (06-78-03-09-1X et 067803091X). Fusionner ces points de données en conflit s’effectue d’une manière attribut par attribut.

Après avoir terminé la [phase de mise en correspondance](match-entities.md), vous pouvez entamer la phase de fusion en sélectionnant la vignette **Fusionner** sur la page **Unifier**.

## <a name="review-system-recommendations"></a>Examiner les recommandations système

Sur la page **Fusionner**, vous choisissez et excluez des attributs à fusionner au sein de votre entité de profil client unifié (le résultat final du processus de configuration). Certains attributs sont automatiquement fusionnés par le système.

### <a name="view-merged-attributes"></a>Afficher les attributs fusionnés

Pour afficher les attributs inclus dans un de vos attributs fusionnés automatiquement, sélectionnez cet attribut fusionnée. Les deux attributs qui composent cet attribut fusionné s’affichent dans deux nouvelles lignes en dessous de l’attribut fusionné.

> [!div class="mx-imgBorder"]
> ![Sélectionner l’attribut fusionné](media/configure-data-merge-profile-attributes.png "Sélectionner l’attribut fusionné")

### <a name="separate-merged-attributes"></a>Séparer les attributs fusionnés

Pour séparer ou annuler la fusion de l’un des attributs fusionnés automatiquement, recherchez l’attribut dans la table **Attributs de profil**.

1. Activez le bouton des points de suspension (...).
  
2. Dans la liste déroulante, sélectionnez **Séparer les champs**.

### <a name="remove-merged-attributes"></a>Supprimer les attributs fusionnés

Pour exclure un attribut de l’entité de profil client final, recherchez-le dans la table **Attributs du profil**.

1. Activez le bouton des points de suspension (...).
  
2. Dans la liste déroulante, sélectionnez **Ne pas fusionner**.

   L’attribut bascule dans la section **Supprimé de l’enregistrement de client**.

## <a name="manually-add-a-merged-attribute"></a>Ajouter manuellement un attribut fusionné

Pour ajouter un attribut fusionné, accédez à la page **Fusionner**.

1. Sélectionnez **Ajouter un attribut fusionné**.

2. Indiquez un **Nom** pour l’identifier sur la page **Fusionner** plus tard.

3. Éventuellement, fournissez un **Nom d’affichage** à apparaître dans l’entité Profil client unifié.

4. Configurez **Sélectionner les attributs dupliqués** pour sélectionner les attributs que vous souhaitez fusionner à partir des entités mises en correspondance. Vous pouvez également rechercher des attributs.

5. Définissez l’option **Classer par importance** pour donner la priorité à un attribut par rapport aux autres. Par exemple, si l’entité *WebAccountCSV* comprend les données les plus précises sur l’attribut *Noms complets*, nous classerons par priorité cette entité *ContactCSV* en sélectionnant *WebAccountCSV*. Par conséquent, *WebAccountCSV* devient la priorité numéro un, tandis que *ContactCSV* bascule en priorité numéro deux lors de l’extraction des valeurs pour l’attribut *Nom complet*.

## <a name="run-your-merge"></a>Exécuter la fusion

Que vous fusionniez manuellement les attributs ou laissiez le système le faire pour vous, à ce stade vous pouvez toujours exécuter votre fusion. Sélectionnez **Exécuter** sur la page **Fusionner** pour démarrer le processus.

> [!div class="mx-imgBorder"]
> ![Fusion des données - Enregistrer et exécuter](media/configure-data-merge-save-run.png "Fusion des données - Enregistrer et exécuter")

Pour apporter des modifications supplémentaires et réexécuter l’étape, vous pouvez annuler une fusion en cours. Sélectionnez **Actualisation en cours...** et sélectionnez **Annuler la tâche** dans le volet latéral qui s’affiche.

Une fois le texte **Actualisation en cours...** modifié en **Opération réussie**, la fusion est terminée et les contradictions dans vos données ont été résolues selon les stratégies que vous avez définies. Les attributs fusionnés et non fusionnés sont inclus dans l’entité de profil unifié, contrairement aux attributs exclus.

Si ce n’était pas la première fois que vous exécutiez une fusion avec succès, tous les processus en aval, y compris l’enrichissement, la segmentation et les mesures, seront réexécutés automatiquement. Une fois tous les processus en aval réexécutés, les profils client reflètent les modifications que vous avez apportées.

> [!TIP]
> Il existe [six types de statuts](system.md#status-types) pour les tâches/processus. En outre, la plupart des processus [dépendent d’autres processus en aval](system.md#refresh-policies). Vous pouvez sélectionner le statut d’un processus pour afficher des détails sur la progression de toute la tâche. Après avoir sélectionné **Voir les détails** pour l’une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.

## <a name="next-step"></a>Étape suivante

Pour plus d’informations sur vos clients, configurez les [activités](activities.md), l’[enrichissement](enrichment-microsoft-graph.md) ou les [relations](relationships.md).

Si vous avez déjà configuré des activités, un enrichissement ou des relations, ou si vous avez défini des segments, ils seront traités automatiquement pour utiliser les dernières données client.




[!INCLUDE[footer-include](../includes/footer-banner.md)]