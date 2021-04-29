---
title: Enrichissement des profils d’entreprise avec l’enrichissement tiers de Leadspace
description: Informations générales sur l’enrichissement tiers de Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895910"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="0621b-103">Enrichissement des profils d’entreprise avec Leadspace (aperçu)</span><span class="sxs-lookup"><span data-stu-id="0621b-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="0621b-104">Leadspace est une entreprise de science des données qui fournit une plateforme de données client B2B.</span><span class="sxs-lookup"><span data-stu-id="0621b-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="0621b-105">Elle permet aux clients ayant un profil client unifié pour les entreprises d’enrichir leurs données.</span><span class="sxs-lookup"><span data-stu-id="0621b-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="0621b-106">Les enrichissements comprennent d’autres attributs tels que la taille de la société, son emplacement, son secteur d’activité, et plus encore.</span><span class="sxs-lookup"><span data-stu-id="0621b-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0621b-107">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="0621b-107">Prerequisites</span></span>

<span data-ttu-id="0621b-108">Pour configurer Leadspace, les conditions préalables suivantes doivent être respectées :</span><span class="sxs-lookup"><span data-stu-id="0621b-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="0621b-109">Vous disposez d’une licence Leadspace active.</span><span class="sxs-lookup"><span data-stu-id="0621b-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="0621b-110">Vous avez des [profils clients unifiés](customer-profiles.md) pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="0621b-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="0621b-111">Une connexion Leadspace a déjà été configurée par un administrateur ou vous disposez d’autorisations [administrateur](permissions.md#administrator) et de la « clé perpétuelle » (appelée **Jeton Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="0621b-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="0621b-112">Contactez [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directement pour obtenir des détails sur leur produit.</span><span class="sxs-lookup"><span data-stu-id="0621b-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="0621b-113">Configurer l’enrichissement</span><span class="sxs-lookup"><span data-stu-id="0621b-113">Configure the enrichment</span></span>

1. <span data-ttu-id="0621b-114">Dans les informations sur l’audience, accédez à **Données** > **Enrichissement**.</span><span class="sxs-lookup"><span data-stu-id="0621b-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="0621b-115">Sélectionnez **Enrichir mes données** sur la vignette de Leadspace et sélectionnez **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="0621b-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Capture d’écran de la vignette de Leadspace.":::

1. <span data-ttu-id="0621b-117">Sélectionnez une [connexion](connections.md) dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="0621b-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="0621b-118">Contactez un administrateur si aucune connexion n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="0621b-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="0621b-119">Si vous êtes un administrateur, vous pouvez créer une connexion en sélectionnant **Ajouter une connexion** et en choisissant **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="0621b-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="0621b-120">Sélectionnez **Se connecter à Leadspace** pour confirmer la connexion.</span><span class="sxs-lookup"><span data-stu-id="0621b-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="0621b-121">Sélectionnez **Suivant** et choisissez le **Jeu de données client** que vous souhaitez enrichir avec les données d’entreprise de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="0621b-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="0621b-122">Vous pouvez sélectionner l’entité **Client** pour enrichir tous vos profils clients ou sélectionner une entité segment pour enrichir uniquement les profils clients contenus dans ce segment.</span><span class="sxs-lookup"><span data-stu-id="0621b-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Capture d’écran lors du choix du jeu de données client.":::

1. <span data-ttu-id="0621b-124">Sélectionnez **Suivant** et définissez les champs de vos profils unifiés qui sont utilisés pour rechercher les données d’entreprise correspondantes de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="0621b-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="0621b-125">Le champ **Nom de la société** est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="0621b-125">The **Name of company** field is required.</span></span> <span data-ttu-id="0621b-126">Pour une plus grande précision de la correspondance, jusqu’à deux autres champs, **Site web de la société** et **Emplacement de la société**, peuvent être ajoutés.</span><span class="sxs-lookup"><span data-stu-id="0621b-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Volet de mappage de champ de Leadspace.":::

1. <span data-ttu-id="0621b-128">Sélectionnez **Suivant** pour terminer le mappage de champs.</span><span class="sxs-lookup"><span data-stu-id="0621b-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="0621b-129">Fournissez un nom pour l’enrichissement et sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.</span><span class="sxs-lookup"><span data-stu-id="0621b-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="0621b-130">Configurer la connexion pour Leadspace</span><span class="sxs-lookup"><span data-stu-id="0621b-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="0621b-131">Vous devez être un administrateur pour configurer les connexions.</span><span class="sxs-lookup"><span data-stu-id="0621b-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="0621b-132">Sélectionnez **Ajouter une connexion** lors de la configuration d’un enrichissement *ou* accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** sur la vignette de Leadspace.</span><span class="sxs-lookup"><span data-stu-id="0621b-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="0621b-133">Sélectionnez **Démarrer**</span><span class="sxs-lookup"><span data-stu-id="0621b-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="0621b-134">Entrez un nom pour la connexion dans la zone **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="0621b-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="0621b-135">Fournissez un jeton Leadspace valide.</span><span class="sxs-lookup"><span data-stu-id="0621b-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="0621b-136">Vérifiez et donnez votre consentement pour la **Confidentialité et conformité des données** en cochant la case **J’accepte**</span><span class="sxs-lookup"><span data-stu-id="0621b-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="0621b-137">Sélectionnez **Vérifier** pour valider la configuration.</span><span class="sxs-lookup"><span data-stu-id="0621b-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="0621b-138">Une fois la vérification terminée, sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="0621b-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Page de configuration de la connexion de Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="0621b-140">Résultats d’enrichissement</span><span class="sxs-lookup"><span data-stu-id="0621b-140">Enrichment results</span></span>

<span data-ttu-id="0621b-141">Après avoir actualisé l’enrichissement, vous pouvez consulter les données d’entreprise nouvellement enrichies sous [Mes enrichissements](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="0621b-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="0621b-142">Vous pouvez trouver l’heure de la dernière mise à jour et le nombre de profils enrichis.</span><span class="sxs-lookup"><span data-stu-id="0621b-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="0621b-143">Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.</span><span class="sxs-lookup"><span data-stu-id="0621b-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="0621b-144">Pour plus d’informations, voir [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="0621b-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0621b-145">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="0621b-145">Next steps</span></span>

<span data-ttu-id="0621b-146">Exploitez vos données client enrichies.</span><span class="sxs-lookup"><span data-stu-id="0621b-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="0621b-147">Créez des [Segments](segments.md), des [Mesures](measures.md), voire [Exportez des données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.</span><span class="sxs-lookup"><span data-stu-id="0621b-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0621b-148">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="0621b-148">Data privacy and compliance</span></span>

<span data-ttu-id="0621b-149">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Leadspace, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="0621b-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0621b-150">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Leadspace respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="0621b-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0621b-151">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0621b-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0621b-152">Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="0621b-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
