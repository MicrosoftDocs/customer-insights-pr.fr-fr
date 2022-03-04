---
title: Limites de service dans Dynamics 365 Customer Insights
description: Comprenez les limites et les restrictions.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350404"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Limites de service dans les fonctionnalités Customer Insights

Cet article décrit les limites intégrées au service Customer Insights, qui sont conçues pour garantir la fiabilité et la stabilité du service. Toutes les demandes de modifications peuvent être effectuées via le [Forum d’idées](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Informations sur l’audience

| Area  | Limites  | Remarques |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segments, mesures et prédictions | 300  | Le nombre total de [segments](audience-insights/segments.md), de [mesures](audience-insights/measures.md) et de [prédictions](audience-insights/predictions.md) combinés ne peut pas dépasser 300.  |
| Relations | 20 niveaux de profondeur sur les relations dans les chemins d'entité. | Lors de la création de [segments](audience-insights/segments.md) ou de [mesures](audience-insights/measures.md) en utilisant l’interface du générateur, les chemins d’entité peuvent avoir jusqu’à 20 sauts de relation entre l’entité de départ et l’entité cible.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
