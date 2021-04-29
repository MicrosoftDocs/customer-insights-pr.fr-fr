---
title: Connecteur LiveRamp
description: Apprenez à configurer la connexion et à exporter vers LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760324"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="a302f-103">Exporter des segments vers LiveRamp&reg; (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="a302f-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="a302f-104">Activez vos données dans LiveRamp pour vous connecter à plus de 500 plateformes dans les écosystèmes numériques, sociaux et télévisés.</span><span class="sxs-lookup"><span data-stu-id="a302f-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="a302f-105">Exploitez vos données dans LiveRamp pour cibler, supprimer et personnaliser des campagnes publicitaires.</span><span class="sxs-lookup"><span data-stu-id="a302f-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="a302f-106">Conditions préalables à une connexion</span><span class="sxs-lookup"><span data-stu-id="a302f-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="a302f-107">Vous avez besoin d’un abonnement LiveRamp pour utiliser ce connecteur.</span><span class="sxs-lookup"><span data-stu-id="a302f-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="a302f-108">Pour obtenir un abonnement, [contactez LiveRamp](https://liveramp.com/contact/) directement.</span><span class="sxs-lookup"><span data-stu-id="a302f-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="a302f-109">[En savoir plus sur LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="a302f-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="a302f-110">Configurer la connexion à LiveRamp</span><span class="sxs-lookup"><span data-stu-id="a302f-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="a302f-111">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="a302f-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a302f-112">Sélectionnez **Ajouter une connexion** et choisissez **LiveRamp** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="a302f-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="a302f-113">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="a302f-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a302f-114">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="a302f-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a302f-115">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="a302f-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a302f-116">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="a302f-116">Choose who can use this connection.</span></span> <span data-ttu-id="a302f-117">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="a302f-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a302f-118">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a302f-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a302f-119">Fournissez un **Nom d’utilisateur** et un **Mot de passe** pour votre compte LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="a302f-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="a302f-120">Ces informations d’identification peuvent être différentes de vos informations d’identification à LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="a302f-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="a302f-121">Sélectionnez **Vérifier** pour tester la connexion à LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="a302f-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="a302f-122">Une fois la vérification réussie, donnez votre consentement pour **Confidentialité et conformité des données** en cochant la case **J’accepte**.</span><span class="sxs-lookup"><span data-stu-id="a302f-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="a302f-123">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="a302f-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a302f-124">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="a302f-124">Configure an export</span></span>

<span data-ttu-id="a302f-125">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="a302f-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a302f-126">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a302f-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a302f-127">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="a302f-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a302f-128">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="a302f-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a302f-129">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="a302f-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="a302f-130">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="a302f-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a302f-131">Dans le champ **Choisir votre identifiant de clé**, sélectionnez **E-mail**, **Nom et adresse** ou **Téléphone** à envoyer à LiveRamp pour la résolution des problèmes d’identité.</span><span class="sxs-lookup"><span data-stu-id="a302f-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a302f-132">![Connecteur LiveRamp avec mappage d’attributs](media/export-liveramp-segments.png "Connecteur LiveRamp avec mappage d’attributs")</span><span class="sxs-lookup"><span data-stu-id="a302f-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="a302f-133">Mappez les attributs correspondants de votre entité client unifiée pour l’identifiant de clé sélectionné.</span><span class="sxs-lookup"><span data-stu-id="a302f-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="a302f-134">Sélectionnez **Ajouter un attribut** pour mapper d’autres attributs à envoyer vers LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="a302f-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="a302f-135">L’envoi d’attributs d’identifiant de clé supplémentaires à LiveRamp est susceptible de vous permettre d’obtenir un taux de correspondance plus élevé.</span><span class="sxs-lookup"><span data-stu-id="a302f-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="a302f-136">Sélectionnez les segments que vous souhaitez exporter vers LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="a302f-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="a302f-137">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a302f-137">Select **Save**.</span></span>

<span data-ttu-id="a302f-138">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="a302f-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a302f-139">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a302f-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a302f-140">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a302f-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a302f-141">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="a302f-141">Data privacy and compliance</span></span>

<span data-ttu-id="a302f-142">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Liveramp, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="a302f-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a302f-143">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Liveramp respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="a302f-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a302f-144">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a302f-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a302f-145">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="a302f-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
