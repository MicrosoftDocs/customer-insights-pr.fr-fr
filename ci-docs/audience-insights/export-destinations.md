---
title: Destinations d'export
description: Exportez des données et gérez les destinations d'exportation.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643860"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="9c0d9-103">Destinations d'export (aperçu)</span><span class="sxs-lookup"><span data-stu-id="9c0d9-103">Export destinations (preview)</span></span>

<span data-ttu-id="9c0d9-104">La page **Destinations d'exportation** vous indique tous les emplacements que vous avez configurés afin d'y exporter des données.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="9c0d9-105">Vous pouvez également ajouter de nouvelles destinations pour l'exportation.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-105">You can also add new destinations for export.</span></span> <span data-ttu-id="9c0d9-106">De plus, elle affiche les options d'exportation actuellement disponibles.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="9c0d9-107">Obtenez un aperçu rapide, une description et découvrez ce que vous pouvez faire avec chaque option d'extensibilité.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="9c0d9-108">Exportez des profils, des mesures et des segments unifiés vers des applications prises en charge pertinentes pour votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="9c0d9-109">Aller à **Administrateur** > **Exporter des destinations** pour rechercher les options d'extensibilité suivantes :</span><span class="sxs-lookup"><span data-stu-id="9c0d9-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="9c0d9-110">Complément de carte client Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="9c0d9-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="9c0d9-111">Connecteur Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="9c0d9-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="9c0d9-112">Power Automateconnecteur</span><span class="sxs-lookup"><span data-stu-id="9c0d9-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="9c0d9-113">Power Appsconnecteur</span><span class="sxs-lookup"><span data-stu-id="9c0d9-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="9c0d9-114">Power BIconnecteur</span><span class="sxs-lookup"><span data-stu-id="9c0d9-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="9c0d9-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="9c0d9-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="9c0d9-116">Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="9c0d9-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="9c0d9-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="9c0d9-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="9c0d9-118">Stockage Blob Azure</span><span class="sxs-lookup"><span data-stu-id="9c0d9-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="9c0d9-119">Connecteur LiveRamp&reg;</span><span class="sxs-lookup"><span data-stu-id="9c0d9-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="9c0d9-120">Bot pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9c0d9-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="9c0d9-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="9c0d9-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="9c0d9-122">API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9c0d9-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="9c0d9-123">Ajouter une nouvelle destination d'exportation</span><span class="sxs-lookup"><span data-stu-id="9c0d9-123">Add a new export destination</span></span>

<span data-ttu-id="9c0d9-124">Pour ajouter des destinations d'exportation, vous devez avoir des [autorisations administrateur](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9c0d9-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="9c0d9-125">Si vous exportez vers des services Microsoft, nous supposons que les deux services appartiennent à la même organisation.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="9c0d9-126">Accédez à **Administration** > **Destinations d'exportation**.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="9c0d9-127">Passez à l'onglet **Mes destinations d'exportation**.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="9c0d9-128">Sélectionnez **Ajouter une destination** pour créer une destination d'exportation.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="9c0d9-129">Dans le volet **Ajouter une destination**, sélectionnez le **Type** de destination d'exportation dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="9c0d9-130">Fournissez les détails requis et sélectionnez **Suivant** pour créer la destination d'exportation.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="9c0d9-131">Vous pouvez également sélectionner **Configurer** sur une vignette sur l'onglet **Découvrir**.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="9c0d9-132">Afficher les destinations d'exportation</span><span class="sxs-lookup"><span data-stu-id="9c0d9-132">View Export destinations</span></span>

<span data-ttu-id="9c0d9-133">Après avoir créé des destinations d'exportation, vous les trouverez dans un tableau sur l'onglet **Mes destinations d'exportation**. Ce tableau comporte trois colonnes :</span><span class="sxs-lookup"><span data-stu-id="9c0d9-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="9c0d9-134">**Nom complet** : le nom que vous avez entré lors de la création de la destination.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="9c0d9-135">**Type** : Le type de destination d'exportation défini lors de la création de la destination.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="9c0d9-136">**Créée** : la date à laquelle vous avez créé la destination.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="9c0d9-137">Modifier une destination d'exportation</span><span class="sxs-lookup"><span data-stu-id="9c0d9-137">Edit an export destination</span></span>

1. <span data-ttu-id="9c0d9-138">Sélectionnez les points de suspension pour la destination d'exportation que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9c0d9-139">![Ellipses verticales](media/export-destinations-page-ellipsis.png "Ellipses verticales")</span><span class="sxs-lookup"><span data-stu-id="9c0d9-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="9c0d9-140">Sélectionnez **Modifier** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="9c0d9-141">Modifiez les valeurs qui nécessitent une mise à jour et sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="9c0d9-142">Exporter les données à la demande</span><span class="sxs-lookup"><span data-stu-id="9c0d9-142">Export data on demand</span></span>

<span data-ttu-id="9c0d9-143">Après avoir configuré un connecteur pour une destination d'exportation, les exportations s'exécutent avec chaque [actualisation programmée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9c0d9-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="9c0d9-144">Pour exporter des données sans attendre une actualisation planifiée, accédez à l'onglet **Mes destinations d'exportation** sur **Administration** > **Exporter des destinations**.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9c0d9-145">![Ellipses verticales](media/export-destinations-page-ellipsis.png "Ellipses verticales")</span><span class="sxs-lookup"><span data-stu-id="9c0d9-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="9c0d9-146">Sélectionnez **Exporter** au-dessus de la liste pour exécuter l'exportation vers toutes les destinations d'exportation simultanément.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="9c0d9-147">Sélectionnez les points de suspension (…) après un élément de liste, puis choisissez **Exporter** pour exécuter l'exportation pour une seule destination d'exportation.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="9c0d9-148">Supprimer une destination d'exportation</span><span class="sxs-lookup"><span data-stu-id="9c0d9-148">Remove an Export destination</span></span>

<span data-ttu-id="9c0d9-149">Pour supprimer une destination d'exportation, commencez par la page principale **Destinations d'exportation**.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="9c0d9-150">Sélectionnez les points de suspension pour la destination d'exportation que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9c0d9-151">![Ellipses verticales](media/export-destinations-page-ellipsis.png "Ellipses verticales")</span><span class="sxs-lookup"><span data-stu-id="9c0d9-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="9c0d9-152">Sélectionnez **Supprimer** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="9c0d9-153">Confirmez la suppression en sélectionnant **Supprimer** sur l'écran de confirmation.</span><span class="sxs-lookup"><span data-stu-id="9c0d9-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
