---
title: Exporter des données Customer Insights vers Mailchimp
description: Découvrez comment configurer la connexion à Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598198"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="e4373-103">Connecteur pour Mailchimp (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="e4373-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="e4373-104">Exportez des segments de profils clients unifiés vers Mailchimp pour créer des bulletins d’informations et des campagnes par e-mail.</span><span class="sxs-lookup"><span data-stu-id="e4373-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e4373-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="e4373-105">Prerequisites</span></span>

-   <span data-ttu-id="e4373-106">Vous disposez d’un [compte Mailchimp](https://mailchimp.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="e4373-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e4373-107">Il existe des audiences dans Mailchimp et les ID correspondants.</span><span class="sxs-lookup"><span data-stu-id="e4373-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="e4373-108">Pour plus d’informations, consultez [Audiences Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="e4373-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="e4373-109">Vous avez [configuré des segments](segments.md)</span><span class="sxs-lookup"><span data-stu-id="e4373-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="e4373-110">Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="e4373-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="e4373-111">Se connecter à Mailchimp</span><span class="sxs-lookup"><span data-stu-id="e4373-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="e4373-112">Accédez à **Administration** > **Destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="e4373-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e4373-113">Sous **Mailchimp**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="e4373-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="e4373-114">Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="e4373-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e4373-115">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="e4373-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e4373-116">Entrez votre **[ID d’audience Mailchimp](https://mailchimp.com/help/find-audience-id/)** et sélectionnez **Connecter** pour initialiser la connexion à Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e4373-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="e4373-117">Sélectionnez **S’authentifier avec Mailchimp** et fournissez vos informations d’identification Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e4373-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="e4373-118">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e4373-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Capture d’écran d’exportation pour la connexion à Mailchimp":::

1. <span data-ttu-id="e4373-120">Sélectionnez **Suivant** pour configurer l’exportation.</span><span class="sxs-lookup"><span data-stu-id="e4373-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="e4373-121">Configurer le connecteur</span><span class="sxs-lookup"><span data-stu-id="e4373-121">Configure the connector</span></span>

1. <span data-ttu-id="e4373-122">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="e4373-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="e4373-123">Vous pouvez éventuellement exporter les champs **Prénom** et **Nom** comme champs supplémentaires pour créer des e-mails plus personnalisés.</span><span class="sxs-lookup"><span data-stu-id="e4373-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="e4373-124">Sélectionnez **Ajouter un attribut** pour mapper ces champs.</span><span class="sxs-lookup"><span data-stu-id="e4373-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e4373-125">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="e4373-125">Select the segments you want to export.</span></span> <span data-ttu-id="e4373-126">Vous pouvez exporter jusqu’à 1 million de profils clients au total vers Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e4373-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Sélectionner les champs et les segments à exporter vers Mailchimp":::

1. <span data-ttu-id="e4373-128">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e4373-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e4373-129">Exporter les données</span><span class="sxs-lookup"><span data-stu-id="e4373-129">Export the data</span></span>

<span data-ttu-id="e4373-130">Vous pouvez [exporter les données à la demande](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e4373-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e4373-131">L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e4373-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e4373-132">Dans Mailchimp, vous trouverez désormais vos segments sous [Audiences Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="e4373-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e4373-133">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="e4373-133">Known limitations</span></span>

- <span data-ttu-id="e4373-134">Jusqu’à 1 million de profils par exportation vers Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e4373-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="e4373-135">L’exportation vers Mailchimp est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="e4373-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="e4373-136">L’exportation de segments avec un total de 1 million de profils peut prendre jusqu’à trois heures en raison des limitations du côté du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="e4373-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="e4373-137">Le nombre de profils que vous pouvez exporter vers Mailchimp dépend et est limité par votre contrat avec Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e4373-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e4373-138">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="e4373-138">Data privacy and compliance</span></span>

<span data-ttu-id="e4373-139">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Mailchimp, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="e4373-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e4373-140">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Mailchimp respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="e4373-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e4373-141">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e4373-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e4373-142">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="e4373-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]