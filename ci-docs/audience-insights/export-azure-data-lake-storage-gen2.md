---
title: Exporter des données Customer Insights vers des hôtes Azure Data Lake Storage Gen2
description: Découvrez comment configurer la connexion à Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477176"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="702d1-103">Connecteur pour Azure Data Lake Storage Gen2 (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="702d1-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="702d1-104">Stockez vos données Customer Insights dans Azure Data Lake Storage Gen2 ou utilisez-le pour transférer vos données vers d’autres applications.</span><span class="sxs-lookup"><span data-stu-id="702d1-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="702d1-105">Configurer le connecteur pour Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="702d1-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="702d1-106">Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="702d1-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="702d1-107">Sous **Azure Data Lake Storage Gen2**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="702d1-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="702d1-108">Donnez à votre destination un nom reconnaissable dans le champ **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="702d1-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="702d1-109">Entrez **Nom du compte**, **Clé de compte** et **conteneur** pour votre Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="702d1-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="702d1-110">Pour savoir comment créer un compte de stockage à utiliser avec Azure Data Lake Storage Gen2, voir [Créer un compte de stockage](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="702d1-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="702d1-111">Pour en savoir plus sur la recherche du nom et de la clé de compte du compte de stockage Azure Data Lake Gen2, voir [Gérer les paramètres du compte de stockage dans le portail Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="702d1-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="702d1-112">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="702d1-112">Select **Next**.</span></span>

1. <span data-ttu-id="702d1-113">Cochez la case en regard de chacune des entités que vous souhaitez exporter vers cette destination.</span><span class="sxs-lookup"><span data-stu-id="702d1-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="702d1-114">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="702d1-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="702d1-115">Exporter les données</span><span class="sxs-lookup"><span data-stu-id="702d1-115">Export the data</span></span>

<span data-ttu-id="702d1-116">Vous pouvez [exporter les données à la demande](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="702d1-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="702d1-117">L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="702d1-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
