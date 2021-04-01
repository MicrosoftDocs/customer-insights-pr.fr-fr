---
title: Exporter les données Customer Insights vers Adobe Campaign Standard
description: Découvrez comment utiliser les segments des informations sur l’audience dans Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596312"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Utiliser les segments Customer Insights dans Adobe Campaign Standard (version préliminaire)

En tant qu’utilisateur d’informations sur l’audience pour Dynamics 365 Customer Insights, vous avez peut-être créé des segments pour rendre vos campagnes marketing plus efficaces en ciblant des audiences pertinentes. Pour utiliser un segment des informations sur l’audience dans Adobe Experience Platform et dans des applications comme Adobe Campaign Standard, vous devez suivre quelques étapes décrites dans cet article.

:::image type="content" source="media/ACS-flow.png" alt-text="Schéma du processus des étapes décrites dans cet article.":::

## <a name="prerequisites"></a>Conditions préalables

-   Licence Dynamics 365 Customer Insights
-   Licence Adobe Campaign Standard
-   Compte de stockage Blob Azure

## <a name="campaign-overview"></a>Vue d’ensemble de la campagne

Pour mieux comprendre comment utiliser des segments des informations sur l’audience dans Adobe Experience Platform, examinons un exemple de campagne fictif.

Supposons que votre entreprise offre un service mensuel basé sur un abonnement à vos clients aux États-Unis. Vous souhaitez identifier les clients dont les abonnements doivent être renouvelés dans les huit prochains jours, mais qui n’ont pas encore renouvelé leur abonnement. Pour fidéliser ces clients, vous souhaitez leur envoyer une offre promotionnelle par e-mail, à l’aide d’Adobe Campaign Standard.

Dans cet exemple, nous souhaitons exécuter la campagne d’e-mails promotionnels une seule fois. Cet article ne couvre pas le cas d’utilisation de l’exécution de la campagne plusieurs fois. Cependant, les informations sur l’audience et Adobe Campaign Standard peuvent également être configurées pour fonctionner pour un scénario de campagne récurrent.

## <a name="identify-your-target-audience"></a>Identifier votre audience cible

Dans notre scénario, nous supposons que les adresses e-mail des clients sont disponibles dans les informations sur l’audience et que les préférences promotionnelles des clients ont été analysées pour identifier les membres du segment.

Le [segment que vous avez défini dans les informations sur l’audience](segments.md) est appelé **ChurnProneCustomers** et vous prévoyez d’envoyer à ces clients la promotion par e-mail.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Capture d’écran de la page des segments avec le segment ChurnProneCustomers créé.":::

L’e-mail d’offre que vous souhaitez envoyer contiendra le prénom, le nom et la date de fin d’abonnement du client. Il informe les clients de la réduction qu’ils obtiendront s’ils renouvellent leur abonnement avant qu’il ne se termine.

## <a name="export-your-target-audience"></a>Exporter votre audience cible

Une fois notre audience cible identifiée, nous pouvons configurer l’exportation des informations sur l’audience vers un compte de stockage Blob Azure.

1. Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.

1. Dans la vignette **Adobe Campaign**, sélectionnez **Configurer**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Vignette de configuration pour Adobe Campaign Standard.":::

1. Renseignez un **Nom d’affichage** pour cette nouvelle destination d’exportation, puis saisissez le **Nom du compte**, la **Clé de compte** et le **Conteneur** du compte de stockage Blob Azure vers lequel vous souhaitez exporter le segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Capture d’écran de la configuration du compte de stockage. "::: 

   - Pour en savoir plus sur la recherche du nom et de la clé de compte de stockage Blob Azure, consultez [Gérer les paramètres du compte de stockage dans le portail Azure](/azure/storage/common/storage-account-manage).

   - Pour savoir comment créer un conteneur, voir [Créer un conteneur](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Cliquez sur **Suivant**.

1. Choisissez le segment que vous souhaitez exporter. Dans cet exemple, il s’agit de **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Capture d’écran de l’interface utilisateur de sélection de segment avec le segment ChurnProneCustomers sélectionné.":::

1. Cliquez sur **Suivant**.

1. Maintenant, nous mappons les champs **Source** du segment des informations sur l’audience au champ **Cible** du schéma de profil Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mappage de champs pour le connecteur Adobe Campaign Standard.":::

   Si vous souhaitez ajouter d’autres attributs, sélectionnez **Ajouter un attribut**. Le nom de la cible peut être différent du nom du champ de la source, afin que vous puissiez toujours mapper la sortie du segment des informations sur l’audience à Adobe Campaign Standard si les champs ne portent pas le même nom dans les deux systèmes.

   > [!NOTE]
   > L’adresse e-mail est utilisée comme champ d’identité, mais vous pouvez utiliser tout autre identificateur de votre profil client des informations sur l’audience pour mapper des données à Adobe Campaign Standard.

1. Sélectionnez **Enregistrer**.

Après avoir enregistré la destination d’exportation, vous la trouvez sur **Administration** > **Exportations** > **Mes destinations d’exportation**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Capture d’écran montrant la liste des exportations et l’exemple de segment en surbrillance.":::

Vous pouvez maintenant [exporter le segment à la demande](export-destinations.md#export-data-on-demand). L'exportation sera également exécutée à chaque [actualisation planifiée](system.md).

> [!NOTE]
> Assurez-vous que le nombre d’enregistrements dans le segment exporté se situe dans la limite autorisée de votre licence Adobe Campaign Standard.

Les données exportées sont stockées dans le conteneur de stockage Blob Azure que vous avez configuré ci-dessus. Le chemin d’accès aux dossiers suivant est créé automatiquement dans votre conteneur :

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Exemple : Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurer Adobe Campaign Standard

Lorsqu’un segment des informations sur l’audience est exporté, il contient les colonnes que vous avez sélectionnées lors de la définition de la destination d’exportation à l’étape précédente. Ces données peuvent être utilisées pour [créer des profils dans Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Pour utiliser le segment dans Adobe Campaign Standard, nous devons étendre le schéma de profil dans Adobe Campaign Standard pour inclure deux champs supplémentaires. Découvrez comment [étendre la ressource de profil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) avec de nouveaux champs dans Adobe Campaign Standard.

Dans notre exemple, ces champs sont *Nom du segment et Date du segment (facultatif).*

Nous utiliserons ces champs pour identifier les profils dans Adobe Campaign Standard que nous souhaitons cibler pour cette campagne.

S’il n’y a pas d’autres enregistrements dans Adobe Campaign Standard, autres que ceux que vous allez importer, vous pouvez ignorer cette étape.

## <a name="import-data-into-adobe-campaign-standard"></a>Importer des données dans Adobe Campaign Standard

Maintenant que tout est en place, nous devons importer les données d’audience préparées à partir des informations sur l’audience dans Adobe Campaign Standard pour créer des profils. Découvrez [comment importer des profils dans Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) en utilisant un workflow.

Le workflow d’importation dans l’image ci-dessous a été configuré pour s’exécuter toutes les 8 heures et recherche les segments des informations sur l’audience exportés (fichier .csv dans le stockage Blob Azure). Le workflow extrait le contenu du fichier .csv dans un ordre de colonne spécifié. Ce workflow a été conçu pour effectuer une gestion des erreurs de base et garantir que chaque enregistrement possède une adresse e-mail avant d’hydrater les données dans Adobe Campaign Standard. Le workflow extrait également le nom du segment du nom de fichier avant de les insérer dans les données de profil ACS.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Capture d’écran d’un workflow d’importation dans l’interface utilisateur d’Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Récupérer l’audience dans Adobe Campaign Standard

Une fois les données importées dans Adobe Campaign Standard, vous [pouvez créer un workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) et [interroger](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) les clients en fonction des données *Nom du segment* et *Date du segment* pour sélectionner les profils identifiés pour notre exemple de campagne.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Créer et envoyer l’e-mail à l’aide d’Adobe Campaign Standard

Créez le contenu de l’e-mail, puis [testez et envoyez](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) votre e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemple d’e-mail avec l’offre de renouvellement d’Adobe Campaign Standard.":::