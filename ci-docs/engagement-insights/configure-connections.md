---
title: Configurer les connexions
description: Comment configurer et gérer les connexions à la fonction Informations sur l’audience.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 6d794f6f4e4f351f46c58e03ffa5945d6a18cfe5
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650407"
---
# <a name="configure-connections"></a>Configurer les connexions

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La connexion des fonctions [Informations sur l’audience Dynamics 365 Customer Insights](../audience-insights/index.yml) et Informations sur l'engagement permet de voir les [rapports sur les données clients](profile-reports.md).

> [!IMPORTANT]
> L'environnement Audience Insights que vous prévoyez de connecter doit écrire les données dans le propre compte Azure Data Lake Storage Gen 2 d'un client. Les administrateurs d'Informations sur l’audience définissent cela dans les paramètres avancés lors de la [création d'un environnement](../audience-insights/get-started-paid.md).

## <a name="prerequisites"></a>Conditions préalables

- La personne qui établit la connexion dispose des autorisations [administrateur d'environnement](user-roles.md) dans Informations sur l’engagement.
- Le même administrateur d'environnement doit être l'administrateur du compte de stockage ou avoir accès aux détails du compte de stockage, tels que les clés partagées.

## <a name="set-up-the-connection-with-audience-insights"></a>Configurer la connexion avec Informations sur l’audience

En tant qu'[administrateur d'environnement](user-roles.md), vous pouvez configurer des connexions à partir de tous les environnements que vous administrez. Pour passer à un autre environnement, voir [Choisir l'environnement à configurer](manage-environments-workspaces.md#choose-an-environment-and-create-a-workspace).

1. Allez dans **Administrateur** > **Environnement** et sélectionnez **Connexions**.

1. S'il s'agit de votre première connexion, sélectionnez **Créer une connexion**. Pour créer plus de connexions, sélectionnez **Ajouter une connexion**.
   :::image type="content" source="media/create-connection.png" alt-text="Créer une nouvelle connexion à Customer Insights.":::

1. Fournissez les paramètres à votre fonction Informations sur l’audience Azure Data Lake Storage Gen2. Pour plus d'informations sur les comptes de stockage, voir [Créer et gérer des comptes de stockage](/azure/storage/blobs/data-lake-storage-quickstart-create-account).
   - **Compte de stockage ADLS gen2** : Indiquez le nom du compte de stockage. Par exemple, my-storage-account.
   - **Clé partagée** : La clé d'accès pour authentifier vos applications. Cette clé se trouve dans le portail Azure sous **Clés d'accès** dans les paramètres du compte de stockage.
   - **ID environnement Informations sur l’audience** : L'ID de l'environnement Informations sur l’audience. Vous pouvez trouver l'ID dans Informations sur l’audience, sous **Paramètres** > **À propos**.
   - **Nom du dossier de l'environnement Informations sur l’audience** : Le chemin du dossier vers l'environnement Informations sur l’audience dans le compte de stockage. Par exemple, `ci_xxxxxx-xxx-xxxxx`

1. Cliquez sur **Suivant**.

1. Les données de profil client contiennent souvent des informations client sensibles telles que l'âge, le sexe et les revenus. Seul l'administrateur de l'environnement qui configure la connexion a automatiquement a accès au rapport de profil client. Les autres membres ne peuvent pas voir le rapport sauf si l'accès est explicitement accordé.    
   Vous pouvez ajouter ou supprimer des membres ayant accès à ces données dans la zone **Connexions** des paramètres d'environnement.
 
1. Vérifiez les paramètres et sélectionnez **Terminé** pour créer la connexion. 

> [!NOTE]
> La mise à disposition des données dans les informations sur l’engagement peut prendre plusieurs heures. Vous pouvez vérifier si une connexion a été établie dans la zone **Connexions**.

Pour consulter le rapport sur les profils des clients, allez dans **Découvrir** > **Profils**. Pour plus d’informations, voir [Rapport de profil client](profile-reports.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]