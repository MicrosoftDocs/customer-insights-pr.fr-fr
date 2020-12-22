---
title: Demandes de droits de la personne concernée dans le cadre du RGPD | Microsoft Docs
description: Répondez aux demandes de la personne concernée pour la fonctionnalité Audience Insights de Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405667"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Demandes de droits de la personne concernée dans le cadre du RGPD

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Répondre aux demandes de suppression de la personne concernée dans le cadre du RGPD pour la fonctionnalité Audience Insights de Dynamics 365 Customer Insights

Le « droit d'effacement », par la suppression des données personnelles dans les données client d'une entreprise est un élément de protection essentiel du Règlement général sur la protection des données (RGPD). La suppression des données personnelles inclut toutes les données personnelles et journaux générés par le système, à l'exception des informations des journaux d'audit.

### <a name="manage-data-subject-delete-requests"></a>Gestion des demandes de suppression des personnes concernées

Audience Insights offre les fonctionnalités intégrées suivantes pour supprimer les données personnelles d'un client ou d'un utilisateur spécifique :

- **Gérer les demandes de suppression de données client** : Les données client dans Customer Insights sont ingérées à partir de sources de données d'origine externes à Customer Insights. Toutes les demandes de suppression du RGPD doivent être effectuées dans la source de données d'origine.
- **Gérer les demandes de suppression de données utilisateur de Customer Insights** : les données des utilisateurs sont créées par Customer Insights. Toutes les demandes de suppression du RGPD doivent être effectuées dans Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Gérer les demandes de suppression de données client

Un administrateur Customer Insights peut suivre ces étapes pour supprimer les données client qui ont été supprimées dans le source de données :

1. Connectez-vous à Dynamics 365 Customer Insights.
2. Dans Audience Insights, accédez à **Données** > **Sources de données**
3. Pour chaque source de données de la liste contenant des données client supprimées, procédez comme suit :
   1. Sélectionnez (...), puis sélectionnez **Actualiser**.
   2. Vérifiez le statut de la source de données sous **Statut**. Une coche signifie que l'actualisation a réussi. Un triangle d'avertissement indique que quelque chose n'a pas fonctionné. Si un triangle d'avertissement s'affiche, contactez D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Gestion des demandes de suppression de données client dans le cadre du RGPD](media/gdpr-data-sources.png "Gestion des demandes de suppression de données client dans le cadre du RGPD")

#### <a name="manage-delete-requests-for-user-data"></a>Gérer les demandes de suppression de données utilisateur

Un administrateur Customer Insights peut procéder de la manière suivante pour supprimer les données d'utilisateur Customer Insights :

1. Connectez-vous à Dynamics 365 Customer Insights.
2. Dans Audience Insights, accédez à **Administration** > **Autorisations**.
3. Activez la case à cocher correspondant à l'utilisateur que vous souhaitez supprimer.
4. Cliquez sur **Supprimer**.

> [!div class="mx-imgBorder"]
> ![Gestion des demandes de suppression de données utilisateur dans le cadre du RGPD](media/gdpr-permissions.png "Gestion des demandes de suppression de données utilisateur dans le cadre du RGPD")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Répondre aux demandes d'exportation de la personne concernée dans le cadre du RGPD

Dans le cadre de notre engagement à vous accompagner le long de votre parcours de conformité au Règlement général sur la protection des données (RGPD), nous avons élaboré une documentation pour vous aider à vous préparer. Cette documentation décrit les étapes que vous pouvez suivre pour assurer la conformité au RGPD lorsque vous utilisez Audience Insights.

### <a name="manage-export-and-view-requests"></a>Gérer les demandes de visualisation et d'exportation

Le droit à la portabilité des données permet à une personne concernée de demander une copie de ses données personnelles dans un format électronique (à savoir, un format « structuré, répandu, lisible sur ordinateur et interopérable ») transmissible à un autre contrôleur de données.

#### <a name="export-customer-data-tenant-admin"></a>Exporter des données client (administrateur du client)

Un administrateur du client peut exécuter la procédure suivante pour exporter des données :

1. Envoyer un e-mail à D365CI@microsoft.com en indiquant l'adresse de messagerie du client dans la demande. L'équipe Customer Insights enverra un e-mail à l'adresse de messagerie enregistrée de l'administrateur du client, en demandant confirmation de l'exportation des données.
2. Acquitter la confirmation de l'exportation des données pour le client demandé.
3. Recevoir les données exportées via l'adresse de messagerie de l'administrateur du client.

#### <a name="export-user-data-tenant-admin"></a>Exporter des données utilisateur (administrateur du client)

1. Envoyer un e-mail à D365CI@microsoft.com en indiquant l'adresse de messagerie de l'utilisateur dans la demande. L'équipe Customer Insights enverra un e-mail à l'adresse de messagerie enregistrée de l'administrateur du client, en demandant confirmation de l'exportation des données.
2. Acquitter la confirmation de l'exportation des données pour l'utilisateur demandé.
3. Recevoir les données exportées via l'adresse de messagerie de l'administrateur du client.
