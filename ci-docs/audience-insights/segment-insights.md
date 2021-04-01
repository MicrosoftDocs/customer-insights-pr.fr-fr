---
title: Informations sur les segments existants
description: Obtenez des informations sur les segments existants pour voir les différences et les points communs.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 90ebcaab896c628b04e751ad9857e924749895e7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595331"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="6428b-103">Aperçu des segments (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="6428b-103">Segment insights (preview)</span></span>

<span data-ttu-id="6428b-104">Découvrez des aperçus et des informations supplémentaires sur vos segments existants.</span><span class="sxs-lookup"><span data-stu-id="6428b-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="6428b-105">Découvrez ce qui différencie deux segments ou ce qu’ils ont en commun.</span><span class="sxs-lookup"><span data-stu-id="6428b-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="6428b-106">Chevauchement de segment</span><span class="sxs-lookup"><span data-stu-id="6428b-106">Segment overlap</span></span>

<span data-ttu-id="6428b-107">L’analyse de chevauchement des segments montre combien et quels clients sont communs à deux segments ou plus.</span><span class="sxs-lookup"><span data-stu-id="6428b-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="6428b-108">Par exemple, comment un segment de clients fréquents chevauche un segment qui contient des clients satisfaits de votre service ou produit.</span><span class="sxs-lookup"><span data-stu-id="6428b-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="6428b-109">Vous pouvez également analyser la façon dont le chevauchement change pour des attributs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6428b-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="6428b-110">Exécuter une analyse de chevauchement</span><span class="sxs-lookup"><span data-stu-id="6428b-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="6428b-111">Accédez à **Segments** et sélectionnez l’onglet **Insights (aperçu)**.</span><span class="sxs-lookup"><span data-stu-id="6428b-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="6428b-112">Sélectionnez **Nouveau** et choisissez l’option **Chevauchement** dans le volet **Choisir le type d’informations**.</span><span class="sxs-lookup"><span data-stu-id="6428b-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="6428b-113">Choisissez les segments d’intérêt et sélectionnez **Prochain**.</span><span class="sxs-lookup"><span data-stu-id="6428b-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="6428b-114">Facultativement, choisissez un ou plusieurs champs d’intérêt pour analyser les chevauchements pour chaque valeur de champ possible et sélectionnez **Prochain**.</span><span class="sxs-lookup"><span data-stu-id="6428b-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="6428b-115">Fournissez un nom pour votre analyse de chevauchement, un nom complet facultatif et une description.</span><span class="sxs-lookup"><span data-stu-id="6428b-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="6428b-116">Sélectionnez **Enregistrer** pour démarrer l’analyse.</span><span class="sxs-lookup"><span data-stu-id="6428b-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="6428b-117">L’analyse de chevauchement est prête lorsque le statut passe de Actualisation à Réussi.</span><span class="sxs-lookup"><span data-stu-id="6428b-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="6428b-118">Afficher et optimiser une analyse de chevauchement</span><span class="sxs-lookup"><span data-stu-id="6428b-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="6428b-119">Après avoir terminé l’analyse, trouvez des détails sur cet aperçu sur **Segments** > **Aperçu (version préliminaire)**.</span><span class="sxs-lookup"><span data-stu-id="6428b-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Détails des informations sur le chevauchement des segments":::

<span data-ttu-id="6428b-121">Sélectionnez un aperçu pour voir les résultats de l’analyse :</span><span class="sxs-lookup"><span data-stu-id="6428b-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="6428b-122">Nombre de membres chevauchant les segments sélectionnés pour l’analyse.</span><span class="sxs-lookup"><span data-stu-id="6428b-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="6428b-123">Le nombre de membres inclus dans l’un des segments, mais pas dans le reste des segments.</span><span class="sxs-lookup"><span data-stu-id="6428b-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="6428b-124">Si vous avez sélectionné des champs lors de la configuration de l’analyse de chevauchement, vous les trouverez dans les onglets correspondants.</span><span class="sxs-lookup"><span data-stu-id="6428b-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="6428b-125">Vous pouvez utiliser le menu déroulant du filtre pour sélectionner n’importe quel niveau d’attribut d’intérêt et le tableau en bas affichera les données correspondantes.</span><span class="sxs-lookup"><span data-stu-id="6428b-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="6428b-126">Facteurs de différenciation des segments</span><span class="sxs-lookup"><span data-stu-id="6428b-126">Segment differentiators</span></span>

<span data-ttu-id="6428b-127">Les différenciateurs de segments vous aident à découvrir ce qui différencie un segment du reste de vos clients ou d’un autre segment.</span><span class="sxs-lookup"><span data-stu-id="6428b-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="6428b-128">Il vous suffit de sélectionner un segment et le système identifie les attributs de profil et les mesures qui distinguent le segment sélectionné.</span><span class="sxs-lookup"><span data-stu-id="6428b-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="6428b-129">Exécuter une analyse de différenciation</span><span class="sxs-lookup"><span data-stu-id="6428b-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="6428b-130">Accédez à **Segments** et sélectionnez l’onglet **Insights (aperçu)**.</span><span class="sxs-lookup"><span data-stu-id="6428b-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="6428b-131">Sélectionnez **Nouveau** et choisissez l’option **Chevauchement** dans le volet **Choisir le type d’informations**.</span><span class="sxs-lookup"><span data-stu-id="6428b-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="6428b-132">Choisissez le segment que vous souhaitez analyser comme **Segment principal** et sélectionnez **Prochain**.</span><span class="sxs-lookup"><span data-stu-id="6428b-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="6428b-133">Choisissez **Tous les clients** ou un **Segment secondaire** pour comparer votre segment principal et sélectionnez **Prochain**.</span><span class="sxs-lookup"><span data-stu-id="6428b-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="6428b-134">Facultativement, choisissez un ou plusieurs champs d’intérêt pour concentrer l’analyse sur des attributs spécifiques et sélectionnez **Prochain**.</span><span class="sxs-lookup"><span data-stu-id="6428b-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="6428b-135">Fournissez un nom pour votre analyse de chevauchement, un nom complet facultatif et une description.</span><span class="sxs-lookup"><span data-stu-id="6428b-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="6428b-136">Sélectionnez **Enregistrer** pour démarrer l’analyse.</span><span class="sxs-lookup"><span data-stu-id="6428b-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="6428b-137">L’analyse de chevauchement est prête lorsque le statut passe de Actualisation à Réussi.</span><span class="sxs-lookup"><span data-stu-id="6428b-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="6428b-138">Afficher et optimiser une analyse des différenciateurs</span><span class="sxs-lookup"><span data-stu-id="6428b-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="6428b-139">Après avoir terminé l’analyse, trouvez des détails sur cet aperçu sur **Segments** > **Aperçu (version préliminaire)**.</span><span class="sxs-lookup"><span data-stu-id="6428b-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Détails des informations sur le différenciateur des segments":::

<span data-ttu-id="6428b-141">Sélectionnez un aperçu pour voir les résultats de l’analyse.</span><span class="sxs-lookup"><span data-stu-id="6428b-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="6428b-142">Une analyse du différentiateur comprend deux onglets.</span><span class="sxs-lookup"><span data-stu-id="6428b-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="6428b-143">L’onglet **Attributs** répertorie les attributs de profil considérés comme des différenciateurs.</span><span class="sxs-lookup"><span data-stu-id="6428b-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="6428b-144">L’onglet **Mesures** répertorie les différenciateurs.</span><span class="sxs-lookup"><span data-stu-id="6428b-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="6428b-145">Chaque onglet comprend les détails suivants :</span><span class="sxs-lookup"><span data-stu-id="6428b-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="6428b-146">Liste classée des différenciateurs, triée par score de différence.</span><span class="sxs-lookup"><span data-stu-id="6428b-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="6428b-147">Le **Score de différence** pour chaque différenciateur.</span><span class="sxs-lookup"><span data-stu-id="6428b-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="6428b-148">Le score de différence représente le degré de différence d’un attribut entre deux segments.</span><span class="sxs-lookup"><span data-stu-id="6428b-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="6428b-149">Plus le score de différence est élevé, plus les attributs diffèrent entre les deux segments.</span><span class="sxs-lookup"><span data-stu-id="6428b-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="6428b-150">Sélectionnez une partition pour ouvrir le volet **Score de différence** avec les distributions de valeurs pour cet attribut.</span><span class="sxs-lookup"><span data-stu-id="6428b-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="6428b-151">Gérer les informations du segment</span><span class="sxs-lookup"><span data-stu-id="6428b-151">Manage segment insights</span></span>

<span data-ttu-id="6428b-152">Vous pouvez utiliser les options suivantes sur vos informations à partir de la barre de commandes :</span><span class="sxs-lookup"><span data-stu-id="6428b-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="6428b-153">**Retour** pour revenir à la liste des informations</span><span class="sxs-lookup"><span data-stu-id="6428b-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="6428b-154">**Actualiser** pour exécuter à nouveau l’analyse</span><span class="sxs-lookup"><span data-stu-id="6428b-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="6428b-155">**Supprimer** pour supprimer cette idée</span><span class="sxs-lookup"><span data-stu-id="6428b-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]