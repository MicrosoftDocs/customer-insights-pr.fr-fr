---
title: Segments dans les informations sur l’audience
description: Présentation des segments, de leur création et de leur gestion.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6cb7bd62bf0f61e6dc5811b20e5011e4a086c743
ms.sourcegitcommit: 84283d523a891298fca8aaf629d9f9ab2a1bc067
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111384"
---
# <a name="segments-overview"></a><span data-ttu-id="ff8a0-103">Vue d’ensemble des segments</span><span class="sxs-lookup"><span data-stu-id="ff8a0-103">Segments overview</span></span>

<span data-ttu-id="ff8a0-104">Les segments vous permettent de regrouper vos clients en fonction des attributs démographiques, transactionnels ou comportementaux.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="ff8a0-105">Vous pouvez utiliser les segments pour cibler les campagnes promotionnelles, les activités commerciales et les actions de support client pour atteindre vos objectifs commerciaux.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="ff8a0-106">Les profils client qui correspondent aux filtres d’une définition de segment sont appelés *membres* d’un segment.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="ff8a0-107">Certaines [limites du service](service-limits.md) s’appliquent.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="ff8a0-108">Créer un segment</span><span class="sxs-lookup"><span data-stu-id="ff8a0-108">Create a new segment</span></span>

<span data-ttu-id="ff8a0-109">Il existe plusieurs façons de créer un segment :</span><span class="sxs-lookup"><span data-stu-id="ff8a0-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="ff8a0-110">Segment complexe avec générateur de segments : [segment vide](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="ff8a0-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="ff8a0-111">Segments simples avec un seul opérateur : [segment rapide](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="ff8a0-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="ff8a0-112">Moyen optimisé par l’IA pour trouver des clients similaires : [clients similaires](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="ff8a0-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="ff8a0-113">Suggestions basées sur l’IA à partir de mesures ou d’attributs : [segments suggérés pour améliorer les mesures](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="ff8a0-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="ff8a0-114">Suggestions basées sur les activités : [segments suggérés en fonction de l’activité des clients](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="ff8a0-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="ff8a0-115">Gérer les segments existants</span><span class="sxs-lookup"><span data-stu-id="ff8a0-115">Manage existing segments</span></span>

<span data-ttu-id="ff8a0-116">Accédez à la page **Segments** pour afficher tous vos segments enregistrés et les gérer.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="ff8a0-117">Chaque segment est représenté par une ligne qui contient des informations supplémentaires sur le segment.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segment sélectionné avec liste déroulante d'options et options disponibles.":::

<span data-ttu-id="ff8a0-119">L’action suivante est disponible lorsque vous sélectionnez un segment :</span><span class="sxs-lookup"><span data-stu-id="ff8a0-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="ff8a0-120">**Afficher** les détails du segment, y compris un aperçu de la tendance du nombre de membres du segment.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="ff8a0-121">**Modifier** le segment pour modifier ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="ff8a0-122">**Créez un doublon** d’un segment.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="ff8a0-123">Vous pouvez choisir de modifier ses propriétés immédiatement ou simplement d’enregistrer le doublon.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="ff8a0-124">**Actualiser** le segment pour inclure les dernières données.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="ff8a0-125">**Activer** ou **Désactiver** le segment.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="ff8a0-126">Les segments ont deux états possibles : actif ou inactif.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="ff8a0-127">Ces états sont utiles lors de l’édition d’un segment.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="ff8a0-128">Pour les segments inactifs, la définition de segment existe, mais elle ne contient pas encore de clients.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="ff8a0-129">Lorsque vous activez un segment, son état passe de « inactif » à « actif » et il commence à rechercher des clients qui correspondent à la définition du segment.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="ff8a0-130">Si une [actualisation programmée](system.md#schedule-tab) est configurée, les segments inactifs ont leur **Statut** répertorié comme **Ignoré**, indiquant qu’une actualisation n’a même pas été tentée.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="ff8a0-131">Lorsqu’un segment inactif est activé, il s’actualise et sera inclus dans les actualisations programmées.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="ff8a0-132">Vous pouvez également utiliser la fonctionnalité **Planifier plus tard** dans la liste déroulante **Activer/Désactiver** pour spécifier une date et une heure futures d’activation et de désactivation d’un segment particulier.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="ff8a0-133">**Renommer** le segment.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-133">**Rename** the segment.</span></span>
- <span data-ttu-id="ff8a0-134">**Télécharger** la liste des membres en tant que fichier .CSV.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="ff8a0-135">**Gérer les exportations** pour voir le segment lié aux exportations et les gérer.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="ff8a0-136">En savoir plus sur les exportations</span><span class="sxs-lookup"><span data-stu-id="ff8a0-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="ff8a0-137">**Supprimer** le segment.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="ff8a0-138">Actualiser des segments</span><span class="sxs-lookup"><span data-stu-id="ff8a0-138">Refresh segments</span></span>

<span data-ttu-id="ff8a0-139">Vous pouvez actualiser tous les segments à la fois en sélectionnant **Actualiser tout** sur la page **Segments** ou vous pouvez actualiser un ou plusieurs segments lorsque vous les sélectionnez et choisissez **Actualiser** dans les options.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="ff8a0-140">Vous pouvez également configurer une actualisation périodique en cliquant sur **Administrateur** > **Système** > **Planifier**.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="ff8a0-141">Il existe [six types de statuts](system.md#status-types) pour les tâches/processus.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="ff8a0-142">En outre, la plupart des processus [dépendent d’autres processus en aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="ff8a0-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="ff8a0-143">Vous pouvez sélectionner le statut d’un processus pour afficher des détails sur la progression de toute la tâche.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="ff8a0-144">Après avoir sélectionné **Voir les détails** pour l’une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="ff8a0-145">Exporter les segments</span><span class="sxs-lookup"><span data-stu-id="ff8a0-145">Export segments</span></span>

<span data-ttu-id="ff8a0-146">Vous pouvez exporter un segment à partir de la page des segments ou de la [page des exportations](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ff8a0-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="ff8a0-147">Accédez à la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="ff8a0-148">Sélectionnez **Afficher plus [...]** pour le segment que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="ff8a0-149">Sélectionnez **Gérer les exportations** dans la liste déroulante des actions.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-149">Select **Manage exports** from the actions drop-down list.</span></span>

1. <span data-ttu-id="ff8a0-150">La page **Exportations du segment (aperçu)** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="ff8a0-151">Vous pouvez voir toutes les exportations configurées regroupées par exportations qui contiennent le segment actuel ou qui ne le contiennent pas.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="ff8a0-152">Pour ajouter le segment sélectionné à une exportation, sélectionnez l'exportation dans la liste et sélectionnez **Ajouter un segment**.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="ff8a0-153">Pour créer une nouvelle exportation avec le segment sélectionné, sélectionnez **Ajouter une exportation**.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="ff8a0-154">Pour plus d'informations sur la création d'exportations, consultez [Configurer une nouvelle exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ff8a0-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ff8a0-155">Sélectionnez **Précédent** pour revenir à la page principale des segments.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="ff8a0-156">Afficher l’historique de traitement et les membres du segment</span><span class="sxs-lookup"><span data-stu-id="ff8a0-156">View processing history and segment members</span></span>

<span data-ttu-id="ff8a0-157">Vous pouvez voir les données consolidées d’un segment en examinant ses détails.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="ff8a0-158">Dans la page **Segments**, sélectionnez le segment à vérifier.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="ff8a0-159">La partie supérieure de la page comprend un graphique de tendance qui indique l’évolution du nombre des membres.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="ff8a0-160">Passez la souris sur les points de données pour voir le nombre de membres à une date spécifique.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="ff8a0-161">Vous pouvez mettre à jour le délai d’exécution de la visualisation.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ff8a0-162">![Intervalle de temps du segment](media/segment-time-range.png "Intervalle de temps du segment")</span><span class="sxs-lookup"><span data-stu-id="ff8a0-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="ff8a0-163">La partie inférieure contient la liste des membres du segment.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="ff8a0-164">Les champs qui apparaissent dans cette liste sont basés sur les attributs des entités de votre segment.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="ff8a0-165">La liste est un aperçu des membres du segment correspondant et affiche les 100 premiers enregistrements de votre segment afin que vous puissiez rapidement l’évaluer et revoir ses définitions si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="ff8a0-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="ff8a0-166">Pour voir tous les enregistrements correspondants, vous devez [exporter le segment](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ff8a0-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
