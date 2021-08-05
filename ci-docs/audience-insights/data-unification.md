---
title: Unification des données
description: Découvrez comment unifier des données ingérées.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: cb96763d4b5b67b5110db757eb7d160c294d6fc3
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539066"
---
# <a name="data-unification-overview"></a>Vue d’ensemble de l’unification des données

Une fois la [configuration des sources de données](data-sources.md) terminée, vous pouvez unifier les données. L’unification des données comprend trois étapes : **Mapper**, **Mettre en correspondance** et **Fusionner**.

Le processus d’unification des données vous permet d’unifier des sources de données autrefois disparates en un seul maître jeu de données qui fournit une vue unifiée de vos clients. Les étapes d’unification sont obligatoires et exécutées dans l’ordre suivant :

1. [Mappage](map-entities.md)
2. [Mise en correspondance](match-entities.md)
3. [Fusion](merge-entities.md)

Après avoir terminé l’unification des données, vous pouvez éventuellement

- [configurer les relations entre des entités](relationships.md) pour créer des segments sophistiqués
- [enrichir vos données](enrichment-hub.md) pour obtenir un éventail plus large d’informations sur vos clients
- [définir des activités](activities.md) à partir de certains des attributs ingérés


[!INCLUDE[footer-include](../includes/footer-banner.md)]