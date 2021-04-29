---
title: Exporter des données Customer Insights vers des hôtes Azure Data Lake Storage Gen2
description: Découvrez comment configurer la connexion à Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760048"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="56f91-103">Configurer la connexion à Azure Data Lake Storage Gen2 (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="56f91-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="56f91-104">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="56f91-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="56f91-105">Sélectionnez **Ajouter une connexion** et choisissez **Azure Data Lake Gen 2** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="56f91-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="56f91-106">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="56f91-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="56f91-107">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="56f91-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="56f91-108">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="56f91-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="56f91-109">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="56f91-109">Choose who can use this connection.</span></span> <span data-ttu-id="56f91-110">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="56f91-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="56f91-111">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="56f91-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="56f91-112">Entrez **Nom du compte**, **Clé de compte** et **conteneur** pour votre Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="56f91-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="56f91-113">Pour savoir comment créer un compte de stockage à utiliser avec Azure Data Lake Storage Gen2, voir [Créer un compte de stockage](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="56f91-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="56f91-114">Pour obtenir plus d’informations sur le nom et la clé du compte de stockage Azure Data Lake Gen2, voir [Gérer les paramètres du compte de stockage dans le portail Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="56f91-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="56f91-115">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="56f91-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="56f91-116">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="56f91-116">Configure an export</span></span>

<span data-ttu-id="56f91-117">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="56f91-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="56f91-118">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="56f91-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="56f91-119">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="56f91-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="56f91-120">Pour créer une nouvelle exportation, sélectionnez **Ajouter une exportation**.</span><span class="sxs-lookup"><span data-stu-id="56f91-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="56f91-121">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="56f91-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="56f91-122">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="56f91-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="56f91-123">Cochez la case en regard de chacune des entités que vous souhaitez exporter vers cette destination.</span><span class="sxs-lookup"><span data-stu-id="56f91-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="56f91-124">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="56f91-124">Select **Save**.</span></span>

<span data-ttu-id="56f91-125">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="56f91-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="56f91-126">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="56f91-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="56f91-127">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="56f91-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="56f91-128">Les données exportées sont stockées dans le conteneur de stockage Azure Data Lake Gen 2 que vous avez configuré.</span><span class="sxs-lookup"><span data-stu-id="56f91-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
