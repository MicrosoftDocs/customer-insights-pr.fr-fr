---
title: Exporter des données Customer Insights vers Azure Synapse Analytics
description: Découvrez comment configurer la connexion à Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977374"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="fd275-103">Exporter des données vers Azure Synapse Analytics (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="fd275-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="fd275-104">Azure Synapse est un service d’analyse qui accélère le temps nécessaire pour obtenir des informations sur les entrepôts de données et les systèmes Big Data.</span><span class="sxs-lookup"><span data-stu-id="fd275-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="fd275-105">Vous pouvez ingérer et utiliser vos données Customer Insights dans [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="fd275-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fd275-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="fd275-106">Prerequisites</span></span>

<span data-ttu-id="fd275-107">Les conditions préalables suivantes doivent être remplies pour configurer la connexion entre Customer Insights et Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="fd275-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="fd275-108">Assurez-vous de configurer toutes les **attributions de rôle** comme décrit.</span><span class="sxs-lookup"><span data-stu-id="fd275-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="fd275-109">Conditions préalables dans Customer Insights</span><span class="sxs-lookup"><span data-stu-id="fd275-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="fd275-110">Vous disposez d’un rôle **Administrateur** dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="fd275-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="fd275-111">En savoir plus sur la [configuration des autorisations utilisateur dans les informations sur l’audience](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="fd275-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="fd275-112">Dans Azure :</span><span class="sxs-lookup"><span data-stu-id="fd275-112">In Azure:</span></span> 

- <span data-ttu-id="fd275-113">Un abonnement Azure actif.</span><span class="sxs-lookup"><span data-stu-id="fd275-113">An active Azure subscription.</span></span>

- <span data-ttu-id="fd275-114">Si vous utilisez un nouveau compte Azure Data Lake Storage Gen2, le *principal de service pour les informations sur l’audience* a besoin d’autorisations **Contributeur d’objet BLOB de stockage**.</span><span class="sxs-lookup"><span data-stu-id="fd275-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="fd275-115">En savoir plus sur la [connexion à un compte Azure Data Lake Storage Gen2 avec le principal de service Azure pour les informations sur l’audience](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="fd275-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="fd275-116">Le compte Data Lake Storage Gen2 **doit avoir un** [espace de noms hiérarchique](/azure/storage/blobs/data-lake-storage-namespace) activé.</span><span class="sxs-lookup"><span data-stu-id="fd275-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="fd275-117">Sur le groupe de ressources dans lequel l’espace de travail Azure Synapse est localisé, le *principal de service* et l’*utilisateur pour les informations sur l’audience* doivent au minimum se voir attribuer les autorisations **Lecteur**.</span><span class="sxs-lookup"><span data-stu-id="fd275-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="fd275-118">Pour plus d’informations, voir [Attribuer des rôles Azure à l’aide du portail Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="fd275-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="fd275-119">L’*utilisateur* a besoin d’autorisations **Contributeur d’objet BLOB de stockage** sur le compte Azure Data Lake Storage Gen2 où les données se trouvent et sont liées à l’espace de travail Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="fd275-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="fd275-120">En savoir plus sur l’[utilisation du portail Azure pour attribuer un rôle Azure afin d’accéder aux données des objets blob et des files d’attente](/azure/storage/common/storage-auth-aad-rbac-portal) et les [autorisations collaborateur de données BLOB de stockage](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="fd275-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="fd275-121">L’*[identité gérée de l’espace de travail Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* a besoin d’autorisations **Contributeur d’objet BLOB de stockage** sur le compte Azure Data Lake Storage Gen2 où les données se trouvent et sont liées à l’espace de travail Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="fd275-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="fd275-122">En savoir plus sur l’[utilisation du portail Azure pour attribuer un rôle Azure afin d’accéder aux données des objets blob et des files d’attente](/azure/storage/common/storage-auth-aad-rbac-portal) et les [autorisations collaborateur de données BLOB de stockage](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="fd275-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="fd275-123">Sur l’espace de travail Azure Synapse, le *principal de service pour les informations sur l’audience* a besoin que le rôle **Administrateur de Synapse** lui soit attribué.</span><span class="sxs-lookup"><span data-stu-id="fd275-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="fd275-124">Pour plus d’informations, voir [Comment configurer le contrôle d’accès pour votre espace de travail Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="fd275-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="fd275-125">Configurer la connexion et exporter vers Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="fd275-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="fd275-126">Configurer une connexion</span><span class="sxs-lookup"><span data-stu-id="fd275-126">Configure a connection</span></span>

1. <span data-ttu-id="fd275-127">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="fd275-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="fd275-128">Sélectionnez **Ajouter une connexion** et choisissez **Azure Synapse Analytics** ou sélectionnez **Configurer** dans la vignette **Azure Synapse Analytics** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="fd275-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="fd275-129">Donnez à votre connexion un nom reconnaissable dans le champ Nom d’affichage.</span><span class="sxs-lookup"><span data-stu-id="fd275-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="fd275-130">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="fd275-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="fd275-131">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="fd275-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="fd275-132">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="fd275-132">Choose who can use this connection.</span></span> <span data-ttu-id="fd275-133">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="fd275-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="fd275-134">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="fd275-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="fd275-135">Sélectionnez ou recherchez l’abonnement dans lequel vous souhaitez utiliser les données Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fd275-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="fd275-136">Dès qu’un abonnement est sélectionné, vous pouvez également sélectionner **Espace de travail**, **Compte de stockage** et **Conteneur**.</span><span class="sxs-lookup"><span data-stu-id="fd275-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="fd275-137">Sélectionnez **Enregistrer** pour enregistrer la connexion.</span><span class="sxs-lookup"><span data-stu-id="fd275-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="fd275-138">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="fd275-138">Configure an export</span></span>

<span data-ttu-id="fd275-139">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="fd275-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="fd275-140">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="fd275-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="fd275-141">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="fd275-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="fd275-142">Pour créer une nouvelle exportation, sélectionnez **Ajouter une exportation**.</span><span class="sxs-lookup"><span data-stu-id="fd275-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="fd275-143">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="fd275-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="fd275-144">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune [connexion](connections.md) de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="fd275-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="fd275-145">Indiquez un **nom d’affichage** reconnaissable pour votre exportation et un **nom de base de données**.</span><span class="sxs-lookup"><span data-stu-id="fd275-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="fd275-146">Sélectionnez les entités que vous souhaitez exporter vers Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="fd275-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="fd275-147">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="fd275-147">Select **Save**.</span></span>

<span data-ttu-id="fd275-148">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="fd275-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="fd275-149">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fd275-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fd275-150">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="fd275-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="fd275-151">Mettre à jour une exportation</span><span class="sxs-lookup"><span data-stu-id="fd275-151">Update an export</span></span>

1. <span data-ttu-id="fd275-152">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="fd275-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="fd275-153">Sélectionnez **Modifier** pour l’exportation que vous souhaitez mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="fd275-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="fd275-154">**Ajoutez** ou **supprimez** des entités de la sélection.</span><span class="sxs-lookup"><span data-stu-id="fd275-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="fd275-155">Si des entités sont supprimées de la sélection, elles ne sont pas supprimées de la base de données Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="fd275-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="fd275-156">Cependant, les futures actualisations des données ne mettront pas à jour les entités supprimées dans cette base de données.</span><span class="sxs-lookup"><span data-stu-id="fd275-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="fd275-157">**Changer le nom de la base de données** crée une nouvelle base de données Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="fd275-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="fd275-158">La base de données avec le nom qui a été configuré auparavant ne recevra aucune mise à jour lors des actualisations ultérieures.</span><span class="sxs-lookup"><span data-stu-id="fd275-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
