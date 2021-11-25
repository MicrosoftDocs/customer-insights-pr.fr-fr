---
title: Créer un environnement
description: Le but d’un environnement et comment en créer un nouveau.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 8ff04a6b2ffbd513a77f7f8a33358f3d8f559c7e
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673639"
---
# <a name="create-a-new-environment"></a>Créer un environnement 

## <a name="overview"></a>Résumé

Un environnement est un espace dans lequel vous gérez vos espaces de travail et vos connexions. La façon dont vous utilisez les environnements dépend de votre organisation et de votre cas d'utilisation. Par exemple, vous pouvez créer :

- Un seul environnement.
- Des environnements distincts pour les tests et la production.
- Des environnements distincts pour des équipes ou des services spécifiques de votre organisation qui contiennent des événements pertinents pour chaque audience.
- Des environnements distincts pour différentes succursales mondiales de votre société.
- Connexions à la fonction Informations sur l’audience de Customer Insights.

## <a name="create-a-new-environment"></a>Créer un environnement

1. Sur le côté droit de la bannière principale, sélectionnez le sélecteur d’environnement, puis **+Nouveau**.

   :::image type="content" source="media/environment-picker.png" alt-text="Sélectionnez le sélectionneur d’environnement.":::

1. Dans le volet **Configurer**, tapez un **Nom de l’environnement**.

1. Choisir le **Type** de compte, selon votre type de plan.

1. Choisissez la **Région** et sélectionnez **Suivant**. 

1. Entrez un **nom d’espace de travail**, qui vous permet de collecter des données pour des sites web ou des applications spécifiques. Pour plus d’informations, consultez [Créer un espace de travail](create-workspace.md).

1. Choisissez le **type d’espace de travail** (web ou mobile) que vous souhaitez créer. 

1. Sélectionnez **Afficher les paramètres avancés** pour activer ou désactiver ces paramètres facultatifs :

   - Faites basculer **Inconnu à connu** sur « activé » pour associer des événements web aux utilisateurs qui se sont préalablement authentifiés. Pour plus d’informations, consultez [Reconnaître les événements web des visiteurs préalablement authentifiés](unknown-to-known.md).
   - Faites basculer **Filtrer le trafic du bot** sur "activé pour supprimer le trafic web des robots pour cet espace de travail. 

1. Une fois que vous avez terminé, sélectionnez **Terminer**. 

1. Installez le code extrait pour commencer à recevoir des données, puis sélectionnez **Finir** pour créer l’espace de travail. Pour plus d’informations, voir [Vue d’ensemble des ressources du développeur](developer-resources.md).

> [!NOTE]
> Vous pouvez maintenant ajouter des membres et attribuer leur niveau d’autorisation à partir de la liste **Rôle**. Pour en savoir plus, consultez [Rôles et autorisations](user-roles.md). 

Pour plus d'informations, consultez [Gérer les environnements et les espaces de travail](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Travailler avec votre nouvel environnement

- [Créer un espace de travail](../engagement-insights/create-workspace.md) et ajouter des membres.
- [Ajoutez du code à votre site web](../engagement-insights/instrument-website.md) ou [application mobile](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Consultez un [rapport en temps réel](../engagement-insights/view-reports.md) ou créez des [rapports personnalisés](../engagement-insights/custom-reports.md).
- [Créez des événements affinés](../engagement-insights/refined-events.md) pour l'exportation.
- [Exportez les données](../engagement-insights/export-events.md) dans Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
