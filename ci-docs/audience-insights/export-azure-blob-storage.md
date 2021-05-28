---
title: Exporter des données Customer Insights vers un stockage Blob Azure
description: Apprenez à configurer la connexion et à exporter vers un stockage Blob.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976131"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="a9a40-103">Exporter une liste de segments et d’autres données vers un stockage Blob Azure (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="a9a40-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="a9a40-104">Stockez vos données Customer Insights dans un stockage Blob ou utilisez-le pour transférer vos données vers d’autres applications.</span><span class="sxs-lookup"><span data-stu-id="a9a40-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="a9a40-105">Configurer la connexion au stockage Blob</span><span class="sxs-lookup"><span data-stu-id="a9a40-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="a9a40-106">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="a9a40-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a9a40-107">Sélectionnez **Ajouter une connexion** et choisissez **Stockage Blob Azure** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="a9a40-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="a9a40-108">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="a9a40-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a9a40-109">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="a9a40-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a9a40-110">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="a9a40-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a9a40-111">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="a9a40-111">Choose who can use this connection.</span></span> <span data-ttu-id="a9a40-112">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="a9a40-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a9a40-113">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a9a40-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a9a40-114">Entrez le **Nom du compte**, la **Clé du compte** et le **Conteneur** de votre compte de stockage Blob.</span><span class="sxs-lookup"><span data-stu-id="a9a40-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="a9a40-115">Pour obtenir plus d’informations sur la recherche du nom et de la clé du compte de stockage Blob, voir [Gérer les paramètres du compte de stockage dans le portail Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="a9a40-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="a9a40-116">Pour savoir comment créer un conteneur, voir [Créer un conteneur](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="a9a40-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="a9a40-117">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="a9a40-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="a9a40-118">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="a9a40-118">Configure an export</span></span>

<span data-ttu-id="a9a40-119">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="a9a40-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a9a40-120">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a9a40-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a9a40-121">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="a9a40-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a9a40-122">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="a9a40-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a9a40-123">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Stockage Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="a9a40-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="a9a40-124">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="a9a40-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a9a40-125">Cochez la case en regard de chacune des entités que vous souhaitez exporter vers cette destination.</span><span class="sxs-lookup"><span data-stu-id="a9a40-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="a9a40-126">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a9a40-126">Select **Save**.</span></span>

<span data-ttu-id="a9a40-127">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="a9a40-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a9a40-128">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a9a40-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="a9a40-129">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a9a40-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="a9a40-130">Les données exportées sont stockées dans le conteneur de stockage Blob que vous avez configuré.</span><span class="sxs-lookup"><span data-stu-id="a9a40-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="a9a40-131">Les chemins d’accès suivants aux dossiers sont créés automatiquement dans votre conteneur :</span><span class="sxs-lookup"><span data-stu-id="a9a40-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="a9a40-132">Pour les entités sources et les entités générées par le système : `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="a9a40-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="a9a40-133">Exemple : `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="a9a40-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="a9a40-134">Le fichier model.json des entités exportées sera au niveau de %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="a9a40-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="a9a40-135">Exemple : `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="a9a40-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
