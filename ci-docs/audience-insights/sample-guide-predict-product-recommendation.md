---
title: Exemple de guide de prédiction de recommandation de produit
description: Utilisez cet exemple de guide pour essayer le modèle de prédiction de recommandation de produit prédéfini.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: a85ee598ec747d0594755314e83a127ce0f2af95
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306163"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="3bd99-103">Exemple de guide (version préliminaire) de prédiction de recommandation de produit</span><span class="sxs-lookup"><span data-stu-id="3bd99-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="3bd99-104">Nous vous présenterons un exemple de bout en bout de prédiction de recommandation de produit en utilisant les exemples de données fournis ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="3bd99-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="3bd99-105">Scénario</span><span class="sxs-lookup"><span data-stu-id="3bd99-105">Scenario</span></span>

<span data-ttu-id="3bd99-106">Contoso est une entreprise qui produit du café et des machines à café de haute qualité, qu'elle vend via son site web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="3bd99-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="3bd99-107">Leur objectif est de comprendre quels produits doivent-ils recommander à leurs clients récurrents.</span><span class="sxs-lookup"><span data-stu-id="3bd99-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="3bd99-108">Savoir ce que sont les clients **susceptible d’acheter**, peut les aider à économiser leurs efforts de marketing en se concentrant sur des éléments spécifiques.</span><span class="sxs-lookup"><span data-stu-id="3bd99-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3bd99-109">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="3bd99-109">Prerequisites</span></span>

- <span data-ttu-id="3bd99-110">Au minimum [Autorisations collaborateur](permissions.md) dans Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3bd99-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="3bd99-111">Nous vous recommandons de mettre en œuvre les étapes suivantes [dans un nouvel environnement](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="3bd99-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="3bd99-112">Tâche 1 : ingérer les données</span><span class="sxs-lookup"><span data-stu-id="3bd99-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="3bd99-113">Passez en revue les articles sur [l’ingestion de données](data-sources.md) et [l’importation de sources de données à l’aide des connecteurs Power Query](connect-power-query.md) en particulier.</span><span class="sxs-lookup"><span data-stu-id="3bd99-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="3bd99-114">Les informations suivantes supposent que vous vous êtes familiarisé avec l’ingestion de données en général.</span><span class="sxs-lookup"><span data-stu-id="3bd99-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="3bd99-115">Ingérer les données client d’une plateforme d’eCommerce</span><span class="sxs-lookup"><span data-stu-id="3bd99-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="3bd99-116">Créez une source de données nommée **eCommerce**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="3bd99-117">Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="3bd99-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="3bd99-118">Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="3bd99-119">Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="3bd99-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="3bd99-120">**DateOfBirth** : date</span><span class="sxs-lookup"><span data-stu-id="3bd99-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="3bd99-121">**CreatedOn** : date/heure/fuseau</span><span class="sxs-lookup"><span data-stu-id="3bd99-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformez la date de naissance en date.":::

5. <span data-ttu-id="3bd99-123">Dans le champ « Nom » du volet droit, renommez votre source de données **Requête** en **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="3bd99-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="3bd99-124">**Enregistrez** la source de données.</span><span class="sxs-lookup"><span data-stu-id="3bd99-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="3bd99-125">Ingérer les données d’achat en ligne</span><span class="sxs-lookup"><span data-stu-id="3bd99-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="3bd99-126">Ajoutez un autre ensemble de données à la même source de données **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="3bd99-127">Choisissez à nouveau le connecteur **Texte/CSV**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="3bd99-128">Entrez l’URL des données **d’achats en ligne** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="3bd99-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="3bd99-129">Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="3bd99-130">Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="3bd99-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="3bd99-131">**PurchasedOn** : date/heure</span><span class="sxs-lookup"><span data-stu-id="3bd99-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="3bd99-132">**TotalPrice** : devise</span><span class="sxs-lookup"><span data-stu-id="3bd99-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="3bd99-133">Dans le champ **Nom** du volet latéral, renommez votre source de données **Requête** en **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="3bd99-134">**Enregistrez** la source de données.</span><span class="sxs-lookup"><span data-stu-id="3bd99-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="3bd99-135">Ingérer les données client du programme de fidélité</span><span class="sxs-lookup"><span data-stu-id="3bd99-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="3bd99-136">Créez une source de données nommée **LoyaltyScheme**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="3bd99-137">Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="3bd99-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="3bd99-138">Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="3bd99-139">Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="3bd99-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="3bd99-140">**DateOfBirth** : date</span><span class="sxs-lookup"><span data-stu-id="3bd99-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="3bd99-141">**RewardsPoints** : nombre entier</span><span class="sxs-lookup"><span data-stu-id="3bd99-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="3bd99-142">**CreatedOn** : date/heure</span><span class="sxs-lookup"><span data-stu-id="3bd99-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="3bd99-143">Dans le champ **Nom** du volet droit, renommez votre source de données **Requête** en **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="3bd99-144">**Enregistrez** la source de données.</span><span class="sxs-lookup"><span data-stu-id="3bd99-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="3bd99-145">Tâche 2 : unification des données</span><span class="sxs-lookup"><span data-stu-id="3bd99-145">Task 2 - Data unification</span></span>

<span data-ttu-id="3bd99-146">Après avoir ingéré les données, nous commençons maintenant le processus d'unification des données pour créer un profil client unifié.</span><span class="sxs-lookup"><span data-stu-id="3bd99-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="3bd99-147">Pour plus d’informations, consultez [Unification des données](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="3bd99-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="3bd99-148">Mappage</span><span class="sxs-lookup"><span data-stu-id="3bd99-148">Map</span></span>

1. <span data-ttu-id="3bd99-149">Une fois les données ingérées, mappez les contacts des données d’eCommerce et du programme de fidélité aux types de données courants.</span><span class="sxs-lookup"><span data-stu-id="3bd99-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="3bd99-150">Accédez à **Données** > **Unifier** > **Mettre en correspondance**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="3bd99-151">Sélectionnez les entités qui représentent le profil client : **eCommerceContacts** et **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![Unifiez les sources de données d’eCommerce et du programme de fidélité.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="3bd99-153">Sélectionnez **ContactId** comme clé primaire pour **eCommerceContacts** et **LoyaltyID** comme clé primaire pour **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unifiez LoyaltyId comme clé primaire.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="3bd99-155">Correspondance</span><span class="sxs-lookup"><span data-stu-id="3bd99-155">Match</span></span>

1. <span data-ttu-id="3bd99-156">Accédez à l’onglet **Mettre en correspondance** et sélectionnez **Définir l’ordre**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="3bd99-157">Dans la liste déroulante **Principal**, choisissez **eCommerceContacts : eCommerce** comme source principale et incluez tous les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="3bd99-157">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="3bd99-158">Dans la liste déroulante **Entité 2**, choisissez **loyCustomers : LoyaltyScheme** et incluez tous les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="3bd99-158">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Unifiez l’ordre de mise en correspondance des données d’eCommerce et du programme de fidélité.](media/unify-match-order.png)

4. <span data-ttu-id="3bd99-160">Sélectionnez **Créer une nouvelle règle**</span><span class="sxs-lookup"><span data-stu-id="3bd99-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="3bd99-161">Ajoutez votre première condition en utilisant FullName.</span><span class="sxs-lookup"><span data-stu-id="3bd99-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="3bd99-162">Pour eCommerceContacts, sélectionnez **FullName** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="3bd99-162">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="3bd99-163">Pour loyCustomers, sélectionnez **FullName** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="3bd99-163">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="3bd99-164">Sélectionnez la liste déroulante **Normaliser** et choisissez **Type (téléphone, nom, adresse, ...)**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="3bd99-165">Définissez le **Niveau de précision** sur **Base** et la **Valeur** sur **Élevé**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="3bd99-166">Saisissez le nom **FullName, Email** pour la nouvelle règle.</span><span class="sxs-lookup"><span data-stu-id="3bd99-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="3bd99-167">Ajoutez une deuxième condition pour l’adresse e-mail en sélectionnant **Ajouter une condition**</span><span class="sxs-lookup"><span data-stu-id="3bd99-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="3bd99-168">Pour l’entité eCommerceContacts, choisissez **E-mail** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="3bd99-168">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="3bd99-169">Pour l’entité loyCustomers, choisissez **E-mail** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="3bd99-169">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="3bd99-170">Laissez le champ Normaliser vide.</span><span class="sxs-lookup"><span data-stu-id="3bd99-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="3bd99-171">Définissez le **Niveau de précision** sur **Base** et la **Valeur** sur **Élevé**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Unifiez la règle de mise en correspondance pour le nom et l’adresse e-mail.](media/unify-match-rule.png)

7. <span data-ttu-id="3bd99-173">Sélectionnez **Enregistrer** et **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="3bd99-174">Fusionner</span><span class="sxs-lookup"><span data-stu-id="3bd99-174">Merge</span></span>

1. <span data-ttu-id="3bd99-175">Accédez à l’onglet **Fusionner**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="3bd99-176">Dans le champ **ContactId** de l’entité **loyCustomers**, modifiez le nom d’affichage en **ContactIdLOYALTY** pour le différencier des autres ID ingérés.</span><span class="sxs-lookup"><span data-stu-id="3bd99-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Renommez contactid à partir de l’ID du programme de fidélité.](media/unify-merge-contactid.png)

1. <span data-ttu-id="3bd99-178">Sélectionnez **Enregistrer** et **Exécuter** pour démarrer le processus de fusion.</span><span class="sxs-lookup"><span data-stu-id="3bd99-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="3bd99-179">Tâche 3 – Configurer la recommandation de produit prédiction</span><span class="sxs-lookup"><span data-stu-id="3bd99-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="3bd99-180">Une fois les profils clients unifiés en place, nous pouvons maintenant exécuter la prédiction de l’attrition des abonnements.</span><span class="sxs-lookup"><span data-stu-id="3bd99-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="3bd99-181">Aller à **Intelligence** > **Prédiction**, choisir **Recommandation de produit**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="3bd99-182">Cliquez sur **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-182">Select **Get started**.</span></span>

1. <span data-ttu-id="3bd99-183">Nommez le modèle **Modèle de recommandation de produit prédéfinis prédiction** et l’entité de sortie **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="3bd99-184">Définissez trois conditions pour le modèle :</span><span class="sxs-lookup"><span data-stu-id="3bd99-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="3bd99-185">**Nombre de produits** : Définissez cette valeur sur **5**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="3bd99-186">Ce paramètre définit le nombre de produits que vous souhaitez recommander à vos clients.</span><span class="sxs-lookup"><span data-stu-id="3bd99-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="3bd99-187">**Achats répétés attendus** : Sélectionnez **Oui** pour indiquer que vous souhaitez inclure dans la recommandation des produits que vos clients ont déjà achetés.</span><span class="sxs-lookup"><span data-stu-id="3bd99-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="3bd99-188">**Fenêtre de consultation :** Sélectionnez au moins **365 jours**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="3bd99-189">Ce paramètre définit la consultation de l’activité du client à utiliser comme entrée dans les recommandations.</span><span class="sxs-lookup"><span data-stu-id="3bd99-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Préférences de modèle pour le modèle de recommandation de produit.":::

1. <span data-ttu-id="3bd99-191">Sélectionnez **Données requises** et sélectionnez **Ajouter des données** pour l’historique des achats.</span><span class="sxs-lookup"><span data-stu-id="3bd99-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="3bd99-192">Ajoutez l’entité **eCommercePurchases : eCommerce** et mappez les champs d’eCommerce aux champs correspondants requis par le modèle.</span><span class="sxs-lookup"><span data-stu-id="3bd99-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="3bd99-193">Associez l’entité **eCommercePurchases : eCommerce** à **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Associez les entités d’eCommerce.](media/model-purchase-join.png)

1. <span data-ttu-id="3bd99-195">Sélectionnez **Suivant** pour définir la planification du modèle.</span><span class="sxs-lookup"><span data-stu-id="3bd99-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="3bd99-196">Le modèle doit s’entraîner régulièrement à apprendre de nouveaux modèles lorsque de nouvelles données sont ingérées.</span><span class="sxs-lookup"><span data-stu-id="3bd99-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="3bd99-197">Dans cet exemple, sélectionnez **Mensuel**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="3bd99-198">Une fois tous les détails passés en revue, sélectionnez **Enregistrer et exécuter**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="3bd99-199">Tâche 4 : passer en revue les résultats et les explications du modèle</span><span class="sxs-lookup"><span data-stu-id="3bd99-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="3bd99-200">Laissez le modèle terminer la formation et la notation des données.</span><span class="sxs-lookup"><span data-stu-id="3bd99-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="3bd99-201">Vous pouvez maintenant passer en revue les explications du modèle recommandation de produit.</span><span class="sxs-lookup"><span data-stu-id="3bd99-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="3bd99-202">Pour plus d’informations, consultez [Passer en revue le statut et les résultats d’une prédiction](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="3bd99-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="3bd99-203">Tâche 5 – Créer un segment de produits très achetés</span><span class="sxs-lookup"><span data-stu-id="3bd99-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="3bd99-204">L’exécution du modèle de production crée une nouvelle entité que vous pouvez voir dans **Données** > **Entités**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="3bd99-205">Vous pouvez créer un nouveau segment basé sur l’entité créée par le modèle.</span><span class="sxs-lookup"><span data-stu-id="3bd99-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="3bd99-206">Accédez à **Segments**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-206">Go to **Segments**.</span></span> <span data-ttu-id="3bd99-207">Sélectionnez **Nouveau** et choisissez **Créer à partir de** > **Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="3bd99-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Création d’un segment avec la sortie du modèle.](media/segment-intelligence.png)

1. <span data-ttu-id="3bd99-209">Sélectionnez le point de terminaison **OOBProductRecommendationModelPrediction** et définissez le segment :</span><span class="sxs-lookup"><span data-stu-id="3bd99-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="3bd99-210">Champ : ProductID</span><span class="sxs-lookup"><span data-stu-id="3bd99-210">Field: ProductID</span></span>
   - <span data-ttu-id="3bd99-211">Opérateur : Valeur</span><span class="sxs-lookup"><span data-stu-id="3bd99-211">Operator: Value</span></span>
   - <span data-ttu-id="3bd99-212">Valeur : Sélectionnez les trois premiers ID de produit</span><span class="sxs-lookup"><span data-stu-id="3bd99-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Créez un segment à partir des résultats du modèle.":::

<span data-ttu-id="3bd99-214">Vous disposez désormais d’un segment mis à jour dynamiquement qui identifie les clients les plus disposés à acheter les trois produits les plus recommandés</span><span class="sxs-lookup"><span data-stu-id="3bd99-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="3bd99-215">Pour plus d’informations, consultez [Créer et gérer les segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="3bd99-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
