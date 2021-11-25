---
title: Gérer les espaces de travail et les environnements
description: Comment créer, renommer et supprimer des espaces de travail et des environnements.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 09cb3ddf0f8b4507b7eae6668ea3dad08cfcea29
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673787"
---
# <a name="manage-environments-and-workspaces"></a>Gérer les environnements et les espaces de travail

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Résumé

Cette rubrique explique comment gérer les espaces de travail et les environnements une fois qu’ils ont été créés. 

- Un *espace de travail* est un espace pour stocker et gérer des événements et des rapports. C'est là que vous pouvez voir l'activité des utilisateurs en temps réel. Lorsque vous créez un espace de travail, vous devez sélectionner le type de données à y transférer. Actuellement, les données web et les applications mobiles sont prises en charge. Pour plus d'informations, consultez [Créer un nouvel espace de travail et ajouter des membres](create-workspace.md).

- Un *environnement* est un espace dans lequel vous gérez vos espaces de travail et vos connexions. Pour plus d’informations, consultez [Créer un environnement](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Gérer un espace de travail existant

Vous pouvez gérer plusieurs espaces de travail simultanément dans un environnement. Votre [rôle](user-roles.md) détermine comment vous pouvez y travailler. 

 - Vous devez être un administrateur d’environnement ou un administrateur d’espace de travail pour gérer l’espace de travail.
 - En tant qu’administrateur d’espace de travail, vous pouvez renommer les espaces de travail existants ou les supprimer. 

:::image type="content" source="media/workspace-edit.png" alt-text="Centre d’administration des espaces de travail.":::

### <a name="edit-a-workspace-name"></a>Modifier le nom d'un espace de travail

1. Allez dans **Administrateur** > **Espace de travail** et sélectionnez **Paramètres**.

1. Saisissez un nouveau nom dans la zone **Nom de l’espace de travail**.

1. Sélectionnez **Enregistrer** pour appliquer vos modifications.

### <a name="delete-a-workspace"></a>Supprimer un espace de travail

La suppression de l’espace de travail supprime définitivement la totalité de ses contenus, données, paramètres et autorisations. Cette opération ne peut pas être annulée.

1. Allez dans **Administrateur** > **Espace de travail** et sélectionnez **Paramètres**.

1. Sélectionnez **Supprimer l'espace de travail**. 

1. Dans le dialogue **Supprimer l’espace de travail**, entrez **CONFIRMER LA SUPPRESSION** en majuscules. 

1. Sélectionnez **Supprimer** pour supprimer définitivement l’espace de travail.

### <a name="manage-workspace-members"></a>Gérer les membres de l’espace de travail

1. Allez dans **Administrateur** > **Espace de travail** et sélectionnez **Membres**.

1. Sélectionnez **Ajouter des membres** pour donner accès et [attribuer des rôles](user-roles.md). Actuellement, seul l'**Administrateur de l'espace de travail** est disponible.

1. Sélectionnez **Ajouter des membres** pour les ajouter à votre espace de travail.

## <a name="manage-an-existing-environment"></a>Gérer un environnement existant

En tant qu’administrateur d’environnement, vous pouvez accéder à un environnement à partir du volet de navigation de gauche. Vous pouvez configurer les paramètres de l’environnement, d’autres administrateurs de l’environnement et les espaces de travail. Sélectionnez des onglets pour vous déplacer entre différentes zones du centre d'administration.

:::image type="content" source="media/environment-edit.png" alt-text="Centre d'administration de l'environnement.":::

### <a name="edit-an-environment-name"></a>Modifier un nom d'environnement

1. Allez dans **Administrateur** > **Environnement** et sélectionnez **Paramètres**.

1. Mettez à jour le **Nom de l'environnement** et cliquez sur **Enregistrer** pour appliquer vos modifications.

### <a name="delete-an-environment"></a>Supprimer un environnement

Les administrateurs d'environnement peuvent supprimer des environnements. Avant de pouvoir supprimer un environnement, vous devez supprimer tous les espaces de travail qu'il contient.

1. Allez dans **Administrateur** > **Environnement** et sélectionnez **Paramètres**.

1. Sélectionnez **Supprimer l'environnement**. 

1. Dans le dialogue **Supprimer l’espace de travail**, entrez **CONFIRMER LA SUPPRESSION** en majuscules. 

1. Sélectionnez **Supprimer** pour supprimer définitivement l'environnement.

### <a name="manage-environment-members"></a>Gérer les membres de l’environnement

1. Allez dans **Administrateur** > **Environnement** et sélectionnez **Membres**.

1. Sélectionnez **Ajouter des membres** pour mettre à jour les membres et [attribuer des rôles](user-roles.md). Actuellement, seul l'**Administrateur de l’environnement** est disponible.

1. Sélectionnez **Ajouter des membres** pour les ajouter à votre environnement.

## <a name="manage-connections"></a>Gérer des connexions

L'établissement de connexions à Informations sur l’audience vous permet d'afficher des rapports dans Informations sur l’engagement basés sur des profils clients unifiés. 

Pour plus d’informations, voir [Créer un lien entre les informations sur l’audience et les informations sur l’engagement](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Gérer les données personnelles

Pour protéger les données personnelles de vos clients, vous pouvez supprimer ou exporter les données identifiables de l'utilisateur final.

Pour plus d’informations, consultez [Supprimer et exporter des données liées aux événements contenant des informations personnelles](../dsr-rights-requests.md#deleting-and-exporting-event-data-containing-end-user-identifiable-information).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
