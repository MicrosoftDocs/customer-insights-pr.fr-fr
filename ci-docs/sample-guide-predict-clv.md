---
title: Exemple de guide Prédiction de la valeur de durée de vie du client (CLV)
description: Utilisez cet exemple de guide pour essayer le modèle de prédiction de la valeur de durée de vie du client.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 2013533ed225a396d21e51e63297d7608ce58ac6
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051634"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Exemple de guide Prédiction de la valeur de durée de vie du client (CLV)

Ce guide vous présente un exemple de bout en bout de la prédiction de la valeur de durée de vie du client (CLV) dans Customer Insights à l’aide d’exemples de données.

## <a name="scenario"></a>Scénario

Contoso est une entreprise qui produit du café et des machines à café de haute qualité. Ils vendent les produits via leur site web Contoso Coffee. L’entreprise veut comprendre la valeur (revenus) que ses clients peuvent générer au cours des 12 prochains mois. Le fait de connaître la valeur attendue de leurs clients au cours des 12 prochains mois les aidera à orienter leurs efforts marketing vers les clients à forte valeur ajoutée.

## <a name="prerequisites"></a>Conditions préalables

- Au minimum [Autorisations collaborateur](permissions.md) dans Customer Insights.
- Nous vous recommandons de mettre en œuvre les étapes suivantes [dans un nouvel environnement](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tâche 1 : ingérer les données

Consultez les articles [à propos de l’ingestion de données](data-sources.md) et [importation de sources de données à l’aide connecteurs Power Query](connect-power-query.md). Les informations suivantes supposent que vous vous êtes familiarisé avec l’ingestion de données en général.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingérer les données client d’une plateforme d’eCommerce

1. Créez une source de données nommée **eCommerce**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.

1. Entrez l’URL des contacts d’eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :
   - **DateOfBirth** : date
   - **CreatedOn** : date/heure/fuseau

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformez la date de naissance en date.":::

1. Dans le champ « Nom » du volet droit, renommez votre source de données **Requête** en **eCommerceContacts**

1. **Enregistrez** la source de données.

### <a name="ingest-online-purchase-data"></a>Ingérer les données d’achat en ligne

1. Ajoutez un autre ensemble de données à la même source de données **eCommerce**. Choisissez à nouveau le connecteur **Texte/CSV**.

1. Entrez l’URL des données **d’achats en ligne** https://aka.ms/ciadclassonline.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :
   - **PurchasedOn** : date/heure
   - **TotalPrice** : devise

1. Dans le champ **Nom** du volet latéral, renommez votre source de données **Requête** en **eCommercePurchases**.

1. **Enregistrez** la source de données.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingérer les données client du programme de fidélité

1. Créez une source de données nommée **LoyaltyScheme**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.

1. Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :
   - **DateOfBirth** : date
   - **RewardsPoints** : nombre entier
   - **CreatedOn** : date/heure

1. Dans le champ **Nom** du volet droit, renommez votre source de données **Requête** en **loyCustomers**.

1. **Enregistrez** la source de données.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingérer les données client des avis sur le site web

1. Créez une source de données nommée **Site web**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.

1. Entrez l’URL des contacts d’eCommerce https://aka.ms/CI-ILT/WebReviews.

1. Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.

1. Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :

   - **ReviewRating** : nombre décimal
   - **ReviewDate** : date

1. Dans le champ « Nom » du volet droit, renommez votre source de données **Requête** en **Évaluations**.

1. **Enregistrez** la source de données.

## <a name="task-2---data-unification"></a>Tâche 2 : unification des données

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Tâche 3 – Configurer la prédiction de la valeur de durée de vie du client

Une fois les profils client unifiés en place, nous pouvons désormais exécuter la prédiction de la valeur de durée de vie du client. Pour les étapes détaillées, voir [Prédiction de la valeur de durée de vie du client](predict-customer-lifetime-value.md).

1. Accédez à **Intelligence**  > **Prédictions** et sélectionnez le **Modèle de valeur de la durée de vie du client**.

1. Parcourez les informations dans le volet latéral et sélectionnez **Commencer**.

1. Nommez le modèle **Prédiction de valeur de durée de vie du client OOB eCommerce** et l’entité de sortie **OOBeCommerceCLVPediction**.

1. Définissez les préférences de modèle pour le modèle CLV :
   - **Période de prédiction** : **12 mois ou 1 an**. Ce paramètre définit jusqu’à quand prédire la valeur de durée de vie du client.
   - **Clients actifs** : spécifiez ce que les clients actifs signifient pour votre entreprise. Définissez le délai historique au cours duquel un client doit avoir effectué au moins une transaction pour être considéré comme actif. Le modèle ne prédira la Valeur de la durée de vie du client que pour les clients actifs. Choisissez entre laisser le modèle calculer la période en fonction de l’historique des données de transaction ou fournir un délai spécifique. Dans cet exemple de guide, nous **laissons le modèle calculer l’intervalle d’achat**, qui est l’option par défaut.
   - **Clients à valeur ajoutée** : définissez les clients à valeur ajoutée en tant que centile des clients qui génèrent le plus de revenus. Le modèle utilise cette entrée pour fournir des résultats qui correspondent à la définition que donne votre entreprise des clients à valeur ajoutée. Vous pouvez choisir de laisser le modèle définir les clients à valeur ajoutée. Il utilise une règle heuristique qui dérive le centile. Vous pouvez également définir les clients à valeur ajoutée en tant que centile des clients qui génèreront le plus de revenus. Dans cet exemple de guide, nous définissons manuellement les clients à valeur ajoutée comme **Premiers 30 % des clients payants actifs** et sélectionnez **Suivant**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Étape des préférences dans l’expérience guidée pour le modèle CLV.":::

1. Dans l’étape **Données requises**, sélectionnez **Ajouter des données** pour fournir l’historique des données des transactions.

1. Ajoutez l’entité **eCommercePurchases : eCommerce** et mapper les attributs requis par le modèle :
   - ID de la transaction : eCommerce.eCommercePurchases.PurchaseId
   - Date de la transaction : eCommerce.eCommercePurchases.PurchasedOn
   - Montant de la transaction : eCommerce.eCommercePurchases.TotalPrice
   - ID produit : eCommerce.eCommercePurchases.ProductId

1. Cliquez sur **Suivant**.

1. Configurez la relation entre l’entité **eCommercePurchases : eCommerce** et **eCommerceContacts : eCommerce**.

1. L’étape **Données supplémentaires (facultatif)** vous permet d’ajouter d’autres données d’activité client. Ces données peuvent aider à obtenir plus d’informations sur les interactions des clients avec votre entreprise, ce qui peut contribuer à la CLV. L’ajout d’interactions client clés telles que les journaux Web, les journaux service clientèle ou l’historique du programme de récompenses peut améliorer la précision des prédictions. Sélectionnez **Ajouter des données** pour inclure d’autres données sur l’activité des clients.

1. Ajoutez l’entité d’activité client et mappez ses noms de champs aux champs correspondants requis par le modèle :
   - Entité d’activité client : Reviews:Website
   - Clé primaire : Website.Reviews.ReviewId
   - Horodatage : Website.Reviews.ReviewDate
   - Événement (nom de l’activité) : Website.Reviews.ActivityTypeDisplay
   - Détails (montant ou valeur) : Website.Reviews.ReviewRating

1. Sélectionnez **Suivant** et configurez l’activité et la relation entre les données de transaction et les données client :  
   - Type d’activité : Choisir un type d’activité existant
   - Étiquette de l’activité : Évaluation
   - Étiquette correspondante : Website.Reviews.UserId
   - Entité client : eCommerceContacts:eCommerce
   - Relation : WebsiteReviews

1. Sélectionnez **Suivant** pour définir la planification du modèle.

   Le modèle doit s’entraîner régulièrement pour apprendre de nouveaux modèles lorsque de nouvelles données sont ingérées. Pour cet exemple, choisissez **Mensuel**.

1. Une fois tous les détails passés en revue, sélectionnez **Enregistrer et exécuter**.

## <a name="task-4---review-model-results-and-explanations"></a>Tâche 4 : passer en revue les résultats et les explications du modèle

Laissez le modèle terminer la formation et la notation des données. Ensuite, vous pouvez consulter les résultats et les explications du modèle CLV. Pour plus d’informations, consultez [Passer en revue le statut et les résultats d’une prédiction](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Tâche 5 – Créer un segment de clients à valeur ajoutée

L’exécution du modèle crée une nouvelle entité, qui est répertoriée dans **Données** > **Entités**. Vous pouvez créer un nouveau segment de clientèle basé sur l’entité créée par le modèle.

1. Accédez à **Segments**. 

1. Sélectionnez **Nouveau** et choisissez **Créer à partir de** > **Intelligence**.

   ![Création d’un segment avec la sortie du modèle.](media/segment-intelligence.png)

1. Sélectionnez l’entité **OOBeCommerceCLVPediction** et définissez le segment :
  - Champ : CLVScore
  - Opérateur : supérieur à
  - Valeur : 1500

1. Sélectionnez **Vérifier** et **Enregistrer** le segment.

Vous disposez désormais d’un segment qui identifie les clients qui devraient générer plus de 1 500 $ de revenus au cours des 12 prochains mois. Ce segment est mis à jour dynamiquement si d’autres données sont ingérées.

Pour plus d’informations, consultez [Créer et gérer les segments](segments.md).
