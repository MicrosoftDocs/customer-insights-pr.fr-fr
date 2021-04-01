---
title: Créer et gérer des segments
description: Créez des segments de clients pour les regrouper en fonction de divers attributs.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597048"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="6e45b-103">Créer et gérer des segments</span><span class="sxs-lookup"><span data-stu-id="6e45b-103">Create and manage segments</span></span>

<span data-ttu-id="6e45b-104">Les segments vous permettent de regrouper vos clients en fonction des attributs démographiques, transactionnels ou comportementaux.</span><span class="sxs-lookup"><span data-stu-id="6e45b-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="6e45b-105">Vous pouvez utiliser les segments pour cibler les campagnes promotionnelles, les activités commerciales et les actions de support client pour atteindre vos objectifs commerciaux.</span><span class="sxs-lookup"><span data-stu-id="6e45b-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="6e45b-106">Vous pouvez définir des filtres complexes autour de l’entité Profil client et des entités associées.</span><span class="sxs-lookup"><span data-stu-id="6e45b-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="6e45b-107">Chaque segment, après le traitement, crée un ensemble d’enregistrement d’entité client que vous pouvez exporter et utiliser pour entreprendre des actions.</span><span class="sxs-lookup"><span data-stu-id="6e45b-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="6e45b-108">Certaines [limites du service](service-limits.md) s’appliquent.</span><span class="sxs-lookup"><span data-stu-id="6e45b-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="6e45b-109">Sauf indication contraire, tous les segments sont des **segments dynamiques**, qui sont actualisés selon un calendrier périodique.</span><span class="sxs-lookup"><span data-stu-id="6e45b-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="6e45b-110">L’exemple suivant illustre la fonctionnalité de segmentation.</span><span class="sxs-lookup"><span data-stu-id="6e45b-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="6e45b-111">Nous avons défini un segment pour les clients qui ont commandé au moins 500 USD de marchandises au cours des 90 derniers jours *et* qui ont été appelés par le service clientèle.</span><span class="sxs-lookup"><span data-stu-id="6e45b-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6e45b-112">![Groupes multiples](media/segmentation-group1-2.png "Groupes multiples")</span><span class="sxs-lookup"><span data-stu-id="6e45b-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="6e45b-113">Créer un segment</span><span class="sxs-lookup"><span data-stu-id="6e45b-113">Create a new segment</span></span>

<span data-ttu-id="6e45b-114">Les segments sont gérés sur la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="6e45b-115">Dans les informations sur l’audience, accédez à la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="6e45b-116">Sélectionnez **Nouveau** > **Segment vide**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="6e45b-117">Dans le volet **Nouveau segment**, choisissez un type de segment et indiquez un **Nom**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="6e45b-118">Vous pouvez aussi fournir un nom complet et une description qui aide à identifier le segment.</span><span class="sxs-lookup"><span data-stu-id="6e45b-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="6e45b-119">Sélectionnez **Suivant** pour arriver sur la page **Générateur de segments** où vous devez définir un groupe.</span><span class="sxs-lookup"><span data-stu-id="6e45b-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="6e45b-120">Un groupe est un ensemble de clients.</span><span class="sxs-lookup"><span data-stu-id="6e45b-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="6e45b-121">Choisissez l’entité qui comprend l’attribut selon lequel vous souhaitez segmenter.</span><span class="sxs-lookup"><span data-stu-id="6e45b-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="6e45b-122">Choisissez l’attribut de segmentation.</span><span class="sxs-lookup"><span data-stu-id="6e45b-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="6e45b-123">Cet attribut peut avoir un des quatre types de valeur : numérique, chaîne, date ou booléen.</span><span class="sxs-lookup"><span data-stu-id="6e45b-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="6e45b-124">Choisissez un opérateur et une valeur pour l’attribut sélectionné.</span><span class="sxs-lookup"><span data-stu-id="6e45b-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6e45b-125">![Filtre de groupe personnalisé](media/customer-group-numbers.png "Filtre du groupe de clients")</span><span class="sxs-lookup"><span data-stu-id="6e45b-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="6e45b-126">Numéro</span><span class="sxs-lookup"><span data-stu-id="6e45b-126">Number</span></span> |<span data-ttu-id="6e45b-127">Définition</span><span class="sxs-lookup"><span data-stu-id="6e45b-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="6e45b-128">1</span><span class="sxs-lookup"><span data-stu-id="6e45b-128">1</span></span>     |<span data-ttu-id="6e45b-129">Entité</span><span class="sxs-lookup"><span data-stu-id="6e45b-129">Entity</span></span>          |
   |<span data-ttu-id="6e45b-130">2</span><span class="sxs-lookup"><span data-stu-id="6e45b-130">2</span></span>     |<span data-ttu-id="6e45b-131">Attribut</span><span class="sxs-lookup"><span data-stu-id="6e45b-131">Attribute</span></span>          |
   |<span data-ttu-id="6e45b-132">3</span><span class="sxs-lookup"><span data-stu-id="6e45b-132">3</span></span>    |<span data-ttu-id="6e45b-133">Opérateur</span><span class="sxs-lookup"><span data-stu-id="6e45b-133">Operator</span></span>         |
   |<span data-ttu-id="6e45b-134">4</span><span class="sxs-lookup"><span data-stu-id="6e45b-134">4</span></span>    |<span data-ttu-id="6e45b-135">Valeur</span><span class="sxs-lookup"><span data-stu-id="6e45b-135">Value</span></span>         |

8. <span data-ttu-id="6e45b-136">Si l’entité est connectée à l’entité client unifiée par le biais de [relations](relationships.md), vous devez définir le chemin d’accès de la relation pour créer un segment valide.</span><span class="sxs-lookup"><span data-stu-id="6e45b-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="6e45b-137">Ajoutez les entités à partir du chemin d’accès de la relation jusqu’à ce que vous puissiez sélectionner l’entité **Client : CustomerInsights** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="6e45b-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="6e45b-138">Ensuite, choisissez **Tous les enregistrements** pour chaque condition.</span><span class="sxs-lookup"><span data-stu-id="6e45b-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6e45b-139">![Chemin d’accès de la relation lors de la création d’un segment](media/segments-multiple-relationships.png "Chemin d’accès de la relation lors de la création d’un segment")</span><span class="sxs-lookup"><span data-stu-id="6e45b-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="6e45b-140">Par défaut, les segments génèrent une entité de sortie qui contient tous les attributs des profils client qui correspondent aux filtres définis.</span><span class="sxs-lookup"><span data-stu-id="6e45b-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="6e45b-141">Si un segment est basé sur d’autres entités que l’entité *Client*, vous pouvez ajouter d’autres attributs de ces entités à l’entité de sortie.</span><span class="sxs-lookup"><span data-stu-id="6e45b-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="6e45b-142">Sélectionnez **Attributs du projet** pour choisir les attributs qui seront ajoutés à l’entité de sortie.</span><span class="sxs-lookup"><span data-stu-id="6e45b-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="6e45b-143">Exemple : un segment est basé sur une entité qui contient des données d’activité client liées à l’entité *Client*.</span><span class="sxs-lookup"><span data-stu-id="6e45b-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="6e45b-144">Le segment recherche tous les clients qui ont appelé le service d’assistance au cours des 60 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="6e45b-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="6e45b-145">Vous pouvez choisir d’ajouter la durée de l’appel et le nombre d’appels à tous les enregistrements client correspondants dans l’entité de sortie.</span><span class="sxs-lookup"><span data-stu-id="6e45b-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="6e45b-146">Ces informations peuvent être utiles pour envoyer un e-mail contenant des liens utiles vers des articles d’aide en ligne et des questions fréquentes (FAQ) aux clients qui ont appelé fréquemment.</span><span class="sxs-lookup"><span data-stu-id="6e45b-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="6e45b-147">Sélectionnez **Enregistrer** pour enregistrer votre segment.</span><span class="sxs-lookup"><span data-stu-id="6e45b-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="6e45b-148">Votre segment sera enregistré et traité si toutes les exigences sont validées.</span><span class="sxs-lookup"><span data-stu-id="6e45b-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="6e45b-149">Sinon, il sera enregistré en tant que brouillon.</span><span class="sxs-lookup"><span data-stu-id="6e45b-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="6e45b-150">Sélectionnez **Revenir aux segments** pour revenir à la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="6e45b-151">Gérer les segments existants</span><span class="sxs-lookup"><span data-stu-id="6e45b-151">Manage existing segments</span></span>

<span data-ttu-id="6e45b-152">Sur la page **Segments** vous pouvez afficher tous vos segments enregistrés et les gérer.</span><span class="sxs-lookup"><span data-stu-id="6e45b-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="6e45b-153">Chaque segment est représenté par une ligne qui contient des informations supplémentaires sur le segment.</span><span class="sxs-lookup"><span data-stu-id="6e45b-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="6e45b-154">Vous pouvez trier les segments d’une colonne en sélectionnant l’en-tête de colonne.</span><span class="sxs-lookup"><span data-stu-id="6e45b-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="6e45b-155">Utilisez la case **Rechercher** dans le coin supérieur droit pour filtrer les segments.</span><span class="sxs-lookup"><span data-stu-id="6e45b-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6e45b-156">![Options de gestion d’un segment existant](media/segments-selected-segment.png "Options de gestion d’un segment existant")</span><span class="sxs-lookup"><span data-stu-id="6e45b-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="6e45b-157">L’action suivante est disponible lorsque vous sélectionnez un segment :</span><span class="sxs-lookup"><span data-stu-id="6e45b-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="6e45b-158">**Afficher** les détails du segment, y compris un aperçu de la tendance du nombre de membres du segment.</span><span class="sxs-lookup"><span data-stu-id="6e45b-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="6e45b-159">**Modifier** le segment pour modifier ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="6e45b-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="6e45b-160">**Créez un doublon** d’un segment.</span><span class="sxs-lookup"><span data-stu-id="6e45b-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="6e45b-161">Vous pouvez choisir de modifier ses propriétés immédiatement ou simplement d’enregistrer le doublon.</span><span class="sxs-lookup"><span data-stu-id="6e45b-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="6e45b-162">**Actualiser** le segment pour inclure les dernières données.</span><span class="sxs-lookup"><span data-stu-id="6e45b-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="6e45b-163">**Activer** ou **Désactiver** le segment.</span><span class="sxs-lookup"><span data-stu-id="6e45b-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="6e45b-164">Les segments ont deux états possibles : actif ou inactif.</span><span class="sxs-lookup"><span data-stu-id="6e45b-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="6e45b-165">Ces états sont utiles lors de l’édition d’un segment.</span><span class="sxs-lookup"><span data-stu-id="6e45b-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="6e45b-166">Pour les segments inactifs, la définition de segment existe, mais elle ne contient pas encore de clients.</span><span class="sxs-lookup"><span data-stu-id="6e45b-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="6e45b-167">Lorsque vous activez un segment, son état passe de « inactif » à « actif » et il commence à rechercher des clients qui correspondent à la définition du segment.</span><span class="sxs-lookup"><span data-stu-id="6e45b-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="6e45b-168">Si une [actualisation programmée](system.md#schedule-tab) est configurée, les segments inactifs ont leur **Statut** répertorié comme **Ignoré**, indiquant qu’une actualisation n’a même pas été tentée.</span><span class="sxs-lookup"><span data-stu-id="6e45b-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="6e45b-169">Lorsqu’un segment inactif est activé, il s’actualise et sera inclus dans les actualisations programmées.</span><span class="sxs-lookup"><span data-stu-id="6e45b-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="6e45b-170">Vous pouvez également utiliser la fonctionnalité **Planifier plus tard** dans la liste déroulante **Activer/Désactiver** pour spécifier une date et une heure futures d’activation et de désactivation d’un segment particulier.</span><span class="sxs-lookup"><span data-stu-id="6e45b-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="6e45b-171">**Renommer** le segment.</span><span class="sxs-lookup"><span data-stu-id="6e45b-171">**Rename** the segment.</span></span>
- <span data-ttu-id="6e45b-172">**Télécharger** la liste des membres en tant que fichier .CSV.</span><span class="sxs-lookup"><span data-stu-id="6e45b-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="6e45b-173">L’option **Ajouter à** envoie la liste des ID clients du segment aux fins de traitement dans une autre application.</span><span class="sxs-lookup"><span data-stu-id="6e45b-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="6e45b-174">**Supprimer** le segment.</span><span class="sxs-lookup"><span data-stu-id="6e45b-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="6e45b-175">Actualiser des segments</span><span class="sxs-lookup"><span data-stu-id="6e45b-175">Refresh segments</span></span>

<span data-ttu-id="6e45b-176">Vous pouvez actualiser tous les segments à la fois en sélectionnant **Actualiser tout** sur la page **Segments** ou vous pouvez actualiser un ou plusieurs segments lorsque vous les sélectionnez et choisissez **Actualiser** dans les options.</span><span class="sxs-lookup"><span data-stu-id="6e45b-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="6e45b-177">Vous pouvez également configurer une actualisation périodique en cliquant sur **Administrateur** > **Système** > **Planifier**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="6e45b-178">Il existe [six types de statuts](system.md#status-types) pour les tâches/processus.</span><span class="sxs-lookup"><span data-stu-id="6e45b-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="6e45b-179">En outre, la plupart des processus [dépendent d’autres processus en aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="6e45b-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="6e45b-180">Vous pouvez sélectionner le statut d’un processus pour afficher des détails sur la progression de toute la tâche.</span><span class="sxs-lookup"><span data-stu-id="6e45b-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="6e45b-181">Après avoir sélectionné **Voir les détails** pour l’une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.</span><span class="sxs-lookup"><span data-stu-id="6e45b-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="6e45b-182">Télécharger et exporter des segments</span><span class="sxs-lookup"><span data-stu-id="6e45b-182">Download and export segments</span></span>

<span data-ttu-id="6e45b-183">Vous pouvez télécharger vos segments dans un fichier CSV ou les exporter vers Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="6e45b-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="6e45b-184">Télécharger des segments dans un fichier CSV</span><span class="sxs-lookup"><span data-stu-id="6e45b-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="6e45b-185">Dans les informations sur l’audience, accédez à la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="6e45b-186">Sélectionnez les points de suspension dans une vignette de segment spécifique.</span><span class="sxs-lookup"><span data-stu-id="6e45b-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="6e45b-187">Sélectionnez **Télécharger au format CSV** dans la liste déroulante des actions.</span><span class="sxs-lookup"><span data-stu-id="6e45b-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="6e45b-188">Exporter des segments vers Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="6e45b-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="6e45b-189">Avant d’exporter des segments vers Dynamics 365 Sales, un administrateur doit [créer la destination d’exportation](export-destinations.md) pour Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="6e45b-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="6e45b-190">Dans les informations sur l’audience, accédez à la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="6e45b-191">Sélectionnez les points de suspension dans une vignette de segment spécifique.</span><span class="sxs-lookup"><span data-stu-id="6e45b-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="6e45b-192">Sélectionnez **Ajouter à** dans la liste déroulante des actions et sélectionnez la destination d’exportation vers laquelle vous souhaitez envoyer les données.</span><span class="sxs-lookup"><span data-stu-id="6e45b-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="6e45b-193">Mode brouillon pour les segments</span><span class="sxs-lookup"><span data-stu-id="6e45b-193">Draft mode for segments</span></span>

<span data-ttu-id="6e45b-194">Si toutes les exigences pour traiter un segment ne sont pas remplies, vous pouvez enregistrer le segment en tant que brouillon et y accéder à partir de la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="6e45b-195">Il est enregistré en tant que segment inactif et ne peut pas être activé tant qu’il n’est pas valide.</span><span class="sxs-lookup"><span data-stu-id="6e45b-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="6e45b-196">Ajouter plus de conditions à un groupe</span><span class="sxs-lookup"><span data-stu-id="6e45b-196">Add more conditions to a group</span></span>

<span data-ttu-id="6e45b-197">Pour ajouter plus de conditions à un groupe, vous pouvez utiliser deux opérateurs logiques :</span><span class="sxs-lookup"><span data-stu-id="6e45b-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="6e45b-198">Opérateur **ET** : Les deux conditions doivent être remplies dans le cadre du processus de segmentation.</span><span class="sxs-lookup"><span data-stu-id="6e45b-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="6e45b-199">Cette option est particulièrement utile lorsque vous définissez des conditions sur différentes entités.</span><span class="sxs-lookup"><span data-stu-id="6e45b-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="6e45b-200">Opérateur **OU** : L’une ou l’autre des conditions doit être satisfaite dans le cadre de le processus de segmentation.</span><span class="sxs-lookup"><span data-stu-id="6e45b-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="6e45b-201">Cette option est très utile lorsque vous définissez plusieurs conditions pour la même entité.</span><span class="sxs-lookup"><span data-stu-id="6e45b-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6e45b-202">![Opérateur OU où l’une ou l’autre des conditions doit être remplie](media/segmentation-either-condition.png "Opérateur OU où l’une ou l’autre des conditions doit être remplie")</span><span class="sxs-lookup"><span data-stu-id="6e45b-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="6e45b-203">Il est actuellement possible d’imbriquer un opérateur **OU** sous un opérateur **ET**, mais pas l’inverse.</span><span class="sxs-lookup"><span data-stu-id="6e45b-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="6e45b-204">Combiner plusieurs groupes</span><span class="sxs-lookup"><span data-stu-id="6e45b-204">Combine multiple groups</span></span>

<span data-ttu-id="6e45b-205">Chaque produit groupe un ensemble spécifique de clients.</span><span class="sxs-lookup"><span data-stu-id="6e45b-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="6e45b-206">Vous pouvez combiner ces groupes pour inclure les clients requis pour votre étude de cas.</span><span class="sxs-lookup"><span data-stu-id="6e45b-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="6e45b-207">Dans les informations sur l’audience, accédez à la page **Segments** et sélectionnez un segment.</span><span class="sxs-lookup"><span data-stu-id="6e45b-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="6e45b-208">Sélectionnez **Ajouter un groupe**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6e45b-209">![Groupe de clients - Ajouter un groupe](media/customer-group-add-group.png "Groupe de clients - Ajouter un groupe")</span><span class="sxs-lookup"><span data-stu-id="6e45b-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="6e45b-210">Sélectionnez l’un des opérateurs d’ensemble suivants : **Union**, **Intersection** ou **Exception**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6e45b-211">![Groupe de clients - Ajouter une union](media/customer-group-union.png "Groupe de clients - Ajouter une union")</span><span class="sxs-lookup"><span data-stu-id="6e45b-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="6e45b-212">Sélectionnez un opérateur configuré pour définir un nouveau groupe.</span><span class="sxs-lookup"><span data-stu-id="6e45b-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="6e45b-213">Enregistrez différents groupes pour déterminer quelles données sont conservées :</span><span class="sxs-lookup"><span data-stu-id="6e45b-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="6e45b-214">**Union** unit les deux groupes.</span><span class="sxs-lookup"><span data-stu-id="6e45b-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="6e45b-215">**Intersection** fait se chevaucher les deux groupes.</span><span class="sxs-lookup"><span data-stu-id="6e45b-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="6e45b-216">Seules les données qui *sont communes* aux deux groupes sont conservées dans le groupe unifié.</span><span class="sxs-lookup"><span data-stu-id="6e45b-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="6e45b-217">**Exception** combine les deux groupes.</span><span class="sxs-lookup"><span data-stu-id="6e45b-217">**Except** combines the two groups.</span></span> <span data-ttu-id="6e45b-218">Seules les données du groupe A qui *ne sont pas communes* aux données du groupe B sont conservées.</span><span class="sxs-lookup"><span data-stu-id="6e45b-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="6e45b-219">Afficher l’historique de traitement et les membres du segment</span><span class="sxs-lookup"><span data-stu-id="6e45b-219">View processing history and segment members</span></span>

<span data-ttu-id="6e45b-220">Vous pouvez voir les données consolidées d’un segment en examinant ses détails.</span><span class="sxs-lookup"><span data-stu-id="6e45b-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="6e45b-221">Dans la page **Segments**, sélectionnez le segment à vérifier.</span><span class="sxs-lookup"><span data-stu-id="6e45b-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="6e45b-222">La partie supérieure de la page comprend un graphique de tendance qui indique l’évolution du nombre des membres.</span><span class="sxs-lookup"><span data-stu-id="6e45b-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="6e45b-223">Passez la souris sur les points de données pour voir le nombre de membres à une date spécifique.</span><span class="sxs-lookup"><span data-stu-id="6e45b-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="6e45b-224">Vous pouvez mettre à jour le délai d’exécution de la visualisation.</span><span class="sxs-lookup"><span data-stu-id="6e45b-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6e45b-225">![Intervalle de temps du segment](media/segment-time-range.png "Intervalle de temps du segment")</span><span class="sxs-lookup"><span data-stu-id="6e45b-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="6e45b-226">La partie inférieure contient la liste des membres du segment.</span><span class="sxs-lookup"><span data-stu-id="6e45b-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="6e45b-227">Les champs qui apparaissent dans cette liste sont basés sur les attributs des entités de votre segment.</span><span class="sxs-lookup"><span data-stu-id="6e45b-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="6e45b-228">La liste est un aperçu des membres du segment correspondant et affiche les 100 premiers enregistrements de votre segment afin que vous puissiez rapidement l’évaluer et revoir ses définitions si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="6e45b-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="6e45b-229">Pour voir tous les enregistrements correspondants, vous devez [exporter le segment](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6e45b-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="6e45b-230">Segments rapides</span><span class="sxs-lookup"><span data-stu-id="6e45b-230">Quick segments</span></span>

<span data-ttu-id="6e45b-231">Outre le générateur de segments, il existe un autre moyen de créer des segments.</span><span class="sxs-lookup"><span data-stu-id="6e45b-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="6e45b-232">Les segments rapides vous permettent de créer des segments simples (avec un seul opérateur) rapidement et avec des informations instantanées.</span><span class="sxs-lookup"><span data-stu-id="6e45b-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="6e45b-233">Sur la page **Segments**, sélectionnez **Nouveau** > **Création rapide depuis**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="6e45b-234">Sélectionnez l’option **Profils** pour créer un segment basé sur l’entité Client unifiée.</span><span class="sxs-lookup"><span data-stu-id="6e45b-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="6e45b-235">Sélectionnez l’option **Mesures** pour créer un segment pour chaque type Attribut de client des mesures que vous avez précédemment créées dans la page **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="6e45b-236">Sélectionnez l’option **Intelligence** pour créer un segment autour de l’une des entités de sortie que vous avez générées à l’aide des fonctionnalités **Prédictions** ou **Modèles personnalisés**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="6e45b-237">Dans la boîte de dialogue **Nouveau segment rapide**, sélectionnez un attribut dans la liste déroulante **Champ**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="6e45b-238">Le système fournit des informations supplémentaires qui vous permettent de créer de meilleurs segments de vos clients.</span><span class="sxs-lookup"><span data-stu-id="6e45b-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="6e45b-239">Pour les champs de catégorie, nous affichons les 10 meilleurs clients.</span><span class="sxs-lookup"><span data-stu-id="6e45b-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="6e45b-240">Choisissez une **Valeur** et sélectionnez **Réviser**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="6e45b-241">Pour un attribut numérique, le système affiche la valeur d’attribut correspondant au centile de chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6e45b-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="6e45b-242">Choisissez un **Opérateur** et une **Valeur**, puis sélectionnez **Réviser**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="6e45b-243">Le système vous fournira une **taille estimée du segment**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="6e45b-244">Vous pouvez choisir de générer le segment que vous avez défini ou de le revoir pour obtenir une taille de segment différente.</span><span class="sxs-lookup"><span data-stu-id="6e45b-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6e45b-245">![Nom et estimation pour un segment rapide](media/quick-segment-name.png "Nom et estimation pour un segment rapide")</span><span class="sxs-lookup"><span data-stu-id="6e45b-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="6e45b-246">Fournissez un **Nom** pour votre segment.</span><span class="sxs-lookup"><span data-stu-id="6e45b-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="6e45b-247">Indiquez éventuellement un **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="6e45b-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="6e45b-248">Sélectionnez **Enregistrer** pour créer votre segment.</span><span class="sxs-lookup"><span data-stu-id="6e45b-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="6e45b-249">Une fois le segment terminé, vous pouvez l’afficher comme tout autre segment que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="6e45b-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="6e45b-250">Pour les scénarios suivants, nous vous conseillons d’utiliser le générateur de segments plutôt que la capacité de segments recommandée :</span><span class="sxs-lookup"><span data-stu-id="6e45b-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="6e45b-251">Création de segments avec des filtres sur des champs de catégorie où l’opérateur est différent de l’opérateur **Est**</span><span class="sxs-lookup"><span data-stu-id="6e45b-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="6e45b-252">Création de segments avec des filtres sur des champs numériques où l’opérateur est différent des opérateurs **Entre**, **Supérieur à** et **Inférieur à**</span><span class="sxs-lookup"><span data-stu-id="6e45b-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="6e45b-253">Création de segments avec des filtres sur des champs de type Date</span><span class="sxs-lookup"><span data-stu-id="6e45b-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="6e45b-254">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="6e45b-254">Next steps</span></span>

<span data-ttu-id="6e45b-255">[Exportez un segment](export-destinations.md) et explorer la [carte client](customer-card-add-in.md) et les [connecteurs](export-power-bi.md) pour obtenir des informations sur le niveau du client.</span><span class="sxs-lookup"><span data-stu-id="6e45b-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]