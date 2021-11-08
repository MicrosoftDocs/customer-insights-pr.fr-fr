---
title: Commencez avec les comptes professionnels comme audience cible principale
description: Découvrez les comptes professionnels comme audience cible principale Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ac5ae950a44f7f32e3cb9fdc0ffad05b78fddef0
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673684"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>Travaillez avec des comptes d’entreprise dans les insights d’audience

La capacité d'insights d'audience dans Dynamics 365 Customer Insights vous permet de configurer votre environnement pour différentes audiences cibles principales : les clients particuliers (B2C) et les comptes professionnels (B2B). Dans les scénarios B2C, les données sont centrées sur les individus. Pour le B2B, les principales audiences cibles sont les comptes - organisations ou entreprises - et les contacts. Cet article vous aide à vous familiariser avec un environnement pour les comptes d’entreprise. Il répertorie les différences pour les zones de fonctionnalités dans les informations d’audience, en fonction de votre environnement. Pour plus d’informations sur les différences, consultez la documentation des zones de fonctionnalités. 

## <a name="create-an-environment-for-business-accounts"></a>Créer un environnement pour les comptes professionnels

Les administrateurs peuvent [créer un environnement dans une organisation existante](create-environment.md). Une étape du processus de création d’un nouvel environnement demande aux administrateurs l’audience cible principale de l’environnement. S’il s’agit de la configuration initiale des informations d’audience après l’achat d’une licence, une expérience guidée aide à la création du premier environnement.

Vous pouvez alors [ingérer des données](data-sources.md) pour les comptes professionnels et les contacts associés en tant que sources de données de toutes les sources prises en charge.

Après avoir unifié les données, [spécifiez les hiérarchies de comptes](relationships.md#set-up-account-hierarchies) dans le cadre de la configuration de la relation. Vous pouvez également [configurer les mappages sémantiques](semantic-mappings.md) pour connecter les entités de contact et de compte. 

## <a name="switch-between-primary-target-audience"></a>Basculer entre l’audience cible principale

Si votre organisation gère des environnements pour des clients individuels et des comptes professionnels, vous pouvez utiliser le sélecteur dans le volet de gauche pour choisir l’audience cible principale.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Sélecteur pour changer l’audience cible principale entre les clients individuels et les comptes professionnels.":::

## <a name="supported-feature-areas"></a>Fonctionnalités prises en charge

- [Activités](activities.md) : Prise en charge des comptes et des contacts associés pour créer des activités et les afficher dans une chronologie.
- [Relations](relationships.md) : L’assistant d’activité permet de créer des relations entre les entités afin que la vue du compte puisse afficher toutes les activités des contacts. Les contacts peuvent accéder au détail pour voir la vue des contacts et les hiérarchies peuvent être utilisées pour les agrégations d’activités de compte.
- [Les mesures](measures.md) : prend en charge les mesures créées à partir du générateur de mesures avec un seul calcul. Un paramètre facultatif permet le cumul des sous-comptes lors de la création de mesures.
- [Segments](segments.md) : prend en charge les segments créés à partir de zéro avec le générateur de segments. De nouveaux opérateurs permettent d’intégrer la hiérarchie des comptes lors de la création de segments.
- [Ingestion de données](data-sources.md) : Toutes les fonctionnalités de cette zone sont les mêmes pour les comptes professionnels et les clients particuliers.
- [Unification des données](data-unification.md) : Toutes les fonctionnalités de cette zone sont les mêmes pour les comptes professionnels et les clients particuliers.
- [Enrichissement](enrichment-hub.md) : Certains types d’enrichissement sont disponibles uniquement pour les scénarios de clients individuels, tandis que d’autres sont exclusivement disponibles pour les comptes professionnels.
- [Prédictions et modèles prêts à l’emploi](predictions-overview.md) : La prédiction d’attrition transactionnelle contient des étapes supplémentaires pour les comptes d’entreprise. Les autres prédictions ne sont disponibles que pour les clients individuels.
- [Activation et exportation](export-destinations.md) : Les exportations sont disponibles pour les comptes professionnels et les clients particuliers. Certaines exportations nécessitent une configuration supplémentaire et des informations de contact projetées dans les segments sous-jacents pour être valides pour les comptes professionnels.
- [Paramètres systèmes](system.md) et [gestion des utilisateurs](permissions.md) : Toutes les fonctionnalités de cette zone sont les mêmes pour les comptes professionnels et les clients particuliers.

