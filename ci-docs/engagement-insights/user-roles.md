---
title: Rôles et autorisations
description: Vue d'ensemble des rôles et autorisations disponibles pour les membres de l'espace de travail.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 85e051c67bde6bfc6cd39553e463bd81752d0d73
ms.sourcegitcommit: adb9c43ddaba25e511535d78a4bcf8815f154a7b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6362461"
---
# <a name="roles-and-permissions"></a>Rôles et autorisations

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un espace de travail représente la manière dont vous stockez et gérez des événements et des rapports. Un membre est un utilisateur qui peut accéder à un espace de travail. Vous pouvez affecter des membres à votre espace de travail et définir leurs rôles et autorisations. Les rôles d'administrateur gèrent les espaces de travail et les environnements et configurent les informations d'engagement pour les autres utilisateurs. Les rôles de contributeur sont destinés aux analystes qui n'ont pas besoin de configurer les informations d'engagement mais souhaitent créer leurs propres rapports, entonnoirs ou segments.

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
