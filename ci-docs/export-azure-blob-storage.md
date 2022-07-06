---
title: Exporter des données vers un stockage Blob Azure (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers un stockage Blob.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 059c8364ca0f3740bc0e4ffeeeba94246c9e5696
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055487"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Exporter des données vers un stockage Blob Azure (version préliminaire)

Stockez vos données Customer Insights dans un stockage Blob ou utilisez-le pour transférer vos données vers d’autres applications.

## <a name="known-limitations"></a>Limitations connues

1. Pour Azure Blob Storage, vous pouvez choisir entre [les niveaux Performances standard et Performances Premium](/azure/storage/blobs/storage-blob-performance-tiers). Si vous choisissez le niveau Performances Premium, sélectionnez les [objets blob de bloc premium en tant que type de compte](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>Configurer la connexion au Stockage Blob

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Stockage Blob Azure** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez le **Nom du compte**, la **Clé du compte** et le **Conteneur** de votre compte de Stockage Blob.
    - Pour obtenir plus d’informations sur la recherche du nom et de la clé du compte de stockage Blob, voir [Gérer les paramètres du compte de stockage dans le portail Azure](/azure/storage/common/storage-account-manage).
    - Pour savoir comment créer un conteneur, voir [Créer un conteneur](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Sélectionnez **Enregistrer** pour terminer la connexion. 

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Si vous avez activé le paramètre de suppression temporaire pour le compte Stockage Blob Azure, les exportations seront un échec. Désactivez la suppression temporaire pour exporter les données vers les objets blob. Pour plus d’informations, consultez [Activer la suppression temporaire des objets blob](/azure/storage/blobs/soft-delete-blob-enable)

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Stockage Blob Azure. Si le nom de la section ne s’affiche pas, aucune connexion de ce type n’est disponible pour vous.

1. Cochez la case en regard de chacune des entités que vous souhaitez exporter vers cette destination.

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).

Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).

Les données exportées sont stockées dans le conteneur de Stockage Blob que vous avez configuré. Les chemins d’accès suivants aux dossiers sont créés automatiquement dans votre conteneur :

- Pour les entités sources et les entités générées par le système :  
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Exemple : `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
  
  > [!TIP]
  > L'exportation d'entités contenant une grande quantité de données peut générer plusieurs fichiers CSV dans le même dossier pour chaque exportation. Le fractionnement des exportations se produit pour des raisons de performances afin de minimiser le temps nécessaire à l'exécution d'une exportation.

- Le fichier model.json des entités exportées sera au niveau de %ExportDestinationName%.  
  - Exemple : `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]
