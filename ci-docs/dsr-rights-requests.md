---
title: Demandes de droits de la personne concernée dans le cadre du RGPD | Microsoft Docs
description: Répondez aux demandes de la personne concernée pour la fonctionnalité d’informations sur l’audience de Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732677"
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


## <a name="engagement-insights-preview"></a>Insights sur l’engagement (version préliminaire)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Suppression et exportation de données liées aux événements contenant des informations identifiables par l'utilisateur final

Les sections suivantes décrivent comment supprimer et exporter des données liées aux événements susceptibles de contenir des données personnelles.

Pour supprimer ou exporter des données :

1. Marquez les propriétés d'événement qui contiennent des données avec des informations personnelles.
2. Supprimez ou exportez les données associées à des valeurs spécifiques (par exemple : un ID utilisateur spécifié).

#### <a name="tag-and-update-event-properties"></a>Marquer et mettre à jour les propriétés des événements

Les données personnelles sont marquées au niveau de la propriété d'événement. Commencez par marquer les propriétés à supprimer ou exporter.

Pour marquer une propriété d'événement comme contenant des informations personnelles, procédez comme suit :

1. Ouvrez l'espace de travail contenant l'événement.

1. Allez dans **Données** > **Événements** pour voir la liste des événements dans l'espace de travail sélectionné.
  
1. Sélectionnez l'environnement à marquer.

1. Sélectionnez **Modifier les propriétés** pour ouvrir le volet répertoriant toutes les propriétés de l'événement sélectionné.
     
1. Sélectionnez **...** puis choisissez **Modifier** pour accéder à la boîte de dialogue **Mettre à jour la propriété**.

   ![Modifier l’événement.](engagement-insights/media/edit-event.png "Modifier l’événement")

1. Dans la fenêtre **Mettre à jour la propriété**, choisissez **...** dans le coin supérieur droit, puis choisissez la zone **Contient EUII**. Choisissez **Mettre à jour** pour enregistrer vos modifications.

   ![Enregistrez vos modifications.](engagement-insights/media/update-property.png "Enregistrer vos modifications")

   > [!NOTE]
   > Chaque fois que le schéma d'événement change ou que vous créez un événement, il est recommandé d'évaluer les propriétés d'événement associées et de les marquer ou de les décocher comme contenant des données personnelles, si nécessaire.

#### <a name="delete-or-export-tagged-event-data"></a>Supprimer ou exporter des données d'événement marquées

Si toutes les propriétés d'événement ont été correctement marquées comme décrit à l'étape précédente, un administrateur d'environnement peut émettre une demande de suppression sur les données d'événement marquées.

Pour gérer les demandes de suppression ou d'exportation EUII

1. Allez dans **Administrateur** > **Environnement** > **Paramètres**.

1. Dans la section **Gérer les informations identifiables de l'utilisateur final (EUII)**, sélectionnez **Gérer EUII**.

##### <a name="deletion"></a>Suppression

Pour la suppression, vous pouvez saisir une liste d'ID utilisateur séparés par des virgules dans la section **Supprimer les informations d'identification de l'utilisateur final (EUII)**. Ces ID seront ensuite comparés à toutes les propriétés d'événement marquées de tous les projets de l'environnement actuel via une correspondance de chaîne exacte. 

Si une valeur de propriété correspond à l'un des ID fournis, l'événement associé sera définitivement supprimé. En raison de l'irréversibilité de cette action, vous devez confirmer la suppression après avoir sélectionné **Supprimer**.

##### <a name="export"></a>Export

Le processus d'exportation est identique au processus de suppression lorsqu'il s'agit de définir les valeurs de propriété d'événement dans la section **Exporter les informations d'identification de l'utilisateur final (EUII)**. De plus, vous devrez fournir une **URL de stockage d'objets blob Azure** pour spécifier la destination d'exportation. L'URL de l'objet blob Azure doit inclure une [Signature d'accès partagé (SAS)](/azure/storage/common/storage-sas-overview).

Après avoir sélectionné **Exporter**, tous les événements de l'équipe actuelle contenant des propriétés marquées correspondantes seront exportés au format CSV vers la destination d'exportation.

### <a name="good-practices"></a>Meilleures pratiques

* Essayez d'éviter d'envoyer des événements contenant des données personnelles.
* Si vous devez envoyer des événements contenant des données EUII, limitez le nombre d'événements et de propriétés d'événement contenant des données EUII. Idéalement, limitez-vous à un de ces événements.
* Assurez-vous que le moins de personnes possible aient accès aux données personnelles envoyées.
* Pour les événements contenant des données personnelles, assurez-vous de définir une propriété pour émettre un identifiant unique qui peut facilement être lié à un utilisateur spécifique (par exemple, un ID utilisateur). Cela facilite la séparation des données et l'exportation ou la suppression des bonnes données.
* Marquez une seule propriété par événement comme contenant des données personnelles. Idéalement, celle qui ne contient qu'un identifiant unique.
* Ne marquez pas les propriétés contenant des valeurs détaillées (par exemple, un corps de requête entier). La fonction Informations sur l’engagement utilise la correspondance exacte des chaînes lors du choix des événements à supprimer ou à exporter.

[!INCLUDE[footer-include](includes/footer-banner.md)]