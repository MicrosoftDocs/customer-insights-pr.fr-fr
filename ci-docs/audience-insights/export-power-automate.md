---
title: Connecteur Power Automate | Microsoft Docs
description: Créer des flux dans Microsoft Power Automate de Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305061"
---
# <a name="power-automate-connector-preview"></a>Connecteur Power Automate (préversion)

Déclenchez des événements spécifiques automatiques lorsque vos données sont modifiées et gérez des flux plus complexes directement dans [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Déclencheurs Power Automate

Utilisez des déclencheurs pour créer des flux de cloud et automatiser des tâches répétitives, telles que des notifications ou des actions plus avancées. 

- Déclencher quand une actualisation source de données échoue. 
- Déclencher quand une actualisation source de données réussit.
- Déclencher lorsqu’un seuil est franchi sur un segment. Le déclencheur se limite à franchir le seuil.
- Déclencher lorsqu’un seuil est franchi sur une mesure d’activité. Seules les mesures d’entreprise sans dimension sont prises en charge. Le déclencheur se limite à franchir le seuil.
- Déclencher quand une actualisation complète (sources de données, segments, mesures...) est terminée.
- Déclencher lorsqu’une actualisation du processus d’unification (mappage, correspondance, fusion) est terminée.

[Configurer vos déclencheurs dans Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Actions Power Automate

Le connecteur Power Automate fournit d’autres actions que les déclencheurs disponibles. Pour plus d’informations, voir le [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Créer un flux Power Automate

1. Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.

1. Sur la vignette **Power Automate**, sélectionnez **Configurer**.

1. Connecteur Customer Insights (version préliminaire) dans les applications Power Automate. **Connectez-vous** à Power Automate.

1. Choisissez l’un des déclencheurs disponibles et ajoutez d’autres étapes à votre nouveau flux. Pour plus d’informations, voir [Créer un flux de cloud dans Power Automate](/power-automate/get-started-logic-flow).

Exemples d’utilisation des flux : 
- Publiez un message à un canal Microsoft Teams si une actualisation de source de données échoue. 
- Envoyez un e-mail aux propriétaires des données lorsqu’un seuil sur un segment est franchi.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
