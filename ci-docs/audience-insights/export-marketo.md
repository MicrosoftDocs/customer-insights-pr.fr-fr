---
title: Exporter des données Customer Insights vers Marketo
description: Découvrez comment configurer la connexion à Marketo.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597968"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="dde26-103">Connecteur pour Marketo (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="dde26-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="dde26-104">Exportez des segments de profils clients unifiés pour générer des campagnes, fournir des activités de marketing par e-mail et utiliser certains groupes de clients avec Marketo.</span><span class="sxs-lookup"><span data-stu-id="dde26-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dde26-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="dde26-105">Prerequisites</span></span>

-   <span data-ttu-id="dde26-106">Vous disposez d’un [compte Marketo](https://login.marketo.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="dde26-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="dde26-107">Il existe des listes dans Marketo et les ID correspondants.</span><span class="sxs-lookup"><span data-stu-id="dde26-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="dde26-108">Pour plus d’informations, consultez [Listes Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="dde26-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="dde26-109">Vous avez [configuré des segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="dde26-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="dde26-110">Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="dde26-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="dde26-111">Se connecter à Marketo</span><span class="sxs-lookup"><span data-stu-id="dde26-111">Connect to Marketo</span></span>

1. <span data-ttu-id="dde26-112">Accédez à **Administration** > **Destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="dde26-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="dde26-113">Sous **Marketo**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="dde26-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="dde26-114">Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="dde26-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="dde26-115">Entrez vos **[ID de client Marketo, secret client et nom d’hôte du point de terminaison REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="dde26-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="dde26-116">Entrez votre **[ID de liste Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="dde26-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="dde26-117">Sélectionnez **J’accepte** pour confirmer la **Confidentialité et conformité des données** et sélectionnez **Connecter** pour initialiser la connexion à Marketo.</span><span class="sxs-lookup"><span data-stu-id="dde26-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="dde26-118">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dde26-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Capture d’écran d’exportation pour la connexion à Marketo":::

1. <span data-ttu-id="dde26-120">Sélectionnez **Suivant** pour configurer l’exportation.</span><span class="sxs-lookup"><span data-stu-id="dde26-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="dde26-121">Configurer le connecteur</span><span class="sxs-lookup"><span data-stu-id="dde26-121">Configure the connector</span></span>

1. <span data-ttu-id="dde26-122">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="dde26-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="dde26-123">Vous pouvez éventuellement exporter les champs **Prénom**, **Nom**, **Ville**, **Département** et **Pays/Région** comme champs supplémentaires pour créer des e-mails plus personnalisés.</span><span class="sxs-lookup"><span data-stu-id="dde26-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="dde26-124">Sélectionnez **Ajouter un attribut** pour mapper ces champs.</span><span class="sxs-lookup"><span data-stu-id="dde26-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="dde26-125">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="dde26-125">Select the segments you want to export.</span></span> <span data-ttu-id="dde26-126">Vous pouvez exporter jusqu’à 1 million de profils clients au total vers Marketo.</span><span class="sxs-lookup"><span data-stu-id="dde26-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Sélectionner les champs et les segments à exporter vers Marketo":::

1. <span data-ttu-id="dde26-128">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="dde26-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="dde26-129">Exporter les données</span><span class="sxs-lookup"><span data-stu-id="dde26-129">Export the data</span></span>

<span data-ttu-id="dde26-130">Vous pouvez [exporter les données à la demande](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="dde26-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="dde26-131">L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dde26-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dde26-132">Dans Marketo, vous trouverez désormais vos segments sous [Listes Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="dde26-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="dde26-133">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="dde26-133">Known limitations</span></span>

- <span data-ttu-id="dde26-134">Jusqu’à 1 million de profils par exportation vers Marketo.</span><span class="sxs-lookup"><span data-stu-id="dde26-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="dde26-135">L’exportation vers Marketo est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="dde26-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="dde26-136">L’exportation de segments avec un total de 1 million de profils peut prendre jusqu’à 3 heures.</span><span class="sxs-lookup"><span data-stu-id="dde26-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="dde26-137">Le nombre de profils que vous pouvez exporter vers Marketo dépend et est limité par votre contrat avec Marketo.</span><span class="sxs-lookup"><span data-stu-id="dde26-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dde26-138">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="dde26-138">Data privacy and compliance</span></span>

<span data-ttu-id="dde26-139">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Marketo, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="dde26-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dde26-140">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Marketo respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="dde26-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dde26-141">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dde26-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dde26-142">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="dde26-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]