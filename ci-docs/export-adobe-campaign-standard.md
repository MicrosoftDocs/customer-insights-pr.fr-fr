---
title: Exporter les données Customer Insights vers Adobe Campaign Standard
description: Découvrez comment utiliser les segments Customer Insights dans Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 2a62d2f889f199222eeb8cc969fce62fa89fa6f0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646232"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Utiliser les segments Customer Insights dans Adobe Campaign Standard (version préliminaire)

En tant qu’utilisateur de Dynamics 365 Customer Insights, vous avez peut-être créé des segments pour rendre vos campagnes marketing plus efficaces en ciblant des audiences pertinentes. Pour utiliser un segment de Customer Insights dans Adobe Experience Platform et les applications comme Adobe Campaign Standard, vous devez suivre quelques étapes décrites dans cet article.

:::image type="content" source="media/ACS-flow.png" alt-text="Schéma du processus des étapes décrites dans cet article.":::

## <a name="prerequisites"></a>Conditions préalables

-   Licence Dynamics 365 Customer Insights
-   Licence Adobe Campaign Standard
-   Compte de stockage Blob Azure

## <a name="campaign-overview"></a>Vue d’ensemble de la campagne

Pour mieux comprendre comment vous pouvez utiliser les segments de Customer Insights dans Adobe Experience Platform, examinons un exemple de campagne fictif.

Supposons que votre entreprise offre un service mensuel basé sur un abonnement à vos clients aux États-Unis. Vous souhaitez identifier les clients dont les abonnements doivent être renouvelés dans les huit prochains jours, mais qui n’ont pas encore renouvelé leur abonnement. Pour fidéliser ces clients, vous souhaitez leur faire parvenir par e-mail une offre promotionnelle en utilisant Adobe Campaign Standard.

Dans cet exemple, nous souhaitons exécuter la campagne d’e-mails promotionnels une seule fois. Cet article ne couvre pas le cas d’utilisation de l’exécution de la campagne plusieurs fois. Cependant, Customer Insights et Adobe Campaign Standard peuvent également être configurés pour fonctionner dans un scénario de campagne récurrent.

## <a name="identify-your-target-audience"></a>Identifier votre audience cible

Dans notre scénario, nous supposons que les adresses e-mail des clients sont disponibles et leurs préférences promotionnelles ont été analysées pour identifier les membres du segment.

Le [segment que vous avez défini dans Customer Insights](segments.md) est appelé **ChurnProneCustomers** et vous prévoyez d’envoyer la promotion à ces clients.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Capture d’écran de la page des segments avec le segment ChurnProneCustomers créé.":::

L’e-mail d’offre que vous souhaitez envoyer contiendra le prénom, le nom et la date de fin d’abonnement du client. Il informe les clients de la réduction qu’ils obtiendront s’ils renouvellent leur abonnement avant qu’il ne se termine.

## <a name="export-your-target-audience"></a>Exporter votre audience cible

### <a name="configure-a-connection"></a>Configurer une connexion

Avec notre audience cible identifiée, nous pouvons configurer l’exportation vers un compte de Stockage Blob Azure.

1. Dans Customer Insights, accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Adobe Campaign** pour configurer la connexion, ou sélectionnez **Configurer** dans la vignette **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Vignette de configuration pour Adobe Campaign Standard.":::

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Entrez le **Nom du compte**, la **Clé du compte** et le **Conteneur** du compte de stockage Blob Azure vers lequel vous souhaitez exporter le segment.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Capture d’écran de la configuration du compte de stockage. "::: 

   - Pour en savoir plus sur la recherche du nom et de la clé du compte de stockage Blob Azure, consultez [Gérer les paramètres du compte de stockage dans le portail Azure](/azure/storage/common/storage-account-manage).

   - Pour savoir comment créer un conteneur, voir [Créer un conteneur](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Sélectionnez **Enregistrer** pour terminer la connexion.

### <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Adobe Campaign. Si le nom de la section ne s’affiche pas, aucune connexion de ce type n’est disponible pour vous.

1. Choisissez le segment que vous souhaitez exporter. Dans cet exemple, il s’agit de **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Capture d’écran de l’interface utilisateur de sélection de segment avec le segment ChurnProneCustomers sélectionné.":::

1. Cliquez sur **Suivant**.

1. Maintenant nous mappons les champs **Source** du segment Customer Insights aux noms du champ **Cible** dans le schéma de profil Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mappage des champs pour le connecteur standard Adobe Campaign Standard.":::

   Si vous souhaitez ajouter d’autres attributs, sélectionnez **Ajouter un attribut**. Le nom cible peut être différent du nom du champ source ; par conséquent, vous pouvez toujours mapper la sortie du segment de Customer Insights à Adobe Campaign Standard si les champs n’ont pas le même nom dans les deux systèmes.

   > [!NOTE]
   > L’adresse e-mail est utilisée comme champ d’identité, mais vous pouvez utiliser tout autre identifiant du profil client pour mapper les données à Adobe Campaign Standard.

1. Cliquez sur **Enregistrer**.

Une fois la destination d’exportation enregistrée, vous la trouverez dans **Données** > **Exportations**.

Vous pouvez maintenant [exporter le segment à la demande](export-destinations.md#run-exports-on-demand). L'exportation sera également exécutée à chaque [actualisation planifiée](system.md).

> [!NOTE]
> Vérifiez que le nombre d’enregistrements dans le segment exporté se trouve dans la limite autorisée par votre licence Adobe Campaign Standard.

Les données exportées sont stockées dans le conteneur de stockage Blob Azure que vous avez configuré ci-dessus. Le chemin d’accès aux dossiers suivant est créé automatiquement dans votre conteneur :

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Exemple : Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurer Adobe Campaign Standard

Les segments exportés contiennent les colonnes que vous avez sélectionnées lors de la définition de la destination d’exportation dans l’étape précédente. Ces données peuvent servir à [créer des profils dans Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Pour utiliser le segment dans Adobe Campaign Standard, nous devons étendre le schéma de profils dans Adobe Campaign Standard pour inclure deux champs supplémentaires. Apprenez à [étendre la ressource du profil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) avec de nouveaux champs dans Adobe Campaign Standard.

Dans notre exemple, ces champs sont *Nom du segment et Date du segment (facultatif)*.

Ces champs servent à identifier les profils dans Adobe Campaign Standard à cibler pour cette campagne.

S’il n’y a pas d’autres enregistrements dans Adobe Campaign Standard que ceux que vous allez importer, vous pouvez ignorer cette étape.

## <a name="import-data-into-adobe-campaign-standard"></a>Importer des données dans Adobe Campaign Standard

Maintenant que tout est en place, nous devons importer les données d’audience préparées de Customer Insights dans Adobe Campaign Standard pour créer des profils. Apprenez à [importer des profils dans Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) en utilisant un worflow.

Le flux de travail d’importation dans l’image ci-dessous a été configuré pour s’exécuter toutes les huit heures et rechercher les segments Customer Insights exportés (fichier .csv dans le Stockage Blob Azure). Le workflow extrait le contenu du fichier .csv dans un ordre de colonne spécifié. Ce workflow a été conçu pour assurer la gestion de base des erreurs et veiller à ce que chaque enregistrement soit associé à une adresse e-mail avant d’hydrater les données dans Adobe Campaign Standard. Le workflow extrait aussi le nom du segment du nom de fichier avant de l’insérer dans les données de profil Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Capture d’écran d’un workflow d’importation dans l’interface utilisateur d’Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Récupérer l’audience dans Adobe Campaign Standard

Une fois les données importées dans Adobe Campaign Standard, vous [pouvez créer un workflo](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) et [interroger](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) les clients sur la base *Nom du segment* et *Date du segment* pour sélectionner les profils identifiés pour notre exemple de campagne.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Créer et envoyer l’e-mail en utilisant Adobe Campaign Standard

Créez le contenu de l’e-mail, puis [testez et envoyez](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) votre e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemple d’e-mail avec offre de renouvellement provenant d’Adobe Campaign Standard.":::
