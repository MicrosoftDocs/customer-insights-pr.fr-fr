---
title: Limites de service dans Customer Insights
description: Vous devez connaître les limites et les restrictions dans le service SaaS pour Customer Insights.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c3863b1a72fd92ddc87755699feda11371ec9214
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463216"
---
# <a name="service-limits-in-customer-insights"></a>Limites de service dans Customer Insights

 Customer Insights comporte des limites intégrées conçues pour garantir la fiabilité et la stabilité du service. Toutes les demandes de modifications peuvent être effectuées via le [Forum d’idées](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Area  | Limites  | Remarques |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segments, mesures et prédictions | 300  | Le nombre total de [segments](segments.md), de [mesures](measures.md) et de [prédictions](predictions-overview.md) combinés ne peut pas dépasser 300.  |
| Relations | 20 niveaux de profondeur sur les relations dans les chemins d'entité. | Lors de la création de [segments](segments.md) ou de [mesures](measures.md) en utilisant l’interface du générateur, les chemins d’entité peuvent avoir jusqu’à 20 sauts de relation entre l’entité de départ et l’entité cible.  |
|Ingestion des données| Les évaluations simultanées pour les sources de données Power Query sont limitées. | Customer Insights a les mêmes [limites d’actualisation comme les flux de données dans PowerBI.com](/power-query/power-query-online-limits#refresh-limits). |

## <a name="fair-scheduling-of-jobs"></a>Ordonnancement équitable des travaux

Customer Insights est un service SaaS qui utilise des ressources Azure partagées. Les clients ont tendance à avoir des charges de travail d'intensité variable et selon des horaires différents. Pour garantir un accès équitable aux ressources sous-jacentes, nous nous assurons que les processus système sont exécutés dans un ordre équitable. Des exemples de processus système sont les tâches liées à l'unification des données, aux mises à jour de segments ou au calcul de mesures. La planification équitable vous protège des files d'attente pour les ressources en cas de pic de tâches demandées. Dans le même temps, Customer Insights ne garantit pas que toutes les tâches que vous mettez en file d'attente sont traitées en parallèle.

[!INCLUDE [footer-include](includes/footer-banner.md)]
