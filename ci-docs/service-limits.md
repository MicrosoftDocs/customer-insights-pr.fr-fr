---
title: Limites de service dans Dynamics 365 Customer Insights
description: Comprenez les limites et les restrictions.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483663"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Limites de service dans les fonctionnalités Customer Insights

Cet article décrit les limites intégrées au service Customer Insights, qui sont conçues pour garantir la fiabilité et la stabilité du service. Toutes les demandes de modifications peuvent être effectuées via le [Forum d’idées](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Informations sur l’audience

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Limites du service dans la fonctionnalité les informations sur l’audience de Dynamics 365 Customer Insights

| Aires  | Limites  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segments et mesures | 100 segments ou mesures. | Le nombre total de [segments](audience-insights/segments.md) et de [mesures](audience-insights/measures.md) actifs combinés ne peut pas dépasser 100.  |
| Relations | 20 niveaux de profondeur sur les relations dans les chemins d'entité. | Lors de la création de [segments](audience-insights/segments.md) ou de [mesures](audience-insights/measures.md) en utilisant l’interface du générateur, les chemins d’entité peuvent avoir jusqu’à 20 sauts de relation entre l’entité de départ et l’entité cible.  |


## <a name="engagement-insights"></a>Informations sur l’engagement

### <a name="workspace-and-event-quotas"></a>Quotas d’espaces de travail et d’événements

Informations sur l'engagement est une application hautement évolutive qui peut prendre en charge des millions d'événements par seconde. Lors de la version préliminaire publique, les événements ont un seuil de volume. Le nombre d'espaces de travail dans une organisation est également limité.

### <a name="engagement-insights-limits"></a>Limitations relatives à la fonction Informations sur l'engagement

- Volume d'événements maximum par espace de travail = 100 événements par seconde

- Nombre maximum d'espaces de travail par organisation = 100

Lorsque les événements dépassent le seuil, cela peut entraîner une perte de données dans les rapports basés sur ces événements. Vous pouvez [contacter le support](https://go.microsoft.com/fwlink/?linkid=2145734) pour demander une augmentation de volume avant de dépasser les limites. Nous verrons avec vous comment déterminer votre besoin d'augmentation de volume et prendre en charge votre demande.


[!INCLUDE[footer-include](includes/footer-banner.md)]