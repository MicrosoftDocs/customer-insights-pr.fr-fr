---
title: Exporter les données Customer Insights vers ActiveCampaign
description: Apprenez à configurer la connexion et à exporter vers ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314608"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="a9323-103">Exporter des segments vers ActiveCampaign (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="a9323-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="a9323-104">Exportez des segments de profils client unifiés vers ActiveCampaign et utilisez-les pour des activités de marketing.</span><span class="sxs-lookup"><span data-stu-id="a9323-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a9323-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="a9323-105">Prerequisites</span></span>

-   <span data-ttu-id="a9323-106">Vous disposez d’un [compte ActiveCampaign](https://www.activecampaign.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="a9323-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a9323-107">Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="a9323-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a9323-108">Les profils client unifiés dans les segments exportés contiennent un champ avec une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="a9323-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a9323-109">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="a9323-109">Known limitations</span></span>

- <span data-ttu-id="a9323-110">Vous pouvez exporter jusqu’à 1 million de profils par exportation vers ActiveCampaign et cette opération peut prendre jusqu’à 90 minutes.</span><span class="sxs-lookup"><span data-stu-id="a9323-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="a9323-111">L’exportation vers ActiveCampaign est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="a9323-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="a9323-112">Le nombre de profils que vous pouvez exporter vers ActiveCampaign dépend de votre contrat avec ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="a9323-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="a9323-113">Configurer la connexion à ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="a9323-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="a9323-114">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="a9323-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a9323-115">Sélectionnez **Ajouter une connexion** et choisissez **ActiveCampaign** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="a9323-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="a9323-116">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="a9323-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a9323-117">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="a9323-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a9323-118">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="a9323-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a9323-119">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="a9323-119">Choose who can use this connection.</span></span> <span data-ttu-id="a9323-120">Par défaut, il s’agit uniquement des administrateurs.</span><span class="sxs-lookup"><span data-stu-id="a9323-120">By default, it's only administrators.</span></span> <span data-ttu-id="a9323-121">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a9323-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a9323-122">Entrez la [clé API ActiveCampaign et le nom d’hôte du point de terminaison REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="a9323-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="a9323-123">Le nom d’hôte du point de terminaison REST est le nom d’hôte uniquement, sans https://.</span><span class="sxs-lookup"><span data-stu-id="a9323-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="a9323-124">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="a9323-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a9323-125">Sélectionnez **Connecter** pour initialiser la connexion à ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="a9323-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="a9323-126">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a9323-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a9323-127">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="a9323-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a9323-128">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="a9323-128">Configure an export</span></span>

<span data-ttu-id="a9323-129">Vous pouvez configurer une exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="a9323-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="a9323-130">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a9323-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a9323-131">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="a9323-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a9323-132">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="a9323-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a9323-133">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="a9323-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="a9323-134">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="a9323-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a9323-135">Entrez votre [**ID de liste ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="a9323-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="a9323-136">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="a9323-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a9323-137">Il est nécessaire d’exporter les segments vers ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="a9323-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="a9323-138">Vous pouvez éventuellement exporter le prénom, le nom et le téléphone pour créer des e-mails plus personnalisés.</span><span class="sxs-lookup"><span data-stu-id="a9323-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="a9323-139">Sélectionnez Ajouter un attribut pour mapper ces champs.</span><span class="sxs-lookup"><span data-stu-id="a9323-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="a9323-140">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a9323-140">Select **Save**.</span></span>

<span data-ttu-id="a9323-141">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="a9323-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a9323-142">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a9323-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a9323-143">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a9323-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a9323-144">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="a9323-144">Data privacy and compliance</span></span>

<span data-ttu-id="a9323-145">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données à ActiveCampaign, vous autorisez le transfert de données en dehors de la limite de conformité pour Dynamics 365 Customer Insights, y compris les données potentiellement sensibles telles que les données personnelles.</span><span class="sxs-lookup"><span data-stu-id="a9323-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a9323-146">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer qu’ActiveCampaign respecte vos éventuelles obligations de confidentialité ou de sécurité.</span><span class="sxs-lookup"><span data-stu-id="a9323-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a9323-147">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a9323-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a9323-148">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="a9323-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
