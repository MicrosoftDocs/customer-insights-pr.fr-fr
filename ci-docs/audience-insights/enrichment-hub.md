---
title: Enrichir les profils clients unifiés
description: Utilisez des fonctionnalités pour enrichir vos données client.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305245"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enrichissement des profils clients (aperçu)

Utilisez des données provenant de sources telles que Microsoft et d’autres partenaires pour enrichir vos données client.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Page du Centre d’enrichissement":::

Dans les informations sur l’audience, accédez à **Données** > **Enrichissement** pour utiliser les options d’enrichissement.  

Vous devez disposer des autorisations Collaborateur ou Administrateur pour créer ou modifier des enrichissements. Pour plus d’informations, voir [Autorisations](permissions.md).

Sur l’onglet **Découvrir**, vous trouverez les enrichissements suivants :

- [Marques](enrichment-microsoft.md) fournies par Microsoft
- [Intérêts](enrichment-microsoft.md) fournis par Microsoft
- [Adresses améliorées](enrichment-enhanced-addresses.md) fournies par Microsoft
- [Données de la société](enrichment-leadspace.md) fournies par Leadspace
- [Données démographiques](enrichment-experian.md) fournies par Experian
- [Données de localisation](enrichment-here.md) fournies par HERE Technologies
- [Données personnalisées](enrichment-SFTP-custom-import.md) via SFTP (Secure File Transfer Protocol)

Sur l’onglet **Mes enrichissements**, vous pouvez voir les enrichissements que vous avez configurés et modifier leurs propriétés.

## <a name="manage-existing-enrichments"></a>Gérer les enrichissements existants

Accédez à l’onglet **Mes enrichissements** pour voir tous les enrichissements configurés. Chaque enrichissement est représenté sous la forme d’une ligne contenant des informations supplémentaires sur l’enrichissement.

Sélectionnez un enrichissement pour voir les options disponibles. Vous pouvez également sélectionner les points de suspension (...) d’un élément de liste pour voir les options.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Options pour gérer les enrichissements dans la liste des enrichissements":::

- **Affichez** les détails de l’enrichissement avec le nombre de profils clients enrichis.
- **Modifiez** la configuration de l’enrichissement.
- **Exécutez** l’enrichissement pour mettre à jour les profils clients avec les dernières données.
- **Désactivez** un enrichissement existant pour empêcher qu’il s’actualise automatiquement à chaque actualisation programmée. (Les données de la dernière actualisation réussie restent disponibles.) **Activez** un enrichissement inactif pour redémarrer l’actualisation automatique à chaque actualisation programmée.
- **Supprimez** un enrichissement.

Vous pouvez exécuter ou désactiver plusieurs enrichissements à la fois en les sélectionnant dans la liste. Les options d’affichage et de modification ne sont pas disponibles en tant qu’action en bloc et ne fonctionnent que pour un enrichissement à la fois.

## <a name="enrichments-and-connections"></a>Enrichissements et connexions

Les enrichissements tiers sont configurés à l’aide de [connexions](connections.md), qu’un administrateur configure avec les informations d’identification et donne son consentement pour les transferts de données. La connexion peut être utilisée par les administrateurs et les contributeurs pour configurer les enrichissements.  

## <a name="multiple-enrichments-of-the-same-type"></a>Enrichissements multiples du même type

L’entité à enrichir est spécifiée lors de la configuration de l’enrichissement, ce qui vous permet d’enrichir uniquement un sous-ensemble de vos profils. Par exemple, enrichissez les données uniquement pour un segment spécifique. Vous pouvez configurer plusieurs enrichissements du même type et réutiliser la même connexion. Certains enrichissements auront des limites au nombre d’enrichissements du même type pouvant être créés. Les limites et l’utilisation actuelle sont visibles sur la page **Enrichissement**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]