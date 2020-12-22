---
title: Ingérer des données via un connecteur Power Query
description: Connecteurs pour sources de données basées sur Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405660"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="d3733-103">Connexion à une source de données Power Query</span><span class="sxs-lookup"><span data-stu-id="d3733-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="d3733-104">Power Query propose un large éventail de connecteurs pour ingérer des données.</span><span class="sxs-lookup"><span data-stu-id="d3733-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="d3733-105">La plupart de ces connecteurs sont pris en charge par Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d3733-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="d3733-106">L'ajout de sources de données basées sur des connecteurs Power Query suit généralement la procédure décrite dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="d3733-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="d3733-107">Cependant, selon le connecteur que vous utilisez, des informations différentes sont requises.</span><span class="sxs-lookup"><span data-stu-id="d3733-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="d3733-108">Pour plus d'informations, consultez la documentation sur les connecteurs individuels dans la [Référence des connecteurs Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="d3733-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="d3733-109">Créer une source de données</span><span class="sxs-lookup"><span data-stu-id="d3733-109">Create a new data source</span></span>

1. <span data-ttu-id="d3733-110">Dans Audience Insights, accédez à **Données** > **Sources de données**.</span><span class="sxs-lookup"><span data-stu-id="d3733-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="d3733-111">Sélectionnez **Ajouter une source de données**.</span><span class="sxs-lookup"><span data-stu-id="d3733-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="d3733-112">Choisissez la méthode **Importer des données** et sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d3733-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="d3733-113">Indiquez un **Nom** pour la source de données, et sélectionnez **Suivant** pour créer la source de données.</span><span class="sxs-lookup"><span data-stu-id="d3733-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="d3733-114">Choisissez l'un des [connecteurs disponibles](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="d3733-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="d3733-115">Pour cet exemple, nous sélectionnons le connecteur **Texte/CSV**.</span><span class="sxs-lookup"><span data-stu-id="d3733-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d3733-116">Entrez les détails requis dans les **Paramètres de connexion** pour le connecteur sélectionné et sélectionnez **Suivant** pour voir un aperçu des données.</span><span class="sxs-lookup"><span data-stu-id="d3733-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="d3733-117">Sélectionnez **Transformer les données**.</span><span class="sxs-lookup"><span data-stu-id="d3733-117">Select **Transform data**.</span></span> <span data-ttu-id="d3733-118">Dans la cette étape, vous allez ajouter des entités à votre source de données.</span><span class="sxs-lookup"><span data-stu-id="d3733-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="d3733-119">Les entités sont des jeux de données.</span><span class="sxs-lookup"><span data-stu-id="d3733-119">Entities are datasets.</span></span> <span data-ttu-id="d3733-120">Si vous avez une base de données qui comprend plusieurs jeux de données, chaque jeu de données est sa propre entité.</span><span class="sxs-lookup"><span data-stu-id="d3733-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="d3733-121">La boîte de dialogue **Power Query - Modifier les requêtes** vous permet d'examiner et d'affiner les données.</span><span class="sxs-lookup"><span data-stu-id="d3733-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="d3733-122">Les entités que les systèmes ont identifiées dans votre source de données sélectionnée s'affiche dans le volet de gauche.</span><span class="sxs-lookup"><span data-stu-id="d3733-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d3733-123">![Boîte de dialogue Modifier les requêtes](media/data-manager-configure-edit-queries.png "Boîte de dialogue Modifier les requêtes")</span><span class="sxs-lookup"><span data-stu-id="d3733-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="d3733-124">Vous pouvez également transformer vos données.</span><span class="sxs-lookup"><span data-stu-id="d3733-124">You can also transform your data.</span></span> <span data-ttu-id="d3733-125">Sélectionnez une entité à modifier ou transformer.</span><span class="sxs-lookup"><span data-stu-id="d3733-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="d3733-126">Utilisez les options de la fenêtre Power Query pour appliquer les transformations.</span><span class="sxs-lookup"><span data-stu-id="d3733-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="d3733-127">Chaque transformation est répertoriée sous **Étapes appliquées**.</span><span class="sxs-lookup"><span data-stu-id="d3733-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="d3733-128">Power Query fournit de nombreuses options de transformation prédéfinies.</span><span class="sxs-lookup"><span data-stu-id="d3733-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="d3733-129">Pour plus d’informations, consultez [Transformations Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="d3733-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="d3733-130">Vous pouvez ajouter des entités supplémentaires à votre source de données en sélectionnant **Obtenir des données** dans la boîte de dialogue **Modifier les requêtes**.</span><span class="sxs-lookup"><span data-stu-id="d3733-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="d3733-131">Ces transformations sont vivement recommandées :</span><span class="sxs-lookup"><span data-stu-id="d3733-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="d3733-132">Si vous ingérez des données à partir d'un fichier CSV, la première ligne contient souvent des en-têtes.</span><span class="sxs-lookup"><span data-stu-id="d3733-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="d3733-133">Accédez à **Transformer la table**, puis sélectionnez **Utiliser les en-têtes comme première ligne**.</span><span class="sxs-lookup"><span data-stu-id="d3733-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="d3733-134">Assurez-vous que le type de données est défini de manière appropriée.</span><span class="sxs-lookup"><span data-stu-id="d3733-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="d3733-135">Sélectionnez **Enregistrer** au bas de la fenêtre Power Query pour enregistrer les transformations.</span><span class="sxs-lookup"><span data-stu-id="d3733-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="d3733-136">Après l'enregistrement, vous trouverez votre source de données sur **Données** > **Sources de données**.</span><span class="sxs-lookup"><span data-stu-id="d3733-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="d3733-137">Dans la page **Sources de données**, vous remarquerez que la nouvelle source de données a le statut **Actualisation en cours**.</span><span class="sxs-lookup"><span data-stu-id="d3733-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="d3733-138">Sources de données Power Query disponibles</span><span class="sxs-lookup"><span data-stu-id="d3733-138">Available Power Query data sources</span></span>

<span data-ttu-id="d3733-139">Consultez la [Référence des connecteurs Power Query](https://docs.microsoft.com/power-query/connectors/) pour voir la liste à jour des connecteurs que vous pouvez sélectionner pour importer des données dans Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d3733-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="d3733-140">Les connecteurs portant une coche dans la colonne **Customer Insights (Dataflows)** sont disponibles pour créer de nouvelles sources de données basées sur Power Query.</span><span class="sxs-lookup"><span data-stu-id="d3733-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="d3733-141">Consultez la documentation d'un connecteur spécifique pour en savoir plus sur ses prérequis, ses limitations et autres détails.</span><span class="sxs-lookup"><span data-stu-id="d3733-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="d3733-142">Modifier les sources de données Power Query</span><span class="sxs-lookup"><span data-stu-id="d3733-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="d3733-143">Remarque : il se peut qu'apporter des modifications aux sources de données qui sont actuellement utilisées dans un des processus de l'application (*segmentation*, *mise en correspondance*, *fusion*, etc.) ne soit pas possible.</span><span class="sxs-lookup"><span data-stu-id="d3733-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="d3733-144">Avec la page **Paramètres**, vous pouvez suivre la progression de chacun des processus actifs.</span><span class="sxs-lookup"><span data-stu-id="d3733-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="d3733-145">Lorsqu'un processus est terminé, vous pouvez revenir à la page **Sources de données**, puis apporter vos modifications.</span><span class="sxs-lookup"><span data-stu-id="d3733-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="d3733-146">Dans Audience Insights, accédez à **Données** > **Sources de données**.</span><span class="sxs-lookup"><span data-stu-id="d3733-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="d3733-147">Sélectionnez les points de suspension en regard de la source de données que vous souhaitez modifier et sélectionnez **Modifier** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="d3733-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d3733-148">![Option Modifier](media/edit-option-data-sources.png "Option Modifier")</span><span class="sxs-lookup"><span data-stu-id="d3733-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="d3733-149">Appliquez vos modifications et transformations dans la boîte de dialogue **Power Query - Modifier les requêtes** comme décrit dans la section [Créer une source de données](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="d3733-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="d3733-150">Sélectionnez **Enregistrer** dans Power Query après avoir terminé vos modifications pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="d3733-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
