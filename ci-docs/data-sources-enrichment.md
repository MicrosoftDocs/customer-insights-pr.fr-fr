---
title: Enrichissement des sources de données
description: Enrichissez les sources de données avant de passer par le processus d’unification des données.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: d1e14d2d4e718d71ccbd2afd259a350ad5c9e69a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755683"
---
# <a name="enrichment-for-data-sources-preview"></a>Enrichissement des sources de données (version préliminaire)

Utilisez des données provenant de sources telles que Microsoft et d’autres partenaires pour enrichir vos données client avant l’unification des données. Les enrichissements de sources de données permettent de produire des données plus complètes et de meilleure qualité, ce qui peut aider à obtenir de meilleurs résultats une fois que vous avez unifié vos données. Par exemple, l’utilisation d’un format normalisé et standardisé pour les adresses augmente la qualité des résultats de correspondance. Pour obtenir la liste des enrichissements pris en charge, consultez les [options d’enrichissement de source de données prises en charge](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Enrichir une source de données

Vous devez disposer des autorisations Contributeur ou Administrateur pour créer ou modifier des enrichissements. Pour plus d’informations, voir [Autorisations](permissions.md).  

1. Accédez à **Données** > **Unifier**. Sélectionnez l’entité que vous souhaitez enrichir et sélectionnez un attribut comme clé primaire pour l’entité. Pour plus d’informations, consultez [Sélectionner la clé primaire](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Accédez à **Données** > **Sources de données**.

1. Sélectionnez les points de suspension verticaux à côté de la source de données à enrichir et sélectionnez **Enrichir**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Page d’enrichissement des sources de données.":::

   L’onglet **Découvrir** affiche les [options d’enrichissement de source de données prises en charge](#supported-data-source-enrichments).

1. Sélectionnez **Enrichir mes données** pour configurer un enrichissement source de données. Le nom de l’entité de sortie est renseigné automatiquement.

## <a name="supported-data-source-enrichments"></a>Enrichissements de source de données pris en charge

Les enrichissements suivants sont actuellement disponibles pour les sources de données. Passez en revue les étapes détaillées de l’enrichissement pour savoir comment le configurer.

- [Adresses améliorées](enrichment-enhanced-addresses.md)
- [Amélioration des données de l’entreprise](enrichment-enhanced-company-data.md)

## <a name="manage-existing-data-source-enrichments"></a>Gérer les enrichissements de source de données existants

Accédez à l’onglet **Mes enrichissements** pour voir tous les enrichissements configurés.

Sélectionnez l’enrichissement pour voir les options disponibles. Vous pouvez également sélectionner les points de suspension (...) d’un élément de liste pour voir les options. Si vous avez configuré plusieurs enrichissements, vous pouvez utiliser le champ de recherche pour le retrouver rapidement.

Vous pouvez afficher, modifier, exécuter ou supprimer un enrichissement de source de données. Pour plus d’informations, voir [Gérer les enrichissements existants](enrichment-hub.md)..