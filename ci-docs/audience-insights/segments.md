---
title: Segments dans les informations sur l’audience
description: Présentation des segments, de leur création et de leur gestion.
ms.date: 03/30/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 68e71df3853470af47228c7365f25db3a71d15b0
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529536"
---
# <a name="segments-overview"></a>Vue d’ensemble des segments

Les segments vous permettent de regrouper vos clients en fonction des attributs démographiques, transactionnels ou comportementaux. Vous pouvez utiliser les segments pour cibler les campagnes promotionnelles, les activités commerciales et les actions de support client pour atteindre vos objectifs commerciaux.

Les profils client qui correspondent aux filtres d’une définition de segment sont appelés *membres* d’un segment. Certaines [limites du service](/dynamics365/customer-insights/service-limits) s’appliquent.

## <a name="create-a-new-segment"></a>Créer un segment

Il existe plusieurs façons de créer un segment : 

# <a name="individual-consumers-b-to-c"></a>[Consommateurs individuels (B-to-C)](#tab/b2c)

- Segment complexe avec générateur de segment : [Construire le nôtre](segment-builder.md#create-a-new-segment) 
- Segments simples avec un seul opérateur : [segment rapide](segment-builder.md#quick-segments) 
- Moyen optimisé par l’IA pour trouver des clients similaires : [clients similaires](find-similar-customer-segments.md) 
- Suggestions basées sur l’IA à partir de mesures ou d’attributs : [segments suggérés pour améliorer les mesures](suggested-segments.md) 
- Suggestions basées sur les activités : [segments suggérés en fonction de l’activité des clients](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Comptes d’entreprise (B-to-B)](#tab/b2b)

- Segment complexe avec générateur de segment : [Construire le nôtre](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Gérer les segments existants

Accédez à la page **Segments** pour afficher tous vos segments enregistrés et les gérer.

Chaque segment est représenté par une ligne qui contient des informations supplémentaires sur le segment.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segment sélectionné avec la liste déroulante d’options et les options disponibles." lightbox="media/segments-selected-segment.png":::

Les actions suivantes sont disponibles lorsque vous sélectionnez un segment :

- **Afficher** les détails du segment, y compris un aperçu de la tendance du nombre de membres du segment.
- **Télécharger** la liste des membres en tant que fichier .CSV.
- **Modifier** le segment pour modifier ses propriétés.
- **Créez un doublon** d’un segment. Vous pouvez choisir de modifier ses propriétés immédiatement ou simplement d’enregistrer le doublon.
- **Actualiser** le segment pour inclure les dernières données.
- **Activer** ou **Désactiver** le segment. Pour les segments inactifs, la définition de segment existe, mais elle ne contient pas encore de clients. Un segment actif recherche les clients qui correspondent à la définition du segment. Si une [actualisation programmée](system.md#schedule-tab) est configurée, les segments inactifs ont leur **Statut** répertorié comme **Ignoré**, indiquant qu’une actualisation n’a même pas été tentée. Lorsqu’un segment inactif est activé, il s’actualise et sera inclus dans les actualisations programmées.
  Vous pouvez également utiliser la fonctionnalité **Planifier plus tard** dans la liste déroulante **Activer/Désactiver** pour spécifier une date et une heure futures d’activation et de désactivation d’un segment particulier.
- **[Rechercher des clients similaires](find-similar-customer-segments.md)** dans le segment.
- **Renommer** le segment.
- **Étiquette** pour [gérer les étiquettes](work-with-tags-columns.md#manage-tags) du segment.
- **Télécharger** la liste des membres en tant que fichier .CSV.
- **Gérer les exportations** pour voir le segment lié aux exportations et les gérer. [En savoir plus sur les exportations](export-destinations.md)
- **Supprimer** le segment.
- **Colonnes** pour [personnaliser les colonnes](work-with-tags-columns.md#customize-columns) qui s’affichent.
- **Filtrer** pour [filtrer selon les étiquettes](work-with-tags-columns.md#filter-on-tags).
- **Rechercher un nom** pour effectuer une recherche par nom de segment.

## <a name="refresh-segments"></a>Actualiser des segments

Vous pouvez actualiser tous les segments à la fois en sélectionnant **Actualiser tout** sur la page **Segments** ou vous pouvez actualiser un ou plusieurs segments lorsque vous les sélectionnez et choisissez **Actualiser** dans les options. Vous pouvez également configurer une actualisation périodique en cliquant sur **Administrateur** > **Système** > **Planifier**. Lorsqu’une actualisation périodique est configurée, les règles suivantes s’appliquent :
- Tous les segments avec le type **Dynamique** ou **Expansion** seront actualisés automatiquement à la fréquence définie. Lorsque l’actualisation est terminée, le **Statut** indique si des problèmes se sont produits pendant l’actualisation du segment. L’option **Dernière actualisation** affiche un horodatage de la dernière actualisation réussie. Si une erreur s’est produite, sélectionnez l’erreur pour voir les détails.
- Les segments avec le type **Statique** *ne seront pas* actualisés automatiquement. L’option **Dernière actualisation** affiche un horodatage de la dernière exécution ou actualisation manuelle des segments statiques.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="export-segments"></a>Exporter les segments

Vous pouvez exporter un segment à partir de la page des segments ou de la [page des exportations](export-destinations.md). 

1. Accédez à la page **Segments**.

1. Sélectionnez **Afficher plus [...]** pour le segment que vous souhaitez exporter.

1. Sélectionnez **Gérer les exportations** dans la liste déroulante d’actions.

1. La page **Exportations du segment (aperçu)** s'ouvre. Vous pouvez voir toutes les exportations configurées regroupées selon qu’elles contiennent ou non le segment actuel.

   1. Pour ajouter le segment sélectionné à une exportation, **Éditez** l’exportation respective pour sélectionner le segment correspondant, puis enregistrez. Dans les environnements pour clients individuels, vous pouvez à la place sélectionner l’exportation dans la liste et sélectionner **Ajouter un segment** pour arriver au même résultat.

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
