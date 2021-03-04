---
title: Exporter des données Customer Insights vers un stockage Blob Azure
description: Découvrez comment configurer la connexion au stockage Blob Azure.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ecacf20365e78ced8859dfa54b1b16cb923c00eb
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269189"
---
# <a name="connector-for-azure-blob-storage-preview"></a><span data-ttu-id="3a8d9-103">Connecteur pour le stockage Blob Azure (préversion)</span><span class="sxs-lookup"><span data-stu-id="3a8d9-103">Connector for Azure Blob storage (preview)</span></span>

<span data-ttu-id="3a8d9-104">Stockez vos données Customer Insights dans un stockage Blob Azure ou utilisez-le pour transférer vos données vers d’autres applications.</span><span class="sxs-lookup"><span data-stu-id="3a8d9-104">Store your Customer Insights data in an Azure Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-blob-storage"></a><span data-ttu-id="3a8d9-105">Configurer le connecteur pour le stockage Blob Azure</span><span class="sxs-lookup"><span data-stu-id="3a8d9-105">Configure the connector for Azure Blob storage</span></span>

1. <span data-ttu-id="3a8d9-106">Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="3a8d9-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3a8d9-107">Sous **Stockage Blob Azure**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="3a8d9-107">Under **Azure Blob Storage**, select **Set up**.</span></span>

1. <span data-ttu-id="3a8d9-108">Saisissez le **Nom du compte**, la **Clé de compte** et le **Conteneur** pour votre compte de stockage Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="3a8d9-108">Enter **Account name**, **Account key**, and **Container** for your Azure Blob storage account.</span></span>
    - <span data-ttu-id="3a8d9-109">Pour en savoir plus sur la recherche du nom et de la clé de compte de stockage Blob Azure, consultez [Gérer les paramètres du compte de stockage dans le portail Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="3a8d9-109">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="3a8d9-110">Pour savoir comment créer un conteneur, voir [Créer un conteneur](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="3a8d9-110">To learn how to create a container, see [Create a container](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="3a8d9-111">Donnez à votre destination un nom reconnaissable dans le champ **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="3a8d9-111">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="3a8d9-112">Sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="3a8d9-112">Select **Next**.</span></span>

1. <span data-ttu-id="3a8d9-113">Cochez la case en regard de chacune des entités que vous souhaitez exporter vers cette destination.</span><span class="sxs-lookup"><span data-stu-id="3a8d9-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="3a8d9-114">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="3a8d9-114">Select **Save**.</span></span>

<span data-ttu-id="3a8d9-115">Les données exportées sont stockées dans le conteneur de stockage Blob Azure que vous avez configuré.</span><span class="sxs-lookup"><span data-stu-id="3a8d9-115">Exported data is stored in the Azure Blob storage container you configured.</span></span> <span data-ttu-id="3a8d9-116">Les chemins d’accès suivants aux dossiers sont créés automatiquement dans votre conteneur :</span><span class="sxs-lookup"><span data-stu-id="3a8d9-116">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="3a8d9-117">Pour les entités sources et les entités générées par le système : `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="3a8d9-117">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="3a8d9-118">Exemple : `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="3a8d9-118">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="3a8d9-119">Le fichier model.json pour les entités exportées résidera au niveau %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="3a8d9-119">The model.json for the exported entities will reside at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="3a8d9-120">Exemple : `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="3a8d9-120">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3a8d9-121">Exporter les données</span><span class="sxs-lookup"><span data-stu-id="3a8d9-121">Export the data</span></span>

<span data-ttu-id="3a8d9-122">Vous pouvez [exporter les données à la demande](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3a8d9-122">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="3a8d9-123">L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3a8d9-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]