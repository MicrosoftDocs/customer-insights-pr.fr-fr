---
title: Exporter des données Customer Insights vers Dynamics 365 Marketing
description: Apprenez à configurer la connexion et à exporter vers Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759634"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="88af5-103">Utiliser des segments dans Dynamics 365 Marketing (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="88af5-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="88af5-104">Utilisez des [segments](segments.md) pour générer des campagnes et contacter des groupes de clients spécifiques avec Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="88af5-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="88af5-105">Pour plus d’informations, voir [Utiliser des segments de Dynamics 365 Customer Insights avec Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).</span><span class="sxs-lookup"><span data-stu-id="88af5-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="88af5-106">Conditions préalables à une connexion</span><span class="sxs-lookup"><span data-stu-id="88af5-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="88af5-107">Les enregistrements de contact doivent être présents dans Dynamics 365 Marketing avant de pouvoir exporter un segment de Customer Insights vers Marketing.</span><span class="sxs-lookup"><span data-stu-id="88af5-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="88af5-108">En savoir plus sur la façon d’intégrer des contacts dans [Dynamics 365 Marketing utilisant Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="88af5-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="88af5-109">L’exportation de segments des informations sur l’audience vers Marketing ne créera pas des enregistrements de contact dans les instances Marketing.</span><span class="sxs-lookup"><span data-stu-id="88af5-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="88af5-110">Les enregistrements de contact de Marketing doivent être intégrés aux informations sur l’audience et utilisés comme source de données.</span><span class="sxs-lookup"><span data-stu-id="88af5-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="88af5-111">Ils doivent également être inclus dans l’entité Client unifiée pour mapper les ID client avec les ID de contact avant que les segments puissent être exportés.</span><span class="sxs-lookup"><span data-stu-id="88af5-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="88af5-112">Configurer la connexion à Marketing</span><span class="sxs-lookup"><span data-stu-id="88af5-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="88af5-113">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="88af5-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="88af5-114">Sélectionnez **Ajouter une connexion** et choisissez **Dynamics 365 Marketing** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="88af5-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="88af5-115">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="88af5-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="88af5-116">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="88af5-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="88af5-117">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="88af5-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="88af5-118">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="88af5-118">Choose who can use this connection.</span></span> <span data-ttu-id="88af5-119">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="88af5-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="88af5-120">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="88af5-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="88af5-121">Entrez l’URL marketing de votre organisation dans le champ **Adresse du serveur**.</span><span class="sxs-lookup"><span data-stu-id="88af5-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="88af5-122">Dans la section **Compte administrateur du serveur**, sélectionnez **Se connecter** et choisissez un compte Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="88af5-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="88af5-123">Mappez un champ d’ID de client à l’ID de contact Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="88af5-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="88af5-124">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="88af5-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="88af5-125">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="88af5-125">Configure an export</span></span>

<span data-ttu-id="88af5-126">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="88af5-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="88af5-127">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="88af5-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="88af5-128">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="88af5-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="88af5-129">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="88af5-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="88af5-130">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="88af5-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="88af5-131">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="88af5-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="88af5-132">Choisissez un ou plusieurs segments.</span><span class="sxs-lookup"><span data-stu-id="88af5-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="88af5-133">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="88af5-133">Select **Save**.</span></span>

<span data-ttu-id="88af5-134">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="88af5-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="88af5-135">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="88af5-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="88af5-136">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="88af5-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
