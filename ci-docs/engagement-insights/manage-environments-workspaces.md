---
title: Gérer les espaces de travail et les environnements
description: Comment créer, renommer et supprimer des espaces de travail et des environnements.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486032"
---
# <a name="manage-environments-and-workspaces"></a>Gérer les environnements et les espaces de travail

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Présentation

Un espace de travail est un espace pour stocker et gérer des événements et des rapports. C'est là que vous pouvez voir l'activité des utilisateurs en temps réel. Lorsque vous créez un espace de travail, vous devez sélectionner le type de données à y transférer. Actuellement, les données web et les applications mobiles sont prises en charge.

Un environnement est un espace dans lequel vous gérez vos espaces de travail et vos connexions. La façon dont vous utilisez les environnements dépend de votre organisation et de votre cas d'utilisation. Par exemple, vous pouvez créer :

-   Un seul environnement.
-   Des environnements distincts pour les tests et la production.
-   Des environnements distincts pour des équipes ou des services spécifiques de votre organisation qui contiennent des événements pertinents pour chaque audience.
-   Des environnements distincts pour différentes succursales mondiales de votre société.
-   Connexions à la fonction Informations sur l’audience de Customer Insights.

## <a name="choose-an-environment-and-create-a-workspace"></a>Choisir un environnement et créer un espace de travail 

Chaque espace de travail doit être dans un environnement. Vous pouvez sélectionner un environnement préexistant ou en créer un nouveau lorsque vous créez un espace de travail. Vous pouvez ensuite choisir d'ajouter des membres de l'espace de travail et commencer à collecter des données.

**Pour créer votre premier espace de travail**

1. Dans Informations sur l’engagement, sélectionnez **Nouveau** depuis le sélecteur d'espace de travail. 

   :::image type="content" source="media/New-workspace.png" alt-text="Sélecteur d'espace de travail de la page Customer Insights.":::

1. Choisissez un environnement dans la liste ou sélectionnez **Créer un environnement**.

1. Tapez un nom dans le champ **Nom de l’espace de travail**. 

1. Sélectionnez le type d’environnement que vous souhaitez créer, selon que vous souhaitez mesurer ce qui se passe sur un site web ou dans une application mobile. 

1. Vous pouvez ajouter des membres et attribuer leur niveau d'autorisation à partir de la liste **Rôle**. Puis, sélectionnez **Terminer** pour créer l'espace de travail ou **Suivant** pour installer le code. 

1. Installez l'extrait de code pour commencer à recevoir des données, puis sélectionnez **Terminé**. 

## <a name="manage-a-workspace"></a>Gérer un espace de travail

Vous pouvez gérer plusieurs espaces de travail simultanément dans un environnement. Votre [rôle](user-roles.md) détermine comment vous pouvez y travailler. 

 - Vous devez être un administrateur d’environnement ou un administrateur d’espace de travail pour gérer l’espace de travail.
 - En tant qu’administrateur d’espace de travail, vous pouvez renommer les espaces de travail existants ou les supprimer. 

### <a name="edit-a-workspace-name"></a>Modifier le nom d'un espace de travail

1. Allez dans **Administrateur** > **Espace de travail** et sélectionnez **Paramètres**.

1. Saisissez un nouveau nom dans la zone **Nom de l’espace de travail**.

1. Sélectionnez **Enregistrer** pour appliquer vos modifications.

### <a name="delete-a-workspace"></a>Supprimer un espace de travail

La suppression d'un espace de travail va supprimer définitivement la totalité de ses contenus, données, paramètres et autorisations. Cette opération ne peut pas être annulée.

1. Allez dans **Administrateur** > **Espace de travail** et sélectionnez **Paramètres**.

1. Sélectionnez **Supprimer l'espace de travail**. 

1. Dans la boîte de dialogue **Supprimer l’espace de travail**, entrez **CONFIRMER LA SUPPRESSION**. 

1. Sélectionnez **Supprimer** pour supprimer définitivement l’espace de travail.

### <a name="manage-workspace-members"></a>Gérer les membres de l’espace de travail

1. Allez dans **Administrateur** > **Espace de travail** et sélectionnez **Membres**.

1. Sélectionnez **Ajouter des membres** pour donner accès et [attribuer des rôles](user-roles.md). Actuellement, seul l'**Administrateur de l'espace de travail** est disponible.

1. Sélectionnez **Ajouter des membres** pour les ajouter à votre espace de travail.

## <a name="manage-an-environment"></a>Gérer un environnement

En tant qu'administrateur d'environnement, vous pouvez accéder à un environnement à partir du volet de navigation de gauche. Vous pouvez configurer les paramètres de l’environnement, d’autres administrateurs de l’environnement et les espaces de travail. Sélectionnez des onglets pour vous déplacer entre différentes zones du centre d'administration.

:::image type="content" source="media/New-environment.png" alt-text="Centre d'administration de l'environnement.":::

### <a name="create-an-environment"></a>Créer un environnement

1. Dans le sélecteur d'espace de travail, sélectionnez **+Nouveau**.

1. Dans l'expérience guidée, ouvrez le menu déroulant **Environnement** et sélectionnez **Créer un nouvel environnement**. 

1. Spécifiez un **Nom d'environnement**.

   :::image type="content" source="media/create-environment.png" alt-text="Étape de l'expérience guidée pour spécifier les détails de l'environnement.":::

1. Choisissez la **Région** et sélectionnez **Suivant**. 

1. Indiquez un nom d'espace de travail et choisissez le type d'espace de travail que vous souhaitez créer. 

1.  Vous pouvez éventuellement ajouter des membres et copier l'extrait de code pour terminer le processus de création.

### <a name="rename-an-environment"></a>Renommer un environnement

1. Allez dans **Administrateur** > **Environnement** et sélectionnez **Paramètres**.

1. Mettez à jour le **Nom de l'environnement** et cliquez sur **Enregistrer** pour appliquer vos modifications.

### <a name="manage-environment-members"></a>Gérer les membres de l’environnement

1. Allez dans **Administrateur** > **Environnement** et sélectionnez **Membres**.

1. Sélectionnez **Ajouter des membres** pour mettre à jour les membres et [attribuer des rôles](user-roles.md). Actuellement, seul l'**Administrateur de l’environnement** est disponible.

1. Sélectionnez **Ajouter des membres** pour les ajouter à votre environnement.

### <a name="delete-an-environment"></a>Supprimer un environnement

Les administrateurs d'environnement peuvent supprimer des environnements. Avant de pouvoir supprimer un environnement, vous devez supprimer tous les espaces de travail qu'il contient.

1. Allez dans **Administrateur** > **Environnement** et sélectionnez **Paramètres**.

1. Sélectionnez **Supprimer l'environnement**. 

1. Dans la boîte de dialogue **Supprimer l’espace de travail**, entrez **CONFIRMER LA SUPPRESSION**. 

1. Sélectionnez **Supprimer** pour supprimer définitivement l'environnement.

## <a name="manage-connections"></a>Gérer des connexions

L'établissement de connexions à Informations sur l’audience vous permet d'afficher des rapports dans Informations sur l’engagement basés sur des profils clients unifiés. 

Pour plus d’informations, voir [Créer un lien entre les informations sur l’audience et les informations sur l’engagement](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Gérer les données personnelles

Pour protéger les données personnelles de vos clients, vous pouvez supprimer ou exporter les données identifiables de l'utilisateur final.

Pour plus d’informations, consultez [Supprimer et exporter des données liées aux événements contenant des informations personnelles](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
