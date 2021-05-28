---
title: Fusionner des entités pour l’unification des données
description: Fusionnez des données pour créer des profils clients unifiés.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085573"
---
# <a name="merge-entities"></a><span data-ttu-id="18b3c-103">Fusionner des entités</span><span class="sxs-lookup"><span data-stu-id="18b3c-103">Merge entities</span></span>

<span data-ttu-id="18b3c-104">La fusion est la dernière phase du processus d’unification des données.</span><span class="sxs-lookup"><span data-stu-id="18b3c-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="18b3c-105">Son objectif consiste à rapprocher les données conflictuelles.</span><span class="sxs-lookup"><span data-stu-id="18b3c-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="18b3c-106">Des exemples de données en conflit sont le nom d’un client qui réside dans deux de vos jeux de données, avec une petite différence (« Martin Lucas » au lieu de « Martin »), ou un format de numéro de téléphone légèrement différent (06-78-03-09-1X et 067803091X).</span><span class="sxs-lookup"><span data-stu-id="18b3c-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="18b3c-107">Fusionner ces points de données en conflit s’effectue d’une manière attribut par attribut.</span><span class="sxs-lookup"><span data-stu-id="18b3c-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Page de fusion dans le processus d’unification des données affichant une table avec des champs fusionnés qui définissent le profil client unifié.":::

<span data-ttu-id="18b3c-109">Après avoir terminé la [phase de mise en correspondance](match-entities.md), vous pouvez entamer la phase de fusion en sélectionnant la vignette **Fusionner** sur la page **Unifier**.</span><span class="sxs-lookup"><span data-stu-id="18b3c-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="18b3c-110">Examiner les recommandations système</span><span class="sxs-lookup"><span data-stu-id="18b3c-110">Review system recommendations</span></span>

<span data-ttu-id="18b3c-111">Sur **Données** > **Unifier** > **Fusionner**, vous choisissez et excluez les attributs à fusionner au sein de votre entité de profil client unifiée.</span><span class="sxs-lookup"><span data-stu-id="18b3c-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="18b3c-112">Le profil client unifié est le résultat du processus d’unification des données.</span><span class="sxs-lookup"><span data-stu-id="18b3c-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="18b3c-113">Certains attributs sont automatiquement fusionnés par le système.</span><span class="sxs-lookup"><span data-stu-id="18b3c-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="18b3c-114">Pour afficher les attributs inclus dans l’un de vos attributs fusionnés automatiquement, sélectionnez cet attribut fusionné dans l’onglet **Champs client** de la table.</span><span class="sxs-lookup"><span data-stu-id="18b3c-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="18b3c-115">Les attributs qui composent cet attribut fusionné s’affichent dans deux nouvelles lignes en dessous de l’attribut fusionné.</span><span class="sxs-lookup"><span data-stu-id="18b3c-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="18b3c-116">Séparer, renommer, exclure et modifier les champs fusionnés</span><span class="sxs-lookup"><span data-stu-id="18b3c-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="18b3c-117">Vous pouvez modifier la façon dont le système traite les attributs fusionnés pour générer le profil client unifié.</span><span class="sxs-lookup"><span data-stu-id="18b3c-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="18b3c-118">Sélectionnez **Afficher plus** et choisissez ce que vous voulez changer.</span><span class="sxs-lookup"><span data-stu-id="18b3c-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Options du menu déroulant Afficher plus pour gérer les attributs fusionnés.":::

<span data-ttu-id="18b3c-120">Pour plus d’informations, consultez les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="18b3c-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="18b3c-121">Champs fusionnés séparés</span><span class="sxs-lookup"><span data-stu-id="18b3c-121">Separate merged fields</span></span>

<span data-ttu-id="18b3c-122">Pour séparer des champs fusionnés, recherchez l’attribut dans la table.</span><span class="sxs-lookup"><span data-stu-id="18b3c-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="18b3c-123">Les champs séparés s’affichent sous forme de points de données individuels sur le profil client unifié.</span><span class="sxs-lookup"><span data-stu-id="18b3c-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="18b3c-124">Sélectionnez le champ fusionné.</span><span class="sxs-lookup"><span data-stu-id="18b3c-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="18b3c-125">Sélectionnez **Afficher plus** et choisissez **Séparer les champs**.</span><span class="sxs-lookup"><span data-stu-id="18b3c-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="18b3c-126">Confirmez la séparation.</span><span class="sxs-lookup"><span data-stu-id="18b3c-126">Confirm the separation.</span></span>

1. <span data-ttu-id="18b3c-127">Cliquez sur **Enregistrer**, puis sur **Exécuter** pour traiter les modifications.</span><span class="sxs-lookup"><span data-stu-id="18b3c-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="18b3c-128">Renommer les champs fusionnés</span><span class="sxs-lookup"><span data-stu-id="18b3c-128">Rename merged fields</span></span>

<span data-ttu-id="18b3c-129">Modifiez le nom d’affichage des attributs fusionnés.</span><span class="sxs-lookup"><span data-stu-id="18b3c-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="18b3c-130">Vous ne pouvez pas modifier le nom de l’entité de sortie.</span><span class="sxs-lookup"><span data-stu-id="18b3c-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="18b3c-131">Sélectionnez le champ fusionné.</span><span class="sxs-lookup"><span data-stu-id="18b3c-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="18b3c-132">Sélectionnez **Afficher plus** et choisissez **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="18b3c-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="18b3c-133">Confirmez le nom d’affichage modifié.</span><span class="sxs-lookup"><span data-stu-id="18b3c-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="18b3c-134">Cliquez sur **Enregistrer**, puis sur **Exécuter** pour traiter les modifications.</span><span class="sxs-lookup"><span data-stu-id="18b3c-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="18b3c-135">Exclure les champs fusionnés</span><span class="sxs-lookup"><span data-stu-id="18b3c-135">Exclude merged fields</span></span>

<span data-ttu-id="18b3c-136">Excluez un attribut du profil client unifié.</span><span class="sxs-lookup"><span data-stu-id="18b3c-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="18b3c-137">Si le champ est utilisé dans d’autres processus, par exemple dans un segment, supprimez-le de ces processus avant de l’exclure du profil client.</span><span class="sxs-lookup"><span data-stu-id="18b3c-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="18b3c-138">Sélectionnez le champ fusionné.</span><span class="sxs-lookup"><span data-stu-id="18b3c-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="18b3c-139">Sélectionnez **Afficher plus** et choisissez **Exclure**.</span><span class="sxs-lookup"><span data-stu-id="18b3c-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="18b3c-140">Confirmez l’exclusion.</span><span class="sxs-lookup"><span data-stu-id="18b3c-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="18b3c-141">Cliquez sur **Enregistrer**, puis sur **Exécuter** pour traiter les modifications.</span><span class="sxs-lookup"><span data-stu-id="18b3c-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="18b3c-142">Sur la page **Fusionner**, sélectionnez **Champs exclus** pour voir la liste de tous les champs exclus.</span><span class="sxs-lookup"><span data-stu-id="18b3c-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="18b3c-143">Ce volet vous permet d’ajouter à nouveau des champs exclus.</span><span class="sxs-lookup"><span data-stu-id="18b3c-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="18b3c-144">Combiner manuellement des champs</span><span class="sxs-lookup"><span data-stu-id="18b3c-144">Manually combine fields</span></span>

<span data-ttu-id="18b3c-145">Spécifiez un attribut fusionné manuellement.</span><span class="sxs-lookup"><span data-stu-id="18b3c-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="18b3c-146">Sur la page **Fusionner**, sélectionnez **Combiner les champs**.</span><span class="sxs-lookup"><span data-stu-id="18b3c-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="18b3c-147">Fournissez un **Nom** et un **Nom du champ de sortie**.</span><span class="sxs-lookup"><span data-stu-id="18b3c-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="18b3c-148">Choisissez un champ à ajouter.</span><span class="sxs-lookup"><span data-stu-id="18b3c-148">Choose a field to add.</span></span> <span data-ttu-id="18b3c-149">Sélectionnez **Ajouter des champs** pour combiner plus de champs.</span><span class="sxs-lookup"><span data-stu-id="18b3c-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="18b3c-150">Confirmez l’exclusion.</span><span class="sxs-lookup"><span data-stu-id="18b3c-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="18b3c-151">Cliquez sur **Enregistrer**, puis sur **Exécuter** pour traiter les modifications.</span><span class="sxs-lookup"><span data-stu-id="18b3c-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="18b3c-152">Modifier l’ordre des champs</span><span class="sxs-lookup"><span data-stu-id="18b3c-152">Change the order of fields</span></span>

<span data-ttu-id="18b3c-153">Certaines entités contiennent plus de détails que d’autres.</span><span class="sxs-lookup"><span data-stu-id="18b3c-153">Some entities contain more details than others.</span></span> <span data-ttu-id="18b3c-154">Si une entité inclut les dernières données concernant un champ, vous pouvez lui donner priorité par rapport aux autres entités lors de la fusion des valeurs.</span><span class="sxs-lookup"><span data-stu-id="18b3c-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="18b3c-155">Sélectionnez le champ fusionné.</span><span class="sxs-lookup"><span data-stu-id="18b3c-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="18b3c-156">Sélectionnez **Afficher plus** et choisissez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="18b3c-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="18b3c-157">Dans le volet **Combiner des champs**, sélectionnez **Monter/descendre** pour définir l’ordre ou faites-les glisser et déposez-les dans la position souhaitée.</span><span class="sxs-lookup"><span data-stu-id="18b3c-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="18b3c-158">Confirmez la modification.</span><span class="sxs-lookup"><span data-stu-id="18b3c-158">Confirm the change.</span></span>

1. <span data-ttu-id="18b3c-159">Cliquez sur **Enregistrer**, puis sur **Exécuter** pour traiter les modifications.</span><span class="sxs-lookup"><span data-stu-id="18b3c-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="18b3c-160">Exécuter la fusion</span><span class="sxs-lookup"><span data-stu-id="18b3c-160">Run your merge</span></span>

<span data-ttu-id="18b3c-161">Que vous fusionniez manuellement les attributs ou laissiez le système le faire pour vous, à ce stade vous pouvez toujours exécuter votre fusion.</span><span class="sxs-lookup"><span data-stu-id="18b3c-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="18b3c-162">Sélectionnez **Exécuter** sur la page **Fusionner** pour démarrer le processus.</span><span class="sxs-lookup"><span data-stu-id="18b3c-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="18b3c-163">![Fusion des données - Enregistrer et exécuter](media/configure-data-merge-save-run.png "Fusion des données - Enregistrer et exécuter")</span><span class="sxs-lookup"><span data-stu-id="18b3c-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="18b3c-164">Choisissez **Exécuter uniquement une fusion** si vous souhaitez uniquement voir la sortie reflétée dans l’entité client unifiée.</span><span class="sxs-lookup"><span data-stu-id="18b3c-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="18b3c-165">Les processus en aval seront actualisés comme [défini dans le calendrier d’actualisation](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="18b3c-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="18b3c-166">Choisissez **Exécuter les processus de fusion et en aval** pour actualiser le système avec vos modifications.</span><span class="sxs-lookup"><span data-stu-id="18b3c-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="18b3c-167">Tous les processus, y compris l’enrichissement, les segments et les mesures, seront réexécutés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="18b3c-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="18b3c-168">Une fois tous les processus en aval terminés, les profils client reflètent toutes les modifications que vous avez apportées.</span><span class="sxs-lookup"><span data-stu-id="18b3c-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="18b3c-169">Pour apporter d’autres modifications et réexécuter l’étape, vous pouvez annuler une fusion en cours.</span><span class="sxs-lookup"><span data-stu-id="18b3c-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="18b3c-170">Sélectionnez **Actualisation en cours...** et sélectionnez **Annuler la tâche** dans le volet latéral qui s’affiche.</span><span class="sxs-lookup"><span data-stu-id="18b3c-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="18b3c-171">Il existe [six types de statuts](system.md#status-types) pour les tâches/processus.</span><span class="sxs-lookup"><span data-stu-id="18b3c-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="18b3c-172">En outre, la plupart des processus [dépendent d’autres processus en aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="18b3c-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="18b3c-173">Vous pouvez sélectionner le statut d’un processus pour afficher des détails sur la progression de toute la tâche.</span><span class="sxs-lookup"><span data-stu-id="18b3c-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="18b3c-174">Après avoir sélectionné **Voir les détails** pour l’une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.</span><span class="sxs-lookup"><span data-stu-id="18b3c-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="18b3c-175">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="18b3c-175">Next Step</span></span>

<span data-ttu-id="18b3c-176">Pour plus d'informations sur vos clients, configurez les [activités](activities.md), l'[enrichissement](enrichment-hub.md) ou les [relations](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="18b3c-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="18b3c-177">Si vous avez déjà configuré des activités, un enrichissement ou des segments, ils seront traités automatiquement pour utiliser les dernières données client.</span><span class="sxs-lookup"><span data-stu-id="18b3c-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
