---
title: Afficher les profils de client
description: Afficher vos données client unifiées, y compris en utilisant la recherche et les filtres
ms.date: 06/08/2022
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
ms.openlocfilehash: 0c8edfd8f45ce7770d568811df2b38be1b04e73a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303780"
---
# <a name="view-customer-profiles"></a>Afficher les profils de client

Les profils de client sont disponibles une fois que vous avez [créé l’entité *Client* unifiée](data-unification.md). La vue combinée de vos profils clients unifiés s’affiche sur la page **Clients**. Les clients peuvent être des individus ou des organisations.

Accédez à la page **Clients** pour afficher vos clients et leurs profils. Chaque profil client est représenté par une vignette. Utilisez les contrôles de pagination pour obtenir plus d’enregistrements. La carte affiche les champs de l’entité *Client* telle que définie dans l’**index Rechercher et filtrer**. L’ordre des champs dans chaque carte est choisi par le système.

> [!NOTE]
> Si vous ne voyez pas les vignettes lorsque vous sélectionnez **Clients**, votre administrateur doit [définir au moins un attribut pouvant être recherché](search-filter-index.md) dans l’**index Rechercher et filtrer**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Page Clients affichant les vignettes de résultats.":::

Sélectionnez l’une des actions suivantes :
- [Afficher les détails du client](#view-customer-details)
- [Gérer l’index de recherche et de filtrage](search-filter-index.md) (administrateurs uniquement)
- [Filtrer les clients](#filter-customers)
- **Développez les cartes** ou **Réduire les cartes** pour développer ou réduire les informations affichées sur la vignette du client
- **Trier par** un attribut particulier
- [Rechercher des clients](#search-for-customers)

  > [!NOTE]
  > Pour utiliser la recherche et le filtrage, un administrateur doit configurer les attributs de recherche et définir les champs filtrables à l’aide de l’index de recherche et de filtrage.

## <a name="search-for-customers"></a>Rechercher des clients

Recherchez des clients en saisissant un nom ou d’autres attributs dans **Rechercher les clients**. Les attributs consultables sont définis par l’administrateur et proviennent de l’entité *Client*.

> [!NOTE]
> **Chaîne** est le seul type de données inclus dans la recherche. Utilisez-le dans le champ **Rechercher des clients** sur la page Clients pour rechercher des clients.

## <a name="filter-customers"></a>Filtrer les clients

Filtrez les clients selon les champs d’entité *Client*. Les champs filtrables sont définis par l’administrateur.

1. Sur la page **Clients**, sélectionnez **Afficher les filtres**. Le volet Filtre s’affiche.

1. Cochez les cases en regard des attributs selon lesquels vous souhaitez filtrer les clients.

1. Supprimez tous les filtres en sélectionnant **Effacer les filtres** ou décochez une case en regard d’un attribut sélectionné.

1. Sélectionnez **Masquer les filtres** pour fermer le volet de filtre.

1. Pour enregistrer les résultats du filtre en tant que [segment](segments.md), sélectionnez **Enregistrer les filtres en tant que segment**.
   1. Entrez un nom pour le segment.
   1. Sélectionnez **Enregistrer** pour enregistrer le segment.
   1. Choisissez d’exécuter le segment maintenant en sélectionnant **Activer** ou exécutez-le **ultérieurement**.

## <a name="view-customer-details"></a>Afficher les détails du client

Sur la page **Clients**, sélectionnez une vignette client pour afficher les détails du client sélectionné.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Page des détails du client.":::

Les détails du client comprennent :

**Vignette de profil client** : montre les différentes valeurs de l’entité *Client* unifiée. Si un champ n'a pas de valeur pour le profil client sélectionné, il ne s'affichera pas sauf pour le champ d'adresse. La vignette est structurée en sections :

- La première section affiche un ensemble prédéfini de champs suivi de tous les champs faisant partie de l’index de recherche et de filtrage. Tous les champs liés à l'adresse sont combinés sur une seule ligne, qui s'affiche même si le profil ne contient aucune information d'adresse.
- **Contacts pour ce client** s’affichent dans des environnements pour comptes professionnels (B-to-B). Chaque contact est affiché avec ses champs. Les champs vides sont masqués.
- **Champs supplémentaires** : affiche les champs restants du client sélectionné, à l’exception des ID.
- **ID** : répertorie tous les ID sous leur nom d’entité correspondant. Les champs sont identifiés comme ID par leur sémantique.

**Chronologie des activités** affiche les données si vous avez configuré des [activités](activities.md). La vue chronologique contient les activités triées par ordre chronologique du client sélectionné, en commençant par l’activité la plus récente.

**Insights** :

- Les **mesures** s’affichent si vous avez configuré les [mesures d’attribut client](measures.md). Elles englobent les KPI calculés de vos clients au niveau de chaque client.

- **Intérêts potentiels, marques potentielles** indique si vous avez configuré un [enrichissement par marque ou par affinité d’intérêt](enrichment-microsoft.md). Il représente des intérêts et affinités potentiels pour les marques en fonction d’autres clients dont le profil est similaire au profil client sélectionné.

Pour revenir à la page **Clients**, sélectionnez **Retour aux clients**.

## <a name="next-steps"></a>Étapes suivantes

[Ajoutez plus de sources de données](data-sources.md), [enrichissez les profils unifiés](enrichment-hub.md) ou [créez des segments](segments.md) pour travailler avec des profils clients unifiés dans d’autres applications.

[!INCLUDE [footer-include](includes/footer-banner.md)]
