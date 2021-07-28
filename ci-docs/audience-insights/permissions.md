---
title: Gérer les autorisations de l’utilisateur
description: En savoir plus sur les autorisations et les rôles d’utilisateur.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760370"
---
# <a name="user-permissions"></a>Autorisations de l’utilisateur

La page **Autorisations** est l’endroit où vous définirez les rôles et les autorisations pour utiliser les informations sur l’audience.

Vous devez disposer des autorisations d’administration pour voir la page. Pour accéder à la page des autorisations dans les informations sur l’audience, accédez à **Administration** > **Autorisations**.

Il existe trois types de rôles :

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
- Exécutez les sections *Unification des données* (**Mapper**, **Mettre en correspondance** et **Fusionner**) qui résultent en l’entité de profil client unifié.
- Définissez les **Relations** et **Activités**.
- Créez des segments à l’aide de la page **Segments**.
- Créez les mesures à l’aide de la page **Mesures**.
- Gérez la configuration et enrichissez les profils clients à partir de la page **Enrichissement** (pour les enrichissements propriétaires uniquement).
- Gérez et créez des exportations basées sur les connexions partagées avec les contributeurs. [En savoir plus sur la manière dont les administrateurs autorisent les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="administrator"></a>Administrateur

- Toutes ces autorisations sont accessibles au Collaborateur.
- Modifiez les paramètres de la page **Système**, notamment la langue, et actualisez les planifications de vos processus système.
- Affichez et ajoutez des autorisations à l’aide de la page **Autorisations**.
- Définissez les champs de recherche et de filtre pour la page Clients avec la page **Index Rechercher et Filtrer** (accessible via la page **Clients**).
- Gérez les connexions et autorisez-les pour d’autres rôles d’utilisateur sur la page **Connexions**.
- Gérez la configuration et enrichissez les profils clients à partir de la page **Enrichissement** (pour tous les enrichissements).
- Gérez et créez des exportations sur la page **Exportations**.
- Installez et utilisez le **Complément de carte client**.
- Ajoutez et utilisez le **connecteur Power Apps**.
- Activez l’utilisation des [API de Customer Insights](apis.md).

## <a name="assign-roles-and-permissions"></a>Attribuer des autorisations et des rôles

1. Dans les informations sur l’audience, accédez à **Administration** > **Autorisations**.

1. Sélectionnez **Ajouter des utilisateurs** pour ouvrir le volet **Ajouter/modifier des autorisations**.

1. Utilisez le champ **Rechercher** pour trouver l’utilisateur ou groupe Azure Active Directory dont vous souhaitez modifier les autorisations. Sélectionnez un **Rôle** à attribuer à cet utilisateur ou à ce groupe.

1. Sélectionnez **Enregistrer**. L’environnement actuel sera automatiquement partagé avec l’utilisateur ou les membres du groupe dont vous avez modifié les autorisations. Les utilisateurs peuvent accéder à l’application Customer Insights et travailler en fonction du rôle spécifié.

## <a name="view-current-permissions"></a>Afficher les autorisations en cours

Dans les informations sur l’audience, accédez à **Administration** > **Autorisations** pour voir quelles attributions de rôle sont actuellement actives.

- La colonne **Type** spécifie s’il s’agit d’un utilisateur unique, d’un groupe ou d’une application. Le système prend en charge les utilisateurs individuels et les groupes.
- Les rôles sont spécifiées dans la colonne **Rôle**.
- Sélectionnez un titre de colonne pour trier les résultats selon la valeur de cette colonne.
- Utilisez le champ **Rechercher** en haut de la page pour localiser des utilisateurs spécifiques.


[!INCLUDE[footer-include](../includes/footer-banner.md)]