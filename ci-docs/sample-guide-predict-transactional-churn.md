---
title: Exemple de guide de prédiction de l’attrition transactionnelle
description: Utilisez cet exemple de guide pour essayer le modèle de prédiction de l’attrition transactionnelle prédéfini.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741316"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Exemple de guide de prédiction de l’attrition transactionnelle

Ce guide vous présentera un exemple de bout en bout de prédiction de l’attrition transactionnelle dans Customer Insights en utilisant les données fournies ci-dessous. Toutes les données utilisées dans ce guide ne sont pas des données client réelles et font partie de l’ensemble de données de Contoso disponibles dans l’environnement de *Démonstration* de votre abonnement Customer Insights.

## <a name="scenario"></a>Scénario

Contoso est une société qui produit du café et des machines à café de haute qualité qu’elle vend sur son site web Contoso Coffee. Son objectif est de savoir quels clients qui achètent régulièrement ses produits, cesseront d’être des clients actifs au cours des 60 prochains jours. Savoir lesquels de ses clients **sont susceptibles de se tourner vers la concurrence**, peut l’aider à économiser ses efforts marketing en se concentrant sur leur fidélisation.

## <a name="prerequisites"></a>Conditions préalables

- Au minimum [Autorisations collaborateur](permissions.md) dans Customer Insights.
- Nous vous recommandons de mettre en œuvre les étapes suivantes [dans un nouvel environnement](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tâche 1 : ingérer les données

Consultez les articles [à propos de l’ingestion de données](data-sources.md) et [importation de sources de données à l’aide connecteurs Power Query](connect-power-query.md) spécifiquement. Les informations suivantes supposent que vous vous êtes familiarisé avec l’ingestion de données en général. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingérer les données client d’une plateforme d’eCommerce

1. Créez une source de données nommée **eCommerce**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.

1. Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadclasscontacts.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :

   - **DateOfBirth** : date
   - **CreatedOn** : date/heure/fuseau

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformez la date de naissance en date.":::

1. Dans le champ **Nom** du volet droit, renommez votre source de données **Requête** en **eCommerceContacts**

1. Enregistrez la source de données.

### <a name="ingest-online-purchase-data"></a>Ingérer les données d’achat en ligne

1. Ajoutez un autre ensemble de données à la même source de données **eCommerce**. Choisissez à nouveau le connecteur **Texte/CSV**.

1. Entrez l’URL des données **d’achats en ligne** https://aka.ms/ciadclassonline.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :

   - **PurchasedOn** : date/heure
   - **TotalPrice** : devise
   
1. Dans le champ **Nom** du volet droit, renommez votre source de données **Requête** en **eCommercePurchases**.

1. Enregistrez la source de données.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingérer les données client du programme de fidélité

1. Créez une source de données nommée **LoyaltyScheme**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.

1. Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :

   - **DateOfBirth** : date
   - **RewardsPoints** : nombre entier
   - **CreatedOn** : date/heure

1. Dans le champ **Nom** du volet droit, renommez votre source de données **Requête** en **loyCustomers**.

1. Enregistrez la source de données.

## <a name="task-2---data-unification"></a>Tâche 2 : unification des données

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Tâche 3 : configurer la prédiction de l’attrition des transactions

Avec les profils de clients unifiés en place, nous pouvons maintenant exécuter la prédiction d’attrition des transactions. Pour connaître les étapes détaillées, consultez l’article [Prédiction de l’attrition des transactions](predict-transactional-churn.md). 

1. Accédez à **Intelligence** > **Découvrir** et choisissez le **Modèle d’attrition clients**.

1. Sélectionnez l’option **Transactionnel** et sélectionnez **Démarrer**.

1. Nommez le modèle **Prédiction de l’attrition des transactions d’eCommerce OOB** et l’entité de sortie **OOBeCommerceChurnPrediction**.

1. Définissez deux conditions pour le modèle d’attrition :

   * **Fenêtre de prédiction** : **au moins 60** jours. Ce paramètre définit la période sur laquelle vous souhaitez prédire l’attrition clients.

   * **Définition de l’attrition** : **au moins 60** jours. La durée sans achats après laquelle un client est considéré comme perdu.

     :::image type="content" source="media/model-levers.PNG" alt-text="Sélectionnez la fenêtre de prédiction des leviers du modèle et la définition de l’attrition.":::

1. Sélectionnez **Historique des achats (requis)** et sélectionnez **Ajouter des données** pour l’historique des achats.

1. Ajoutez l’entité **eCommercePurchases : eCommerce** et mappez les champs d’eCommerce aux champs correspondants requis par le modèle.

1. Associez l’entité **eCommercePurchases : eCommerce** à **eCommerceContacts : eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Associez les entités d’eCommerce.":::

1. Sélectionnez **Suivant** pour définir la planification du modèle.

   Le modèle doit s’entraîner régulièrement à apprendre de nouveaux modèles lorsque de nouvelles données sont ingérées. Dans cet exemple, sélectionnez **Mensuel**.

1. Une fois tous les détails passés en revue, sélectionnez **Enregistrer et exécuter**.

## <a name="task-4---review-model-results-and-explanations"></a>Tâche 4 : passer en revue les résultats et les explications du modèle

Laissez le modèle terminer la formation et la notation des données. Vous pouvez maintenant consulter les explications sur le modèle d’attrition. Pour plus d’informations, consultez [Passer en revue le statut et les résultats d’une prédiction](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Tâche 5 : créer un segment de clients à haut risque d’attrition

L’exécution du modèle de production crée une nouvelle entité que vous pouvez voir dans **Données** > **Entités**.   

Vous pouvez créer un nouveau segment basé sur l’entité créée par le modèle.

1.  Accédez à **Segments**. Sélectionnez **Nouveau** et choisissez **Créer à partir de** > **Intelligence**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Création d’un segment avec la sortie du modèle.":::

1. Sélectionnez le point de terminaison **OOBeCommerceChurnPrediction** et définissez le segment : 
   - Champ : ChurnScore
   - Opérateur : supérieur à
   - Valeur : 0,6

Vous avez maintenant un segment mis à jour dynamiquement qui identifie les clients présentant un haut risque de désabonnement.

Pour plus d’informations, consultez [Créer et gérer les segments](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
