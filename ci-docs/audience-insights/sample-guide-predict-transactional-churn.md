---
title: Exemple de guide de prédiction de l’attrition transactionnelle
description: Utilisez cet exemple de guide pour essayer le modèle de prédiction de l’attrition transactionnelle prédéfini.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 251bc26246cee16952e8e4cb08e2ed7aa4d18488
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595423"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="04eac-103">Exemple de guide de prédiction de l’attrition transactionnelle (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="04eac-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="04eac-104">Ce guide vous présentera un exemple de bout en bout de prédiction de l’attrition transactionnelle dans Customer Insights en utilisant les données fournies ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="04eac-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="04eac-105">Toutes les données utilisées dans ce guide ne sont pas des données client réelles et font partie de l’ensemble de données de Contoso disponibles dans l’environnement de *Démonstration* de votre abonnement Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="04eac-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="04eac-106">Scénario</span><span class="sxs-lookup"><span data-stu-id="04eac-106">Scenario</span></span>

<span data-ttu-id="04eac-107">Contoso est une société qui produit du café et des machines à café de haute qualité qu’elle vend sur son site web Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="04eac-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="04eac-108">Son objectif est de savoir quels clients qui achètent régulièrement ses produits, cesseront d’être des clients actifs au cours des 60 prochains jours.</span><span class="sxs-lookup"><span data-stu-id="04eac-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="04eac-109">Savoir lesquels de ses clients **sont susceptibles de se tourner vers la concurrence**, peut l’aider à économiser ses efforts marketing en se concentrant sur leur fidélisation.</span><span class="sxs-lookup"><span data-stu-id="04eac-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="04eac-110">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="04eac-110">Prerequisites</span></span>

- <span data-ttu-id="04eac-111">Au minimum [Autorisations collaborateur](permissions.md) dans Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="04eac-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="04eac-112">Nous vous recommandons de mettre en œuvre les étapes suivantes [dans un nouvel environnement](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="04eac-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="04eac-113">Tâche 1 : ingérer les données</span><span class="sxs-lookup"><span data-stu-id="04eac-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="04eac-114">Passez en revue les articles sur [l’ingestion de données](data-sources.md) et [l’importation de sources de données à l’aide des connecteurs Power Query](connect-power-query.md) en particulier.</span><span class="sxs-lookup"><span data-stu-id="04eac-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="04eac-115">Les informations suivantes supposent que vous vous êtes familiarisé avec l’ingestion de données en général.</span><span class="sxs-lookup"><span data-stu-id="04eac-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="04eac-116">Ingérer les données client d’une plateforme d’eCommerce</span><span class="sxs-lookup"><span data-stu-id="04eac-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="04eac-117">Créez une source de données nommée **eCommerce**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.</span><span class="sxs-lookup"><span data-stu-id="04eac-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="04eac-118">Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="04eac-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="04eac-119">Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.</span><span class="sxs-lookup"><span data-stu-id="04eac-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="04eac-120">Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="04eac-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="04eac-121">**DateOfBirth** : date</span><span class="sxs-lookup"><span data-stu-id="04eac-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="04eac-122">**CreatedOn** : date/heure/fuseau</span><span class="sxs-lookup"><span data-stu-id="04eac-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="04eac-123">![Transformer la date de naissance en date](media/ecommerce-dob-date.PNG "transformer la date de naissance en date")</span><span class="sxs-lookup"><span data-stu-id="04eac-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="04eac-124">Dans le champ **Nom** du volet droit, renommez votre source de données **Requête** en **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="04eac-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="04eac-125">Enregistrez la source de données.</span><span class="sxs-lookup"><span data-stu-id="04eac-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="04eac-126">Ingérer les données d’achat en ligne</span><span class="sxs-lookup"><span data-stu-id="04eac-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="04eac-127">Ajoutez un autre ensemble de données à la même source de données **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="04eac-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="04eac-128">Choisissez à nouveau le connecteur **Texte/CSV**.</span><span class="sxs-lookup"><span data-stu-id="04eac-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="04eac-129">Entrez l’URL des données **d’achats en ligne** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="04eac-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="04eac-130">Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.</span><span class="sxs-lookup"><span data-stu-id="04eac-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="04eac-131">Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="04eac-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="04eac-132">**PurchasedOn** : date/heure</span><span class="sxs-lookup"><span data-stu-id="04eac-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="04eac-133">**TotalPrice** : devise</span><span class="sxs-lookup"><span data-stu-id="04eac-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="04eac-134">Dans le champ **Nom** du volet droit, renommez votre source de données **Requête** en **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="04eac-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="04eac-135">Enregistrez la source de données.</span><span class="sxs-lookup"><span data-stu-id="04eac-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="04eac-136">Ingérer les données client du programme de fidélité</span><span class="sxs-lookup"><span data-stu-id="04eac-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="04eac-137">Créez une source de données nommée **LoyaltyScheme**, choisissez l’option d’importation et sélectionnez le connecteur **Texte/CSV**.</span><span class="sxs-lookup"><span data-stu-id="04eac-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="04eac-138">Entrez l’URL des contacts d’eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="04eac-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="04eac-139">Lors de la modification des données, sélectionnez **Transformer**, puis **Utiliser la première ligne pour les en-têtes**.</span><span class="sxs-lookup"><span data-stu-id="04eac-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="04eac-140">Mettez à jour le type de données pour les colonnes répertoriées ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="04eac-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="04eac-141">**DateOfBirth** : date</span><span class="sxs-lookup"><span data-stu-id="04eac-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="04eac-142">**RewardsPoints** : nombre entier</span><span class="sxs-lookup"><span data-stu-id="04eac-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="04eac-143">**CreatedOn** : date/heure</span><span class="sxs-lookup"><span data-stu-id="04eac-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="04eac-144">Dans le champ **Nom** du volet droit, renommez votre source de données **Requête** en **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="04eac-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="04eac-145">Enregistrez la source de données.</span><span class="sxs-lookup"><span data-stu-id="04eac-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="04eac-146">Tâche 2 : unification des données</span><span class="sxs-lookup"><span data-stu-id="04eac-146">Task 2 - Data unification</span></span>

<span data-ttu-id="04eac-147">Une fois les données ingérées, nous commençons maintenant le processus de **Mappage, correspondance, fusion** pour créer un profil client unifié.</span><span class="sxs-lookup"><span data-stu-id="04eac-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="04eac-148">Pour plus d’informations, consultez [Unification des données](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="04eac-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="04eac-149">Mappage</span><span class="sxs-lookup"><span data-stu-id="04eac-149">Map</span></span>

1. <span data-ttu-id="04eac-150">Une fois les données ingérées, mappez les contacts des données d’eCommerce et du programme de fidélité aux types de données courants.</span><span class="sxs-lookup"><span data-stu-id="04eac-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="04eac-151">Accédez à **Données** > **Unifier** > **Mettre en correspondance**.</span><span class="sxs-lookup"><span data-stu-id="04eac-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="04eac-152">Sélectionnez les entités qui représentent le profil client : **eCommerceContacts** et **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="04eac-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Unifiez les sources de données d’eCommerce et du programme de fidélité.":::

1. <span data-ttu-id="04eac-154">Sélectionnez **ContactId** comme clé primaire pour **eCommerceContacts** et **LoyaltyID** comme clé primaire pour **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="04eac-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unifiez LoyaltyId comme clé primaire.":::

### <a name="match"></a><span data-ttu-id="04eac-156">Correspondance</span><span class="sxs-lookup"><span data-stu-id="04eac-156">Match</span></span>

1. <span data-ttu-id="04eac-157">Accédez à l’onglet **Mettre en correspondance** et sélectionnez **Définir l’ordre**.</span><span class="sxs-lookup"><span data-stu-id="04eac-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="04eac-158">Dans la liste déroulante **Primaire**, choisissez **eCommerceContacts : eCommerce** comme source principale et incluez tous les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="04eac-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="04eac-159">Dans la liste déroulante **Entité 2**, choisissez **loyCustomers : LoyaltyScheme** et incluez tous les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="04eac-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unifiez l’ordre de mise en correspondance des données d’eCommerce et du programme de fidélité.":::

1. <span data-ttu-id="04eac-161">Sélectionnez **Créer une nouvelle règle**</span><span class="sxs-lookup"><span data-stu-id="04eac-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="04eac-162">Ajoutez votre première condition en utilisant FullName.</span><span class="sxs-lookup"><span data-stu-id="04eac-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="04eac-163">Pour eCommerceContacts, sélectionnez **FullName** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="04eac-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="04eac-164">Pour loyCustomers, sélectionnez **FullName** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="04eac-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="04eac-165">Sélectionnez la liste déroulante **Normaliser** et choisissez **Type (téléphone, nom, adresse, ...)**.</span><span class="sxs-lookup"><span data-stu-id="04eac-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="04eac-166">Définissez le **Niveau de précision** sur **Base** et la **Valeur** sur **Élevé**.</span><span class="sxs-lookup"><span data-stu-id="04eac-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="04eac-167">Saisissez le nom **FullName, Email** pour la nouvelle règle.</span><span class="sxs-lookup"><span data-stu-id="04eac-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="04eac-168">Ajoutez une deuxième condition pour l’adresse e-mail en sélectionnant **Ajouter une condition**</span><span class="sxs-lookup"><span data-stu-id="04eac-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="04eac-169">Pour l’entité eCommerceContacts, choisissez **E-mail** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="04eac-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="04eac-170">Pour l’entité loyCustomers, choisissez **E-mail** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="04eac-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="04eac-171">Laissez le champ Normaliser vide.</span><span class="sxs-lookup"><span data-stu-id="04eac-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="04eac-172">Définissez le **Niveau de précision** sur **Base** et la **Valeur** sur **Élevé**.</span><span class="sxs-lookup"><span data-stu-id="04eac-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Unifiez la règle de mise en correspondance pour le nom et l’adresse e-mail.":::

7. <span data-ttu-id="04eac-174">Sélectionnez **Enregistrer** et **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="04eac-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="04eac-175">Fusionner</span><span class="sxs-lookup"><span data-stu-id="04eac-175">Merge</span></span>

1. <span data-ttu-id="04eac-176">Accédez à l’onglet **Fusionner**.</span><span class="sxs-lookup"><span data-stu-id="04eac-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="04eac-177">Dans le champ **ContactId** de l’entité **loyCustomers**, modifiez le nom d’affichage en **ContactIdLOYALTY** pour le différencier des autres ID ingérés.</span><span class="sxs-lookup"><span data-stu-id="04eac-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Renommez contactid à partir de l’ID du programme de fidélité.":::

1. <span data-ttu-id="04eac-179">Sélectionnez **Enregistrer** et **Exécuter** pour démarrer le processus de fusion.</span><span class="sxs-lookup"><span data-stu-id="04eac-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="04eac-180">Tâche 3 : configurer la prédiction de l’attrition des transactions</span><span class="sxs-lookup"><span data-stu-id="04eac-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="04eac-181">Une fois les profils clients unifiés en place, nous pouvons maintenant exécuter la prédiction de l’attrition des abonnements.</span><span class="sxs-lookup"><span data-stu-id="04eac-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="04eac-182">Pour connaître les étapes détaillées, consultez l’article [Prédiction de l’attrition des abonnements (version préliminaire)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="04eac-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="04eac-183">Accédez à **Intelligence** > **Découvrir** et choisissez le **Modèle d’attrition clients**.</span><span class="sxs-lookup"><span data-stu-id="04eac-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="04eac-184">Sélectionnez l’option **Transactionnel** et sélectionnez **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="04eac-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="04eac-185">Nommez le modèle **Prédiction de l’attrition des transactions d’eCommerce OOB** et l’entité de sortie **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="04eac-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="04eac-186">Définissez deux conditions pour le modèle d’attrition :</span><span class="sxs-lookup"><span data-stu-id="04eac-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="04eac-187">**Fenêtre de prédiction** : **au moins 60** jours.</span><span class="sxs-lookup"><span data-stu-id="04eac-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="04eac-188">Ce paramètre définit la période sur laquelle vous souhaitez prédire l’attrition clients.</span><span class="sxs-lookup"><span data-stu-id="04eac-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="04eac-189">**Définition de l’attrition** : **au moins 60** jours.</span><span class="sxs-lookup"><span data-stu-id="04eac-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="04eac-190">La durée sans achats après laquelle un client est considéré comme perdu.</span><span class="sxs-lookup"><span data-stu-id="04eac-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Sélectionnez la fenêtre de prédiction des leviers du modèle et la définition de l’attrition.":::

1. <span data-ttu-id="04eac-192">Sélectionnez **Historique des achats (requis)** et sélectionnez **Ajouter des données** pour l’historique des achats.</span><span class="sxs-lookup"><span data-stu-id="04eac-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="04eac-193">Ajoutez l’entité **eCommercePurchases : eCommerce** et mappez les champs d’eCommerce aux champs correspondants requis par le modèle.</span><span class="sxs-lookup"><span data-stu-id="04eac-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="04eac-194">Associez l’entité **eCommercePurchases : eCommerce** à **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="04eac-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Associez les entités d’eCommerce.":::

1. <span data-ttu-id="04eac-196">Sélectionnez **Suivant** pour définir la planification du modèle.</span><span class="sxs-lookup"><span data-stu-id="04eac-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="04eac-197">Le modèle doit s’entraîner régulièrement à apprendre de nouveaux modèles lorsque de nouvelles données sont ingérées.</span><span class="sxs-lookup"><span data-stu-id="04eac-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="04eac-198">Dans cet exemple, sélectionnez **Mensuel**.</span><span class="sxs-lookup"><span data-stu-id="04eac-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="04eac-199">Une fois tous les détails passés en revue, sélectionnez **Enregistrer et exécuter**.</span><span class="sxs-lookup"><span data-stu-id="04eac-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="04eac-200">Tâche 4 : passer en revue les résultats et les explications du modèle</span><span class="sxs-lookup"><span data-stu-id="04eac-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="04eac-201">Laissez le modèle terminer la formation et la notation des données.</span><span class="sxs-lookup"><span data-stu-id="04eac-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="04eac-202">Vous pouvez maintenant passer en revue les explications du modèle d’attrition des abonnements.</span><span class="sxs-lookup"><span data-stu-id="04eac-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="04eac-203">Pour plus d’informations, consultez [Passer en revue le statut et les résultats d’une prédiction](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="04eac-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="04eac-204">Tâche 5 : créer un segment de clients à haut risque d’attrition</span><span class="sxs-lookup"><span data-stu-id="04eac-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="04eac-205">L’exécution du modèle de production crée une nouvelle entité que vous pouvez voir dans **Données** > **Entités**.</span><span class="sxs-lookup"><span data-stu-id="04eac-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="04eac-206">Vous pouvez créer un nouveau segment basé sur l’entité créée par le modèle.</span><span class="sxs-lookup"><span data-stu-id="04eac-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="04eac-207">Accédez à **Segments**.</span><span class="sxs-lookup"><span data-stu-id="04eac-207">Go to **Segments**.</span></span> <span data-ttu-id="04eac-208">Sélectionnez **Nouveau** et choisissez **Créer à partir de** > **Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="04eac-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Création d’un segment avec la sortie du modèle.":::

1. <span data-ttu-id="04eac-210">Sélectionnez le point de terminaison **OOBSubscriptionChurnPrediction** et définissez le segment :</span><span class="sxs-lookup"><span data-stu-id="04eac-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="04eac-211">Champ : ChurnScore</span><span class="sxs-lookup"><span data-stu-id="04eac-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="04eac-212">Opérateur : supérieur à</span><span class="sxs-lookup"><span data-stu-id="04eac-212">Operator: greater than</span></span>
   - <span data-ttu-id="04eac-213">Valeur : 0,6</span><span class="sxs-lookup"><span data-stu-id="04eac-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configurez le segment d’attrition des abonnements.":::

<span data-ttu-id="04eac-215">Vous disposez maintenant d’un segment mis à jour de manière dynamique qui identifie les clients à haut risque d’attrition pour cette activité d’abonnement.</span><span class="sxs-lookup"><span data-stu-id="04eac-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="04eac-216">Pour plus d’informations, consultez [Créer et gérer les segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="04eac-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]