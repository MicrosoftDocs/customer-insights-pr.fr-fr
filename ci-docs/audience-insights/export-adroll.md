---
title: Exporter des données Customer Insights vers AdRoll
description: Apprenez à configurer la connexion et à exporter vers AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304814"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="f798c-103">Exporter des segments vers AdRoll (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="f798c-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="f798c-104">Exportez des segments de profils clients unifiés vers AdRoll et utilisez-les pour la publicité.</span><span class="sxs-lookup"><span data-stu-id="f798c-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f798c-105">Conditions préalables à une connexion</span><span class="sxs-lookup"><span data-stu-id="f798c-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f798c-106">Vous disposez d’un [compte AdRoll](https://www.adroll.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="f798c-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f798c-107">Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="f798c-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f798c-108">Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="f798c-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f798c-109">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="f798c-109">Known limitations</span></span>

- <span data-ttu-id="f798c-110">Vous pouvez exporter jusqu’à 250 000 profils à la fois vers AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f798c-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="f798c-111">Vous ne pouvez pas exporter de segments contenant moins de 100 profils vers AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f798c-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="f798c-112">L’exportation vers AdRoll est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="f798c-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="f798c-113">L’exportation de jusqu’à 250 000 profils vers AdRoll peut prendre jusqu’à 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="f798c-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="f798c-114">Le nombre de profils que vous pouvez exporter vers AdRoll dépend de votre contrat avec AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f798c-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="f798c-115">Configurer la connexion à AdRoll</span><span class="sxs-lookup"><span data-stu-id="f798c-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="f798c-116">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="f798c-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f798c-117">Sélectionnez **Ajouter une connexion** et choisissez **AdRoll** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="f798c-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="f798c-118">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="f798c-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f798c-119">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="f798c-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f798c-120">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="f798c-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f798c-121">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="f798c-121">Choose who can use this connection.</span></span> <span data-ttu-id="f798c-122">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="f798c-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f798c-123">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f798c-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f798c-124">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="f798c-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f798c-125">Sélectionnez **Connecter** pour initialiser la connexion à AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f798c-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="f798c-126">Sélectionnez **S’authentifier avec AdRoll** et fournissez vos informations d’administrateur pour AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f798c-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="f798c-127">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f798c-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f798c-128">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="f798c-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f798c-129">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="f798c-129">Configure an export</span></span>

<span data-ttu-id="f798c-130">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="f798c-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f798c-131">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f798c-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f798c-132">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="f798c-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f798c-133">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="f798c-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f798c-134">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f798c-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="f798c-135">Si le nom de la section ne s’affiche pas, aucune connexion de ce type n’est disponible pour vous.</span><span class="sxs-lookup"><span data-stu-id="f798c-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="f798c-136">Entrez votre **ID d’annonceur AdRoll**.</span><span class="sxs-lookup"><span data-stu-id="f798c-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="f798c-137">Pour plus d’informations, voir [Profils d’annonceur AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="f798c-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="f798c-138">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="f798c-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f798c-139">Il est nécessaire d’exporter des segments vers AdRoll.</span><span class="sxs-lookup"><span data-stu-id="f798c-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="f798c-140">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="f798c-140">Select the segments you want to export.</span></span> <span data-ttu-id="f798c-141">Sélectionnez un segment avec au moins 100 membres.</span><span class="sxs-lookup"><span data-stu-id="f798c-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="f798c-142">Vous ne pouvez pas exporter des segments plus petits.</span><span class="sxs-lookup"><span data-stu-id="f798c-142">You can't export smaller segments.</span></span> <span data-ttu-id="f798c-143">De plus, la taille maximale d’un segment à exporter est de 250 000 membres par exportation.</span><span class="sxs-lookup"><span data-stu-id="f798c-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="f798c-144">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f798c-144">Select **Save**.</span></span>

<span data-ttu-id="f798c-145">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="f798c-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f798c-146">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f798c-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="f798c-147">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f798c-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f798c-148">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="f798c-148">Data privacy and compliance</span></span>

<span data-ttu-id="f798c-149">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers AdRoll, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="f798c-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f798c-150">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que AdRoll respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="f798c-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f798c-151">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f798c-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="f798c-152">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="f798c-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
