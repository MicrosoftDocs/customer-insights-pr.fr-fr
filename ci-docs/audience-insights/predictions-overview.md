---
title: Présentation des scénarios de prédiction pris en charge
description: Scénarios et options de prédiction couverts par l'application Dynamics 365 Customer Insights.
ms.date: 09/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 63e22bf9a457ea43c65132643681cffb295ae7e5
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673959"
---
# <a name="predictions-overview"></a>Présentation des prédictions

Dynamics 365 Customer Insights est fourni avec de nombreuses options qui exploitent l'IA et le Machine Learning pour prédire les données. 

## <a name="out-of-box-models"></a>Modèles prêts à l'emploi

Le moyen le plus simple de commencer à prédire les données est de recourir à des modèles prédéfinis, souvent appelés modèles prêts à l'emploi. Ils ne nécessitent que certaines données et certaines structures pour générer rapidement des informations. Actuellement, les modèles suivants sont disponibles : 

# <a name="individual-consumers-b-to-c"></a>[Consommateurs individuels (B-to-C)](#tab/b2c)

- [Valeur de durée de vie du client](predict-customer-lifetime-value.md) : prédit les revenus potentiels d'un client tout au long de l'interaction avec une entreprise.
- [Recommandation de produits](predict-product-recommendation.md) : suggère des ensembles de recommandations de produits prédictives basées sur le comportement d'achat et les clients ayant des modèles d'achat similaires.
- [Attrition des abonnements](predict-subscription-churn.md) : prédit si un client risque de ne plus utiliser les produits ou services d'abonnement de votre société.
- [Attrition de transactions](predict-transactional-churn.md) : prédit si un client n'achètera plus vos produits ou services dans un certain délai d'exécution.

# <a name="business-accounts-b-to-b"></a>[Comptes d’entreprise (B-to-B)](#tab/b2b)

- [Attrition de transactions](predict-transactional-churn.md) : prédit si un client n'achètera plus vos produits ou services dans un certain délai d'exécution.

---


## <a name="azure-machine-learning-integration"></a>Intégration d’Azure Machine Learning

Si une organisation utilise déjà des scénarios de Machine Learning basés sur des expériences Azure Machine Learning, la fonctionnalité de modèles personnalisés dans Customer Insights permet de connecter les points. Créez des flux de travail qui vous aident à choisir les données pour lesquelles vous souhaitez générer des informations et à mettre en correspondance les résultats avec vos profils de client unifiés. Pour plus d’informations, voir [Modèles personnalisés Machine Learning](custom-models.md).

## <a name="ai-builder-prediction"></a>Prédiction AI Builder

Parfois, les jeux de données sont incomplets et certaines valeurs sont manquantes. Customer Insights peut aider à prédire les valeurs manquantes pour l'entité et les segments Client. Pour plus d’informations, consultez [Compléter vos données partielles avec des prédictions](predictions.md).
