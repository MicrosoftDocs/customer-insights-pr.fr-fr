---
title: Exporter des données Customer Insights vers Dynamics 365 Marketing
description: Découvrez comment configurer la connexion à Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269051"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Connecteur pour Dynamics 365 Marketing (préversion)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilisez des [segments](segments.md) pour générer des campagnes et contacter des groupes de clients spécifiques avec Dynamics 365 Marketing. Pour plus d’informations, voir [Utiliser des segments de Dynamics 365 Customer Insights avec Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments).

## <a name="prerequisite"></a>Conditions préalables

- Les enregistrements de contact doivent être présents dans Dynamics 365 Marketing avant de pouvoir exporter un segment de Customer Insights vers Marketing. En savoir plus sur la façon d’intégrer des contacts dans [Dynamics 365 Marketing utilisant Common Data Services](connect-power-query.md).

  > [!NOTE]
  > L’exportation de segments des informations sur l’audience vers Marketing ne créera pas des enregistrements de contact dans les instances Marketing. Les enregistrements de contact de Marketing doivent être intégrés aux informations sur l’audience et utilisés comme source de données. Ils doivent également être inclus dans l’entité Client unifiée pour mapper les ID client avec les ID de contact avant que les segments puissent être exportés.

## <a name="configure-the-connector-for-marketing"></a>Configurer le connecteur pour Marketing

1. Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.

1. Sous **Dynamics 365 Marketing**, sélectionnez **Configurer**.

1. Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.

1. Entrez l’URL marketing de votre organisation dans le champ **Adresse du serveur**.

1. Dans la section **Compte administrateur du serveur**, sélectionnez **Se connecter** et choisissez un compte Dynamics 365 Marketing.

1. Mappez un champ d’ID de client à l’ID de contact Dynamics 365.

1. Cliquez sur **Suivant**.

1. Choisissez un ou plusieurs segments.

1. Sélectionnez **Enregistrer**.

## <a name="export-the-data"></a>Exporter les données

Vous pouvez [exporter les données à la demande](export-destinations.md). L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]