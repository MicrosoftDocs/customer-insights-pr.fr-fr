---
title: Exporter les données Customer Insights vers Adobe Experience Platform
description: Découvrez comment utiliser les segments Customer Insights dans Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 42a4e0c6bce67a63b449a541299620ef2f4a3259
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646356"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Utiliser les segments Customer Insights dans Adobe Experience Platform (version préliminaire)

En tant qu’utilisateur de Dynamics 365 Customer Insights, vous avez peut-être créé des segments pour rendre vos campagnes marketing plus efficaces en ciblant des audiences pertinentes. Pour utiliser un segment de Customer Insights dans Adobe Experience Platform et les applications comme Adobe Campaign Standard, vous devez suivre quelques étapes décrites dans cet article.

:::image type="content" source="media/AEP-flow.png" alt-text="Schéma du processus des étapes décrites dans cet article.":::

## <a name="prerequisites"></a>Conditions préalables

-   Licence Dynamics 365 Customer Insights
-   Licence Adobe Experience Platform
-   Licence Adobe Campaign Standard
-   Compte de stockage Blob Azure

## <a name="campaign-overview"></a>Vue d’ensemble de la campagne

Pour mieux comprendre comment vous pouvez utiliser les segments de Customer Insights dans Adobe Experience Platform, examinons un exemple de campagne fictif.

Supposons que votre entreprise offre un service mensuel basé sur un abonnement à vos clients aux États-Unis. Vous souhaitez identifier les clients dont les abonnements doivent être renouvelés dans les huit prochains jours, mais qui n’ont pas encore renouvelé leur abonnement. Pour fidéliser ces clients, vous souhaitez leur faire parvenir par e-mail une offre promotionnelle en utilisant Adobe Experience Platform.

Dans cet exemple, nous souhaitons exécuter la campagne d’e-mails promotionnels une seule fois. Cet article ne couvre pas le cas d’utilisation de l’exécution de la campagne plusieurs fois.

## <a name="identify-your-target-audience"></a>Identifier votre audience cible

Dans notre scénario, nous supposons que les adresses e-mail des clients sont disponibles dans Customer Insights et leurs préférences promotionnelles ont été analysées pour identifier les membres du segment.

Le [segment que vous avez défini dans Customer Insights](segments.md) est appelé **ChurnProneCustomers** et vous prévoyez d’envoyer la promotion à ces clients.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Capture d’écran de la page des segments avec le segment ChurnProneCustomers créé.":::

L’e-mail d’offre que vous souhaitez envoyer contiendra le prénom, le nom et la date de fin d’abonnement du client. Il informe les clients de la réduction qu’ils obtiendront s’ils renouvellent leur abonnement avant qu’il ne se termine.

## <a name="export-your-target-audience"></a>Exporter votre audience cible

Avec notre audience cible identifiée, nous pouvons configurer l’exportation de Customer Insights vers un compte de stockage Blob Azure.

### <a name="configure-a-connection"></a>Configurer une connexion

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Stockage Blob Azure** ou sélectionnez **Configurer** dans la vignette **Stockage Blob Azure** pour configurer la connexion.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Vignette de configuration pour Stockage Blob Azure."::: 

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez le **Nom du compte**, la **Clé du compte** et le **Conteneur** de votre compte de stockage Blob vers lequel vous souhaitez exporter le segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Capture d’écran de la configuration du compte de stockage. "::: 
   
    - Pour obtenir plus d’informations sur la recherche du nom et de la clé du compte de stockage Blob, voir [Gérer les paramètres du compte de stockage dans le portail Azure](/azure/storage/common/storage-account-manage).
    - Pour savoir comment créer un conteneur, voir [Créer un conteneur](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Sélectionnez **Enregistrer** pour terminer la connexion. 

### <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Stockage Blob Azure. Si le nom de la section ne s’affiche pas, aucune connexion de ce type n’est disponible pour vous.

1. Choisissez le segment que vous souhaitez exporter. Dans cet exemple, il s’agit de **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Capture d’écran de l’interface utilisateur de sélection de segment avec le segment ChurnProneCustomers sélectionné.":::

1. Sélectionnez **Enregistrer**.

Une fois la destination d’exportation enregistrée, vous la trouverez dans **Données** > **Exportations**.

Vous pouvez maintenant [exporter le segment à la demande](export-destinations.md#run-exports-on-demand). L'exportation sera également exécutée à chaque [actualisation planifiée](system.md).

> [!NOTE]
> Vérifiez que le nombre d’enregistrements dans le segment exporté se trouve dans la limite autorisée par votre licence Adobe Campaign Standard.

Les données exportées sont stockées dans le conteneur de stockage Blob Azure que vous avez configuré ci-dessus. Le chemin d’accès aux dossiers suivant est créé automatiquement dans votre conteneur :

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Le fichier *model.json* pour les entités exportées réside au niveau *%ExportDestinationName%*.

Exemple : Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Définir le modèle de données d’expérience (XDM) dans Adobe Experience Platform

Avant que les données exportées de Customer Insights puissent être utilisées dans Adobe Experience Platform, nous devons définir le schéma du modèle de données d’expérience et [configurer les données du profil client en temps réel](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Découvrez [le modèle de données d’expérience utilisateur](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) et les [principes de base de la composition de schémas](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importer des données dans Adobe Experience Platform

Maintenant que tout est en place, nous devons importer les données d’audience préparées de Customer Insights dans Adobe Experience Platform.

Tout d’abord, [créez une connexion source Stockage Blob Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Après avoir défini la connexion source, [configurez un flux de données](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pour une connexion par lots au stockage cloud pour importer la sortie du segment de Customer Insights dans Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Créer une audience dans Adobe Campaign Standard

Pour envoyer l’e-mail de cette campagne, nous utilisons Adobe Campaign Standard. Après avoir importé les données dans Adobe Experience Platform, nous devons [créer un audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) dans Adobe Campaign Standard utilisant les données dans Adobe Experience Platform.


Apprenez à [utiliser le générateur de segments](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) dans Adobe Campaign Standard pour définir une audience basée sur les données dans Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Créer et envoyer l’e-mail en utilisant Adobe Campaign Standard

Créez le contenu de l’e-mail, puis [testez et envoyez](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) votre e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemple d’e-mail avec offre de renouvellement provenant d’Adobe Campaign Standard.":::