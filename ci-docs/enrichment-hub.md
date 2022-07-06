---
title: Présentation de l’enrichissement des données (version préliminaire)
description: Utilisez les fonctionnalités de Microsoft et d’autres services tiers pour enrichir vos données clients.
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
ms.openlocfilehash: 6b6daab480db5e37830ff58b71dcdd3bbdbe46da
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053864"
---
# <a name="data-enrichment-preview-overview"></a>Présentation de l’enrichissement des données (version préliminaire)

Utilisez des données provenant de sources telles que Microsoft et d’autres partenaires pour enrichir vos données client. Les enrichissements tiers sont configurés à l’aide de [connexions](connections.md), qu’un administrateur configure avec les informations d’identification et donne son consentement pour les transferts de données. Les connexions peuvent être utilisées par les administrateurs et les contributeurs pour configurer les enrichissements.  

## <a name="multiple-enrichments-of-the-same-type"></a>Enrichissements multiples du même type

L’entité à enrichir est spécifiée lors de la configuration de l’enrichissement, ce qui vous permet d’enrichir uniquement un sous-ensemble de vos profils. Par exemple, enrichissez les données uniquement pour un segment spécifique. Vous pouvez configurer plusieurs enrichissements du même type et réutiliser la même connexion. Certains enrichissements auront des limites au nombre d’enrichissements du même type pouvant être créés. Les limites et l'utilisation actuelle peuvent être vues sur chaque mosaïque dans l'onglet **Découvrir** sur la page **Enrichissement**.

## <a name="enrich-data-sources-before-unification"></a>Enrichir les sources de données avant l’unification

Vous pouvez enrichir vos données client avant l’unification des données pour améliorer la qualité d’une correspondance de données. Pour plus d’informations, voir [enrichissement de source de données](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Créer un enrichissement

Vous devez disposer des [autorisations](permissions.md) Collaborateur ou Administrateur pour créer ou modifier des enrichissements.

Accédez à **Données** > **Enrichissement**. L’onglet **Découvrir** affiche toutes les options d’enrichissement prises en charge.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Page du Centre d’enrichissement.":::

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

## <a name="manage-existing-enrichments"></a>Gérer les enrichissements existants

Accédez à **Données** > **Enrichissement**. Dans l’onglet **Mes enrichissements**, affichez les enrichissements configurés, leur statut, le nombre de clients enrichis et la dernière date d’actualisation des données. Vous pouvez trier la liste des enrichissements par colonne ou utiliser la zone de recherche pour trouver l’enrichissement que vous souhaitez gérer.

Sélectionnez l’enrichissement pour afficher les actions disponibles.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Options pour gérer les enrichissements dans la liste des enrichissements.":::

- **Affichez** les détails de l’enrichissement avec le nombre de profils clients enrichis.
- **Modifiez** la configuration de l’enrichissement.
- [**Exécutez**](#run-or-refresh-enrichments) l’enrichissement pour mettre à jour les profils clients avec les données les plus récentes. Exécutez plusieurs enrichissements simultanément en les sélectionnant dans la liste.
- **Activez** ou **désactivez** un enrichissement. Les enrichissements inactifs ne seront pas actualisés pendant une [actualisation planifiée](system.md#schedule-tab).
- **Supprimez** l’enrichissement.

Vous pouvez également créer des [segments](segments.md) ou des [mesures](measures.md) à partir des enrichissements.

## <a name="run-or-refresh-enrichments"></a>Exécuter ou actualiser des enrichissements

Une fois exécutés, les enrichissements peuvent être actualisés selon une planification automatique ou actualisés manuellement à la demande.

1. Pour actualiser manuellement un ou plusieurs enrichissements, sélectionnez-les et choisissez **Exécuter**. Pour [planifier une actualisation automatique](system.md#schedule-tab), accédez à **Administrateur** > **Système** > **Planification**. Le temps de traitement dépend de la taille de vos données client.

1. En option, [voir l'avancement du processus d'enrichissement](#see-the-progress-of-the-enrichment-process).

1. Une fois le processus d'enrichissement terminé, accédez à **Mes enrichissements** pour examiner les données des profils clients nouvellement enrichis, l'heure de la dernière mise à jour et le nombre de profils enrichis.

1. Sélectionnez l'enrichissement pour afficher les [résultats d'enrichissement](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Voir la progression du processus d’enrichissement

Vous trouverez des détails sur le traitement d’un enrichissement, y compris son statut et les problèmes potentiels pendant son actualisation ou à la fin d’une actualisation. Comprenez les processus impliqués pour actualiser un enrichissement et leur durée d’exécution. Le statut d’enrichissement est pris en charge pour Experian, Leadspace, HERE Technologies, SFTP Import et Azure Maps.

1. Accédez à **Données** > **Enrichissement**.
1. Dans l'onglet **Mes enrichissements**, sélectionnez le statut de l'enrichissement pour ouvrir un volet latéral.
1. Dans le volet **Détails de la progression**, développez la section **Enrichissements**.
1. Sous l’enrichissement dont vous souhaitez voir la progression, sélectionnez **Voir les détails**.
1. Dans le volet **Détails de la tâche**, sélectionnez **Afficher les détails** pour voir les processus impliqués dans la mise à jour de l’enrichissement et leur statut.

## <a name="view-enrichment-results"></a>Afficher les résultats de l’enrichissement

Une fois l’exécution de l’enrichissement terminée, consultez les résultats de l’enrichissement.

1. Accédez à **Données** > **Enrichissement**.
1. Dans l’onglet **Mes enrichissements**, sélectionnez l’enrichissement que vous souhaitez afficher.

Tous les enrichissements affichent des informations de base comme le nombre de profils enrichis et le nombre de profils enrichis dans le temps. La vignette **Aperçu clients enrichis** montre un échantillon de l'entité d'enrichissement générée. Pour afficher une vue détaillée, sélectionnez **Afficher plus** et sélectionnez l’onglet **Données**.

:::image type="content" source="media/enrichments-results.png" alt-text="Page de résultats des enrichissements.":::

S’il est disponible, le **Nombre de clients enrichis par champ** fournit une analyse détaillée de la couverture de chaque champ enrichi.

Certains enrichissements affichent également des informations spécifiques au type d’enrichissement. Pour plus d'informations, consultez la documentation associée.

[!INCLUDE [footer-include](includes/footer-banner.md)]
