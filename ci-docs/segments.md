---
title: Vue d’ensemble des segments
description: Présentation des segments, de leur création et de leur gestion.
ms.date: 08/12/2022
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
ms.openlocfilehash: d4de3a6af6bc7d54305a23e3fbd3cc95d464d352
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304792"
---
# <a name="segments-overview"></a>Vue d’ensemble des segments

Les segments vous permettent de regrouper vos clients en fonction des attributs démographiques, transactionnels ou comportementaux. Vous pouvez utiliser les segments pour cibler les campagnes promotionnelles, les activités commerciales et les actions de support client pour atteindre vos objectifs commerciaux.

Les profils client ou contact qui correspondent aux filtres d’une définition de segment sont appelés *membres* d’un segment. Certaines [limites du service](/dynamics365/customer-insights/service-limits) s’appliquent.

## <a name="create-a-segment"></a>Créer un segment

Choisissez comment créer un segment basé sur votre audience cible.

# <a name="individual-consumers-b-to-c"></a>[Consommateurs individuels (B-to-C)](#tab/b2c)

- Segments complexes avec générateur de segment : [créez les vôtres](segment-builder.md)
- Segments simples avec un seul opérateur : [segment rapide](segment-quick.md)
- Moyen optimisé par l’IA pour trouver des clients similaires : [clients similaires](find-similar-customer-segments.md)
- Suggestions basées sur l’IA à partir de mesures ou d’attributs : [segments suggérés en fonction des mesures](suggested-segments.md)
- Suggestions basées sur les activités : [segments suggérés en fonction de l’activité des clients](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Comptes d’entreprise (B-to-B)](#tab/b2b)

Segment de comptes ou segment de contacts (aperçu) avec le générateur de segments : [Créer le vôtre](segment-builder.md)

> [!NOTE]
> La plupart des destinations d’exportation exigent des informations de contact à des fins de marketing. Par conséquent, créez des segments de contacts à utiliser pour ces exportations.

---

## <a name="manage-existing-segments"></a>Gérer les segments existants

Accédez à la page **Segments** pour afficher les segments que vous avez créés, leur statut et leur état, ainsi que la dernière fois que les données ont été actualisées. Vous pouvez trier la liste des segments par colonne ou utiliser la zone de recherche pour trouver le segment que vous souhaitez gérer.

> [!TIP]
> Dans les environnements B to B, la colonne **Type audience** identifie si un segment est basé sur des comptes ou des contacts.

Sélectionnez un segment pour afficher les actions disponibles.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segment sélectionné avec la liste déroulante d’options et les options disponibles." lightbox="media/segments-selected-segment.png":::

- [**Afficher**](#view-segment-details) les détails du segment, y compris un aperçu de la tendance du nombre de membres du segment.
- **Télécharger** la liste des membres en tant que fichier .CSV.
- **Modifier** le segment pour modifier ses propriétés.
- **Créez un doublon** d’un segment. Vous pouvez choisir de modifier immédiatement ses propriétés ou d’enregistrer le doublon.
- [**Actualiser**](#refresh-segments) le segment pour inclure les dernières données.
- **Activer** ou **Désactiver** le segment. Les segments inactifs ne seront pas actualisés pendant une [actualisation planifiée](schedule-refresh.md) et auront le **statut** **Ignoré**, indiquant qu’aucune actualisation n’a été tentée. Les segments actifs sont actualisés en fonction de leur type : statique ou dynamique.
- **Rendre statique** ou **Rendre dynamique** le type de segment. Les segments statiques ne doivent pas être actualisés manuellement. Les segments dynamiques seront actualisés automatiquement lors des actualisations du système
- [**Rechercher des clients similaires**](find-similar-customer-segments.md) dans le segment.
- **Renommer** le segment.
- **Étiquette** pour [gérer les étiquettes](work-with-tags-columns.md#manage-tags) du segment.
- [**Gérer les exportations**](#export-segments) pour voir le segment lié aux exportations et les gérer. [En savoir plus sur les exportations](export-destinations.md)
- **Supprimer** le segment.
- **Colonnes** pour [personnaliser les colonnes](work-with-tags-columns.md#customize-columns) qui s’affichent.
- **Filtrer** pour [filtrer selon les étiquettes](work-with-tags-columns.md#filter-on-tags).
- **Rechercher un nom** pour effectuer une recherche par nom de segment.

## <a name="view-segment-details"></a>Afficher les détails du segment

Sur la page **Segments**, sélectionnez un segment pour afficher l’historique de traitement et les membres du segment.

La partie supérieure de la page comprend un graphique de tendance qui indique l’évolution du nombre des membres. Passez la souris sur les points de données pour voir le nombre de membres à une date spécifique. Modifier le délai d’exécution de la visualisation.

:::image type="content" source="media/segment-time-range.png" alt-text="Intervalle de temps du segment.":::

La partie inférieure contient la liste des membres du segment.

> [!NOTE]
> Les champs qui apparaissent dans cette liste sont basés sur les attributs des entités de votre segment.
>
> La liste est un aperçu des membres du segment correspondant et affiche les 100 premiers enregistrements de votre segment afin que vous puissiez rapidement l’évaluer et revoir ses définitions si nécessaire. Pour voir tous les enregistrements correspondants, sélectionnez **Afficher plus** qui ouvre la page [**Entités**](entities.md) ou [exportez le segment](export-destinations.md).

## <a name="refresh-segments"></a>Actualiser des segments

Les segments peuvent être actualisés selon un calendrier automatique ou actualisées manuellement à la demande. Pour actualiser manuellement un ou plusieurs segments, sélectionnez-les et choisissez **Actualiser**.

Pour [planifier une actualisation automatique](schedule-refresh.md), accédez à **Administrateur** > **Système** > **Planification**. Les règles suivantes s’appliquent :

- Tous les segments avec le type **Dynamique** ou **Expansion** seront actualisés automatiquement à la fréquence définie. Une fois l’actualisation terminée, le **Statut** indique si des problèmes se sont produits pendant l’actualisation du segment. L’option **Dernière actualisation** affiche un horodatage de la dernière actualisation réussie. Si une erreur s’est produite, sélectionnez l’erreur pour voir les détails.
- Les segments avec le type **Statique** *ne seront pas* actualisés automatiquement. L’option **Dernière actualisation** affiche un horodatage de la dernière exécution ou actualisation manuelle du segment statique.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Exporter les segments

Exportez des segments vers d’autres applications pour utiliser davantage les données. Exportez un segment à partir de la page des segments ou de la [page des exportations](export-destinations.md).

1. Accédez à la page **Segments** et sélectionnez le segment à exporter.

1. Sélectionnez **Gérer les exportations**. La page **Exportations du segment (aperçu)** s'ouvre. Affichez toutes les exportations configurées regroupées selon qu’elles contiennent ou non le segment actuel.

   1. Pour ajouter le segment sélectionné à une exportation, **Éditez** l’exportation respective pour sélectionner le segment correspondant, puis enregistrez. Dans les environnements pour clients individuels, sélectionnez l’exportation dans la liste et sélectionner **Ajouter un segment** pour arriver au même résultat.

   1. Pour créer une nouvelle exportation avec le segment sélectionné, sélectionnez **Ajouter une exportation**. Pour plus d'informations sur la création d'exportations, consultez [Configurer une nouvelle exportation](export-destinations.md#set-up-a-new-export).

1. Sélectionnez **Précédent** pour revenir à la page principale des segments.

## <a name="track-usage-of-a-segment"></a>Suivre l’utilisation d’un segment

Si vous utilisez des segments dans des applications, qui sont basées sur la même organisation Microsoft Dataverse connectée à Customer Insights, vous pouvez suivre l’utilisation d’un segment. Pour les [segments Customer Insights utilisés dans les parcours du client de Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), le système vous informe de l’utilisation de ce segment.

Lors de la modification d’un segment utilisé dans l’environnement Customer Insights ou dans un parcours du client dans Marketing, une bannière dans le [générateur de segments](segment-builder.md) vous informe des dépendances. Inspectez les détails de la dépendance directement à partir de la bannière ou en sélectionnant **Utilisation** dans le générateur de segments.

Le volet **Utilisation du segment** affiche les détails de l’utilisation de ce segment dans les applications Dataverse. Pour les segments utilisés dans les parcours du client, vous trouverez un lien pour inspecter le parcours dans Marketing où ce segment est utilisé. Si vous disposez des autorisations nécessaires pour accéder à l’application Marketing, affichez des détails supplémentaires ici.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Volet latéral avec les détails de l’utilisation du segment dans le générateur de segments.":::

Le système vous informe de l’utilisation d’un segment suivi lorsque vous essayez de le supprimer. Si le segment que vous êtes sur le point de supprimer est utilisé dans un parcours du client dans Marketing, ce parcours s’arrêtera pour tous les utilisateurs du segment. Si le parcours fait partie d’une campagne marketing, la suppression affectera cette campagne proprement dite. Cependant, vous pouvez quand même supprimer le segment malgré les avertissements.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Boîte de dialogue pour confirmer la suppression du segment lorsqu’il est utilisé dans une application Dataverse.":::

### <a name="supported-apps"></a>Applications prises en charge

L’utilisation est actuellement suivie dans les applications Dataverse suivantes :

- [Parcours du client dans Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
