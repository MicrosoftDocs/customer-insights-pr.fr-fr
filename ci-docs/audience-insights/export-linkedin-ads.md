---
title: Exporter des données Customer Insights vers LinkedIn Ads
description: Apprenez à configurer la connexion et à exporter vers LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124485"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="d2739-103">Exporter des segments vers LinkedIn Ads (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="d2739-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="d2739-104">Exportez des segments de profils clients unifiés vers LinkedIn Ads pour créer des audiences correspondantes.</span><span class="sxs-lookup"><span data-stu-id="d2739-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="d2739-105">Utilisez les audiences correspondantes pour le ciblage des entreprises et le ciblage des contacts.</span><span class="sxs-lookup"><span data-stu-id="d2739-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d2739-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="d2739-106">Prerequisites</span></span>

-   <span data-ttu-id="d2739-107">Vous disposez d’un [compte LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="d2739-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d2739-108">Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="d2739-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d2739-109">Les profils client dans les segments exportés contiennent un champ avec une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="d2739-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d2739-110">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="d2739-110">Known limitations</span></span>

- <span data-ttu-id="d2739-111">Vous pouvez exporter jusqu’à 100 000 profils par exportation vers LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="d2739-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="d2739-112">L’exportation vers LinkedIn Ads est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="d2739-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="d2739-113">L’exportation de jusqu’à 100 000 profils vers LinkedIn Ads peut prendre jusqu’à 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="d2739-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="d2739-114">Configurer la connexion à LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="d2739-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="d2739-115">Dans Audience insights, accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="d2739-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d2739-116">Sélectionnez **Ajouter une connexion** et choisissez **LinkedIn Ads** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="d2739-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="d2739-117">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="d2739-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d2739-118">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="d2739-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d2739-119">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="d2739-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d2739-120">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="d2739-120">Choose who can use this connection.</span></span> <span data-ttu-id="d2739-121">Si vous n’effectuez aucune action, ce sont par défaut les administrateurs.</span><span class="sxs-lookup"><span data-stu-id="d2739-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="d2739-122">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d2739-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d2739-123">Fournissez votre [ID de compte LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="d2739-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="d2739-124">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="d2739-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d2739-125">Sélectionnez **Connecter** pour initialiser la connexion à Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="d2739-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="d2739-126">Sélectionnez **S’authentifier avec LinkedIn** et fournissez vos informations d’identification administrateur pour LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="d2739-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="d2739-127">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d2739-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d2739-128">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="d2739-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d2739-129">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="d2739-129">Configure an export</span></span>

<span data-ttu-id="d2739-130">Vous pouvez configurer une exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="d2739-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="d2739-131">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d2739-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d2739-132">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="d2739-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d2739-133">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="d2739-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d2739-134">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="d2739-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="d2739-135">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="d2739-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d2739-136">Choisissez si vous souhaitez exporter les données pour effectuer un [ciblage des contacts](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ou un [ciblage des entreprises](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) sur Linkedin.</span><span class="sxs-lookup"><span data-stu-id="d2739-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="d2739-137">Dans la section **Mise en correspondance de données**, sélectionnez le champ de votre profil client unifié qui représente l'adresse e-mail d'un client.</span><span class="sxs-lookup"><span data-stu-id="d2739-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d2739-138">Il est obligatoire d’exporter des segments vers LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="d2739-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="d2739-139">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="d2739-139">Select the segments you want to export.</span></span> <span data-ttu-id="d2739-140">Les audiences correspondantes dans LinkedIn Campaign Manager seront automatiquement créées avec le nom des segments que vous avez choisi d'exporter.</span><span class="sxs-lookup"><span data-stu-id="d2739-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="d2739-141">Chaque segment aboutira à une audience correspondante distincte.</span><span class="sxs-lookup"><span data-stu-id="d2739-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="d2739-142">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d2739-142">Select **Save**.</span></span>

<span data-ttu-id="d2739-143">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="d2739-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d2739-144">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d2739-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d2739-145">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d2739-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d2739-146">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="d2739-146">Data privacy and compliance</span></span>

<span data-ttu-id="d2739-147">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers LinkedIn Ads, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="d2739-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d2739-148">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que LinkedIn Ads respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="d2739-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="d2739-149">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d2739-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d2739-150">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d'exportation à tout moment pour stopper l'utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="d2739-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
