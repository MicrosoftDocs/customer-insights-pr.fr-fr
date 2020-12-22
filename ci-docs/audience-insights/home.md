---
title: Page d'accueil de Audience Insights
description: Commencez à explorer l'application sur la page d'accueil.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405666"
---
# <a name="create-a-new-environment"></a>Créer un environnement

## <a name="create-a-trial-environment"></a>Créer un environnement d'essai

Vous pouvez vous inscrire à un essai sur la [page d'inscription à un essai](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Les essais expirent après 30 jours.

1. Choisissez l'option **S'inscrire à un essai gratuit** et sélectionnez **S'inscrire maintenant**.

1. Indiquez votre adresse e-mail professionnelle ou scolaire, dites-nous en plus sur vous et sélectionnez **Suivant**.

1. Indiquez un **Nom** pour votre nouvel environnement. 

1. Sélectionnez le type d'essai.

1. Choisissez la **Région** pour votre environnement.

1. Facultativement, pour les administrateurs d'une organisation Dynamics 365 : sélectionnez **Paramètres avancés** et indiquez l'URL de votre organisation pour utiliser les fonctionnalités prédictives telles que le taux de désabonnement des clients.

1. Sélectionnez **Créer**. 

Une fois l'environnement créé, vous verrez l'environnement **Démo** environnement qui vous permet d'explorer l'application avec des données fictives. Vous pouvez modifier les exemples de données en fonction de votre secteur. Sélectionnez l'icône **Paramètres** dans l'en-tête, puis sélectionnez **Paramètres de démonstration**. En outre, vous pouvez modifier le thème visuel. 

[Basculez vers l'environnement](#change-between-environments) que vous avez créé pendant le processus d'inscription pour utiliser vos propres données.

## <a name="create-a-new-production-or-sandbox-environment"></a>Créer un environnement de production ou de bac à sable

Dans votre environnement, sélectionnez l'icône **Paramètres** dans l'en-tête et sélectionnez **Nouvel environnement**.

Procédez comme si vous [créiez un environnement d'essai](#create-a-trial-environment). Vous obtenez une option supplémentaire lors de la sélection des **Paramètres avancés** pour stocker vos données dans votre propre Azure Data Lake. Indiquez votre nom de compte et votre clé de compte pour établir une connexion à votre Azure Data Lake. Par défaut, les données sont stockées dans le lac de données géré de Customer Insights.

> [!IMPORTANT]
> En enregistrant les données dans votre Azure Data Lake Storage, vous acceptez qu’elles soient transférées vers l’emplacement géographique approprié pour ce compte de stockage Azure et qu’elles y soient stockées. Cet emplacement peut différer de l’emplacement de stockage des données dans Dynamics 365 Customer Insights. [En savoir plus sur le Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Explorer la page d’accueil

Vous pouvez [accéder à votre environnement Customer Insights](https://home.ci.ai.dynamics.com/) sur l'URL suivante : [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
La page **Accueil** présente une vue d’ensemble de votre clientèle et des mesures clés pour suivre l’intégrité de votre entreprise.

> [!div class="mx-imgBorder"] 
> ![Informations de la page d’accueil](media/home-page-insights.png "Informations de la page d’accueil")

Sous **Segments récents**, vous voyez des groupes de clients en fonction des attributs démographiques, comportementaux ou transactionnels que vous avez définis. [Création de segments](segments.md) vous aide à mieux cibler vos activités commerciales.

**Mesures récentes** illustre les vignettes avec [les mesures](measures.md). Les mesures ont des indicateurs de performance clés (KPI) que vous avez définis. Par exemple, la probabilité moyenne d’attrition clients ou les dépenses moyennes en ligne par client.

La section **Enrichissements récents** répertorie les résultats des cycles d’enrichissement récemment terminés. Les enrichissements ajoutent des informations sur votre clientèle. Par exemple, en comprenant les centres d’intérêts et les marques pour lesquels ils ont des affinités. Ces informations peuvent être déverrouillées à l’aide des capacités d’[enrichissement](enrichment-microsoft-graph.md), après avoir terminé les phases de [mappage](map-entities.md), de [mise en correspondance](match-entities.md), et de [fusion](merge-entities.md).

## <a name="change-between-environments"></a>Basculer entre les environnements

Une fois que vous avez installé et configuré les [sources d’information](data-sources.md), vous voudrez passer d’un environnement de démonstration à un environnement réel. L’utilisation de l’environnement de production vous permet d’utiliser vos propres données client. Sélectionnez le contrôle **Environnement** dans le coin supérieur droit de la page pour changer d’environnement.

> [!div class="mx-imgBorder"] 
> ![Modifier l’environnement](media/home-page-environment-switcher.png "Modifier l’environnement")

Les administrateurs peuvent créer et gérer des [environnements multiples](manage-environments.md). La gestion de plusieurs environnements peut être utile si, par exemple, votre organisation opère à l’international et que vous devez séparer les données et les informations de différentes manières.

## <a name="next-step"></a>Étape suivante

Pour voir vos propres informations sur la page d’accueil, vous devez d’abord [ajouter des sources de données](data-sources.md) et [unifier](data-unification.md) vos données pour construire des profils clients.
