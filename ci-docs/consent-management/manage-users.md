---
title: Gérer les utilisateurs dans la fonctionnalité de gestion des consentements
description: Tous les utilisateurs d’une organisation qui possède la gestion des consentements peuvent accéder au service. Les administrateurs ajoutent des utilisateurs et leur attribuent les autorisations requises dans Customer Insights.
ms.date: 04/27/2022
ms.subservice: consent-management
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ffc1010b6bc005c595c2083057d77c8dcf7e688f
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653457"
---
# <a name="manage-users-and-permissions"></a>Gérer les utilisateurs et les autorisations

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tous les administrateurs des insights d’audience ont accès à la capacité de gestion du consentement. Ils peuvent ajouter et supprimer d’autres utilisateurs et leur attribuer les autorisations requises.

## <a name="roles"></a>Rôles

- Lecteur
    - Est un rôle en lecture seule qui peut voir les données de consentement importées et leur analyse récapitulative associée sur la page d’accueil.

- Contributeur
    - Peut configurer l’importation des données de consentement.
    - Peut configurer les règles de consentement.

- Administrateur : 
    - Dispose de toutes les autorisations du rôle Contributeur.
    - Peut définir les paramètres du système.
    - Peut gérer les utilisateurs et les autorisations.
    - Le premier administrateur qui active la capacité de gestion du consentement dans Customer Insights obtient le rôle Administrateur (propriétaire). Cet utilisateur ne peut pas être supprimé du système.

## <a name="add-users"></a>Ajouter des utilisateurs

1. Dans le Centre de consentement (version préliminaire), accédez à **Administrateur** > **Autorisations**.
1. Sélectionnez **Ajouter des utilisateurs**
1. Dans le volet **Ajouter des utilisateurs**, choisissez le **Rôle** et les utilisateurs à ajouter. 
1. Sélectionnez **Autoriser l’accès**. 

## <a name="remove-users"></a>Supprimer des utilisateurs

1. Dans le Centre de consentement (version préliminaire), accédez à **Administrateur** > **Autorisations**.
1. Sélectionnez l’utilisateur que vous souhaitez supprimer de la liste.
1. Sélectionnez **Plus d’options (...)** et choisissez **Supprimer l’utilisateur**
1. Confirmez la suppression pour révoquer l’accès aux utilisateurs.

## <a name="change-roles"></a>Modifier les rôles

1. Dans le Centre de consentement (version préliminaire), accédez à **Administrateur** > **Autorisations**.
1. Sélectionnez l’utilisateur que vous souhaitez supprimer de la liste.
1. Sélectionnez **Plus d’options (...)** et choisissez **Supprimer l’utilisateur**
