---
title: Exporter des données Customer Insights vers Omnisend
description: Apprenez à configurer la connexion et à exporter vers Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124484"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="948bf-103">Exporter des segments vers Omnisend (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="948bf-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="948bf-104">Exportez des segments de profils client unifiés vers Omnisend et utilisez-les pour les activités marketing.</span><span class="sxs-lookup"><span data-stu-id="948bf-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="948bf-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="948bf-105">Prerequisites</span></span>

-   <span data-ttu-id="948bf-106">Vous disposez d’un [compte Omnisend](https://www.omnisend.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="948bf-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="948bf-107">Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="948bf-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="948bf-108">Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="948bf-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="948bf-109">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="948bf-109">Known limitations</span></span>

- <span data-ttu-id="948bf-110">Vous pouvez exporter jusqu'à 1 million de profils par exportation vers Omnisend et cela peut prendre jusqu'à 4 heures.</span><span class="sxs-lookup"><span data-stu-id="948bf-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="948bf-111">L’exportation vers Omnisend est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="948bf-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="948bf-112">Le nombre de profils que vous pouvez exporter vers Omnisend dépend de votre contrat avec Omnisend.</span><span class="sxs-lookup"><span data-stu-id="948bf-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="948bf-113">Configurer la connexion à Omnisend</span><span class="sxs-lookup"><span data-stu-id="948bf-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="948bf-114">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="948bf-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="948bf-115">Sélectionnez **Ajouter une connexion** et choisissez **Omnisend** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="948bf-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="948bf-116">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="948bf-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="948bf-117">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="948bf-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="948bf-118">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="948bf-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="948bf-119">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="948bf-119">Choose who can use this connection.</span></span> <span data-ttu-id="948bf-120">Par défaut, il s'agit uniquement des administrateurs.</span><span class="sxs-lookup"><span data-stu-id="948bf-120">By default it's only administrators.</span></span> <span data-ttu-id="948bf-121">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="948bf-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="948bf-122">Entrez votre [clé API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="948bf-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="948bf-123">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="948bf-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="948bf-124">Sélectionnez **Connecter** pour initialiser la connexion à Omnisend.</span><span class="sxs-lookup"><span data-stu-id="948bf-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="948bf-125">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="948bf-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="948bf-126">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="948bf-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="948bf-127">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="948bf-127">Configure an export</span></span>

<span data-ttu-id="948bf-128">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="948bf-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="948bf-129">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="948bf-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="948bf-130">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="948bf-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="948bf-131">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="948bf-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="948bf-132">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Omnisend.</span><span class="sxs-lookup"><span data-stu-id="948bf-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="948bf-133">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="948bf-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="948bf-134">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="948bf-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="948bf-135">Il est obligatoire d’exporter des segments vers Omnisend.</span><span class="sxs-lookup"><span data-stu-id="948bf-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="948bf-136">Vous pouvez éventuellement exporter le Prénom, le Nom, l'Adresse, le/la Pays/région, le Département, la Ville et le Code postal pour créer des e-mails plus personnalisés.</span><span class="sxs-lookup"><span data-stu-id="948bf-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="948bf-137">Sélectionnez **Ajouter un attribut** pour mapper ces champs.</span><span class="sxs-lookup"><span data-stu-id="948bf-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="948bf-138">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="948bf-138">Select **Save**.</span></span>

<span data-ttu-id="948bf-139">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="948bf-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="948bf-140">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="948bf-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="948bf-141">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="948bf-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="948bf-142">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="948bf-142">Data privacy and compliance</span></span>

<span data-ttu-id="948bf-143">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Ommisend, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="948bf-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="948bf-144">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer qu'Ommisend respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="948bf-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="948bf-145">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="948bf-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="948bf-146">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="948bf-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
