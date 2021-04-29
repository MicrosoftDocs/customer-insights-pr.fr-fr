---
title: Exporter des données Customer Insights vers Snapchat
description: Apprenez à configurer la connexion et à exporter vers Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760520"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="d1e80-103">Exporter des listes de segments vers Snapchat (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="d1e80-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="d1e80-104">Exportez des segments de profils client unifiés vers Snapchat et utilisez-les pour les activités de publicité.</span><span class="sxs-lookup"><span data-stu-id="d1e80-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="d1e80-105">Conditions préalables à une connexion</span><span class="sxs-lookup"><span data-stu-id="d1e80-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="d1e80-106">Vous disposez d’un [Compte professionnel Snapchat](https://business.snapchat.com/), d’un[Compte Snapchat Ads](https://ads.snapchat.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="d1e80-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d1e80-107">Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="d1e80-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d1e80-108">Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="d1e80-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d1e80-109">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="d1e80-109">Known limitations</span></span>

- <span data-ttu-id="d1e80-110">L’exportation vers Snapchat est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="d1e80-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="d1e80-111">L’exportation de jusqu’à 1 million de profils vers Snapchat peut prendre jusqu’à 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="d1e80-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="d1e80-112">Configurer la connexion à Snapchat</span><span class="sxs-lookup"><span data-stu-id="d1e80-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="d1e80-113">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="d1e80-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d1e80-114">Sélectionnez **Ajouter une connexion** et choisissez **Snapchat** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="d1e80-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="d1e80-115">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="d1e80-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d1e80-116">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="d1e80-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d1e80-117">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="d1e80-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d1e80-118">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="d1e80-118">Choose who can use this connection.</span></span> <span data-ttu-id="d1e80-119">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="d1e80-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d1e80-120">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d1e80-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d1e80-121">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="d1e80-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d1e80-122">Sélectionnez **Connecter** pour initialiser la connexion à Snapchat.</span><span class="sxs-lookup"><span data-stu-id="d1e80-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="d1e80-123">Sélectionnez **S’authentifier avec Snapchat** et fournissez vos informations d’identification administrateur pour Snapchat.</span><span class="sxs-lookup"><span data-stu-id="d1e80-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="d1e80-124">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d1e80-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d1e80-125">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="d1e80-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d1e80-126">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="d1e80-126">Configure an export</span></span>

<span data-ttu-id="d1e80-127">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="d1e80-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d1e80-128">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d1e80-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d1e80-129">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="d1e80-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d1e80-130">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="d1e80-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d1e80-131">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Snapchat.</span><span class="sxs-lookup"><span data-stu-id="d1e80-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="d1e80-132">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="d1e80-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d1e80-133">Entrez l’[**ID d’audience Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="d1e80-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="d1e80-134">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="d1e80-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d1e80-135">Il est obligatoire d’exporter des segments vers Snapchat.</span><span class="sxs-lookup"><span data-stu-id="d1e80-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="d1e80-136">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="d1e80-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="d1e80-137">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d1e80-137">Select **Save**.</span></span>

<span data-ttu-id="d1e80-138">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="d1e80-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d1e80-139">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d1e80-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d1e80-140">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d1e80-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d1e80-141">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="d1e80-141">Data privacy and compliance</span></span>

<span data-ttu-id="d1e80-142">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Snapchat, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="d1e80-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d1e80-143">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Snapchat respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="d1e80-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d1e80-144">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d1e80-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d1e80-145">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="d1e80-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
