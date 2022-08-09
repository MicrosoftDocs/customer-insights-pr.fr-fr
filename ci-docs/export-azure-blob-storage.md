---
title: Exporter des données vers un stockage Blob Azure (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers un stockage Blob.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195701"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Exporter des données vers un stockage Blob Azure (version préliminaire)

Stockez vos données Customer Insights dans un stockage Blob ou utilisez-le pour transférer vos données vers d’autres applications.

## <a name="prerequisites"></a>Conditions préalables

- Un nom de [compte Stockage Blob Azure](/azure/storage/blobs/create-data-lake-storage-account) et une clé de compte. Pour rechercher le nom et la clé, consultez [Gérer les paramètres du compte de stockage dans le portail Azure](/azure/storage/common/storage-account-manage).
- Un [conteneur Stockage Blob Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Limitations connues

- Pour Stockage Blob Azure, choisissez entre les [niveaux Performances standard et Performances Premium](/azure/storage/blobs/storage-blob-performance-tiers). Si vous choisissez le niveau Performances Premium, sélectionnez les [objets blob de bloc premium en tant que type de compte](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Configurer la connexion à Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion**, puis choisissez **Stockage Blob Azure**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez le **Nom du compte**, la **Clé du compte** et le **Conteneur** de votre compte de Stockage Blob.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

Pour configurer cette exportation, vous devez avoir l’[autorisation](export-destinations.md#set-up-a-new-export) correspondant à ce type de connexion.

> [!IMPORTANT]
> Si vous avez activé le [paramètre de suppression temporaire](/azure/storage/blobs/soft-delete-blob-enable) pour le compte Stockage Blob Azure, les exportations seront un échec. Désactivez la suppression temporaire pour exporter les données vers les objets blob.

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Stockage Blob Azure. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Entrez le nom du dossier pour le Stockage Blob.

1. Cochez la case en regard de chacune des entités que vous souhaitez exporter vers cette destination.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Les données exportées sont stockées dans le conteneur de Stockage Blob que vous avez configuré. Les chemins d’accès suivants aux dossiers sont créés automatiquement dans votre conteneur :

- Pour les entités sources et les entités générées par le système :  
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Exemple : Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > L'exportation d'entités contenant une grande quantité de données peut générer plusieurs fichiers CSV dans le même dossier pour chaque exportation. Le fractionnement des exportations se produit pour des raisons de performances afin de minimiser le temps nécessaire à l'exécution d'une exportation.

- Le fichier model.json pour les entités exportées réside au niveau *%ExportDestinationName%*.  
  
  Exemple : Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
