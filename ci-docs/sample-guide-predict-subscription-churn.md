---
title: Exemple de guide de prédiction de l’attrition des abonnements
description: Utilisez cet exemple de guide pour essayer le modèle de prédiction de l’attrition des abonnements prédéfini.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610003"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Exemple de guide de prédiction de l’attrition des abonnements

Ce guide vous présentera un exemple de bout en bout de prédiction du taux de désabonnement en utilisant des exemples de données. Nous vous recommandons d’essayer cette prédiction [dans un nouvel environnement](manage-environments.md).

## <a name="scenario"></a>Scénario

Contoso est une entreprise qui produit du café et des machines à café de haute qualité. Ils vendent les produits via leur site web Contoso Coffee. Elle a récemment lancé un système d’abonnement pour que ses clients achètent régulièrement du café. Son objectif est de comprendre quels clients abonnés risquent d’annuler leur abonnement dans les prochains mois. Savoir lesquels de ses clients **sont susceptibles de se tourner vers la concurrence**, peut l’aider à économiser ses efforts marketing en se concentrant sur leur fidélisation.

## <a name="prerequisites"></a>Conditions préalables

- Au minimum [Autorisations collaborateur](permissions.md) dans Customer Insights.

## <a name="task-1---ingest-data"></a>Tâche 1 : ingérer les données

Consultez les articles [à propos de l’ingestion de données](data-sources.md) et la [connexion à une source de données Power Query](connect-power-query.md). Les informations suivantes supposent que vous vous êtes familiarisé avec l’ingestion de données en général.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingérer les données client d’une plateforme d’eCommerce

1. Créez une source de données Power Query nommée **eCommerce** et sélectionnez le connecteur **Texte/CSV**.

1. Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadclasscontacts.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :
   - **DateOfBirth** : date
   - **CreatedOn** : date/heure/fuseau

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformez la date de naissance en date.":::

1. Dans le champ **Nom** du volet droit, renommez votre source de données en **eCommerceContacts**

1. Enregistrez la source de données.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingérer les données client du programme de fidélité

1. Créez une source de données nommée **LoyaltyScheme** et sélectionnez le connecteur **Texte/CSV**.

1. Saisissez l’URL des clients du programme de fidélité https://aka.ms/ciadclasscustomerloyalty.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :
   - **DateOfBirth** : date
   - **RewardsPoints** : nombre entier
   - **CreatedOn** : date/heure

1. Dans le champ **Nom** du volet droit, renommez votre source de données en **loyCustomers**.

1. Enregistrez la source de données.

### <a name="ingest-subscription-information"></a>Ingérer les informations sur l’abonnement

1. Créez une source de données nommée **SubscriptionHistory** et sélectionnez le connecteur **Texte/CSV**.

1. Saisissez l’URL des abonnements https://aka.ms/ciadchurnsubscriptionhistory.

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

1. Dans le champ **Nom** du volet droit, renommez votre source de données en **SubscriptionHistory**.

1. Enregistrez la source de données.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingérer les données client des avis sur le site web

1. Créez une source de données nommée **Site Web** et sélectionnez le connecteur **Texte/CSV**.

1. Entrez l’URL pour les révisions du site Web https://aka.ms/ciadclasswebsite.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :
   - **ReviewRating** : nombre entier
   - **ReviewDate** : date

1. Dans le champ **Nom** du volet droit, renommez votre source de données en **webReviews**.

## <a name="task-2---data-unification"></a>Tâche 2 : unification des données

Consultez l’article [sur l’unification des données](data-unification.md). Les informations suivantes supposent que vous vous êtes familiarisé avec l’unification de données en général.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tâche 3 : créer une activité d’historique des transactions

Consultez l’article [sur les activités client](activities.md). Les informations suivantes supposent que vous vous êtes familiarisé avec la création d’activités en général.

1. Créez une activité appelée **SubscriptionHistory** avec l’entité *Abonnement* et sa clé primaire, **CustomerId**.

1. Créez une relation entre *SubscriptionHistory:Subscription* et *eCommerceContacts:eCommerce* avec **CustomerID** comme clé étrangère pour connecter les deux entités.

1. Sélectionnez **SubscriptionType** pour **EventActivity** et **SubscriptionEndDate** de **TimeStamp**.

1. Sélectionnez **Abonnement** pour le **Type d’activité** et mappez sémantiquement les données d’activité.

1. Exécutez l’activité.

1. Ajoutez une autre activité et associez ses noms de champs aux champs correspondants :
   - Entité d’activité client : Reviews:Website
   - Clé primaire : Website.Reviews.ReviewId
   - Horodatage : Website.Reviews.ReviewDate
   - Événement (nom de l’activité) : Website.Reviews.ActivityTypeDisplay
   - Détails (montant ou valeur) : Website.Reviews.ReviewRating

1. Exécutez l’activité.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Tâche 4 : configurer la prédiction de l’attrition des abonnements

Une fois les profils clients unifiés en place et l’activité créée, exécutez la prédiction du taux de désabonnement. Pour connaître les étapes détaillées, consultez [Prédiction du taux de désabonnement](predict-subscription-churn.md).

1. Accédez à **Intelligence** > **Prédictions**.

1. Dans l’onglet **Créer**, sélectionnez **Utiliser le modèle** dans la vignette **Modèle d’attrition clients**.

1. Sélectionnez **Abonnement** pour le type d’attrition, puis **Démarrer**.

1. Nommez le modèle **Prédiction de l’attrition des abonnements OOB** et l’entité de sortie **OOBSubscriptionChurnPrediction**.

1. Définissez les préférences du modèle :
   - **Jours depuis la fin de l’abonnement** : **60** jours pour indiquer qu’un client est considéré comme désabonné s’il ne renouvelle pas l’abonnement dans cette période après la fin de son abonnement.
   - **Jours à examiner à l’avenir pour prévoir l’attrition** : **93** jours correspondant à la durée pendant laquelle le modèle prédit quels clients pourraient se désabonner. Plus vous regardez loin dans le futur, moins les résultats sont précis.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Sélectionnez les préférences du modèle et la définition de l’attrition.":::

1. Cliquez sur **Suivant**.

1. Dans l’étape **Données requises**, sélectionnez **Ajouter des données** pour fournir l’historique des abonnements.

1. Sélectionnez **Abonnement** et l’entité SubscriptionHistory et sélectionnez **Suivant**. Les données requises sont automatiquement renseignées à partir de l’activité. Cliquez sur **Enregistrer**.

1. Sous Activités client, sélectionnez **Ajouter des données**.

1. Pour cet exemple, ajoutez l’activité de révision Web.

1. Cliquez sur **Suivant**.

1. À l’étape **Mises à jour des données**, sélectionnez **Mensuel** pour la planification du modèle.

1. Une fois tous les détails passés en revue, sélectionnez **Enregistrer et exécuter**.

## <a name="task-5---review-model-results-and-explanations"></a>Tâche 5 : passer en revue les résultats et les explications du modèle

Laissez le modèle terminer la formation et la notation des données. Consultez les explications sur le modèle d’attrition des abonnements. Pour plus d’informations, consultez [Afficher les résultats de la prédiction](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Tâche 6 : créer un segment de clients à haut risque d’attrition

L’exécution du modèle crée une nouvelle entité, qui est répertoriée dans **Données** > **Entités**. Vous pouvez créer un nouveau segment basé sur l’entité créée par le modèle.

1. Sur la page de résultats, sélectionnez **Créer un segment**.

1. Créez une règle en utilisant l’entité **OOBSubscriptionChurnPrediction** et définissez le segment :
   - **Champ** : ChurnScore
   - **Opérateur** : supérieur à
   - **Valeur** : 0.6

1. Sélectionnez **Enregistrer** et **Exécutez** le segment.

Vous disposez maintenant d’un segment mis à jour de manière dynamique qui identifie les clients à haut risque d’attrition pour cette activité d’abonnement. Pour plus d’informations, consultez [Créer et gérer les segments](segments.md).

> [!TIP]
> Vous pouvez également créer un segment pour un modèle de prédiction à partir de la page **Segments** en sélectionnant **Nouveau** et en choisissant **Créer à partir de** > **Intelligence**. Pour plus d’informations, consultez [Créer un nouveau segment avec des segments rapides](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
