---
title: Utiliser des comptes professionnels
description: Découvrez les comptes professionnels comme audience cible principale dans Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: abb77a720ab737520a905b0c93b65573e669109f
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303913"
---
# <a name="work-with-business-accounts"></a>Utiliser des comptes professionnels

Dynamics 365 Customer Insights vous permet de configurer votre environnement pour différentes audiences cibles principales : les clients particuliers (B2C) et les comptes professionnels (B2B). Dans les scénarios B2C, les données sont centrées sur les individus. Pour le B2B, les principales audiences cibles sont les comptes - organisations ou entreprises - et les contacts. Cet article vous aide à vous familiariser avec un environnement pour les comptes d’entreprise. Il répertorie les différences pour les zones de fonctionnalités dans Customer Insights, en fonction de votre environnement. Pour plus d’informations sur les différences, consultez la documentation des zones de fonctionnalités. 

## <a name="create-an-environment-for-business-accounts"></a>Créer un environnement pour les comptes professionnels

Les administrateurs peuvent [créer un environnement dans une organisation existante](create-environment.md). Une étape du processus de création d’un nouvel environnement demande aux administrateurs l’audience cible principale de l’environnement. S’il s’agit de la configuration initiale après l’achat d’une licence, une expérience guidée aide à la création du premier environnement.

Vous pouvez alors [ingérer des données](data-sources.md) pour les comptes professionnels et les contacts associés en tant que sources de données de toutes les sources prises en charge.

 [Unifier](data-unification.md) vos données de compte suivies de vos données de contact pour connecter les entités de contact et de compte.

## <a name="switch-between-primary-target-audience"></a>Basculer entre l’audience cible principale

Si votre organisation gère des environnements pour des clients individuels et des comptes professionnels, vous pouvez utiliser le sélecteur dans le volet de gauche pour choisir l’audience cible principale.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Sélecteur pour changer l’audience cible principale entre les clients individuels et les comptes professionnels.":::

## <a name="supported-feature-areas"></a>Fonctionnalités prises en charge

- [Activités](activities.md) : Prise en charge des comptes et des contacts associés pour créer des activités et les afficher dans une chronologie.
- [Relations](relationships.md) : L’assistant d’activité permet de créer des relations entre les entités afin que la vue du compte puisse afficher toutes les activités des contacts. Les contacts peuvent accéder au détail pour voir la vue des contacts et les hiérarchies peuvent être utilisées pour les agrégations d’activités de compte.
- [Les mesures](measures.md) : prend en charge les mesures créées à partir du générateur de mesures avec un seul calcul. Un paramètre facultatif permet le cumul des sous-comptes lors de la création de mesures.
- [Segments](segments.md) : prend en charge les segments créés à partir de zéro avec le générateur de segments. Les segments peuvent être basés sur des comptes ou des contacts.
- [Ingestion de données](data-sources.md) : Toutes les fonctionnalités de cette zone sont les mêmes pour les comptes professionnels et les clients particuliers.
- L’unification des données B-to-B est très similaire à l’unification des données B-to-C mais comporte une étape supplémentaire pour unifier les contacts après l’unification du compte. Consultez [Comptes d’entreprise (B-to-B)](data-unification.md).
- [Enrichissement](enrichment-hub.md) : Certains types d’enrichissement sont disponibles uniquement pour les scénarios de clients individuels, tandis que d’autres sont exclusivement disponibles pour les comptes professionnels.
- [Prédictions et modèles prêts à l’emploi](predictions-overview.md) : La prédiction d’attrition transactionnelle contient des étapes supplémentaires pour les comptes d’entreprise. Les autres prédictions ne sont disponibles que pour les clients individuels.
- [Activation et exportation](export-destinations.md) : Les exportations sont disponibles pour les comptes professionnels et les clients particuliers. Certaines exportations nécessitent une configuration supplémentaire et des informations de contact projetées dans les segments sous-jacents pour être valides pour les comptes professionnels.
- [Paramètres systèmes](system.md) et [gestion des utilisateurs](permissions.md) : Toutes les fonctionnalités de cette zone sont les mêmes pour les comptes professionnels et les clients particuliers.

[!INCLUDE [footer-include](includes/footer-banner.md)]
