---
title: Connecteur LiveRamp
description: Découvrez comment exporter des données vers LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270155"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="c35fa-103">Connecteur&reg; LiveRamp (aperçu)</span><span class="sxs-lookup"><span data-stu-id="c35fa-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="c35fa-104">Activez vos données dans LiveRamp pour vous connecter à plus de 500 plateformes à travers les écosystèmes numériques, sociaux et télévisuels.</span><span class="sxs-lookup"><span data-stu-id="c35fa-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="c35fa-105">Exploitez vos données dans LiveRamp pour cibler, supprimer et personnaliser des campagnes publicitaires.</span><span class="sxs-lookup"><span data-stu-id="c35fa-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c35fa-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="c35fa-106">Prerequisites</span></span>

- <span data-ttu-id="c35fa-107">Vous avez besoin d’un abonnement LiveRamp pour utiliser ce connecteur.</span><span class="sxs-lookup"><span data-stu-id="c35fa-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="c35fa-108">Pour obtenir un abonnement, [contactez LiveRamp](https://liveramp.com/contact/) directement.</span><span class="sxs-lookup"><span data-stu-id="c35fa-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="c35fa-109">[En savoir plus sur LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="c35fa-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="c35fa-110">Se connecter à LiveRamp</span><span class="sxs-lookup"><span data-stu-id="c35fa-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="c35fa-111">Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="c35fa-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c35fa-112">Dans la vignette **LiveRamp**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="c35fa-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="c35fa-113">Donnez à votre destination un nom reconnaissable dans le champ **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="c35fa-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c35fa-114">Fournissez un **Nom d’utilisateur** et un **Mot de passe** pour votre compte LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="c35fa-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="c35fa-115">Ces informations d’identification peuvent être différentes de vos informations d’identification à LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="c35fa-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="c35fa-116">Sélectionnez **Vérifier** pour tester la connexion à LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="c35fa-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="c35fa-117">Une fois la vérification réussie, donnez votre consentement pour **Confidentialité et conformité des données** en cochant la case **J’accepte**.</span><span class="sxs-lookup"><span data-stu-id="c35fa-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="c35fa-118">Sélectionnez **Suivant** pour configurer le connecteur LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="c35fa-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="c35fa-119">Configurer le connecteur</span><span class="sxs-lookup"><span data-stu-id="c35fa-119">Configure the connector</span></span>

1. <span data-ttu-id="c35fa-120">Dans le champ **Choisir votre identifiant de clé**, sélectionnez **E-mail**, **Nom et adresse** ou **Téléphone** à envoyer à LiveRamp pour la résolution des problèmes d’identité.</span><span class="sxs-lookup"><span data-stu-id="c35fa-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="c35fa-121">Mappez les attributs correspondants de votre entité client unifiée pour l’identifiant de clé sélectionné.</span><span class="sxs-lookup"><span data-stu-id="c35fa-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="c35fa-122">Sélectionnez **Ajouter un attribut** pour mapper des attributs supplémentaires à envoyer à LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="c35fa-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="c35fa-123">L’envoi d’attributs d’identifiant de clé supplémentaires à LiveRamp est susceptible de vous permettre d’obtenir un taux de correspondance plus élevé.</span><span class="sxs-lookup"><span data-stu-id="c35fa-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="c35fa-124">Sélectionnez les segments que vous souhaitez exporter vers LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="c35fa-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="c35fa-125">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c35fa-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c35fa-126">![Connecteur LiveRamp avec mappage d’attributs](media/export-liveramp-segments.png "Connecteur LiveRamp avec mappage d’attributs")</span><span class="sxs-lookup"><span data-stu-id="c35fa-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c35fa-127">Exporter les données</span><span class="sxs-lookup"><span data-stu-id="c35fa-127">Export the data</span></span>

<span data-ttu-id="c35fa-128">L’exportation doit démarrer rapidement si toutes les conditions préalables requises pour l’exportation sont satisfaites.</span><span class="sxs-lookup"><span data-stu-id="c35fa-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="c35fa-129">L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c35fa-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="c35fa-130">Une fois l’exportation terminée, vous pouvez vous connecter à LiveRamp Onboarding pour activer et distribuer vos données.</span><span class="sxs-lookup"><span data-stu-id="c35fa-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c35fa-131">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="c35fa-131">Data privacy and compliance</span></span>

<span data-ttu-id="c35fa-132">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Liveramp, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="c35fa-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c35fa-133">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Liveramp respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="c35fa-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c35fa-134">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c35fa-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c35fa-135">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="c35fa-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]