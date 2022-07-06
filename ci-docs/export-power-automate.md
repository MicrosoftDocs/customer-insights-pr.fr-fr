---
title: Connecteur Power Automate (version préliminaire) | Microsoft Docs
description: Créer des flux dans Microsoft Power Automate de Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29a861dad926072f6f849d738d868f0f3b9306be
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081060"
---
# <a name="power-automate-connector-preview"></a>Connecteur Power Automate (préversion)

Déclenchez des événements spécifiques automatiques lorsque vos données sont modifiées et gérez des flux plus complexes directement dans [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Limitations connues

- Vous pouvez passer au maximum 100 appels par minute. Vous pouvez appeler le point de terminaison d’API plusieurs fois en utilisant le paramètre $skip. [En savoir plus sur le paramètre $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Déclencheurs Power Automate

Utilisez des déclencheurs pour créer des flux de cloud et automatiser des tâches répétitives, telles que des notifications ou des actions plus avancées.

- Déclencher quand une actualisation source de données échoue.
- Déclencher quand une actualisation source de données réussit.
- Déclencher lorsqu’un seuil est franchi sur un segment. Le déclencheur se limite à franchir le seuil.
- Déclencher lorsqu’un seuil est franchi sur une mesure d’activité. Seules les mesures d’entreprise sans dimension sont prises en charge. Le déclencheur se limite à franchir le seuil.
- Déclencher quand une actualisation complète (sources de données, segments, mesures...) est terminée.
- Déclenchement lorsqu’une actualisation du processus d’unification est terminée.

[Configurer vos déclencheurs dans Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Actions Power Automate

Le connecteur Power Automate fournit d’autres actions que les déclencheurs disponibles. Pour plus d’informations, voir le [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Créer un flux Power Automate

1. Accédez à **Administration** > **Destinations d’exportation**.

1. Sur la vignette **Power Automate**, sélectionnez **Configurer**.

1. Connecteur Customer Insights (version préliminaire) dans les applications Power Automate. **Connectez-vous** à Power Automate.

1. Choisissez l’un des déclencheurs disponibles et ajoutez d’autres étapes à votre nouveau flux. Pour plus d’informations, voir [Créer un flux de cloud dans Power Automate](/power-automate/get-started-logic-flow).

Exemples d’utilisation des flux : 
- Publiez un message à un canal Microsoft Teams si une actualisation de source de données échoue. 
- Envoyez un e-mail aux propriétaires des données lorsqu’un seuil sur un segment est franchi.



[!INCLUDE [footer-include](includes/footer-banner.md)]
