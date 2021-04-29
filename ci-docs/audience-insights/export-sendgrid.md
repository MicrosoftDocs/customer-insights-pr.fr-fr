---
title: Exporter des données Customer Insights vers SendGrid
description: Apprenez à configurer la connexion et à exporter vers SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759762"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="2ac19-103">Exporter des segments vers SendGrid (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="2ac19-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="2ac19-104">Exportez des segments de profils clients unifiés vers les listes de contacts SendGrid et utilisez-les pour les campagnes marketing et par e-mail dans SendGrid.</span><span class="sxs-lookup"><span data-stu-id="2ac19-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="2ac19-105">Conditions préalables à une connexion</span><span class="sxs-lookup"><span data-stu-id="2ac19-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="2ac19-106">Vous disposez d’un [compte SendGrid](https://sendgrid.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="2ac19-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2ac19-107">Il existe des listes de contacts dans SendGrid et les ID correspondants.</span><span class="sxs-lookup"><span data-stu-id="2ac19-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="2ac19-108">Pour plus d’informations, voir [SendGrid – Gérer les contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="2ac19-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="2ac19-109">Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="2ac19-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="2ac19-110">Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="2ac19-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2ac19-111">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="2ac19-111">Known limitations</span></span>

- <span data-ttu-id="2ac19-112">Jusqu’à 100 000 profils au total vers SendGrid.</span><span class="sxs-lookup"><span data-stu-id="2ac19-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="2ac19-113">L’exportation vers SendGrid est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="2ac19-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="2ac19-114">L’exportation de jusqu’à 100 000 profils vers SendGrid peut prendre jusqu’à quelques heures.</span><span class="sxs-lookup"><span data-stu-id="2ac19-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="2ac19-115">Le nombre de profils que vous pouvez exporter vers SendGrid dépend et est limité par votre contrat avec SendGrid.</span><span class="sxs-lookup"><span data-stu-id="2ac19-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="2ac19-116">Configurer la connexion à SendGrid</span><span class="sxs-lookup"><span data-stu-id="2ac19-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="2ac19-117">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="2ac19-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2ac19-118">Sélectionnez **Ajouter une connexion** et choisissez **SendGrid** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="2ac19-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="2ac19-119">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="2ac19-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2ac19-120">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="2ac19-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2ac19-121">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="2ac19-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2ac19-122">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="2ac19-122">Choose who can use this connection.</span></span> <span data-ttu-id="2ac19-123">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="2ac19-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2ac19-124">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2ac19-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2ac19-125">Entrez votre **Clé API SendGrid** [Clé API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="2ac19-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="2ac19-126">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="2ac19-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2ac19-127">Sélectionnez **Connecter** pour initialiser la connexion à SendGrid.</span><span class="sxs-lookup"><span data-stu-id="2ac19-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="2ac19-128">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2ac19-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2ac19-129">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="2ac19-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2ac19-130">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="2ac19-130">Configure an export</span></span>

<span data-ttu-id="2ac19-131">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="2ac19-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2ac19-132">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2ac19-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2ac19-133">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="2ac19-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2ac19-134">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="2ac19-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2ac19-135">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section SendGrid.</span><span class="sxs-lookup"><span data-stu-id="2ac19-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="2ac19-136">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="2ac19-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2ac19-137">Entrez votre **[ID de liste SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="2ac19-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="2ac19-138">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="2ac19-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2ac19-139">Répétez les mêmes étapes pour les autres champs facultatifs tels que **Prénom**, **Nom**, **Pays/Région**, **État**, **Ville** et **Code postal**.</span><span class="sxs-lookup"><span data-stu-id="2ac19-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="2ac19-140">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="2ac19-140">Select the segments you want to export.</span></span> <span data-ttu-id="2ac19-141">Nous **recommandons vivement de ne pas exporter plus de 100 000 profils clients au total** vers SendGrid.</span><span class="sxs-lookup"><span data-stu-id="2ac19-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="2ac19-142">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2ac19-142">Select **Save**.</span></span>

<span data-ttu-id="2ac19-143">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="2ac19-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2ac19-144">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2ac19-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2ac19-145">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2ac19-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2ac19-146">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="2ac19-146">Data privacy and compliance</span></span>

<span data-ttu-id="2ac19-147">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers SendGrid, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="2ac19-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2ac19-148">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que SendGrid respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="2ac19-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="2ac19-149">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2ac19-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2ac19-150">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="2ac19-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]