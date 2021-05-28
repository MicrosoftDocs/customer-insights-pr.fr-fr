---
title: Exporter des données Customer Insights vers Dynamics 365 Sales
description: Apprenez à configurer la connexion et à exporter vers Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976223"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="349ea-103">Utiliser des segments dans Dynamics 365 Sales (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="349ea-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="349ea-104">Utilisez vos données client pour créer des listes marketing, effectuer le suivi de workflows et publier des promotions avec Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="349ea-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="349ea-105">Conditions préalables à une connexion</span><span class="sxs-lookup"><span data-stu-id="349ea-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="349ea-106">Les enregistrements de contact doivent être présents dans Dynamics 365 Sales avant de pouvoir exporter un segment de Customer Insights vers Sales.</span><span class="sxs-lookup"><span data-stu-id="349ea-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="349ea-107">En savoir plus sur la façon d’intégrer des contacts dans [Dynamics 365 Sales utilisant Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="349ea-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="349ea-108">L’exportation de segments des informations sur l’audience vers Sales ne créera pas des enregistrements de contact dans les instances Sales.</span><span class="sxs-lookup"><span data-stu-id="349ea-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="349ea-109">Les enregistrements de contact de Sales doivent être intégrés aux informations sur l’audience et utilisés comme source de données.</span><span class="sxs-lookup"><span data-stu-id="349ea-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="349ea-110">Ils doivent également être inclus dans l’entité Client unifiée pour mapper les ID client avec les ID de contact avant que les segments puissent être exportés.</span><span class="sxs-lookup"><span data-stu-id="349ea-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="349ea-111">Configurer la connexion à Sales</span><span class="sxs-lookup"><span data-stu-id="349ea-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="349ea-112">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="349ea-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="349ea-113">Sélectionnez **Ajouter une connexion** et choisissez **Dynamics 365 Sales** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="349ea-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="349ea-114">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="349ea-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="349ea-115">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="349ea-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="349ea-116">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="349ea-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="349ea-117">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="349ea-117">Choose who can use this connection.</span></span> <span data-ttu-id="349ea-118">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="349ea-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="349ea-119">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="349ea-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="349ea-120">Entrez l’URL Sales de votre organisation dans le champ **Adresse du serveur**.</span><span class="sxs-lookup"><span data-stu-id="349ea-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="349ea-121">Dans la section **Compte administrateur du serveur**, sélectionnez **Se connecter** et choisissez un compte Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="349ea-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="349ea-122">Mappez un champ d’ID de client à l’ID de contact Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="349ea-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="349ea-123">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="349ea-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="349ea-124">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="349ea-124">Configure an export</span></span>

<span data-ttu-id="349ea-125">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="349ea-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="349ea-126">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="349ea-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="349ea-127">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="349ea-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="349ea-128">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="349ea-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="349ea-129">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="349ea-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="349ea-130">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="349ea-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="349ea-131">Choisissez un ou plusieurs segments.</span><span class="sxs-lookup"><span data-stu-id="349ea-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="349ea-132">Cliquez sur **Enregistrer**</span><span class="sxs-lookup"><span data-stu-id="349ea-132">Select **Save**</span></span>

<span data-ttu-id="349ea-133">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="349ea-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="349ea-134">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="349ea-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="349ea-135">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="349ea-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
