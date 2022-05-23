---
title: Schéma des entités Customer Insights dans Common Data Model
description: Utilisez des entités dans Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 33a0562854e97b9ac5218e060f965996305627fd
ms.sourcegitcommit: d45c00a5f6cb106714366af81e8070e7f53654b3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2022
ms.locfileid: "8757429"
---
# <a name="entity-schemas-in-common-data-model"></a>Schémas des entités dans Common Data Model



[Common Data Model](/common-data-model/) est une spécification déclarative, qui définit les entités standard qui représentent les concepts et les activités couramment utilisés dans les applications métier et de productivité. Ce modèle est également étendu aux données d’observation et d’analyse. Common Data Model fournit des entités métier bien définies, modulaires et extensibles, telles que les entités Compte, Division, Incident, Contact, Prospect, Opportunité et Produit, ainsi que des interactions avec les fournisseurs, les collaborateurs et les clients, telles que les activités et les contrats de niveau de service. Tout le monde peut s’appuyer sur des définitions Common Data Model et les étendre pour capturer des idées supplémentaires propres à l’entreprise.

Ce modèle de données partagé permet aux applications et aux intégrateurs de données de collaborer plus facilement en fournissant une définition unifiée des données. Common Data Model comprend un système complet de métadonnées avec des entités standard, des relations, des hiérarchies, des caractéristiques, etc. Il est issu des applications Dynamics 365 et est en open-source sur GitHub avec plus de 260 entités standard. Un vaste système de partenaires internes et externes contribue aux concepts propres au secteur du Common Data Model.

Plusieurs systèmes et plateformes mettent en œuvre le Common Data Model aujourd’hui, y compris les flux de données Power BI et Azure Data Services. Il est déjà pris en charge dans Microsoft Dataverse, Dynamics 365, Power Apps, Power BI et les services de données Azure à venir, accumulant directement de la valeur pour l’[Open Data Initiative](https://dynamics.microsoft.com/en-us/open-data-initiative/).

## <a name="customer-insights-entity-schemas"></a>Schémas d’entité Customer Insights

Pour établir une vue globale du client et créer des modèles Customer Insights disponibles dans Common Data Model pour l’extensibilité, nous avons publié les schémas d’entité suivants :

| Entité | Description |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Une activité réalisée par un utilisateur qui a une valeur d’observation pour l’entreprise. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Une personne ou une organisation qui a exercé ou a le potentiel d’exercer des activités professionnelles. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Définition des Indicateurs de performance clés partitionnés par aucune ou plusieurs dimensions (par exemple, Utilisateurs actifs mensuels, Dépenses totales par client, Coût d’acquisition moyen du client) |
|[Segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Définit un groupe de membres avec des caractéristiques communes. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Membres participant à un segment donné. |

Pour plus d’informations, consultez la documentation sur les [Schémas d’entité Customer Insights dans Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Afficher les entités à l’aide du navigateur d’entités de Common Data Model

Vous pouvez afficher les entités dans le [Navigateur d’entités de Common Data Model](https://microsoft.github.io/CDM/). Sélectionnez une entité dans la section Application Insights pour obtenir la liste des entités Customer Insights et leurs définitions.
> [!div class="mx-imgBorder"]
> ![Navigateur d’entité CDM affichant l’entité CustomerActivity.](media/CDM-entity-navigator.png "Navigateur d’entité CDM affichant l’entité CustomerActivity")


[!INCLUDE [footer-include](includes/footer-banner.md)]
