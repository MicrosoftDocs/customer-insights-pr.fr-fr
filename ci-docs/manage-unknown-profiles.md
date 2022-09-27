---
title: Gérer les profils inconnus avec Customer Insights
description: Utilisez des profils de clients inconnus créés et gérés dans Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: d7e5050ee5832df5ecf40a352f7ea8d42830fa45
ms.sourcegitcommit: f6b6a4c4ce9cf12e449488b24aab80a2cbfe0c47
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2022
ms.locfileid: "9556393"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Gérer les profils inconnus avec Customer Insights

Les internautes sont souvent non identifiés et anonymes en ligne. S’ils ne sont pas connectés parce qu’ils utilisent des appareils ou des canaux différents, c’est même vrai pour les clients les plus fidèles. Les cookies tiers étant susceptibles de disparaître bientôt, la gestion des préférences des utilisateurs en fonction des données de première partie est cruciale pour obtenir des expériences personnalisées différenciées. Pour de nombreuses marques, les utilisateurs connus ou authentifiés sont minoritaires malgré les attentes croissantes des clients en matière de personnalisation. C’est formidable pour les entreprises de savoir qui sont leurs clients, sur la base de données fiables, détaillées et unifiées.

La personnalisation mémorable dépend de la richesse et de l’exhaustivité de vos données clients et Customer Insights vous aide à atteindre ces objectifs. Vous n’êtes pas obligé de limiter ou d’arrêter l’utilisation des données collectées au début du parcours du client. Customer Insights vous permet d’apporter vos propres données pour créer un profil client pour les utilisateurs inconnus. Vous pouvez ensuite utiliser ce profil pour d’autres actions, malgré les informations de contact manquantes. Importez des données de première partie à partir de sources telles que des systèmes Web, mobiles ou CRM dans Customer Insights pour enrichir en continu les profils des clients. À mesure que vous unifiez davantage d’interactions, [transformez le client *inconnu* en un client *connu*](unknown-to-known.md).

## <a name="sample-scenario"></a>Exemple de scénario

Le commerce électronique est le canal avec la croissance la plus rapide au cours de la dernière décennie. Supposons qu’un utilisateur utilise son appareil mobile pour parcourir votre site de commerce électronique. Le site Web attribue au visiteur « mobile_guest123 » un identifiant unique et vous commencez à collecter des activités comportementales en fonction de son activité en ligne. Par exemple, quelles pages il a visitées, combien de temps il a passé sur ces pages ou sur quels liens il a cliqué. Vous ne connaissez pas leur nom ou leur adresse e-mail, mais ces données peuvent aider à fournir aux marques des informations utiles sur cet utilisateur spécifique. En retour, vous pouvez mettre ces informations en pratique la prochaine fois que l’utilisateur visitera le site. Interrogez Customer Insights pour « mobile_guest123 » pour récupérer la liste des segments de l’utilisateur, tels que « organiques », « clients mobiles en précommande », « clients à forte valeur », etc., ou récupérez le profil pour créer des expériences Web personnalisées. Vous pouvez également exporter les données vers n’importe quel système d’activation pour faire de même.

## <a name="prerequisites"></a>Conditions préalables

- Ingérer des données de première partie dans Customer Insights
- Chaque entité a un identifiant unique qui est défini comme clé primaire
- Chaque entité avec une clé primaire pour la personnalisation est unifiée
- Le système de gestion de contenu de votre site Web est capable d’utiliser des API (pour une personnalisation Web basée sur une communication directe avec Customer Insights)

Le tableau suivant montre un exemple simplifié de la manière dont les événements web de grande valeur peuvent être capturés.

|EventID|EventTimeStamp|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|Vue de produit|
|2|09-18-2022 10:05:00|abc123|CookieID1|Vue de produit|
|3|09-18-2022 10:10:00|abc123|CookieID1|Ajouter au panier|
|4|09-21-2022 09:05:00|abc123|CookieID1|Vue de produit|

## <a name="data-ingestion"></a>Ingestion des données

Pour plus d’informations sur les options disponibles pour l’ingestion des données, voir [Présentation des sources de données](data-sources.md).

## <a name="data-unification"></a>Unification des données

Pour plus d’informations sur l’unification de vos profils clients, voir [Présentation de l’unification des données](data-unification.md).

## <a name="get-insights"></a>Obtenir des informations

[Enrichissez](enrichment-hub.md) vos données, créez des [mesures](measures.md) et créez des [segments](segments.md) pour une activation ultérieure.

Par exemple, vous pouvez créer des segments d’utilisateurs inconnus qui ont parcouru les mêmes pages de produits, mais n’ont jamais terminé le paiement.

## <a name="activation"></a>Activation

Avec vos données dans Customer Insights et vos informations prêtes à être utilisées, vous pouvez utiliser Customer Insights pour la personnalisation :

1. Utilisez l’[API OData](apis.md) pour récupérer une appartenance à un segment ou un profil client Pour plus d’exemples, voir [Exemples de requêtes OData pour les API Customer Insights](odata-examples.md).

1. [Exportez](export-destinations.md) vos données vers vos systèmes d’activation.

Exemple : Un utilisateur inconnu visite plusieurs fois un site Web et consulte des pages de produits pour différents modèles de chaussures en cuir. Avec ces données disponibles dans Customer Insights, vous pouvez inclure l’utilisateur inconnu dans le segment des personnes intéressées par les chaussures en cuir. Utilisez ce segment pour informer la personnalisation de la création de votre site Web pour les visiteurs qui reviennent. À sa prochaine visite, le site reconnaîtra l’utilisateur inconnu et pourra lui offrir un coupon de 10 % de remise sur des chaussures en cuir.

[!INCLUDE [footer-include](includes/footer-banner.md)]
