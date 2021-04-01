---
title: Compléter des données partielles avec des prédictions
description: Utilisez des prédictions pour remplir des données client incomplètes.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3342328b9eead9bdcb8b41f119a1d0a5823001c8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595898"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="6d55e-103">Compléter vos données partielles avec des prédictions</span><span class="sxs-lookup"><span data-stu-id="6d55e-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="6d55e-104">Les prédictions vous permettent de créer facilement des valeurs prédites qui peuvent améliorer votre compréhension d’un client.</span><span class="sxs-lookup"><span data-stu-id="6d55e-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="6d55e-105">Sur la page **Intelligence** > **Prédictions**, vous pouvez sélectionner **Mes prédictions** pour voir les prédictions que vous avez configurées dans d’autres parties des informations sur l’audience, et les personnaliser davantage.</span><span class="sxs-lookup"><span data-stu-id="6d55e-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="6d55e-106">Vous ne pouvez pas utiliser cette fonctionnalité si votre environnement utilise le stockage Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="6d55e-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="6d55e-107">La fonctionnalité de prédictions utilise des moyens automatisés pour évaluer les données et faire des prédictions sur la base de ces données, et a donc la capacité d’être utilisée comme méthode de profilage, comme ce terme est défini par le Règlement général sur la protection des données (« RGPD »).</span><span class="sxs-lookup"><span data-stu-id="6d55e-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="6d55e-108">L’utilisation par le client de cette fonctionnalité pour traiter des données peut être soumise au RGPD ou à d’autres lois ou réglementations.</span><span class="sxs-lookup"><span data-stu-id="6d55e-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="6d55e-109">Vous êtes tenu de vous assurer que votre utilisation de Dynamics 365 Customer Insights, notamment les prédictions, est conforme à toutes les lois et réglementations applicables, notamment les lois relatives à la confidentialité, aux données personnelles, aux données biométriques, à la protection des données et à la confidentialité des communications.</span><span class="sxs-lookup"><span data-stu-id="6d55e-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6d55e-110">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="6d55e-110">Prerequisites</span></span>

<span data-ttu-id="6d55e-111">Avant que votre organisation ne puisse utiliser la fonction de prévisions, les conditions préalables suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="6d55e-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="6d55e-112">Votre organisation a une instance [configurée dans Common Data Service](/ai-builder/build-model#prerequisites) qui se trouve dans la même organisation que Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6d55e-112">Your organization has an instance [set up in the Common Data Service](/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="6d55e-113">Votre environnement est associé à votre instance Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6d55e-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="6d55e-114">Si vous [créez un environnement](manage-environments.md), configurez-le dans la boîte de dialogue **Créer un environnement** et sélectionnez **Avancée**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="6d55e-115">Si vous avez déjà créé un environnement, accédez à ses paramètres et sélectionnez **Avancés**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="6d55e-116">Dans les deux cas, dans la section **Utiliser des prédictions**, entrez l’URL de l’instance Common Data Service à laquelle vous souhaitez associer votre environnement.</span><span class="sxs-lookup"><span data-stu-id="6d55e-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="6d55e-117">Créer une prédiction dans l’entité Client</span><span class="sxs-lookup"><span data-stu-id="6d55e-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="6d55e-118">Dans les informations sur l’audience, accédez à **Données** > **Entités**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="6d55e-119">Sélectionnez l’entité **Client**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="6d55e-120">Dans l’entité **Client : CustomerInsights**, sélectionnez l’onglet **Champs**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="6d55e-121">Recherchez le nom d’attribut pour lequel vous souhaitez prédire des valeurs, puis sélectionnez l’icône **Aperçu** dans la colonne **Résumé**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6d55e-122">![Icône de présentation](media/intelligence-overviewicon.png "Icône de présentation")</span><span class="sxs-lookup"><span data-stu-id="6d55e-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="6d55e-123">S’il y a un taux élevé de valeurs manquantes pour votre attribut, sélectionnez **Prédire les valeurs manquantes** pour continuer votre prédiction.</span><span class="sxs-lookup"><span data-stu-id="6d55e-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6d55e-124">![Aperçu du statut avec bouton de prédiction des valeurs manquantes affiché](media/intelligence-overviewpredictmissingvalues.png "Aperçu du statut avec bouton de prédiction des valeurs manquantes affiché")</span><span class="sxs-lookup"><span data-stu-id="6d55e-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="6d55e-125">Fournissez un **nom complet** et un **Nom d’entité de sortie** pour les résultats de la prédiction.</span><span class="sxs-lookup"><span data-stu-id="6d55e-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="6d55e-126">Une liste d’options préremplie indique où vous pouvez mapper les valeurs à une catégorie prédite.</span><span class="sxs-lookup"><span data-stu-id="6d55e-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="6d55e-127">Dans ce cas, vos seules options de catégorie seront 0 ou 1, car elles correspondent à la nature vraie/fausse ou binaire de la prédiction.</span><span class="sxs-lookup"><span data-stu-id="6d55e-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="6d55e-128">Dans la colonne Catégorie, mappez les valeurs de champ que vous souhaitez classer comme « 0 » dans la prédiction finale à « 0 » et les éléments que vous souhaitez classer comme « 1 » dans la prédiction finale à « 1 ».</span><span class="sxs-lookup"><span data-stu-id="6d55e-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6d55e-129">![Exemple montrant des valeurs de champ mappées à des catégories](media/intelligence-categorymapping.png "Exemple montrant des valeurs de champ mappées à des catégories")</span><span class="sxs-lookup"><span data-stu-id="6d55e-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="6d55e-130">Sélectionnez **Terminé** et la prédiction sera traitée.</span><span class="sxs-lookup"><span data-stu-id="6d55e-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="6d55e-131">Le traitement prendra un certain temps, selon la taille et la complexité des données.</span><span class="sxs-lookup"><span data-stu-id="6d55e-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="6d55e-132">Les résultats seront disponibles dans une nouvelle entité basée sur la prédiction **Nom de l’entité de sortie** que vous avez créée.</span><span class="sxs-lookup"><span data-stu-id="6d55e-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="6d55e-133">Créer une prédiction tout en créant un segment</span><span class="sxs-lookup"><span data-stu-id="6d55e-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="6d55e-134">La prédiction de valeurs manquantes pour un attribut spécifique de choix est également possible lors de la création d’un segment.</span><span class="sxs-lookup"><span data-stu-id="6d55e-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="6d55e-135">Plus précisément, lorsque vous créez rapidement un segment en fonction de votre entité client unifiée ou de l’entité Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="6d55e-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="6d55e-136">Dans le cadre de ce flux, vous choisissez un attribut spécifique sur lequel baser votre segment, comme la satisfaction du client ou le montant de l’achat.</span><span class="sxs-lookup"><span data-stu-id="6d55e-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="6d55e-137">Lors de la création du segment, le système proposera une méthode pour prédire toute valeur manquante pour cet attribut.</span><span class="sxs-lookup"><span data-stu-id="6d55e-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="6d55e-138">Dans les informations sur l’audience, accédez à **Segments** et sélectionnez la vignette **Profils**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="6d55e-139">Choisissez un **champ** pour créer un segment et sélectionner un **Opérateur**, puis sélectionnez **Réviser**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="6d55e-140">Fournissez un **Nom** et un **Nom complet** pour le segment.</span><span class="sxs-lookup"><span data-stu-id="6d55e-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="6d55e-141">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-141">Select **Save**.</span></span>

5. <span data-ttu-id="6d55e-142">Si le segment que vous avez créé contient des données incomplètes dans le champ source, vous pouvez choisir de prédire les valeurs manquantes.</span><span class="sxs-lookup"><span data-stu-id="6d55e-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6d55e-143">![Bouton Prédiction](media/segments-predictoption.png "Bouton Prédiction")</span><span class="sxs-lookup"><span data-stu-id="6d55e-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="6d55e-144">Fournissez un **nom complet** et un **Nom d’entité de sortie** pour les résultats de la prédiction.</span><span class="sxs-lookup"><span data-stu-id="6d55e-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="6d55e-145">Sélectionnez **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-145">Select **Done**.</span></span> <span data-ttu-id="6d55e-146">Votre prédiction sera générée sous peu dans une nouvelle entité avec le nom que vous avez fourni pour le **Nom de l’entité de sortie**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="6d55e-147">Afficher une prédiction</span><span class="sxs-lookup"><span data-stu-id="6d55e-147">View a prediction</span></span>

1. <span data-ttu-id="6d55e-148">Dans les informations sur l’audience, accédez à **Intelligence** > **Prédictions** > **Mes prédictions**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="6d55e-149">Sélectionnez la prédiction à réviser.</span><span class="sxs-lookup"><span data-stu-id="6d55e-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="6d55e-150">Sélectionnez les points de suspension dans la colonne **Actions**, puis choisissez **Vue**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="6d55e-151">Vous verrez un certain nombre de points de données dans la vue de votre prédiction.</span><span class="sxs-lookup"><span data-stu-id="6d55e-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6d55e-152">![Page Prédictions](media/intelligence-predictionsviewpage.png "Page Prédictions")</span><span class="sxs-lookup"><span data-stu-id="6d55e-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="6d55e-153">**Valeurs prédites** affiche le mappage que vous avez créé pendant la phase de mappage de la valeur du champ à la catégorie.</span><span class="sxs-lookup"><span data-stu-id="6d55e-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="6d55e-154">Il s’agit des valeurs de votre jeu de données qui ont été mappées à une catégorie spécifique.</span><span class="sxs-lookup"><span data-stu-id="6d55e-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="6d55e-155">-**Principaux influenceurs** sont les facteurs au sein de votre jeu de données qui étaient les plus susceptibles d’influencer la confiance de la prédiction quant à la valeur de votre champ mappé à une catégorie spécifique.</span><span class="sxs-lookup"><span data-stu-id="6d55e-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="6d55e-156">**Performance** indique comment les prédictions se portent.</span><span class="sxs-lookup"><span data-stu-id="6d55e-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="6d55e-157">Sélectionnez le lien pour en savoir plus.</span><span class="sxs-lookup"><span data-stu-id="6d55e-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="6d55e-158">**Aperçu** montre des échantillons du jeu de données de sortie de votre prédiction et la probabilité, ou notre confiance, de la valeur prédite où 0 est incertain et 1 est certain.</span><span class="sxs-lookup"><span data-stu-id="6d55e-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="6d55e-159">Mettre à jour une prédiction</span><span class="sxs-lookup"><span data-stu-id="6d55e-159">Update a prediction</span></span>

1. <span data-ttu-id="6d55e-160">Dans les informations sur l’audience, accédez à **Intelligence** > **Prédictions** > **Mes prédictions**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="6d55e-161">Sélectionnez la prédiction que vous souhaitez mettre à jour et sélectionnez l’icône **Mise à jour**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="6d55e-162">La prédiction sera planifiée pour traitement.</span><span class="sxs-lookup"><span data-stu-id="6d55e-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="6d55e-163">Vous pouvez voir l’heure de sa dernière mise à jour dans la colonne **Mis à jour** de la page **Prédictions**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="6d55e-164">Modifier une prédiction</span><span class="sxs-lookup"><span data-stu-id="6d55e-164">Edit a prediction</span></span>

<span data-ttu-id="6d55e-165">Après avoir créé une prédiction, vous pouvez personnaliser le modèle dans AI Builder pour augmenter l’efficacité de votre modèle.</span><span class="sxs-lookup"><span data-stu-id="6d55e-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="6d55e-166">Dans les informations sur l’audience, accédez à **Intelligence** > **Prédictions** > **Mes prédictions**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="6d55e-167">Sélectionnez la prédiction que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="6d55e-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="6d55e-168">Sélectionnez les points de suspension dans la colonne **Actions**, puis choisissez **Vue**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="6d55e-169">Sélectionnez **Personnaliser dans AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="6d55e-170">Mettez à jour votre modèle dans AI Builder.</span><span class="sxs-lookup"><span data-stu-id="6d55e-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="6d55e-171">[En savoir plus sur la gestion des modèles dans AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="6d55e-171">[Learn more about managing models in the AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="6d55e-172">La prochaine exécution de votre prédiction utilisera le modèle mis à jour que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="6d55e-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="6d55e-173">Les nouveaux modèles créés dans AI Builder ne seront pas affichés dans les informations sur l’audience, sauf si le modèle a été créé à partir des expériences répertoriées ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="6d55e-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="6d55e-174">Supprimer une prédiction</span><span class="sxs-lookup"><span data-stu-id="6d55e-174">Remove a prediction</span></span>

1. <span data-ttu-id="6d55e-175">Dans les informations sur l’audience, accédez à **Intelligence** > **Prédictions** > **Mes prédictions**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="6d55e-176">Sélectionnez la prédiction à supprimer.</span><span class="sxs-lookup"><span data-stu-id="6d55e-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="6d55e-177">Sélectionnez les points de suspension dans la colonne **Actions**, puis choisissez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="6d55e-178">Confirmez la suppression.</span><span class="sxs-lookup"><span data-stu-id="6d55e-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="6d55e-179">Dépannage</span><span class="sxs-lookup"><span data-stu-id="6d55e-179">Troubleshooting</span></span>

<span data-ttu-id="6d55e-180">Si vous ne pouvez pas terminer le processus d’attachement Common Data Service en raison d’une erreur, vous pouvez essayer de terminer le processus manuellement.</span><span class="sxs-lookup"><span data-stu-id="6d55e-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="6d55e-181">Deux problèmes connus peuvent survenir dans le processus d’attachement :</span><span class="sxs-lookup"><span data-stu-id="6d55e-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="6d55e-182">La solution Complément de carte client n’est pas installée.</span><span class="sxs-lookup"><span data-stu-id="6d55e-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="6d55e-183">Suivez les instructions pour [installer et configurer la solution](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="6d55e-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="6d55e-184">Les autorisations de l’application ne sont pas accordées.</span><span class="sxs-lookup"><span data-stu-id="6d55e-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="6d55e-185">Accédez à [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="6d55e-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="6d55e-186">Sélectionnez **Environnements**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="6d55e-187">Sélectionnez les points de suspension en regard de l’environnement auquel vous souhaitez ajouter l’autorisation et sélectionnez **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="6d55e-188">Développez **Utilisateurs + autorisations** et sélectionnez **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="6d55e-189">Sélectionnez **+ Nouveau** et sélectionnez **Utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="6d55e-190">Sélectionnez **Utilisateur de l’application** s’il n’est pas déjà sélectionné et entrez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6d55e-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="6d55e-191">**Nom d’utilisateur :** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6d55e-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="6d55e-192">**ID d’application** : 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="6d55e-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="6d55e-193">**Prénom** : Client</span><span class="sxs-lookup"><span data-stu-id="6d55e-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="6d55e-194">**Nom** : Informations</span><span class="sxs-lookup"><span data-stu-id="6d55e-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="6d55e-195">**E-mail principal** : cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6d55e-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="6d55e-196">Cliquez sur **Enregistrer et fermer**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="6d55e-197">Sélectionnez l’utilisateur que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="6d55e-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="6d55e-198">Sélectionnez **Gérer les rôles** dans la barre de menus supérieure.</span><span class="sxs-lookup"><span data-stu-id="6d55e-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="6d55e-199">Sélectionnez **Administrateur système**, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d55e-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]