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
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095705"
---
# <a name="predictions-overview"></a><span data-ttu-id="0ca2c-103">Présentation des prédictions</span><span class="sxs-lookup"><span data-stu-id="0ca2c-103">Predictions overview</span></span>

<span data-ttu-id="0ca2c-104">Dynamics 365 Customer Insights est fourni avec de nombreuses options qui exploitent l'IA et le Machine Learning pour prédire les données.</span><span class="sxs-lookup"><span data-stu-id="0ca2c-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="0ca2c-105">Modèles prêts à l'emploi</span><span class="sxs-lookup"><span data-stu-id="0ca2c-105">Out-of-box models</span></span>

<span data-ttu-id="0ca2c-106">Le moyen le plus simple de commencer à prédire les données est de recourir à des modèles prédéfinis, souvent appelés modèles prêts à l'emploi.</span><span class="sxs-lookup"><span data-stu-id="0ca2c-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="0ca2c-107">Ils ne nécessitent que certaines données et certaines structures pour générer rapidement des informations.</span><span class="sxs-lookup"><span data-stu-id="0ca2c-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="0ca2c-108">Actuellement, les modèles suivants sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="0ca2c-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="0ca2c-109">[Valeur de durée de vie du client](predict-customer-lifetime-value.md) : prédit les revenus potentiels d'un client tout au long de l'interaction avec une entreprise.</span><span class="sxs-lookup"><span data-stu-id="0ca2c-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="0ca2c-110">[Recommandation de produits](predict-product-recommendation.md) : suggère des ensembles de recommandations de produits prédictives basées sur le comportement d'achat et les clients ayant des modèles d'achat similaires.</span><span class="sxs-lookup"><span data-stu-id="0ca2c-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="0ca2c-111">[Attrition des abonnements](predict-subscription-churn.md) : prédit si un client risque de ne plus utiliser les produits ou services d'abonnement de votre société.</span><span class="sxs-lookup"><span data-stu-id="0ca2c-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="0ca2c-112">[Attrition de transactions](predict-transactional-churn.md) : prédit si un client n'achètera plus vos produits ou services dans un certain délai d'exécution.</span><span class="sxs-lookup"><span data-stu-id="0ca2c-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="0ca2c-113">Intégration d’Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="0ca2c-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="0ca2c-114">Si une organisation utilise déjà des scénarios de Machine Learning basés sur des expériences Azure Machine Learning, la fonctionnalité de modèles personnalisés dans Customer Insights permet de connecter les points.</span><span class="sxs-lookup"><span data-stu-id="0ca2c-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="0ca2c-115">Créez des flux de travail qui vous aident à choisir les données pour lesquelles vous souhaitez générer des informations et à mettre en correspondance les résultats avec vos profils de client unifiés.</span><span class="sxs-lookup"><span data-stu-id="0ca2c-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="0ca2c-116">Pour plus d’informations, voir [Modèles personnalisés Machine Learning](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="0ca2c-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="0ca2c-117">Prédiction AI Builder</span><span class="sxs-lookup"><span data-stu-id="0ca2c-117">AI Builder prediction</span></span>

<span data-ttu-id="0ca2c-118">Parfois, les jeux de données sont incomplets et certaines valeurs sont manquantes.</span><span class="sxs-lookup"><span data-stu-id="0ca2c-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="0ca2c-119">Customer Insights peut aider à prédire les valeurs manquantes pour l'entité et les segments Client.</span><span class="sxs-lookup"><span data-stu-id="0ca2c-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="0ca2c-120">Pour plus d’informations, consultez [Compléter vos données partielles avec des prédictions](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="0ca2c-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
