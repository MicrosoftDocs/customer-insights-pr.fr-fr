---
title: Guide de démarrage rapide de la gestion du consentement
description: Suivez ces quatre étapes pour configurer rapidement la gestion du consentement, importer des données de consentement et configurer des règles de données de consentement dans Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: consent-management
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-system-consent
- customerInsights
ms.openlocfilehash: 5ded1c685e0c4588da0971b9dcea50f6a5dcf53d
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653597"
---
# <a name="get-started-with-consent-management"></a>Démarrer avec la gestion du consentement

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La capacité de gestion du consentement de Dynamics 365 Customer Insights permet aux organisations de gérer les données de consentement.

## <a name="step-1-set-up-consent-management"></a>Étape 1 : Configurer la gestion du consentement

Vous devez être [administrateur dans Customer Insights](../permissions.md) pour utiliser la capacité de gestion du consentement.

Sélectionnez **Bienvenue dans le Centre de consentement** de la page **Accueil** de Customer Insights. La préparation du Centre de consentement peut prendre un certain temps s’il s’agit de votre première visite. Consultez les conditions d’utilisation avant de continuer. Vous allez commencer sur la page d’accueil du Centre de consentement. Cette page donne un aperçu des fonctionnalités clés et fournit des liens vers la documentation associée.

:::image type="content" source="media/consent-center-cta.png" alt-text="Lancez le Centre de consentement à partir de la page d’accueil de Customer Insights.":::

## <a name="step-2-import-consent-data"></a>Étape 2 : Importer des données de consentement

Dans le Centre de consentement, [importez les données de consentement](import-consent-data.md) que votre organisation a collectées via un large éventail de connecteurs disponibles.

## <a name="step-3-configure-consent-data-rules-and-define-default-rules"></a>Étape 3 : Configurer les règles de données de consentement et définir des règles par défaut

Après avoir importé les données de consentement, [configurez les règles de données de consentement](set-consent-rules.md) et définissez des règles à appliquer par défaut.

## <a name="step-4-apply-consent-rules-to-segments-in-customer-insights"></a>Étape 4 : Appliquer les règles de consentement aux segments dans Customer Insights

Les règles que vous avez créées se synchronisent automatiquement avec Customer Insights. [Activez les règles de consentement par défaut](../activate-consent.md) pour les segments dans Customer Insights. Vous pouvez maintenant [exporter des segments](../export-destinations.md) dans Customer Insights avec les règles de données de consentement appliquées.

## <a name="step-5-review-consent-metrics-on-the-home-page"></a>Étape 5 : Examiner les mesures de consentement sur la page d’accueil

Les données de consentement importées et les règles associées sont visualisées sur la page **Accueil** du Centre de consentement. Les graphiques vous informent des importations et règles de données récentes.

- **Répartition des préférences de communication** vous aide à analyser le consentement de vos clients dans les différents canaux de communication comme le courrier électronique et les SMS pour vous aider à identifier rapidement le canal qui a la meilleure portée. Elle affiche le nombre total d’identifiants de personnes concernées comme les courriers électroniques et les numéros de téléphone qui ont donné leur consentement et d’identifiants de personnes concernées qui n’ont pas donné leur consentement pour chaque canal de communication.
- **Répartition des règles de consentement** vous donne un aperçu rapide du nombre total d’identifiants de personnes concernées qui ont donné leur consentement et d’identifiants de personnes concernées qui n’ont pas donné leur consentement pour vous aider à identifier rapidement le nombre de clients joignables dans votre clientèle.
- **Répartition des objectifs d’utilisation des données** vous aide à visualiser rapidement les principaux objectifs d’utilisation des données pour lesquelles votre clientèle a donné son consentement et les décompose pour mettre en évidence le nombre total d’identifiants de personnes concernées qui ont donné leur consentement et d’identifiants de personnes concernées qui n’ont pas donné leur consentement.
- **Répartition des abonnements** vous aide à visualiser rapidement les principaux abonnements pour lesquels votre clientèle a donné son consentement et les décompose pour mettre en évidence le nombre total d’identifiants de personnes concernées qui ont donné leur consentement et d’identifiants de personnes concernées qui n’ont pas donné leur consentement. 

La page d’accueil fournit également un ensemble de liens utiles qui pointent vers des articles pertinents de la documentation.
