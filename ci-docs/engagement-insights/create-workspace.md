---
title: Créer un espace de travail
description: Le but d’un espace de travail et comment en créer un nouveau.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 816f948331a06794c15000eb779f93cc7fdda202
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645307"
---
# <a name="create-a-new-workspace-and-add-members"></a>Créer un espace de travail d’application et ajouter des membres

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un espace de travail vous permet de visualiser l'activité des utilisateurs en temps réel pour mieux comprendre votre audience. C'est là que vous stockez et gérez les événements et les rapports.

Lorsque vous créez un espace de travail, vous devez sélectionner le type de données sur lequel vous souhaitez vous concentrer. Vous pouvez à tout moment ajouter d'autres utilisateurs ou membres à un espace de travail existant. 

## <a name="create-a-new-workspace"></a>Créer un espace de travail

Le processus de création d'un espace de travail comprend la configuration de l'*environnement* pour l'organisation. Un environnement est un espace qui peut contenir un ou plusieurs espaces de travail. Vous pouvez utiliser un environnement pour gérer vos espaces de travail et vos connexions à la fonction Informations sur l’audience de Customer Insights.

1. Sélectionnez **Nouveau** depuis le sélecteur d'espace de travail.

   :::image type="content" source="media/new-workspace.png" alt-text="Page Customer Insights avec une légende sur le volet de navigation et une description.":::

1. Dans le volet **Espace de travail**, entrez un **Nom d’espace de travail**.

   :::image type="content" source="media/workspace-name.png" alt-text="Entrez un nom d’espace de travail.":::

1. Choisissez le type de plateforme (web ou mobile) que vous souhaitez évaluer.

1. Sélectionnez **Afficher les paramètres avancés** pour activer ou désactiver ces paramètres facultatifs :

   - Faites basculer **Inconnu à connu** sur « activé » pour associer des événements web aux utilisateurs qui se sont préalablement authentifiés. Pour plus d’informations, consultez [Reconnaître les événements web des visiteurs préalablement authentifiés](unknown-to-known.md)
   - Faites basculer **Filtrer le trafic du bot** sur "activé pour supprimer le trafic web des robots pour cet espace de travail. 

1. Une fois que vous avez terminé, sélectionnez **Terminer**. 

1. Installez le code extrait pour commencer à recevoir des données, puis sélectionnez **Finir** pour créer l’espace de travail. Pour plus d’informations, voir [Vue d’ensemble des ressources du développeur](developer-resources.md).

> [!NOTE]
> Vous pouvez maintenant ajouter des membres et attribuer leur niveau d’autorisation à partir de la liste **Rôle**. Pour en savoir plus, consultez [Rôles et autorisations](user-roles.md). 

Pour plus d'informations, consultez [Gérer les environnements et les espaces de travail](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
