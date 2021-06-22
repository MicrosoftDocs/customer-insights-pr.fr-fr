---
title: Exemple de guide Prédiction de la valeur de durée de vie du client
description: Utilisez cet exemple de guide pour essayer le modèle de prédiction de la valeur de durée de vie du client.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129942"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="44499-103">Exemple de guide Prédiction de la valeur de durée de vie du client (CLV)</span><span class="sxs-lookup"><span data-stu-id="44499-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="44499-104">Ce guide vous présente un exemple de bout en bout de la prédiction de la valeur de durée de vie du client (CLV) dans Customer Insights à l'aide d'exemples de données.</span><span class="sxs-lookup"><span data-stu-id="44499-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="44499-105">Scénario</span><span class="sxs-lookup"><span data-stu-id="44499-105">Scenario</span></span>

<span data-ttu-id="44499-106">Contoso est une entreprise qui produit du café et des machines à café de haute qualité.</span><span class="sxs-lookup"><span data-stu-id="44499-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="44499-107">L'entreprise vend les produits par l'intermédiaire du site web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="44499-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="44499-108">L'entreprise veut comprendre la valeur (revenus) que ses clients peuvent générer au cours des 12 prochains mois.</span><span class="sxs-lookup"><span data-stu-id="44499-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="44499-109">Le fait de connaître la valeur attendue de leurs clients au cours des 12 prochains mois les aidera à orienter leurs efforts marketing vers les clients à forte valeur ajoutée.</span><span class="sxs-lookup"><span data-stu-id="44499-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="44499-110">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="44499-110">Prerequisites</span></span>

- <span data-ttu-id="44499-111">Au moins des [autorisations contributeur](permissions.md) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="44499-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="44499-112">Nous vous recommandons de mettre en œuvre les étapes suivantes [dans un nouvel environnement](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="44499-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="44499-113">Tâche 1 : ingérer les données</span><span class="sxs-lookup"><span data-stu-id="44499-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="44499-114">Consultez les articles [à propos de l'ingestion de données](data-sources.md) et l'[importation de sources de données à l'aide de connecteurs Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="44499-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="44499-115">Les informations suivantes supposent que vous vous êtes familiarisé avec l’ingestion de données en général.</span><span class="sxs-lookup"><span data-stu-id="44499-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="44499-116">Ingérer les données client d’une plateforme d’eCommerce</span><span class="sxs-lookup"><span data-stu-id="44499-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="44499-117">Créez une source de données nommée **eCommerce**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.</span><span class="sxs-lookup"><span data-stu-id="44499-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="44499-118">Entrez l’URL des contacts d’eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="44499-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="44499-119">Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.</span><span class="sxs-lookup"><span data-stu-id="44499-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="44499-120">Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="44499-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="44499-121">**DateOfBirth** : date</span><span class="sxs-lookup"><span data-stu-id="44499-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="44499-122">**CreatedOn** : date/heure/fuseau</span><span class="sxs-lookup"><span data-stu-id="44499-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformez la date de naissance en date.":::

1. <span data-ttu-id="44499-124">Dans le champ « Nom » du volet droit, renommez votre source de données **Requête** en **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="44499-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="44499-125">**Enregistrez** la source de données.</span><span class="sxs-lookup"><span data-stu-id="44499-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="44499-126">Ingérer les données d’achat en ligne</span><span class="sxs-lookup"><span data-stu-id="44499-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="44499-127">Ajoutez un autre ensemble de données à la même source de données **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="44499-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="44499-128">Choisissez à nouveau le connecteur **Texte/CSV**.</span><span class="sxs-lookup"><span data-stu-id="44499-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="44499-129">Entrez l’URL des données **d’achats en ligne** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="44499-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="44499-130">Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.</span><span class="sxs-lookup"><span data-stu-id="44499-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="44499-131">Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="44499-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="44499-132">**PurchasedOn** : date/heure</span><span class="sxs-lookup"><span data-stu-id="44499-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="44499-133">**TotalPrice** : devise</span><span class="sxs-lookup"><span data-stu-id="44499-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="44499-134">Dans le champ **Nom** du volet latéral, renommez votre source de données **Requête** en **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="44499-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="44499-135">**Enregistrez** la source de données.</span><span class="sxs-lookup"><span data-stu-id="44499-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="44499-136">Ingérer les données client du programme de fidélité</span><span class="sxs-lookup"><span data-stu-id="44499-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="44499-137">Créez une source de données nommée **LoyaltyScheme**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.</span><span class="sxs-lookup"><span data-stu-id="44499-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="44499-138">Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="44499-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="44499-139">Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.</span><span class="sxs-lookup"><span data-stu-id="44499-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="44499-140">Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="44499-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="44499-141">**DateOfBirth** : date</span><span class="sxs-lookup"><span data-stu-id="44499-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="44499-142">**RewardsPoints** : nombre entier</span><span class="sxs-lookup"><span data-stu-id="44499-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="44499-143">**CreatedOn** : date/heure</span><span class="sxs-lookup"><span data-stu-id="44499-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="44499-144">Dans le champ **Nom** du volet droit, renommez votre source de données **Requête** en **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="44499-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="44499-145">**Enregistrez** la source de données.</span><span class="sxs-lookup"><span data-stu-id="44499-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="44499-146">Ingérer les données client des avis sur le site web</span><span class="sxs-lookup"><span data-stu-id="44499-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="44499-147">Créez une source de données nommée **Site web**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.</span><span class="sxs-lookup"><span data-stu-id="44499-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="44499-148">Entrez l’URL des contacts d’eCommerce https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="44499-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="44499-149">Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.</span><span class="sxs-lookup"><span data-stu-id="44499-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="44499-150">Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="44499-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="44499-151">**ReviewRating** : nombre décimal</span><span class="sxs-lookup"><span data-stu-id="44499-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="44499-152">**ReviewDate** : date</span><span class="sxs-lookup"><span data-stu-id="44499-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="44499-153">Dans le champ « Nom » du volet droit, renommez votre source de données **Requête** en **Évaluations**.</span><span class="sxs-lookup"><span data-stu-id="44499-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="44499-154">**Enregistrez** la source de données.</span><span class="sxs-lookup"><span data-stu-id="44499-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="44499-155">Tâche 2 : unification des données</span><span class="sxs-lookup"><span data-stu-id="44499-155">Task 2 - Data unification</span></span>

<span data-ttu-id="44499-156">Après avoir ingéré les données, nous commençons maintenant le processus d'unification des données pour créer un profil client unifié.</span><span class="sxs-lookup"><span data-stu-id="44499-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="44499-157">Pour plus d’informations, consultez [Unification des données](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="44499-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="44499-158">Mappage</span><span class="sxs-lookup"><span data-stu-id="44499-158">Map</span></span>

1. <span data-ttu-id="44499-159">Une fois les données ingérées, mappez les contacts des données d’eCommerce et du programme de fidélité aux types de données courants.</span><span class="sxs-lookup"><span data-stu-id="44499-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="44499-160">Accédez à **Données** > **Unifier** > **Mettre en correspondance**.</span><span class="sxs-lookup"><span data-stu-id="44499-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="44499-161">Sélectionnez les entités qui représentent le profil client : **eCommerceContacts** et **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="44499-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="44499-162">Sélectionnez ensuite **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="44499-162">Then, select **Apply**.</span></span>

   ![Unifiez les sources de données d’eCommerce et du programme de fidélité.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="44499-164">Sélectionnez **ContactId** comme clé primaire pour **eCommerceContacts** et **LoyaltyID** comme clé primaire pour **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="44499-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unifiez LoyaltyId comme clé primaire.](media/unify-loyaltyid.png)

1. <span data-ttu-id="44499-166">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="44499-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="44499-167">Correspondance</span><span class="sxs-lookup"><span data-stu-id="44499-167">Match</span></span>

1. <span data-ttu-id="44499-168">Accédez à l’onglet **Mettre en correspondance** et sélectionnez **Définir l’ordre**.</span><span class="sxs-lookup"><span data-stu-id="44499-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="44499-169">Dans la liste déroulante **Primaire**, choisissez **eCommerceContacts : eCommerce** comme source principale et incluez tous les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="44499-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="44499-170">Dans la liste déroulante **Entité 2**, choisissez **loyCustomers : LoyaltyScheme** et incluez tous les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="44499-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Unifiez l’ordre de mise en correspondance des données d’eCommerce et du programme de fidélité.](media/unify-match-order.png)

1. <span data-ttu-id="44499-172">Sélectionnez **Ajouter une règle**</span><span class="sxs-lookup"><span data-stu-id="44499-172">Select **Add rule**</span></span>

1. <span data-ttu-id="44499-173">Ajoutez votre première condition en utilisant FullName.</span><span class="sxs-lookup"><span data-stu-id="44499-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="44499-174">Pour eCommerceContacts, sélectionnez **FullName** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="44499-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="44499-175">Pour loyCustomers, sélectionnez **FullName** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="44499-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="44499-176">Sélectionnez la liste déroulante **Normaliser** et choisissez **Type (téléphone, nom, adresse, ...)**.</span><span class="sxs-lookup"><span data-stu-id="44499-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="44499-177">Définissez le **Niveau de précision** sur **Base** et la **Valeur** sur **Élevé**.</span><span class="sxs-lookup"><span data-stu-id="44499-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="44499-178">Saisissez le nom **FullName, Email** pour la nouvelle règle.</span><span class="sxs-lookup"><span data-stu-id="44499-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="44499-179">Ajoutez une deuxième condition pour l’adresse e-mail en sélectionnant **Ajouter une condition**</span><span class="sxs-lookup"><span data-stu-id="44499-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="44499-180">Pour l’entité eCommerceContacts, choisissez **E-mail** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="44499-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="44499-181">Pour l’entité loyCustomers, choisissez **E-mail** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="44499-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="44499-182">Laissez le champ Normaliser vide.</span><span class="sxs-lookup"><span data-stu-id="44499-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="44499-183">Définissez le **Niveau de précision** sur **Base** et la **Valeur** sur **Élevé**.</span><span class="sxs-lookup"><span data-stu-id="44499-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Unifiez la règle de mise en correspondance pour le nom et l’adresse e-mail.](media/unify-match-rule.png)

1. <span data-ttu-id="44499-185">Cliquez sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="44499-185">Select **Done**.</span></span>

1. <span data-ttu-id="44499-186">Sélectionnez **Enregistrer** et **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="44499-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="44499-187">Fusionner</span><span class="sxs-lookup"><span data-stu-id="44499-187">Merge</span></span>

1. <span data-ttu-id="44499-188">Accédez à l’onglet **Fusionner**.</span><span class="sxs-lookup"><span data-stu-id="44499-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="44499-189">Dans le champ **ContactId** de l’entité **loyCustomers**, modifiez le nom d’affichage en **ContactIdLOYALTY** pour le différencier des autres ID ingérés.</span><span class="sxs-lookup"><span data-stu-id="44499-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Renommez contactid à partir de l’ID du programme de fidélité.](media/unify-merge-contactid.png)

1. <span data-ttu-id="44499-191">Sélectionnez **Enregistrer** et **Exécuter les processus de fusion et en aval**.</span><span class="sxs-lookup"><span data-stu-id="44499-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="44499-192">Tâche 3 – Configurer la prédiction de la valeur de durée de vie du client</span><span class="sxs-lookup"><span data-stu-id="44499-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="44499-193">Une fois les profils client unifiés en place, nous pouvons désormais exécuter la prédiction de la valeur de durée de vie du client.</span><span class="sxs-lookup"><span data-stu-id="44499-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="44499-194">Pour obtenir les étapes détaillées, voir [Prédiction de la valeur de durée de vie du client (aperçu)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="44499-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="44499-195">Accédez à **Intelligence**  > **Prédictions** et sélectionnez le **Modèle de valeur de la durée de vie du client**.</span><span class="sxs-lookup"><span data-stu-id="44499-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="44499-196">Parcourez les informations dans le volet latéral et sélectionnez **Commencer**.</span><span class="sxs-lookup"><span data-stu-id="44499-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="44499-197">Nommez le modèle **Prédiction de valeur de durée de vie du client OOB eCommerce** et l'entité de sortie **OOBeCommerceCLVPediction**.</span><span class="sxs-lookup"><span data-stu-id="44499-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="44499-198">Définissez les préférences de modèle pour le modèle CLV :</span><span class="sxs-lookup"><span data-stu-id="44499-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="44499-199">**Période de prédiction** : **12 mois ou 1 an**.</span><span class="sxs-lookup"><span data-stu-id="44499-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="44499-200">Ce paramètre définit jusqu'à quand prédire la valeur de durée de vie du client.</span><span class="sxs-lookup"><span data-stu-id="44499-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="44499-201">**Clients actifs** : spécifiez ce que les clients actifs signifient pour votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="44499-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="44499-202">Définissez le délai historique au cours duquel un client doit avoir effectué au moins une transaction pour être considéré comme actif.</span><span class="sxs-lookup"><span data-stu-id="44499-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="44499-203">Le modèle ne prédira la Valeur de la durée de vie du client que pour les clients actifs.</span><span class="sxs-lookup"><span data-stu-id="44499-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="44499-204">Choisissez entre laisser le modèle calculer la période en fonction de l'historique des données de transaction ou fournir un délai spécifique.</span><span class="sxs-lookup"><span data-stu-id="44499-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="44499-205">Dans cet exemple de guide, nous **laissons le modèle calculer l'intervalle d'achat**, qui est l'option par défaut.</span><span class="sxs-lookup"><span data-stu-id="44499-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="44499-206">**Clients à valeur ajoutée** : définissez les clients à valeur ajoutée en tant que centile des clients qui génèrent le plus de revenus.</span><span class="sxs-lookup"><span data-stu-id="44499-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="44499-207">Le modèle utilise cette entrée pour fournir des résultats qui correspondent à la définition que donne votre entreprise des clients à valeur ajoutée.</span><span class="sxs-lookup"><span data-stu-id="44499-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="44499-208">Vous pouvez choisir de laisser le modèle définir les clients à valeur ajoutée.</span><span class="sxs-lookup"><span data-stu-id="44499-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="44499-209">Il utilise une règle heuristique qui dérive le centile.</span><span class="sxs-lookup"><span data-stu-id="44499-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="44499-210">Vous pouvez également définir les clients à valeur ajoutée en tant que centile des clients qui génèreront le plus de revenus.</span><span class="sxs-lookup"><span data-stu-id="44499-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="44499-211">Dans cet exemple de guide, nous définissons manuellement les clients à valeur ajoutée comme **Premiers 30 % des clients payants actifs** et sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="44499-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Étape des préférences dans l'expérience guidée pour le modèle CLV.":::

1. <span data-ttu-id="44499-213">Dans l'étape **Données requises**, sélectionnez **Ajouter des données** pour fournir l'historique des données des transactions.</span><span class="sxs-lookup"><span data-stu-id="44499-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="44499-214">Ajoutez l'entité **eCommercePurchases : eCommerce** et mapper les attributs requis par le modèle :</span><span class="sxs-lookup"><span data-stu-id="44499-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="44499-215">ID de la transaction : eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="44499-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="44499-216">Date de la transaction : eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="44499-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="44499-217">Montant de la transaction : eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="44499-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="44499-218">ID produit : eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="44499-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="44499-219">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="44499-219">Select **Next**.</span></span>

1. <span data-ttu-id="44499-220">Configurez la relation entre l'entité **eCommercePurchases : eCommerce** et **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="44499-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="44499-221">L'étape **Données supplémentaires (facultatif)** vous permet d'ajouter d'autres données d’activité client.</span><span class="sxs-lookup"><span data-stu-id="44499-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="44499-222">Ces données peuvent aider à obtenir plus d'informations sur les interactions des clients avec votre entreprise, ce qui peut contribuer à la CLV.</span><span class="sxs-lookup"><span data-stu-id="44499-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="44499-223">L'ajout d'interactions client clés telles que les journaux Web, les journaux service clientèle ou l'historique du programme de récompenses peut améliorer la précision des prédictions.</span><span class="sxs-lookup"><span data-stu-id="44499-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="44499-224">Sélectionnez **Ajouter des données** pour inclure d'autres données sur l'activité des clients.</span><span class="sxs-lookup"><span data-stu-id="44499-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="44499-225">Ajoutez l'entité d'activité client et mappez ses noms de champs aux champs correspondants requis par le modèle :</span><span class="sxs-lookup"><span data-stu-id="44499-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="44499-226">Entité d'activité client : Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="44499-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="44499-227">Clé primaire : Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="44499-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="44499-228">Horodatage : Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="44499-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="44499-229">Événement (nom de l'activité) : Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="44499-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="44499-230">Détails (montant ou valeur) : Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="44499-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="44499-231">Sélectionnez **Suivant** et configurez l'activité et la relation entre les données de transaction et les données client :</span><span class="sxs-lookup"><span data-stu-id="44499-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="44499-232">Type d'activité : Choisir un type d'activité existant</span><span class="sxs-lookup"><span data-stu-id="44499-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="44499-233">Étiquette de l’activité : Évaluation</span><span class="sxs-lookup"><span data-stu-id="44499-233">Activity label: Review</span></span>
   - <span data-ttu-id="44499-234">Étiquette correspondante : Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="44499-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="44499-235">Entité client : eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="44499-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="44499-236">Relation : WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="44499-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="44499-237">Sélectionnez **Suivant** pour définir la planification du modèle.</span><span class="sxs-lookup"><span data-stu-id="44499-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="44499-238">Le modèle doit s'entraîner régulièrement pour apprendre de nouveaux modèles lorsque de nouvelles données sont ingérées.</span><span class="sxs-lookup"><span data-stu-id="44499-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="44499-239">Pour cet exemple, choisissez **Mensuel**.</span><span class="sxs-lookup"><span data-stu-id="44499-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="44499-240">Une fois tous les détails passés en revue, sélectionnez **Enregistrer et exécuter**.</span><span class="sxs-lookup"><span data-stu-id="44499-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="44499-241">Tâche 4 : passer en revue les résultats et les explications du modèle</span><span class="sxs-lookup"><span data-stu-id="44499-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="44499-242">Laissez le modèle terminer la formation et la notation des données.</span><span class="sxs-lookup"><span data-stu-id="44499-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="44499-243">Ensuite, vous pouvez consulter les résultats et les explications du modèle CLV.</span><span class="sxs-lookup"><span data-stu-id="44499-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="44499-244">Pour plus d’informations, consultez [Passer en revue le statut et les résultats d’une prédiction](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="44499-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="44499-245">Tâche 5 – Créer un segment de clients à valeur ajoutée</span><span class="sxs-lookup"><span data-stu-id="44499-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="44499-246">L'exécution du modèle crée une nouvelle entité, qui est répertoriée dans **Données** > **Entités**.</span><span class="sxs-lookup"><span data-stu-id="44499-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="44499-247">Vous pouvez créer un nouveau segment de clientèle basé sur l'entité créée par le modèle.</span><span class="sxs-lookup"><span data-stu-id="44499-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="44499-248">Accédez à **Segments**.</span><span class="sxs-lookup"><span data-stu-id="44499-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="44499-249">Sélectionnez **Nouveau** et choisissez **Créer à partir de** > **Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="44499-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Création d’un segment avec la sortie du modèle.](media/segment-intelligence.png)

1. <span data-ttu-id="44499-251">Sélectionnez l'entité **OOBeCommerceCLVPediction** et définissez le segment :</span><span class="sxs-lookup"><span data-stu-id="44499-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="44499-252">Champ : CLVScore</span><span class="sxs-lookup"><span data-stu-id="44499-252">Field: CLVScore</span></span>
  - <span data-ttu-id="44499-253">Opérateur : supérieur à</span><span class="sxs-lookup"><span data-stu-id="44499-253">Operator: greater than</span></span>
  - <span data-ttu-id="44499-254">Valeur : 1500</span><span class="sxs-lookup"><span data-stu-id="44499-254">Value: 1500</span></span>

1. <span data-ttu-id="44499-255">Sélectionnez **Vérifier** et **Enregistrer** le segment.</span><span class="sxs-lookup"><span data-stu-id="44499-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="44499-256">Vous disposez désormais d'un segment qui identifie les clients qui devraient générer plus de 1 500 $ de revenus au cours des 12 prochains mois.</span><span class="sxs-lookup"><span data-stu-id="44499-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="44499-257">Ce segment est mis à jour dynamiquement si d'autres données sont ingérées.</span><span class="sxs-lookup"><span data-stu-id="44499-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="44499-258">Pour plus d’informations, consultez [Créer et gérer les segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="44499-258">For more information, see [Create and manage segments](segments.md).</span></span>
