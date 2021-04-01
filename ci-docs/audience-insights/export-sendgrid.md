---
title: Exporter des données Customer Insights vers SendGrid
description: Découvrez comment configurer la connexion à SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597278"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="127c3-103">Connecteur pour SendGrid (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="127c3-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="127c3-104">Exportez des segments de profils clients unifiés vers les listes de contacts SendGrid et utilisez-les pour les campagnes marketing et par e-mail dans SendGrid.</span><span class="sxs-lookup"><span data-stu-id="127c3-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="127c3-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="127c3-105">Prerequisites</span></span>

-   <span data-ttu-id="127c3-106">Vous disposez d’un [compte SendGrid](https://sendgrid.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="127c3-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="127c3-107">Il existe des listes de contacts dans SendGrid et les ID correspondants.</span><span class="sxs-lookup"><span data-stu-id="127c3-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="127c3-108">Pour plus d’informations, voir [SendGrid – Gérer les contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="127c3-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="127c3-109">Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="127c3-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="127c3-110">Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="127c3-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="127c3-111">Se connecter à SendGrid</span><span class="sxs-lookup"><span data-stu-id="127c3-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="127c3-112">Accédez à **Administration** > **Destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="127c3-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="127c3-113">Sous **SendGrid**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="127c3-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="127c3-114">Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="127c3-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Volet de configuration d’exportation SendGrid.":::

1. <span data-ttu-id="127c3-116">Entrez votre **Clé API SendGrid** [Clé API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="127c3-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="127c3-117">Entrez votre **[ID de liste SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="127c3-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="127c3-118">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="127c3-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="127c3-119">Sélectionnez **Connecter** pour initialiser la connexion à SendGrid.</span><span class="sxs-lookup"><span data-stu-id="127c3-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="127c3-120">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="127c3-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="127c3-121">Sélectionnez **Suivant** pour configurer l’exportation.</span><span class="sxs-lookup"><span data-stu-id="127c3-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="127c3-122">Configurer le connecteur</span><span class="sxs-lookup"><span data-stu-id="127c3-122">Configure the connector</span></span>

1. <span data-ttu-id="127c3-123">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="127c3-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="127c3-124">Répétez les mêmes étapes pour les autres champs facultatifs tels que **Prénom**, **Nom**, **Pays/Région**, **État**, **Ville** et **Code postal**.</span><span class="sxs-lookup"><span data-stu-id="127c3-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="127c3-125">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="127c3-125">Select the segments you want to export.</span></span> <span data-ttu-id="127c3-126">Nous **recommandons vivement de ne pas exporter plus de 100 000 profils clients au total** vers SendGrid.</span><span class="sxs-lookup"><span data-stu-id="127c3-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="127c3-127">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="127c3-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="127c3-128">Exporter les données</span><span class="sxs-lookup"><span data-stu-id="127c3-128">Export the data</span></span>

<span data-ttu-id="127c3-129">Vous pouvez [exporter les données à la demande](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="127c3-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="127c3-130">L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="127c3-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="127c3-131">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="127c3-131">Known limitations</span></span>

- <span data-ttu-id="127c3-132">Jusqu’à 100 000 profils au total vers SendGrid.</span><span class="sxs-lookup"><span data-stu-id="127c3-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="127c3-133">L’exportation vers SendGrid est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="127c3-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="127c3-134">L’exportation de jusqu’à 100 000 profils vers SendGrid peut prendre jusqu’à quelques heures.</span><span class="sxs-lookup"><span data-stu-id="127c3-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="127c3-135">Le nombre de profils que vous pouvez exporter vers SendGrid dépend et est limité par votre contrat avec SendGrid.</span><span class="sxs-lookup"><span data-stu-id="127c3-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="127c3-136">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="127c3-136">Data privacy and compliance</span></span>

<span data-ttu-id="127c3-137">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers SendGrid, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="127c3-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="127c3-138">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que SendGrid respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="127c3-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="127c3-139">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="127c3-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="127c3-140">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="127c3-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]