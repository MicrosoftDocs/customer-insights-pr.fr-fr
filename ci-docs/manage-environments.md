---
title: Procédure pour gérer les environnements
description: Découvrez comment gérer les environnements Customer Insights existants en tant qu’administrateur.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: fc3b3f404cf0ac84c782778414494289c803babe
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081189"
---
# <a name="how-to-manage-environments"></a>Procédure pour gérer les environnements

Les administrateurs [créent](create-environment.md) et gérent les environnements. Ils peuvent modifier certains paramètres dans les environnements existants. L’entreprise, le type, la région, l’option de stockage et les paramètres Dataverse sont fixes après la création de l’environnement. Si vous souhaitez modifier ces paramètres, réinitialisez l’environnement ou créez un nouvel environnement.

## <a name="edit-an-existing-environment"></a>Modifier un environnement existant

Vous pouvez modifier certains détails des environnements existants.

1. Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.

1. Sélectionnez l’icône **Modifier**.

   :::image type="content" source="media/edit-environment.png" alt-text="Icône pour modifier les paramètres de l’environnement.":::

1. Dans la zone **Modifier l’environnement**, vous pouvez mettre à jour les paramètres de l’environnement.

Pour commencer avec un nouvel environnement, consultez [Créer un nouvel environnement](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Changer le propriétaire d’un environnement

Plusieurs utilisateurs peuvent disposer d’autorisations d’administrateur, mais un seul utilisateur est propriétaire d’un environnement. Par défaut, il s’agit de l’administrateur qui crée initialement un environnement. En tant qu’administrateur d’un environnement, vous pouvez attribuer la propriété à un autre utilisateur avec des autorisations d’administrateur.

1. Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.

1. Sélectionnez l’icône **Modifier**.

1. Dans la zone **Modifier l’environnement**, allez à l’étape **Informations de base**.

1. Dans le champ **Changer le propriétaire de l’environnement**, choisissez le nouveau propriétaire de l’environnement.  

1. Sélectionnez **Réviser et terminer**, puis **Mettre à jour** pour appliquer les changements.

## <a name="claim-ownership-of-an-environment"></a>Revendiquer la propriété d’un environnement

Si le compte d’utilisateur du propriétaire est supprimé ou suspendu, l’environnement n’aura pas de propriétaire. Chaque utilisateur administrateur peut revendiquer la propriété et devenir le nouveau propriétaire. Il peut continuer à être propriétaire de l’environnement ou [attribuer la propriété à un autre administrateur](#change-the-owner-of-an-environment).

Pour revendiquer la propriété, cliquez sur le bouton **Prendre possession** qui s’affiche en haut de chaque page dans Customer Insights lorsque le propriétaire d’origine a quitté l’organisation.

## <a name="reset-an-existing-environment-preview"></a>Réinitialiser un environnement existant (version préliminaire)

En tant que propriétaire d’un environnement, vous pouvez réinitialiser un environnement à un état vide si vous souhaitez supprimer toutes les configurations et les données ingérées.

1. Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.

1. Sélectionnez l’environnement à réinitialiser et sélectionnez les points de suspension verticaux (&vellip;).

1. Choisissez l’option **Réinitialiser**.

   :::image type="content" source="media/reset-environment.png" alt-text="Contrôle pour réinitialiser un environnement.":::

1. Choisissez si vous souhaitez réinitialiser tout l’environnement, tout sauf les sources de données ou tout ce qui est configuré en plus du profil client unifié.

1. Pour confirmer, entrez le nom de l’environnement et sélectionnez **Réinitialiser**.

## <a name="delete-an-existing-environment"></a>Supprimer un environnement existant

En tant que propriétaire d’un environnement, vous pouvez supprimer un environnement que vous administrez.

1. Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.

1. Sélectionnez l’environnement à réinitialiser et sélectionnez les points de suspension verticaux (&vellip;). 

1. Choisissez l’option **Supprimer**.

   :::image type="content" source="media/delete-environment.png" alt-text="Contrôle pour supprimer l’environnement.":::

1. Pour confirmer la suppression, sélectionnez le nom de l’environnement et sélectionnez **Supprimer**.

> [!IMPORTANT]
> La suppression d’un environnement n’entraîne pas la suppression de la connexion à un environnement Dataverse. Si vous prévoyez de connecter le même environnement Dataverse à un nouvel environnement Customer Insights à l’avenir, vous devez supprimer cette connexion. Découvrez comment [supprimer une connexion existante à un environnement Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
