---
title: Exporter des données Customer Insights vers Autopilot
description: Apprenez à configurer la connexion et à exporter vers Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760140"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="ba6c3-103">Exporter des segments vers Autopilot (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="ba6c3-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="ba6c3-104">Exportez des segments de profils clients unifiés vers Autopilot et utilisez-les pour le marketing par e-mail dans Autopilot.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="ba6c3-105">Conditions préalables à une connexion</span><span class="sxs-lookup"><span data-stu-id="ba6c3-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="ba6c3-106">Vous disposez d’un [compte Autopilot](https://www.autopilothq.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ba6c3-107">Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ba6c3-108">Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ba6c3-109">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="ba6c3-109">Known limitations</span></span>

- <span data-ttu-id="ba6c3-110">Vous pouvez exporter jusqu’à 100 000 profils clients au total vers Autopilot.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="ba6c3-111">L’exportation vers Autopilot est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="ba6c3-112">L’exportation de jusqu’à 100 000 profils vers Autopilot peut prendre jusqu’à quelques heures.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="ba6c3-113">Le nombre de profils que vous pouvez exporter vers Autopilot dépend et est limité par votre contrat avec Autopilot.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="ba6c3-114">Configurer la connexion à Autopilot</span><span class="sxs-lookup"><span data-stu-id="ba6c3-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="ba6c3-115">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ba6c3-116">Sélectionnez **Ajouter une connexion** et choisissez **Autopilot** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="ba6c3-117">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ba6c3-118">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ba6c3-119">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ba6c3-120">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-120">Choose who can use this connection.</span></span> <span data-ttu-id="ba6c3-121">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ba6c3-122">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ba6c3-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="ba6c3-123">Entrez votre [Clé API Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="ba6c3-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="ba6c3-124">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ba6c3-125">Sélectionnez **Connecter** pour initialiser la connexion à Autopilot.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="ba6c3-126">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ba6c3-127">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ba6c3-128">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="ba6c3-128">Configure an export</span></span>

<span data-ttu-id="ba6c3-129">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ba6c3-130">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ba6c3-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ba6c3-131">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ba6c3-132">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ba6c3-133">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Autopilot.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="ba6c3-134">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="ba6c3-135">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ba6c3-136">Répétez les mêmes étapes pour les autres champs facultatifs tels que **Prénom** et **Nom**.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="ba6c3-137">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-137">Select the segments you want to export.</span></span> <span data-ttu-id="ba6c3-138">Nous **recommandons vivement de ne pas exporter plus de 100 000 profils clients au total** vers Autopilot.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="ba6c3-139">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-139">Select **Save**.</span></span>

<span data-ttu-id="ba6c3-140">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ba6c3-141">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ba6c3-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ba6c3-142">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ba6c3-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ba6c3-143">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="ba6c3-143">Data privacy and compliance</span></span>

<span data-ttu-id="ba6c3-144">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Autopilot, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ba6c3-145">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Autopilot respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ba6c3-146">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ba6c3-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ba6c3-147">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
