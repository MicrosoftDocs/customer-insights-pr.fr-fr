---
title: Exporter des données Customer Insights vers Mailchimp
description: Apprenez à configurer la connexion et à exporter vers Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 35848998e738c7ecc1642f2b75912ff78d85f79e
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976152"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="15fc4-103">Exporter des listes de segments vers Mailchimp (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="15fc4-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="15fc4-104">Exportez des segments de profils clients unifiés vers Mailchimp pour créer des bulletins d’informations et des campagnes par e-mail.</span><span class="sxs-lookup"><span data-stu-id="15fc4-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="15fc4-105">Conditions préalables à une connexion</span><span class="sxs-lookup"><span data-stu-id="15fc4-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="15fc4-106">Vous disposez d’un [compte Mailchimp](https://mailchimp.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="15fc4-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="15fc4-107">Il existe des audiences dans Mailchimp et les ID correspondants.</span><span class="sxs-lookup"><span data-stu-id="15fc4-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="15fc4-108">Pour plus d’informations, consultez [Audiences Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="15fc4-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="15fc4-109">Vous avez [configuré des segments](segments.md)</span><span class="sxs-lookup"><span data-stu-id="15fc4-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="15fc4-110">Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="15fc4-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="15fc4-111">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="15fc4-111">Known limitations</span></span>

- <span data-ttu-id="15fc4-112">Jusqu’à 1 million de profils par exportation vers Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="15fc4-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="15fc4-113">L’exportation vers Mailchimp est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="15fc4-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="15fc4-114">L’exportation de segments avec 1 million de profils peut prendre jusqu’à trois heures.</span><span class="sxs-lookup"><span data-stu-id="15fc4-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="15fc4-115">Le nombre de profils que vous pouvez exporter vers Mailchimp dépend et est limité par votre contrat avec Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="15fc4-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="15fc4-116">Configurer la connexion à Mailchimp</span><span class="sxs-lookup"><span data-stu-id="15fc4-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="15fc4-117">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="15fc4-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="15fc4-118">Sélectionnez **Ajouter une connexion** et choisissez **Autopilot** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="15fc4-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="15fc4-119">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="15fc4-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="15fc4-120">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="15fc4-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="15fc4-121">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="15fc4-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="15fc4-122">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="15fc4-122">Choose who can use this connection.</span></span> <span data-ttu-id="15fc4-123">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="15fc4-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="15fc4-124">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="15fc4-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="15fc4-125">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="15fc4-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="15fc4-126">Sélectionnez **Connecter** pour initialiser la connexion à Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="15fc4-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="15fc4-127">Sélectionnez **S’authentifier avec Mailchimp** et fournissez vos informations d’identification Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="15fc4-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="15fc4-128">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="15fc4-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="15fc4-129">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="15fc4-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="15fc4-130">Configurer le connecteur</span><span class="sxs-lookup"><span data-stu-id="15fc4-130">Configure the connector</span></span>

<span data-ttu-id="15fc4-131">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="15fc4-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="15fc4-132">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="15fc4-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="15fc4-133">Accédez à **Données**> **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="15fc4-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="15fc4-134">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="15fc4-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="15fc4-135">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="15fc4-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="15fc4-136">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="15fc4-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="15fc4-137">Entrez votre **[ID d’audience Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="15fc4-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="15fc4-138">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="15fc4-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="15fc4-139">Vous pouvez éventuellement exporter le **Prénom** et le **Nom** pour créer des e-mails plus personnalisés.</span><span class="sxs-lookup"><span data-stu-id="15fc4-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="15fc4-140">Sélectionnez **Ajouter un attribut** pour mapper ces champs.</span><span class="sxs-lookup"><span data-stu-id="15fc4-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="15fc4-141">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="15fc4-141">Select the segments you want to export.</span></span> <span data-ttu-id="15fc4-142">Vous pouvez exporter jusqu’à 1 million de profils clients au total vers Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="15fc4-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="15fc4-143">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="15fc4-143">Select **Save**.</span></span>

<span data-ttu-id="15fc4-144">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="15fc4-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="15fc4-145">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="15fc4-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="15fc4-146">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="15fc4-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="15fc4-147">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="15fc4-147">Data privacy and compliance</span></span>

<span data-ttu-id="15fc4-148">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Mailchimp, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="15fc4-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="15fc4-149">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Mailchimp respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="15fc4-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="15fc4-150">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="15fc4-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="15fc4-151">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="15fc4-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
