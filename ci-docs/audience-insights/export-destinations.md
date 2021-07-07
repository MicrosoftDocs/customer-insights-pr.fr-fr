---
title: Exporter des données de Customer Insights
description: Gérez les exportations pour partager des données.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305475"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="0f6aa-103">Vue d’ensemble des exportations (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="0f6aa-103">Exports (preview) overview</span></span>

<span data-ttu-id="0f6aa-104">La page **Exportations** affiche toutes les exportations configurées.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="0f6aa-105">Les exportations partagent des données spécifiques avec diverses applications.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="0f6aa-106">Elles peuvent inclure des profils ou entités client, des schémas et des détails de mappage.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="0f6aa-107">Chaque exportation nécessite une [connexion, configurée par un administrateur, pour gérer l’authentification et l’accès](connections.md).</span><span class="sxs-lookup"><span data-stu-id="0f6aa-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="0f6aa-108">Accédez à **Données** > **Exportations** pour afficher la page des exportations.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="0f6aa-109">Tous les rôles d’utilisateur peuvent afficher les exportations configurées.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-109">All user roles can view configured exports.</span></span> <span data-ttu-id="0f6aa-110">Utilisez le champ de recherche dans la barre de commandes pour rechercher des exportations par leur nom, nom de connexion ou type de connexion.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="0f6aa-111">Configurer une nouvelle exportation</span><span class="sxs-lookup"><span data-stu-id="0f6aa-111">Set up a new export</span></span>

<span data-ttu-id="0f6aa-112">Pour configurer ou modifier une exportation, vous devez avoir des connexions disponibles.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="0f6aa-113">Les connexions dépendent de votre [rôle d’utilisateur](permissions.md) :</span><span class="sxs-lookup"><span data-stu-id="0f6aa-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="0f6aa-114">Les administrateurs ont accès à toutes les connexions.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-114">Administrators have access to all connections.</span></span> <span data-ttu-id="0f6aa-115">Ils peuvent également créer de nouvelles connexions lors de la configuration d’une exportation.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="0f6aa-116">Les contributeurs peuvent avoir accès à des connexions spécifiques.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="0f6aa-117">Ils dépendent des administrateurs pour configurer et partager des connexions.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="0f6aa-118">La liste des exportations indique aux contributeurs s'ils peuvent modifier ou uniquement afficher une exportation dans la colonne **Vos autorisations**.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="0f6aa-119">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0f6aa-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="0f6aa-120">Les utilisateurs peuvent uniquement afficher les exportations existantes, mais pas les créer.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="0f6aa-121">Définir une nouvelle exportation</span><span class="sxs-lookup"><span data-stu-id="0f6aa-121">Define a new export</span></span>

1. <span data-ttu-id="0f6aa-122">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0f6aa-123">Sélectionnez **Ajouter une exportation** pour créer une nouvelle exportation.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="0f6aa-124">Dans le volet **Configurer l’exportation**, sélectionnez la connexion à utiliser.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="0f6aa-125">Les [Connexions](connections.md) sont gérées par les administrateurs.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="0f6aa-126">Fournissez les détails nécessaires et sélectionnez **Enregistrer** pour créer l’exportation.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="0f6aa-127">Définir une nouvelle exportation basée sur une exportation existante</span><span class="sxs-lookup"><span data-stu-id="0f6aa-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="0f6aa-128">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0f6aa-129">Dans la liste des exportations, sélectionnez l’exportation que vous souhaitez dupliquer.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="0f6aa-130">Sélectionnez **Créer un doublon** dans la barre de commandes pour ouvrir le volet **Configurer l'exportation** avec les détails de l'exportation sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="0f6aa-131">Vérifiez et adaptez l'exportation et sélectionnez **Enregistrer** pour créer une exportation.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="0f6aa-132">Modifier une exportation</span><span class="sxs-lookup"><span data-stu-id="0f6aa-132">Edit an export</span></span>

1. <span data-ttu-id="0f6aa-133">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0f6aa-134">Dans la liste des exportations, sélectionnez l’exportation que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="0f6aa-135">Sélectionnez **Modifier** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="0f6aa-136">Modifiez les valeurs que vous souhaitez mettre à jour et sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="0f6aa-137">Afficher les exportations et les détails de l’exportation</span><span class="sxs-lookup"><span data-stu-id="0f6aa-137">View exports and export details</span></span>

<span data-ttu-id="0f6aa-138">Une fois les destinations d’exportation créées, elles sont répertoriées dans **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="0f6aa-139">Tous les utilisateurs peuvent voir les données partagées et leur statut le plus récent.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="0f6aa-140">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0f6aa-141">Les utilisateurs sans autorisations de modification sélectionnent **Afficher** au lieu de **Modifier** pour voir les détails de l’exportation.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="0f6aa-142">Le volet latéral montre la configuration d'une exportation.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="0f6aa-143">Sans autorisations de modification, vous ne pouvez pas modifier les valeurs.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="0f6aa-144">Sélectionnez **Fermer** pour revenir à la page des exportations.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="0f6aa-145">Planifier et exécuter les exportations</span><span class="sxs-lookup"><span data-stu-id="0f6aa-145">Schedule and run exports</span></span>

<span data-ttu-id="0f6aa-146">Chaque exportation que vous configurez comporte une planification d’actualisation.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="0f6aa-147">Lors d'une actualisation, le système recherche des données nouvelles ou mises à jour à inclure dans une exportation.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="0f6aa-148">Par défaut, les exportations sont exécutées dans le cadre de chaque [actualisation du système planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0f6aa-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0f6aa-149">Vous pouvez personnaliser la planification d’actualisation ou la désactiver pour exécuter les exportations manuellement.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="0f6aa-150">Les planifications d'exportation dépendent de l'état de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="0f6aa-151">Si des mises à jour sont en cours sur les [dépendances](system.md#refresh-policies) lorsqu’une exportation planifiée doit commencer, le système finalisera d’abord les mises à jour, puis exécutera l’exportation.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="0f6aa-152">Vous pouvez consulter les informations relatives à la dernière actualisation d'une exportation dans la colonne **Actualisé**.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="0f6aa-153">Panifier des exportations</span><span class="sxs-lookup"><span data-stu-id="0f6aa-153">Schedule exports</span></span>

<span data-ttu-id="0f6aa-154">Vous pouvez définir des planifications d’actualisation personnalisées pour des exportations individuelles ou plusieurs exportations à la fois.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="0f6aa-155">La planification actuellement définie est répertoriée dans la colonne **Planifier** de la liste d'exportations.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="0f6aa-156">L'autorisation nécessaire pour modifier la planification est la même que pour [modifier et définir des exportations](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0f6aa-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="0f6aa-157">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0f6aa-158">Sélectionnez l'exportation à planifier.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="0f6aa-159">Sélectionnez **Planifier** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="0f6aa-160">Dans le volet **Planifier l'exportation**, définissez l'option **Planifier l'exécution** sur **Activé** pour exécuter l'exportation automatiquement.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="0f6aa-161">Définissez l'option sur **Désactivé** pour une actualisation manuelle.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="0f6aa-162">Pour que les exportations soient actualisées automatiquement, choisissez une valeur **Périodicité** et spécifiez les détails de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="0f6aa-163">Le temps défini s'applique à toutes les instances d'une périodicité.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="0f6aa-164">C'est le moment où l'actualisation d'une exportation doit commencer.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="0f6aa-165">Appliquez et activez vos modifications en sélectionnant **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="0f6aa-166">Lorsque vous modifiez la planification de plusieurs exportations, vous devez effectuer une sélection sous **Conserver ou remplacer les planifications** :</span><span class="sxs-lookup"><span data-stu-id="0f6aa-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="0f6aa-167">**Conserver les planifications individuelles** : conserver la planification précédemment définie pour les exportations sélectionnées et uniquement les désactiver ou les activer.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="0f6aa-168">**Définir une nouvelle planification pour toutes les exportations sélectionnées** : remplacer les planifications existantes des exportations sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="0f6aa-169">Exécuter des exportations à la demande</span><span class="sxs-lookup"><span data-stu-id="0f6aa-169">Run exports on demand</span></span>

<span data-ttu-id="0f6aa-170">Pour exporter des données sans attendre une actualisation planifiée, accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="0f6aa-171">Pour exécuter toutes les exportations, sélectionnez **Tout exécuter** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="0f6aa-172">Cette action n'exécutera que les exportations ayant une planification active.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="0f6aa-173">Pour exécuter une seule exportation, sélectionnez-la dans la liste et sélectionnez **Exécuter** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="0f6aa-174">C'est de cette manière que vous exécutez les exportations sans planification active.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="0f6aa-175">Supprimer une exportation</span><span class="sxs-lookup"><span data-stu-id="0f6aa-175">Remove an Export</span></span>

1. <span data-ttu-id="0f6aa-176">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0f6aa-177">Sélectionnez l'exportation à supprimer.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="0f6aa-178">Sélectionnez **Supprimer** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="0f6aa-179">Confirmez la suppression en sélectionnant **Supprimer** sur l’écran de confirmation.</span><span class="sxs-lookup"><span data-stu-id="0f6aa-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
