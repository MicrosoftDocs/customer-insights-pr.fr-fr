---
title: Exemple de guide de prédiction de l’attrition transactionnelle
description: Utilisez cet exemple de guide pour essayer le modèle de prédiction de l’attrition transactionnelle prédéfini.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609681"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Exemple de guide de prédiction de l’attrition transactionnelle

Ce guide vous présentera un exemple de bout en bout de prédiction de l’attrition transactionnelle en utilisant des exemples de données. Nous vous recommandons d’essayer cette prédiction [dans un nouvel environnement](manage-environments.md).

## <a name="scenario"></a>Scénario

Contoso est une entreprise qui produit du café et des machines à café de haute qualité. Ils vendent les produits via leur site web Contoso Coffee. Son objectif est de savoir quels clients qui achètent régulièrement ses produits, cesseront d’être des clients actifs au cours des 60 prochains jours. Savoir lesquels de ses clients **sont susceptibles de se tourner vers la concurrence**, peut l’aider à économiser ses efforts marketing en se concentrant sur leur fidélisation.

## <a name="prerequisites"></a>Conditions préalables

- Au moins des [autorisations contributeur](permissions.md).

## <a name="task-1---ingest-data"></a>Tâche 1 : ingérer les données

Consultez les articles [à propos de l’ingestion de données](data-sources.md) et la [connexion à une source de données Power Query](connect-power-query.md). Les informations suivantes supposent que vous vous êtes familiarisé avec l’ingestion de données en général.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingérer les données client d’une plateforme d’eCommerce

1. Créez une source de données nommée **eCommerce** et sélectionnez le connecteur **Texte/CSV**.

1. Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadclasscontacts.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :

   - **DateOfBirth** : date
   - **CreatedOn** : date/heure/fuseau

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformez la date de naissance en date.":::

1. Dans le champ **Nom** du volet droit, renommez votre source de données en **eCommerceContacts**

1. Enregistrez la source de données.

### <a name="ingest-online-purchase-data"></a>Ingérer les données d’achat en ligne

1. Ajoutez un autre ensemble de données à la même source de données **eCommerce**. Choisissez à nouveau le connecteur **Texte/CSV**.

1. Entrez l’URL des données d’achats en ligne https://aka.ms/ciadclassonline.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :

   - **PurchasedOn** : date/heure
   - **TotalPrice** : devise

1. Dans le champ **Nom** du volet droit, renommez votre source de données en **eCommercePurchases**.

1. Enregistrez la source de données.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingérer les données client du programme de fidélité

1. Créez une source de données nommée **LoyaltyScheme** et sélectionnez le connecteur **Texte/CSV**.

1. Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :

   - **DateOfBirth** : date
   - **RewardsPoints** : nombre entier
   - **CreatedOn** : date/heure

1. Dans le champ **Nom** du volet droit, renommez votre source de données en **loyCustomers**.

1. Enregistrez la source de données.

## <a name="task-2---data-unification"></a>Tâche 2 : unification des données

Consultez l’article [sur l’unification des données](data-unification.md). Les informations suivantes supposent que vous vous êtes familiarisé avec l’unification de données en général.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tâche 3 : créer une activité d’historique des transactions

Consultez l’article [sur les activités client](activities.md). Les informations suivantes supposent que vous vous êtes familiarisé avec la création d’activités en général.

1. Créez une activité appelée **eCommercePurchases** avec l’entité *eCommercePurchases:eCommerce* et sa clé primaire, **PurchaseId**.

1. Créez une relation entre *eCommercePurchases:eCommerce* et *eCommerceContacts:eCommerce* avec **ContactID** comme clé étrangère pour connecter les deux entités.

1. Sélectionnez **TotalPrice** pour **EventActivity** et **PurchasedOn** pour **TimeStamp**.

1. Sélectionnez **SalesOrderLine** pour le **Type d’activité** et mappez sémantiquement les données d’activité.

1. Exécutez l’activité.

## <a name="task-4---configure-transaction-churn-prediction"></a>Tâche 4 : configurer la prédiction de l’attrition des transactions

Avec les profils de clients unifiés en place et l’activité, exécutez la prédiction d’attrition des transactions.

1. Accédez à **Intelligence** > **Prédictions**.

1. Dans l’onglet **Créer**, sélectionnez **Utiliser le modèle** dans **Modèle d’attrition clients**.

1. Sélectionnez **Transactionnel** pour le type d’attrition, puis **Démarrer**.

1. Nommez le modèle **Prédiction de l’attrition des transactions d’eCommerce OOB** et l’entité de sortie **OOBeCommerceChurnPrediction**.

1. Cliquez sur **Suivant**.

1. Définissez les préférences du modèle :

   - **Période de prédiction** : **60** jours pour définir jusqu’où dans le futur nous voulons prédire l’attrition clients.

   - **Définition de l’attrition** : **60** jours pour indiquer la durée sans achat au-delà de laquelle un client est considéré comme perdu.

     :::image type="content" source="media/model-levers.PNG" alt-text="Sélectionnez la période de prédiction des préférences du modèle et la définition de l’attrition.":::

1. Cliquez sur **Suivant**.

1. Sélectionnez **Historique des achats (requis)** et sélectionnez **Ajouter des données** pour l’historique des achats.

1. Sélectionnez **SalesOrderLine** et l’entité eCommercePurchases et sélectionnez **Suivant**. Les données requises sont automatiquement renseignées à partir de l’activité. Sélectionnez **Enregistrer**, puis **Suivant**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Associez les entités d’eCommerce.":::

1. Ignorez l’étape **Données supplémentaires (facultatif)**.

1. À l’étape **Mises à jour des données**, sélectionnez **Mensuel** pour la planification du modèle.

1. Une fois tous les détails passés en revue, sélectionnez **Enregistrer et exécuter**.

## <a name="task-5---review-model-results-and-explanations"></a>Tâche 5 : passer en revue les résultats et les explications du modèle

Laissez le modèle terminer la formation et la notation des données. Consultez les explications sur le modèle d’attrition. Pour plus d’informations, consultez [Afficher les résultats de la prédiction](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Tâche 6 : créer un segment de clients à haut risque d’attrition

L’exécution du modèle de production crée une nouvelle entité, qui est répertoriée dans **Données** > **Entités**. Vous pouvez créer un nouveau segment basé sur l’entité créée par le modèle.

1. Sur la page de résultats, sélectionnez **Créer un segment**.

1. Créez une règle en utilisant l’entité **OOBeCommerceChurnPrediction** et définissez le segment :
   - **Champ** : ChurnScore
   - **Opérateur** : supérieur à
   - **Valeur** : 0.6

1. Sélectionnez **Enregistrer** et **Exécutez** le segment.

Vous avez maintenant un segment mis à jour dynamiquement qui identifie les clients présentant un haut risque de désabonnement. Pour plus d’informations, consultez [Créer et gérer les segments](segments.md).

> [!TIP]
> Vous pouvez également créer un segment pour un modèle de prédiction à partir de la page **Segments** en sélectionnant **Nouveau** et en choisissant **Créer à partir de** > **Intelligence**. Pour plus d’informations, consultez [Créer un nouveau segment avec des segments rapides](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
