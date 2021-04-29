---
title: Exporter des données de Customer Insights
description: Gérez les exportations pour partager des données.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896140"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="c9188-103">Vue d’ensemble des exportations (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="c9188-103">Exports (preview) overview</span></span>

<span data-ttu-id="c9188-104">La page **Exportations** affiche toutes les exportations configurées.</span><span class="sxs-lookup"><span data-stu-id="c9188-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="c9188-105">Les exportations partagent des données spécifiques avec diverses applications.</span><span class="sxs-lookup"><span data-stu-id="c9188-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="c9188-106">Elles peuvent inclure des profils ou entités client, des schémas et des détails de mappage.</span><span class="sxs-lookup"><span data-stu-id="c9188-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="c9188-107">Chaque exportation nécessite une [connexion, configurée par un administrateur, pour gérer l’authentification et l’accès](connections.md).</span><span class="sxs-lookup"><span data-stu-id="c9188-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c9188-108">Jusqu’en mars 2021, les exportations créaient automatiquement une connexion au service correspondant.</span><span class="sxs-lookup"><span data-stu-id="c9188-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="c9188-109">Les exportations nécessitent désormais une [connexion créée et partagée par un administrateur](connections.md) avant de pouvoir les créer.</span><span class="sxs-lookup"><span data-stu-id="c9188-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="c9188-110">Accédez à **Données** > **Exportations** pour afficher la page des exportations.</span><span class="sxs-lookup"><span data-stu-id="c9188-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="c9188-111">Tous les rôles d’utilisateur ont accès pour afficher les exportations configurées.</span><span class="sxs-lookup"><span data-stu-id="c9188-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="c9188-112">Utilisez le champ de recherche dans la barre de commandes pour rechercher des exportations par leur nom, nom de connexion ou type de connexion.</span><span class="sxs-lookup"><span data-stu-id="c9188-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="c9188-113">Configurer une nouvelle exportation</span><span class="sxs-lookup"><span data-stu-id="c9188-113">Set up a new export</span></span>

<span data-ttu-id="c9188-114">Pour configurer ou modifier une exportation, vous devez avoir des connexions disponibles.</span><span class="sxs-lookup"><span data-stu-id="c9188-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="c9188-115">Les connexions dépendent de votre [rôle d’utilisateur](permissions.md) :</span><span class="sxs-lookup"><span data-stu-id="c9188-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="c9188-116">Les administrateurs ont accès à toutes les connexions.</span><span class="sxs-lookup"><span data-stu-id="c9188-116">Administrators have access to all connections.</span></span> <span data-ttu-id="c9188-117">Ils peuvent également créer de nouvelles connexions lors de la configuration d’une exportation.</span><span class="sxs-lookup"><span data-stu-id="c9188-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="c9188-118">Les contributeurs peuvent avoir accès à des connexions spécifiques.</span><span class="sxs-lookup"><span data-stu-id="c9188-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="c9188-119">Ils dépendent des administrateurs pour configurer et partager des connexions.</span><span class="sxs-lookup"><span data-stu-id="c9188-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="c9188-120">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c9188-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="c9188-121">Les utilisateurs peuvent uniquement afficher les exportations existantes, mais pas les créer.</span><span class="sxs-lookup"><span data-stu-id="c9188-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="c9188-122">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="c9188-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c9188-123">Sélectionnez **Ajouter une exportation** pour créer une nouvelle destination d’exportation.</span><span class="sxs-lookup"><span data-stu-id="c9188-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="c9188-124">Dans le volet **Configurer l’exportation**, sélectionnez la connexion à utiliser.</span><span class="sxs-lookup"><span data-stu-id="c9188-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="c9188-125">Les [Connexions](connections.md) sont gérées par les administrateurs.</span><span class="sxs-lookup"><span data-stu-id="c9188-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="c9188-126">Fournissez les détails nécessaires et sélectionnez **Enregistrer** pour créer l’exportation.</span><span class="sxs-lookup"><span data-stu-id="c9188-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="c9188-127">Modifier une exportation</span><span class="sxs-lookup"><span data-stu-id="c9188-127">Edit an export</span></span>

1. <span data-ttu-id="c9188-128">Sélectionnez les points de suspension de la destination d’exportation que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="c9188-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="c9188-129">Sélectionnez **Modifier** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="c9188-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="c9188-130">Modifiez les valeurs que vous souhaitez mettre à jour et sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c9188-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="c9188-131">Afficher les exportations et les détails de l’exportation</span><span class="sxs-lookup"><span data-stu-id="c9188-131">View Exports and export details</span></span>

<span data-ttu-id="c9188-132">Une fois les destinations d’exportation créées, elles sont répertoriées dans **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="c9188-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="c9188-133">Tous les utilisateurs peuvent voir les données partagées et leur statut le plus récent.</span><span class="sxs-lookup"><span data-stu-id="c9188-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="c9188-134">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="c9188-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c9188-135">Les utilisateurs sans autorisations de modification sélectionnent **Afficher** au lieu de **Modifier** pour voir les détails de l’exportation.</span><span class="sxs-lookup"><span data-stu-id="c9188-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="c9188-136">Ce volet latéral montre la configuration de cette exportation.</span><span class="sxs-lookup"><span data-stu-id="c9188-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="c9188-137">Sans autorisations de modification, vous ne pouvez pas modifier les valeurs.</span><span class="sxs-lookup"><span data-stu-id="c9188-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="c9188-138">Sélectionnez **Fermer** pour revenir à la page des exportations.</span><span class="sxs-lookup"><span data-stu-id="c9188-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="c9188-139">Exécuter des exportations à la demande</span><span class="sxs-lookup"><span data-stu-id="c9188-139">Run exports on demand</span></span>

<span data-ttu-id="c9188-140">Une fois une exportation configurée, elle s’exécutera avec chaque [actualisation planifiée](system.md#schedule-tab) tant qu’une connexion active sera disponible.</span><span class="sxs-lookup"><span data-stu-id="c9188-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="c9188-141">Pour exporter des données sans attendre une actualisation planifiée, accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="c9188-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="c9188-142">Deux options s’offrent à vous :</span><span class="sxs-lookup"><span data-stu-id="c9188-142">You have two options:</span></span>

- <span data-ttu-id="c9188-143">Pour exécuter toutes les exportations, sélectionnez **Tout exécuter** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="c9188-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="c9188-144">Pour exécuter une seule exportation, sélectionnez les points de suspension (...) d’un élément de liste, puis choisissez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c9188-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="c9188-145">Supprimer une exportation</span><span class="sxs-lookup"><span data-stu-id="c9188-145">Remove an Export</span></span>

1. <span data-ttu-id="c9188-146">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="c9188-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c9188-147">Sélectionnez les points de suspension de l’exportation que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="c9188-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="c9188-148">Sélectionnez **Supprimer** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="c9188-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="c9188-149">Confirmez la suppression en sélectionnant **Supprimer** sur l’écran de confirmation.</span><span class="sxs-lookup"><span data-stu-id="c9188-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
