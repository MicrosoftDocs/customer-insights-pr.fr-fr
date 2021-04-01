---
title: Afficher les profils de client
description: Obtenez une vue combinée de vos données client unifiées.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596864"
---
# <a name="customer-profiles"></a>Profils clients

La page **Clients** offre une vue combinée de vos clients, en fonction des données de profil collectées à partir de [toutes les sources de données](data-sources.md). Les profils de client sont disponibles une fois que vous avez [créé l’entité Client unifiée](data-unification.md). Veillez à terminer le processus d’unification des données pour obtenir des vues enrichies de vos clients. La page vous permet également rechercher des clients.

Les clients peuvent être des personnes ou des organisations (préversion). Chaque profil de client ou d’organisation est représenté par une vignette. Sélectionnez une vignette pour voir des informations supplémentaires sur ce client ou cette organisation. Utilisez les commandes de pagination en bas de la page pour voir des enregistrements supplémentaires.

> [!div class="mx-imgBorder"] 
> ![Profils de client B2C](media/profiles-customers.png "Profils de client B2C")

Organisations (Préversion)
> [!div class="mx-imgBorder"] 
> ![Profils de client B2B](media/profile-customers-b2b.png "Profils de client B2B")

> [!NOTE]
> Si les vignettes ne s’affichent pas lorsque vous sélectionnez **Clients** dans le volet de navigation, votre administrateur doit [définir au moins un attribut de recherche](search-filter-index.md) dans **Index Rechercher et filtrer**.

## <a name="search-for-customers"></a>Rechercher des clients

Recherchez des clients en saisissant un nom ou d’autres attributs dans la zone de recherche. La recherche n’aura lieu qu’au sein de l’entité Profil du client créée lors du processus d’unification des données.

En tant qu’administrateur, vous pouvez configurer les attributs de recherche à l’aide de la page **Index Rechercher et filtrer**. Pour plus d’informations, voir [Gérer l’index Rechercher et filtrer](search-filter-index.md).

## <a name="filter-customers"></a>Filtrer les clients

Vous pouvez filtrer les clients par les champs d’entité Profil client. Comme pour la recherche, votre administrateur devra tout d’abord définir ces champs comme pouvant être filtrés à l’aide de la page **Index Rechercher et filtrer**.

1. Sélectionnez **Filtrer** sur la page **Clients**.

2. Cochez les cases en regard des attributs selon lesquels vous souhaitez filtrer les clients.

   > [!div class="mx-imgBorder"] 
   > ![Profils clients](media/profiles-customers3.png "Profils client")

3. Supprimez vos filtres en sélectionnant **Effacer les filtres** sur la page **Clients**.

##  <a name="customer-details-page"></a>Page des détails du client

Sélectionnez l’une des vignettes client pour ouvrir la **Page des détails du client**. Cette vue contient des informations unifiées pour le client sélectionné.

Les détails du client comprennent :

-   **Vignette du profil client :** cette vignette indique les différentes valeurs de l’entité de profil client unifié. Ces détails peuvent comprendre l’adresse e-mail, le nom, la ville, etc. 

-   **Intérêts potentiels, marques potentielles :** indique si vous avez configuré un enrichissement interne. Il représente les intérêts et affinités potentiels pour des marques que pourrait avoir un client avec un profil similaire à ce client. Pour plus d’informations, consultez [Enrichissement des profils clients avec des affinités de marque et d’intérêt](enrichment-microsoft-graph.md).

-   **Mesures :** indique si vous avez configuré une ou plusieurs mesures d’un type spécifique : mesures d’attribut client. Elles englobent les KPI calculés de vos clients au niveau de chaque client. Pour plus d’informations, consultez [Définir et gérer les mesures](measures.md).

-   **Chronologie des activités :** indique si vous avez configuré des activités. La vue chronologique contient les activités triées par ordre chronologique de ce client, en commençant par l’activité la plus récente. Pour plus d’informations, voir [Activités client](activities.md).

Sélectionnez **Retour aux clients** pour revenir à la page de recherche de clients.

## <a name="next-steps"></a>Étapes suivantes

[Ajoutez d’autres sources de données](data-sources.md) ou [créez des segments de client](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]