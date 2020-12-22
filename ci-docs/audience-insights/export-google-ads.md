---
title: Exporter des données Customer Insights vers Google Ads
description: Découvrez comment configurer la connexion à Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568433"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="6ac0d-103">Connecteur pour Google Ads (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="6ac0d-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="6ac0d-104">Exportez des segments de profils clients unifiés vers la liste d'audience Google Ads et utilisez-les pour faire de la publicité sur Google Search, Gmail, YouTube et le Réseau Display de Google.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="6ac0d-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="6ac0d-105">Prerequisites</span></span>

-   <span data-ttu-id="6ac0d-106">Vous disposez d'un [compte Google Ads](https://ads.google.com/) et des informations d'identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6ac0d-107">Il existe des audiences dans Google Ads et les ID correspondants.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="6ac0d-108">Pour plus d'informations, consultez [Audiences Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="6ac0d-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="6ac0d-109">Vous avez [configuré des segments](segments.md)</span><span class="sxs-lookup"><span data-stu-id="6ac0d-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="6ac0d-110">Les profils clients unifiés dans les segments exportés contiennent des champs représentant une adresse e-mail, un prénom et un nom</span><span class="sxs-lookup"><span data-stu-id="6ac0d-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="6ac0d-111">Se connecter à Google Ads</span><span class="sxs-lookup"><span data-stu-id="6ac0d-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="6ac0d-112">Accédez à **Administration** > **Destinations d'exportation**.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6ac0d-113">Sous **Google Ads**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="6ac0d-114">Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="6ac0d-115">Entrez votre **[ID de client Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="6ac0d-116">Entrez votre **[Jeton de développeur approuvé par Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="6ac0d-117">Sélectionnez **J'accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6ac0d-118">Entrez votre **[ID d'audience Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** et sélectionnez **Connecter** pour initialiser la connexion à Google Ads.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="6ac0d-119">Sélectionnez **S'authentifier avec Google Ads** et fournissez vos informations d'identification Google Ads.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="6ac0d-120">Sélectionnez **Vous ajouter en tant qu'utilisateur à exporter** et fournissez vos informations d'identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Capture d'écran d'exportation pour la connexion à Google Ads":::

1. <span data-ttu-id="6ac0d-122">Sélectionnez **Suivant** pour configurer l'exportation.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="6ac0d-123">Configurer le connecteur</span><span class="sxs-lookup"><span data-stu-id="6ac0d-123">Configure the connector</span></span>

1. <span data-ttu-id="6ac0d-124">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l'adresse e-mail d'un client.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6ac0d-125">Répétez les mêmes étapes pour les champs **Prénom** et **Nom**.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="6ac0d-126">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-126">Select the segments you want to export.</span></span> <span data-ttu-id="6ac0d-127">Vous pouvez exporter jusqu'à 1 million de profils clients au total vers Google Ads.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="6ac0d-128">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6ac0d-129">Exporter les données</span><span class="sxs-lookup"><span data-stu-id="6ac0d-129">Export the data</span></span>

<span data-ttu-id="6ac0d-130">Vous pouvez [exporter les données à la demande](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6ac0d-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6ac0d-131">L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6ac0d-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6ac0d-132">Dans Google Ads, vous trouverez désormais vos segments sous [Audiences Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="6ac0d-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6ac0d-133">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="6ac0d-133">Known limitations</span></span>

- <span data-ttu-id="6ac0d-134">Jusqu'à 1 million de profils par exportation vers Google Ads.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="6ac0d-135">L'exportation vers Google Ads est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="6ac0d-136">L'exportation de segments avec un total de 1 million de profils peut prendre jusqu'à 5 minutes en raison des limitations du côté du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="6ac0d-137">La mise en correspondance dans Google Ads peut prendre jusqu'à 48 heures.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6ac0d-138">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="6ac0d-138">Data privacy and compliance</span></span>

<span data-ttu-id="6ac0d-139">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Google Ads, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6ac0d-140">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Google Ads respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="6ac0d-141">Pour plus d'informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6ac0d-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6ac0d-142">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d'exportation à tout moment pour interrompre l'utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="6ac0d-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
