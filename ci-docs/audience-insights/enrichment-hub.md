---
title: Enrichir les profils clients unifiés
description: Utilisez des fonctionnalités pour enrichir vos données client.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667091"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enrichissement des profils clients (aperçu)

Utilisez des données provenant de sources telles que Microsoft et d'autres partenaires pour enrichir vos données client.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Page du Centre d'enrichissement":::

Dans Audience Insights, accédez à **Données** > **Enrichissement** pour utiliser les options d'enrichissement.    
Vous devez disposer des autorisations Collaborateur ou Administrateur pour créer ou modifier des enrichissements. Pour plus d’informations, voir [Autorisations](permissions.md).

Sur l'onglet **Découvrir**, vous trouverez les enrichissements suivants :

- [Marques](enrichment-microsoft-graph.md) fournies par Microsoft Graph.
- [Centres d'intérêt](enrichment-microsoft-graph.md) fournis par Microsoft Graph.
- [Données de la société](enrichment-leadspace.md) fournies par Leadspace
- [Données démographiques](enrichment-experian.md) fournies par Experian
- [Données de localisation](enrichment-here.md) fournies par HERE Technologies
- [Données personnalisées](enrichment-SFTP-custom-import.md) via SFTP (Secure File Transfer Protocol)

Sur l'onglet **Mes enrichissements**, vous pouvez voir les enrichissements que vous avez configurés et modifier leurs propriétés.

## <a name="manage-existing-enrichments"></a>Gérer les enrichissements existants

Allez à **Mes enrichissements** pour voir tous les enrichissements configurés. Chaque enrichissement est représenté sous la forme d'une ligne contenant des informations supplémentaires sur l'enrichissement.

Sélectionnez un enrichissement pour voir les options disponibles. Vous pouvez également sélectionner les points de suspension (...) sur un élément de liste pour voir les options.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Options pour gérer les enrichissements dans la liste des enrichissements":::

- **Affichez** les détails de l'enrichissement avec le nombre de profils clients enrichis.
- **Modifiez** la configuration de l'enrichissement.
- **Exécutez** l'enrichissement pour mettre à jour les profils clients avec les dernières données.
- **Désactivez** un enrichissement existant pour empêcher qu'il s'actualise automatiquement à chaque actualisation programmée. Les données de la dernière actualisation réussie resteront disponibles. **Activez** un enrichissement inactif pour redémarrer l'actualisation automatique à chaque actualisation programmée.
- **Supprimez** un enrichissement.

Vous pouvez exécuter ou désactiver plusieurs enrichissements à la fois en les sélectionnant dans la liste. Les options d'affichage et de modification ne sont pas disponibles en tant qu'action en bloc et ne fonctionnent que pour un enrichissement à la fois.
