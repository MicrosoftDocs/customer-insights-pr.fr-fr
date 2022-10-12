---
title: Exemple de guide Prédiction de la valeur de durée de vie du client (CLV)
description: Utilisez cet exemple de guide pour essayer le modèle de prédiction de la valeur de durée de vie du client.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609635"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Exemple de guide Prédiction de la valeur de durée de vie du client (CLV)

Ce guide vous présente un exemple de bout en bout de la prédiction de la valeur de durée de vie du client (CLV) dans Customer Insights en utilisant des exemples de données. Nous vous recommandons d’essayer cette prédiction [dans un nouvel environnement](manage-environments.md).

## <a name="scenario"></a>Scénario

Contoso est une entreprise qui produit du café et des machines à café de haute qualité. Ils vendent les produits via leur site web Contoso Coffee. L’entreprise veut comprendre la valeur (revenus) que ses clients peuvent générer au cours des 12 prochains mois. Le fait de connaître la valeur attendue de leurs clients au cours des 12 prochains mois les aidera à orienter leurs efforts marketing vers les clients à forte valeur ajoutée.

## <a name="prerequisites"></a>Conditions préalables

- Au moins des [autorisations contributeur](permissions.md).

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

1. **Enregistrez** la source de données.

### <a name="ingest-online-purchase-data"></a>Ingérer les données d’achat en ligne

1. Ajoutez un autre ensemble de données à la même source de données **eCommerce**. Choisissez à nouveau le connecteur **Texte/CSV**.

1. Entrez l’URL des données **d’achats en ligne** https://aka.ms/ciadclassonline.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :
   - **PurchasedOn** : date/heure
   - **TotalPrice** : devise

1. Dans le champ **Nom** du volet latéral, renommez votre source de données en **eCommercePurchases**.

1. **Enregistrez** la source de données.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingérer les données client du programme de fidélité

1. Créez une source de données nommée **LoyaltyScheme** et sélectionnez le connecteur **Texte/CSV**.

1. Saisissez l’URL des clients du programme de fidélité https://aka.ms/ciadclasscustomerloyalty.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :
   - **DateOfBirth** : date
   - **RewardsPoints** : nombre entier
   - **CreatedOn** : date/heure

1. Dans le champ **Nom** du volet droit, renommez votre source de données en **loyCustomers**.

1. **Enregistrez** la source de données.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingérer les données client des avis sur le site web

1. Créez une source de données nommée **Site Web** et sélectionnez le connecteur **Texte/CSV**.

1. Entrez l’URL pour les révisions du site Web https://aka.ms/CI-ILT/WebReviews.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :
   - **ReviewRating** : nombre décimal
   - **ReviewDate** : date

1. Dans le champ **Nom** du volet droit, renommez votre source de données en **Révisions**.

1. **Enregistrez** la source de données.

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

1. Ajoutez une autre activité et associez ses noms de champs aux champs correspondants :
   - **Entité d’activité** : Reviews:Website
   - **Clé primaire** : ReviewId
   - **Horodateur** : ReviewDate
   - **Activité de l’événement** : ActivityTypeDisplay
   - **Détails supplémentaires** : ReviewRating
   - **Type d’activité** : révision

1. Exécutez l’activité.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Tâche 4 – Configurer la prédiction de la valeur de durée de vie du client

Une fois les profils client unifiés en place et l’activité créée, exécutez la prédiction de la valeur de durée de vie du client (CLV). Pour les étapes détaillées, voir [Prédiction de la valeur de durée de vie du client](predict-customer-lifetime-value.md).

1. Accédez à **Intelligence** > **Prédictions**.

1. Dans l’onglet **Créer**, sélectionnez **Utiliser le modèle** dans la vignette **Valeur de la durée de vie du client**.

1. Cliquez sur **Démarrer**.

1. Nommez le modèle **Prédiction de valeur de durée de vie du client OOB eCommerce** et l’entité de sortie **OOBeCommerceCLVPediction**.

1. Définissez les préférences du modèle :
   - **Période de prédiction** : **12 mois ou 1 an** pour définir à quelle distance dans le futur prédire la Valeur de la durée de vie du client.
   - **Clients actifs** : **laissez le modèle calculer l’intervalle d’achat** qui est la pếriode dans laquelle un client doit avoir eu au moins une transaction pour être considéré comme actif.
   - **Client à forte valeur ajoutée** : définissez manuellement les clients à forte valeur ajoutée comme les **Premiers 30 % des clients actifs**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Étape des préférences dans l’expérience guidée pour le modèle CLV.":::

1. Cliquez sur **Suivant**.

1. Dans l’étape **Données requises**, sélectionnez **Ajouter des données** pour fournir l’historique des données des transactions.

    :::image type="content" source="media/clv-model-required.png" alt-text="Étape Ajouter des données dans l’expérience guidée pour le modèle CLV.":::

1. Sélectionnez **SalesOrderLine** et l’entité eCommercePurchases et sélectionnez **Suivant**. Les données requises sont automatiquement renseignées à partir de l’activité. Sélectionnez **Enregistrer**, puis **Suivant**.

1. L’étape **Données supplémentaires (facultatif)** vous permet d’ajouter d’autres données d’activité client pour obtenir plus d’informations sur les interactions avec les clients. Pour cet exemple, sélectionnez **Ajouter des données** et ajoutez l’activité de révision Web.

1. Cliquez sur **Suivant**.

1. À l’étape **Mises à jour des données**, sélectionnez **Mensuel** pour la planification du modèle.

1. Cliquez sur **Suivant**.

1. Une fois tous les détails passés en revue, sélectionnez **Enregistrer et exécuter**.

## <a name="task-5---review-model-results-and-explanations"></a>Tâche 5 : passer en revue les résultats et les explications du modèle

Laissez le modèle terminer la formation et la notation des données. Passez en revue les [résultats et les explications du modèle CLV](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Tâche 6 – Créer un segment de clients à valeur ajoutée

L’exécution du modèle crée une nouvelle entité, qui est répertoriée dans **Données** > **Entités**. Vous pouvez créer un nouveau segment de clientèle basé sur l’entité créée par le modèle.

1. Sur la page de résultats, sélectionnez **Créer un segment**.

1. Créez une règle en utilisant l’entité **OOBeCommerceCLVPrediction** et définissez le segment :
   - **Champ** : CLVScore
   - **Opérateur** : supérieur à
   - **Valeur** : 1500

1. Sélectionnez **Enregistrer** et **Exécutez** le segment.

Vous disposez désormais d’un segment qui identifie les clients qui devraient générer plus de 1 500 $ de revenus au cours des 12 prochains mois. Ce segment est mis à jour dynamiquement si d’autres données sont ingérées. Pour plus d’informations, consultez [Créer et gérer les segments](segments.md).

> [!TIP]
> Vous pouvez également créer un segment pour un modèle de prédiction à partir de la page **Segments** en sélectionnant **Nouveau** et en choisissant **Créer à partir de** > **Intelligence**. Pour plus d’informations, consultez [Créer un nouveau segment avec des segments rapides](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
