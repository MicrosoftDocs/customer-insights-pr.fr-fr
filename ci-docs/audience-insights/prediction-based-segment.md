---
title: Segments basés sur la sortie de prédiction
description: Créez des segments basés sur l’entité de sortie d’un modèle de prédiction.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741426"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="b53d7-103">Créer un segment basé sur un modèle de prédiction (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="b53d7-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="b53d7-104">Les résultats des prédictions ne s’appliquent parfois qu’à un sous-ensemble de vos clients.</span><span class="sxs-lookup"><span data-stu-id="b53d7-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="b53d7-105">Augmentez la personnalisation des recommandations en créant des segments à partir des résultats des modèles de prédiction.</span><span class="sxs-lookup"><span data-stu-id="b53d7-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="b53d7-106">Par exemple, vous souhaitez peut-être donner des recommandations spécifiques aux clients qui préfèrent un certain type de service.</span><span class="sxs-lookup"><span data-stu-id="b53d7-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="b53d7-107">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="b53d7-107">Prerequisites</span></span>

- <span data-ttu-id="b53d7-108">Au minimum [Autorisations collaborateur](permissions.md) dans Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b53d7-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="b53d7-109">Un modèle de recommandation de produits, d’attrition de transactions, d’attrition d’abonnements ou de valeur de durée de vie du client configuré dans Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b53d7-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="b53d7-110">Passez en revue les conditions requises pour configurer les différents modèles :</span><span class="sxs-lookup"><span data-stu-id="b53d7-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="b53d7-111">Modèle de recommandation de produits</span><span class="sxs-lookup"><span data-stu-id="b53d7-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="b53d7-112">Modèle d’attrition d’abonnements</span><span class="sxs-lookup"><span data-stu-id="b53d7-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="b53d7-113">Modèle d’attrition de transactions</span><span class="sxs-lookup"><span data-stu-id="b53d7-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="b53d7-114">Modèle de valeur de durée de vie du client</span><span class="sxs-lookup"><span data-stu-id="b53d7-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="b53d7-115">Créer un segment de client basé sur des prédictions</span><span class="sxs-lookup"><span data-stu-id="b53d7-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="b53d7-116">Accédez à **Intelligence** > **Prédictions** et sélectionnez l’onglet **Mes prédictions**.</span><span class="sxs-lookup"><span data-stu-id="b53d7-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="b53d7-117">Sélectionnez les points de suspension verticaux en regard du modèle que vous souhaitez réviser et sélectionnez **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="b53d7-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="b53d7-118">Sur la page de résultats, sélectionnez **Créer un segment**.</span><span class="sxs-lookup"><span data-stu-id="b53d7-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="b53d7-119">Pour obtenir plus d’informations sur la page de résultats, consultez l’article sur le modèle.</span><span class="sxs-lookup"><span data-stu-id="b53d7-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Capture d’écran de la page des résultats de prédiction avec l’action Créer un segment mise en surbrillance.":::

1. <span data-ttu-id="b53d7-121">Créer un nouveau segment basé sur l’entité de sortie du modèle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b53d7-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="b53d7-122">Pour plus d’informations, consultez [Créer et gérer les segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="b53d7-122">For more information, see [Create and manage segments](segments.md).</span></span>