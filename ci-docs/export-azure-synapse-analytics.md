---
title: Exporter les données Customer Insights vers Azure Synapse Analytics
description: Découvrez comment configurer la connexion à Azure Synapse Analytics.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 772fe0978362ccd829077a8133e2a3e74043f3f8
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741500"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exporter des données vers Azure Synapse Analytics (Version préliminaire)

Azure Synapse est un service d’analyse qui accélère le temps nécessaire pour obtenir des informations sur les entrepôts de données et les systèmes Big Data. Vous pouvez ingérer et utiliser vos données Customer Insights dans [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Conditions préalables

Les conditions préalables suivantes doivent être remplies pour configurer la connexion entre Customer Insights et Azure Synapse.

> [!NOTE]
> Assurez-vous de configurer toutes les **attributions de rôle** comme décrit.  

## <a name="prerequisites-in-customer-insights"></a>Conditions préalables dans Customer Insights

* Votre compte d’utilisateur Azure Active Directory (AD) a un rôle **Administrateur** dans Customer Insights. En savoir plus sur la [définition des autorisations utilisateur](permissions.md#assign-roles-and-permissions).

Dans Azure : 

- Un abonnement Azure actif.

- Si vous utilisez un nouveau compte Gen2 Azure Data Lake Storage, le *principal de service pour Customer Insights* a besoin d’autorisations **Données d’objets blob de stockage collaborateur**. En savoir plus sur la [connexion à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure pour Customer Insights](connect-service-principal.md). Le compte Data Lake Storage Gen2 **doit avoir un** [espace de noms hiérarchique](/azure/storage/blobs/data-lake-storage-namespace) activé.

- Dans le groupe de ressources où se trouve Azure Synapse workspace, le *principal de service* et l’*utilisateur Azure AD avec les autorisations d’administrateur dans Customer Insights* doivent au moins disposer des autorisations de **Lecteur**. Pour plus d’informations, voir [Attribuer des rôles Azure à l’aide du portail Azure](/azure/role-based-access-control/role-assignments-portal).

- L’*utilisateur Azure AD avec des autorisations d’administrateur dans Customer Insights* a besoin d’autorisations **Données d’objets blob de stockage collaborateur** sur le compte Gen2 Azure Data Lake Storage où se trouvent les données et liées à Azure Synapse workspace. En savoir plus sur l’[utilisation du portail Azure pour attribuer un rôle Azure afin d’accéder aux données des objets blob et des files d’attente](/azure/storage/common/storage-auth-aad-rbac-portal) et les [autorisations collaborateur de données BLOB de stockage](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- L’*[identité gérée de l’espace de travail Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* a besoin d’autorisations **Contributeur d’objet BLOB de stockage** sur le compte Azure Data Lake Storage Gen2 où les données se trouvent et sont liées à l’espace de travail Azure Synapse. En savoir plus sur l’[utilisation du portail Azure pour attribuer un rôle Azure afin d’accéder aux données des objets blob et des files d’attente](/azure/storage/common/storage-auth-aad-rbac-portal) et les [autorisations collaborateur de données BLOB de stockage](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Sur Azure Synapse workspace, le *principal de service pour Customer Insights* a besoin de disposer du rôle **Administrateur de Synapse**. Pour plus d’informations, voir [Comment configurer le contrôle d’accès pour votre espace de travail Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Configurer la connexion et exporter vers Azure Synapse

### <a name="configure-a-connection"></a>Configurer une connexion

Pour créer une connexion, le principal du service et le compte d’utilisateur dans Customer Insights doivent avoir les autorisations de **Lecteur** sur le *groupe de ressources* où se trouve l’espace de travail Synapse Analytics. De plus, le principal du service et l’utilisateur de l’espace de travail Synapse Analytics doivent avoir les autorisations **Administrateur Synapse**. 

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Azure Synapse Analytics** ou sélectionnez **Configurer** sur la vignette **Azure Synapse Analytics** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ Nom d’affichage. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sélectionnez ou recherchez l’abonnement dans lequel vous souhaitez utiliser les données Customer Insights. Dès qu’un abonnement est sélectionné, vous pouvez également sélectionner **Espace de travail**, **Compte de stockage** et **Conteneur**.

1. Sélectionnez **Enregistrer** pour enregistrer la connexion.

### <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour configurer l’exportation avec une connexion partagée, vous avez besoin au moins des autorisations **Contributeur** dans Customer Insights. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section **Azure Synapse Analytics**. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune [connexion](connections.md) de ce type n’est disponible.

1. Indiquez un **nom d’affichage** reconnaissable pour votre exportation et un **nom de base de données**.

1. Sélectionnez les entités que vous souhaitez exporter vers Azure Synapse Analytics.
   > [!NOTE]
   > Les sources de données basées sur un [dossier Common Data Model](connect-common-data-model.md) ne sont pas pris en charge.

2. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).

Pour interroger les données exportées vers Synapse Analytics, il faut que le **Lecteur de données d’objets blob de stockage** puisse accéder au stockage destination sur l’espace de travail des exports. 

### <a name="update-an-export"></a>Mettre à jour une exportation

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Modifier** pour l’exportation que vous souhaitez mettre à jour.

   - **Ajoutez** ou **supprimez** des entités de la sélection. Si des entités sont supprimées de la sélection, elles ne sont pas supprimées de la base de données Synapse Analytics. Cependant, les futures actualisations des données ne mettront pas à jour les entités supprimées dans cette base de données.

   - **Changer le nom de la base de données** crée une nouvelle base de données Synapse Analytics. La base de données avec le nom qui a été configuré auparavant ne recevra aucune mise à jour lors des actualisations ultérieures.