---
title: Exporter des données Customer Insights vers AdRoll
description: Découvrez comment configurer la connexion à AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697071"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="a9e78-103">Connecteur pour AdRoll (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="a9e78-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="a9e78-104">Exportez des segments de profils clients unifiés vers AdRoll et utilisez-les pour la publicité.</span><span class="sxs-lookup"><span data-stu-id="a9e78-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a9e78-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="a9e78-105">Prerequisites</span></span>

-   <span data-ttu-id="a9e78-106">Vous disposez d’un [compte AdRoll](https://www.adroll.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="a9e78-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a9e78-107">Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="a9e78-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a9e78-108">Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="a9e78-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="a9e78-109">Se connecter à AdRoll</span><span class="sxs-lookup"><span data-stu-id="a9e78-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="a9e78-110">Accédez à **Administration** > **Destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="a9e78-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a9e78-111">Sous **AdRoll**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="a9e78-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="a9e78-112">Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="a9e78-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Volet de configuration pour la connexion à AdRoll.":::

1. <span data-ttu-id="a9e78-114">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="a9e78-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a9e78-115">Sélectionnez **Connecter** pour initialiser la connexion à AdRoll.</span><span class="sxs-lookup"><span data-stu-id="a9e78-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="a9e78-116">Sélectionnez **S’authentifier avec AdRoll** et fournissez vos informations d’administrateur pour AdRoll.</span><span class="sxs-lookup"><span data-stu-id="a9e78-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="a9e78-117">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a9e78-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a9e78-118">Entrez votre **ID d’annonceur AdRoll** [possibilité de publicité AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="a9e78-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="a9e78-119">Sélectionnez **Suivant** pour configurer l’exportation.</span><span class="sxs-lookup"><span data-stu-id="a9e78-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="a9e78-120">Configurer le connecteur</span><span class="sxs-lookup"><span data-stu-id="a9e78-120">Configure the connector</span></span>

1. <span data-ttu-id="a9e78-121">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="a9e78-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a9e78-122">Il est nécessaire d’exporter des segments vers AdRoll.</span><span class="sxs-lookup"><span data-stu-id="a9e78-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="a9e78-123">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="a9e78-123">Select the segments you want to export.</span></span> <span data-ttu-id="a9e78-124">Sélectionnez un segment avec au moins 100 membres.</span><span class="sxs-lookup"><span data-stu-id="a9e78-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="a9e78-125">Vous ne pouvez pas exporter des segments plus petits.</span><span class="sxs-lookup"><span data-stu-id="a9e78-125">You can't export smaller segments.</span></span> <span data-ttu-id="a9e78-126">De plus, la taille maximale d’un segment à exporter est de 250 000 membres par exportation.</span><span class="sxs-lookup"><span data-stu-id="a9e78-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="a9e78-127">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a9e78-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a9e78-128">Exporter les données</span><span class="sxs-lookup"><span data-stu-id="a9e78-128">Export the data</span></span>

<span data-ttu-id="a9e78-129">Vous pouvez [exporter les données à la demande](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a9e78-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a9e78-130">L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a9e78-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a9e78-131">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="a9e78-131">Known limitations</span></span>

- <span data-ttu-id="a9e78-132">Vous pouvez exporter jusqu’à 250 000 profils par exportation vers AdRoll.</span><span class="sxs-lookup"><span data-stu-id="a9e78-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="a9e78-133">Vous ne pouvez pas exporter de segments contenant moins de 100 profils vers AdRoll.</span><span class="sxs-lookup"><span data-stu-id="a9e78-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="a9e78-134">L’exportation vers AdRoll est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="a9e78-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="a9e78-135">L’exportation de jusqu’à 250 000 profils vers AdRoll peut prendre jusqu’à 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="a9e78-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="a9e78-136">Le nombre de profils que vous pouvez exporter vers AdRoll dépend et est limité par votre contrat avec AdRoll.</span><span class="sxs-lookup"><span data-stu-id="a9e78-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a9e78-137">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="a9e78-137">Data privacy and compliance</span></span>

<span data-ttu-id="a9e78-138">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers AdRoll, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="a9e78-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a9e78-139">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que AdRoll respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="a9e78-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a9e78-140">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a9e78-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a9e78-141">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="a9e78-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
