---
title: Exporter des données Customer Insights vers Campaign Monitor
description: Apprenez à configurer la connexion et à exporter vers Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760522"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a><span data-ttu-id="1e221-103">Exporter des listes de segments vers Campaign Monitor (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="1e221-103">Export segment lists to Campaign Monitor (preview)</span></span>

<span data-ttu-id="1e221-104">Exportez des segments de profils client unifiés vers Campaign Monitor et utilisez-les pour les activités marketing.</span><span class="sxs-lookup"><span data-stu-id="1e221-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1e221-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="1e221-105">Prerequisites</span></span>

-   <span data-ttu-id="1e221-106">Vous disposez d’un [Compte Campaign Monitor](https://www.campaignmonitor.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="1e221-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1e221-107">Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="1e221-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1e221-108">Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="1e221-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1e221-109">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="1e221-109">Known limitations</span></span>

- <span data-ttu-id="1e221-110">Vous pouvez exporter jusqu’à 1 million de profils par exportation vers Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="1e221-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="1e221-111">L’exportation vers Campaign Monitor est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="1e221-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="1e221-112">L’exportation de jusqu’à 1 million de profils vers Campaign Monitor peut prendre jusqu’à 20 minutes.</span><span class="sxs-lookup"><span data-stu-id="1e221-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="1e221-113">Le nombre de profils que vous pouvez exporter vers Campaign Monitor dépend et est limité par votre contrat avec Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="1e221-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="1e221-114">Configurer la connexion à Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="1e221-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="1e221-115">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="1e221-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1e221-116">Sélectionnez **Ajouter une connexion** et choisissez **Campaign Monitor** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="1e221-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="1e221-117">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="1e221-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1e221-118">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="1e221-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1e221-119">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="1e221-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1e221-120">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="1e221-120">Choose who can use this connection.</span></span> <span data-ttu-id="1e221-121">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="1e221-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1e221-122">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1e221-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1e221-123">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="1e221-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1e221-124">Sélectionnez **Connecter** pour initialiser la connexion à Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="1e221-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="1e221-125">Sélectionnez **S’authentifier avec Campaign Monitor** et fournissez vos informations d’identification administrateur pour Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="1e221-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="1e221-126">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1e221-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1e221-127">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="1e221-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1e221-128">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="1e221-128">Configure an export</span></span>

<span data-ttu-id="1e221-129">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="1e221-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1e221-130">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1e221-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1e221-131">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="1e221-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1e221-132">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="1e221-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1e221-133">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="1e221-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="1e221-134">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="1e221-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1e221-135">Entrez votre [**ID de liste Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="1e221-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="1e221-136">[Générez la clé API](https://www.campaignmonitor.com/api/getting-started/) à partir des **Paramètres du compte** de Campaign Monitor pour afficher l’ID de la liste d’API.</span><span class="sxs-lookup"><span data-stu-id="1e221-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="1e221-137">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="1e221-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1e221-138">Il est obligatoire d’exporter des segments vers Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="1e221-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="1e221-139">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1e221-139">Select **Save**.</span></span>

<span data-ttu-id="1e221-140">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="1e221-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1e221-141">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1e221-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1e221-142">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1e221-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1e221-143">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="1e221-143">Data privacy and compliance</span></span>

<span data-ttu-id="1e221-144">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Campaign Monitor, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="1e221-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1e221-145">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Campaign Monitor respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="1e221-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1e221-146">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1e221-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="1e221-147">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1e221-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
