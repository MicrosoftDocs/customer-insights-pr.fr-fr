---
title: Ingérer des données via un connecteur Power Query
description: Connecteurs pour sources de données basées sur Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d51a7efa5fd9f7336d1662500eb804a674738493
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267766"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="d7c3c-103">Connexion à une source de données Power Query</span><span class="sxs-lookup"><span data-stu-id="d7c3c-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="d7c3c-104">Power Query propose un large éventail de connecteurs pour ingérer des données.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="d7c3c-105">La plupart de ces connecteurs sont pris en charge par Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="d7c3c-106">L’ajout de sources de données basées sur des connecteurs Power Query suit généralement la procédure décrite dans la section suivante.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="d7c3c-107">Cependant, selon le connecteur que vous utilisez, des informations différentes sont requises.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="d7c3c-108">Pour plus d’informations, consultez la documentation sur les connecteurs individuels dans la [Référence des connecteurs Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="d7c3c-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="d7c3c-109">Créer une source de données</span><span class="sxs-lookup"><span data-stu-id="d7c3c-109">Create a new data source</span></span>

1. <span data-ttu-id="d7c3c-110">Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="d7c3c-111">Sélectionnez **Ajouter une source de données**.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="d7c3c-112">Choisissez la méthode **Importer des données** et sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="d7c3c-113">Indiquez un **Nom** pour la source de données, et sélectionnez **Suivant** pour créer la source de données.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="d7c3c-114">Instructions relatives au nom :</span><span class="sxs-lookup"><span data-stu-id="d7c3c-114">Name guidelines:</span></span> 
   - <span data-ttu-id="d7c3c-115">Commencez par une lettre.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-115">Start with a letter.</span></span>
   - <span data-ttu-id="d7c3c-116">Utilisez uniquement des lettres et des chiffres.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-116">Use letters and numbers only.</span></span> <span data-ttu-id="d7c3c-117">Les espaces et caractères spéciaux ne sont pas autorisés.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="d7c3c-118">Utilisez entre 3 et 64 caractères.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="d7c3c-119">Choisissez l’un des [connecteurs disponibles](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="d7c3c-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="d7c3c-120">Pour cet exemple, nous sélectionnons le connecteur **Texte/CSV**.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d7c3c-121">Entrez les détails requis dans les **Paramètres de connexion** pour le connecteur sélectionné et sélectionnez **Suivant** pour voir un aperçu des données.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="d7c3c-122">Sélectionnez **Transformer les données**.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-122">Select **Transform data**.</span></span> <span data-ttu-id="d7c3c-123">Dans la cette étape, vous allez ajouter des entités à votre source de données.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="d7c3c-124">Les entités sont des jeux de données.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-124">Entities are datasets.</span></span> <span data-ttu-id="d7c3c-125">Si vous avez une base de données qui comprend plusieurs jeux de données, chaque jeu de données est sa propre entité.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="d7c3c-126">La boîte de dialogue **Power Query - Modifier les requêtes** vous permet d’examiner et d’affiner les données.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="d7c3c-127">Les entités que les systèmes ont identifiées dans votre source de données sélectionnée s’affiche dans le volet de gauche.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d7c3c-128">![Boîte de dialogue Modifier les requêtes](media/data-manager-configure-edit-queries.png "Boîte de dialogue Modifier les requêtes")</span><span class="sxs-lookup"><span data-stu-id="d7c3c-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="d7c3c-129">Vous pouvez également transformer vos données.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-129">You can also transform your data.</span></span> <span data-ttu-id="d7c3c-130">Sélectionnez une entité à modifier ou transformer.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="d7c3c-131">Utilisez les options de la fenêtre Power Query pour appliquer les transformations.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="d7c3c-132">Chaque transformation est répertoriée sous **Étapes appliquées**.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="d7c3c-133">Power Query fournit de nombreuses options de transformation prédéfinies.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="d7c3c-134">Pour plus d’informations, consultez [Transformations Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="d7c3c-134">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="d7c3c-135">Vous pouvez ajouter des entités supplémentaires à votre source de données en sélectionnant **Obtenir des données** dans la boîte de dialogue **Modifier les requêtes**.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="d7c3c-136">Ces transformations sont vivement recommandées :</span><span class="sxs-lookup"><span data-stu-id="d7c3c-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="d7c3c-137">Si vous ingérez des données à partir d’un fichier CSV, la première ligne contient souvent des en-têtes.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="d7c3c-138">Accédez à **Transformer la table**, puis sélectionnez **Utiliser les en-têtes comme première ligne**.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="d7c3c-139">Assurez-vous que le type de données est défini de manière appropriée.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="d7c3c-140">Sélectionnez **Enregistrer** au bas de la fenêtre Power Query pour enregistrer les transformations.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="d7c3c-141">Après l’enregistrement, vous trouverez votre source de données sur **Données** > **Sources de données**.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="d7c3c-142">Dans la page **Sources de données**, vous remarquerez que la nouvelle source de données a le statut **Actualisation en cours**.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="d7c3c-143">Sources de données Power Query disponibles</span><span class="sxs-lookup"><span data-stu-id="d7c3c-143">Available Power Query data sources</span></span>

<span data-ttu-id="d7c3c-144">Consultez la [Référence des connecteurs Power Query](https://docs.microsoft.com/power-query/connectors/) pour voir la liste à jour des connecteurs que vous pouvez sélectionner pour importer des données dans Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-144">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="d7c3c-145">Les connecteurs portant une coche dans la colonne **Customer Insights (Dataflows)** sont disponibles pour créer de nouvelles sources de données basées sur Power Query.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="d7c3c-146">Consultez la documentation d’un connecteur spécifique pour en savoir plus sur ses prérequis, ses limitations et autres détails.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="d7c3c-147">Modifier les sources de données Power Query</span><span class="sxs-lookup"><span data-stu-id="d7c3c-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="d7c3c-148">Remarque : il se peut qu’apporter des modifications aux sources de données qui sont actuellement utilisées dans un des processus de l’application (*segmentation*, *mise en correspondance*, *fusion*, etc.) ne soit pas possible.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="d7c3c-149">Avec la page **Paramètres**, vous pouvez suivre la progression de chacun des processus actifs.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="d7c3c-150">Lorsqu’un processus est terminé, vous pouvez revenir à la page **Sources de données**, puis apporter vos modifications.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="d7c3c-151">Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="d7c3c-152">Sélectionnez les points de suspension en regard de la source de données que vous souhaitez modifier et sélectionnez **Modifier** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d7c3c-153">![Option Modifier](media/edit-option-data-sources.png "Option Modifier")</span><span class="sxs-lookup"><span data-stu-id="d7c3c-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="d7c3c-154">Appliquez vos modifications et transformations dans la boîte de dialogue **Power Query - Modifier les requêtes** comme décrit dans la section [Créer une source de données](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="d7c3c-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="d7c3c-155">Sélectionnez **Enregistrer** dans Power Query après avoir terminé vos modifications pour enregistrer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="d7c3c-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]