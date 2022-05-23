---
title: Exemple de guide de prédiction de l’attrition des abonnements
description: Utilisez cet exemple de guide pour essayer le modèle de prédiction de l’attrition des abonnements prédéfini.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741408"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Exemple de guide de prédiction de l’attrition des abonnements

Nous vous présenterons un exemple de bout en bout de prédiction de l’attrition des abonnements en utilisant les exemples de données fournis ci-dessous. 

## <a name="scenario"></a>Scénario

Contoso est une société qui produit du café et des machines à café de haute qualité qu’elle vend sur son site web Contoso Coffee. Elle a récemment lancé un système d’abonnement pour que ses clients achètent régulièrement du café. Son objectif est de comprendre quels clients abonnés risquent d’annuler leur abonnement dans les prochains mois. Savoir lesquels de ses clients **sont susceptibles de se tourner vers la concurrence**, peut l’aider à économiser ses efforts marketing en se concentrant sur leur fidélisation.

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

### <a name="ingest-subscription-information"></a>Ingérer les informations sur l’abonnement

1. Créez une source de données nommée **SubscriptionHistory**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.

1. Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadchurnsubscriptionhistory.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :

   - **SubscriptioID** : nombre entier
   - **SubscriptionAmount** : devise
   - **SubscriptionEndDate** : date/heure
   - **SubscriptionStartDate** : date/heure
   - **TransactionDate** : date/heure
   - **IsRecurring** : vrai/faux
   - **Is_auto_renew** : vrai/faux
   - **RécurrentFrequencyInMonths** : nombre entier

1. Dans le champ **Nom** du volet droit, renommez votre source de données **Requête** en **SubscriptionHistory**.

1. Enregistrez la source de données.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingérer les données client des avis sur le site web

1. Créez une source de données nommée **Site web**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.

1. Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadclasswebsite.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :

   - **ReviewRating** : nombre entier
   - **ReviewDate** : date

1. Dans le champ « Nom » du volet droit, renommez votre source de données **Requête** en **webReviews**.

## <a name="task-2---data-unification"></a>Tâche 2 : unification des données

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>Tâche 3 : configurer la prédiction de l’attrition des abonnements

Une fois les profils clients unifiés en place, nous pouvons maintenant exécuter la prédiction de l’attrition des abonnements. Pour connaître les étapes détaillées, consultez l’article [Prédiction du taux de désabonnement](predict-subscription-churn.md). 

1. Accédez à **Intelligence** > **Découvrir** et choisissez le **Modèle d’attrition clients**.

1. Sélectionnez l’option **Abonnement** et sélectionnez **Démarrer**.

1. Nommez le modèle **Prédiction de l’attrition des abonnements OOB** et l’entité de sortie **OOBSubscriptionChurnPrediction**.

1. Définissez deux conditions pour le modèle d’attrition :

   * **Jours depuis la fin de l’abonnement** : **au moins 60** jours. Si un client ne renouvelle son abonnement dans cette période après la fin de celui-ci, il est considéré comme ayant résilié. 

   * **Définition de l’attrition** : **au moins 93** jours. Durée de la prédiction du modèle pendant laquelle les clients risquent de se désabonner. Plus vous regardez loin dans le futur, moins les résultats sont précis.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Sélectionnez la fenêtre de prédiction des leviers du modèle et la définition de l’attrition.":::

1. Sélectionnez **Ajouter les données requises** et sélectionnez **Ajouter des données** pour l’historique des abonnements.

1. Ajoutez l’entité **Abonnement : SubscriptionHistory** et mappez les champs d’eCommerce aux champs correspondants requis par le modèle.

1. Associez l’entité **Abonnement : SubscriptionHistory** à **eCommerceContacts : eCommerce**, nommez la relation **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Associez les entités d’eCommerce.":::

1. Sous Activités client, ajoutez l’entité **webReviews : site web** et mappez les champs de webReviews aux champs correspondants requis par le modèle. 
   - Clé primaire : ReviewId
   - Horodatage : ReviewDate
   - Événement : ReviewRating

1. Configurez une activité pour les avis sur le site web. Sélectionnez l’activité **Avis** et associez l’entité **webReviews : site web** à **eCommerceContacts : eCommerce**.

1. Sélectionnez **Suivant** pour définir la planification du modèle.

   Le modèle doit s’entraîner régulièrement à apprendre de nouveaux modèles lorsque de nouvelles données sont ingérées. Dans cet exemple, sélectionnez **Mensuel**.

1. Une fois tous les détails passés en revue, sélectionnez **Enregistrer et exécuter**.

## <a name="task-4---review-model-results-and-explanations"></a>Tâche 4 : passer en revue les résultats et les explications du modèle

Laissez le modèle terminer la formation et la notation des données. Vous pouvez maintenant passer en revue les explications du modèle d’attrition des abonnements. Pour plus d’informations, consultez [Passer en revue le statut et les résultats d’une prédiction](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Tâche 5 : créer un segment de clients à haut risque d’attrition

L’exécution du modèle de production crée une nouvelle entité que vous pouvez voir dans **Données** > **Entités**.   

Vous pouvez créer un nouveau segment basé sur l’entité créée par le modèle.

1.  Accédez à **Segments**. Sélectionnez **Nouveau** et choisissez **Créer à partir de** > **Intelligence**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Création d’un segment avec la sortie du modèle.":::

1. Sélectionnez le point de terminaison **OOBSubscriptionChurnPrediction** et définissez le segment : 
   - Champ : ChurnScore
   - Opérateur : supérieur à
   - Valeur : 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configurez le segment d’attrition des abonnements.":::

Vous disposez maintenant d’un segment mis à jour de manière dynamique qui identifie les clients à haut risque d’attrition pour cette activité d’abonnement.

Pour plus d’informations, consultez [Créer et gérer les segments](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]