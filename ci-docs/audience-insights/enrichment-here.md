---
title: Enrichissement avec l’enrichissement tiers de HERE Technologies
description: Informations générales sur l’enrichissement tiers de HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305291"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="48840-103">Enrichissement de profils clients avec HERE Technologies (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="48840-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="48840-104">HERE Technologies est une société de plateforme de localisation qui fournit des données et des services axés sur la localisation.</span><span class="sxs-lookup"><span data-stu-id="48840-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="48840-105">Avec les services d’enrichissement de données de HERE Technologies, vous pouvez avoir une idée plus précise de la localisation de vos clients avec la normalisation de l’adresse, l’extraction de la latitude et la longitude, etc.</span><span class="sxs-lookup"><span data-stu-id="48840-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="48840-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="48840-106">Prerequisites</span></span>

<span data-ttu-id="48840-107">Pour configurer des enrichissements HERE Technologies, les conditions préalables suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="48840-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="48840-108">Vous disposez d’un abonnement HERE Technologies actif.</span><span class="sxs-lookup"><span data-stu-id="48840-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="48840-109">Pour obtenir un abonnement, vous pouvez vous [inscrire ici](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [contacter HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directement.</span><span class="sxs-lookup"><span data-stu-id="48840-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="48840-110">En savoir plus sur l’enrichissement de la localisation de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="48840-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="48840-111">Une [connexion](connections.md) HERE est disponible *ou* vous disposez d’autorisations[administrateur](permissions.md#administrator) et de la clé API de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="48840-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="48840-112">Configurer l’enrichissement</span><span class="sxs-lookup"><span data-stu-id="48840-112">Configure the enrichment</span></span>

1. <span data-ttu-id="48840-113">Accédez à **Données** > **Enrichissement**.</span><span class="sxs-lookup"><span data-stu-id="48840-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="48840-114">Sélectionnez **Enrichir mes données** sur la vignette de HERE Technologies et sélectionnez **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="48840-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48840-115">![Vignette de HERE Technologies](media/HERE-tile.png "Vignette de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="48840-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="48840-116">Sélectionnez une [connexion](connections.md) dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="48840-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="48840-117">Contactez un administrateur si aucune connexion n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="48840-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="48840-118">Si vous êtes un administrateur, vous pouvez créer une connexion en sélectionnant **Ajouter une connexion**.</span><span class="sxs-lookup"><span data-stu-id="48840-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="48840-119">Choisissez **HERE Technologies** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="48840-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="48840-120">Sélectionnez **Se connecter à HERE Technologies** pour confirmer la sélection.</span><span class="sxs-lookup"><span data-stu-id="48840-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="48840-121">Sélectionnez **Suivant** et choisissez le **Jeu de données client** que vous souhaitez enrichir avec les données d’emplacement de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="48840-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="48840-122">Vous pouvez sélectionner l’entité **Client** pour enrichir tous vos profils clients ou sélectionner une entité segment pour enrichir uniquement les profils clients contenus dans ce segment.</span><span class="sxs-lookup"><span data-stu-id="48840-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Capture d’écran lors du choix du jeu de données client.":::

1. <span data-ttu-id="48840-124">Choisissez si vous souhaitez mapper les champs à l’adresse principale et/ou secondaire.</span><span class="sxs-lookup"><span data-stu-id="48840-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="48840-125">Vous pouvez spécifier un mappage de champs pour les deux adresses et enrichir les profils pour les deux adresses séparément.</span><span class="sxs-lookup"><span data-stu-id="48840-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="48840-126">Par exemple, s’il y a une adresse personnelle et professionnelle.</span><span class="sxs-lookup"><span data-stu-id="48840-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="48840-127">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="48840-127">Select **Next**.</span></span>

1. <span data-ttu-id="48840-128">Définissez quels champs de vos profils unifiés doivent être utilisés pour rechercher les données de localisation correspondantes de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="48840-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="48840-129">Les champs **Rue 1** et **Code postal** sont obligatoires pour l’adresse principale et/ou secondaire sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="48840-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="48840-130">Pour une plus grande précision de la correspondance, des champs supplémentaires peuvent être ajoutés.</span><span class="sxs-lookup"><span data-stu-id="48840-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48840-131">![Page de configuration de l’enrichissement de HERE Technologies](media/enrichment-HERE-configuration.png "Page de configuration de l’enrichissement de HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="48840-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="48840-132">Sélectionnez **Suivant** pour terminer le mappage de champs.</span><span class="sxs-lookup"><span data-stu-id="48840-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="48840-133">Fournissez un nom pour l’enrichissement.</span><span class="sxs-lookup"><span data-stu-id="48840-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="48840-134">Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.</span><span class="sxs-lookup"><span data-stu-id="48840-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="48840-135">Configurer la connexion pour HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="48840-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="48840-136">Vous devez être un administrateur pour configurer les connexions.</span><span class="sxs-lookup"><span data-stu-id="48840-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="48840-137">Sélectionnez **Ajouter une connexion** lors de la configuration d’un enrichissement *ou* accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** sur la vignette de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="48840-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="48840-138">Entrez un nom pour la connexion dans la zone **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="48840-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="48840-139">Fournissez une clé API HERE Technologies valide.</span><span class="sxs-lookup"><span data-stu-id="48840-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="48840-140">Vérifiez et donnez votre consentement pour **Confidentialité et conformité des données** en sélectionnant **J’accepte**.</span><span class="sxs-lookup"><span data-stu-id="48840-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="48840-141">Sélectionnez **Vérifier** pour valider la configuration.</span><span class="sxs-lookup"><span data-stu-id="48840-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="48840-142">Une fois la vérification terminée, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="48840-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48840-143">![Page de configuration de la connexion de HERE technologies](media/enrichment-HERE-connection.png "Page de configuration de la connexion de HERE technologies")</span><span class="sxs-lookup"><span data-stu-id="48840-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="48840-144">Résultats d’enrichissement</span><span class="sxs-lookup"><span data-stu-id="48840-144">Enrichment results</span></span>

<span data-ttu-id="48840-145">Pour démarrer le processus d’enrichissement, sélectionnez **Exécuter** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="48840-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="48840-146">Vous pouvez également laisser le système exécuter l’enrichissement automatiquement dans le cadre d’une [actualisation programmée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="48840-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="48840-147">Le temps de traitement dépendra de la taille de vos données client et des temps de réponse de l’API de HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="48840-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="48840-148">Une fois le processus d’enrichissement terminé, vous pouvez consulter les données des profils clients nouvellement enrichis sous **Mes enrichissements**.</span><span class="sxs-lookup"><span data-stu-id="48840-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="48840-149">De plus, vous trouverez l’heure de la dernière mise à jour et le nombre de profils enrichis.</span><span class="sxs-lookup"><span data-stu-id="48840-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="48840-150">Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.</span><span class="sxs-lookup"><span data-stu-id="48840-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="48840-151">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="48840-151">Next steps</span></span>

<span data-ttu-id="48840-152">Exploitez vos données client enrichies.</span><span class="sxs-lookup"><span data-stu-id="48840-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="48840-153">Créez des [segments](segments.md) et des [mesures](measures.md) et [exportez les données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.</span><span class="sxs-lookup"><span data-stu-id="48840-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="48840-154">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="48840-154">Data privacy and compliance</span></span>

<span data-ttu-id="48840-155">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers HERE Technologies, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="48840-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="48840-156">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que HERE Technologies respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="48840-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="48840-157">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="48840-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="48840-158">Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour ne plus utiliser cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="48840-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
