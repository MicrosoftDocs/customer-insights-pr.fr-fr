---
title: Segments suggérés basées sur l’activité.
description: Laissez le Machine Learning vous aider à trouver de nouveaux segments intéressants en fonction de l’activité des clients.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034069"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="80083-103">Segments suggérés basés sur les données d’activité (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="80083-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="80083-104">Découvrez des segments intéressants de vos clients en fonction des données d’activité client ingérées dans Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="80083-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="80083-105">Les transactions, la durée des appels au support, les achats ou les retours sont des exemples de données d’activité.</span><span class="sxs-lookup"><span data-stu-id="80083-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="80083-106">Pour suggérer des segments, la récence, la fréquence et la valeur monétaire (ou durée) des données d’activité sont analysées.</span><span class="sxs-lookup"><span data-stu-id="80083-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="80083-107">Vous pouvez également générer des [segments suggérés pour améliorer une mesure ou mieux comprendre ce qui influence un attribut](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="80083-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Onglet Segments suggérés affichant des suggestions de segments pour les segments basés sur l’activité et sur les attributs.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="80083-109">Catégoriser les clients par activité</span><span class="sxs-lookup"><span data-stu-id="80083-109">Categorize customers by activity</span></span>

<span data-ttu-id="80083-110">Avec les [données d’activité](activities.md) disponibles dans Customer Insights, nous pouvons générer des suggestions qui représentent des groupes de clients :</span><span class="sxs-lookup"><span data-stu-id="80083-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="80083-111">Les clients les plus actifs</span><span class="sxs-lookup"><span data-stu-id="80083-111">most active customers</span></span> 
- <span data-ttu-id="80083-112">Les clients qui ont effectué le plus d’achats</span><span class="sxs-lookup"><span data-stu-id="80083-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="80083-113">Les clients qui ont généré le plus de revenus</span><span class="sxs-lookup"><span data-stu-id="80083-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="80083-114">Les clients qui n’ont pas été actifs ces derniers temps</span><span class="sxs-lookup"><span data-stu-id="80083-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="80083-115">Les clients qui interagissent fréquemment avec votre entreprise</span><span class="sxs-lookup"><span data-stu-id="80083-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="80083-116">Si vous avez une entreprise de vente au détail, vous pouvez découvrir quels clients génèrent le plus de revenus et les récompenser avec un coupon.</span><span class="sxs-lookup"><span data-stu-id="80083-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="80083-117">Ou vous pouvez identifier des clients occasionnels et leur proposer de rejoindre un programme de récompenses afin qu’ils visitent votre entreprise plus souvent.</span><span class="sxs-lookup"><span data-stu-id="80083-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="80083-118">Si vous travaillez dans le secteur de la santé et que vous fournissez des soins de santé publics, votre objectif est de minimiser les dépenses pour les patients individuels.</span><span class="sxs-lookup"><span data-stu-id="80083-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="80083-119">Pour cela, vous pouvez réduire les visites récurrentes en offrant les meilleurs soins possibles en limitant le plus possible le nombre de visites.</span><span class="sxs-lookup"><span data-stu-id="80083-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="80083-120">Dans ce cas, votre objectif est de maintenir la fréquence des visites à un faible niveau et de minimiser les coûts récurrents pour les patients.</span><span class="sxs-lookup"><span data-stu-id="80083-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="80083-121">Ou vous pouvez identifier des segments de patients qui ont des rendez-vous fréquents et des coûts récurrents élevés, et analyser ces cas pour améliorer le traitement des individus.</span><span class="sxs-lookup"><span data-stu-id="80083-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="80083-122">Données requises</span><span class="sxs-lookup"><span data-stu-id="80083-122">Required data</span></span>

<span data-ttu-id="80083-123">Des suggestions sont générées en fonction des données d’entrée sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="80083-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="80083-124">Profils clients : tous les clients ou membres d’un segment spécifique.</span><span class="sxs-lookup"><span data-stu-id="80083-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="80083-125">Période : le mois dernier, l’année dernière ou tout délai d’exécution personnalisé.</span><span class="sxs-lookup"><span data-stu-id="80083-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="80083-126">Type d’activité : achats, transactions de détail, transactions en ligne, cas de support client, abonnements, etc.</span><span class="sxs-lookup"><span data-stu-id="80083-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="80083-127">Entité dans Customer Insights qui contient les données d’activité : l’entité UnifiedActivity ou l’entité pour une activité spécifique.</span><span class="sxs-lookup"><span data-stu-id="80083-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="80083-128">Dimensions à inclure : récence, fréquence ou dimension monétaire, en fonction des besoins de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="80083-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="80083-129">Générer des segments suggérés</span><span class="sxs-lookup"><span data-stu-id="80083-129">Generate suggested segments</span></span>

1. <span data-ttu-id="80083-130">Accédez à **Segments**.</span><span class="sxs-lookup"><span data-stu-id="80083-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="80083-131">Sélectionnez l’onglet **Suggestions (version préliminaire)**.</span><span class="sxs-lookup"><span data-stu-id="80083-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="80083-132">Sélectionnez **Rechercher de nouvelles suggestions** et choisissez **Afficher ou anticiper le comportement du client**.</span><span class="sxs-lookup"><span data-stu-id="80083-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="80083-133">Sélectionnez **Démarrer** pour exécuter l’expérience guidée.</span><span class="sxs-lookup"><span data-stu-id="80083-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Première étape de l’assistant de configuration pour un segment suggéré en fonction de l’activité.":::

1. <span data-ttu-id="80083-135">Fournissez les données d’entrée requises et sélectionnez **Suivant** pour poursuivre.</span><span class="sxs-lookup"><span data-stu-id="80083-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="80083-136">Choisissez les clients : incluez tous les clients ou un segment spécifique.</span><span class="sxs-lookup"><span data-stu-id="80083-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="80083-137">Choisissez l’activité : sélectionnez le type d’activité et les entités qui décrivent l’activité.</span><span class="sxs-lookup"><span data-stu-id="80083-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="80083-138">Préférences : définissez la période à prendre en compte, les facteurs de suggestions et mappez les attributs.</span><span class="sxs-lookup"><span data-stu-id="80083-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="80083-139">Passez en revue votre entrée et sélectionnez **Exécuter** pour exécuter le modèle et générer des suggestions.</span><span class="sxs-lookup"><span data-stu-id="80083-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="80083-140">En fonction du nombre de profils clients et des activités sélectionnées, cela peut prendre quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="80083-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="80083-141">Après avoir généré les suggestions, vous pouvez les filtrer en fonction de la dimension ou de la valeur qui vous intéresse le plus.</span><span class="sxs-lookup"><span data-stu-id="80083-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="80083-142">Afficher les détails d’un segment suggéré</span><span class="sxs-lookup"><span data-stu-id="80083-142">View details of a suggested segment</span></span>

<span data-ttu-id="80083-143">Une fois les suggestions générées, elles sont répertoriées dans **Segments** > **Suggestions (version préliminaire)** dans la section **Suggestions basées sur les activités**.</span><span class="sxs-lookup"><span data-stu-id="80083-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Volet latéral développé affichant les données détaillées d’un segment suggéré.":::

<span data-ttu-id="80083-145">Sélectionnez **Afficher la suggestion** sur un segment suggéré pour afficher les détails de ce segment.</span><span class="sxs-lookup"><span data-stu-id="80083-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="80083-146">Le volet latéral fournit des détails comme l’étendue de chaque dimension par rapport au groupe cible.</span><span class="sxs-lookup"><span data-stu-id="80083-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="80083-147">Il met également en évidence le nombre de membres potentiels dans le segment et le pourcentage correspondant du nombre total de clients.</span><span class="sxs-lookup"><span data-stu-id="80083-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="80083-148">Si vous souhaitez conserver la suggestion sous forme de segment, sélectionnez **Créer un segment**.</span><span class="sxs-lookup"><span data-stu-id="80083-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="80083-149">Enregistrer une suggestion en tant que segment</span><span class="sxs-lookup"><span data-stu-id="80083-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="80083-150">Aller à **Segments** > **Suggestions (aperçu)**.</span><span class="sxs-lookup"><span data-stu-id="80083-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="80083-151">Sélectionnez le segment à enregistrer.</span><span class="sxs-lookup"><span data-stu-id="80083-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="80083-152">Dans le volet latéral, sélectionnez **Créer un segment**.</span><span class="sxs-lookup"><span data-stu-id="80083-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="80083-153">Lorsque vous avez enregistré le segment, il s’affiche dans la liste des segments de l’onglet **Tous les segments**. Il peut alors être [actualisé ou supprimé comme n’importe quel autre segment](segments.md).</span><span class="sxs-lookup"><span data-stu-id="80083-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="80083-154">Vous ne pouvez pas modifier les détails du segment.</span><span class="sxs-lookup"><span data-stu-id="80083-154">You can't edit the segment details.</span></span> <span data-ttu-id="80083-155">Cependant, vous pouvez modifier les critères d’entrée des suggestions et générer différentes suggestions.</span><span class="sxs-lookup"><span data-stu-id="80083-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="80083-156">Actualiser ou modifier un ensemble de suggestions</span><span class="sxs-lookup"><span data-stu-id="80083-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="80083-157">Accédez à **Segments** > **Suggestions (version préliminaire)** et recherchez le segment dans la section **Suggestions basées sur les activités**.</span><span class="sxs-lookup"><span data-stu-id="80083-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="80083-158">Sélectionnez **Actualiser les suggestions** pour actualiser les suggestions tout en conservant les attributs configurés.</span><span class="sxs-lookup"><span data-stu-id="80083-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="80083-159">Ou sélectionnez **Modifier les suggestions** pour modifier les attributs configurés.</span><span class="sxs-lookup"><span data-stu-id="80083-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="80083-160">Le système réexécutera le processus, générera des suggestions de segment basées sur les dernières données et remplacera les suggestions actuelles.</span><span class="sxs-lookup"><span data-stu-id="80083-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
