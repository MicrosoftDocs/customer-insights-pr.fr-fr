---
title: Mise en route de Dynamics 365 Customer Insights
description: Une présentation des ressources d’aide de Customer Insights pour démarrer rapidement
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1a19d83930d667bdca5301dcc5a3ffa5db6a7bdc
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741130"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Mise en route de Dynamics 365 Customer Insights

Customer Insights peut vous aider à mieux comprendre vos clients. Connectez les données de diverses sources transactionnelles, comportementales et d’observation pour créer une vue client à 360 degrés. Utilisez ces informations pour générer des expériences et des processus orientés client. Unifiez et comprenez les données clientes et exploitez-les pour en tirer des informations et des actions utiles.

## <a name="step-1-create-an-environment"></a>Étape 1 : Créer un environnement

Pour commencer, vous devez d’abord créer un environnement dans lequel travailler. Si votre organisation a déjà acheté une licence, consultez [Créer un environnement](create-environment.md). Pour démarrer un essai de Customer Insights, consultez [Configurer un environnement d’essai](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Étape 2 : Explorer Customer Insights

La première fois que vous vous connectez à Customer Insights, vous pouvez configurer les paramètres et explorer le produit.

1. [Connectez-vous à Customer Insights](https://home.ci.ai.dynamics.com) en utilisant votre compte d’utilisateur Microsoft Azure Active Directory (AAD).

1. [Changez l’environnement](manage-environments.md#switch-environments) pour voir les données de démonstration et [explorer Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Étape 3 : Ingérer, unifier et configurer les relations pour vos données

Les profils unifiés sont la base pour obtenir des informations et agir sur les données. Importez des données de diverses sources et exécutez le processus d’unification des données pour combiner des profils unifiés. Spécifiez les relations entre les entités ingérées et utilisez les fonctionnalités d’enrichissement pour ajouter des informations aux profils.

1. Ingérez des données en créant des sources de données à partir de plusieurs options. Choisissez entre des [connecteurs Power Query](connect-power-query.md), un [dossier Common Data Model](connect-common-data-model.md), ou [Microsoft Dataverse](connect-dataverse-managed-lake.md). 

1. Exécutez le [processus d’unification des données](data-unification.md) en identifiant les [champs source](map-entities.md), en supprimant les [doublons](remove-duplicates.md), les [conditions de correspondance](match-entities.md), et les [champs d’unification](merge-entities.md).

1. Familiarisez-vous avec les [entités créées par le système](entities.md) et créez des [relations entre les entités ingérées](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Étape 4 : Améliorer les profils unifiés avec des prédictions, activités et mesures

Une fois les profils unifiés configurés, vous pouvez améliorer vos données et augmenter davantage les informations qu’ils fournissent.

1. Choisissez dans une bibliothèque extensible de fournisseurs d’enrichissement pour [enrichir vos données clientes](enrichment-hub.md).

1. Utilisez des [modèles prédéfinis](predictions-overview.md) pour prédire la probabilité d’abandon ou les revenus attendus.

1. [Configurez des activités](activities.md) en fonction des données ingérées et visualisez les interactions avec vos clients dans une vue chronologique.

1. [Créez des mesures](measures.md) pour évaluer vos objectifs commerciaux et vos KPI.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Étape 5 : Créer des segments et activer les données via diverses options d’exportation

Maintenant que vos données sont complètes et contiennent un large éventail d’informations sur vos clients, il est temps de rechercher des moyens d’agir sur ces données.

1. [Créez des segments](segments.md), c’est-à-dire des sous-ensembles de votre clientèle, pour vous assurer que vos actions sont pertinentes pour les clients ciblés.

1. Parcourez le catalogue extensible des [options d’exportation](export-destinations.md) où vous pouvez utiliser les données clientes. Par exemple, vous pouvez utiliser les données pour gérer les promotions et contacter les clients par marketing numérique.

1. Passez en revue les options d’intégration, par exemple à d’autres applications Dynamics 365 avec le [Complément de carte client](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]