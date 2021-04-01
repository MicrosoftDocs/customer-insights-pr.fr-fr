---
title: Enrichissement avec l’enrichissement tiers de HERE Technologies
description: Informations générales sur l’enrichissement tiers de HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597738"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="8dde1-103">Enrichissement de profils clients avec HERE Technologies (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="8dde1-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="8dde1-104">HERE Technologies est une société de plateforme de localisation qui fournit des données et des services axés sur la localisation.</span><span class="sxs-lookup"><span data-stu-id="8dde1-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="8dde1-105">Avec les services d’enrichissement de données de HERE Technologies, vous pouvez avoir une idée plus précise de la localisation de vos clients avec la normalisation de l’adresse, l’extraction de la latitude et la longitude, etc.</span><span class="sxs-lookup"><span data-stu-id="8dde1-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8dde1-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="8dde1-106">Prerequisites</span></span>

<span data-ttu-id="8dde1-107">Pour configurer des enrichissements HERE Technologies, les conditions préalables suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="8dde1-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="8dde1-108">Vous disposez d’un abonnement HERE Technologies actif.</span><span class="sxs-lookup"><span data-stu-id="8dde1-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="8dde1-109">Pour obtenir un abonnement, vous pouvez vous [inscrire ici](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [contacter HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directement.</span><span class="sxs-lookup"><span data-stu-id="8dde1-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="8dde1-110">En savoir plus sur l’enrichissement de la localisation de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8dde1-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="8dde1-111">Vous disposez de la clé API de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8dde1-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="8dde1-112">Vous disposez d’autorisations [Administrateur](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="8dde1-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="8dde1-113">configuration</span><span class="sxs-lookup"><span data-stu-id="8dde1-113">Configuration</span></span>

1. <span data-ttu-id="8dde1-114">Accédez à **Données** > **Enrichissement**.</span><span class="sxs-lookup"><span data-stu-id="8dde1-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="8dde1-115">Sélectionnez **Enrichir mes données** sur la vignette de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8dde1-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8dde1-116">![Vignette de HERE Technologies](media/HERE-tile.png "Vignette de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="8dde1-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="8dde1-117">Entrez une **Clé API HERE Technologies** active.</span><span class="sxs-lookup"><span data-stu-id="8dde1-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="8dde1-118">Vérifiez et donnez votre consentement pour **Confidentialité et conformité des données** en cochant la case **J’accepte**.</span><span class="sxs-lookup"><span data-stu-id="8dde1-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="8dde1-119">Confirmez les deux entrées en sélectionnant **Se connecter à HERE**.</span><span class="sxs-lookup"><span data-stu-id="8dde1-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="8dde1-120">Sélectionnez **Ajouter des données** et choisissez le **Jeu de données client** que vous souhaitez enrichir avec les données géographiques de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8dde1-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="8dde1-121">Vous pouvez sélectionner l’entité **Client** pour enrichir tous vos profils clients ou sélectionner une entité segment pour enrichir uniquement les profils clients contenus dans ce segment.</span><span class="sxs-lookup"><span data-stu-id="8dde1-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Capture d’écran lors du choix du jeu de données client.":::

1. <span data-ttu-id="8dde1-123">Choisissez si vous souhaitez mapper les champs à l’adresse principale et/ou secondaire.</span><span class="sxs-lookup"><span data-stu-id="8dde1-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="8dde1-124">Vous pouvez spécifier un mappage de champ pour les deux adresses (par exemple, une adresse personnelle et professionnelle) et enrichir les profils pour les deux adresses séparément.</span><span class="sxs-lookup"><span data-stu-id="8dde1-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="8dde1-125">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8dde1-125">Select **Next**.</span></span>

1. <span data-ttu-id="8dde1-126">Définissez quels champs de vos profils unifiés doivent être utilisés pour rechercher les données de localisation correspondantes de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8dde1-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="8dde1-127">Les champs **Rue 1** et **Code postal** sont obligatoires pour l’adresse principale et/ou secondaire sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8dde1-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="8dde1-128">Pour une plus grande précision de la correspondance, des champs supplémentaires peuvent être ajoutés.</span><span class="sxs-lookup"><span data-stu-id="8dde1-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8dde1-129">![Page de configuration de l’enrichissement de HERE Technologies](media/enrichment-HERE-configuration.png "Page de configuration de l’enrichissement de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="8dde1-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="8dde1-130">Sélectionnez **Appliquer** pour terminer le mappage de champ.</span><span class="sxs-lookup"><span data-stu-id="8dde1-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="8dde1-131">Résultats d’enrichissement</span><span class="sxs-lookup"><span data-stu-id="8dde1-131">Enrichment results</span></span>

<span data-ttu-id="8dde1-132">Pour démarrer le processus d’enrichissement, sélectionnez **Exécuter** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="8dde1-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="8dde1-133">Vous pouvez également laisser le système exécuter l’enrichissement automatiquement dans le cadre d’une [actualisation programmée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8dde1-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8dde1-134">Le temps de traitement dépendra de la taille de vos données client et des temps de réponse de l’API de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8dde1-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="8dde1-135">Une fois le processus d’enrichissement terminé, vous pouvez consulter les données des profils clients nouvellement enrichis sous **Mes enrichissements**.</span><span class="sxs-lookup"><span data-stu-id="8dde1-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="8dde1-136">De plus, vous trouverez l’heure de la dernière mise à jour et le nombre de profils enrichis.</span><span class="sxs-lookup"><span data-stu-id="8dde1-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="8dde1-137">Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.</span><span class="sxs-lookup"><span data-stu-id="8dde1-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8dde1-138">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="8dde1-138">Next steps</span></span>

<span data-ttu-id="8dde1-139">Exploitez vos données client enrichies.</span><span class="sxs-lookup"><span data-stu-id="8dde1-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="8dde1-140">Créez des [Segments](segments.md), des [Mesures](measures.md), voire [Exportez des données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.</span><span class="sxs-lookup"><span data-stu-id="8dde1-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8dde1-141">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="8dde1-141">Data privacy and compliance</span></span>

<span data-ttu-id="8dde1-142">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers HERE Technologies, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="8dde1-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8dde1-143">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que HERE Technologies respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="8dde1-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8dde1-144">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8dde1-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8dde1-145">Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="8dde1-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]