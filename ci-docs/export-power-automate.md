---
title: Connecteur Power Automate (version préliminaire) | Microsoft Docs
description: Créer des flux dans Microsoft Power Automate de Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196115"
---
# <a name="power-automate-connector-preview"></a>Connecteur Power Automate (préversion)

Déclenchez des événements spécifiques automatiques lorsque vos données sont modifiées et gérez des flux plus complexes directement dans [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Limitations connues

- Un maximum de 100 appels par minute. Utilisez le [paramètre $skip](/connectors/customerinsights/#get-items-from-an-entity) pour appeler le point de terminaison d’API plusieurs fois.

## <a name="power-automate-triggers"></a>Déclencheurs Power Automate

Utilisez des déclencheurs pour créer des flux de cloud et automatiser des tâches répétitives, telles que des notifications ou des actions plus avancées. Utilisez des déclencheurs quand :

- L’actualisation d’une source de données échoue.
- L’actualisation d’une source de données réussit.
- Un seuil est franchi sur un segment. Le déclencheur se limite à franchir le seuil.
- Un seuil est franchi sur une mesure d’activité. Seules les mesures d’entreprise sans dimension sont prises en charge. Le déclencheur se limite à franchir le seuil.
- Une actualisation planifiée complète est terminée. Ce déclencheur ne fonctionne pas pour les actualisations lancées manuellement.
- Une actualisation du processus d’unification est terminée.

[Configurer vos déclencheurs dans Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Actions Power Automate

Le connecteur Power Automate fournit d’autres actions que les déclencheurs disponibles. Pour plus d’informations, voir le [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Créer un flux Power Automate

1. Accédez à **Administrateur** > **Connexions**.

1. Sur la vignette **Power Automate**, sélectionnez **Configurer**.

1. Connecteur Customer Insights (version préliminaire) dans les applications Power Automate. **Connectez-vous** à Power Automate.

1. Choisissez l’un des déclencheurs disponibles et ajoutez d’autres étapes à votre nouveau flux. Pour plus d’informations, voir [Créer un flux de cloud dans Power Automate](/power-automate/get-started-logic-flow).

Exemples d’utilisation des flux : 
- Publiez un message à un canal Microsoft Teams si une actualisation de source de données échoue. 
- Envoyez un e-mail aux propriétaires des données lorsqu’un seuil sur un segment est franchi.

[!INCLUDE [footer-include](includes/footer-banner.md)]
