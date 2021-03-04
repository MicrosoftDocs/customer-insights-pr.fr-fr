---
title: Exporter des données Customer Insights vers Facebook Ads Manager
description: Découvrez comment configurer la connexion au Gestionnaire d’annonces Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269971"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="d3e7c-103">Connecteur pour le gestionnaire d’annonces Facebook (préversion)</span><span class="sxs-lookup"><span data-stu-id="d3e7c-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="d3e7c-104">Exportez des segments de profils client unifiés vers le gestionnaire d’annonces Facebook pour créer des campagnes sur Facebook et Instagram.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3e7c-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="d3e7c-105">Prerequisites</span></span>

- <span data-ttu-id="d3e7c-106">Vous devez avoir un [compte **Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) comprenant un [compte professionnel **Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="d3e7c-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="d3e7c-107">Vous devez être un administrateur du [compte **Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="d3e7c-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="d3e7c-108">Se connecter au gestionnaire d’annonces Facebook</span><span class="sxs-lookup"><span data-stu-id="d3e7c-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="d3e7c-109">Accédez à **Administration** > **Destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d3e7c-110">Sous le **gestionnaire d’annonces Facebook**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="d3e7c-111">Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="d3e7c-112">Sélectionner **Continue avec Facebook** pour vous connecter à votre compte publicitaire Facebook.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="d3e7c-113">Activez l’autorisation **ads_management** après l’authentification dans Facebook.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="d3e7c-114">Sélectionnez le **Compte d’annonces Facebook** que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="d3e7c-115">Sélectionnez une **Audience personnalisée existante** dans la liste déroulante ou créez une **Nouvelle audience personnalisée**.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="d3e7c-116">Pour plus d’informations, voir [**Audiences dans le gestionnaire d’annonces Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="d3e7c-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="d3e7c-117">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d3e7c-118">Sélectionnez **Suivant** pour configurer l’exportation.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="d3e7c-119">Configurer le connecteur</span><span class="sxs-lookup"><span data-stu-id="d3e7c-119">Configure the connector</span></span>

1. <span data-ttu-id="d3e7c-120">Dans le champ **Sélectionner votre champ d’identificateur de la clé**, sélectionnez **E-mail**, **Nom et adresse** ou **Téléphone** à envoyer au gestionnaire d’annonces Facebook.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="d3e7c-121">Mappez les attributs correspondants de votre entité client unifiée pour l’identifiant de clé sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="d3e7c-122">[CONSEIL] Les meilleures chances pour une correspondance se produisent si vous sélectionnez **E-mail** comme identificateur de la clé.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="d3e7c-123">L’ajout d’identificateurs supplémentaires peut améliorer la correspondance.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="d3e7c-124">Sélectionnez **Ajouter un attribut** pour mapper des attributs supplémentaires à envoyer au gestionnaire d’annonces Facebook.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="d3e7c-125">Les attributs du gestionnaire d’annonces Facebook correspondent aux noms conviviaux des utilisateurs suivants : **FN** = **Prénom**, **LN** = **Nom de famille**, **FI** = **Première initiale**, **PHONE** = **Téléphone**, **GEN** = **Sexe**, **DOB** = **Date de naissance**, **ST** = **État**, **CT** = **Ville**, **ZIP** = **Code postal**, **COUNTRY** = **Pays/Région**</span><span class="sxs-lookup"><span data-stu-id="d3e7c-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="d3e7c-126">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="d3e7c-127">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d3e7c-128">Exporter les données</span><span class="sxs-lookup"><span data-stu-id="d3e7c-128">Export the data</span></span>

<span data-ttu-id="d3e7c-129">Vous pouvez [exporter les données à la demande](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d3e7c-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="d3e7c-130">L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d3e7c-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d3e7c-131">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="d3e7c-131">Known limitations</span></span>

- <span data-ttu-id="d3e7c-132">Jusqu’à 10 millions de profils clients par exportation vers le Gestionnaire publicités Facebook</span><span class="sxs-lookup"><span data-stu-id="d3e7c-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="d3e7c-133">L’exportation vers le Gestionnaire de publicités Facebook est limitée aux segments</span><span class="sxs-lookup"><span data-stu-id="d3e7c-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="d3e7c-134">L’exportation de segments avec un total de 10 million de profils peut prendre jusqu’à 90 minutes pour se terminer</span><span class="sxs-lookup"><span data-stu-id="d3e7c-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d3e7c-135">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="d3e7c-135">Data privacy and compliance</span></span>

<span data-ttu-id="d3e7c-136">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Facebook Ads Manager, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d3e7c-137">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Facebook Ads respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="d3e7c-138">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d3e7c-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d3e7c-139">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="d3e7c-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]