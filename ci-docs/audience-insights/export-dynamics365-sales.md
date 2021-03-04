---
title: Exporter des données Customer Insights vers Dynamics 365 Sales
description: Découvrez comment configurer la connexion à Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269005"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Connecteur pour Dynamics 365 Sales (préversion)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilisez vos données client pour créer des listes marketing, effectuer le suivi de workflows et publier des promotions avec Dynamics 365 Sales.

## <a name="prerequisite"></a>Conditions préalables

1. Les enregistrements de contact doivent être présents dans Dynamics 365 Sales avant de pouvoir exporter un segment de Customer Insights vers Sales. En savoir plus sur la façon d’intégrer des contacts dans [Dynamics 365 Sales utilisant Common Data Services](connect-power-query.md).

   > [!NOTE]
   > L’exportation de segments des informations sur l’audience vers Sales ne créera pas des enregistrements de contact dans les instances Sales. Les enregistrements de contact de Sales doivent être intégrés aux informations sur l’audience et utilisés comme source de données. Ils doivent également être inclus dans l’entité Client unifiée pour mapper les ID client avec les ID de contact avant que les segments puissent être exportés.

## <a name="configure-the-connector-for-sales"></a>Configurer le connecteur pour Sales

1. Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.

1. Sous **Dynamics 365 Sales**, sélectionnez **Configurer**.

1. Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.

1. Entrez l’URL Sales de votre organisation dans le champ **Adresse du serveur**.

1. Dans la section **Compte administrateur du serveur**, sélectionnez **Se connecter** et choisissez un compte Dynamics 365 Sales.

1. Mappez un champ d’ID de client à l’ID de contact Dynamics 365.

1. Cliquez sur **Suivant**.

1. Choisissez un ou plusieurs segments.

1. Sélectionnez **Enregistrer**.

## <a name="export-the-data"></a>Exporter les données

Vous pouvez [exporter les données à la demande](export-destinations.md). L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]