---
title: Exporter les données Customer Insights vers Adobe Experience Platform
description: Découvrez comment utiliser les segments des informations sur l’audience dans Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596266"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Utiliser les segments Customer Insights dans Adobe Experience Platform (version préliminaire)

En tant qu’utilisateur d’informations sur l’audience pour Dynamics 365 Customer Insights, vous avez peut-être créé des segments pour rendre vos campagnes marketing plus efficaces en ciblant des audiences pertinentes. Pour utiliser un segment des informations sur l’audience dans Adobe Experience Platform et dans des applications comme Adobe Campaign Standard, vous devez suivre quelques étapes décrites dans cet article.

:::image type="content" source="media/AEP-flow.png" alt-text="Schéma du processus des étapes décrites dans cet article.":::

## <a name="prerequisites"></a>Conditions préalables

-   Licence Dynamics 365 Customer Insights
-   Licence Adobe Experience Platform
-   Licence Adobe Campaign Standard
-   Compte de stockage Blob Azure

## <a name="campaign-overview"></a>Vue d’ensemble de la campagne

Pour mieux comprendre comment utiliser des segments des informations sur l’audience dans Adobe Experience Platform, examinons un exemple de campagne fictif.

Supposons que votre entreprise offre un service mensuel basé sur un abonnement à vos clients aux États-Unis. Vous souhaitez identifier les clients dont les abonnements doivent être renouvelés dans les huit prochains jours, mais qui n’ont pas encore renouvelé leur abonnement. Pour fidéliser ces clients, vous souhaitez leur envoyer une offre promotionnelle par e-mail, à l’aide d’Adobe Experience Platform.

Dans cet exemple, nous souhaitons exécuter la campagne d’e-mails promotionnels une seule fois. Cet article ne couvre pas le cas d’utilisation de l’exécution de la campagne plusieurs fois.

## <a name="identify-your-target-audience"></a>Identifier votre audience cible

Dans notre scénario, nous supposons que les adresses e-mail des clients sont disponibles dans les informations sur l’audience et que les préférences promotionnelles des clients ont été analysées pour identifier les membres du segment.

Le [segment que vous avez défini dans les informations sur l’audience](segments.md) est appelé **ChurnProneCustomers** et vous prévoyez d’envoyer à ces clients la promotion par e-mail.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Capture d’écran de la page des segments avec le segment ChurnProneCustomers créé.":::

L’e-mail d’offre que vous souhaitez envoyer contiendra le prénom, le nom et la date de fin d’abonnement du client. Il informe les clients de la réduction qu’ils obtiendront s’ils renouvellent leur abonnement avant qu’il ne se termine.

## <a name="export-your-target-audience"></a>Exporter votre audience cible

Une fois notre audience cible identifiée, nous pouvons configurer l’exportation des informations sur l’audience vers un compte de stockage Blob Azure.

1. Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.

1. Dans la vignette **Stockage Blob Azure**, sélectionnez **Configurer**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Vignette de configuration pour Stockage Blob Azure.":::

1. Renseignez un **Nom d’affichage** pour cette nouvelle destination d’exportation, puis saisissez le **Nom du compte**, la **Clé de compte** et le **Conteneur** du compte de stockage Blob Azure vers lequel vous souhaitez exporter le segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Capture d’écran de la configuration du compte de stockage. "::: 

   - Pour en savoir plus sur la recherche du nom et de la clé de compte de stockage Blob Azure, consultez [Gérer les paramètres du compte de stockage dans le portail Azure](/azure/storage/common/storage-account-manage).

   - Pour savoir comment créer un conteneur, voir [Créer un conteneur](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Cliquez sur **Suivant**.

1. Choisissez le segment que vous souhaitez exporter. Dans cet exemple, il s’agit de **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Capture d’écran de l’interface utilisateur de sélection de segment avec le segment ChurnProneCustomers sélectionné.":::

1. Sélectionnez **Enregistrer**.

Après avoir enregistré la destination d’exportation, vous la trouvez sur **Administration** > **Exportations** > **Mes destinations d’exportation**.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Capture d’écran montrant la liste des exportations et l’exemple de segment en surbrillance.":::

Vous pouvez maintenant [exporter le segment à la demande](export-destinations.md#export-data-on-demand). L'exportation sera également exécutée à chaque [actualisation planifiée](system.md).

> [!NOTE]
> Assurez-vous que le nombre d’enregistrements dans le segment exporté se situe dans la limite autorisée de votre licence Adobe Campaign Standard.

Les données exportées sont stockées dans le conteneur de stockage Blob Azure que vous avez configuré ci-dessus. Le chemin d’accès aux dossiers suivant est créé automatiquement dans votre conteneur :

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Le fichier *model.json* pour les entités exportées réside au niveau *%ExportDestinationName%*.

Exemple : Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Définir le modèle de données d’expérience utilisateur dans Adobe Experience Platform

Avant que les données exportées des informations sur l’audience puissent être utilisées dans Adobe Experience Platform, nous devons définir le schéma du modèle de données d’expérience et [configurer les données pour le profil client en temps réel](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Découvrez [le modèle de données d’expérience utilisateur](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) et les [principes de base de la composition de schémas](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importer des données dans Adobe Experience Platform

Maintenant que tout est en place, nous devons importer les données d’audience préparées à partir des informations sur l’audience dans Adobe Experience Platform.

Tout d’abord, [créez une connexion source Stockage Blob Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Après avoir défini la connexion source, [configurez un dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pour une connexion par lots de stockage cloud afin d’importer la sortie de segment des informations sur l’audience dans Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Créer une audience dans Adobe Campaign Standard

Pour envoyer l’e-mail de cette campagne, nous utiliserons Adobe Campaign Standard. Après avoir importé les données dans Adobe Experience Platform, nous devons [créer un audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) dans Adobe Campaign Standard en utilisant les données d’Adobe Experience Platform.

Découvrez comment [utiliser le générateur de segments](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) dans Adobe Campaign Standard pour définir une audience basée sur les données d’Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Créer et envoyer l’e-mail à l’aide d’Adobe Campaign Standard

Créez le contenu de l’e-mail, puis [testez et envoyez](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) votre e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemple d’e-mail avec l’offre de renouvellement d’Adobe Campaign Standard.":::