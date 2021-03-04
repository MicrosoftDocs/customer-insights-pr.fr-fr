---
title: Fusionner des entités pour l’unification des données
description: Fusionnez des données pour créer des profils clients unifiés.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 5d5ff4c6f091d1b50d0f6c8366bbe4f0e6428dac
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268499"
---
# <a name="merge-entities"></a><span data-ttu-id="e120f-103">Fusionner des entités</span><span class="sxs-lookup"><span data-stu-id="e120f-103">Merge entities</span></span>

<span data-ttu-id="e120f-104">La fusion est la dernière phase du processus d’unification des données.</span><span class="sxs-lookup"><span data-stu-id="e120f-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="e120f-105">Son objectif consiste à rapprocher les données conflictuelles.</span><span class="sxs-lookup"><span data-stu-id="e120f-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="e120f-106">Des exemples de données en conflit sont le nom d’un client qui réside dans deux de vos jeux de données, avec une petite différence (« Martin Lucas » au lieu de « Martin »), ou un format de numéro de téléphone légèrement différent (06-78-03-09-1X et 067803091X).</span><span class="sxs-lookup"><span data-stu-id="e120f-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="e120f-107">Fusionner ces points de données en conflit s’effectue d’une manière attribut par attribut.</span><span class="sxs-lookup"><span data-stu-id="e120f-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="e120f-108">Après avoir terminé la [phase de mise en correspondance](match-entities.md), vous pouvez entamer la phase de fusion en sélectionnant la vignette **Fusionner** sur la page **Unifier**.</span><span class="sxs-lookup"><span data-stu-id="e120f-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="e120f-109">Examiner les recommandations système</span><span class="sxs-lookup"><span data-stu-id="e120f-109">Review system recommendations</span></span>

<span data-ttu-id="e120f-110">Sur la page **Fusionner**, vous choisissez et excluez des attributs à fusionner au sein de votre entité de profil client unifié (le résultat final du processus de configuration).</span><span class="sxs-lookup"><span data-stu-id="e120f-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="e120f-111">Certains attributs sont automatiquement fusionnés par le système.</span><span class="sxs-lookup"><span data-stu-id="e120f-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="e120f-112">Afficher les attributs fusionnés</span><span class="sxs-lookup"><span data-stu-id="e120f-112">View merged attributes</span></span>

<span data-ttu-id="e120f-113">Pour afficher les attributs inclus dans un de vos attributs fusionnés automatiquement, sélectionnez cet attribut fusionnée.</span><span class="sxs-lookup"><span data-stu-id="e120f-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="e120f-114">Les deux attributs qui composent cet attribut fusionné s’affichent dans deux nouvelles lignes en dessous de l’attribut fusionné.</span><span class="sxs-lookup"><span data-stu-id="e120f-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e120f-115">![Sélectionner l’attribut fusionné](media/configure-data-merge-profile-attributes.png "Sélectionner l’attribut fusionné")</span><span class="sxs-lookup"><span data-stu-id="e120f-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="e120f-116">Séparer les attributs fusionnés</span><span class="sxs-lookup"><span data-stu-id="e120f-116">Separate merged attributes</span></span>

<span data-ttu-id="e120f-117">Pour séparer ou annuler la fusion de l’un des attributs fusionnés automatiquement, recherchez l’attribut dans la table **Attributs de profil**.</span><span class="sxs-lookup"><span data-stu-id="e120f-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="e120f-118">Activez le bouton des points de suspension (...).</span><span class="sxs-lookup"><span data-stu-id="e120f-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="e120f-119">Dans la liste déroulante, sélectionnez **Séparer les champs**.</span><span class="sxs-lookup"><span data-stu-id="e120f-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="e120f-120">Supprimer les attributs fusionnés</span><span class="sxs-lookup"><span data-stu-id="e120f-120">Remove merged attributes</span></span>

<span data-ttu-id="e120f-121">Pour exclure un attribut de l’entité de profil client final, recherchez-le dans la table **Attributs du profil**.</span><span class="sxs-lookup"><span data-stu-id="e120f-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="e120f-122">Activez le bouton des points de suspension (...).</span><span class="sxs-lookup"><span data-stu-id="e120f-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="e120f-123">Dans la liste déroulante, sélectionnez **Ne pas fusionner**.</span><span class="sxs-lookup"><span data-stu-id="e120f-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="e120f-124">L’attribut bascule dans la section **Supprimé de l’enregistrement de client**.</span><span class="sxs-lookup"><span data-stu-id="e120f-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="e120f-125">Ajouter manuellement un attribut fusionné</span><span class="sxs-lookup"><span data-stu-id="e120f-125">Manually add a merged attribute</span></span>

<span data-ttu-id="e120f-126">Pour ajouter un attribut fusionné, accédez à la page **Fusionner**.</span><span class="sxs-lookup"><span data-stu-id="e120f-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="e120f-127">Sélectionnez **Ajouter un attribut fusionné**.</span><span class="sxs-lookup"><span data-stu-id="e120f-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="e120f-128">Indiquez un **Nom** pour l’identifier sur la page **Fusionner** plus tard.</span><span class="sxs-lookup"><span data-stu-id="e120f-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="e120f-129">Éventuellement, fournissez un **Nom d’affichage** à apparaître dans l’entité Profil client unifié.</span><span class="sxs-lookup"><span data-stu-id="e120f-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="e120f-130">Configurez **Sélectionner les attributs dupliqués** pour sélectionner les attributs que vous souhaitez fusionner à partir des entités mises en correspondance.</span><span class="sxs-lookup"><span data-stu-id="e120f-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="e120f-131">Vous pouvez également rechercher des attributs.</span><span class="sxs-lookup"><span data-stu-id="e120f-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="e120f-132">Définissez l’option **Classer par importance** pour donner la priorité à un attribut par rapport aux autres.</span><span class="sxs-lookup"><span data-stu-id="e120f-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="e120f-133">Par exemple, si l’entité *WebAccountCSV* comprend les données les plus précises sur l’attribut *Noms complets*, nous classerons par priorité cette entité *ContactCSV* en sélectionnant *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="e120f-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="e120f-134">Par conséquent, *WebAccountCSV* devient la priorité numéro un, tandis que *ContactCSV* bascule en priorité numéro deux lors de l’extraction des valeurs pour l’attribut *Nom complet*.</span><span class="sxs-lookup"><span data-stu-id="e120f-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="e120f-135">Exécuter la fusion</span><span class="sxs-lookup"><span data-stu-id="e120f-135">Run your merge</span></span>

<span data-ttu-id="e120f-136">Que vous fusionniez manuellement les attributs ou laissiez le système le faire pour vous, à ce stade vous pouvez toujours exécuter votre fusion.</span><span class="sxs-lookup"><span data-stu-id="e120f-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="e120f-137">Sélectionnez **Exécuter** sur la page **Fusionner** pour démarrer le processus.</span><span class="sxs-lookup"><span data-stu-id="e120f-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e120f-138">![Fusion des données - Enregistrer et exécuter](media/configure-data-merge-save-run.png "Fusion des données - Enregistrer et exécuter")</span><span class="sxs-lookup"><span data-stu-id="e120f-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="e120f-139">Pour apporter des modifications supplémentaires et réexécuter l’étape, vous pouvez annuler une fusion en cours.</span><span class="sxs-lookup"><span data-stu-id="e120f-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="e120f-140">Sélectionnez **Actualisation en cours...** et sélectionnez **Annuler la tâche** dans le volet latéral qui s’affiche.</span><span class="sxs-lookup"><span data-stu-id="e120f-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="e120f-141">Une fois le texte **Actualisation en cours...** modifié en **Opération réussie**, la fusion est terminée et les contradictions dans vos données ont été résolues selon les stratégies que vous avez définies.</span><span class="sxs-lookup"><span data-stu-id="e120f-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="e120f-142">Les attributs fusionnés et non fusionnés sont inclus dans l’entité de profil unifié,</span><span class="sxs-lookup"><span data-stu-id="e120f-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="e120f-143">contrairement aux attributs exclus.</span><span class="sxs-lookup"><span data-stu-id="e120f-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="e120f-144">Si ce n’était pas la première fois que vous exécutiez une fusion avec succès, tous les processus en aval, y compris l’enrichissement, la segmentation et les mesures, seront réexécutés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="e120f-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="e120f-145">Une fois tous les processus en aval réexécutés, les profils client reflètent les modifications que vous avez apportées.</span><span class="sxs-lookup"><span data-stu-id="e120f-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="e120f-146">Il existe [six types de statuts](system.md#status-types) pour les tâches/processus.</span><span class="sxs-lookup"><span data-stu-id="e120f-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e120f-147">En outre, la plupart des processus [dépendent d’autres processus en aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e120f-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e120f-148">Vous pouvez sélectionner le statut d’un processus pour afficher des détails sur la progression de toute la tâche.</span><span class="sxs-lookup"><span data-stu-id="e120f-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e120f-149">Après avoir sélectionné **Voir les détails** pour l’une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.</span><span class="sxs-lookup"><span data-stu-id="e120f-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="e120f-150">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="e120f-150">Next Step</span></span>

<span data-ttu-id="e120f-151">Pour plus d’informations sur vos clients, configurez les [activités](activities.md), l’[enrichissement](enrichment-microsoft-graph.md) ou les [relations](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="e120f-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="e120f-152">Si vous avez déjà configuré des activités, un enrichissement ou des relations, ou si vous avez défini des segments, ils seront traités automatiquement pour utiliser les dernières données client.</span><span class="sxs-lookup"><span data-stu-id="e120f-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]