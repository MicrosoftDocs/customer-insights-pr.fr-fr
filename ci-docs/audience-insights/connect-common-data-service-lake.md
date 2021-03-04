---
title: Se connecter aux entités dans le lac géré Common Data Service
description: Importer des données depuis un lac de données géré Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267810"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="c3836-103">Se connecter aux données dans un lac de données géré Common Data Service</span><span class="sxs-lookup"><span data-stu-id="c3836-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c3836-104">Cet article fournit des informations sur la façon dont les clients Dynamics 365 existants peuvent se connecter rapidement à leurs entités analytiques dans le lac géré Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c3836-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="c3836-105">Vous devez être administrateur de l’organisation Common Data Service pour continuer et voir la liste des entités disponibles dans le lac géré.</span><span class="sxs-lookup"><span data-stu-id="c3836-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="c3836-106">Remarques importantes</span><span class="sxs-lookup"><span data-stu-id="c3836-106">Important considerations</span></span>

<span data-ttu-id="c3836-107">Les données stockées dans des services en ligne, tels que Azure Data Lake Storage, peut être stocké dans un emplacement différent de celui où les données sont traitées ou stockées dans Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c3836-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="c3836-108"> En important ou en vous connectant aux données stockées dans les services en ligne, vous acceptez que les données puissent être transférées et stockées avec Dynamics 365 Customer Insights. [En savoir plus sur le Centre de gestion de la confidentialité Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="c3836-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="c3836-109">Se connecter à un lac géré Common Data Service</span><span class="sxs-lookup"><span data-stu-id="c3836-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="c3836-110">Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.</span><span class="sxs-lookup"><span data-stu-id="c3836-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="c3836-111">Sélectionnez **Ajouter une source de données**.</span><span class="sxs-lookup"><span data-stu-id="c3836-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="c3836-112">Sélectionnez **Se connecter à Common Data Service** et sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c3836-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="c3836-113">Saisissez un **Nom** pour la source de données, puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c3836-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="c3836-114">Instructions relatives au nom :</span><span class="sxs-lookup"><span data-stu-id="c3836-114">Name guidelines:</span></span> 
   - <span data-ttu-id="c3836-115">Commencez par une lettre.</span><span class="sxs-lookup"><span data-stu-id="c3836-115">Start with a letter.</span></span>
   - <span data-ttu-id="c3836-116">Utilisez uniquement des lettres et des chiffres.</span><span class="sxs-lookup"><span data-stu-id="c3836-116">Use letters and numbers only.</span></span> <span data-ttu-id="c3836-117">Les espaces et caractères spéciaux ne sont pas autorisés.</span><span class="sxs-lookup"><span data-stu-id="c3836-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="c3836-118">Utilisez entre 3 et 64 caractères.</span><span class="sxs-lookup"><span data-stu-id="c3836-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="c3836-119">Renseignez le champ **Adresse du serveur** pour votre organisation Common Data Service et sélectionnez **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="c3836-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c3836-120">![Boîte de dialogue pour saisir l’adresse de serveur Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="c3836-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="c3836-121">Sélectionnez les entités que vous souhaitez ingérer dans la liste disponible.</span><span class="sxs-lookup"><span data-stu-id="c3836-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="c3836-122">Si certaines entités sont déjà sélectionnées, elles peuvent être utilisées par d’autres applications Dynamics 365 (telles que Dynamics 365 Sales Insights ou Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="c3836-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="c3836-123">Vous ne pouvez pas modifier la sélection.</span><span class="sxs-lookup"><span data-stu-id="c3836-123">You can't change the selection.</span></span> <span data-ttu-id="c3836-124">Ces entités seront disponibles une fois la source de données créée.</span><span class="sxs-lookup"><span data-stu-id="c3836-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c3836-125">![Boîte de dialogue affichant une liste d’entités dans l’organisation Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="c3836-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="c3836-126">Enregistrez votre sélection pour commencer à synchroniser les entités sélectionnées avec le lac géré Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c3836-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="c3836-127">Vous trouverez la connexion récemment ajoutée sur la page **Sources de données**.</span><span class="sxs-lookup"><span data-stu-id="c3836-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="c3836-128">Elles sera mise en file d’attente pour actualisation et affichera les entités comme 0 jusqu’à ce que toutes les entités soient synchronisées.</span><span class="sxs-lookup"><span data-stu-id="c3836-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="c3836-129">Une seule source de données d’un environnement peut utiliser simultanément le même lac géré Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c3836-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="c3836-130">Modifier une source de données du lac géré Common Data Service</span><span class="sxs-lookup"><span data-stu-id="c3836-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="c3836-131">Vous ne modifiez la sélection d’entités qu’après avoir créé la source de données.</span><span class="sxs-lookup"><span data-stu-id="c3836-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="c3836-132">Par exemple, si des entités supplémentaires ont été ajoutées à Common Data Service et que vous souhaitez également les importer.</span><span class="sxs-lookup"><span data-stu-id="c3836-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="c3836-133">Pour vous connecter à un autre Common Data Service, [créer une source de données](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="c3836-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="c3836-134">Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.</span><span class="sxs-lookup"><span data-stu-id="c3836-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="c3836-135">En regard de la source de données que vous souhaitez mettre à jour, sélectionnez les points de suspension.</span><span class="sxs-lookup"><span data-stu-id="c3836-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="c3836-136">Sélectionnez l’option **Modifier** dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c3836-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="c3836-137">Sélectionnez des entités supplémentaires dans la liste des entités disponibles et sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c3836-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]