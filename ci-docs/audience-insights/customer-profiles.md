---
title: Afficher les profils de client
description: Obtenez une vue combinée de vos données client unifiées.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 3a17716508a14020c56640c7d68f300a9d721af4
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354878"
---
# <a name="customer-profiles"></a>Profils clients

La page **Clients** affiche une vue combinée de vos profils clients unifiés. Les profils clients sont disponibles une fois que vous avez [créé l’entité Client unifiée](data-unification.md). La page vous permet de rechercher des clients et de définir l’index de cette recherche.

Les clients peuvent être des individus ou des organisations. Chaque profil client est représenté par une vignette. Utilisez les contrôles de pagination pour obtenir plus d’enregistrements. La carte affiche les champs de l’entité *Client* telle que définie dans l’**index Rechercher et filtrer**. Sélectionnez une vignette pour voir les données du client sélectionné sur une page dédiée appelée [Page de détails du client](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Page Clients affichant les vignettes de résultats](media/customers-page-result-tiles-B2C.png "Page Clients affichant les vignettes de résultats")

> [!NOTE]
> Si vous ne voyez pas les vignettes lorsque vous sélectionnez **Clients** dans le volet de navigation, votre administrateur doit [définir au moins un attribut pouvant être recherché](search-filter-index.md) dans l’**index Rechercher et filtrer**.

## <a name="search-for-customers"></a>Rechercher des clients

Recherchez des clients en saisissant un nom ou d’autres attributs dans la zone de recherche. La recherche ne fonctionne que dans l’entité _Client_ créée au cours du processus d’unification des données.

En tant qu’administrateur, vous pouvez configurer les attributs de recherche à l’aide de la page **Index Rechercher et filtrer**. Pour plus d’informations, rendez-vous sur [Gérer l’index de recherche et de filtrage](search-filter-index.md).

## <a name="filter-customers"></a>Filtrer les clients

Vous pouvez filtrer les clients par les champs d’entité _Client_. Comme pour la recherche, votre administrateur devra tout d’abord définir ces champs comme pouvant être filtrés à l’aide de la page **Index Rechercher et filtrer**.

1. Sélectionnez **Afficher les filtres** sur la page **Clients**.

1. Cochez les cases en regard des attributs selon lesquels vous souhaitez filtrer les clients.

1. Supprimez vos filtres en sélectionnant **Effacer les filtres** sur la page **Clients**.

## <a name="customer-details-page"></a>Page des détails du client

Sélectionnez l’une des vignettes client pour ouvrir la **Page des détails du client**. Cette vue contient des informations unifiées pour le client sélectionné. Les détails du client incluent le contenu suivant :

**Vignette de profil client** : cette vignette montre les différentes valeurs de l’entité _Client_ unifiée. Si un champ n’a pas de valeur pour le profil client sélectionné, il ne s’affichera pas. La vignette est structurée en sections :  
  - La première section affiche un ensemble prédéfini de champs suivi de tous les champs faisant partie de l’index de recherche et de filtrage. Tous les champs liés à l’adresse sont combinés en une seule ligne si le profil contient de tels champs. 
  - **Contacts pour ce client** : dans les environnements de comptes professionnels, vous verrez tous les contacts associés à ce client dans la deuxième section. Chaque contact est affiché avec ses champs. Les champs vides sont masqués.
  - **Champs supplémentaires** : Affiche les champs restants du client sélectionné, à l’exception des ID. 
  - **ID** : répertorie tous les ID sous leur nom d’entité correspondant. Les champs sont identifiés comme des identifiants par leur sémantique, qui les catégorise comme tels.

**Chronologie des activités** : Affiche les données si vous avez configuré des activités. La vue chronologique contient les activités triées par ordre chronologique du client sélectionné, en commençant par l’activité la plus récente. Pour plus d’informations, consultez [Activités client](activities.md).

**Insights** :  
  - **Mesures** : indique si vous avez configuré une ou plusieurs mesures d’attribut client. Elles englobent les KPI calculés de vos clients au niveau de chaque client. Pour plus d’informations, rendez-vous sur [Définir et gérer les mesures](measures.md).

  - **Intérêts potentiels, marques potentielles** : indique si vous avez configuré un enrichissement par marque ou par affinité d’intérêt. Il représente des intérêts et affinités potentiels pour les marques en fonction d’autres clients dont le profil est similaire au profil client sélectionné. Pour plus d’informations, rendez-vous sur [Enrichir les profils clients avec des affinités de marque et d’intérêt](enrichment-microsoft.md).

Pour revenir à la page de recherche de clients, sélectionnez **Retour aux clients**.

## <a name="next-steps"></a>Étapes suivantes

[Ajoutez plus de sources de données](data-sources.md), [enrichissez les profils unifiés](enrichment-hub.md) ou [créez des segments](segments.md) pour travailler avec des profils clients unifiés dans d’autres applications.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
