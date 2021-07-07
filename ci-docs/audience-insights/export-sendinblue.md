---
title: Exporter les données Customer Insights vers Sendinblue
description: Apprenez à configurer la connexion et à exporter vers Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314607"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="be440-103">Exporter des segments vers Sendinblue (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="be440-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="be440-104">Exportez des segments de profils clients unifiés pour générer des campagnes, fournir le marketing par e-mail et utiliser des groupes de clients spécifiques avec Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="be440-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="be440-105">Conditions préalables à une connexion</span><span class="sxs-lookup"><span data-stu-id="be440-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="be440-106">Vous disposez d’un [compte Sendinblue](https://www.sendinblue.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="be440-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="be440-107">Il y a des listes existantes dans Sendinblue et les ID correspondants.</span><span class="sxs-lookup"><span data-stu-id="be440-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="be440-108">Vous avez [configuré des segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="be440-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="be440-109">Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="be440-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="be440-110">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="be440-110">Known limitations</span></span>

- <span data-ttu-id="be440-111">Jusqu’à 1 million de profils par exportation vers Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="be440-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="be440-112">L’exportation vers Sendinblue est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="be440-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="be440-113">L’exportation de segments avec un total de 1 million de profils peut prendre jusqu’à 90 minutes.</span><span class="sxs-lookup"><span data-stu-id="be440-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="be440-114">Le nombre de profils que vous pouvez exporter vers Sendinblue dépend de votre contrat avec Sendinblue et est limité à ce qui est spécifié dans ce contrat.</span><span class="sxs-lookup"><span data-stu-id="be440-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="be440-115">Configurer la connexion à Sendinblue</span><span class="sxs-lookup"><span data-stu-id="be440-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="be440-116">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="be440-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="be440-117">Sélectionnez **Ajouter une connexion** et choisissez **Sendinblue** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="be440-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="be440-118">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="be440-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="be440-119">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="be440-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="be440-120">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="be440-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="be440-121">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="be440-121">Choose who can use this connection.</span></span> <span data-ttu-id="be440-122">Par défaut, il s'agit uniquement des administrateurs.</span><span class="sxs-lookup"><span data-stu-id="be440-122">By default it's only administrators.</span></span> <span data-ttu-id="be440-123">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="be440-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="be440-124">Entrez votre **[Clé API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="be440-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="be440-125">Sélectionnez **J’accepte** pour confirmer la **Confidentialité et conformité des données** et sélectionnez **Connecter** pour initialiser la connexion à Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="be440-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="be440-126">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="be440-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="be440-127">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="be440-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="be440-128">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="be440-128">Configure an export</span></span>

<span data-ttu-id="be440-129">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="be440-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="be440-130">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="be440-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="be440-131">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="be440-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="be440-132">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="be440-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="be440-133">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="be440-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="be440-134">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="be440-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="be440-135">Entrez votre **ID de liste Sendinblue**</span><span class="sxs-lookup"><span data-stu-id="be440-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="be440-136">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="be440-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="be440-137">Vous pouvez éventuellement exporter le **prénom**, le **nom** et le **téléphone** pour créer des e-mails plus personnalisés.</span><span class="sxs-lookup"><span data-stu-id="be440-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="be440-138">Sélectionnez **Ajouter un attribut** pour mapper ces champs.</span><span class="sxs-lookup"><span data-stu-id="be440-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="be440-139">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="be440-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="be440-140">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="be440-140">Select **Save**.</span></span>

<span data-ttu-id="be440-141">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="be440-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="be440-142">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="be440-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="be440-143">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="be440-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="be440-144">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="be440-144">Data privacy and compliance</span></span>

<span data-ttu-id="be440-145">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données à Sendinblue, vous autorisez le transfert de données en dehors de la limite de conformité pour Dynamics 365 Customer Insights, y compris les données potentiellement sensibles telles que les données personnelles.</span><span class="sxs-lookup"><span data-stu-id="be440-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="be440-146">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Sendinblue respecte vos éventuelles obligations de confidentialité ou de sécurité.</span><span class="sxs-lookup"><span data-stu-id="be440-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="be440-147">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="be440-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="be440-148">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="be440-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
