---
title: Exporter des segments Customer Insights vers Adobe Campaign Standard (version préliminaire)
description: Découvrez comment utiliser les segments Customer Insights dans Adobe Campaign Standard.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195517"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Exporter des segments Customer Insights vers Adobe Campaign Standard (version préliminaire)

Exportez des segments qui ciblent des audiences pertinentes vers Adobe Campaign Standard.

:::image type="content" source="media/ACS-flow.png" alt-text="Schéma du processus des étapes décrites dans cet article.":::

## <a name="prerequisites"></a>Conditions préalables

- Une licence Adobe Campaign Standard.
- Un nom de [compte Stockage Blob Azure](/azure/storage/blobs/create-data-lake-storage-account) et une clé de compte. Pour rechercher le nom et la clé, consultez [Gérer les paramètres du compte de stockage dans le portail Azure](/azure/storage/common/storage-account-manage).
- Un [conteneur Stockage Blob Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Vue d’ensemble de la campagne

Pour mieux comprendre comment vous pouvez utiliser les segments de Customer Insights dans Adobe Experience Platform, examinons un exemple de campagne fictif.

Supposons que votre entreprise offre un service mensuel basé sur un abonnement à vos clients aux États-Unis. Vous souhaitez identifier les clients dont les abonnements doivent être renouvelés dans les huit prochains jours, mais qui n’ont pas encore renouvelé leur abonnement. Pour fidéliser ces clients, vous souhaitez leur faire parvenir par e-mail une offre promotionnelle en utilisant Adobe Campaign Standard.

Dans cet exemple, nous souhaitons exécuter la campagne d’e-mails promotionnels une seule fois. Cet article ne couvre pas le cas d’utilisation de l’exécution de la campagne plusieurs fois. Cependant, Customer Insights et Adobe Campaign Standard peuvent également être configurés pour fonctionner dans un scénario de campagne récurrent.

## <a name="identify-your-target-audience"></a>Identifier votre audience cible

Dans notre scénario, nous supposons que les adresses e-mail des clients sont disponibles dans Customer Insights et leurs préférences promotionnelles ont été analysées pour identifier les membres du segment.

Le [segment que vous avez défini dans Customer Insights](segments.md) est appelé **ChurnProneCustomers** et vous prévoyez d’envoyer la promotion à ces clients.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Capture d’écran de la page des segments avec le segment ChurnProneCustomers créé.":::

L’e-mail d’offre que vous souhaitez envoyer contiendra le prénom, le nom et la date de fin d’abonnement du client. Il informe les clients de la réduction qu’ils obtiendront s’ils renouvellent leur abonnement avant qu’il ne se termine.

## <a name="export-your-target-audience"></a>Exporter votre audience cible

### <a name="set-up-connection-to-adobe-campaign"></a>Configurer la connexion à Adobe Campaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Adobe Campaign**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez le **Nom du compte**, la **Clé du compte** et le **Conteneur** de votre compte de Stockage Blob.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Capture d’écran de la configuration du compte de stockage. ":::

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

### <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Adobe Campaign. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Choisissez le segment que vous souhaitez exporter. Dans cet exemple, il s’agit de **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Capture d’écran de l’interface utilisateur de sélection de segment avec le segment ChurnProneCustomers sélectionné.":::

1. Cliquez sur **Suivant**.

1. Mappez les champs **Source** du segment Customer Insights aux noms du champ **Cible** dans le schéma de profil Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mappage des champs pour le connecteur standard Adobe Campaign Standard.":::

   Si vous souhaitez ajouter d’autres attributs, sélectionnez **Ajouter un attribut**. Le nom cible peut être différent du nom du champ source ; par conséquent, vous pouvez toujours mapper la sortie du segment de Customer Insights à Adobe Campaign Standard si les champs n’ont pas le même nom dans les deux systèmes.

   > [!NOTE]
   > L’adresse e-mail est utilisée comme champ d’identité, mais vous pouvez utiliser tout autre identifiant du profil client pour mapper les données à Adobe Campaign Standard.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Vérifiez que le nombre d’enregistrements dans le segment exporté se trouve dans la limite autorisée par votre licence Adobe Campaign Standard.

Les données exportées sont stockées dans le conteneur de stockage Blob Azure que vous avez configuré ci-dessus. Le chemin de dossier suivant est automatiquement créé dans votre conteneur : *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Exemple : Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurer Adobe Campaign Standard

Les segments exportés contiennent les colonnes que vous avez sélectionnées lors de la configuration de l’exportation. Ces données peuvent servir à [créer des profils dans Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Pour utiliser le segment dans Adobe Campaign Standard, [étendez le schéma de profils](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) dans Adobe pour inclure deux champs supplémentaires.

Dans notre exemple, ces champs sont Nom du segment et Date du segment. Ces champs servent à identifier les profils dans Adobe Campaign Standard à cibler pour cette campagne.

S’il n’y a pas d’autres enregistrements dans Adobe Campaign Standard que ceux que vous allez importer, ignorez cette étape.

## <a name="import-data-into-adobe-campaign-standard"></a>Importer des données dans Adobe Campaign Standard

Importez les données d’audience préparées de Customer Insights dans Adobe Campaign Standard pour [créer des profils à l’aide d’un workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Le flux de travail d’importation dans l’image ci-dessous a été configuré pour s’exécuter toutes les huit heures et rechercher les segments Customer Insights exportés (fichier .csv dans le Stockage Blob Azure). Le workflow extrait le contenu du fichier .csv dans un ordre de colonne spécifié. Ce workflow a été conçu pour assurer la gestion de base des erreurs et veiller à ce que chaque enregistrement soit associé à une adresse e-mail avant d’hydrater les données dans Adobe Campaign Standard. Le workflow extrait aussi le nom du segment du nom de fichier avant de l’insérer dans les données de profil Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Capture d’écran d’un workflow d’importation dans l’interface utilisateur d’Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Récupérer l’audience dans Adobe Campaign Standard

Une fois les données importées dans Adobe Campaign Standard, [créez un workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) et [interrogez](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) les clients en fonction du nom et de la date du segment pour sélectionner les profils identifiés pour notre exemple de campagne.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Créer et envoyer l’e-mail en utilisant Adobe Campaign Standard

Créez le contenu de l’e-mail, puis [testez et envoyez](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) votre e-mail.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemple d’e-mail avec offre de renouvellement provenant d’Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
