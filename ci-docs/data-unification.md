---
title: Vue d’ensemble de l’unification des données
description: Suivez le processus d’unification des données avec vos données pour créer un seul jeu de données des profils client unifiés.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 766e688cb80c50a0d620943f87b76eb84a2fb89a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139484"
---
# <a name="data-unification-overview"></a>Vue d’ensemble de l’unification des données

Une fois la [configuration des sources de données](data-sources.md) terminée, vous pouvez unifier les données. L’unification des données vous permet d’unifier des sources de données qui étaient auparavant disparates en un seul jeu de données principal qui en fournit une vue unifiée. Pour les clients particuliers (B2C) où les données sont centrées sur les individus, l’unification fournit une vue unifiée de vos clients. Pour les comptes professionnels (B2B) où les données sont centrées sur les comptes, l’unification fournit une vue unifiée de vos comptes.

Les données peuvent être unifiées sur une ou plusieurs entités. L’unification est effectuée dans l’ordre suivant :

1. [Champs sources](map-entities.md) (précédemment appelé Mapper) : à l’étape des champs source, sélectionnez les entités et les champs à inclure dans le processus d’unification. Mappez les champs à un type sémantique commun qui décrit l’objectif du champ.

1. [Enregistrements en double](remove-duplicates.md) (qui faisait auparavant partie de Mapper) : à l’étape des enregistrements en double, vous pouvez éventuellement définir des règles pour supprimer les enregistrements client en double dans chaque entité.

1. [Conditions de correspondance](match-entities.md) (précédemment appelé Mapper) : à l’étape des conditions de correspondance, définissez les règles qui correspondent aux enregistrements client entre les entités. Lorsqu’un client est trouvé dans deux entités ou plus, un seul enregistrement consolidé est créé avec toutes les colonnes et les données de chaque entité.

1. [Champs client unifiés](merge-entities.md) (précédemment appelé Fusionner) : à l’étape des champs client unifiés, déterminez les champs source à inclure, exclure ou fusionner dans un profil client unifié.  

1. [Vérifiez](review-unification.md) et créez le profil unifié.

Après avoir terminé l’unification des données, vous pouvez éventuellement :

- [configurer les relations entre les entités](relationships.md) pour créer des segments sophistiqués ;
- [enrichir vos données](enrichment-hub.md) pour obtenir un éventail plus large d’informations sur vos clients :
- [définir des activités](activities.md) à partir de certains des attributs ingérés ;
- [créer des mesures](measures.md) pour mieux comprendre les comportements des clients et les performances de l’entreprise.

[!INCLUDE [footer-include](includes/footer-banner.md)]
