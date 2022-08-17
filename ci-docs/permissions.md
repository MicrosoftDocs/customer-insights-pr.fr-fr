---
title: Attribuer des autorisations aux utilisateurs
description: En savoir plus sur les autorisations et les rôles d’utilisateur.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245416"
---
# <a name="assign-user-permissions"></a>Attribuer des autorisations aux utilisateurs

L’accès à Customer Insights est limité aux utilisateurs de votre organisation ajoutés à l’application par un administrateur. Un administrateur peut ajouter, modifier ou supprimer des utilisateurs. Un utilisateur peut être un utilisateur unique, un groupe ou une application. Il existe trois types de rôles qu’un utilisateur peut avoir :

## <a name="viewer"></a>Observateur

- Explorez les informations et les segments sur les pages **Accueil** et **Segments**.
- Recherchez et filtrez des profils client via la page **Clients**. Les champs doivent pouvoir faire l’objet d’une recherche.
- Affichez et explorez la page **Enrichissement**.
- Explorez et exportez les entités avec la page **Entités**.
- Affichez le statut des processus système à l’aide de la page **Système**.
- Affichez les exportations dans la page **Exportations**.
- Installez et utilisez le tableau de bord **Power BI Customer Insights**.

## <a name="contributor"></a>Contributeur

- Toutes ces autorisations sont accessibles à la Visionneuse.
- Chargez et transformez des données à l’aide de la page **Sources de données**.
- Renseignez la section **Unification des données** qui se traduit par l’entité de profil client unifié.
- Définissez les **Relations** et **Activités**.
- Créez des segments à l’aide de la page **Segments**.
- Créez les mesures à l’aide de la page **Mesures**.
- Gérez la configuration et enrichissez les profils clients à partir de la page **Enrichissement** (pour les enrichissements propriétaires uniquement).
- Gérez et créez des exportations basées sur les [connexions partagées avec les contributeurs](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Admin

- Toutes ces autorisations sont accessibles au Collaborateur.
- Modifiez les paramètres de la page **Système**, notamment la langue, actualisez les planifications de vos processus système et exportez vos journaux de diagnostic.
- Modifiez les paramètres sur la page **Sécurité**, y compris les utilisateurs, les clés API, les liens privés et le coffre de clés.
- Définissez les champs de recherche et de filtre pour la page Clients avec la page **Index Rechercher et Filtrer** (accessible via la page **Clients**).
- Gérez les connexions et autorisez-les pour d’autres rôles d’utilisateur sur la page **Connexions**.
- Gérez la configuration et enrichissez les profils clients à partir de la page **Enrichissement** (pour tous les enrichissements).
- Gérez et créez des exportations sur la page **Exportations**.
- Installez et utilisez le **Complément de carte client**.
- Ajoutez et utilisez le **connecteur Power Apps**.
- Activez l’utilisation des [API de Customer Insights](apis.md).
- [Attribuer la propriété de l’environnement](manage-environments.md#change-the-owner-of-an-environment) à un autre administrateur.

## <a name="admin-owner"></a>Administrateur (propriétaire)

- Toutes les autorisations disponibles pour l’administrateur.
- [Réinitialisez et supprimez](manage-environments.md#reset-an-existing-environment-preview) l’environnement.

## <a name="add-users"></a>Ajouter des utilisateurs

1. Accédez à **Administrateur** > **Sécurité** et sélectionnez l’onglet **Utilisateurs**.

1. Sélectionnez **Ajouter des utilisateurs** pour ouvrir le volet **Ajouter/modifier des autorisations**.

1. Utilisez le champ **Rechercher** pour trouver l’utilisateur ou groupe Azure Active Directory que vous souhaitez ajouter. Sélectionnez un **Rôle** à attribuer à cet utilisateur ou à ce groupe.

1. Cliquez sur **Enregistrer**. L’environnement actuel est automatiquement partagé avec l’utilisateur ou les membres du groupe. Les utilisateurs peuvent accéder à l’application Customer Insights et travailler en fonction du rôle spécifié.

## <a name="view-current-permissions"></a>Afficher les autorisations en cours

Accédez à **Administrateur** > **Sécurité** et sélectionnez l'onglet **Utilisateurs** pour afficher la liste des utilisateurs actifs et leurs affectations. Vous pouvez trier la liste des utilisateurs par colonne ou utiliser la zone de recherche pour trouver un utilisateur spécifique.

## <a name="manage-current-users"></a>Gérer les utilisateurs actuels

Accédez à **Administrateur** > **Sécurité** et sélectionnez l’onglet **Utilisateurs**. Vous pouvez trier la liste des utilisateurs par colonne ou utiliser la zone de recherche pour trouver l’utilisateur que vous souhaitez gérer.

Sélectionnez un utilisateur pour afficher les actions disponibles.

- **Modifier** pour modifier le rôle de l’utilisateur dans Customer Insights. Sélectionnez **Enregistrer** pour confirmer la modification.
- **Supprimer** pour supprimer l’accès de l’utilisateur à Customer Insights. Sélectionnez **Supprimer** pour confirmer la suppression.

[!INCLUDE [footer-include](includes/footer-banner.md)]
