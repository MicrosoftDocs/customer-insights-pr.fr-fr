---
title: Ingérer des données à partir de Azure Synapse Analytics
description: Utilisez une base de données dans Azure Synapse en tant que source de données de Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6f94cdbcc203fc4518544f7a945bd80e871b36c1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011424"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Se connecter à une source de données Azure Synapse Analytics (version préliminaire)

Azure Synapse Analytics est un service d’analyse d’entreprise qui accélère l’obtention d’informations entre entrepôts de données et systèmes de Big Data. Azure Synapse Analytics rassemble le meilleur des technologies SQL utilisées dans l’entreposage de données d’entreprise, des technologies Spark utilisées pour le Big Data, de l’Explorateur de données pour l’analyse des journaux et des séries chronologiques, des pipelines pour l’intégration de données et les processus ETL/ELT, et une intégration approfondie avec d’autres services Azure tels que Power BI, Cosmos DB et AzureML.

Pour plus d’informations, voir [Vue d’ensemble de Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Conditions préalables

> [!IMPORTANT]
> Assurez-vous de configurer toutes les **attributions de rôle** comme décrit.  

**Dans Customer Insights** :

* Vous disposez d’un rôle **Administrateur** dans Customer Insights. En savoir plus sur les [autorisations utilisateur dans Customer Insights](permissions.md#assign-roles-and-permissions).

**Dans Azure** :

- Un abonnement Azure actif.

- Si vous utilisez un nouveau compte Gen2 Azure Data Lake Storage, le *principal de service pour Customer Insights* a besoin d’autorisations **Données d’objets blob de stockage collaborateur**. En savoir plus sur la [connexion à un Azure Data Lake Storage avec un principal de service pour Customer Insights](connect-service-principal.md). Le compte Data Lake Storage Gen2 **doit avoir un** [espace de noms hiérarchique](/azure/storage/blobs/data-lake-storage-namespace) activé.

- Dans le groupe de ressources où se trouve Azure Synapse workspace, le *principal de service* et l’*utilisateur pour Customer Insights* doivent au moins disposer des autorisations de **Lecteur**. Pour plus d’informations, voir [Attribuer des rôles Azure à l’aide du portail Azure](/azure/role-based-access-control/role-assignments-portal).

- L’*utilisateur* a besoin d’autorisations **Contributeur d’objet BLOB de stockage** sur le compte Azure Data Lake Storage Gen2 où les données se trouvent et sont liées à l’espace de travail Azure Synapse. En savoir plus sur l’[utilisation du portail Azure pour attribuer un rôle Azure afin d’accéder aux données des objets blob et des files d’attente](/azure/storage/common/storage-auth-aad-rbac-portal) et les [autorisations collaborateur de données BLOB de stockage](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- L’*[identité gérée de l’espace de travail Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* a besoin d’autorisations **Contributeur d’objet BLOB de stockage** sur le compte Azure Data Lake Storage Gen2 où les données se trouvent et sont liées à l’espace de travail Azure Synapse. En savoir plus sur l’[utilisation du portail Azure pour attribuer un rôle Azure afin d’accéder aux données des objets blob et des files d’attente](/azure/storage/common/storage-auth-aad-rbac-portal) et les [autorisations collaborateur de données BLOB de stockage](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Sur Azure Synapse workspace, le *principal de service pour Customer Insights* a besoin de disposer du rôle **Administrateur de Synapse**. Pour plus d’informations, voir [Comment configurer le contrôle d’accès pour votre espace de travail Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Se connecter à la base de données en lac de données dans Azure Synapse Analytics

1. Accédez à **Données** > **Sources de données**.

1. Sélectionnez **Ajouter une source de données**.

1. Choisissez la méthode **Azure Synapse Analytics (Version préliminaire)**.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Boîte de dialogue pour se connecter aux données Synapse Analytics":::
  
1. Entrez le **nom** de la source de données et une **description** facultative.

1. Choisissez une [connexion disponible](connections.md) à Azure Synapse Analytics ou créez-en une nouvelle.

1. Choisissez une **Base de données** depuis l'espace de travail connecté à la connexion Azure Synapse Analytics sélectionnée, puis sélectionnez **Suivant**.

1. Sélectionnez les entités à ingérer à partir de la base de données connectée et sélectionnez **Suivant**.

1. Choisissez éventuellement les entités de données sur lesquelles autoriser le profilage des données.

1. Sélectionnez **Enregistrer** pour appliquer votre sélection et démarrer l’ingestion des données de votre source de données nouvellement créée liée aux tables de la base de données en lac de Azure Synapse Analytics. La page **Source de données** s'ouvre et affiche la nouvelle source de données avec le statut **Actualisation en cours**.
