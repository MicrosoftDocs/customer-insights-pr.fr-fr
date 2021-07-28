---
title: Rechercher et filtrer des profils clients
description: Trouvez rapidement des informations sur les profils de clients unifiés et filtrez les attributs spécifiés.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597140"
---
# <a name="customer-profiles-search--filter-index"></a>Profils client : Index Rechercher et filtrer

Le résultat de l’unification de vos données client est une entité de profil client qui fournit une vue unifiée de l’intégralité de votre clientèle. Pour rapidement [trouver des informations sur un client ou un groupe de clients spécifique](customer-profiles.md), vous pouvez configurer les capacités **Rechercher** et **Filtrer** sur la page **Clients**. Lisez la suite pour savoir comment les administrateurs peuvent modifier les attributs sur la page **Index Rechercher et filtrer**, disponibles pour la recherche et le filtrage.

> [!div class="mx-imgBorder"]
> ![Filtre de recherche](media/search-filter.png "Filtre de recherche")

## <a name="add-fields-and-specify-attributes"></a>Ajouter des champs et spécifier des attributs

Si c’est la première fois que vous définissez des attributs de recherche en tant qu’administrateur, vous devez d’abord définir des champs indexés. Nous vous suggérons de choisir tous les attributs par lesquels les utilisateurs peuvent rechercher et filtrer les clients sur la page **Clients**. Vous pouvez sélectionner uniquement des attributs qui existent dans l’entité Profil client que vous avez créée pendant le processus d’unification des données.

1. Ouvrez la page **Clients** et sélectionnez **Index Rechercher et filtrer**.

2. Sélectionnez **+ Ajouter** pour spécifier les champs indexés.

3. Dans la liste, sélectionnez les attributs à ajouter en tant que champs indexés. Vous pouvez toujours ajouter plus d’attributs en sélectionnant **Ajouter**. Vous pouvez également supprimer tous les attributs sélectionnés en sélectionnant le symbole **Supprimer**.

## <a name="explore-the-indexed-customer-fields-table"></a>Explorer la table Champs client indexés

Les informations suivantes sont fournies dans le tableau suivant.

- **Nom** : Représente le nom de l’attribut comme il s’affiche dans l’entité Profil de client.
- **Type de données** : Spécifie si le type de données est une chaîne, un nombre ou une date.
- **Inclus dans la recherche** : Spécifie si l’attribut peut être utilisé pour rechercher des clients sur la page **Clients** (en utilisant le champ **Rechercher**).
- **Ajouter un filtre** : Permet de définir la manière dont cet attribut peut être utilisé pour filtrer la page **Clients**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Modifier les options de filtrage pour un attribut donné

Le menu **Filtrer** sur la page **Clients** peut inclure un nombre variable de niveaux d’attribut (par exemple, différentes tranches d’âges à partir desquelles filtrer les clients).

1. Sélectionnez **Ajouter un filtre** pour un attribut donné sur la page **Index Rechercher et filtrer**. Vous pouvez définir le nombre de résultats et l’ordre dans lequel ils seront organisés. Selon le type de données de l’attribut, l’un des volets suivants apparaît.

- Attributs de type chaîne : spécifiez le nombre de résultats souhaités dans le volet **Options de filtre de chaîne**, ainsi que la stratégie d’ordre dans lequel ils seront organisés.

- Attributs de type numérique : spécifiez les intervalles inclus dans le volet **Options de filtre de nombre**, ainsi que la stratégie d’ordre dans lequel ils seront organisés.

- Attributs de type de date : spécifiez les intervalles inclus dans le volet **Options de filtre de date**, ainsi que la stratégie d’ordre dans lequel ils seront organisés.

2. Sélectionnez **Enregistrer** pour appliquer vos modifications.

3. Sélectionnez **Exécuter** une fois que vous êtes prêt(e) à appliquer vos paramètres.

## <a name="next-steps"></a>Étapes suivantes

Aller à la page **Clients** pour rechercher des profils client ou utiliser les champs indexés pour voir un sous-ensemble de tous les profils client.


[!INCLUDE[footer-include](../includes/footer-banner.md)]