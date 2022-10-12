---
title: Présentation des prédictions
description: Scénarios et options de prédiction couverts par l’application Dynamics 365 Customer Insights.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610187"
---
# <a name="predictions-overview"></a>Présentation des prédictions

Dynamics 365 Customer Insights est fourni avec de nombreuses options qui exploitent l’IA et le Machine Learning pour prédire les données.

## <a name="out-of-box-models"></a>Modèles prêts à l’emploi

Le moyen le plus simple de commencer à prédire les données est de recourir à des modèles prédéfinis, souvent appelés modèles prêts à l’emploi. Ils ne nécessitent que certaines données et certaines structures pour générer rapidement des informations. Les modèles suivants sont disponibles :

# <a name="individual-consumers-b-to-c"></a>[Consommateurs individuels (B-to-C)](#tab/b2c)

- [Valeur de durée de vie du client](predict-customer-lifetime-value.md) : prédit les revenus potentiels d’un client tout au long de l’interaction avec une entreprise.
- [Recommandation de produits](predict-product-recommendation.md) : suggère des ensembles de recommandations de produits prédictives basées sur le comportement d’achat et les clients ayant des modèles d’achat similaires.
- [Attrition des abonnements](predict-subscription-churn.md) : prédit si un client risque de ne plus utiliser les produits ou services d’abonnement de votre société.
- [Attrition de transactions](predict-transactional-churn.md) : prédit si un client individuel n’achètera plus vos produits ou services sur une certaine période.
- [Analyse des sentiments](sentiment-analysis.md) : analyse le sentiment des commentaires de vos clients et identifie les aspects commerciaux fréquemment mentionnés.

# <a name="business-accounts-b-to-b"></a>[Comptes d’entreprise (B-to-B)](#tab/b2b)

- [Attrition de transactions](predict-transactional-churn.md) : prédit si un compte client n’achètera plus vos produits ou services sur une certaine période.

---

> [!TIP]
> Nous vous recommandons d’actualiser régulièrement les modèles prédéfinis avec les données mises à jour pour vous assurer qu’ils informent avec précision votre cas d’utilisation métier. Les données sont actualisées de manière ad hoc lorsque le système ingère des sources de données nouvelles ou mises à jour. Cependant, les modèles ne seront restaurés que dans ce cas et continueront à utiliser les données de formation existantes.
>
> Configurez un **Calendrier de mise à jour** en définissant le calendrier de réentraînement du modèle pendant la configuration. Le modèle sera réentraîné et restauré selon ce calendrier, que vous pouvez modifier à tout moment.

## <a name="azure-machine-learning-integration"></a>Intégration d’Azure Machine Learning

Si une organisation utilise déjà des scénarios de Machine Learning basés sur des expériences Azure Machine Learning, la fonctionnalité de modèles personnalisés dans Customer Insights permet de connecter les points. Créez des flux de travail qui vous aident à choisir les données pour lesquelles vous souhaitez générer des informations et à mettre en correspondance les résultats avec vos profils de client unifiés. Pour plus d’informations, voir [Modèles personnalisés Machine Learning](custom-models.md).

## <a name="manage-existing-predictions"></a>Gérer les prédictions existantes

Accédez à la page **Intelligence** > **Prédictions**. Dans l’onglet **Mes prédictions**, affichez les prédictions que vous avez créées, leur type de prédiction, le nom de l’entité de sortie, le statut, la dernière modification de la prédiction et la dernière actualisation des données. Vous pouvez trier la liste de prédictions par colonne.

Sélectionnez une prédiction pour voir les actions disponibles.

:::image type="content" source="media/predictions.png" alt-text="Page Mes prédictions.":::

- **Modifiez** la prédiction pour modifier ses propriétés.
- [**Actualisez**](#refresh-a-prediction) la prédiction pour inclure les données les plus récentes.
- **Affichez** les détails de la prédiction.
- [**Rapport d’utilisabilité des données d’entrée**](#view-the-input-data-usability-report) pour afficher les erreurs, les avertissements et les recommandations.
- **Supprimez** la prédiction.

### <a name="refresh-a-prediction"></a>Actualiser une prédiction

Les prédictions peuvent être actualisées selon une planification automatique ou actualisées manuellement à la demande. Pour actualiser manuellement toutes les prédictions, sélectionnez **Actualiser tout**. Pour actualiser manuellement une prédiction, sélectionnez-la et sélectionnez **Actualiser**. Pour [planifier une actualisation automatique](schedule-refresh.md), accédez à **Administrateur** > **Système** > **Planification**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Afficher le rapport d’utilisation des données d’entrée

Le rapport d'utilisation des données d'entrée fournit une vue consolidée des erreurs et des avertissements que vos prédictions prêtes à l'emploi peuvent générer. Il donne également des recommandations sur la manière d’améliorer les performances du modèle.

Le rapport est disponible une fois qu'un modèle a terminé son processus d'entraînement. Il est créé pour chaque modèle séparément, qu’il ait terminé la formation avec succès ou non.

Dans l’onglet **Mes prédictions**, sélectionnez la prédiction et choisissez **Rapport d’utilisabilité des données d’entrée**. Ou bien, à partir de la vue des détails de la prédiction, sélectionnez **Rapport d’utilisabilité des données d’entrée**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemple de rapport d'utilisation des données d'entrée montrant un tableau avec des erreurs, des avertissements et des recommandations.":::

Le rapport comprend :

- **Nom :** nom descriptif de l'erreur, de l'avertissement ou de la recommandation.
- **Étape :** phase, entraînement ou score du modèle auquel l'information fait référence.
- **État :** gravité de l'information (erreur, avertissement, recommandation).
- **Nom de la colonne :** colonne dans une entité qui doit être modifiée pour améliorer les performances du modèle.
- **Nom de l'entité :** nom de l'entité qui doit être modifiée pour améliorer les performances du modèle.
- **Détails :** détails sur l'erreur, l'avertissement ou la recommandation.

[!INCLUDE [footer-include](includes/footer-banner.md)]
