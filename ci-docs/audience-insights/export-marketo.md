---
title: Exporter des données Customer Insights vers Marketo
description: Apprenez à configurer la connexion et à exporter vers Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759818"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="84a71-103">Exporter des segments vers Marketo (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="84a71-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="84a71-104">Exportez des segments de profils clients unifiés pour générer des campagnes, fournir des activités de marketing par e-mail et utiliser certains groupes de clients avec Marketo.</span><span class="sxs-lookup"><span data-stu-id="84a71-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="84a71-105">Conditions préalables à une connexion</span><span class="sxs-lookup"><span data-stu-id="84a71-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="84a71-106">Vous disposez d’un [compte Marketo](https://login.marketo.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="84a71-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="84a71-107">Il existe des listes dans Marketo et les ID correspondants.</span><span class="sxs-lookup"><span data-stu-id="84a71-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="84a71-108">Pour plus d’informations, consultez [Listes Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="84a71-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="84a71-109">Vous avez [configuré des segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="84a71-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="84a71-110">Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="84a71-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="84a71-111">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="84a71-111">Known limitations</span></span>

- <span data-ttu-id="84a71-112">Jusqu’à 1 million de profils par exportation vers Marketo.</span><span class="sxs-lookup"><span data-stu-id="84a71-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="84a71-113">L’exportation vers Marketo est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="84a71-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="84a71-114">L’exportation de segments avec un total de 1 million de profils peut prendre jusqu’à 3 heures.</span><span class="sxs-lookup"><span data-stu-id="84a71-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="84a71-115">Le nombre de profils que vous pouvez exporter vers Marketo dépend et est limité par votre contrat avec Marketo.</span><span class="sxs-lookup"><span data-stu-id="84a71-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="84a71-116">Configurer la connexion à Marketo</span><span class="sxs-lookup"><span data-stu-id="84a71-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="84a71-117">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="84a71-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="84a71-118">Sélectionnez **Ajouter une connexion** et choisissez **Marketo** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="84a71-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="84a71-119">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="84a71-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="84a71-120">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="84a71-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="84a71-121">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="84a71-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="84a71-122">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="84a71-122">Choose who can use this connection.</span></span> <span data-ttu-id="84a71-123">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="84a71-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="84a71-124">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="84a71-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="84a71-125">Entrez vos **[ID de client Marketo, secret client et nom d’hôte du point de terminaison REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="84a71-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="84a71-126">Sélectionnez **J’accepte** pour confirmer la **Confidentialité et conformité des données** et sélectionnez **Connecter** pour initialiser la connexion à Marketo.</span><span class="sxs-lookup"><span data-stu-id="84a71-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="84a71-127">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="84a71-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="84a71-128">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="84a71-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="84a71-129">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="84a71-129">Configure an export</span></span>

<span data-ttu-id="84a71-130">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="84a71-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="84a71-131">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="84a71-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="84a71-132">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="84a71-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="84a71-133">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="84a71-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="84a71-134">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Marketo.</span><span class="sxs-lookup"><span data-stu-id="84a71-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="84a71-135">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="84a71-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="84a71-136">Entrez votre **[ID de liste Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="84a71-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="84a71-137">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="84a71-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="84a71-138">Vous pouvez éventuellement exporter le **Prénom**, le **Nom**, la **Ville**, le **Département** et le/la **Pays/région** pour créer des e-mails plus personnalisés.</span><span class="sxs-lookup"><span data-stu-id="84a71-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="84a71-139">Sélectionnez **Ajouter un attribut** pour mapper ces champs.</span><span class="sxs-lookup"><span data-stu-id="84a71-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="84a71-140">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="84a71-140">Select the segments you want to export.</span></span> <span data-ttu-id="84a71-141">Vous pouvez exporter jusqu’à 1 million de profils clients au total vers Marketo.</span><span class="sxs-lookup"><span data-stu-id="84a71-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="84a71-142">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="84a71-142">Select **Save**.</span></span>

<span data-ttu-id="84a71-143">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="84a71-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="84a71-144">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="84a71-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="84a71-145">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="84a71-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="84a71-146">Dans Marketo, vous trouverez désormais vos segments sous [Listes Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="84a71-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="84a71-147">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="84a71-147">Data privacy and compliance</span></span>

<span data-ttu-id="84a71-148">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Marketo, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="84a71-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="84a71-149">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Marketo respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="84a71-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="84a71-150">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="84a71-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="84a71-151">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="84a71-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]