---
title: Ingérer des données à partir de Azure Synapse Analytics
description: Utilisez une base de données dans Azure Synapse en tant que source de données de Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646172"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Se connecter à une source de données Azure Synapse (version préliminaire)

Azure Synapse Analytics est un service d’analyse d’entreprise qui accélère l’obtention d’informations entre entrepôts de données et systèmes de Big Data. Azure Synapse Analytics rassemble le meilleur des technologies SQL utilisées dans l’entreposage de données d’entreprise, des technologies Spark utilisées pour le Big Data, de l’Explorateur de données pour l’analyse des journaux et des séries chronologiques, des pipelines pour l’intégration de données et les processus ETL/ELT, et une intégration approfondie avec d’autres services Azure tels que Power BI, Cosmos DB et AzureML.

Pour plus d’informations, voir [Vue d’ensemble de Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Conditions préalables

Les conditions préalables suivantes doivent être remplies pour configurer la connexion de Dynamics 365 Customer Insights vers Azure Synapse.

> [!IMPORTANT]
> Assurez-vous de configurer toutes les **attributions de rôle** comme décrit.  

## <a name="prerequisites-in-customer-insights"></a>Conditions préalables dans Customer Insights

* Vous disposez d’un rôle **Administrateur** dans Customer Insights. En savoir plus sur les [autorisations utilisateur dans Customer Insights](permissions.md#assign-roles-and-permissions).

Dans Azure : 

- Un abonnement Azure actif.

- Si vous utilisez un nouveau compte Gen2 Azure Data Lake Storage, le *principal de service pour Customer Insights* a besoin d’autorisations **Données d’objets blob de stockage collaborateur**. En savoir plus sur la [connexion à un Azure Data Lake Storage avec un principal de service pour Customer Insights](connect-service-principal.md). Le compte Data Lake Storage Gen2 **doit avoir un** [espace de noms hiérarchique](/azure/storage/blobs/data-lake-storage-namespace) activé.

- Dans le groupe de ressources où se trouve Azure Synapse workspace, le *principal de service* et l’*utilisateur pour Customer Insights* doivent au moins disposer des autorisations de **Lecteur**. Pour plus d’informations, voir [Attribuer des rôles Azure à l’aide du portail Azure](/azure/role-based-access-control/role-assignments-portal).

- L’*utilisateur* a besoin d’autorisations **Contributeur d’objet BLOB de stockage** sur le compte Azure Data Lake Storage Gen2 où les données se trouvent et sont liées à l’espace de travail Azure Synapse. En savoir plus sur l’[utilisation du portail Azure pour attribuer un rôle Azure afin d’accéder aux données des objets blob et des files d’attente](/azure/storage/common/storage-auth-aad-rbac-portal) et les [autorisations collaborateur de données BLOB de stockage](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- L’*[identité gérée de l’espace de travail Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* a besoin d’autorisations **Contributeur d’objet BLOB de stockage** sur le compte Azure Data Lake Storage Gen2 où les données se trouvent et sont liées à l’espace de travail Azure Synapse. En savoir plus sur l’[utilisation du portail Azure pour attribuer un rôle Azure afin d’accéder aux données des objets blob et des files d’attente](/azure/storage/common/storage-auth-aad-rbac-portal) et les [autorisations collaborateur de données BLOB de stockage](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Sur Azure Synapse workspace, le *principal de service pour Customer Insights* a besoin de disposer du rôle **Administrateur de Synapse**. Pour plus d’informations, voir [Comment configurer le contrôle d’accès pour votre espace de travail Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Se connecter à des bases de données en lac de données dans Azure Synapse Analytics

1. Accédez à **Données** > **Sources de données**.

1. Sélectionnez **Ajouter une source de données**.

1. Choisissez la méthode **Azure Synapse Analytics (Version préliminaire)**.

1. Indiquez un **Nom** pour la source de données, et sélectionnez **Suivant** pour créer la source de données. 

1. Choisissez une [connexion disponible](connections.md) à Azure Synapse Analytics ou créez-en une nouvelle.

1. Choisissez une **Base de données en lac** depuis l’espace de travail connecté à la connexion Azure Synapse Analytics sélectionnée, puis sélectionnez **Suivant**.

1. Sélectionnez les entités à ingérer à partir de la base de données connectée. 

1. Choisissez éventuellement les entités de données sur lesquelles autoriser le profilage des données. 

1. Sélectionnez **Enregistrer** pour appliquer votre sélection et démarrer l’ingestion des données de votre source de données nouvellement créée liée aux tables de la base de données en lac de Azure Synapse Analytics.
