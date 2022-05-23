---
title: Gérer les utilisateurs dans la fonctionnalité de gestion des consentements
description: Tous les utilisateurs d’une organisation qui possède la gestion des consentements peuvent accéder au service. Les administrateurs ajoutent des utilisateurs et leur attribuent les autorisations requises dans Customer Insights.
ms.date: 04/27/2022
ms.subservice: consent-management
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 32551b5bb47a0bb912ae458b37e22bb57b36eacc
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755667"
---
# <a name="manage-users-and-permissions"></a>Gérer les utilisateurs et les autorisations

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tous les administrateurs de Customer Insights ont accès à la capacité de gestion du consentement. Ils peuvent ajouter et supprimer d’autres utilisateurs et leur attribuer les autorisations requises.

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
