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
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641759"
---
# <a name="service-limits-in-customer-insights"></a>Limites de service dans Customer Insights

Cet article décrit les limites intégrées au service Customer Insights, qui sont conçues pour garantir la fiabilité et la stabilité du service. Toutes les demandes de modifications peuvent être effectuées via le [Forum d’idées](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Area  | Limites  | Remarques |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segments, mesures et prédictions | 300  | Le nombre total de [segments](segments.md), de [mesures](measures.md) et de [prédictions](predictions.md) combinés ne peut pas dépasser 300.  |
| Relations | 20 niveaux de profondeur sur les relations dans les chemins d'entité. | Lors de la création de [segments](segments.md) ou de [mesures](measures.md) en utilisant l’interface du générateur, les chemins d’entité peuvent avoir jusqu’à 20 sauts de relation entre l’entité de départ et l’entité cible.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
