---
title: Unification des données
description: Découvrez comment unifier des données ingérées.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405644"
---
# <a name="data-unification"></a>Unification des données

Une fois la [configuration des sources de données](data-sources.md) terminée, vous pouvez unifier les données. L'unification des données comprend trois étapes : **Mapper**, **Mettre en correspondance** et **Fusionner**.

Le processus d'unification des données vous permet d'unifier des sources de données autrefois disparates en un seul maître jeu de données qui fournit une vue unifiée de vos clients. Les étapes d'unification sont obligatoires et exécutées dans l'ordre suivant :

1. [Mappage](map-entities.md)
2. [Mise en correspondance](match-entities.md)
3. [Fusion](merge-entities.md)

Après avoir terminé l'unification des données, vous pouvez éventuellement

- [configurer les relations entre des entités](relationships.md) pour créer des segments sophistiqués
- [enrichir vos données](enrichment-hub.md) pour obtenir un éventail plus large d'informations sur vos clients
- [définir des activités](activities.md) à partir de certains des attributs ingérés
