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
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253037"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="14417-103">Vue d’ensemble des exportations (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="14417-103">Exports (preview) overview</span></span>

<span data-ttu-id="14417-104">La page **Exportations** affiche toutes les exportations configurées.</span><span class="sxs-lookup"><span data-stu-id="14417-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="14417-105">Les exportations partagent des données spécifiques avec diverses applications.</span><span class="sxs-lookup"><span data-stu-id="14417-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="14417-106">Elles peuvent inclure des profils ou entités client, des schémas et des détails de mappage.</span><span class="sxs-lookup"><span data-stu-id="14417-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="14417-107">Chaque exportation nécessite une [connexion, configurée par un administrateur, pour gérer l’authentification et l’accès](connections.md).</span><span class="sxs-lookup"><span data-stu-id="14417-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="14417-108">Accédez à **Données** > **Exportations** pour afficher la page des exportations.</span><span class="sxs-lookup"><span data-stu-id="14417-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="14417-109">Tous les rôles d’utilisateur ont accès pour afficher les exportations configurées.</span><span class="sxs-lookup"><span data-stu-id="14417-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="14417-110">Utilisez le champ de recherche dans la barre de commandes pour rechercher des exportations par leur nom, nom de connexion ou type de connexion.</span><span class="sxs-lookup"><span data-stu-id="14417-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="14417-111">Configurer une nouvelle exportation</span><span class="sxs-lookup"><span data-stu-id="14417-111">Set up a new export</span></span>

<span data-ttu-id="14417-112">Pour configurer ou modifier une exportation, vous devez avoir des connexions disponibles.</span><span class="sxs-lookup"><span data-stu-id="14417-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="14417-113">Les connexions dépendent de votre [rôle d’utilisateur](permissions.md) :</span><span class="sxs-lookup"><span data-stu-id="14417-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="14417-114">Les administrateurs ont accès à toutes les connexions.</span><span class="sxs-lookup"><span data-stu-id="14417-114">Administrators have access to all connections.</span></span> <span data-ttu-id="14417-115">Ils peuvent également créer de nouvelles connexions lors de la configuration d’une exportation.</span><span class="sxs-lookup"><span data-stu-id="14417-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="14417-116">Les contributeurs peuvent avoir accès à des connexions spécifiques.</span><span class="sxs-lookup"><span data-stu-id="14417-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="14417-117">Ils dépendent des administrateurs pour configurer et partager des connexions.</span><span class="sxs-lookup"><span data-stu-id="14417-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="14417-118">La liste des exportations indique aux contributeurs s'ils peuvent modifier ou uniquement afficher une exportation dans la colonne **Vos autorisations**.</span><span class="sxs-lookup"><span data-stu-id="14417-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="14417-119">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="14417-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="14417-120">Les utilisateurs peuvent uniquement afficher les exportations existantes, mais pas les créer.</span><span class="sxs-lookup"><span data-stu-id="14417-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="14417-121">Définir une nouvelle exportation</span><span class="sxs-lookup"><span data-stu-id="14417-121">Define a new export</span></span>

1. <span data-ttu-id="14417-122">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="14417-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="14417-123">Sélectionnez **Ajouter une exportation** pour créer une nouvelle exportation.</span><span class="sxs-lookup"><span data-stu-id="14417-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="14417-124">Dans le volet **Configurer l’exportation**, sélectionnez la connexion à utiliser.</span><span class="sxs-lookup"><span data-stu-id="14417-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="14417-125">Les [Connexions](connections.md) sont gérées par les administrateurs.</span><span class="sxs-lookup"><span data-stu-id="14417-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="14417-126">Fournissez les détails nécessaires et sélectionnez **Enregistrer** pour créer l’exportation.</span><span class="sxs-lookup"><span data-stu-id="14417-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="14417-127">Définir une nouvelle exportation basée sur une exportation existante</span><span class="sxs-lookup"><span data-stu-id="14417-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="14417-128">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="14417-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="14417-129">Dans la liste des exportations, sélectionnez l’exportation que vous souhaitez dupliquer.</span><span class="sxs-lookup"><span data-stu-id="14417-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="14417-130">Sélectionnez **Créer un doublon** dans la barre de commandes pour ouvrir le volet **Configurer l'exportation** avec les détails de l'exportation sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="14417-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="14417-131">Vérifiez et adaptez l'exportation et sélectionnez **Enregistrer** pour créer une exportation.</span><span class="sxs-lookup"><span data-stu-id="14417-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="14417-132">Modifier une exportation</span><span class="sxs-lookup"><span data-stu-id="14417-132">Edit an export</span></span>

1. <span data-ttu-id="14417-133">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="14417-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="14417-134">Dans la liste des exportations, sélectionnez l’exportation que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="14417-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="14417-135">Sélectionnez **Modifier** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="14417-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="14417-136">Modifiez les valeurs que vous souhaitez mettre à jour et sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="14417-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="14417-137">Afficher les exportations et les détails de l’exportation</span><span class="sxs-lookup"><span data-stu-id="14417-137">View exports and export details</span></span>

<span data-ttu-id="14417-138">Une fois les destinations d’exportation créées, elles sont répertoriées dans **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="14417-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="14417-139">Tous les utilisateurs peuvent voir les données partagées et leur statut le plus récent.</span><span class="sxs-lookup"><span data-stu-id="14417-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="14417-140">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="14417-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="14417-141">Les utilisateurs sans autorisations de modification sélectionnent **Afficher** au lieu de **Modifier** pour voir les détails de l’exportation.</span><span class="sxs-lookup"><span data-stu-id="14417-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="14417-142">Le volet latéral montre la configuration d'une exportation.</span><span class="sxs-lookup"><span data-stu-id="14417-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="14417-143">Sans autorisations de modification, vous ne pouvez pas modifier les valeurs.</span><span class="sxs-lookup"><span data-stu-id="14417-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="14417-144">Sélectionnez **Fermer** pour revenir à la page des exportations.</span><span class="sxs-lookup"><span data-stu-id="14417-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="14417-145">Planifier et exécuter les exportations</span><span class="sxs-lookup"><span data-stu-id="14417-145">Schedule and run exports</span></span>

<span data-ttu-id="14417-146">Chaque exportation que vous configurez comporte une planification d’actualisation.</span><span class="sxs-lookup"><span data-stu-id="14417-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="14417-147">Lors d'une actualisation, le système recherche des données nouvelles ou mises à jour à inclure dans une exportation.</span><span class="sxs-lookup"><span data-stu-id="14417-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="14417-148">Par défaut, les exportations sont exécutées dans le cadre de chaque [actualisation du système planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="14417-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="14417-149">Vous pouvez personnaliser la planification d’actualisation ou la désactiver pour exécuter les exportations manuellement.</span><span class="sxs-lookup"><span data-stu-id="14417-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="14417-150">Les planifications d'exportation dépendent de l'état de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="14417-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="14417-151">S'il y a des mises à jour sur des [dépendances](system.md#refresh-policies) en cours lorsqu'une exportation planifiée doit démarrer, le système terminera d'abord les dépendances, puis exécutera l'exportation.</span><span class="sxs-lookup"><span data-stu-id="14417-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="14417-152">Vous pouvez consulter les informations relatives à la dernière actualisation d'une exportation dans la colonne **Actualisé**.</span><span class="sxs-lookup"><span data-stu-id="14417-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="14417-153">Panifier des exportations</span><span class="sxs-lookup"><span data-stu-id="14417-153">Schedule exports</span></span>

<span data-ttu-id="14417-154">Vous pouvez définir des planifications d’actualisation personnalisées pour des exportations individuelles ou plusieurs exportations à la fois.</span><span class="sxs-lookup"><span data-stu-id="14417-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="14417-155">La planification actuellement définie est répertoriée dans la colonne **Planifier** de la liste d'exportations.</span><span class="sxs-lookup"><span data-stu-id="14417-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="14417-156">L'autorisation nécessaire pour modifier la planification est la même que pour [modifier et définir des exportations](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="14417-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="14417-157">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="14417-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="14417-158">Sélectionnez l'exportation à planifier.</span><span class="sxs-lookup"><span data-stu-id="14417-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="14417-159">Sélectionnez **Planifier** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="14417-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="14417-160">Dans le volet **Planifier l'exportation**, définissez l'option **Planifier l'exécution** sur **Activé** pour exécuter l'exportation automatiquement.</span><span class="sxs-lookup"><span data-stu-id="14417-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="14417-161">Définissez l'option sur **Désactivé** pour une actualisation manuelle.</span><span class="sxs-lookup"><span data-stu-id="14417-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="14417-162">Pour que les exportations soient actualisées automatiquement, choisissez une valeur **Périodicité** et spécifiez les détails de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="14417-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="14417-163">Le temps défini s'applique à toutes les instances d'une périodicité.</span><span class="sxs-lookup"><span data-stu-id="14417-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="14417-164">C'est le moment où l'actualisation d'une exportation doit commencer.</span><span class="sxs-lookup"><span data-stu-id="14417-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="14417-165">Appliquez et activez vos modifications en sélectionnant **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="14417-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="14417-166">Lorsque vous modifiez la planification de plusieurs exportations, vous devez effectuer une sélection sous **Conserver ou remplacer les planifications** :</span><span class="sxs-lookup"><span data-stu-id="14417-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="14417-167">**Conserver les planifications individuelles** : conserver la planification précédemment définie pour les exportations sélectionnées et uniquement les désactiver ou les activer.</span><span class="sxs-lookup"><span data-stu-id="14417-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="14417-168">**Définir une nouvelle planification pour toutes les exportations sélectionnées** : remplacer les planifications existantes des exportations sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="14417-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="14417-169">Exécuter des exportations à la demande</span><span class="sxs-lookup"><span data-stu-id="14417-169">Run exports on demand</span></span>

<span data-ttu-id="14417-170">Pour exporter des données sans attendre une actualisation planifiée, accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="14417-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="14417-171">Pour exécuter toutes les exportations, sélectionnez **Tout exécuter** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="14417-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="14417-172">Cette action n'exécutera que les exportations ayant une planification active.</span><span class="sxs-lookup"><span data-stu-id="14417-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="14417-173">Pour exécuter une seule exportation, sélectionnez-la dans la liste et sélectionnez **Exécuter** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="14417-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="14417-174">C'est de cette manière que vous exécutez les exportations sans planification active.</span><span class="sxs-lookup"><span data-stu-id="14417-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="14417-175">Supprimer une exportation</span><span class="sxs-lookup"><span data-stu-id="14417-175">Remove an Export</span></span>

1. <span data-ttu-id="14417-176">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="14417-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="14417-177">Sélectionnez l'exportation à supprimer.</span><span class="sxs-lookup"><span data-stu-id="14417-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="14417-178">Sélectionnez **Supprimer** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="14417-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="14417-179">Confirmez la suppression en sélectionnant **Supprimer** sur l’écran de confirmation.</span><span class="sxs-lookup"><span data-stu-id="14417-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
