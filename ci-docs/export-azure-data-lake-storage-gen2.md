---
title: Exporter des données vers Azure Data Lake Storage Gen2 (version préliminaire)
description: Découvrez comment configurer la connexion à Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196437"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Exporter des données vers Azure Data Lake Storage Gen2 (version préliminaire)

Stockez vos données Customer Insights dans un compte Data Lake Storage Gen2 ou utilisez-le pour transférer vos données vers d’autres applications.

## <a name="prerequisites"></a>Conditions préalables

- Un [compte de stockage à utiliser avec Azure Data Lake Gen 2](/azure/storage/blobs/create-data-lake-storage-account). Pour rechercher le nom et la clé du compte de stockage, consultez [Gérer les paramètres du compte de stockage dans le portail Azure](/azure/storage/common/storage-account-manage).
- Un [conteneur Stockage Blob Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Limitations connues

- Pour Azure Data Lake Storage Gen2, choisissez entre les [niveaux Performances standard et Performances Premium](/azure/storage/blobs/create-data-lake-storage-account). Si vous choisissez le niveau Performances Premium, sélectionnez les [objets blob de bloc premium en tant que type de compte](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Configurer la connexion à Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion**, puis choisissez **Azure Data Lake Gen 2**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez **Nom du compte**, **Clé de compte** et **conteneur** pour votre Azure Data Lake Storage Gen2.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Azure Data Lake. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Entrez le nom du dossier pour le stockage Azure Data Lake Storage Gen2.

1. Cochez la case en regard de chacune des entités que vous souhaitez exporter vers cette destination.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Les données exportées sont stockées dans le conteneur de stockage Azure Data Lake Gen 2 que vous avez configuré.

> [!TIP]
> L'exportation d'entités contenant une grande quantité de données peut générer plusieurs fichiers CSV dans le même dossier pour chaque exportation. Le fractionnement des exportations se produit pour des raisons de performances afin de minimiser le temps nécessaire à l'exécution d'une exportation.

[!INCLUDE [footer-include](includes/footer-banner.md)]
