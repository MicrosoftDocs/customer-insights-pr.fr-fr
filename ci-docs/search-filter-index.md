---
title: Gérer l’index Rechercher et filtrer pour les profils clients
description: Trouvez rapidement des informations sur les profils de clients unifiés et filtrez les attributs spécifiés.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187906"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Gérer l’index Rechercher et filtrer pour les profils clients

Le résultat de l’unification de vos données client est une entité *Client* qui fournit une vue unifiée de l’intégralité de votre clientèle. Pour que les utilisateurs [trouvent des informations sur un client ou un groupe de clients spécifique](customer-profiles.md) rapidement, vous pouvez configurer les capacités **Rechercher** et **Filtrer** sur la page **Clients**.

   :::image type="content" source="media/search-filter.png" alt-text="Filtre de recherche":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Définir les attributs de recherche et les champs indexés

Si c’est la première fois que vous définissez des attributs de recherche en tant qu’administrateur, définissez des champs indexés. Nous vous suggérons de choisir tous les attributs par lesquels les utilisateurs peuvent rechercher et filtrer les clients sur la page **Clients**. Vous pouvez spécifier uniquement des attributs qui existent dans l’entité *Client* que vous avez créée pendant le processus d’unification des données.

1. Accédez à **Clients** et sélectionnez **Index Rechercher et filtrer**.

1. Cliquez sur **+ Ajouter**.

1. Dans la liste, sélectionnez les attributs à ajouter en tant que champs indexés et cliquez sur **Appliquer**.

1. Pour ajouter plus d’attributs, sélectionnez **Ajouter**. Pour supprimer un attribut, sélectionnez-le, puis choisissez **Supprimer**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Page Index Rechercher et filtrer":::

1. Sélectionnez **Exécuter** une fois que vous êtes prêt(e) à appliquer vos paramètres de recherche et de filtrage. Une fois les modifications traitées, affichez-les dans les [fiches client de la page Client](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Définir les options de filtrage pour un attribut donné

Configurez les champs qui peuvent être utilisés pour le filtrage sur la page **Clients**.

1. Accédez à **Clients** et sélectionnez **Index Rechercher et filtrer**.

1. Sélectionnez un attribut, puis **Ajouter un filtre**. Définissez le nombre de résultats et l’ordre dans lequel ils seront organisés. Selon le type de données de l’attribut, l’un des volets suivants apparaît.

   - Attributs de type chaîne : spécifiez le nombre de résultats souhaités dans le volet **Filtre de chaîne**, ainsi que la stratégie d’ordre dans lequel ils seront organisés.

   - Attributs de type numérique : spécifiez les intervalles inclus dans le volet **Filtre de nombre**, ainsi que la stratégie d’ordre dans lequel ils seront organisés.

   - Attributs de type de date : spécifiez les intervalles inclus dans le volet **Filtre de date**, ainsi que la stratégie d’ordre dans lequel ils seront organisés.

1. Cliquez sur **OK**. Répétez l’opération pour tous les attributs que vous souhaitez utiliser pour filtrer.

1. Sélectionnez **Exécuter** une fois que vous êtes prêt(e) à appliquer vos paramètres de recherche et de filtrage. Une fois les modifications traitées, affichez-les dans les [fiches client de la page Client](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Afficher les champs client indexés

La page **Index de recherche et de filtrage** affiche les informations suivantes :

- **Nom** : représente le nom de l’attribut comme il s’affiche dans l’entité *Client*.
- **Type de données** : Spécifie si le type de données est une chaîne, un nombre ou une date.
- **Inclus dans la recherche** : Spécifie si l’attribut peut être utilisé pour rechercher des clients sur la page **Clients** (en utilisant le champ **Rechercher**).
- **Ajouter un filtre** : Permet de définir la manière dont cet attribut peut être utilisé pour filtrer la page **Clients**.

## <a name="next-steps"></a>Étapes suivantes

Révisez la [page des profils unifiés](customer-profiles.md) pour rechercher des profils ou utiliser les champs indexés pour afficher un sous-ensemble de tous les profils unifiés.

[!INCLUDE [footer-include](includes/footer-banner.md)]
