---
title: Demandes de droits de la personne concernée dans le cadre du RGPD | Microsoft Docs
description: Répondre aux demandes de droits de la personne concernée pour Dynamics 365 Customer Insights.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c71305ab835b0f4f75adcce716e795959f898e47
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947365"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Demandes de droits de la personne concernée dans le cadre du RGPD

Le règlement général sur la protection des données (RGPD) de l'Union européenne est en vigueur depuis le 25 mai 2018. Il donne des droits importants aux individus sur leurs données. Le RGPD repose sur la protection et l'application des droits à la vie privée des personnes. Vous pouvez en savoir plus sur l’engagement de Microsoft en matière de sécurité et de conformité dans le [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Nous nous engageons à aider nos clients à répondre à leurs exigences RGPD. Cela comprend le droit de supprimer et d'exporter des données qui incluent des informations personnelles telles que les identifiants d'utilisateur, les numéros de téléphone et les adresses e-mail. Les administrateurs peuvent implémenter les demandes des utilisateurs pour supprimer ou exporter des données personnelles.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Réponse aux demandes de suppression des données de la personne concernée dans le cadre du RGPD pour Dynamics 365 Customer Insights

Le « droit d’effacement », par la suppression des données personnelles dans les données client d’une entreprise est un élément de protection essentiel du Règlement général sur la protection des données (RGPD). La suppression des données personnelles inclut toutes les données personnelles et journaux générés par le système, à l’exception des informations des journaux d’audit.

#### <a name="manage-data-subject-delete-requests"></a>Gestion des demandes de suppression des personnes concernées

Customer Insights offre les expériences intégrées suivantes pour supprimer les données personnelles d’un client ou d’un utilisateur spécifique :

- **Gérer les demandes de suppression de données client** : Les données client dans Customer Insights sont ingérées à partir de sources de données d’origine externes à Customer Insights. Toutes les demandes de suppression du RGPD doivent être effectuées dans la source de données d’origine.
- **Gérer les demandes de suppression de données utilisateur de Customer Insights** : les données des utilisateurs sont créées par Customer Insights. Toutes les demandes de suppression du RGPD doivent être effectuées dans Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Gérer les demandes de suppression de données clientes

Un administrateur Customer Insights peut suivre ces étapes pour supprimer les données client qui ont été supprimées dans le source de données :

1. Connectez-vous à Dynamics 365 Customer Insights.
2. Accédez à **Données** > **Sources de données**
3. Pour chaque source de données de la liste contenant des données client supprimées, procédez comme suit :
   1. Sélectionnez les points de suspension verticaux (&vellip;), puis sélectionnez **Actualiser**.
   2. Vérifiez le statut de la source de données sous **Statut**. Une coche signifie que l’actualisation a réussi. Un triangle d’avertissement indique que quelque chose n’a pas fonctionné. Si un triangle d’avertissement s’affiche, contactez D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Gestion des demandes de suppression de données client dans le cadre du RGPD.](media/gdpr-data-sources.png "Gestion des demandes de suppression de données client dans le cadre du RGPD")

##### <a name="manage-delete-requests-for-user-data"></a>Gérer les demandes de suppression de données utilisateur

Un administrateur Customer Insights peut procéder de la manière suivante pour supprimer les données d’utilisateur Customer Insights :

1. Connectez-vous à Dynamics 365 Customer Insights.
2. Accédez à **Administrateur** > **Sécurité** > **Autorisations**.
3. Activez la case à cocher correspondant à l’utilisateur que vous souhaitez supprimer.
4. Sélectionnez **Supprimer**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Répondre aux demandes d’exportation de la personne concernée dans le cadre du RGPD

Dans le cadre de notre engagement à vous accompagner dans l’implémentation du Règlement général sur la protection des données (RGPD), nous avons élaboré une documentation pour vous aider à répondre aux demandes des personnes concernées.

#### <a name="manage-export-and-view-requests"></a>Gérer les demandes de visualisation et d’exportation

Le droit à la portabilité des données permet à une personne concernée de demander une copie de ses données personnelles dans un format électronique (à savoir, un format « structuré, répandu, lisible sur ordinateur et interopérable ») transmissible à un autre contrôleur de données.

##### <a name="export-customer-data-tenant-admin"></a>Exporter des données client (administrateur du client)

Un administrateur du client peut exécuter la procédure suivante pour exporter des données :

1. Envoyer un e-mail à D365CI@microsoft.com en indiquant l’adresse de messagerie du client dans la demande. L’équipe Customer Insights enverra un e-mail à l’adresse de messagerie enregistrée de l’administrateur du client, en demandant confirmation de l’exportation des données.
2. Acquitter la confirmation de l’exportation des données pour le client demandé.
3. Recevoir les données exportées via l’adresse de messagerie de l’administrateur du client.

##### <a name="export-user-data-tenant-admin"></a>Exporter des données utilisateur (administrateur du client)

1. Envoyer un e-mail à D365CI@microsoft.com en indiquant l’adresse de messagerie de l’utilisateur dans la demande. L’équipe Customer Insights enverra un e-mail à l’adresse de messagerie enregistrée de l’administrateur du client, en demandant confirmation de l’exportation des données.
2. Acquitter la confirmation de l’exportation des données pour l’utilisateur demandé.
3. Recevoir les données exportées via l’adresse de messagerie de l’administrateur du client.

[!INCLUDE [footer-include](includes/footer-banner.md)]