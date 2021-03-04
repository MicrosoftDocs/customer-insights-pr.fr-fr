---
title: Enrichissement des profils d’entreprise avec l’enrichissement tiers de Leadspace
description: Informations générales sur l’enrichissement tiers de Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269419"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="8979c-103">Enrichissement des profils d’entreprise avec Leadspace (aperçu)</span><span class="sxs-lookup"><span data-stu-id="8979c-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="8979c-104">Leadspace est une entreprise de science des données qui fournit une plateforme de données client B2B.</span><span class="sxs-lookup"><span data-stu-id="8979c-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="8979c-105">Elle permet aux clients ayant un profil client unifié pour les entreprises d’enrichir leurs données.</span><span class="sxs-lookup"><span data-stu-id="8979c-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="8979c-106">Les enrichissements comprennent des attributs supplémentaires tels que la taille de l’entreprise, sa localisation, son secteur d’activité, etc.</span><span class="sxs-lookup"><span data-stu-id="8979c-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8979c-107">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="8979c-107">Prerequisites</span></span>

<span data-ttu-id="8979c-108">Pour configurer Leadspace, les conditions préalables suivantes doivent être respectées :</span><span class="sxs-lookup"><span data-stu-id="8979c-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="8979c-109">Vous disposez d’une licence Leadspace active et de la « clé perpétuelle » (appelée **Jeton Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="8979c-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="8979c-110">Contactez directement [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) pour en savoir plus sur leur produit.</span><span class="sxs-lookup"><span data-stu-id="8979c-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="8979c-111">Vous disposez d’autorisations [Administrateur](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="8979c-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="8979c-112">Vous avez des [profils clients unifiés](customer-profiles.md) pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="8979c-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="8979c-113">configuration</span><span class="sxs-lookup"><span data-stu-id="8979c-113">Configuration</span></span>

1. <span data-ttu-id="8979c-114">Dans les informations sur l’audience, accédez à **Données** > **Enrichissement**.</span><span class="sxs-lookup"><span data-stu-id="8979c-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="8979c-115">Sélectionnez **Enrichir mes données** sur la vignette Leadspace.</span><span class="sxs-lookup"><span data-stu-id="8979c-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Capture d’écran de la vignette de Leadspace.":::

1. <span data-ttu-id="8979c-117">Sélectionnez **Démarrer**, puis entrez un **Jeton Leadspace** actif (clé perpétuelle).</span><span class="sxs-lookup"><span data-stu-id="8979c-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="8979c-118">Vérifiez et donnez votre consentement pour **Confidentialité et conformité des données** en cochant la case **J’accepte**.</span><span class="sxs-lookup"><span data-stu-id="8979c-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="8979c-119">Confirmez les deux entrées en sélectionnant **Se connecter à Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="8979c-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="8979c-120">Sélectionnez **Mapper des données** et choisissez le jeu de données à enrichir avec les données d’entreprise de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="8979c-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="8979c-121">Vous pouvez sélectionner l’entité *Client* pour enrichir tous vos profils clients ou sélectionner une entité segment pour enrichir uniquement les profils clients contenus dans ce segment.</span><span class="sxs-lookup"><span data-stu-id="8979c-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Choisissez entre le profil client et l’enrichissement du segment.":::

1. <span data-ttu-id="8979c-123">Cliquez sur **Suivant** et définissez quels champs de vos profils unifiés doivent être utilisés pour rechercher les données d’entreprise correspondantes de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="8979c-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="8979c-124">Le champ **Nom de la société** est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="8979c-124">The **Name of company** field is required.</span></span> <span data-ttu-id="8979c-125">Pour une plus grande précision de la correspondance, jusqu’à deux autres champs, **Site web de la société** et **Emplacement de la société**, peuvent être ajoutés.</span><span class="sxs-lookup"><span data-stu-id="8979c-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Volet de mappage de champ de Leadspace.":::
   
1. <span data-ttu-id="8979c-127">Sélectionnez **Appliquer** pour terminer le mappage de champ.</span><span class="sxs-lookup"><span data-stu-id="8979c-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="8979c-128">Sélectionnez **Exécuter** pour enrichir les profils d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="8979c-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="8979c-129">La durée d’un enrichissement dépend du nombre de profils clients unifiés.</span><span class="sxs-lookup"><span data-stu-id="8979c-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="8979c-130">Résultats d’enrichissement</span><span class="sxs-lookup"><span data-stu-id="8979c-130">Enrichment results</span></span>

<span data-ttu-id="8979c-131">Après avoir actualisé l’enrichissement, vous pouvez consulter les données d’entreprise nouvellement enrichies sous [Mes enrichissements](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="8979c-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="8979c-132">Vous pouvez trouver l’heure de la dernière mise à jour et le nombre de profils enrichis.</span><span class="sxs-lookup"><span data-stu-id="8979c-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="8979c-133">Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.</span><span class="sxs-lookup"><span data-stu-id="8979c-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="8979c-134">Pour plus d’informations, voir [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="8979c-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8979c-135">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="8979c-135">Next steps</span></span>

<span data-ttu-id="8979c-136">Exploitez vos données client enrichies.</span><span class="sxs-lookup"><span data-stu-id="8979c-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="8979c-137">Créez des [Segments](segments.md), des [Mesures](measures.md), voire [Exportez des données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.</span><span class="sxs-lookup"><span data-stu-id="8979c-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8979c-138">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="8979c-138">Data privacy and compliance</span></span>

<span data-ttu-id="8979c-139">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Leadspace, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="8979c-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8979c-140">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Leadspace respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="8979c-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8979c-141">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8979c-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8979c-142">Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="8979c-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]