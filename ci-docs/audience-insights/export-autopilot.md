---
title: Exporter des données Customer Insights vers Autopilot
description: Découvrez comment configurer la connexion à Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269235"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="0514c-103">Connecteur pour Autopilot (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="0514c-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="0514c-104">Exportez des segments de profils clients unifiés vers Autopilot et utilisez-les pour le marketing par e-mail dans Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0514c-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="0514c-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="0514c-105">Prerequisites</span></span>

-   <span data-ttu-id="0514c-106">Vous disposez d’un [compte Autopilot](https://www.autopilothq.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="0514c-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0514c-107">Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="0514c-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0514c-108">Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="0514c-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="0514c-109">Se connecter Autopilot</span><span class="sxs-lookup"><span data-stu-id="0514c-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="0514c-110">Accédez à **Administration** > **Destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="0514c-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0514c-111">Sous **Autopilot**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="0514c-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="0514c-112">Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="0514c-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Volet de configuration pour la connexion à Autopilot.":::

1. <span data-ttu-id="0514c-114">Entrez votre **Clé API Autopilot** [Clé API Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="0514c-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="0514c-115">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="0514c-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0514c-116">Sélectionnez **Connecter** pour initialiser la connexion à Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0514c-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="0514c-117">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0514c-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0514c-118">Sélectionnez **Suivant** pour configurer l’exportation.</span><span class="sxs-lookup"><span data-stu-id="0514c-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="0514c-119">Configurer le connecteur</span><span class="sxs-lookup"><span data-stu-id="0514c-119">Configure the connector</span></span>

1. <span data-ttu-id="0514c-120">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="0514c-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0514c-121">Répétez les mêmes étapes pour les autres champs facultatifs tels que **Prénom** et **Nom**.</span><span class="sxs-lookup"><span data-stu-id="0514c-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="0514c-122">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="0514c-122">Select the segments you want to export.</span></span> <span data-ttu-id="0514c-123">Nous **recommandons vivement de ne pas exporter plus de 100 000 profils clients au total** vers Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0514c-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="0514c-124">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0514c-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0514c-125">Exporter les données</span><span class="sxs-lookup"><span data-stu-id="0514c-125">Export the data</span></span>

<span data-ttu-id="0514c-126">Vous pouvez [exporter les données à la demande](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="0514c-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="0514c-127">L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0514c-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0514c-128">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="0514c-128">Known limitations</span></span>

- <span data-ttu-id="0514c-129">Vous pouvez exporter jusqu’à 100 000 profils clients au total vers Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0514c-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="0514c-130">L’exportation vers Autopilot est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="0514c-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="0514c-131">L’exportation de jusqu’à 100 000 profils vers Autopilot peut prendre jusqu’à quelques heures.</span><span class="sxs-lookup"><span data-stu-id="0514c-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="0514c-132">Le nombre de profils que vous pouvez exporter vers Autopilot dépend et est limité par votre contrat avec Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0514c-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0514c-133">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="0514c-133">Data privacy and compliance</span></span>

<span data-ttu-id="0514c-134">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Autopilot, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="0514c-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0514c-135">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Autopilot respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="0514c-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="0514c-136">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0514c-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0514c-137">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="0514c-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]