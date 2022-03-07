---
title: Exporter des données Customer Insights vers des hôtes Azure Data Lake Storage Gen2
description: Découvrez comment configurer la connexion à Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 934c396559d4c4be8e640917d2265805753eb62d
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605900"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Exporter la liste des segments et d’autres données vers Azure Data Lake Storage Gen2 (aperçu)

Stockez vos données Customer Insights dans un compte Data Lake Storage Gen2 ou utilisez-le pour transférer vos données vers d’autres applications.

## <a name="known-limitations"></a>Limitations connues

1. Pour Azure Data Lake Storage Gen2 vous pouvez choisir entre [les niveaux Performances standard et Performances Premium](/azure/storage/blobs/create-data-lake-storage-account) lorsque vous créez un compte de stockage pour votre lac de données. Si vous choisissez le niveau Performances Premium, sélectionnez les objets blob de bloc premium en tant que type de compte. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Configurer la connexion à Azure Data Lake Storage Gen2 


1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Azure Data Lake Gen 2** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez **Nom du compte**, **Clé de compte** et **conteneur** pour votre Azure Data Lake Storage Gen2.
    - Pour savoir comment créer un compte de stockage à utiliser avec Azure Data Lake Storage Gen2, voir [Créer un compte de stockage](/azure/storage/blobs/create-data-lake-storage-account). 
    - Pour obtenir plus d’informations sur le nom et la clé du compte de stockage Azure Data Lake Gen2, voir [Gérer les paramètres du compte de stockage dans le portail Azure](/azure/storage/common/storage-account-manage).

1. Sélectionnez **Enregistrer** pour terminer la connexion. 

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section **Azure Data Lake**. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.

1. Cochez la case en regard de chacune des entités que vous souhaitez exporter vers cette destination.

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 

Les données exportées sont stockées dans le conteneur de stockage Azure Data Lake Gen 2 que vous avez configuré. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
