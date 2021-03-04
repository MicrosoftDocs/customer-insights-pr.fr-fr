---
title: Exporter des données Customer Insights vers DotDigital
description: Découvrez comment configurer la connexion à DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269097"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="48c48-103">Connecteur pour DotDigital (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="48c48-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="48c48-104">Exportez des segments de profils clients unifiés vers les carnets d’adresses DotDigital et utilisez-les pour les campagnes, le marketing par e-mail, ainsi que pour créer des segments de client avec DotDigital.</span><span class="sxs-lookup"><span data-stu-id="48c48-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="48c48-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="48c48-105">Prerequisites</span></span>

-   <span data-ttu-id="48c48-106">Vous disposez d’un [compte DotDigital](https://dotdigital.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="48c48-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="48c48-107">Il existe des carnets d’adresses dans DotDigital et les ID correspondants.</span><span class="sxs-lookup"><span data-stu-id="48c48-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="48c48-108">L’ID se trouve dans l’URL lorsque vous sélectionnez et ouvrez un carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="48c48-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="48c48-109">Pour plus d’informations, consultez [Carnets d’adresses DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="48c48-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="48c48-110">Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="48c48-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="48c48-111">Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="48c48-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="48c48-112">Se connecter à DotDigital</span><span class="sxs-lookup"><span data-stu-id="48c48-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="48c48-113">Accédez à **Administration** > **Destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="48c48-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="48c48-114">Sous **DotDigital**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="48c48-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="48c48-115">Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="48c48-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Volet de configuration pour l’exportation vers DotDigital.":::

1. <span data-ttu-id="48c48-117">Entrez vos **Nom d’utilisateur et mot de passe DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="48c48-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="48c48-118">Entrez votre **[ID de carnet d’adresses DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="48c48-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="48c48-119">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="48c48-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="48c48-120">Sélectionnez **Connecter** pour initialiser la connexion à DotDigital.</span><span class="sxs-lookup"><span data-stu-id="48c48-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="48c48-121">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="48c48-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="48c48-122">Sélectionnez **Suivant** pour configurer l’exportation.</span><span class="sxs-lookup"><span data-stu-id="48c48-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="48c48-123">Configurer le connecteur</span><span class="sxs-lookup"><span data-stu-id="48c48-123">Configure the connector</span></span>

1. <span data-ttu-id="48c48-124">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="48c48-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="48c48-125">Répétez les mêmes étapes pour les autres champs facultatifs tels que **Prénom**, **Nom**, **Nom complet**, **Sexe** et **Code postal**.</span><span class="sxs-lookup"><span data-stu-id="48c48-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="48c48-126">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="48c48-126">Select the segments you want to export.</span></span> <span data-ttu-id="48c48-127">Vous pouvez exporter jusqu’à 1 million de profils clients au total vers DotDigital.</span><span class="sxs-lookup"><span data-stu-id="48c48-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="48c48-128">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="48c48-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="48c48-129">Exporter les données</span><span class="sxs-lookup"><span data-stu-id="48c48-129">Export the data</span></span>

<span data-ttu-id="48c48-130">Vous pouvez [exporter les données à la demande](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="48c48-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="48c48-131">L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="48c48-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="48c48-132">Dans DotDigital, vous trouverez désormais vos segments dans le [Carnets d’adresses DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="48c48-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="48c48-133">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="48c48-133">Known limitations</span></span>

- <span data-ttu-id="48c48-134">Jusqu’à 1 million de profils par exportation vers DotDigital.</span><span class="sxs-lookup"><span data-stu-id="48c48-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="48c48-135">L’exportation vers DotDigital est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="48c48-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="48c48-136">L’exportation de segments avec un total de 1 million de profils peut prendre jusqu’à 3 heures en raison des limitations du côté du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="48c48-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="48c48-137">Le nombre de profils que vous pouvez exporter vers DotDigital dépend et est limité par votre contrat avec DotDigital.</span><span class="sxs-lookup"><span data-stu-id="48c48-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="48c48-138">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="48c48-138">Data privacy and compliance</span></span>

<span data-ttu-id="48c48-139">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers DotDigital, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="48c48-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="48c48-140">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que DotDigital respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="48c48-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="48c48-141">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="48c48-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="48c48-142">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="48c48-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]