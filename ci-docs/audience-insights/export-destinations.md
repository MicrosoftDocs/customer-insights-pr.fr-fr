---
title: Exporter des données de Customer Insights
description: Gérez les exportations pour partager des données.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016611"
---
# <a name="exports-preview-overview"></a>Vue d’ensemble des exportations (version préliminaire)

La page **Exportations** affiche toutes les exportations configurées. Les exportations partagent des données spécifiques avec diverses applications. Elles peuvent inclure des profils ou entités client, des schémas et des détails de mappage. Chaque exportation nécessite une [connexion, configurée par un administrateur, pour gérer l’authentification et l’accès](connections.md).

Accédez à **Données** > **Exportations** pour afficher la page des exportations. Tous les rôles d’utilisateur ont accès pour afficher les exportations configurées. Utilisez le champ de recherche dans la barre de commandes pour rechercher des exportations par leur nom, nom de connexion ou type de connexion.

## <a name="set-up-a-new-export"></a>Configurer une nouvelle exportation

Pour configurer ou modifier une exportation, vous devez avoir des connexions disponibles. Les connexions dépendent de votre [rôle d’utilisateur](permissions.md) :
- Les administrateurs ont accès à toutes les connexions. Ils peuvent également créer de nouvelles connexions lors de la configuration d’une exportation.
- Les contributeurs peuvent avoir accès à des connexions spécifiques. Ils dépendent des administrateurs pour configurer et partager des connexions. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Les utilisateurs peuvent uniquement afficher les exportations existantes, mais pas les créer.

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation** pour créer une nouvelle destination d’exportation.

1. Dans le volet **Configurer l’exportation**, sélectionnez la connexion à utiliser. Les [Connexions](connections.md) sont gérées par les administrateurs. 

1. Fournissez les détails nécessaires et sélectionnez **Enregistrer** pour créer l’exportation.

### <a name="edit-an-export"></a>Modifier une exportation

1. Sélectionnez les points de suspension de la destination d’exportation que vous souhaitez modifier.

1. Sélectionnez **Modifier** dans le menu déroulant.

1. Modifiez les valeurs que vous souhaitez mettre à jour et sélectionnez **Enregistrer**.

## <a name="view-exports-and-export-details"></a>Afficher les exportations et les détails de l’exportation

Une fois les destinations d’exportation créées, elles sont répertoriées dans **Données** > **Exportations**. Tous les utilisateurs peuvent voir les données partagées et leur statut le plus récent.

1. Accédez à **Données** > **Exportations**.

1. Les utilisateurs sans autorisations de modification sélectionnent **Afficher** au lieu de **Modifier** pour voir les détails de l’exportation.

1. Ce volet latéral montre la configuration de cette exportation. Sans autorisations de modification, vous ne pouvez pas modifier les valeurs. Sélectionnez **Fermer** pour revenir à la page des exportations.

## <a name="run-exports-on-demand"></a>Exécuter des exportations à la demande

Une fois une exportation configurée, elle s’exécutera avec chaque [actualisation planifiée](system.md#schedule-tab) tant qu’une connexion active sera disponible.

Pour exporter des données sans attendre une actualisation planifiée, accédez à **Données** > **Exportations**. Deux options s’offrent à vous :

- Pour exécuter toutes les exportations, sélectionnez **Tout exécuter** dans la barre de commandes. 
- Pour exécuter une seule exportation, sélectionnez les points de suspension (...) d’un élément de liste, puis choisissez **Exécuter**.

## <a name="remove-an-export"></a>Supprimer une exportation

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez les points de suspension de l’exportation que vous souhaitez supprimer.

1. Sélectionnez **Supprimer** dans la liste déroulante.

1. Confirmez la suppression en sélectionnant **Supprimer** sur l’écran de confirmation.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
