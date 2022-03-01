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
# <a name="power-automate-connector-preview"></a>Connecteur Power Automate (préversion)

Déclenchez des événements spécifiques automatiques lorsque vos données sont modifiées et gérez des flux plus complexes directement dans [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Déclencheurs Power Automate

Vous pouvez utiliser une variété de déclencheurs qui vous permettent de créer des flux pour automatiser des tâches répétitives, telles que des notifications ou des actions plus avancées. 

- Déclencher quand une actualisation source de données échoue. 
- Déclencher quand une actualisation source de données réussit.
- Déclencher lorsqu'un seuil est franchi sur un segment. Le déclencheur se limite à franchir le seuil.
- Déclencher lorsqu'un seuil est franchi sur une mesure d'activité. Le déclencheur se limite à franchir le seuil.
- Déclencher quand une actualisation complète des (sources de données, segments, mesures...) est terminée.
- Déclencher lorsqu'une actualisation du processus d'unification (mappage, correspondance, fusion) est terminée.

[Configurer vos déclencheurs dans Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Actions Power Automate
Le connecteur Power Automate fournit d'autres actions que les déclencheurs disponibles. Pour plus d’informations, voir le [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Créer un flux Power Automate dans Audience Insights

1. Dans Audience Insights, accédez à **Administration** > **Système**.

1. Dans la page **Système**, sélectionnez **Statut**.

1. Dans la section **Source de données**, sélectionnez **Flux** et sélectionnez **Créer un flux** dans la liste déroulante.
   > [!div class="mx-imgBorder"]
   > ![Le connecteur Power Automate affichant Créer une action de flux](media/power-automate-connector-create-flow.png "Le connecteur Power Automate affichant Créer une action de flux")

1. Dans Power Automate, sélectionnez l'un des déclencheurs disponibles pour créer votre flux préféré. Si vous créez votre premier flux, vous devrez vous authentifier avec le connecteur Power Automate en premier.
