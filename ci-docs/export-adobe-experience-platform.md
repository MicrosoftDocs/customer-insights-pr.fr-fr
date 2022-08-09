---
title: Exporter des segments vers Adobe Experience Platform (version préliminaire)
description: Découvrez comment utiliser les segments Customer Insights dans Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195287"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Exporter des segments vers Adobe Experience Platform (version préliminaire)

Exportez des segments qui ciblent des audiences pertinentes vers Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Schéma du processus des étapes décrites dans cet article.":::

## <a name="prerequisites"></a>Conditions préalables

- Une licence Adobe Experience Platform.
- Une licence Adobe Campaign Standard.
- Un nom de [compte Stockage Blob Azure](/azure/storage/blobs/create-data-lake-storage-account) et une clé de compte. Pour rechercher le nom et la clé, consultez [Gérer les paramètres du compte de stockage dans le portail Azure](/azure/storage/common/storage-account-manage).
- Un [conteneur Stockage Blob Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

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

Nous allons configurer l’exportation de Customer Insights vers un compte Azure Blob Storage.

### <a name="set-up-connection-to-azure-blob-storage"></a>Configurer la connexion au Stockage Blob Azure

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion**, puis choisissez **Stockage Blob Azure**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez le **Nom du compte**, la **Clé du compte** et le **Conteneur** de votre compte de stockage Blob vers lequel vous souhaitez exporter le segment.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Capture d’écran de la configuration du compte de stockage. ":::

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

### <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Stockage Blob Azure. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Choisissez le segment que vous souhaitez exporter. Dans cet exemple, il s’agit de **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Capture d’écran de l’interface utilisateur de sélection de segment avec le segment ChurnProneCustomers sélectionné.":::

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Vérifiez que le nombre d’enregistrements dans le segment exporté se trouve dans la limite autorisée par votre licence Adobe Campaign Standard.

Les données exportées sont stockées dans le conteneur de Azure Blog Storage que vous avez configuré. Les chemins d’accès suivants aux dossiers sont créés automatiquement dans votre conteneur :

- Pour les entités sources et les entités générées par le système : 

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- Le fichier *model.json* pour les entités exportées réside au niveau *%ExportDestinationName%*.

  Exemple : Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Définir le modèle de données d’expérience (XDM) dans Adobe Experience Platform

Avant que les données exportées de Customer Insights puissent être utilisées dans Adobe Experience Platform, définissez le schéma du modèle de données d’expérience et [configurez les données du profil client en temps réel](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Découvrez [le modèle de données d’expérience utilisateur](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) et les [principes de base de la composition de schémas](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importer des données dans Adobe Experience Platform

Importez les données d’audience préparées à partir de Customer Insights dans Adobe Experience Platform.

1. [Créez une connexion source Stockage Blob Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Configurez un flux de données](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pour une connexion par lots au stockage cloud pour importer la sortie du segment de Customer Insights dans Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Créer une audience dans Adobe Campaign Standard

Pour envoyer l’e-mail de cette campagne, nous utilisons Adobe Campaign Standard.

1. [Créez une audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) dans Adobe Campaign Standard à l’aide des données dans Adobe Experience Platform.

1. [Utilisez le générateur de segments](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) dans Adobe Campaign Standard pour définir une audience basée sur les données dans Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Créer et envoyer l’e-mail en utilisant Adobe Campaign Standard

Créez le contenu de l’e-mail, puis [testez et envoyez](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) votre e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemple d’e-mail avec offre de renouvellement provenant d’Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
