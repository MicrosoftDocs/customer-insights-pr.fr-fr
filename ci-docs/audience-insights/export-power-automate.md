---
title: Connecteur Power Automate | Microsoft Docs
description: Créer des flux dans Microsoft Power Automate de Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405636"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="af375-103">Connecteur Power Automate (préversion)</span><span class="sxs-lookup"><span data-stu-id="af375-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="af375-104">Déclenchez des événements spécifiques automatiques lorsque vos données sont modifiées et gérez des flux plus complexes directement dans [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="af375-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="af375-105">Déclencheurs Power Automate</span><span class="sxs-lookup"><span data-stu-id="af375-105">Power Automate triggers</span></span>

<span data-ttu-id="af375-106">Vous pouvez utiliser une variété de déclencheurs qui vous permettent de créer des flux pour automatiser des tâches répétitives, telles que des notifications ou des actions plus avancées.</span><span class="sxs-lookup"><span data-stu-id="af375-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="af375-107">Déclencher quand une actualisation source de données échoue.</span><span class="sxs-lookup"><span data-stu-id="af375-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="af375-108">Déclencher quand une actualisation source de données réussit.</span><span class="sxs-lookup"><span data-stu-id="af375-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="af375-109">Déclencher lorsqu'un seuil est franchi sur un segment.</span><span class="sxs-lookup"><span data-stu-id="af375-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="af375-110">Le déclencheur se limite à franchir le seuil.</span><span class="sxs-lookup"><span data-stu-id="af375-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="af375-111">Déclencher lorsqu'un seuil est franchi sur une mesure d'activité.</span><span class="sxs-lookup"><span data-stu-id="af375-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="af375-112">Le déclencheur se limite à franchir le seuil.</span><span class="sxs-lookup"><span data-stu-id="af375-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="af375-113">Déclencher quand une actualisation complète des (sources de données, segments, mesures...) est terminée.</span><span class="sxs-lookup"><span data-stu-id="af375-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="af375-114">Déclencher lorsqu'une actualisation du processus d'unification (mappage, correspondance, fusion) est terminée.</span><span class="sxs-lookup"><span data-stu-id="af375-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="af375-115">[Configurer vos déclencheurs dans Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="af375-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="af375-116">Actions Power Automate</span><span class="sxs-lookup"><span data-stu-id="af375-116">Power Automate actions</span></span>
<span data-ttu-id="af375-117">Le connecteur Power Automate fournit d'autres actions que les déclencheurs disponibles.</span><span class="sxs-lookup"><span data-stu-id="af375-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="af375-118">Pour plus d’informations, voir le [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="af375-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="af375-119">Créer un flux Power Automate dans Audience Insights</span><span class="sxs-lookup"><span data-stu-id="af375-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="af375-120">Dans Audience Insights, accédez à **Administration** > **Système**.</span><span class="sxs-lookup"><span data-stu-id="af375-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="af375-121">Dans la page **Système**, sélectionnez **Statut**.</span><span class="sxs-lookup"><span data-stu-id="af375-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="af375-122">Dans la section **Source de données**, sélectionnez **Flux** et sélectionnez **Créer un flux** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="af375-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="af375-123">![Le connecteur Power Automate affichant Créer une action de flux](media/power-automate-connector-create-flow.png "Le connecteur Power Automate affichant Créer une action de flux")</span><span class="sxs-lookup"><span data-stu-id="af375-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="af375-124">Dans Power Automate, sélectionnez l'un des déclencheurs disponibles pour créer votre flux préféré.</span><span class="sxs-lookup"><span data-stu-id="af375-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="af375-125">Si vous créez votre premier flux, vous devrez vous authentifier avec le connecteur Power Automate en premier.</span><span class="sxs-lookup"><span data-stu-id="af375-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
