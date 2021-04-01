---
title: Enrichissement avec l’enrichissement tiers de Experian
description: Informations générales sur l’enrichissement tiers de Experian.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597784"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="b3d29-103">Enrichir les profils des clients avec les données démographiques d’Experian (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="b3d29-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="b3d29-104">Experian est un leader mondial en marketing et reporting dans le domaine du crédit aux consommateurs et aux entreprises.</span><span class="sxs-lookup"><span data-stu-id="b3d29-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="b3d29-105">Avec les Services d’enrichissement de données d’Experian, vous pouvez approfondir votre compréhension de vos clients en enrichissant les profils clients avec des données démographiques telles que la taille du ménage, le revenu, etc.</span><span class="sxs-lookup"><span data-stu-id="b3d29-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b3d29-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="b3d29-106">Prerequisites</span></span>

<span data-ttu-id="b3d29-107">Pour configurer Experian, les conditions préalables suivantes doivent être respectées :</span><span class="sxs-lookup"><span data-stu-id="b3d29-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b3d29-108">Vous avez un abonnement Experian actif.</span><span class="sxs-lookup"><span data-stu-id="b3d29-108">You have an active Experian subscription.</span></span> <span data-ttu-id="b3d29-109">Pour obtenir un abonnement, [contactez Experian](https://www.experian.com/marketing-services/contact) directement.</span><span class="sxs-lookup"><span data-stu-id="b3d29-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="b3d29-110">[Plus d’informations sur l’enrichissement des données Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)</span><span class="sxs-lookup"><span data-stu-id="b3d29-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="b3d29-111">Vous disposez de l’ID utilisateur, de l’ID de partie et du numéro de modèle du compte Secure Transport (ST) compatible SSH créé pour vous par Experian.</span><span class="sxs-lookup"><span data-stu-id="b3d29-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="b3d29-112">Vous disposez d’autorisations [Administrateur](permissions.md#administrator) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="b3d29-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="b3d29-113">configuration</span><span class="sxs-lookup"><span data-stu-id="b3d29-113">Configuration</span></span>

1. <span data-ttu-id="b3d29-114">Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.</span><span class="sxs-lookup"><span data-stu-id="b3d29-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="b3d29-115">Sélectionnez **Enrichir mes données** sur la vignette Experian.</span><span class="sxs-lookup"><span data-stu-id="b3d29-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b3d29-116">![Vignette Experian](media/experian-tile.png "Vignette Experian")</span><span class="sxs-lookup"><span data-stu-id="b3d29-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="b3d29-117">Sélectionnez **Démarrer** et entrez l’ID utilisateur, l’ID de partie et le numéro de modèle de votre compte Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="b3d29-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="b3d29-118">Vérifiez et donnez votre consentement pour **Confidentialité et conformité des données** en cochant la case **J’accepte**.</span><span class="sxs-lookup"><span data-stu-id="b3d29-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="b3d29-119">Confirmez toutes les entrées en sélectionnant **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="b3d29-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="b3d29-120">Mapper vos champs</span><span class="sxs-lookup"><span data-stu-id="b3d29-120">Map your fields</span></span>

1.  <span data-ttu-id="b3d29-121">Sélectionnez **Ajouter des données** et choisissez le **Jeu de données client** que vous souhaitez enrichir avec les données démographiques d’Experian.</span><span class="sxs-lookup"><span data-stu-id="b3d29-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="b3d29-122">Vous pouvez sélectionner l’entité **Client** pour enrichir tous vos profils clients ou sélectionner une entité segment pour enrichir uniquement les profils clients contenus dans ce segment.</span><span class="sxs-lookup"><span data-stu-id="b3d29-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="b3d29-123">Sélectionnez vos identificateurs clés dans **Nom et adresse**, **Adresse e-mail** ou **Téléphone** à envoyer à Experian pour la résolution d’identité.</span><span class="sxs-lookup"><span data-stu-id="b3d29-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="b3d29-124">Plus vous envoyez d’attributs d’identifiant de clé à Experian, plus le taux de correspondance a de chances d’être élevé.</span><span class="sxs-lookup"><span data-stu-id="b3d29-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="b3d29-125">Sélectionnez **Suivant** et mappez les attributs correspondants provenant de votre entité client unifiée pour les champs d’identificateur de clé sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="b3d29-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="b3d29-126">Sélectionnez **Ajouter un attribut** pour mapper les attributs supplémentaires que vous souhaitez envoyer à Experian.</span><span class="sxs-lookup"><span data-stu-id="b3d29-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="b3d29-127">Sélectionnez **Enregistrer** pour terminer le mappage de champs.</span><span class="sxs-lookup"><span data-stu-id="b3d29-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b3d29-128">![Mappage de champ Experian](media/experian-field-mapping.png "Mappage de champ Experian")</span><span class="sxs-lookup"><span data-stu-id="b3d29-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="b3d29-129">Résultats d’enrichissement</span><span class="sxs-lookup"><span data-stu-id="b3d29-129">Enrichment results</span></span>

<span data-ttu-id="b3d29-130">Pour démarrer le processus d’enrichissement, sélectionnez **Exécuter** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="b3d29-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="b3d29-131">Vous pouvez également laisser le système exécuter l’enrichissement automatiquement dans le cadre d’une [actualisation programmée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b3d29-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b3d29-132">Le temps de traitement dépendra de la taille de vos données clients et des processus d’enrichissement mis en place pour votre compte par Experian.</span><span class="sxs-lookup"><span data-stu-id="b3d29-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="b3d29-133">Une fois le processus d’enrichissement terminé, vous pouvez consulter les données des profils clients nouvellement enrichis sous **Mes enrichissements**.</span><span class="sxs-lookup"><span data-stu-id="b3d29-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="b3d29-134">De plus, vous trouverez l’heure de la dernière mise à jour et le nombre de profils enrichis.</span><span class="sxs-lookup"><span data-stu-id="b3d29-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b3d29-135">Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.</span><span class="sxs-lookup"><span data-stu-id="b3d29-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b3d29-136">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="b3d29-136">Next steps</span></span>

<span data-ttu-id="b3d29-137">Exploitez vos données client enrichies.</span><span class="sxs-lookup"><span data-stu-id="b3d29-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b3d29-138">Créez des [Segments](segments.md), des [Mesures](measures.md), voire [Exportez des données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.</span><span class="sxs-lookup"><span data-stu-id="b3d29-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b3d29-139">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="b3d29-139">Data privacy and compliance</span></span>

<span data-ttu-id="b3d29-140">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Experian, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="b3d29-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b3d29-141">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Experian respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="b3d29-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b3d29-142">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b3d29-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b3d29-143">Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="b3d29-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]