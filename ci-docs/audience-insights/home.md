---
title: Page d’accueil des informations sur l’audience
description: Commencez à explorer l’application sur la page d’accueil.
ms.date: 01/07/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7cc767f5d80b213a4c1bb5b2e8062bd44c15279b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477038"
---
# <a name="create-a-new-environment"></a>Créer un environnement

## <a name="create-a-trial-environment"></a>Créer un environnement d’essai

Vous pouvez vous inscrire à un essai sur la [page d’inscription à un essai](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Les essais expirent après 30 jours.

1. Choisissez l’option **S’inscrire à un essai gratuit** et sélectionnez **S’inscrire maintenant**.

1. Indiquez votre adresse e-mail professionnelle ou scolaire, dites-nous en plus sur vous et sélectionnez **Suivant**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Boîte de dialogue pour s’inscrire à une instance d’essai":::

1. Indiquez un **Nom** pour votre nouvel environnement. 

1. Sélectionnez le type d’essai.

1. Choisissez la **Région** pour votre environnement.

1. Facultativement, pour les administrateurs d’une organisation Dynamics 365 : sélectionnez **Paramètres avancés** et indiquez l’URL de votre organisation pour utiliser les fonctionnalités prédictives telles que le taux de désabonnement des clients.

1. Sélectionnez **Créer**. 

Une fois l’environnement créé, vous verrez l’environnement **Démo** environnement qui vous permet d’explorer l’application avec des données fictives. Vous pouvez modifier les exemples de données en fonction de votre secteur. Sélectionnez l’icône **Paramètres** dans l’en-tête, puis sélectionnez **Paramètres de démonstration**. En outre, vous pouvez modifier le thème visuel. 

[Basculez vers l’environnement](#switch-environments) que vous avez créé pendant le processus d’inscription pour utiliser vos propres données.

## <a name="create-a-new-production-or-sandbox-environment"></a>Créer un environnement de production ou de bac à sable

Dans votre environnement, sélectionnez le sélecteur **Environnements** dans l’en-tête de l’application et cliquez sur **Nouveau**.

Procédez comme si vous [créiez un environnement d’essai](#create-a-trial-environment). Par défaut, les données sont stockées dans le lac de données géré de Customer Insights. Vous obtenez une option supplémentaire lors de la sélection des **Paramètres avancés** pour stocker vos données dans votre propre Azure Data Lake. Indiquez votre nom de compte et votre clé de compte pour établir une connexion à votre Azure Data Lake. 

> [!IMPORTANT]
> En enregistrant les données dans votre Azure Data Lake Storage, vous acceptez qu’elles soient transférées vers l’emplacement géographique approprié pour ce compte de stockage Azure et qu’elles y soient stockées. Cet emplacement peut différer de l’emplacement de stockage des données dans Dynamics 365 Customer Insights. [En savoir plus sur le Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Explorer la page d’accueil

Vous pouvez [accéder aux informations sur l’audience dans Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) avec l’URL suivante : [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
La page **Accueil** affiche un aperçu des segments, des mesures et des données d’enrichissement (si configuré) après avoir terminé les phases de [mappage](map-entities.md), de [mise en correspondance](match-entities.md) et de [fusion](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Informations de la page d’accueil](media/home-page-insights.png "Informations de la page d’accueil")

Sous **Segments récents**, vous voyez des groupes de clients en fonction des attributs démographiques, comportementaux ou transactionnels que vous avez définis. La [création de segments](segments.md) vous aide à regrouper votre clientèle et à mieux cibler vos activités commerciales.

Les **mesures récentes** affichent des vignettes avec des [indicateurs de performance clés](measures.md) que vous avez définis. Par exemple, la probabilité moyenne de désabonnement d’un client ou les dépenses moyennes en ligne par client.

La section **Enrichissements récents** répertorie les résultats des cycles d’enrichissement récemment terminés. Les [enrichissements](enrichment-hub.md) ajoutent des informations sur votre clientèle. Par exemple, en comprenant les centres d’intérêts et les marques pour lesquels ils ont des affinités.

## <a name="switch-environments"></a>Changer d’environnements

Sélectionnez le contrôle **Environnement** dans le coin supérieur droit de la page pour changer d’environnement.

> [!div class="mx-imgBorder"] 
> ![Modifier l’environnement](media/home-page-environment-switcher.png "Modifier l’environnement")

Les administrateurs peuvent créer et gérer des [environnements multiples](manage-environments.md). La gestion de plusieurs environnements peut être utile si, par exemple, votre organisation opère à l’international et que vous devez séparer les données et les informations de différentes manières.

## <a name="next-step"></a>Étape suivante

Pour voir vos propres informations sur la page d’accueil, vous devez d’abord [ajouter des sources de données](data-sources.md) et [unifier](data-unification.md) vos données pour construire des profils clients.


[!INCLUDE[footer-include](../includes/footer-banner.md)]