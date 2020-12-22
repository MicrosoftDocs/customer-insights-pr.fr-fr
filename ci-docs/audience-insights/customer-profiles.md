---
title: Afficher les profils de client
description: Obtenez une vue combinée de vos données client unifiées.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 13308c2f40cda0d7e813b4d94ab47d53b5ce2115
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653887"
---
# <a name="customer-profiles"></a><span data-ttu-id="690c4-103">Profils clients</span><span class="sxs-lookup"><span data-stu-id="690c4-103">Customer profiles</span></span>

<span data-ttu-id="690c4-104">La page **Clients** offre une vue combinée de vos clients, en fonction des données de profil collectées à partir de [toutes les sources de données](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="690c4-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="690c4-105">Les profils de client sont disponibles une fois que vous avez [créé l'entité Client unifiée](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="690c4-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="690c4-106">Veillez à terminer le processus d'unification des données pour obtenir des vues enrichies de vos clients.</span><span class="sxs-lookup"><span data-stu-id="690c4-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="690c4-107">La page vous permet également rechercher des clients.</span><span class="sxs-lookup"><span data-stu-id="690c4-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="690c4-108">Les clients peuvent être des personnes ou des organisations (préversion).</span><span class="sxs-lookup"><span data-stu-id="690c4-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="690c4-109">Chaque profil de client ou d'organisation est représenté par une vignette.</span><span class="sxs-lookup"><span data-stu-id="690c4-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="690c4-110">Sélectionnez une vignette pour voir des informations supplémentaires sur ce client ou cette organisation.</span><span class="sxs-lookup"><span data-stu-id="690c4-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="690c4-111">Utilisez les commandes de pagination en bas de la page pour voir des enregistrements supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="690c4-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="690c4-112">![Profils de client B2C](media/profiles-customers.png "Profils de client B2C")</span><span class="sxs-lookup"><span data-stu-id="690c4-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="690c4-113">Organisations (Préversion)</span><span class="sxs-lookup"><span data-stu-id="690c4-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="690c4-114">![Profils de client B2B](media/profile-customers-b2b.png "Profils de client B2B")</span><span class="sxs-lookup"><span data-stu-id="690c4-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="690c4-115">Si les vignettes ne s'affichent pas lorsque vous sélectionnez **Clients** dans le volet de navigation, votre administrateur doit [définir au moins un attribut de recherche](search-filter-index.md) dans **Index Rechercher et filtrer**.</span><span class="sxs-lookup"><span data-stu-id="690c4-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="690c4-116">Rechercher des clients</span><span class="sxs-lookup"><span data-stu-id="690c4-116">Search for customers</span></span>

<span data-ttu-id="690c4-117">Recherchez des clients en saisissant un nom ou d'autres attributs dans la zone de recherche.</span><span class="sxs-lookup"><span data-stu-id="690c4-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="690c4-118">La recherche n'aura lieu qu'au sein de l'entité Profil du client créée lors du processus d'unification des données.</span><span class="sxs-lookup"><span data-stu-id="690c4-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="690c4-119">En tant qu'administrateur, vous pouvez configurer les attributs de recherche à l'aide de la page **Index Rechercher et filtrer**.</span><span class="sxs-lookup"><span data-stu-id="690c4-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="690c4-120">Pour plus d’informations, voir [Gérer l'index Rechercher et filtrer](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="690c4-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="690c4-121">Filtrer les clients</span><span class="sxs-lookup"><span data-stu-id="690c4-121">Filter customers</span></span>

<span data-ttu-id="690c4-122">Vous pouvez filtrer les clients par les champs d'entité Profil client.</span><span class="sxs-lookup"><span data-stu-id="690c4-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="690c4-123">Comme pour la recherche, votre administrateur devra tout d'abord définir ces champs comme pouvant être filtrés à l'aide de la page **Index Rechercher et filtrer**.</span><span class="sxs-lookup"><span data-stu-id="690c4-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="690c4-124">Sélectionnez **Filtrer** sur la page **Clients**.</span><span class="sxs-lookup"><span data-stu-id="690c4-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="690c4-125">Cochez les cases en regard des attributs selon lesquels vous souhaitez filtrer les clients.</span><span class="sxs-lookup"><span data-stu-id="690c4-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="690c4-126">![Profils clients](media/profiles-customers3.png "Profils client")</span><span class="sxs-lookup"><span data-stu-id="690c4-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="690c4-127">Supprimez vos filtres en sélectionnant **Effacer les filtres** sur la page **Clients**.</span><span class="sxs-lookup"><span data-stu-id="690c4-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="690c4-128">Page des détails du client</span><span class="sxs-lookup"><span data-stu-id="690c4-128">Customer details page</span></span>

<span data-ttu-id="690c4-129">Sélectionnez l'une des vignettes client pour ouvrir la **Page des détails du client**.</span><span class="sxs-lookup"><span data-stu-id="690c4-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="690c4-130">Cette vue contient des informations unifiées pour le client sélectionné.</span><span class="sxs-lookup"><span data-stu-id="690c4-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="690c4-131">Les détails du client comprennent :</span><span class="sxs-lookup"><span data-stu-id="690c4-131">Customer details include:</span></span>

-   <span data-ttu-id="690c4-132">**Vignette du profil client :** cette vignette indique les différentes valeurs de l'entité de profil client unifié.</span><span class="sxs-lookup"><span data-stu-id="690c4-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="690c4-133">Ces détails peuvent comprendre l'adresse e-mail, le nom, la ville, etc.</span><span class="sxs-lookup"><span data-stu-id="690c4-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="690c4-134">**Intérêts potentiels, marques potentielles :** indique si vous avez configuré un enrichissement interne.</span><span class="sxs-lookup"><span data-stu-id="690c4-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="690c4-135">Il représente les intérêts et affinités potentiels pour des marques que pourrait avoir un client avec un profil similaire à ce client.</span><span class="sxs-lookup"><span data-stu-id="690c4-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="690c4-136">Pour plus d'informations, consultez [Enrichissement des profils clients avec des affinités de marque et d'intérêt](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="690c4-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="690c4-137">**Mesures :** indique si vous avez configuré une ou plusieurs mesures d'un type spécifique : mesures d'attribut client.</span><span class="sxs-lookup"><span data-stu-id="690c4-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="690c4-138">Elles englobent les KPI calculés de vos clients au niveau de chaque client.</span><span class="sxs-lookup"><span data-stu-id="690c4-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="690c4-139">Pour plus d'informations, consultez [Définir et gérer les mesures](measures.md).</span><span class="sxs-lookup"><span data-stu-id="690c4-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="690c4-140">**Chronologie des activités :** indique si vous avez configuré des activités.</span><span class="sxs-lookup"><span data-stu-id="690c4-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="690c4-141">La vue chronologique contient les activités triées par ordre chronologique de ce client, en commençant par l'activité la plus récente.</span><span class="sxs-lookup"><span data-stu-id="690c4-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="690c4-142">Pour plus d'informations, voir [Activités client](activities.md).</span><span class="sxs-lookup"><span data-stu-id="690c4-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="690c4-143">Sélectionnez **Retour aux clients** pour revenir à la page de recherche de clients.</span><span class="sxs-lookup"><span data-stu-id="690c4-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="690c4-144">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="690c4-144">Next steps</span></span>

<span data-ttu-id="690c4-145">[Ajoutez d'autres sources de données](data-sources.md) ou [créez des segments de client](segments.md).</span><span class="sxs-lookup"><span data-stu-id="690c4-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>
