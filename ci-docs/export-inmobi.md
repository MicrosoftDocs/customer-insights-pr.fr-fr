---
title: Exporter des données Customer Insights vers InMobi
description: Découvrez comment configurer la connexion et exporter vers InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195885"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Exporter des données Customer Insights vers InMobi (version préliminaire)

Exportez des listes de segments ou d’autres données de votre instance Customer Insights vers [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Conditions préalables

- Un [compte InMobi](https://www.inmobi.com/) et des informations d’identification de l’administrateur.
- Un nom de [compte Stockage Blob Azure](/azure/storage/blobs/create-data-lake-storage-account) et une clé de compte. Pour rechercher le nom et la clé, consultez [Gérer les paramètres du compte de stockage dans le portail Azure](/azure/storage/common/storage-account-manage).
- Un [conteneur Stockage Blog Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) vers lequel exporter les données InMobi.
- InMobi créera une connexion directe à votre stockage Blob et configurera une importation automatique de vos données vers InMobi. Contactez votre représentant InMobi pour lancer le processus.

## <a name="known-limitations"></a>Limitations connues

- Pour Stockage Blob Azure, choisissez entre les [niveaux Performances standard et Performances Premium](/azure/storage/blobs/storage-blob-performance-tiers). Si vous choisissez le niveau Performances Premium, sélectionnez les [objets blob de bloc premium en tant que type de compte](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Configurer la connexion au Stockage Blob Azure

[Configurer une connexion à votre Stockage Blog Azure](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Configurer une exportation

[Configurer une exportation](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
