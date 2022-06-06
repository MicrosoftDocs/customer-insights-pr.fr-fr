---
title: Utiliser les profils unifiés dans Dynamics 365 Marketing
description: Apprenez à intégrer les profils et segments unifiés avec Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4cc3cbde97d0f9da198652e86c0843476393b646
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833305"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Utiliser les Unified Customer Profiles dans Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) améliore l’expérience client, en vous permettant d’orchestrer des parcours personnalisés sur tous les points de contact pour renforcer les relations et fidéliser. L’application Dynamics 365 Marketing fonctionne de manière transparente avec Dynamics 365 Sales, Dynamics 365 Customer Insights, Microsoft Teams et d’autres produits, et vous permet de prendre de meilleures décisions plus rapidement en utilisant la puissance des données et de l’IA.

En connectant les données Customer Insights à Marketing, vous pouvez :

- Cibler des Unified Customer Profiles et des segments. Cela vous permet d’interagir avec chaque client, quel que soit l’emplacement des données du client.
- Baser le contenu dynamique (comme les jetons personnalisés) dans les courriers électroniques, les SMS et les notifications push sur des mesures telles que le statut de fidélité, la date de renouvellement de l’abonnement, le compte parent ou toute autre mesure que vous avez capturée dans le profil Customer Insights unifié.
- Charger les données de Marketing dans Customer Insights et les combiner avec les données client d’autres sources.
- Appliquer les outils de nettoyage des données, d’enrichissement, de mise en correspondance partielle de Customer Insights.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Utiliser les profils client enrichis dans le marketing en temps réel

Le marketing en temps réel vous permet de créer des [déclencheurs personnalisés](/dynamics365/marketing/real-time-marketing-custom-triggers) qui lancent des parcours des clients en fonction de n’importe quelle action client. Plus vos données seront personnalisées, plus vos parcours seront pertinents et personnalisés. C’est ce qui rend la combinaison de Marketing et Customer Insights si puissante. Vous pouvez [unifier les données](data-unification.md) de n’importe quelle source, puis les utiliser pour alimenter des parcours des clients hyper-personnalisés.

En savoir plus : [Utiliser les profils et les segments Customer Insights dans le marketing en temps réel](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Utilisation des segments unifiés avec les parcours des clients sortants

Customer Insights vous permet d’affiner les données provenant de nombreuses sources et de les combiner en segments de clients agrégés. En [connectant Customer Insights au marketing sortant](export-dynamics365-marketing.md), ces segments apparaîtront automatiquement *et* s’actualiseront automatiquement dans le concepteur de parcours du client.

Pour en savoir plus : [Utilisation des segments de Dynamics 365 Customer Insights avec Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Extraction de données de votre propre Azure Data Lake Storage

Vous n’êtes pas limité au stockage dans le cloud si vous souhaitez utiliser les données Customer Insights avec Marketing. Si vous avez déjà votre propre entité de Azure Data Lake Storage configurée, vous pouvez vous connecter à Customer Insights, puis partager les données avec l’application Marketing comme vous le feriez avec une configuration basée sur le cloud.

Pour en savoir plus : [Activation du partage de données avec Dataverse à partir de votre propre Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
