---
title: Segments dans les informations sur l’audience
description: Présentation des segments, de leur création et de leur gestion.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6e2080b4ad19f6f57f60da591345e80ce9083e8a
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554064"
---
# <a name="segments-overview"></a>Vue d’ensemble des segments

Les segments vous permettent de regrouper vos clients en fonction des attributs démographiques, transactionnels ou comportementaux. Vous pouvez utiliser les segments pour cibler les campagnes promotionnelles, les activités commerciales et les actions de support client pour atteindre vos objectifs commerciaux.

Les profils client qui correspondent aux filtres d’une définition de segment sont appelés *membres* d’un segment. Certaines [limites du service](service-limits.md) s’appliquent.

## <a name="create-a-new-segment"></a>Créer un segment

Il existe plusieurs façons de créer un segment : 

- Segment complexe avec générateur de segments : [segment vide](segment-builder.md#create-a-new-segment)
- Segments simples avec un seul opérateur : [segment rapide](segment-builder.md#quick-segments)
- Moyen optimisé par l’IA pour trouver des clients similaires : [clients similaires](find-similar-customer-segments.md)
- Suggestions basées sur l’IA à partir de mesures ou d’attributs : [segments suggérés pour améliorer les mesures](suggested-segments.md)
- Suggestions basées sur les activités : [segments suggérés en fonction de l’activité des clients](suggested-segments-activity.md)

## <a name="manage-existing-segments"></a>Gérer les segments existants

Accédez à la page **Segments** pour afficher tous vos segments enregistrés et les gérer.

Chaque segment est représenté par une ligne qui contient des informations supplémentaires sur le segment.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segment sélectionné avec la liste déroulante d’options et les options disponibles.":::

L’action suivante est disponible lorsque vous sélectionnez un segment :

- **Afficher** les détails du segment, y compris un aperçu de la tendance du nombre de membres du segment.
- **Modifier** le segment pour modifier ses propriétés.
- **Créez un doublon** d’un segment. Vous pouvez choisir de modifier ses propriétés immédiatement ou simplement d’enregistrer le doublon.
- **Actualiser** le segment pour inclure les dernières données.
- **Activer** ou **Désactiver** le segment. Les segments ont deux états possibles : actif ou inactif. Ces états sont utiles lors de l’édition d’un segment. Pour les segments inactifs, la définition de segment existe, mais elle ne contient pas encore de clients. Lorsque vous activez un segment, son état passe de « inactif » à « actif » et il commence à rechercher des clients qui correspondent à la définition du segment. Si une [actualisation programmée](system.md#schedule-tab) est configurée, les segments inactifs ont leur **Statut** répertorié comme **Ignoré**, indiquant qu’une actualisation n’a même pas été tentée. Lorsqu’un segment inactif est activé, il s’actualise et sera inclus dans les actualisations programmées.
  Vous pouvez également utiliser la fonctionnalité **Planifier plus tard** dans la liste déroulante **Activer/Désactiver** pour spécifier une date et une heure futures d’activation et de désactivation d’un segment particulier.
- **Renommer** le segment.
- **Télécharger** la liste des membres en tant que fichier .CSV.
- **Gérer les exportations** pour voir le segment lié aux exportations et les gérer. [En savoir plus sur les exportations](export-destinations.md)
- **Supprimer** le segment.

## <a name="refresh-segments"></a>Actualiser des segments

Vous pouvez actualiser tous les segments à la fois en sélectionnant **Actualiser tout** sur la page **Segments** ou vous pouvez actualiser un ou plusieurs segments lorsque vous les sélectionnez et choisissez **Actualiser** dans les options. Vous pouvez également configurer une actualisation périodique en cliquant sur **Administrateur** > **Système** > **Planifier**.

> [!TIP]
> Il existe [six types de statuts](system.md#status-types) pour les tâches/processus. En outre, la plupart des processus [dépendent d’autres processus en aval](system.md#refresh-policies). Vous pouvez sélectionner le statut d’un processus pour afficher des détails sur la progression de toute la tâche. Après avoir sélectionné **Voir les détails** pour l’une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.

## <a name="export-segments"></a>Exporter les segments

Vous pouvez exporter un segment à partir de la page des segments ou de la [page des exportations](export-destinations.md). 

1. Accédez à la page **Segments**.

1. Sélectionnez **Afficher plus [...]** pour le segment que vous souhaitez exporter.

1. Sélectionnez **Gérer les exportations** dans la liste déroulante d’actions.

1. La page **Exportations du segment (aperçu)** s'ouvre. Vous pouvez voir toutes les exportations configurées regroupées par exportations qui contiennent le segment actuel ou qui ne le contiennent pas.

   1. Pour ajouter le segment sélectionné à une exportation, sélectionnez l'exportation dans la liste et sélectionnez **Ajouter un segment**.

   1. Pour créer une nouvelle exportation avec le segment sélectionné, sélectionnez **Ajouter une exportation**. Pour plus d'informations sur la création d'exportations, consultez [Configurer une nouvelle exportation](export-destinations.md#set-up-a-new-export).

1. Sélectionnez **Précédent** pour revenir à la page principale des segments.

## <a name="view-processing-history-and-segment-members"></a>Afficher l’historique de traitement et les membres du segment

Vous pouvez voir les données consolidées d’un segment en examinant ses détails.

Dans la page **Segments**, sélectionnez le segment à vérifier.

La partie supérieure de la page comprend un graphique de tendance qui indique l’évolution du nombre des membres. Passez la souris sur les points de données pour voir le nombre de membres à une date spécifique.

Vous pouvez mettre à jour le délai d’exécution de la visualisation.

> [!div class="mx-imgBorder"]
> ![Intervalle de temps du segment.](media/segment-time-range.png "Intervalle de temps du segment")

La partie inférieure contient la liste des membres du segment.

> [!NOTE]
> Les champs qui apparaissent dans cette liste sont basés sur les attributs des entités de votre segment.
>
>La liste est un aperçu des membres du segment correspondant et affiche les 100 premiers enregistrements de votre segment afin que vous puissiez rapidement l’évaluer et revoir ses définitions si nécessaire. Pour voir tous les enregistrements correspondants, vous devez [exporter le segment](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
