---
title: Demandes de droits de la personne concernée dans le cadre du RGPD | Microsoft Docs
description: Répondre aux demandes de droits de la personne concernée pour Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387108"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Demandes de droits de la personne concernée dans le cadre du RGPD

Le règlement général sur la protection des données (RGPD) de l'Union européenne est en vigueur depuis le 25 mai 2018. Il donne des droits importants aux individus sur leurs données. Le RGPD repose sur la protection et l'application des droits à la vie privée des personnes. En savoir plus sur l’engagement de Microsoft en matière de sécurité et de conformité dans le [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Nous nous engageons à aider nos clients à répondre à leurs exigences RGPD. Cela comprend le droit de supprimer ou d’exporter des données qui incluent des informations personnelles telles que les identifiants d’utilisateur, les numéros de téléphone et les adresses e-mail. Les administrateurs peuvent implémenter les demandes des utilisateurs pour supprimer ou exporter des données personnelles.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Répondre aux demandes de suppression de la personne concernée dans le cadre du RGPD pour Customer Insights

Le « droit d’effacement », par la suppression des données personnelles dans les données client d’une entreprise est un élément de protection essentiel du Règlement général sur la protection des données (RGPD). La suppression des données personnelles inclut toutes les données personnelles et journaux générés par le système, à l’exception des informations des journaux d’audit.

### <a name="manage-data-subject-delete-requests"></a>Gestion des demandes de suppression des personnes concernées

Customer Insights offre les expériences intégrées suivantes pour supprimer les données personnelles d’un client ou d’un utilisateur spécifique :

- **Gérer les demandes de suppression de données client** : Les données client dans Customer Insights sont ingérées à partir de sources de données d’origine externes à Customer Insights. Effectuez les demandes de suppression du RGPD dans la source de données d’origine en premier lieu.
- **Gérer les demandes de suppression de données utilisateur de Customer Insights** : les données des utilisateurs sont créées par Customer Insights. Exécutez toutes les demandes de suppression du RGPD dans Customer Insights.

#### <a name="manage-requests-to-delete-customer-data"></a>Gérer les demandes de suppression de données clientes

En tant qu’administrateur Customer Insights, supprimez les données client Customer Insights qui ont été supprimées dans la source de données. Vérifiez que les demandes de suppression du RGPD ont été effectuées dans la source de données d’origine.

1. Connectez-vous à Dynamics 365 Customer Insights.

1. Accédez à **Données** > **Sources de données**.

1. Pour chaque source de données de la liste contenant des données client supprimées, procédez comme suit :
   1. Sélectionnez la source de données, puis **Actualiser**.
   1. Vérifiez le statut de la source de données sous **Statut**. Une coche signifie que l’actualisation a réussi. Un triangle d’avertissement indique que quelque chose n’a pas fonctionné. Si un triangle d’avertissement s’affiche, contactez D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Gestion des demandes de suppression de données client dans le cadre du RGPD.":::

1. Après une actualisation réussie des sources de données, exécutez également les actualisations en aval. Surtout si vous n’avez pas prévu d’actualisation complète et récurrente de Customer Insights.

   > [!IMPORTANT]
   > Les segments statiques ne sont pas inclus dans une actualisation complète ou l’exécution d’actualisations en aval après une demande de suppression. Pour vous assurer que les données client sont également supprimées des segments statiques, recréez les segments statiques avec les données source actualisées.

#### <a name="manage-delete-requests-for-user-data"></a>Gérer les demandes de suppression de données utilisateur

En tant qu’administrateur Customer Insights, supprimez les données d’utilisateur Customer Insights.

1. Connectez-vous à Dynamics 365 Customer Insights.

1. Accédez à **Administrateur** > **Sécurité** > et sélectionnez l’onglet **Utilisateurs**.

1. Activez la case à cocher correspondant aux utilisateurs que vous souhaitez supprimer.

1. Cliquez sur **Supprimer**.

1. Confirmez la suppression.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Répondre aux demandes d’exportation de la personne concernée dans le cadre du RGPD

Le droit à la portabilité des données permet à une personne concernée de demander une copie de ses données personnelles dans un format électronique (à savoir, un format « structuré, répandu, lisible sur ordinateur et interopérable ») transmissible à un autre contrôleur de données.

### <a name="manage-export-and-view-requests"></a>Gérer les demandes de visualisation et d’exportation

Gérer les demandes d’exportation de données client ou utilisateur.

#### <a name="export-customer-data-tenant-admin"></a>Exporter des données client (administrateur du client)

En tant qu’administrateur du client, exportez les données client.

1. Envoyer un e-mail à D365CI@microsoft.com en indiquant l’adresse de messagerie du client dans la demande. L’équipe Customer Insights enverra un e-mail à l’adresse de messagerie enregistrée de l’administrateur du client, en demandant confirmation de l’exportation des données.
2. Acquitter la confirmation de l’exportation des données pour le client demandé.
3. Recevoir les données exportées via l’adresse de messagerie de l’administrateur du client.

#### <a name="export-user-data-tenant-admin"></a>Exporter des données utilisateur (administrateur du client)

En tant qu’administrateur du client, exportez les données d’utilisateur.

1. Envoyer un e-mail à D365CI@microsoft.com en indiquant l’adresse de messagerie de l’utilisateur dans la demande. L’équipe Customer Insights enverra un e-mail à l’adresse de messagerie enregistrée de l’administrateur du client, en demandant confirmation de l’exportation des données.
1. Acquitter la confirmation de l’exportation des données pour l’utilisateur demandé.
1. Recevoir les données exportées via l’adresse de messagerie de l’administrateur du client.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Gestion de la suppression des données dans Dynamics 365 Customer Insights

Les données sont supprimées (partitions de données et instantanés de données) si les partitions de données et les instantanés de données sont inactifs pendant plus de 30 jours, ce qui signifie qu’ils ont été remplacés par une nouvelle partition de données et un nouvel instantané via une actualisation des sources de données.

Toutes les données et tous les instantanés ne sont pas supprimés. La partition de données et l’instantané de données les plus récents sont actifs, car ils sont utilisés dans Customer Insights. Pour les données les plus récentes, peu importe si les sources de données n’ont pas été actualisées au cours des 30 derniers jours.

[!INCLUDE [footer-include](includes/footer-banner.md)]
