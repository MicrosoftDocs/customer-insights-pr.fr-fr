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
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Créer un segment basé sur un modèle de prédiction (version préliminaire)

Les résultats des prédictions ne s’appliquent parfois qu’à un sous-ensemble de vos clients. Augmentez la personnalisation des recommandations en créant des segments à partir des résultats des modèles de prédiction. Par exemple, vous souhaitez peut-être donner des recommandations spécifiques aux clients qui préfèrent un certain type de service. 

## <a name="prerequisites"></a>Conditions préalables

- Au minimum [Autorisations collaborateur](permissions.md) dans Customer Insights.

- Un modèle de recommandation de produits, d’attrition de transactions, d’attrition d’abonnements ou de valeur de durée de vie du client configuré dans Customer Insights. Passez en revue les conditions requises pour configurer les différents modèles :

  - [Modèle de recommandation de produits](predict-product-recommendation.md)
  - [Modèle d’attrition d’abonnements](predict-subscription-churn.md)
  - [Modèle d’attrition de transactions](predict-transactional-churn.md)
  - [Modèle de valeur de durée de vie du client](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Créer un segment de client basé sur des prédictions

1. Accédez à **Intelligence** > **Prédictions** et sélectionnez l’onglet **Mes prédictions**.

1. Sélectionnez les points de suspension verticaux en regard du modèle que vous souhaitez réviser et sélectionnez **Afficher**.

1. Sur la page de résultats, sélectionnez **Créer un segment**. Pour obtenir plus d’informations sur la page de résultats, consultez l’article sur le modèle.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Capture d’écran de la page des résultats de prédiction avec l’action Créer un segment mise en surbrillance.":::

1. Créer un nouveau segment basé sur l’entité de sortie du modèle sélectionné. Pour plus d’informations, consultez [Créer et gérer les segments](segments.md).