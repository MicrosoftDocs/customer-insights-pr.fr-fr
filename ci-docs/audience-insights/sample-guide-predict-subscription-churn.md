---
title: Exemple de guide de prédiction de l’attrition des abonnements
description: Utilisez cet exemple de guide pour essayer le modèle de prédiction de l’attrition des abonnements prédéfini.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: fa460fa5c79bc8a356ec5e90050ec85e05c55be8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306300"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="a268a-103">Exemple de guide de prédiction de l’attrition des abonnements (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="a268a-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="a268a-104">Nous vous présenterons un exemple de bout en bout de prédiction de l’attrition des abonnements en utilisant les exemples de données fournis ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a268a-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="a268a-105">Scénario</span><span class="sxs-lookup"><span data-stu-id="a268a-105">Scenario</span></span>

<span data-ttu-id="a268a-106">Contoso est une entreprise qui produit du café et des machines à café de haute qualité, qu'elle vend via son site web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="a268a-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="a268a-107">Elle a récemment lancé un système d’abonnement pour que ses clients achètent régulièrement du café.</span><span class="sxs-lookup"><span data-stu-id="a268a-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="a268a-108">Son objectif est de comprendre quels clients abonnés risquent d’annuler leur abonnement dans les prochains mois.</span><span class="sxs-lookup"><span data-stu-id="a268a-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="a268a-109">Savoir lesquels de ses clients **sont susceptibles de se tourner vers la concurrence**, peut l’aider à économiser ses efforts marketing en se concentrant sur leur fidélisation.</span><span class="sxs-lookup"><span data-stu-id="a268a-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a268a-110">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="a268a-110">Prerequisites</span></span>

- <span data-ttu-id="a268a-111">Au minimum [Autorisations collaborateur](permissions.md) dans Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a268a-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="a268a-112">Nous vous recommandons de mettre en œuvre les étapes suivantes [dans un nouvel environnement](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="a268a-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="a268a-113">Tâche 1 : ingérer les données</span><span class="sxs-lookup"><span data-stu-id="a268a-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="a268a-114">Passez en revue les articles sur [l’ingestion de données](data-sources.md) et [l’importation de sources de données à l’aide des connecteurs Power Query](connect-power-query.md) en particulier.</span><span class="sxs-lookup"><span data-stu-id="a268a-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="a268a-115">Les informations suivantes supposent que vous vous êtes familiarisé avec l’ingestion de données en général.</span><span class="sxs-lookup"><span data-stu-id="a268a-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="a268a-116">Ingérer les données client d’une plateforme d’eCommerce</span><span class="sxs-lookup"><span data-stu-id="a268a-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="a268a-117">Créez une source de données nommée **eCommerce**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.</span><span class="sxs-lookup"><span data-stu-id="a268a-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a268a-118">Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="a268a-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="a268a-119">Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.</span><span class="sxs-lookup"><span data-stu-id="a268a-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a268a-120">Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="a268a-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="a268a-121">**DateOfBirth** : date</span><span class="sxs-lookup"><span data-stu-id="a268a-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="a268a-122">**CreatedOn** : date/heure/fuseau</span><span class="sxs-lookup"><span data-stu-id="a268a-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformez la date de naissance en date.":::

1. <span data-ttu-id="a268a-124">Dans le champ **Nom** du volet droit, renommez votre source de données **Requête** en **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="a268a-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="a268a-125">Enregistrez la source de données.</span><span class="sxs-lookup"><span data-stu-id="a268a-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="a268a-126">Ingérer les données client du programme de fidélité</span><span class="sxs-lookup"><span data-stu-id="a268a-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="a268a-127">Créez une source de données nommée **LoyaltyScheme**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.</span><span class="sxs-lookup"><span data-stu-id="a268a-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a268a-128">Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="a268a-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="a268a-129">Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.</span><span class="sxs-lookup"><span data-stu-id="a268a-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a268a-130">Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="a268a-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="a268a-131">**DateOfBirth** : date</span><span class="sxs-lookup"><span data-stu-id="a268a-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="a268a-132">**RewardsPoints** : nombre entier</span><span class="sxs-lookup"><span data-stu-id="a268a-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="a268a-133">**CreatedOn** : date/heure</span><span class="sxs-lookup"><span data-stu-id="a268a-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="a268a-134">Dans le champ **Nom** du volet droit, renommez votre source de données **Requête** en **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="a268a-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="a268a-135">Enregistrez la source de données.</span><span class="sxs-lookup"><span data-stu-id="a268a-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="a268a-136">Ingérer les informations sur l’abonnement</span><span class="sxs-lookup"><span data-stu-id="a268a-136">Ingest subscription information</span></span>

1. <span data-ttu-id="a268a-137">Créez une source de données nommée **SubscriptionHistory**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.</span><span class="sxs-lookup"><span data-stu-id="a268a-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a268a-138">Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="a268a-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="a268a-139">Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.</span><span class="sxs-lookup"><span data-stu-id="a268a-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a268a-140">Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="a268a-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="a268a-141">**SubscriptioID** : nombre entier</span><span class="sxs-lookup"><span data-stu-id="a268a-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="a268a-142">**SubscriptionAmount** : devise</span><span class="sxs-lookup"><span data-stu-id="a268a-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="a268a-143">**SubscriptionEndDate** : date/heure</span><span class="sxs-lookup"><span data-stu-id="a268a-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="a268a-144">**SubscriptionStartDate** : date/heure</span><span class="sxs-lookup"><span data-stu-id="a268a-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="a268a-145">**TransactionDate** : date/heure</span><span class="sxs-lookup"><span data-stu-id="a268a-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="a268a-146">**IsRecurring** : vrai/faux</span><span class="sxs-lookup"><span data-stu-id="a268a-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="a268a-147">**Is_auto_renew** : vrai/faux</span><span class="sxs-lookup"><span data-stu-id="a268a-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="a268a-148">**RécurrentFrequencyInMonths** : nombre entier</span><span class="sxs-lookup"><span data-stu-id="a268a-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="a268a-149">Dans le champ **Nom** du volet droit, renommez votre source de données **Requête** en **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="a268a-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="a268a-150">Enregistrez la source de données.</span><span class="sxs-lookup"><span data-stu-id="a268a-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="a268a-151">Ingérer les données client des avis sur le site web</span><span class="sxs-lookup"><span data-stu-id="a268a-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="a268a-152">Créez une source de données nommée **Site web**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.</span><span class="sxs-lookup"><span data-stu-id="a268a-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a268a-153">Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="a268a-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="a268a-154">Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.</span><span class="sxs-lookup"><span data-stu-id="a268a-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a268a-155">Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="a268a-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="a268a-156">**ReviewRating** : nombre entier</span><span class="sxs-lookup"><span data-stu-id="a268a-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="a268a-157">**ReviewDate** : date</span><span class="sxs-lookup"><span data-stu-id="a268a-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="a268a-158">Dans le champ « Nom » du volet droit, renommez votre source de données **Requête** en **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="a268a-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="a268a-159">Tâche 2 : unification des données</span><span class="sxs-lookup"><span data-stu-id="a268a-159">Task 2 - Data unification</span></span>

<span data-ttu-id="a268a-160">Une fois les données ingérées, nous commençons maintenant le processus de **Mappage, correspondance, fusion** pour créer un profil client unifié.</span><span class="sxs-lookup"><span data-stu-id="a268a-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="a268a-161">Pour plus d’informations, consultez [Unification des données](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="a268a-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="a268a-162">Mappage</span><span class="sxs-lookup"><span data-stu-id="a268a-162">Map</span></span>

1. <span data-ttu-id="a268a-163">Une fois les données ingérées, mappez les contacts des données d’eCommerce et du programme de fidélité aux types de données courants.</span><span class="sxs-lookup"><span data-stu-id="a268a-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="a268a-164">Accédez à **Données** > **Unifier** > **Mettre en correspondance**.</span><span class="sxs-lookup"><span data-stu-id="a268a-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="a268a-165">Sélectionnez les entités qui représentent le profil client : **eCommerceContacts** et **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="a268a-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Unifiez les sources de données d’eCommerce et du programme de fidélité.":::

1. <span data-ttu-id="a268a-167">Sélectionnez **ContactId** comme clé primaire pour **eCommerceContacts** et **LoyaltyID** comme clé primaire pour **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="a268a-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unifiez LoyaltyId comme clé primaire.":::

### <a name="match"></a><span data-ttu-id="a268a-169">Correspondance</span><span class="sxs-lookup"><span data-stu-id="a268a-169">Match</span></span>

1. <span data-ttu-id="a268a-170">Accédez à l’onglet **Mettre en correspondance** et sélectionnez **Définir l’ordre**.</span><span class="sxs-lookup"><span data-stu-id="a268a-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="a268a-171">Dans la liste déroulante **Principal**, choisissez **eCommerceContacts : eCommerce** comme source principale et incluez tous les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="a268a-171">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="a268a-172">Dans la liste déroulante **Entité 2**, choisissez **loyCustomers : LoyaltyScheme** et incluez tous les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="a268a-172">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unifiez l’ordre de mise en correspondance des données d’eCommerce et du programme de fidélité.":::

1. <span data-ttu-id="a268a-174">Sélectionnez **Créer une nouvelle règle**</span><span class="sxs-lookup"><span data-stu-id="a268a-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="a268a-175">Ajoutez votre première condition en utilisant FullName.</span><span class="sxs-lookup"><span data-stu-id="a268a-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="a268a-176">Pour eCommerceContacts, sélectionnez **FullName** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="a268a-176">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="a268a-177">Pour loyCustomers, sélectionnez **FullName** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="a268a-177">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="a268a-178">Sélectionnez la liste déroulante **Normaliser** et choisissez **Type (téléphone, nom, adresse, ...)**.</span><span class="sxs-lookup"><span data-stu-id="a268a-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="a268a-179">Définissez le **Niveau de précision** sur **Base** et la **Valeur** sur **Élevé**.</span><span class="sxs-lookup"><span data-stu-id="a268a-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="a268a-180">Saisissez le nom **FullName, Email** pour la nouvelle règle.</span><span class="sxs-lookup"><span data-stu-id="a268a-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="a268a-181">Ajoutez une deuxième condition pour l’adresse e-mail en sélectionnant **Ajouter une condition**</span><span class="sxs-lookup"><span data-stu-id="a268a-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="a268a-182">Pour l’entité eCommerceContacts, choisissez **E-mail** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="a268a-182">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="a268a-183">Pour l’entité loyCustomers, choisissez **E-mail** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="a268a-183">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="a268a-184">Laissez le champ Normaliser vide.</span><span class="sxs-lookup"><span data-stu-id="a268a-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="a268a-185">Définissez le **Niveau de précision** sur **Base** et la **Valeur** sur **Élevé**.</span><span class="sxs-lookup"><span data-stu-id="a268a-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unifiez la règle de mise en correspondance pour le nom et l’adresse e-mail.":::

7. <span data-ttu-id="a268a-187">Sélectionnez **Enregistrer** et **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a268a-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="a268a-188">Fusionner</span><span class="sxs-lookup"><span data-stu-id="a268a-188">Merge</span></span>

1. <span data-ttu-id="a268a-189">Accédez à l’onglet **Fusionner**.</span><span class="sxs-lookup"><span data-stu-id="a268a-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="a268a-190">Dans le champ **ContactId** de l’entité **loyCustomers**, modifiez le nom d’affichage en **ContactIdLOYALTY** pour le différencier des autres ID ingérés.</span><span class="sxs-lookup"><span data-stu-id="a268a-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Renommez contactid à partir de l’ID du programme de fidélité.":::

1. <span data-ttu-id="a268a-192">Sélectionnez **Enregistrer** et **Exécuter** pour démarrer le processus de fusion.</span><span class="sxs-lookup"><span data-stu-id="a268a-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="a268a-193">Tâche 3 : configurer la prédiction de l’attrition des abonnements</span><span class="sxs-lookup"><span data-stu-id="a268a-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="a268a-194">Une fois les profils clients unifiés en place, nous pouvons maintenant exécuter la prédiction de l’attrition des abonnements.</span><span class="sxs-lookup"><span data-stu-id="a268a-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="a268a-195">Pour connaître les étapes détaillées, consultez l’article [Prédiction de l’attrition des abonnements (version préliminaire)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="a268a-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="a268a-196">Accédez à **Intelligence** > **Découvrir** et choisissez le **Modèle d’attrition clients**.</span><span class="sxs-lookup"><span data-stu-id="a268a-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="a268a-197">Sélectionnez l’option **Abonnement** et sélectionnez **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="a268a-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="a268a-198">Nommez le modèle **Prédiction de l’attrition des abonnements OOB** et l’entité de sortie **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="a268a-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="a268a-199">Définissez deux conditions pour le modèle d’attrition :</span><span class="sxs-lookup"><span data-stu-id="a268a-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="a268a-200">**Jours depuis la fin de l’abonnement** : **au moins 60** jours.</span><span class="sxs-lookup"><span data-stu-id="a268a-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="a268a-201">Si un client ne renouvelle son abonnement dans cette période après la fin de celui-ci, il est considéré comme ayant résilié.</span><span class="sxs-lookup"><span data-stu-id="a268a-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="a268a-202">**Définition de l’attrition** : **au moins 93** jours.</span><span class="sxs-lookup"><span data-stu-id="a268a-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="a268a-203">Durée de la prédiction du modèle pendant laquelle les clients risquent de se désabonner.</span><span class="sxs-lookup"><span data-stu-id="a268a-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="a268a-204">Plus vous regardez loin dans le futur, moins les résultats sont précis.</span><span class="sxs-lookup"><span data-stu-id="a268a-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Sélectionnez la fenêtre de prédiction des leviers du modèle et la définition de l’attrition.":::

1. <span data-ttu-id="a268a-206">Sélectionnez **Ajouter les données requises** et sélectionnez **Ajouter des données** pour l’historique des abonnements.</span><span class="sxs-lookup"><span data-stu-id="a268a-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="a268a-207">Ajoutez l’entité **Abonnement : SubscriptionHistory** et mappez les champs d’eCommerce aux champs correspondants requis par le modèle.</span><span class="sxs-lookup"><span data-stu-id="a268a-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="a268a-208">Associez l’entité **Abonnement : SubscriptionHistory** à **eCommerceContacts : eCommerce**, nommez la relation **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="a268a-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Associez les entités d’eCommerce.":::

1. <span data-ttu-id="a268a-210">Sous Activités client, ajoutez l’entité **webReviews : site web** et mappez les champs de webReviews aux champs correspondants requis par le modèle.</span><span class="sxs-lookup"><span data-stu-id="a268a-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="a268a-211">Clé primaire : ReviewId</span><span class="sxs-lookup"><span data-stu-id="a268a-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="a268a-212">Horodatage : ReviewDate</span><span class="sxs-lookup"><span data-stu-id="a268a-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="a268a-213">Événement : ReviewRating</span><span class="sxs-lookup"><span data-stu-id="a268a-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="a268a-214">Configurez une activité pour les avis sur le site web.</span><span class="sxs-lookup"><span data-stu-id="a268a-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="a268a-215">Sélectionnez l’activité **Avis** et associez l’entité **webReviews : site web** à **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="a268a-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="a268a-216">Sélectionnez **Suivant** pour définir la planification du modèle.</span><span class="sxs-lookup"><span data-stu-id="a268a-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="a268a-217">Le modèle doit s’entraîner régulièrement à apprendre de nouveaux modèles lorsque de nouvelles données sont ingérées.</span><span class="sxs-lookup"><span data-stu-id="a268a-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="a268a-218">Dans cet exemple, sélectionnez **Mensuel**.</span><span class="sxs-lookup"><span data-stu-id="a268a-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="a268a-219">Une fois tous les détails passés en revue, sélectionnez **Enregistrer et exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a268a-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="a268a-220">Tâche 4 : passer en revue les résultats et les explications du modèle</span><span class="sxs-lookup"><span data-stu-id="a268a-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="a268a-221">Laissez le modèle terminer la formation et la notation des données.</span><span class="sxs-lookup"><span data-stu-id="a268a-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="a268a-222">Vous pouvez maintenant passer en revue les explications du modèle d’attrition des abonnements.</span><span class="sxs-lookup"><span data-stu-id="a268a-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="a268a-223">Pour plus d’informations, consultez [Passer en revue le statut et les résultats d’une prédiction](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="a268a-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="a268a-224">Tâche 5 : créer un segment de clients à haut risque d’attrition</span><span class="sxs-lookup"><span data-stu-id="a268a-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="a268a-225">L’exécution du modèle de production crée une nouvelle entité que vous pouvez voir dans **Données** > **Entités**.</span><span class="sxs-lookup"><span data-stu-id="a268a-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="a268a-226">Vous pouvez créer un nouveau segment basé sur l’entité créée par le modèle.</span><span class="sxs-lookup"><span data-stu-id="a268a-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="a268a-227">Accédez à **Segments**.</span><span class="sxs-lookup"><span data-stu-id="a268a-227">Go to **Segments**.</span></span> <span data-ttu-id="a268a-228">Sélectionnez **Nouveau** et choisissez **Créer à partir de** > **Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="a268a-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Création d’un segment avec la sortie du modèle.":::

1. <span data-ttu-id="a268a-230">Sélectionnez le point de terminaison **OOBSubscriptionChurnPrediction** et définissez le segment :</span><span class="sxs-lookup"><span data-stu-id="a268a-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="a268a-231">Champ : ChurnScore</span><span class="sxs-lookup"><span data-stu-id="a268a-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="a268a-232">Opérateur : supérieur à</span><span class="sxs-lookup"><span data-stu-id="a268a-232">Operator: greater than</span></span>
   - <span data-ttu-id="a268a-233">Valeur : 0,6</span><span class="sxs-lookup"><span data-stu-id="a268a-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configurez le segment d’attrition des abonnements.":::

<span data-ttu-id="a268a-235">Vous disposez maintenant d’un segment mis à jour de manière dynamique qui identifie les clients à haut risque d’attrition pour cette activité d’abonnement.</span><span class="sxs-lookup"><span data-stu-id="a268a-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="a268a-236">Pour plus d’informations, consultez [Créer et gérer les segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a268a-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]