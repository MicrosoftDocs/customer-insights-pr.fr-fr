---
title: Exporter des données Customer Insights vers des hôtes Azure Data Lake Storage Gen2
description: Découvrez comment configurer la connexion à Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477176"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Connecteur pour Azure Data Lake Storage Gen2 (version préliminaire)

Stockez vos données Customer Insights dans Azure Data Lake Storage Gen2 ou utilisez-le pour transférer vos données vers d’autres applications.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Configurer le connecteur pour Azure Data Lake Storage Gen2

1. Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.

1. Sous **Azure Data Lake Storage Gen2**, sélectionnez **Configurer**.

1. Donnez à votre destination un nom reconnaissable dans le champ **Nom complet**.

1. Entrez **Nom du compte**, **Clé de compte** et **conteneur** pour votre Azure Data Lake Storage Gen2.
    - Pour savoir comment créer un compte de stockage à utiliser avec Azure Data Lake Storage Gen2, voir [Créer un compte de stockage](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Pour en savoir plus sur la recherche du nom et de la clé de compte du compte de stockage Azure Data Lake Gen2, voir [Gérer les paramètres du compte de stockage dans le portail Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Cliquez sur **Suivant**.

1. Cochez la case en regard de chacune des entités que vous souhaitez exporter vers cette destination.

1. Sélectionnez **Enregistrer**.

## <a name="export-the-data"></a>Exporter les données

Vous pouvez [exporter les données à la demande](export-destinations.md#export-data-on-demand). L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).
