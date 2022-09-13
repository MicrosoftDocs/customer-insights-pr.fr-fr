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
ms.openlocfilehash: 7f38b7d9985368fc38107f1f360f0603a7fcc8e6
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411737"
---
# <a name="service-limits-in-customer-insights"></a>Limites de service dans Customer Insights

 Customer Insights comporte des limites intégrées conçues pour garantir la fiabilité et la stabilité du service. Toutes les demandes de modifications peuvent être effectuées via le [Forum d’idées](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Area  | Limites  | Remarques |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segments, mesures et prédictions | 300  | Le nombre total de [segments](segments.md), de [mesures](measures.md) et de [prédictions](predictions-overview.md) combinés ne peut pas dépasser 300.  |
| Relations | 20 niveaux de profondeur sur les relations dans les chemins d'entité. | Lors de la création de [segments](segments.md) ou de [mesures](measures.md) en utilisant l’interface du générateur, les chemins d’entité peuvent avoir jusqu’à 20 sauts de relation entre l’entité de départ et l’entité cible.  |

## <a name="fair-scheduling-of-jobs"></a>Ordonnancement équitable des travaux

Customer Insights est un service SaaS qui utilise des ressources Azure partagées. Les clients ont tendance à avoir des charges de travail d'intensité variable et selon des horaires différents. Pour garantir un accès équitable aux ressources sous-jacentes, nous nous assurons que les processus système sont exécutés dans un ordre équitable. Des exemples de processus système sont les tâches liées à l'unification des données, aux mises à jour de segments ou au calcul de mesures. La planification équitable vous protège des files d'attente pour les ressources en cas de pic de tâches demandées. Dans le même temps, Customer Insights ne garantit pas que toutes les tâches que vous mettez en file d'attente sont traitées en parallèle.

[!INCLUDE [footer-include](includes/footer-banner.md)]
