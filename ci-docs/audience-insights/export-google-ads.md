---
title: Exporter des données Customer Insights vers Google Ads
description: Apprenez à configurer la connexion et à exporter vers Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c23c8b4e6758df08e04bf1e3ae0cba4dee06fe2b
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305337"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="cd6e1-103">Exporter des segments vers Google Ads (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="cd6e1-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="cd6e1-104">Exportez des segments de profils clients unifiés vers une liste d’audience Google Ads et utilisez-les pour faire de la publicité dans Google Search, Gmail, YouTube et le Réseau Display de Google.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-104">Export segments of unified customer profiles to a Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="cd6e1-105">Conditions préalables à une connexion</span><span class="sxs-lookup"><span data-stu-id="cd6e1-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="cd6e1-106">Vous disposez d’un [compte Google Ads](https://ads.google.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="cd6e1-107">Vous disposez d’un [jeton de développeur Google Ads approuvé](https://developers.google.com/google-ads/api/docs/first-call/dev-token).</span><span class="sxs-lookup"><span data-stu-id="cd6e1-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token).</span></span> 
-   <span data-ttu-id="cd6e1-108">Vous remplissez les conditions de la [Stratégie de correspondance de clients](https://support.google.com/adspolicy/answer/6299717).</span><span class="sxs-lookup"><span data-stu-id="cd6e1-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717).</span></span>
-   <span data-ttu-id="cd6e1-109">Vous remplissez les conditions des [tailles de liste de remarketing](https://support.google.com/google-ads/answer/7558048).</span><span class="sxs-lookup"><span data-stu-id="cd6e1-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048).</span></span>
-   <span data-ttu-id="cd6e1-110">Il existe des audiences dans Google Ads et les ID correspondants.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="cd6e1-111">Pour plus d’informations, consultez [Audiences Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="cd6e1-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="cd6e1-112">Vous avez [configuré des segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="cd6e1-112">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="cd6e1-113">Les profils clients unifiés dans les segments exportés contiennent des champs représentant une adresse e-mail, un prénom et un nom.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="cd6e1-114">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="cd6e1-114">Known limitations</span></span>

- <span data-ttu-id="cd6e1-115">Jusqu’à 1 million de profils par exportation vers Google Ads.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="cd6e1-116">L’exportation vers Google Ads est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="cd6e1-117">L’exportation de segments avec un total de 1 million de profils peut prendre jusqu’à 5 minutes en raison des limitations du côté du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="cd6e1-118">La mise en correspondance dans Google Ads peut prendre jusqu’à 48 heures.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="cd6e1-119">Configurer la connexion à Google Ads</span><span class="sxs-lookup"><span data-stu-id="cd6e1-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="cd6e1-120">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="cd6e1-121">Sélectionnez **Ajouter une connexion** et choisissez **Google Ads** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="cd6e1-122">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="cd6e1-123">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="cd6e1-124">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="cd6e1-125">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-125">Choose who can use this connection.</span></span> <span data-ttu-id="cd6e1-126">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="cd6e1-127">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="cd6e1-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="cd6e1-128">Entrez votre **[ID de client Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="cd6e1-129">Entrez votre **[Jeton de développeur approuvé par Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="cd6e1-130">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="cd6e1-131">Sélectionnez **S’authentifier avec Google Ads** et fournissez vos informations d’identification Google Ads.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="cd6e1-132">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="cd6e1-133">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="cd6e1-134">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="cd6e1-134">Configure an export</span></span>

<span data-ttu-id="cd6e1-135">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="cd6e1-136">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="cd6e1-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="cd6e1-137">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cd6e1-138">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="cd6e1-139">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Google Ads.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="cd6e1-140">Si le nom de la section ne s’affiche pas, aucune connexion de ce type n’est disponible pour vous.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="cd6e1-141">Entrez votre **[ID d’audience Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** et sélectionnez **Connecter** pour initialiser la connexion à Google Ads.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="cd6e1-142">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="cd6e1-143">Répétez les mêmes étapes pour les champs **Prénom** et **Nom**.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-143">Repeat the same steps for **First name** and **Last name** fields.</span></span>

1. <span data-ttu-id="cd6e1-144">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-144">Select the segments you want to export.</span></span> <span data-ttu-id="cd6e1-145">Vous pouvez exporter jusqu’à 1 million de profils clients au total vers Google Ads.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="cd6e1-146">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="cd6e1-147">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cd6e1-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="cd6e1-148">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="cd6e1-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="cd6e1-149">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="cd6e1-149">Data privacy and compliance</span></span>

<span data-ttu-id="cd6e1-150">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Google Ads, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="cd6e1-151">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Google Ads respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="cd6e1-152">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="cd6e1-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="cd6e1-153">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="cd6e1-153">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
