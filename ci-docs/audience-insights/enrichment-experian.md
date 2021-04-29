---
title: Enrichissement avec l’enrichissement tiers de Experian
description: Informations générales sur l’enrichissement tiers de Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896370"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="29183-103">Enrichir les profils des clients avec les données démographiques d’Experian (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="29183-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="29183-104">Experian est un leader mondial en marketing et reporting dans le domaine du crédit aux consommateurs et aux entreprises.</span><span class="sxs-lookup"><span data-stu-id="29183-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="29183-105">Avec les Services d’enrichissement de données d’Experian, vous pouvez approfondir votre compréhension de vos clients en enrichissant les profils clients avec des données démographiques telles que la taille du ménage, le revenu, etc.</span><span class="sxs-lookup"><span data-stu-id="29183-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="29183-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="29183-106">Prerequisites</span></span>

<span data-ttu-id="29183-107">Pour configurer Experian, les conditions préalables suivantes doivent être respectées :</span><span class="sxs-lookup"><span data-stu-id="29183-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="29183-108">Vous avez un abonnement Experian actif.</span><span class="sxs-lookup"><span data-stu-id="29183-108">You have an active Experian subscription.</span></span> <span data-ttu-id="29183-109">Pour obtenir un abonnement, [contactez Experian](https://www.experian.com/marketing-services/contact) directement.</span><span class="sxs-lookup"><span data-stu-id="29183-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="29183-110">[Plus d’informations sur l’enrichissement des données Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)</span><span class="sxs-lookup"><span data-stu-id="29183-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="29183-111">Une connexion Experian a déjà été configurée par un administrateur *ou* vous disposez d’autorisations [administrateur](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="29183-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="29183-112">Vous avez également besoin de l’ID d’utilisateur, de l’ID de partie et du numéro de modèle de votre compte Secure Transport (ST) compatible SSH qu’Experian a créé pour vous.</span><span class="sxs-lookup"><span data-stu-id="29183-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="29183-113">Configurer l’enrichissement</span><span class="sxs-lookup"><span data-stu-id="29183-113">Configure the enrichment</span></span>

1. <span data-ttu-id="29183-114">Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.</span><span class="sxs-lookup"><span data-stu-id="29183-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="29183-115">Sélectionnez **Enrichir mes données** sur la vignette Experian.</span><span class="sxs-lookup"><span data-stu-id="29183-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="29183-116">![Vignette Experian](media/experian-tile.png "Vignette Experian")</span><span class="sxs-lookup"><span data-stu-id="29183-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="29183-117">Sélectionnez une [connexion](connections.md) dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="29183-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="29183-118">Contactez un administrateur si aucune connexion n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="29183-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="29183-119">Si vous êtes un administrateur, vous pouvez créer une connexion en sélectionnant **Ajouter une connexion** et en choisissant Experian dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="29183-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="29183-120">Sélectionnez **Se connecter à Experian** pour confirmer la sélection de la connexion.</span><span class="sxs-lookup"><span data-stu-id="29183-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="29183-121">Sélectionnez **Suivant** et choisissez le **Jeu de données client** que vous souhaitez enrichir avec les données démographiques d’Experian.</span><span class="sxs-lookup"><span data-stu-id="29183-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="29183-122">Vous pouvez sélectionner l’entité **Client** pour enrichir tous vos profils clients ou sélectionner une entité segment pour enrichir uniquement les profils clients contenus dans ce segment.</span><span class="sxs-lookup"><span data-stu-id="29183-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Capture d’écran lors du choix du jeu de données client.":::

1. <span data-ttu-id="29183-124">Sélectionnez **Suivant** et définissez le type de champ de vos profils unifiés à utiliser pour rechercher les données démographiques correspondantes d’Experian.</span><span class="sxs-lookup"><span data-stu-id="29183-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="29183-125">Au moins un des champs **Nom et adresse**, **Téléphone** ou **E-mail** est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="29183-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="29183-126">Pour une plus grande précision de la correspondance, vous pouvez ajouter jusqu’à deux autres champs.</span><span class="sxs-lookup"><span data-stu-id="29183-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="29183-127">Cette sélection affectera les champs de mappage auxquels vous avez accès dans l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="29183-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="29183-128">Plus vous envoyez d’attributs d’identifiant de clé à Experian, plus le taux de correspondance a de chances d’être élevé.</span><span class="sxs-lookup"><span data-stu-id="29183-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="29183-129">Sélectionnez **Suivant** pour démarrer le mappage de champs.</span><span class="sxs-lookup"><span data-stu-id="29183-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="29183-130">Définissez les champs de vos profils unifiés à utiliser pour rechercher les données démographiques correspondantes d’Experian.</span><span class="sxs-lookup"><span data-stu-id="29183-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="29183-131">Les champs obligatoires sont marqués.</span><span class="sxs-lookup"><span data-stu-id="29183-131">Required fields are marked.</span></span>

1. <span data-ttu-id="29183-132">Fournissez un nom pour l’enrichissement et un nom pour l’entité de sortie.</span><span class="sxs-lookup"><span data-stu-id="29183-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="29183-133">Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.</span><span class="sxs-lookup"><span data-stu-id="29183-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="29183-134">Configurer la connexion pour Experian</span><span class="sxs-lookup"><span data-stu-id="29183-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="29183-135">Vous devez être un administrateur pour configurer les connexions.</span><span class="sxs-lookup"><span data-stu-id="29183-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="29183-136">Sélectionnez **Ajouter une connexion** lors de la configuration d’un enrichissement *ou* accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** sur la vignette d’Experian.</span><span class="sxs-lookup"><span data-stu-id="29183-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="29183-137">Cliquez sur **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="29183-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="29183-138">Entrez un nom pour la connexion dans la zone **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="29183-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="29183-139">Entrez un ID d’utilisateur, un ID de partie et un numéro de modèle valides pour votre compte Secure Transport d’Experian.</span><span class="sxs-lookup"><span data-stu-id="29183-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="29183-140">Vérifiez et donnez votre consentement pour la **Confidentialité et conformité des données** en cochant la case **J’accepte**</span><span class="sxs-lookup"><span data-stu-id="29183-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="29183-141">Sélectionnez **Vérifier** pour valider la configuration.</span><span class="sxs-lookup"><span data-stu-id="29183-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="29183-142">Une fois la vérification terminée, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="29183-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Volet de configuration de la connexion d’Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="29183-144">Résultats d’enrichissement</span><span class="sxs-lookup"><span data-stu-id="29183-144">Enrichment results</span></span>

<span data-ttu-id="29183-145">Pour démarrer le processus d’enrichissement, sélectionnez **Exécuter** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="29183-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="29183-146">Vous pouvez également laisser le système exécuter l’enrichissement automatiquement dans le cadre d’une [actualisation programmée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="29183-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="29183-147">Le temps de traitement dépendra de la taille de vos données clients et des processus d’enrichissement mis en place pour votre compte par Experian.</span><span class="sxs-lookup"><span data-stu-id="29183-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="29183-148">Une fois le processus d’enrichissement terminé, vous pouvez consulter les données des profils clients nouvellement enrichis sous **Mes enrichissements**.</span><span class="sxs-lookup"><span data-stu-id="29183-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="29183-149">De plus, vous trouverez l’heure de la dernière mise à jour et le nombre de profils enrichis.</span><span class="sxs-lookup"><span data-stu-id="29183-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="29183-150">Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.</span><span class="sxs-lookup"><span data-stu-id="29183-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="29183-151">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="29183-151">Next steps</span></span>

<span data-ttu-id="29183-152">Exploitez vos données client enrichies.</span><span class="sxs-lookup"><span data-stu-id="29183-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="29183-153">Créez des [Segments](segments.md), des [Mesures](measures.md), voire [Exportez des données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.</span><span class="sxs-lookup"><span data-stu-id="29183-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="29183-154">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="29183-154">Data privacy and compliance</span></span>

<span data-ttu-id="29183-155">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Experian, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="29183-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="29183-156">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Experian respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="29183-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="29183-157">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="29183-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="29183-158">Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="29183-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
