---
title: Enrichir les profils clients unifiés
description: Utilisez des fonctionnalités pour enrichir vos données client.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 3bbe8b829a6698da55d84709dbab6c36aa76792a
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954038"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enrichissement des profils clients (aperçu)

Utilisez des données provenant de sources telles que Microsoft et d’autres partenaires pour enrichir vos données client.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Page du Centre d’enrichissement.":::

Accédez à **Données** > **Enrichissement** pour utiliser les options d’enrichissement.  

Vous devez disposer des autorisations Collaborateur ou Administrateur pour créer ou modifier des enrichissements. Pour plus d’informations, voir [Autorisations](permissions.md).

Sous l’onglet **Découvrir**, vous trouverez toutes les options d’enrichissement prises en charge.

# <a name="individual-consumers-b-to-c"></a>[Consommateurs individuels (B-to-C)](#tab/b2c)

- [Identité AbiliTec](enrichment-liveramp.md) fournie par LiveRamp AbiliTec
- [Marques](enrichment-microsoft.md) fournies par Microsoft
- [Données démographiques](enrichment-experian.md) fournies par Experian
- [Adresses améliorées](enrichment-enhanced-addresses.md) fournies par Microsoft
- [Intérêts](enrichment-microsoft.md) fournis par Microsoft
- [Données d'emplacement](enrichment-azure-maps.md) fourni par Microsoft Azure Maps
- [Données de localisation](enrichment-here.md) fournies par HERE Technologies
- [Données personnalisées SFTP](enrichment-SFTP-custom-import.md) via SFTP (Secure File Transfer Protocol)

# <a name="business-accounts-b-to-b"></a>[Comptes d’entreprise (B-to-B)](#tab/b2b)

- [Données d’engagement de compte](enrichment-office.md) fournies par Microsoft
- [Données d’entreprise](enrichment-dnb.md) fournies par Dun & Bradstreet
- [Données de la société](enrichment-leadspace.md) fournies par Leadspace
- [Adresses améliorées](enrichment-enhanced-addresses.md) fournies par Microsoft
- [Données d'entreprise améliorées](enrichment-enhanced-company-data.md) fournies par Microsoft
- [Données d'emplacement](enrichment-azure-maps.md) fourni par Microsoft Azure Maps
- [Données de localisation](enrichment-here.md) fournies par HERE Technologies
- [Données personnalisées SFTP](enrichment-SFTP-custom-import.md) via SFTP (Secure File Transfer Protocol)

---

Sur l’onglet **Mes enrichissements**, vous pouvez voir les enrichissements que vous avez configurés et modifier leurs propriétés. Vous pouvez également créer des [segments](segments.md) ou des [mesures](measures.md) à partir des enrichissements.

## <a name="manage-existing-enrichments"></a>Gérer les enrichissements existants

Accédez à l’onglet **Mes enrichissements** pour voir tous les enrichissements configurés. Chaque enrichissement est représenté sous la forme d’une ligne contenant des informations supplémentaires sur l’enrichissement.

Sélectionnez l’enrichissement pour voir les options disponibles. Vous pouvez également sélectionner les points de suspension verticaux (&vellip;) d’un élément de liste pour voir les options. Si vous avez configuré plusieurs enrichissements, vous pouvez utiliser le champ de recherche pour le retrouver rapidement.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Options pour gérer les enrichissements dans la liste des enrichissements.":::

- **Affichez** les détails de l’enrichissement avec le nombre de profils clients enrichis.
- **Modifiez** la configuration de l’enrichissement.
- **Exécutez** l’enrichissement pour mettre à jour les profils clients avec les dernières données.
- **Désactivez** un enrichissement existant pour empêcher qu’il s’actualise automatiquement à chaque actualisation programmée. (Les données de la dernière actualisation réussie restent disponibles.) **Activez** un enrichissement inactif pour redémarrer l’actualisation automatique à chaque actualisation programmée.
- **Supprimez** l’enrichissement.

Exécutez ou désactivez plusieurs enrichissements simultanément en les sélectionnant dans la liste. Les options d’affichage et de modification ne sont pas disponibles en tant qu’action groupée. Elles ne fonctionnent que pour un enrichissement à la fois.

## <a name="enrichments-and-connections"></a>Enrichissements et connexions

Les enrichissements tiers sont configurés à l’aide de [connexions](connections.md), qu’un administrateur configure avec les informations d’identification et donne son consentement pour les transferts de données. Les connexions peuvent être utilisées par les administrateurs et les contributeurs pour configurer les enrichissements.  

## <a name="multiple-enrichments-of-the-same-type"></a>Enrichissements multiples du même type

L’entité à enrichir est spécifiée lors de la configuration de l’enrichissement, ce qui vous permet d’enrichir uniquement un sous-ensemble de vos profils. Par exemple, enrichissez les données uniquement pour un segment spécifique. Vous pouvez configurer plusieurs enrichissements du même type et réutiliser la même connexion. Certains enrichissements auront des limites au nombre d’enrichissements du même type pouvant être créés. Les limites et l'utilisation actuelle peuvent être vues sur chaque mosaïque dans l'onglet **Découvrir** sur la page **Enrichissement**.

## <a name="enrich-data-sources-before-unification"></a>Enrichir les sources de données avant l’unification

Vous pouvez enrichir vos données client avant l’unification des données pour améliorer la qualité d’une correspondance de données. Pour plus d’informations, voir [enrichissement de source de données](data-sources-enrichment.md).

## <a name="run-or-refresh-enrichments"></a>Exécuter ou actualiser des enrichissements

1. Pour démarrer le processus d'enrichissement, sélectionnez **Exécuter**. Ou laissez le système exécuter l’enrichissement automatiquement dans le cadre d’une [actualisation programmée](system.md#schedule-tab). Le temps de traitement dépend de la taille de vos données client.

1. En option, [voir l'avancement du processus d'enrichissement](#see-the-progress-of-the-enrichment-process).

1. Une fois le processus d'enrichissement terminé, accédez à **Mes enrichissements** pour examiner les données des profils clients nouvellement enrichis, l'heure de la dernière mise à jour et le nombre de profils enrichis.

1. Sélectionnez l'enrichissement pour afficher les [résultats d'enrichissement](#enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Voir la progression du processus d’enrichissement

Vous trouverez des détails sur le traitement d’un enrichissement, y compris son statut et les problèmes potentiels pendant son actualisation ou à la fin d’une actualisation. Comprenez les processus impliqués pour actualiser un enrichissement et leur durée d’exécution. Le statut d’enrichissement est pris en charge pour Experian, Leadspace, HERE Technologies, SFTP Import et Azure Maps.

1. Accédez à **Données** > **Enrichissement**.
1. Dans l'onglet **Mes enrichissements**, sélectionnez le statut de l'enrichissement pour ouvrir un volet latéral.
1. Dans le volet **Détails de la progression**, développez la section **Enrichissements**.
1. Sous l’enrichissement dont vous souhaitez voir la progression, sélectionnez **Voir les détails**.
1. Dans le volet **Détails de la tâche**, sélectionnez **Afficher les détails** pour voir les processus impliqués dans la mise à jour de l’enrichissement et leur statut.

## <a name="enrichment-results"></a>Résultats d’enrichissement

Une fois l’exécution de l’enrichissement terminée, consultez les résultats de l’enrichissement.

1. Accédez à **Données** > **Enrichissement**.
1. Dans l'onglet **Mes enrichissements**, sélectionnez l'enrichissement sur lequel vous souhaitez obtenir des informations.

Tous les enrichissements affichent des informations de base comme le nombre de profils enrichis et le nombre de profils enrichis dans le temps. La vignette **Aperçu clients enrichis** montre un échantillon de l'entité d'enrichissement générée. Pour afficher une vue détaillée, sélectionnez **Afficher plus** et sélectionnez l’onglet **Données**.

:::image type="content" source="media/enrichments-results.png" alt-text="Page de résultats des enrichissements.":::

S’il est disponible, le **Nombre de clients enrichis par champ** fournit une analyse détaillée de la couverture de chaque champ enrichi.

Certains enrichissements affichent également des informations spécifiques au type d’enrichissement. Pour plus d'informations, consultez la documentation associée.

[!INCLUDE [footer-include](includes/footer-banner.md)]
