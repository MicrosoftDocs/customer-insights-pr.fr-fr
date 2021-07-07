---
title: Enrichissement avec l’enrichissement tiers d’Experian
description: Informations générales sur l’enrichissement tiers d’Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309817"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="52e53-103">Enrichir les profils client avec les données démographiques de Experian (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="52e53-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="52e53-104">Experian est un leader mondial des services de marketing et de reporting relatifs aux crédits accordés aux consommateurs et aux entreprises.</span><span class="sxs-lookup"><span data-stu-id="52e53-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="52e53-105">Les services d’enrichissement de données d’Experian vous aident à mieux comprendre vos clients en enrichissant vos profils client avec des données démographiques telles que la taille du foyer, les revenus, et plus encore.</span><span class="sxs-lookup"><span data-stu-id="52e53-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="52e53-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="52e53-106">Prerequisites</span></span>

<span data-ttu-id="52e53-107">Pour configurer Experian, les conditions préalables suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="52e53-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="52e53-108">Vous disposez d’un abonnement Experian actif.</span><span class="sxs-lookup"><span data-stu-id="52e53-108">You have an active Experian subscription.</span></span> <span data-ttu-id="52e53-109">Pour souscrire un abonnement, [contactez Experian](https://www.experian.com/marketing-services/contact) directement.</span><span class="sxs-lookup"><span data-stu-id="52e53-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="52e53-110">[En savoir plus sur l’enrichissement de données d’Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="52e53-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="52e53-111">Une connexion Experian a déjà été configurée par un administrateur *ou* vous disposez d’autorisations [administrateur](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="52e53-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="52e53-112">Vous avez également besoin de l’ID utilisateur, de l’ID de partie et du numéro de modèle de votre compte de transport sécuritsé (ST) compatible SSH qu’Experian a créé pour vous.</span><span class="sxs-lookup"><span data-stu-id="52e53-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="52e53-113">Pays/régions pris en charge</span><span class="sxs-lookup"><span data-stu-id="52e53-113">Supported countries/regions</span></span>

<span data-ttu-id="52e53-114">Nous prenons actuellement en charge l’enrichissement des profils client aux États-Unis uniquement.</span><span class="sxs-lookup"><span data-stu-id="52e53-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="52e53-115">Configurer l’enrichissement</span><span class="sxs-lookup"><span data-stu-id="52e53-115">Configure the enrichment</span></span>

1. <span data-ttu-id="52e53-116">Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.</span><span class="sxs-lookup"><span data-stu-id="52e53-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="52e53-117">Sélectionnez **Enrichir mes données** dans la vignette Experian.</span><span class="sxs-lookup"><span data-stu-id="52e53-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="52e53-118">![Vignette Experian](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="52e53-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="52e53-119">Sélectionnez une [connexion](connections.md) dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="52e53-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="52e53-120">Contactez un administrateur si aucune connexion n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="52e53-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="52e53-121">Si vous êtes un administrateur, vous pouvez créer une connexion en sélectionnant **Ajouter une connexion** et en choisissant Experian dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="52e53-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="52e53-122">Sélectionnez **Se connecter à Experian** pour confirmer la sélection de la connexion.</span><span class="sxs-lookup"><span data-stu-id="52e53-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="52e53-123">Sélectionnez **Suivant** et choisissez le **Jeu de données client** que vous souhaitez enrichir avec les données démographiques d’Experian.</span><span class="sxs-lookup"><span data-stu-id="52e53-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="52e53-124">Vous pouvez sélectionner l’entité **Client** pour enrichir tous vos profils clients ou sélectionner une entité segment pour enrichir uniquement les profils clients contenus dans ce segment.</span><span class="sxs-lookup"><span data-stu-id="52e53-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Capture d’écran lors du choix du jeu de données client.":::

1. <span data-ttu-id="52e53-126">Sélectionnez **Suivant** et définissez le type de champs de vos profils unifiés à utiliser pour rechercher les données démographiques correspondantes d’Experian.</span><span class="sxs-lookup"><span data-stu-id="52e53-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="52e53-127">Au moins un des champs **Nom et adresse**, **Téléphone** ou **E-mail** est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="52e53-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="52e53-128">Pour une plus grande précision de la correspondance, vous pouvez ajouter jusqu’à deux autres champs.</span><span class="sxs-lookup"><span data-stu-id="52e53-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="52e53-129">Cette sélection affectera les champs de mappage auxquels vous avez accès dans l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="52e53-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="52e53-130">Si vous envoyez plus d’attributs d’identificateur de clé à Experian, un taux de correspondance plus élevé sera probablement généré.</span><span class="sxs-lookup"><span data-stu-id="52e53-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="52e53-131">Sélectionnez **Suivant** pour démarrer le mappage de champs.</span><span class="sxs-lookup"><span data-stu-id="52e53-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="52e53-132">Définissez les champs de vos profils unifiés à utiliser pour rechercher les données démographiques correspondantes d’Experian.</span><span class="sxs-lookup"><span data-stu-id="52e53-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="52e53-133">Les champs obligatoires sont marqués.</span><span class="sxs-lookup"><span data-stu-id="52e53-133">Required fields are marked.</span></span>

1. <span data-ttu-id="52e53-134">Fournissez un nom pour l’enrichissement et un nom pour l’entité de sortie.</span><span class="sxs-lookup"><span data-stu-id="52e53-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="52e53-135">Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.</span><span class="sxs-lookup"><span data-stu-id="52e53-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="52e53-136">Configurer la connexion pour Experian</span><span class="sxs-lookup"><span data-stu-id="52e53-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="52e53-137">Vous devez être un administrateur pour configurer les connexions.</span><span class="sxs-lookup"><span data-stu-id="52e53-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="52e53-138">Sélectionnez **Ajouter une connexion** lors de la configuration d’un enrichissement *ou* accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** dans la vignette Experian.</span><span class="sxs-lookup"><span data-stu-id="52e53-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="52e53-139">Cliquez sur **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="52e53-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="52e53-140">Entrez un nom pour la connexion dans la zone **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="52e53-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="52e53-141">Saisissez un ID utilisateur, un ID de partie et un numéro de modèle valides pour votre compte de transport sécurisé Experian.</span><span class="sxs-lookup"><span data-stu-id="52e53-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="52e53-142">Vérifiez et donnez votre consentement pour **Confidentialité et conformité des données** en sélectionnant **J’accepte**.</span><span class="sxs-lookup"><span data-stu-id="52e53-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="52e53-143">Sélectionnez **Vérifier** pour valider la configuration.</span><span class="sxs-lookup"><span data-stu-id="52e53-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="52e53-144">Une fois la vérification terminée, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="52e53-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Volet de configuration de la connexion Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="52e53-146">Résultats d’enrichissement</span><span class="sxs-lookup"><span data-stu-id="52e53-146">Enrichment results</span></span>

<span data-ttu-id="52e53-147">Pour démarrer le processus d’enrichissement, sélectionnez **Exécuter** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="52e53-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="52e53-148">Vous pouvez également laisser le système exécuter l’enrichissement automatiquement dans le cadre d’une [actualisation programmée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="52e53-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="52e53-149">Le temps de traitement dépendra de la taille des données de vos clients et des processus d’enrichissement configurés pour votre compte par Experian.</span><span class="sxs-lookup"><span data-stu-id="52e53-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="52e53-150">Une fois le processus d’enrichissement terminé, vous pouvez consulter les données des profils clients nouvellement enrichis sous **Mes enrichissements**.</span><span class="sxs-lookup"><span data-stu-id="52e53-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="52e53-151">De plus, vous trouverez l’heure de la dernière mise à jour et le nombre de profils enrichis.</span><span class="sxs-lookup"><span data-stu-id="52e53-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="52e53-152">Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.</span><span class="sxs-lookup"><span data-stu-id="52e53-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="52e53-153">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="52e53-153">Next steps</span></span>

<span data-ttu-id="52e53-154">Exploitez vos données client enrichies.</span><span class="sxs-lookup"><span data-stu-id="52e53-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="52e53-155">Créez des [segments](segments.md) et des [mesures](measures.md) et [exportez les données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.</span><span class="sxs-lookup"><span data-stu-id="52e53-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="52e53-156">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="52e53-156">Data privacy and compliance</span></span>

<span data-ttu-id="52e53-157">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données à Experian, vous autorisez le transfert de données en dehors de la limite de conformité pour Dynamics 365 Customer Insights, y compris les données potentiellement sensibles telles que les données personnelles.</span><span class="sxs-lookup"><span data-stu-id="52e53-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="52e53-158">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer qu’Experian respecte vos éventuelles obligations de confidentialité ou de sécurité.</span><span class="sxs-lookup"><span data-stu-id="52e53-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="52e53-159">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="52e53-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="52e53-160">Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour ne plus utiliser cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="52e53-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
