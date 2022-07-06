---
title: Exporter des données Customer Insights vers InMobi
description: Découvrez comment configurer la connexion et exporter vers InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056540"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Exporter la liste de segments et d’autres données vers InMobi (version préliminaire)

Exportez des listes de segments ou d’autres données de votre instance Customer Insights vers [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Conditions préalables

1. Vous disposez d’un [compte InMobi](https://www.inmobi.com/) et des informations d’identification de l’administrateur.
1. Vous disposez du nom du compte de stockage Blob Azure et de la clé de compte correspondante. Pour plus d’informations, consultez [Gérer les paramètres du compte de stockage dans le portail Azure](/azure/storage/common/storage-account-manage). Le compte de stockage contient un conteneur vers lequel exporter les données inMobi. Pour plus d’informations, consultez [Créer un conteneur](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi créera une connexion directe à votre stockage Blob et configurera une importation automatique de vos données vers InMobi. Contactez votre représentant InMobi pour lancer le processus.

## <a name="known-limitations"></a>Limitations connues

1. Pour le stockage Blob Azure, vous pouvez choisir entre les [niveaux Performances standard et Performances Premium](/azure/storage/blobs/storage-blob-performance-tiers). Si vous choisissez le niveau Performances Premium, sélectionnez les [objets blob de bloc premium en tant que type de compte](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Configurer la connexion au stockage Blob Azure et configurer une exportation

1. Suivez les instructions pour [configurer une connexion à votre stockage Blob Azure](export-azure-blob-storage.md).
2. Suivez les instructions pour [configurer une exportation](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
