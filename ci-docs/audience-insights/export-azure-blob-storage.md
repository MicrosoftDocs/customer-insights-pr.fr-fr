---
title: Exporter des données Customer Insights vers un stockage Blob Azure
description: Découvrez comment configurer la connexion au stockage Blob Azure.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ecacf20365e78ced8859dfa54b1b16cb923c00eb
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269189"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Connecteur pour le stockage Blob Azure (préversion)

Stockez vos données Customer Insights dans un stockage Blob Azure ou utilisez-le pour transférer vos données vers d’autres applications.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Configurer le connecteur pour le stockage Blob Azure

1. Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.

1. Sous **Stockage Blob Azure**, sélectionnez **Configurer**.

1. Saisissez le **Nom du compte**, la **Clé de compte** et le **Conteneur** pour votre compte de stockage Blob Azure.
    - Pour en savoir plus sur la recherche du nom et de la clé de compte de stockage Blob Azure, consultez [Gérer les paramètres du compte de stockage dans le portail Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Pour savoir comment créer un conteneur, voir [Créer un conteneur](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Donnez à votre destination un nom reconnaissable dans le champ **Nom complet**.

1. Sélectionnez **Suivant**.

1. Cochez la case en regard de chacune des entités que vous souhaitez exporter vers cette destination.

1. Sélectionnez **Enregistrer**.

Les données exportées sont stockées dans le conteneur de stockage Blob Azure que vous avez configuré. Les chemins d’accès suivants aux dossiers sont créés automatiquement dans votre conteneur :

- Pour les entités sources et les entités générées par le système : `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Exemple : `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Le fichier model.json pour les entités exportées résidera au niveau %ExportDestinationName%
  - Exemple : `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Exporter les données

Vous pouvez [exporter les données à la demande](export-destinations.md#export-data-on-demand). L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]