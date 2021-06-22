---
title: Exporter des données Customer Insights vers Microsoft Advertising
description: Apprenez à configurer la connexion et à exporter vers Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124483"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="302ae-103">Exporter des segments vers Microsoft Advertising (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="302ae-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="302ae-104">Exportez les segments Customer Insights vers Microsoft Advertising pour créer des audiences Customer Match.</span><span class="sxs-lookup"><span data-stu-id="302ae-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="302ae-105">Utilisez ces audiences pour vos campagnes publicitaires.</span><span class="sxs-lookup"><span data-stu-id="302ae-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="302ae-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="302ae-106">Prerequisites</span></span>

-   <span data-ttu-id="302ae-107">Un [compte Microsoft Advertising](https://ads.microsoft.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="302ae-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="302ae-108">Vous avez accepté les conditions d'utilisation Customer Match.</span><span class="sxs-lookup"><span data-stu-id="302ae-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="302ae-109">[Segments configurés](segments.md) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="302ae-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="302ae-110">Les profils client unifiés dans les segments exportés contiennent un champ avec une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="302ae-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="302ae-111">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="302ae-111">Known limitations</span></span>

- <span data-ttu-id="302ae-112">Vous pouvez exporter jusqu’à 500 000 profils par exportation vers Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="302ae-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="302ae-113">L’exportation vers Microsoft Advertising est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="302ae-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="302ae-114">L’exportation de jusqu’à 500 000 profils vers Microsoft Advertising peut prendre jusqu’à 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="302ae-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="302ae-115">Configurer la connexion à Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="302ae-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="302ae-116">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="302ae-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="302ae-117">Sélectionnez **Ajouter une connexion** et choisissez **Microsoft Advertising** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="302ae-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="302ae-118">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="302ae-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="302ae-119">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="302ae-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="302ae-120">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="302ae-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="302ae-121">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="302ae-121">Choose who can use this connection.</span></span> <span data-ttu-id="302ae-122">Par défaut, ce sont les administrateurs.</span><span class="sxs-lookup"><span data-stu-id="302ae-122">The default is administrators.</span></span> <span data-ttu-id="302ae-123">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="302ae-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="302ae-124">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="302ae-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="302ae-125">Sélectionnez **Connecter** pour initialiser la connexion à Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="302ae-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="302ae-126">Sélectionnez **S’authentifier avec Microsoft Advertising** et fournissez vos informations d’identification administrateur pour Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="302ae-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="302ae-127">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="302ae-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="302ae-128">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="302ae-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="302ae-129">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="302ae-129">Configure an export</span></span>

<span data-ttu-id="302ae-130">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="302ae-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="302ae-131">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="302ae-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="302ae-132">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="302ae-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="302ae-133">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="302ae-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="302ae-134">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="302ae-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="302ae-135">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="302ae-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="302ae-136">Sélectionner les segments à exporter.</span><span class="sxs-lookup"><span data-stu-id="302ae-136">Select the segments to export.</span></span> <span data-ttu-id="302ae-137">Les audiences Customer Match dans Microsoft Advertising sont automatiquement créées avec le nom des segments sélectionnés pour l'exportation.</span><span class="sxs-lookup"><span data-stu-id="302ae-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="302ae-138">Chaque segment aboutira à une audience Customer Match distincte.</span><span class="sxs-lookup"><span data-stu-id="302ae-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="302ae-139">Entrez votre **ID client et ID de compte Microsoft Advertising**.</span><span class="sxs-lookup"><span data-stu-id="302ae-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="302ae-140">Vous pouvez trouver l'ID client (`cid`) et l'ID de compte (`aid`) dans les paramètres de l'URL lorsque vous êtes connecté à Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="302ae-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="302ae-141">Dans la section **Mise en correspondance de données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié avec l'adresse e-mail d'un client.</span><span class="sxs-lookup"><span data-stu-id="302ae-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="302ae-142">Il est obligatoire d’exporter des segments vers Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="302ae-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="302ae-143">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="302ae-143">Select **Save**.</span></span>

<span data-ttu-id="302ae-144">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="302ae-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="302ae-145">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="302ae-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="302ae-146">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="302ae-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="302ae-147">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="302ae-147">Data privacy and compliance</span></span>

<span data-ttu-id="302ae-148">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données à Microsoft Advertising, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="302ae-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="302ae-149">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Microsoft Advertising respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="302ae-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="302ae-150">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="302ae-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="302ae-151">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d'exportation à tout moment pour stopper l'utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="302ae-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
