---
title: Exporter des données Customer Insights vers Constant Contact
description: Apprenez à configurer la connexion et à exporter vers Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124270"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="1f6ee-103">Exporter des segments vers Constant Contact (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="1f6ee-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="1f6ee-104">Exportez des segments de profils client unifiés vers Constant Contact et utilisez-les pour les activités marketing.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="1f6ee-105">Conditions préalables à une connexion</span><span class="sxs-lookup"><span data-stu-id="1f6ee-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="1f6ee-106">Vous disposez d’un [Compte Constant Contact](https://www.constantcontact.com/account-home) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1f6ee-107">Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1f6ee-108">Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1f6ee-109">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="1f6ee-109">Known limitations</span></span>

- <span data-ttu-id="1f6ee-110">Vous pouvez exporter jusqu’à 1 million de profils par exportation vers Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="1f6ee-111">L’exportation vers Constant Contact est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="1f6ee-112">L’exportation de jusqu’à 1 million de profils vers Constant Contact peut prendre jusqu’à 1 heure.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="1f6ee-113">Le nombre de profils que vous pouvez exporter vers Constant Contact dépend et est limité par votre contrat avec Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="1f6ee-114">Configurer la connexion à Constant Contact</span><span class="sxs-lookup"><span data-stu-id="1f6ee-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="1f6ee-115">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1f6ee-116">Sélectionnez **Ajouter une connexion** et choisissez **Constant Contact** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="1f6ee-117">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1f6ee-118">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1f6ee-119">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1f6ee-120">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-120">Choose who can use this connection.</span></span> <span data-ttu-id="1f6ee-121">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1f6ee-122">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1f6ee-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1f6ee-123">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1f6ee-124">Sélectionnez **Connecter** pour initialiser la connexion à Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="1f6ee-125">Sélectionnez **S’authentifier avec AdRoll** et fournissez vos informations d’identification administrateur pour Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="1f6ee-126">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1f6ee-127">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1f6ee-128">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="1f6ee-128">Configure an export</span></span>

<span data-ttu-id="1f6ee-129">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1f6ee-130">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1f6ee-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1f6ee-131">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1f6ee-132">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1f6ee-133">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="1f6ee-134">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1f6ee-135">Entrez votre [**ID de liste Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="1f6ee-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="1f6ee-136">Ouvrez une liste dans Constant Contact pour trouver l’ID de liste dans l’URL.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="1f6ee-137">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1f6ee-138">Il est obligatoire d’exporter des segments vers Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="1f6ee-139">Vous pouvez éventuellement exporter les champs Prénom et Nom comme champs supplémentaires pour créer des e-mails plus personnalisés.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="1f6ee-140">Sélectionnez **Ajouter un attribut** pour mapper ces champs.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="1f6ee-141">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="1f6ee-142">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-142">Select **Save**.</span></span>

<span data-ttu-id="1f6ee-143">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1f6ee-144">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1f6ee-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1f6ee-145">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1f6ee-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1f6ee-146">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="1f6ee-146">Data privacy and compliance</span></span>

<span data-ttu-id="1f6ee-147">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Constant Contact, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1f6ee-148">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Constant Contact respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1f6ee-149">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1f6ee-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="1f6ee-150">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1f6ee-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
