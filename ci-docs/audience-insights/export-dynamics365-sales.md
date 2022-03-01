---
title: Exporter des données Customer Insights vers Dynamics 365 Sales
description: Découvrez comment configurer la connexion à Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643815"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Connecteur pour Dynamics 365 Sales (préversion)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Utilisez vos données client pour créer des listes marketing, effectuer le suivi de workflows et publier des promotions avec Dynamics 365 Sales.

## <a name="prerequisite"></a>Éléments requis

Enregistrements de contact [de Dynamics 365 Sales ingérés à l'aide de Common Data Service](connect-power-query.md).

## <a name="configure-the-connector-for-sales"></a>Configurer le connecteur pour Sales

1. Dans Audience Insights, accédez à **Administration** > **Destinations d'exportation**.

1. Sous **Dynamics 365 Sales**, sélectionnez **Configurer**.

1. Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.

1. Entrez l’URL Sales de votre organisation dans le champ **Adresse du serveur**.

1. Dans la section **Compte administrateur du serveur**, sélectionnez **Se connecter** et choisissez un compte Dynamics 365 Sales.

1. Mappez un champ d'ID de client à l'ID de contact Dynamics 365.

1. Cliquez sur **Suivant**.

1. Choisissez un ou plusieurs segments.

1. Sélectionnez **Enregistrer**.

## <a name="export-the-data"></a>Exporter les données

Vous pouvez [exporter les données à la demande](export-destinations.md). L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).
