---
title: Connecteur Power Apps
description: Connectez-vous à Power Apps et Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598152"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="6f047-103">Connecteur Microsoft Power Apps (préversion)</span><span class="sxs-lookup"><span data-stu-id="6f047-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="6f047-104">Importez des profils client unifiés dans vos applications personnalisées avec Power Apps.</span><span class="sxs-lookup"><span data-stu-id="6f047-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="6f047-105">Connectez-vous à Power Apps et à Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="6f047-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="6f047-106">Customer Insights est l’une des nombreuses [sources disponibles pour les données dans Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="6f047-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="6f047-107">Consultez la documentation de Power Apps pour savoir comment [ajouter une connexion de données à une application](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="6f047-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="6f047-108">Nous vous recommandons de consulter également l’article [Comment Power Apps utilise la délégation pour gérer de grands ensembles de données dans les applications canevas](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="6f047-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="6f047-109">Entités disponibles</span><span class="sxs-lookup"><span data-stu-id="6f047-109">Available entities</span></span>

<span data-ttu-id="6f047-110">Après avoir ajouté Customer Insights en tant que connexion de données, vous pouvez choisir les entités suivantes dans Power Apps :</span><span class="sxs-lookup"><span data-stu-id="6f047-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="6f047-111">Client : pour utiliser les données du [profil client unifié](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6f047-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="6f047-112">UnifiedActivity : pour afficher la [chronologie des activités](activities.md) sur l’application.</span><span class="sxs-lookup"><span data-stu-id="6f047-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="6f047-113">Limitations</span><span class="sxs-lookup"><span data-stu-id="6f047-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="6f047-114">Entités récupérables</span><span class="sxs-lookup"><span data-stu-id="6f047-114">Retrievable entities</span></span>

<span data-ttu-id="6f047-115">Vous ne pouvez récupérer que les entités **Client**, **UnifiedActivity**, et **Segments** à l’aide du connecteur Power Apps.</span><span class="sxs-lookup"><span data-stu-id="6f047-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="6f047-116">D’autres entités sont affichées, car le connecteur sous-jacent les prend en charge par le biais des déclencheurs dans Power Automate.</span><span class="sxs-lookup"><span data-stu-id="6f047-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="6f047-117">Délégation</span><span class="sxs-lookup"><span data-stu-id="6f047-117">Delegation</span></span>

<span data-ttu-id="6f047-118">La délégation fonctionne pour l’entité Client et l’entité UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="6f047-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="6f047-119">Délégation pour l’entité **Client** : pour utiliser la délégation pour cette entité, les champs doivent être indexés dans [Index Rechercher et filtrer](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="6f047-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="6f047-120">Délégation pour **UnifiedActivity** : La délégation pour cette entité ne fonctionne que pour les champs **ActivityId** et **N° de client**.</span><span class="sxs-lookup"><span data-stu-id="6f047-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="6f047-121">Pour plus d’informations sur la délégation, voir [Fonctions et opérations délégables Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="6f047-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="6f047-122">Exemple de contrôle de galerie</span><span class="sxs-lookup"><span data-stu-id="6f047-122">Example gallery control</span></span>

<span data-ttu-id="6f047-123">Par exemple, vous ajoutez des profils clients à un [contrôle de galerie](/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="6f047-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="6f047-124">Ajoutez un contrôle **Galerie** à une application que vous créez.</span><span class="sxs-lookup"><span data-stu-id="6f047-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6f047-125">![Ajouter un élément de galerie](media/connector-powerapps9.png "Ajouter un élément de galerie")</span><span class="sxs-lookup"><span data-stu-id="6f047-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="6f047-126">Sélectionnez **Client** comme source de données pour les éléments.</span><span class="sxs-lookup"><span data-stu-id="6f047-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6f047-127">![Sélectionner une source de données](media/choose-datasource-powerapps.png "Sélectionner une source de données")</span><span class="sxs-lookup"><span data-stu-id="6f047-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="6f047-128">Vous pouvez modifier le volet de données sur la droite pour sélectionner le champ de l’entité Client à afficher dans la galerie.</span><span class="sxs-lookup"><span data-stu-id="6f047-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="6f047-129">Si vous souhaitez afficher n’importe quel champ du client sélectionné dans la galerie, renseignez la propriété de texte d’une étiquette : **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="6f047-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="6f047-130">Exemple : Gallery1.Selected.addresse1_ville</span><span class="sxs-lookup"><span data-stu-id="6f047-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="6f047-131">Pour afficher la chronologie unifiée pour un client, ajouter un élément de galerie et ajouter la propriété Éléments : **Filter(’UnifiedActivity’, CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="6f047-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="6f047-132">Exemple : Filter(’UnifiedActivity’, CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="6f047-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]