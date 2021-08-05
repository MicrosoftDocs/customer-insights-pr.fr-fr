---
title: Limites du service
description: Comprenez les limites et les restrictions.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 81253332cbea3110c0b3804db3a4d03b514f92d4
ms.sourcegitcommit: 9a99e48e96dfb3d895db428f37c30ae55eea66b7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2021
ms.locfileid: "6604366"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Limites du service dans la fonctionnalité les informations sur l’audience de Dynamics 365 Customer Insights

Cet article décrit les limites intégrées au service Customer Insights, qui sont conçues pour garantir la fiabilité et la stabilité du service. Toutes les demandes de modifications peuvent être effectuées via le [Forum d’idées](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Aires  | Limites  | Remarques |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segments et mesures | 100 segments ou mesures. | Le nombre total de [segments](segments.md) et de [mesures](measures.md) actifs combinés ne peut pas dépasser 100.  |
| Relations | 20 niveaux de profondeur sur les relations dans les chemins d'entité. | Lors de la création de [segments](segments.md) ou de [mesures](measures.md) en utilisant l’interface du générateur, les chemins d’entité peuvent avoir jusqu’à 20 sauts de relation entre l’entité de départ et l’entité cible.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]