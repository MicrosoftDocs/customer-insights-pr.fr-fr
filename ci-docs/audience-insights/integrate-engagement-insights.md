---
title: Intégrez les données web issues des informations sur l’engagement avec les informations sur l’audience
description: Apportez des informations web sur les clients, des informations sur l’engagement aux informations sur l’audience.
ms.date: 06/24/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 037e264658bc354618cff56a89645ef7552aeb13
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350542"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Intégrez les données web issues des informations sur l’engagement avec les informations sur l’audience


[!INCLUDE [cc-beta-prerelease-disclaimer](../engagement-insights/includes/cc-beta-prerelease-disclaimer.md)]

Les clients effectuent souvent leurs transactions quotidiennes en ligne à l’aide de sites web. La fonction d’informations d’engagement (version préliminaire) dans Dynamics 365 Customer Insights est une solution pratique pour intégrer les données web en tant que source. En plus des données transactionnelles, démographiques ou comportementales, nous pouvons voir les activités sur le web dans des profils clients unifiés. Nous pouvons utiliser ces profils pour obtenir des informations supplémentaires telles que des segments, mesures ou prédictions pour l’activation de l’audience.

Cet article décrit les étapes à suivre pour intégrer les données d’activité web de vos clients à partir des informations sur l’engagement dans votre environnement d’informations sur l’audience existant.

Dans cet exemple, nous supposons un environnement qui contient des profils client unifiés. Les profils ont été unifiés avec des sources provenant d’enquêtes, de ventes au détail et d’un système de billetterie. Il montre également les activités connexes des clients. 

Nous voulons maintenant savoir si un client visite nos propriétés web et comprendre ses activités. Les activités comprennent, par exemple, des sites web visités ou des pages de produits consultées à partir d’un lien reçu dans un e-mail.

## <a name="prerequisites"></a>Conditions préalables

Pour intégrer les données issues des informations sur l’engagement, quelques conditions préalables doivent être remplies : 

- Intégrer le Kit de développement logiciel (SDK) des informations sur l’engagement à votre site web. Pour plus d’informations, voir [Vue d’ensemble des ressources du développeur](../engagement-insights/developer-resources.md).
- L’exportation d’événements web à partir des informations d’engagement nécessite d’avoir accès à un compte Azure Data Lake Storage qui sera utilisé pour ingérer les données d’événements web dans Audience Insights. Pour plus d’informations, voir [Exporter les événements](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Configurer des événements affinés dans les informations sur l’engagement

Une fois qu’un administrateur a instrumenté un site web avec le SDK des informations d’engagement, les *événements de base* sont collectés lorsqu’un utilisateur affiche une page web ou clique quelque part. Les événements de base ont tendance à contenir de nombreux détails. En fonction de votre cas d’utilisation, vous n’avez besoin que d’un sous-ensemble de données dans un événement de base. Les informations sur l’engagement vous permettent de créer des *événements affinés* qui contiennent uniquement les propriétés d’un événement de base que vous sélectionnez.     

Pour plus d’informations, voir [Créer et modifier des événements affinés](../engagement-insights/refined-events.md).

Considérations lors de la création d’événements raffinés : 

- Donnez un nom significatif à l’événement raffiné. Il sera utilisé comme nom d’activité dans Audience Insights.
- Sélectionnez au moins les propriétés suivantes pour créer une activité dans les informations sur l’audience : 
    - Signal.Action.Name : indique les détails de l’activité.
    - Signal.User.Id : utilisé pour le mappage avec l’ID client.
    - Signal.View.Uri : utilisé comme adresse web de base pour les segments ou les mesures.
    - Signal.Export.Id : utilisé comme clé primaire pour les événements.
    - Signal.Timestamp : détermine la date et l’heure de l’activité.

Sélectionnez les filtres pour vous concentrer sur les événements et les pages qui comptent pour votre cas d’utilisation. Dans cet exemple, nous utiliserons le nom de l’action « Promotion par e-mail ».

## <a name="export-the-refined-web-events"></a>Exporter les événements web affinés 

Une fois l’événement affiné défini, vous devez configurer l’exportation des données de l’événement vers Azure Data Lake Storage, qui peut être défini comme source de données pour l’ingestion dans Audience Insights. Les exportations se produisent constamment à mesure que les événements découlent de la propriété web.

Pour plus d’informations, voir [Exporter les événements](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Ingérer des données d’événement dans les informations sur l’audience

Maintenant que vous avez défini l’événement raffiné et configuré son exportation, nous passons à l’ingestion des données dans les informations sur l’audience. Vous devez créer une source de données basée sur un dossier Common Data Model. Entrez les détails du compte de stockage vers lequel vous exportez les événements. Dans le fichier *default.cdm.json*, sélectionnez l’événement raffiné à ingérer et créez l’entité dans les informations sur l’audience.

Pour plus d’informations, voir [Se connecter à un dossier Common Data Model à l’aide d’un compte Azure Data Lake](connect-common-data-model.md).


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Associer des données d’événements raffinées à une activité d’un profil client

Une fois l’ingestion d’entité terminée, vous pouvez configurer l’activité pour le profil client.

Pour plus d’informations, voir [Activités client](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Page d’activités avec le volet Modifier l’activité développé et les champs remplis.":::

Configurez la nouvelle activité avec le mappage suivant : 

- **Clé primaire** : Signal.Export.Id, identifiant unique disponible pour chaque enregistrement d’événement dans les informations d’engagement. Cette propriété est générée automatiquement.

- **Horodatage** : Signal.Timestamp dans la propriété de l’événement.

- **Événement** : Signal.Name, nom de l’événement à suivre.

- **Adresse web** : Signal.View.Uri faisant référence à l’URI de la page qui a créé l’événement.

- **Détails** : Signal.Action.Name pour représenter les informations à associer à l’événement. La propriété sélectionnée dans ce cas indique que l’événement est destiné à la promotion par e-mail.

- **Type d’activité** : dans cet exemple, nous choisissons le type d’activité existant WebLog. Cette sélection est une option de filtre utile pour exécuter des modèles prédiction ou créer des segments basés sur ce type d’activité.

- **Configurer la relation** : ce paramètre important lie l’activité aux profils clients existants. **Signal.User.Id** est l’identifiant configuré dans le Kit de développement logiciel (SDK) à collecter et qui se rapporte à l’ID utilisateur dans d’autres sources de données configurées dans les informations sur l’audience. Dans cet exemple, nous configurons la relation entre Signal.User.Id et RetailCustomers:CustomerRetailId, qui est la clé primaire identifiée lors de l’étape de mappage du processus d’unification des données.

Après avoir traité les activités, vous pouvez consulter les enregistrements client et ouvrir une fiche client pour voir les activités à partir des informations sur l’engagement dans la chronologie. 

> [!TIP]
> Pour rechercher un identifiant client associé à une activité d’analyse de l’engagement, accédez à **Entités** et prévisualisez les données de l’entité UnifiedActivity. ActivityTypeDisplay = WebLog contient l’activité d’analyse de l’engagement configurée dans l’exemple ci-dessus. Copiez l’ID client de l’un de ces enregistrements et de cet ID sur la page **Clients**.

## <a name="next-steps"></a>Étapes suivantes

Vous pouvez maintenant créer des [segments](segments.md), des [mesures](measures.md) et des [prédictions](predictions.md) pour établir une connexion significative avec vos clients.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
