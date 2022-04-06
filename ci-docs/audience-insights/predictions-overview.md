---
title: Présentation des scénarios de prédiction pris en charge
description: Scénarios et options de prédiction couverts par l’application Dynamics 365 Customer Insights.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 11b0efeecf8bea893272e67d29b1c6622771110c
ms.sourcegitcommit: a5e4503cf9ce0cea562bab9389748d8ca1451f9d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2022
ms.locfileid: "8487496"
---
# <a name="predictions-overview"></a>Présentation des prédictions

Dynamics 365 Customer Insights est fourni avec de nombreuses options qui exploitent l’IA et le Machine Learning pour prédire les données. 

## <a name="out-of-box-models"></a>Modèles prêts à l’emploi

Le moyen le plus simple de commencer à prédire les données est de recourir à des modèles prédéfinis, souvent appelés modèles prêts à l’emploi. Ils ne nécessitent que certaines données et certaines structures pour générer rapidement des informations. Actuellement, les modèles suivants sont disponibles : 

# <a name="individual-consumers-b-to-c"></a>[Consommateurs individuels (B-to-C)](#tab/b2c)

- [Valeur de durée de vie du client](predict-customer-lifetime-value.md) : prédit les revenus potentiels d’un client tout au long de l’interaction avec une entreprise.
- [Recommandation de produits](predict-product-recommendation.md) : suggère des ensembles de recommandations de produits prédictives basées sur le comportement d’achat et les clients ayant des modèles d’achat similaires.
- [Attrition des abonnements](predict-subscription-churn.md) : prédit si un client risque de ne plus utiliser les produits ou services d’abonnement de votre société.
- [Attrition de transactions](predict-transactional-churn.md) : prédit si un client n’achètera plus vos produits ou services dans un certain délai d’exécution.
- [Analyse des sentiments](sentiment-analysis.md) : analysez le sentiment des commentaires de vos clients et identifiez les aspects commerciaux fréquemment mentionnés.

# <a name="business-accounts-b-to-b"></a>[Comptes d’entreprise (B-to-B)](#tab/b2b)

- [Attrition de transactions](predict-transactional-churn.md) : prédit si un client n’achètera plus vos produits ou services dans un certain délai d’exécution.

---

> [!TIP]
> Nous vous recommandons d’actualiser régulièrement les modèles prédéfinis avec les données mises à jour pour vous assurer qu’ils informent avec précision votre cas d’utilisation métier. Les données sont actualisées de manière ad hoc lorsque le système ingère des sources de données nouvelles ou mises à jour. Cependant, les modèles ne seront restaurés que dans ce cas et continueront à utiliser les données de formation existantes.
> 
> Vous pouvez configurer un **Calendrier de mise à jour** en définissant le calendrier de réentraînement du modèle dans l’expérience de configuration. Le modèle sera réentraîné et restauré selon ce calendrier, que vous pouvez modifier à tout moment.


## <a name="azure-machine-learning-integration"></a>Intégration d’Azure Machine Learning

Si une organisation utilise déjà des scénarios de Machine Learning basés sur des expériences Azure Machine Learning, la fonctionnalité de modèles personnalisés dans Customer Insights permet de connecter les points. Créez des flux de travail qui vous aident à choisir les données pour lesquelles vous souhaitez générer des informations et à mettre en correspondance les résultats avec vos profils de client unifiés. Pour plus d’informations, voir [Modèles personnalisés Machine Learning](custom-models.md).

## <a name="ai-builder-prediction"></a>Prédiction AI Builder

Parfois, les jeux de données sont incomplets et certaines valeurs sont manquantes. Customer Insights peut aider à prédire les valeurs manquantes pour l’entité et les segments Client. Pour plus d’informations, consultez [Compléter vos données partielles avec des prédictions](predictions.md).
