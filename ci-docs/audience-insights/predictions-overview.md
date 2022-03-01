---
title: Présentation des scénarios de prédiction pris en charge
description: Scénarios et options de prédiction couverts par l'application Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 57c61895d636273fc90a0ac5a942fd0c9abf583c687ae20621949554e581cdf8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036006"
---
# <a name="predictions-overview"></a>Présentation des prédictions

Dynamics 365 Customer Insights est fourni avec de nombreuses options qui exploitent l'IA et le Machine Learning pour prédire les données. 

## <a name="out-of-box-models"></a>Modèles prêts à l'emploi

Le moyen le plus simple de commencer à prédire les données est de recourir à des modèles prédéfinis, souvent appelés modèles prêts à l'emploi. Ils ne nécessitent que certaines données et certaines structures pour générer rapidement des informations. Actuellement, les modèles suivants sont disponibles : 
- [Valeur de durée de vie du client](predict-customer-lifetime-value.md) : prédit les revenus potentiels d'un client tout au long de l'interaction avec une entreprise. 
- [Recommandation de produits](predict-product-recommendation.md) : suggère des ensembles de recommandations de produits prédictives basées sur le comportement d'achat et les clients ayant des modèles d'achat similaires.
- [Attrition des abonnements](predict-subscription-churn.md) : prédit si un client risque de ne plus utiliser les produits ou services d'abonnement de votre société.
- [Attrition de transactions](predict-transactional-churn.md) : prédit si un client n'achètera plus vos produits ou services dans un certain délai d'exécution.

## <a name="azure-machine-learning-integration"></a>Intégration d’Azure Machine Learning

Si une organisation utilise déjà des scénarios de Machine Learning basés sur des expériences Azure Machine Learning, la fonctionnalité de modèles personnalisés dans Customer Insights permet de connecter les points. Créez des flux de travail qui vous aident à choisir les données pour lesquelles vous souhaitez générer des informations et à mettre en correspondance les résultats avec vos profils de client unifiés. Pour plus d’informations, voir [Modèles personnalisés Machine Learning](custom-models.md).

## <a name="ai-builder-prediction"></a>Prédiction AI Builder

Parfois, les jeux de données sont incomplets et certaines valeurs sont manquantes. Customer Insights peut aider à prédire les valeurs manquantes pour l'entité et les segments Client. Pour plus d’informations, consultez [Compléter vos données partielles avec des prédictions](predictions.md).
