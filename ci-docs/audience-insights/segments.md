---
title: Créer et gérer des segments
description: Créez des segments de clients pour les regrouper en fonction de divers attributs.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405688"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="52ef4-103">Créer et gérer des segments</span><span class="sxs-lookup"><span data-stu-id="52ef4-103">Create and manage segments</span></span>

<span data-ttu-id="52ef4-104">Les segments vous permettent de regrouper vos clients en fonction des attributs démographiques, transactionnels ou comportementaux.</span><span class="sxs-lookup"><span data-stu-id="52ef4-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="52ef4-105">Vous pouvez utiliser les segments pour cibler les campagnes promotionnelles, les activités commerciales et les actions de support client pour atteindre vos objectifs commerciaux.</span><span class="sxs-lookup"><span data-stu-id="52ef4-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="52ef4-106">Vous pouvez définir des filtres complexes autour de l'entité Profil client et des entités associées.</span><span class="sxs-lookup"><span data-stu-id="52ef4-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="52ef4-107">Chaque segment, après le traitement, crée un ensemble d'enregistrement d'entité client que vous pouvez exporter et utiliser pour entreprendre des actions.</span><span class="sxs-lookup"><span data-stu-id="52ef4-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="52ef4-108">Certaines [limites du service](service-limits.md) s'appliquent.</span><span class="sxs-lookup"><span data-stu-id="52ef4-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="52ef4-109">Sauf indication contraire, tous les segments sont des **segments dynamiques**, qui sont actualisés selon un calendrier périodique.</span><span class="sxs-lookup"><span data-stu-id="52ef4-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="52ef4-110">L'exemple suivant illustre la fonctionnalité de segmentation.</span><span class="sxs-lookup"><span data-stu-id="52ef4-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="52ef4-111">Nous avons défini un segment pour les clients qui ont commandé au moins 500 USD de marchandises au cours des 90 derniers jours *et* qui ont été appelés par le service clientèle.</span><span class="sxs-lookup"><span data-stu-id="52ef4-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="52ef4-112">![Groupes multiples](media/segmentation-group1-2.png "Groupes multiples")</span><span class="sxs-lookup"><span data-stu-id="52ef4-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="52ef4-113">Créer un segment</span><span class="sxs-lookup"><span data-stu-id="52ef4-113">Create a new segment</span></span>

<span data-ttu-id="52ef4-114">Les segments sont gérés sur la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="52ef4-115">Dans Audience Insights, accédez à la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="52ef4-116">Sélectionnez **Nouveau** > **Segment vide**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="52ef4-117">Dans le volet **Nouveau segment**, choisissez un type de segment et indiquez un **Nom**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="52ef4-118">Vous pouvez aussi fournir un nom complet et une description qui aide à identifier le segment.</span><span class="sxs-lookup"><span data-stu-id="52ef4-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="52ef4-119">Sélectionnez **Suivant** pour arriver sur la page **Générateur de segments** où vous devez définir un groupe.</span><span class="sxs-lookup"><span data-stu-id="52ef4-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="52ef4-120">Un groupe est un ensemble de clients.</span><span class="sxs-lookup"><span data-stu-id="52ef4-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="52ef4-121">Choisissez l'entité qui comprend l'attribut selon lequel vous souhaitez segmenter.</span><span class="sxs-lookup"><span data-stu-id="52ef4-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="52ef4-122">Choisissez l'attribut de segmentation.</span><span class="sxs-lookup"><span data-stu-id="52ef4-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="52ef4-123">Cet attribut peut avoir un des quatre types de valeur : numérique, chaîne, date ou booléen.</span><span class="sxs-lookup"><span data-stu-id="52ef4-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="52ef4-124">Choisissez un opérateur et une valeur pour l'attribut sélectionné.</span><span class="sxs-lookup"><span data-stu-id="52ef4-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="52ef4-125">![Filtre de groupe personnalisé](media/customer-group-numbers.png "Filtre du groupe de clients")</span><span class="sxs-lookup"><span data-stu-id="52ef4-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="52ef4-126">Numéro</span><span class="sxs-lookup"><span data-stu-id="52ef4-126">Number</span></span> |<span data-ttu-id="52ef4-127">Définition</span><span class="sxs-lookup"><span data-stu-id="52ef4-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="52ef4-128">1</span><span class="sxs-lookup"><span data-stu-id="52ef4-128">1</span></span>     |<span data-ttu-id="52ef4-129">Entité</span><span class="sxs-lookup"><span data-stu-id="52ef4-129">Entity</span></span>          |
   |<span data-ttu-id="52ef4-130">2</span><span class="sxs-lookup"><span data-stu-id="52ef4-130">2</span></span>     |<span data-ttu-id="52ef4-131">Attribut</span><span class="sxs-lookup"><span data-stu-id="52ef4-131">Attribute</span></span>          |
   |<span data-ttu-id="52ef4-132">3</span><span class="sxs-lookup"><span data-stu-id="52ef4-132">3</span></span>    |<span data-ttu-id="52ef4-133">Opérateur</span><span class="sxs-lookup"><span data-stu-id="52ef4-133">Operator</span></span>         |
   |<span data-ttu-id="52ef4-134">4</span><span class="sxs-lookup"><span data-stu-id="52ef4-134">4</span></span>    |<span data-ttu-id="52ef4-135">Valeur</span><span class="sxs-lookup"><span data-stu-id="52ef4-135">Value</span></span>         |

8. <span data-ttu-id="52ef4-136">Si l'entité est connectée à l'entité client unifiée par le biais de [relations](relationships.md), vous devez définir le chemin d'accès de la relation pour créer un segment valide.</span><span class="sxs-lookup"><span data-stu-id="52ef4-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="52ef4-137">Ajoutez les entités à partir du chemin d'accès de la relation jusqu'à ce que vous puissiez sélectionner l'entité **Client : CustomerInsights** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="52ef4-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="52ef4-138">Ensuite, choisissez **Tous les enregistrements** pour chaque condition.</span><span class="sxs-lookup"><span data-stu-id="52ef4-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="52ef4-139">![Chemin d'accès de la relation lors de la création d'un segment](media/segments-multiple-relationships.png "Chemin d'accès de la relation lors de la création d'un segment")</span><span class="sxs-lookup"><span data-stu-id="52ef4-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="52ef4-140">Sélectionnez **Enregistrer** pour enregistrer votre segment.</span><span class="sxs-lookup"><span data-stu-id="52ef4-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="52ef4-141">Votre segment sera enregistré et traité si toutes les exigences sont validées.</span><span class="sxs-lookup"><span data-stu-id="52ef4-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="52ef4-142">Sinon, il sera enregistré en tant que brouillon.</span><span class="sxs-lookup"><span data-stu-id="52ef4-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="52ef4-143">Sélectionnez **Revenir aux segments** pour revenir à la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="52ef4-144">Gérer les segments existants</span><span class="sxs-lookup"><span data-stu-id="52ef4-144">Manage existing segments</span></span>

<span data-ttu-id="52ef4-145">Sur la page **Segments** vous pouvez afficher tous vos segments enregistrés et les gérer.</span><span class="sxs-lookup"><span data-stu-id="52ef4-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="52ef4-146">Chaque segment est représenté par une ligne qui contient des informations supplémentaires sur le segment.</span><span class="sxs-lookup"><span data-stu-id="52ef4-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="52ef4-147">Vous pouvez trier les segments d'une colonne en sélectionnant l'en-tête de colonne.</span><span class="sxs-lookup"><span data-stu-id="52ef4-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="52ef4-148">Utilisez la case **Rechercher** dans le coin supérieur droit pour filtrer les segments.</span><span class="sxs-lookup"><span data-stu-id="52ef4-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="52ef4-149">![Options de gestion d'un segment existant](media/segments-selected-segment.png "Options de gestion d'un segment existant")</span><span class="sxs-lookup"><span data-stu-id="52ef4-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="52ef4-150">L'action suivante est disponible lorsque vous sélectionnez un segment :</span><span class="sxs-lookup"><span data-stu-id="52ef4-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="52ef4-151">**Afficher** les détails du segment, y compris un aperçu de la tendance du nombre de membres du segment.</span><span class="sxs-lookup"><span data-stu-id="52ef4-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="52ef4-152">**Modifier** le segment pour modifier ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="52ef4-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="52ef4-153">**Actualiser** le segment pour inclure les dernières données.</span><span class="sxs-lookup"><span data-stu-id="52ef4-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="52ef4-154">**Activer** ou **Désactiver** le segment.</span><span class="sxs-lookup"><span data-stu-id="52ef4-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="52ef4-155">Les segments ont deux états possibles : actif ou inactif.</span><span class="sxs-lookup"><span data-stu-id="52ef4-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="52ef4-156">Ces états sont utiles lors de l'édition d'un segment.</span><span class="sxs-lookup"><span data-stu-id="52ef4-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="52ef4-157">Pour les segments inactifs, la définition de segment existe, mais elle ne contient pas encore de clients.</span><span class="sxs-lookup"><span data-stu-id="52ef4-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="52ef4-158">Lorsque vous activez un segment, son état passe de « inactif » à « actif » et il commence à rechercher des clients qui correspondent à la définition du segment.</span><span class="sxs-lookup"><span data-stu-id="52ef4-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="52ef4-159">Si une [actualisation programmée](system.md#schedule-tab) est configurée, les segments inactifs ont leur **Statut** répertorié comme **Ignoré**, indiquant qu'une actualisation n'a même pas été tentée.</span><span class="sxs-lookup"><span data-stu-id="52ef4-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="52ef4-160">Lorsqu'un segment inactif est activé, il s'actualise et sera inclus dans les actualisations programmées.</span><span class="sxs-lookup"><span data-stu-id="52ef4-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="52ef4-161">Vous pouvez également utiliser la fonctionnalité **Planifier plus tard** dans la liste déroulante **Activer/Désactiver** pour spécifier une date et une heure futures d'activation et de désactivation d'un segment particulier.</span><span class="sxs-lookup"><span data-stu-id="52ef4-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="52ef4-162">**Renommer** le segment.</span><span class="sxs-lookup"><span data-stu-id="52ef4-162">**Rename** the segment.</span></span>
- <span data-ttu-id="52ef4-163">**Télécharger** la liste des membres en tant que fichier .CSV.</span><span class="sxs-lookup"><span data-stu-id="52ef4-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="52ef4-164">L'option **Ajouter à** envoie la liste des ID clients du segment aux fins de traitement dans une autre application.</span><span class="sxs-lookup"><span data-stu-id="52ef4-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="52ef4-165">**Supprimer** le segment.</span><span class="sxs-lookup"><span data-stu-id="52ef4-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="52ef4-166">Actualiser des segments</span><span class="sxs-lookup"><span data-stu-id="52ef4-166">Refresh segments</span></span>

<span data-ttu-id="52ef4-167">Vous pouvez actualiser tous les segments à la fois en sélectionnant **Actualiser tout** sur la page **Segments** ou vous pouvez actualiser un ou plusieurs segments lorsque vous les sélectionnez et choisissez **Actualiser** dans les options.</span><span class="sxs-lookup"><span data-stu-id="52ef4-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="52ef4-168">Vous pouvez également configurer une actualisation périodique en cliquant sur **Administrateur** > **Système** > **Planifier**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="52ef4-169">Il existe [six types de statuts](system.md#status-types) pour les tâches/processus.</span><span class="sxs-lookup"><span data-stu-id="52ef4-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="52ef4-170">En outre, la plupart des processus [dépendent d'autres processus en aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="52ef4-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="52ef4-171">Vous pouvez sélectionner le statut d'un processus pour afficher des détails sur la progression de toute la tâche.</span><span class="sxs-lookup"><span data-stu-id="52ef4-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="52ef4-172">Après avoir sélectionné **Voir les détails** pour l'une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.</span><span class="sxs-lookup"><span data-stu-id="52ef4-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="52ef4-173">Télécharger et exporter des segments</span><span class="sxs-lookup"><span data-stu-id="52ef4-173">Download and export segments</span></span>

<span data-ttu-id="52ef4-174">Vous pouvez télécharger vos segments dans un fichier CSV ou les exporter vers Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="52ef4-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="52ef4-175">Télécharger des segments dans un fichier CSV</span><span class="sxs-lookup"><span data-stu-id="52ef4-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="52ef4-176">Dans Audience Insights, accédez à la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="52ef4-177">Sélectionnez les points de suspension dans une vignette de segment spécifique.</span><span class="sxs-lookup"><span data-stu-id="52ef4-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="52ef4-178">Sélectionnez **Télécharger au format CSV** dans la liste déroulante des actions.</span><span class="sxs-lookup"><span data-stu-id="52ef4-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="52ef4-179">Exporter des segments vers Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="52ef4-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="52ef4-180">Avant d'exporter des segments vers Dynamics 365 Sales, un administrateur doit [créer la destination d'exportation](export-destinations.md) pour Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="52ef4-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="52ef4-181">Dans Audience Insights, accédez à la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="52ef4-182">Sélectionnez les points de suspension dans une vignette de segment spécifique.</span><span class="sxs-lookup"><span data-stu-id="52ef4-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="52ef4-183">Sélectionnez **Ajouter à** dans la liste déroulante des actions et sélectionnez la destination d'exportation vers laquelle vous souhaitez envoyer les données.</span><span class="sxs-lookup"><span data-stu-id="52ef4-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="52ef4-184">Mode brouillon pour les segments</span><span class="sxs-lookup"><span data-stu-id="52ef4-184">Draft mode for segments</span></span>

<span data-ttu-id="52ef4-185">Si toutes les exigences pour traiter un segment ne sont pas remplies, vous pouvez enregistrer le segment en tant que brouillon et y accéder à partir de la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="52ef4-186">Il est enregistré en tant que segment inactif et ne peut pas être activé tant qu'il n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="52ef4-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="52ef4-187">Ajouter plus de conditions à un groupe</span><span class="sxs-lookup"><span data-stu-id="52ef4-187">Add more conditions to a group</span></span>

<span data-ttu-id="52ef4-188">Pour ajouter plus de conditions à un groupe, vous pouvez utiliser deux opérateurs logiques :</span><span class="sxs-lookup"><span data-stu-id="52ef4-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="52ef4-189">Opérateur **ET** : Les deux conditions doivent être remplies dans le cadre du processus de segmentation.</span><span class="sxs-lookup"><span data-stu-id="52ef4-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="52ef4-190">Cette option est particulièrement utile lorsque vous définissez des conditions sur différentes entités.</span><span class="sxs-lookup"><span data-stu-id="52ef4-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="52ef4-191">Opérateur **OU** : L'une ou l'autre des conditions doit être satisfaite dans le cadre de le processus de segmentation.</span><span class="sxs-lookup"><span data-stu-id="52ef4-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="52ef4-192">Cette option est très utile lorsque vous définissez plusieurs conditions pour la même entité.</span><span class="sxs-lookup"><span data-stu-id="52ef4-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="52ef4-193">![Opérateur OU où l'une ou l'autre des conditions doit être remplie](media/segmentation-either-condition.png "Opérateur OU où l'une ou l'autre des conditions doit être remplie")</span><span class="sxs-lookup"><span data-stu-id="52ef4-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="52ef4-194">Il est actuellement possible d'imbriquer un opérateur **OU** sous un opérateur **ET**, mais pas l'inverse.</span><span class="sxs-lookup"><span data-stu-id="52ef4-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="52ef4-195">Combiner plusieurs groupes</span><span class="sxs-lookup"><span data-stu-id="52ef4-195">Combine multiple groups</span></span>

<span data-ttu-id="52ef4-196">Chaque produit groupe un ensemble spécifique de clients.</span><span class="sxs-lookup"><span data-stu-id="52ef4-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="52ef4-197">Vous pouvez combiner ces groupes pour inclure les clients requis pour votre étude de cas.</span><span class="sxs-lookup"><span data-stu-id="52ef4-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="52ef4-198">Dans Audience Insights, accédez à la page **Segments** et sélectionnez un segment.</span><span class="sxs-lookup"><span data-stu-id="52ef4-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="52ef4-199">Sélectionnez **Ajouter un groupe**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="52ef4-200">![Groupe de clients - Ajouter un groupe](media/customer-group-add-group.png "Groupe de clients - Ajouter un groupe")</span><span class="sxs-lookup"><span data-stu-id="52ef4-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="52ef4-201">Sélectionnez l'un des opérateurs d'ensemble suivants : **Union**, **Intersection** ou **Exception**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="52ef4-202">![Groupe de clients - Ajouter une union](media/customer-group-union.png "Groupe de clients - Ajouter une union")</span><span class="sxs-lookup"><span data-stu-id="52ef4-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="52ef4-203">Sélectionnez un opérateur configuré pour définir un nouveau groupe.</span><span class="sxs-lookup"><span data-stu-id="52ef4-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="52ef4-204">Enregistrez différents groupes pour déterminer quelles données sont conservées :</span><span class="sxs-lookup"><span data-stu-id="52ef4-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="52ef4-205">**Union** unit les deux groupes.</span><span class="sxs-lookup"><span data-stu-id="52ef4-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="52ef4-206">**Intersection** fait se chevaucher les deux groupes.</span><span class="sxs-lookup"><span data-stu-id="52ef4-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="52ef4-207">Seules les données qui *sont communes* aux deux groupes sont conservées dans le groupe unifié.</span><span class="sxs-lookup"><span data-stu-id="52ef4-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="52ef4-208">**Exception** combine les deux groupes.</span><span class="sxs-lookup"><span data-stu-id="52ef4-208">**Except** combines the two groups.</span></span> <span data-ttu-id="52ef4-209">Seules les données du groupe A qui *ne sont pas communes* aux données du groupe B sont conservées.</span><span class="sxs-lookup"><span data-stu-id="52ef4-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="52ef4-210">Afficher l'historique de traitement et les membres du segment</span><span class="sxs-lookup"><span data-stu-id="52ef4-210">View processing history and segment members</span></span>

<span data-ttu-id="52ef4-211">Vous pouvez voir les données consolidées d'un segment en examinant ses détails.</span><span class="sxs-lookup"><span data-stu-id="52ef4-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="52ef4-212">Dans la page **Segments**, sélectionnez le segment à vérifier.</span><span class="sxs-lookup"><span data-stu-id="52ef4-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="52ef4-213">La partie supérieure de la page comprend un graphique de tendance qui indique l'évolution du nombre des membres.</span><span class="sxs-lookup"><span data-stu-id="52ef4-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="52ef4-214">Passez la souris sur les points de données pour voir le nombre de membres à une date spécifique.</span><span class="sxs-lookup"><span data-stu-id="52ef4-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="52ef4-215">Vous pouvez mettre à jour le délai d'exécution de la visualisation.</span><span class="sxs-lookup"><span data-stu-id="52ef4-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="52ef4-216">![Intervalle de temps du segment](media/segment-time-range.png "Intervalle de temps du segment")</span><span class="sxs-lookup"><span data-stu-id="52ef4-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="52ef4-217">La partie inférieure contient la liste des membres du segment.</span><span class="sxs-lookup"><span data-stu-id="52ef4-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="52ef4-218">Les champs qui apparaissent dans cette liste sont basés sur les attributs des entités de votre segment.</span><span class="sxs-lookup"><span data-stu-id="52ef4-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="52ef4-219">La liste est un aperçu des membres du segment correspondant et affiche les 100 premiers enregistrements de votre segment afin que vous puissiez rapidement l'évaluer et revoir ses définitions si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="52ef4-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="52ef4-220">Pour voir tous les enregistrements correspondants, vous devez [exporter le segment](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="52ef4-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="52ef4-221">Segments rapides</span><span class="sxs-lookup"><span data-stu-id="52ef4-221">Quick segments</span></span>

<span data-ttu-id="52ef4-222">Outre le générateur de segments, il existe un autre moyen de créer des segments.</span><span class="sxs-lookup"><span data-stu-id="52ef4-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="52ef4-223">Les segments rapides vous permettent de créer des segments simples (avec un seul opérateur) rapidement et avec des informations instantanées.</span><span class="sxs-lookup"><span data-stu-id="52ef4-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="52ef4-224">Sur la page **Segments**, sélectionnez **Nouveau** > **Création rapide depuis**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="52ef4-225">Sélectionnez l'option **Profils** pour créer un segment basé sur l'entité Client unifiée.</span><span class="sxs-lookup"><span data-stu-id="52ef4-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="52ef4-226">Sélectionnez l'option **Mesures** pour créer un segment pour chaque type Attribut de client des mesures que vous avez précédemment créées dans la page **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="52ef4-227">Sélectionnez l'option **Intelligence** pour créer un segment autour de l'une des entités de sortie que vous avez générées à l'aide des fonctionnalités **Prédictions** ou **Modèles personnalisés**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="52ef4-228">Dans la boîte de dialogue **Nouveau segment rapide**, sélectionnez un attribut dans la liste déroulante **Champ**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="52ef4-229">Le système fournit des informations supplémentaires qui vous permettent de créer de meilleurs segments de vos clients.</span><span class="sxs-lookup"><span data-stu-id="52ef4-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="52ef4-230">Pour les champs de catégorie, nous affichons les 10 meilleurs clients.</span><span class="sxs-lookup"><span data-stu-id="52ef4-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="52ef4-231">Choisissez une **Valeur** et sélectionnez **Réviser**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="52ef4-232">Pour un attribut numérique, le système affiche la valeur d'attribut correspondant au centile de chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="52ef4-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="52ef4-233">Choisissez un **Opérateur** et une **Valeur**, puis sélectionnez **Réviser**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="52ef4-234">Le système vous fournira une **taille estimée du segment**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="52ef4-235">Vous pouvez choisir de générer le segment que vous avez défini ou de le revoir pour obtenir une taille de segment différente.</span><span class="sxs-lookup"><span data-stu-id="52ef4-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="52ef4-236">![Nom et estimation pour un segment rapide](media/quick-segment-name.png "Nom et estimation pour un segment rapide")</span><span class="sxs-lookup"><span data-stu-id="52ef4-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="52ef4-237">Fournissez un **Nom** pour votre segment.</span><span class="sxs-lookup"><span data-stu-id="52ef4-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="52ef4-238">Indiquez éventuellement un **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="52ef4-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="52ef4-239">Sélectionnez **Enregistrer** pour créer votre segment.</span><span class="sxs-lookup"><span data-stu-id="52ef4-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="52ef4-240">Une fois le segment terminé, vous pouvez l'afficher comme tout autre segment que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="52ef4-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="52ef4-241">Pour les scénarios suivants, nous vous conseillons d'utiliser le générateur de segments plutôt que la capacité de segments recommandée :</span><span class="sxs-lookup"><span data-stu-id="52ef4-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="52ef4-242">Création de segments avec des filtres sur des champs de catégorie où l'opérateur est différent de l'opérateur **Est**</span><span class="sxs-lookup"><span data-stu-id="52ef4-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="52ef4-243">Création de segments avec des filtres sur des champs numériques où l'opérateur est différent des opérateurs **Entre**, **Supérieur à** et **Inférieur à**</span><span class="sxs-lookup"><span data-stu-id="52ef4-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="52ef4-244">Création de segments avec des filtres sur des champs de type Date</span><span class="sxs-lookup"><span data-stu-id="52ef4-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="52ef4-245">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="52ef4-245">Next steps</span></span>

<span data-ttu-id="52ef4-246">[Exportez un segment](export-destinations.md) et explorer la [carte client](customer-card-add-in.md) et les [connecteurs](export-power-bi.md) pour obtenir des informations sur le niveau du client.</span><span class="sxs-lookup"><span data-stu-id="52ef4-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
