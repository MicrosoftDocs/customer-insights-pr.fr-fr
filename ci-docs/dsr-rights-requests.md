---
title: Demandes de droits de la personne concernée dans le cadre du RGPD | Microsoft Docs
description: Répondez aux demandes de la personne concernée pour la fonctionnalité d’informations sur l’audience de Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350266"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Demandes de droits de la personne concernée dans le cadre du RGPD

Le règlement général sur la protection des données (RGPD) de l'Union européenne est en vigueur depuis le 25 mai 2018. Il donne des droits importants aux individus sur leurs données. Le RGPD repose sur la protection et l'application des droits à la vie privée des personnes. Vous pouvez en savoir plus sur l’engagement de Microsoft en matière de sécurité et de conformité dans le [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Nous nous engageons à aider nos clients à répondre à leurs exigences RGPD. Cela comprend le droit de supprimer et d'exporter des données qui incluent des informations personnelles telles que les identifiants d'utilisateur, les numéros de téléphone et les adresses e-mail. Les administrateurs peuvent implémenter les demandes des utilisateurs pour supprimer ou exporter des données personnelles.

## <a name="audience-insights"></a>Informations sur l’audience

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Répondre aux demandes de suppression de la personne concernée dans le cadre du RGPD pour la fonctionnalité d’informations sur l’audience de Dynamics 365 Customer Insights

Le « droit d’effacement », par la suppression des données personnelles dans les données client d’une entreprise est un élément de protection essentiel du Règlement général sur la protection des données (RGPD). La suppression des données personnelles inclut toutes les données personnelles et journaux générés par le système, à l’exception des informations des journaux d’audit.

#### <a name="manage-data-subject-delete-requests"></a>Gestion des demandes de suppression des personnes concernées

Les informations sur l’audience offrent les fonctionnalités intégrées suivantes pour supprimer les données personnelles d’un client ou d’un utilisateur spécifique :

- **Gérer les demandes de suppression de données client** : Les données client dans Customer Insights sont ingérées à partir de sources de données d’origine externes à Customer Insights. Toutes les demandes de suppression du RGPD doivent être effectuées dans la source de données d’origine.
- **Gérer les demandes de suppression de données utilisateur de Customer Insights** : les données des utilisateurs sont créées par Customer Insights. Toutes les demandes de suppression du RGPD doivent être effectuées dans Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Gérer les demandes de suppression de données clientes

Un administrateur Customer Insights peut suivre ces étapes pour supprimer les données client qui ont été supprimées dans le source de données :

1. Connectez-vous à Dynamics 365 Customer Insights.
2. Dans les informations sur l’audience, accédez à **Données** > **Sources de données**
3. Pour chaque source de données de la liste contenant des données client supprimées, procédez comme suit :
   1. Sélectionnez (...), puis sélectionnez **Actualiser**.
   2. Vérifiez le statut de la source de données sous **Statut**. Une coche signifie que l’actualisation a réussi. Un triangle d’avertissement indique que quelque chose n’a pas fonctionné. Si un triangle d’avertissement s’affiche, contactez D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Gestion des demandes de suppression de données client dans le cadre du RGPD.](audience-insights/media/gdpr-data-sources.png "Gestion des demandes de suppression de données client dans le cadre du RGPD")

##### <a name="manage-delete-requests-for-user-data"></a>Gérer les demandes de suppression de données utilisateur

Un administrateur Customer Insights peut procéder de la manière suivante pour supprimer les données d’utilisateur Customer Insights :

1. Connectez-vous à Dynamics 365 Customer Insights.
2. Dans les informations sur l’audience, accédez à **Administration** > **Autorisations**.
3. Activez la case à cocher correspondant à l’utilisateur que vous souhaitez supprimer.
4. Sélectionnez **Supprimer**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Répondre aux demandes d’exportation de la personne concernée dans le cadre du RGPD

Dans le cadre de notre engagement à vous accompagner le long de votre parcours de conformité au Règlement général sur la protection des données (RGPD), nous avons élaboré une documentation pour vous aider à vous préparer. Cette documentation décrit les étapes que vous pouvez suivre pour assurer la conformité au RGPD lorsque vous utilisez les informations sur l’audience.

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

## <a name="consent-management-preview"></a>Gestion du consentement (version préliminaire)

La capacité de gestion du consentement ne collecte pas directement les données des utilisateurs. Elle n’importe et ne traite que les données de consentement fournies par les utilisateurs dans d’autres applications.

Pour supprimer les données de consentement concernant des utilisateurs spécifiques, supprimez-les dans les sources de données ingérées dans la fonctionnalité de gestion du consentement. Après avoir actualisé le source de données, les données supprimées sont également supprimées dans le Centre de consentement. Les applications qui utilisent l’entité de consentement suppriment également les données qui ont été supprimées de la source après une [actualisation](audience-insights/system.md#refresh-processes). Nous vous recommandons d’actualiser rapidement les sources de données après avoir répondu à une demande de personne concernée pour supprimer les données de l’utilisateur de tous les autres processus et applications.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]