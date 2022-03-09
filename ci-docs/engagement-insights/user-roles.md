---
title: Rôles et autorisations
description: Vue d'ensemble des rôles et autorisations disponibles pour les membres de l'espace de travail.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ccc6a1b87b4cc28701e276b6e35432356e7647c4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227536"
---
# <a name="roles-and-permissions"></a>Rôles et autorisations

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un espace de travail est l’endroit où vous stockez et gérez les événements et les rapports. Pour plus d’informations, consultez [Créer un espace de travail et ajouter des membres](create-workspace.md). 

Un espace de travail peut inclure les rôles et autorisations suivants :

- Les rôles *Membre* sont des utilisateurs qui peuvent accéder à un espace de travail. Vous pouvez affecter des membres à votre espace de travail et définir leurs rôles et autorisations. 
- Les rôles *Administrateur* gèrent les espaces de travail et les environnements, et configurent les informations d’engagement pour les autres utilisateurs. 
- Les rôles *Contributeur* sont destinés aux analystes qui n’ont pas besoin de configurer des informations sur l’engagement, mais qui souhaitent créer leurs propres rapports, synthèses ou segments.

## <a name="permissions"></a>Autorisations
  
Le tableau suivant identifie les autorisations pour chaque rôle. 

| Autorisation | Administrateur de l’environnement | Administrateur de l’espace de travail | Contributeur à l’environnement | Contributeur de l’espace de travail | 
|--|--|--|--|--|
| Créer des environnements (le créateur devient automatiquement administrateur de l'environnement) | X* | X* | X* | X* |  
| Configurer l'environnement (membres de l'environnement, supprimer l'environnement) | X |  |  |  |  
| Créer des espaces de travail | X |  |  |  |  
| Configurer des espaces de travail (membres de l'espace de travail, supprimer l'espace de travail) | X | X |  |  |  
| Configurer des événements et des événements affinés | X | X | |  |  
| Afficher les événements de l'espace de travail et les événements affinés | X | X | |  |  
| Afficher les ressources de l'espace de travail (rapports, segments et métrique)| X | X | X | X |  
| Créer des rapports et des entonnoirs personnalisés | X | X | X | X |  
| Créer des mesures et des dimensions de base| X | X |  |  |  
| Créer des segments| X | X | X | X |  

*Peut uniquement créer des environnements d'essai en version préliminaire. 

## <a name="add-members"></a>Ajouter des membres

Vous pouvez ajouter et supprimer des membres des espaces de travail et des environnements. Pour plus d'informations, consultez [Environnements et espaces de travail](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
