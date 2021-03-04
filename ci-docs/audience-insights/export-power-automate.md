---
title: Connecteur Power Automate | Microsoft Docs
description: Créer des flux dans Microsoft Power Automate de Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268821"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="ca5aa-103">Connecteur Power Automate (préversion)</span><span class="sxs-lookup"><span data-stu-id="ca5aa-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="ca5aa-104">Déclenchez des événements spécifiques automatiques lorsque vos données sont modifiées et gérez des flux plus complexes directement dans [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="ca5aa-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="ca5aa-105">Déclencheurs Power Automate</span><span class="sxs-lookup"><span data-stu-id="ca5aa-105">Power Automate triggers</span></span>

<span data-ttu-id="ca5aa-106">Utilisez des déclencheurs pour créer des flux de cloud et automatiser des tâches répétitives, telles que des notifications ou des actions plus avancées.</span><span class="sxs-lookup"><span data-stu-id="ca5aa-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="ca5aa-107">Déclencher quand une actualisation source de données échoue.</span><span class="sxs-lookup"><span data-stu-id="ca5aa-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="ca5aa-108">Déclencher quand une actualisation source de données réussit.</span><span class="sxs-lookup"><span data-stu-id="ca5aa-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="ca5aa-109">Déclencher lorsqu’un seuil est franchi sur un segment.</span><span class="sxs-lookup"><span data-stu-id="ca5aa-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="ca5aa-110">Le déclencheur se limite à franchir le seuil.</span><span class="sxs-lookup"><span data-stu-id="ca5aa-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="ca5aa-111">Déclencher lorsqu’un seuil est franchi sur une mesure d’activité.</span><span class="sxs-lookup"><span data-stu-id="ca5aa-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="ca5aa-112">Le déclencheur se limite à franchir le seuil.</span><span class="sxs-lookup"><span data-stu-id="ca5aa-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="ca5aa-113">Déclencher quand une actualisation complète des (sources de données, segments, mesures...) est terminée.</span><span class="sxs-lookup"><span data-stu-id="ca5aa-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="ca5aa-114">Déclencher lorsqu’une actualisation du processus d’unification (mappage, correspondance, fusion) est terminée.</span><span class="sxs-lookup"><span data-stu-id="ca5aa-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="ca5aa-115">[Configurer vos déclencheurs dans Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="ca5aa-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="ca5aa-116">Actions Power Automate</span><span class="sxs-lookup"><span data-stu-id="ca5aa-116">Power Automate actions</span></span>
<span data-ttu-id="ca5aa-117">Le connecteur Power Automate fournit d’autres actions que les déclencheurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="ca5aa-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="ca5aa-118">Pour plus d’informations, voir le [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="ca5aa-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="ca5aa-119">Créer un flux Power Automate</span><span class="sxs-lookup"><span data-stu-id="ca5aa-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="ca5aa-120">Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="ca5aa-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ca5aa-121">Sur la vignette **Power Automate**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="ca5aa-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="ca5aa-122">Connecteur Customer Insights (version préliminaire) dans les applications Power Automate.</span><span class="sxs-lookup"><span data-stu-id="ca5aa-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="ca5aa-123">**Connectez-vous** à Power Automate.</span><span class="sxs-lookup"><span data-stu-id="ca5aa-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="ca5aa-124">Choisissez l’un des déclencheurs disponibles et ajoutez d’autres étapes à votre nouveau flux.</span><span class="sxs-lookup"><span data-stu-id="ca5aa-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="ca5aa-125">Pour plus d’informations, voir [Créer un flux de cloud dans Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="ca5aa-125">For more information, see [Create a cloud flow in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="ca5aa-126">Exemples d’utilisation des flux :</span><span class="sxs-lookup"><span data-stu-id="ca5aa-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="ca5aa-127">Publiez un message à un canal Microsoft Teams si une actualisation de source de données échoue.</span><span class="sxs-lookup"><span data-stu-id="ca5aa-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="ca5aa-128">Envoyez un e-mail aux propriétaires des données lorsqu’un seuil sur un segment est franchi.</span><span class="sxs-lookup"><span data-stu-id="ca5aa-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]