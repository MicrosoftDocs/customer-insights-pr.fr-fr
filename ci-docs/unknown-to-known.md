---
title: Personnaliser vos expériences avec des données sur les utilisateurs connus et inconnus
description: Intégrez les informations sur les utilisateurs précédemment inconnus lorsque vous connaissez leur identité.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: ff99721bef0004bc8cae1ec14ff9df16cbb0682e
ms.sourcegitcommit: ece8ff732490ecd3b3421ab273f331e6fd46a7f7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/19/2022
ms.locfileid: "9173792"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Personnaliser vos expériences avec des données sur les utilisateurs connus et inconnus

La gestion des données clients n’est pas un nouveau défi, mais elle devient de plus en plus difficile à mesure que les utilisateurs naviguent sur les différents canaux numériques proposés par les marques. Un utilisateur connu (authentifié) sur un canal devient inconnu (non authentifié) sur un autre s’il n’est pas connecté. Le problème est souvent que les utilisateurs non authentifiés (inconnus) n’ont pas d’identifiant commun. Il pourrait être utilisé pour associer des attributs de profils significatifs et générer des profils client unifiés. Customer Insights aide à résoudre ce problème en ingérant des données à partir de méthodes de suivi sur vos systèmes sources. Les profils inconnus et connus consolidés offrent aux organisations une vue complète des profils à jour et de leurs transactions, comportements et données démographiques historiques. Il va même plus loin en fournissant une résolution d’identité qui vous permet d’unifier l’activité des clients sur plusieurs canaux, y compris votre site web, les achats en magasin, les programmes de fidélité, etc.

## <a name="sample-scenario"></a>Exemple de scénario

Prenons l’exemple d’une chaîne de cafés, qui dispose d’une large clientèle qui achète du café et de la nourriture dans les magasins et commande des produits en ligne. Souvent, les visiteurs en ligne ne sont pas authentifiés lorsqu’ils parcourent les produits, ce qui en fait des « utilisateurs inconnus ». Il est difficile pour la chaîne de café de proposer des offres et des expériences personnalisées si les utilisateurs sont inconnus. D’autre part, les clients peuvent se connecter à leur compte et devenir des « utilisateurs connus » de l’entreprise en rejoignant un système de fidélité, qui à son tour permet des expériences plus personnalisées. Customer Insights peut aider la chaîne de café à obtenir des informations sur les utilisateurs connus et précédemment inconnus.

Avec Customer Insights, l’entreprise peut combiner les profils des clients avec les données d’activité des sessions non authentifiées (inconnues) une fois qu’un utilisateur s’est connecté et s’est fait connaître. La chaîne de café peut apporter des données provenant d’autres sources de données à l’aide de connecteurs intégrés dans Customer Insights pour fusionner les identités des clients de différents canaux.

## <a name="prerequisites"></a>Conditions préalables

- Les données web sont collectées et contiennent des « ID visiteur » pour tous les visiteurs.
- Les données web contiennent des « ID d’utilisateur authentifiés » pour les visiteurs connectés. Ces ID sont liés au système de fidélité.
- Les données d’événements de grande valeur telles que « Vue du produit » et « Commande » sont définies et incluses dans les données source avec l’horodatage de l’événement et un ID d’événement.

Le tableau suivant montre un exemple simplifié de la manière dont les événements web de grande valeur peuvent être capturés.

|EventID|EventTimeStamp|UserID|LoyaltyID|EventName|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|Vue de produit|
|2|07-23-2022 10:05:00|abc123|707|Connexion de fidélité|
|3|07-23-2022 10:10:00|abc123|707|Paiement|
|4|07-23-2022 10:20:00|xyz789|--|Vue de produit|

## <a name="data-ingestion"></a>Ingestion des données

Les données sur les clients peuvent provenir de votre site web en tant que données d’événement et peuvent être stockées dans vos propres services d’analyse de données internes ou tiers. Les données web contiennent des utilisateurs connus et inconnus si le site web dispose d’un flux d’authentification qui s’intègre à un service d’authentification. Par exemple, un système de commerce électronique qui oblige les utilisateurs à fournir leurs coordonnées complètes pour terminer une transaction d’achat. Ou un système de fidélité qui nécessite une authentification pour confirmer un destinataire valide des remises de récompenses.

Les données d’événement dans notre exemple ci-dessus contiennent les identifiants de profil distincts des utilisateurs connus et inconnus. Dans les événements 1 et 4, les utilisateurs sont inconnus tandis que dans les événements 2 et 3, l’utilisateur avec l’ID abc123 s’inscrit à un programme de fidélité.

:::image type="content" source="media/website-data-source.png" alt-text="Sources de données, y compris le site web Contoso.":::

Pour plus d’informations sur les options disponibles pour l’ingestion des données, voir [Présentation des sources de données](data-sources.md).

## <a name="data-unification"></a>Unification des données

La convergence d’identités inconnues avec des identités connues permet une personnalisation basée sur les comportements des utilisateurs, quel que soit l’état de leur profil (connu ou inconnu). Un contenu personnalisé pour tous les utilisateurs aide les clients à accéder rapidement aux produits ou services les plus pertinents qui les intéressent à ce moment précis.

Étant donné que certains des utilisateurs de nos données sont connus, nous pouvons utiliser Customer Insights pour combiner ces données avec le profil de l’utilisateur. Pour plus d’informations sur l’unification de vos profils clients, voir [Présentation de l’unification des données](data-unification.md).

1. Sélectionnez les champs source à partir de l’entité de données web. Utilisez les données de profil stockées dans vos données web et sélectionnez les champs qui représentent les identifiants avec des données démographiques.

   :::image type="content" source="media/website-source-fields.png" alt-text="Champs source pour la source des données web":::

1. Ajouter des règles pour fusionner les enregistrements dupliqués. Pour les données web, choisissez les données les plus remplies.

1. Configurer les règles et conditions de correspondance. Les données d’événement de profils web dans cet exemple seront mises en correspondance sur les ID avec les profils des autres sources de données qui contiennent des informations sur les clients. Configurez des règles de correspondance exacte sur les ID en tant que règles distinctes avec chacune des autres entités de profil qui ont une clé primaire ou une correspondance d’ID correspondante. Dans l’exemple, les données de profil d’événement web sont utilisées comme dernière entité correspondante afin que les autres données de profil soient combinées en premier.
   1. Le fait de ne pas cocher **Inclure tous les enregistrements** crée des profils unifiés pour les utilisateurs connus et inclut leurs identifiants d’utilisateur inconnus correspondants. Il est utile dans les scénarios où vous souhaitez afficher les activités comportementales passées d’utilisateurs connus alors qu’ils étaient encore inconnus.
   1. Le fait de cocher **Inclure tous les enregistrements** crée des enregistrements de profil distincts pour les utilisateurs inconnus. Les utilisateurs inconnus obtiennent un identifiant client unique. À l’avenir, lorsqu’un profil connu est associé dans les données de profil des événements web, le parcours de l’utilisateur nouvellement connu peut également être visualisé et utilisé pour la personnalisation en fonction de données comportementales passées inconnues.

:::image type="content" source="media/website-match-rule.png" alt-text="Règle de correspondance pour l’entité de site web source de données.":::

## <a name="get-insights"></a>Obtenir des informations

Si des profils client sont créés pour des utilisateurs inconnus et connus, les données d’événements web de grande valeur peuvent être utilisées comme [activités](activities.md). Ces activités peuvent être utilisées pour créer plus d’informations. Par exemple, les clients qui ont visité un site web il y a six mois (alors qu’ils étaient encore inconnus) ou les clients qui n’ont pas d’identifiant de fidélité n’ont jamais effectué de paiement.

:::image type="content" source="media/website-known-unknown.png" alt-text="Capture d’écran de la page client avec les clients connus et inconnus.":::

[Enrichissez](enrichment-hub.md) vos données, créez des [mesures](measures.md) et créez des [segments](segments.md) pour une activation ultérieure.

Par exemple, vous pouvez créer des segments d’utilisateurs connus qui ont regardé certains produits mais n’ont jamais terminé le paiement.

Pour plus d’informations, voir [Vue d’ensemble des segments](segments.md).

## <a name="activate-insights"></a>Activer Insights

Il existe plusieurs façons d’exporter vos données et d’agir en fonction des informations sous-jacentes.

Pour plus d’informations, voir [Présentation des exportations](export-destinations.md).
