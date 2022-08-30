---
title: Utiliser votre propre compte Azure Data Lake Storage Gen2
author: mukeshpo
description: Découvrez les conditions requises pour utiliser votre propre compte Azure Data Lake Storage pour stocker les données Customer Insights.
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304378"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Utiliser votre propre compte Azure Data Lake Storage Gen2

Dynamics 365 Customer Insights vous offre la possibilité de stocker toutes vos données dans [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction). En enregistrant les données dans Data Lake Storage, vous acceptez que les données soient transférées et stockées à l’emplacement géographique approprié pour ce compte de stockage Azure. Pour plus d’informations, reportez-vous au [Centre de gestion de la confidentialité Microsoft](https://www.microsoft.com/trust-center).

Les administrateurs de Customer Insights peuvent [créer des environnements](create-environment.md) et [spécifier l’option de stockage des données](create-environment.md#step-2-configure-data-storage) dans le processus.

## <a name="prerequisites"></a>Conditions préalables

- Les comptes Azure Data Lake Storage doivent être dans la même région Azure que vous avez sélectionnée lors de la création de l’environnement Customer Insights. Pour connaître la région de l’environnement, accédez à **Administrateur** > **Système** > **À propos de** dans Customer Insights.
- Le compte de stockage Data Lake Storage doit être Gen2 Les comptes de stockage Azure Data Lake Gen1 ne sont pas pris en charge.
- Le compte de stockage Data Lake doit avoir la fonctionnalité [espace de noms hiérarchique activée](/azure/storage/blobs/data-lake-storage-namespace).
- Un conteneur nommé `customerinsights` doit exister sur le compte de stockage. Créez-le avant d’utiliser votre propre Data Lake Storage dans Customer Insights.
- L’administrateur qui configure l’environnement Customer Insights doit avoir le rôle Contributeur des données blob de stockage ou Propriétaire des données blob de stockage sur le compte de stockage ou le conteneur `customerinsights`. Pour plus d’informations sur l’attribution d’autorisations dans un compte de stockage, consultez [Créer un compte de stockage](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Connecter Customer Insights à votre compte de stockage

Lorsque vous créez un nouvel environnement, assurez-vous que le compte Data Lake Storage existe et que toutes les conditions préalables sont remplies.

1. Dans l’étape **Stockage de données** pendant la création de l’environnement, définissez **Enregistrer les données de sortie** sur **Azure Data Lake Storage Gen2**.
1. Choisissez comment **Connecter votre stockage**. Vous pouvez choisir entre une option basée sur une ressource et une option basée sur un abonnement pour l’authentification. Pour plus d’informations, consultez [Se connecter à un compte Azure Data Lake Storage en utilisant un principal de service Azure](connect-service-principal.md).
   - Pour l’**Abonnement Azure**, choisissez l’**Abonnement**, le **Groupe de ressources** et le **Compte de stockage** qui contient le conteneur `customerinsights`.
   - Pour la **Clé du compte**, fournissez le **Nom du compte** et la **Clé du compte** pour le compte Data Lake Storage. L’utilisation de cette méthode d’authentification implique que vous êtes informé si votre organisation effectue une rotation des clés. Vous devez [mettre à jour la configuration de l’environnement](manage-environments.md#edit-an-existing-environment) avec la nouvelle clé lors de sa rotation.
1. Choisissez si vous souhaitez utiliser Azure Private Link pour vous connecter au compte de stockage et [créez la connexion à Private Link](security-overview.md#set-up-an-azure-private-link).

Lorsque les processus système tels que l’ingestion de données sont terminés, le système crée les dossiers correspondants dans le compte de stockage. Les fichiers de données et les fichiers model.json sont créés et ajoutés aux dossiers en fonction du nom du processus.

Si vous créez plusieurs environnements de Customer Insights et choisissez d’enregistrer les entités de sortie de ces environnements sur votre compte de stockage, Customer Insights crée des dossiers séparés pour chaque environnement avec `ci_environmentID` dans le conteneur.
