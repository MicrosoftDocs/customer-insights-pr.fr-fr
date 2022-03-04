---
title: Utiliser les segments des informations sur l’audience pour filtrer les rapports sur les informations sur l’engagement
description: Utilisez les segments des informations sur l’audience dans les analyses interactives des données comportementales saisies par les informations sur l’engagement sur le site web d’un client.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230483"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Utiliser les segments des informations sur l’audience pour filtrer les rapports sur les informations sur l’engagement

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Avec les informations sur l’engagement, vous pouvez utiliser les segments des informations sur l’audience dans les analyses interactives des données comportementales saisies par les informations sur l’engagement sur les sites web.

## <a name="prerequisite"></a>Conditions préalables

- Un environnement d’informations sur l’engagement dans lequel vous disposez des données sur les segments des informations sur l’audience liées à l’environnement d’informations sur l’audience dans lequel les segments et les profils client sont créés. Plus d’informations : [Créer un lien entre les informations sur l’audience et les informations sur l’engagement](integrate-audience-insights-engagement-insights.md).

## <a name="create-audience-insights-segments"></a>Créer des segments des informations sur l’audience 

> [!IMPORTANT]
> Pour que les segments des informations sur l’audience apparaissent dans les informations sur l’engagement, vous devez d’abord [exécuter les processus de fusion et en aval](../audience-insights/merge-entities.md). Les processus en aval sont importants car ils génèrent un tableau unique qui prépare les segments des informations sur l’audience à partager avec les informations sur l’engagement. (Si une actualisation du système est planifiée, elle inclut automatiquement les processus en aval.)

Vous pouvez utiliser les segments des informations sur l’audience dans les rapports prêts à l’emploi des informations sur l’engagement ou dans les rapports personnalisés que vous avez créés. Pour plus d’informations, accédez à [Rapports des profils prêts à l’emploi](profile-reports.md) et [Créer et modifier les rapports personnalisés](custom-reports.md).

**Pour utiliser les segments des informations sur l’audience dans les rapports sur les informations sur l’engagement**

1. Depuis la page **Espace de travail**, sélectionnez **Données**, puis sélectionnez l’onglet **Segments**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Sélectionnez l’onglet Segments.":::

   >[!NOTE]
   > En sélectionnant un segment des informations sur l’audience, vous accédez aux informations sur l’audience et découvrez les règles et la logique cachées derrière la création de ce segment. Pour plus d’informations sur les segments des informations sur l’audience, accédez à [Afficher et créer des segments](../audience-insights/segments.md).

2. Sélectionnez un rapport prêt à l’emploi ou [créez un rapport personnalisé](custom-reports.md), puis sélectionnez **Ajouter une condition**. (Pour cet exemple, nous avons choisi le rapport **Pages vues**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Ajoutez une condition.":::

3. Sélectionnez **Filtrer par segment**, développez la liste **Type de segment**, puis sélectionnez **Donnée démographique**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Sélectionnez le type de segment démographique.":::

4. Développez la liste **Nom du segment**, puis choisissez un segment des informations sur l’audience.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Choisissez un segment.":::

5. Vous pouvez appliquer un ou plusieurs segments, dont les segments comportementaux (informations sur l’engagement) et démographiques (informations sur l’audience). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Rapport sur les pages vues limité aux clients américains et aux segments de la page d’accueil.":::

Dans l’image précédente, les segments **Clients américains** et **Page d’accueil** sont sélectionnés, ce qui limite l’affichage du rapport **Pages vues** à ces deux segments. 


>[!NOTE]
> Utilisez les segments des informations sur l’audience pour filtrer les rapports prêts à l’emploi, les rapports personnalisés et les entonnoirs dans les informations sur l’engagement. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]