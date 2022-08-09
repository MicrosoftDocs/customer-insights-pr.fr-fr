---
title: Exporter des données vers Azure Synapse Analytics (version préliminaire)
description: Découvrez comment configurer la connexion à Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196391"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exporter des données vers Azure Synapse Analytics (version préliminaire)

Azure Synapse est un service d’analyse qui accélère le temps nécessaire pour obtenir des informations sur les entrepôts de données et les systèmes Big Data. Vous pouvez ingérer et utiliser vos données Customer Insights dans [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Conditions préalables

> [!NOTE]
> Assurez-vous de configurer toutes les **attributions de rôle** comme décrit.

- Dans Customer Insights, votre compte d’utilisateur Azure Active Directory (AD) doit avoir un rôle [Administrateur](permissions.md#assign-roles-and-permissions).

Dans Azure :

- Un abonnement Azure actif.

- Si vous utilisez un nouveau compte Gen2 Azure Data Lake Storage, le [principal de service pour Customer Insights](connect-service-principal.md) a des autorisations **Données d’objets blob de stockage collaborateur**. Le compte Data Lake Storage Gen2 **doit avoir un** [espace de noms hiérarchique](/azure/storage/blobs/data-lake-storage-namespace) activé.

- Dans le groupe de ressources où se trouve Azure Synapse workspace, le *principal de service* et l’*utilisateur Azure AD avec les autorisations d’administrateur dans Customer Insights* doivent au moins disposer de l’attribut **Lecteur** dans les [autorisations](/azure/role-based-access-control/role-assignments-portal).

- L’*utilisateur Azure AD avec des autorisations d’administrateur dans Customer Insights* a des autorisations **Données d’objets blob de stockage collaborateur** sur le compte Gen2 Azure Data Lake Storage où se trouvent les données et liées à Azure Synapse workspace. En savoir plus sur l’[utilisation du portail Azure pour attribuer un rôle Azure afin d’accéder aux données des objets blob et des files d’attente](/azure/storage/common/storage-auth-aad-rbac-portal) et les [autorisations collaborateur de données BLOB de stockage](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- L’*[identité gérée d’Azure Synapse workspace](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* a des autorisations **Contributeur d’objet BLOB de stockage** sur le compte Azure Data Lake Storage Gen2 où les données se trouvent et sont liées à Azure Synapse workspace. En savoir plus sur l’[utilisation du portail Azure pour attribuer un rôle Azure afin d’accéder aux données des objets blob et des files d’attente](/azure/storage/common/storage-auth-aad-rbac-portal) et les [autorisations collaborateur de données BLOB de stockage](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Sur Azure Synapse workspace, le *principal de service pour Customer Insights* a **Administrateur de Synapse** comme [rôle attribué](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-connection-to-azure-synapse"></a>Configurer la connexion à Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion**, puis choisissez **Azure Synapse Analytics**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sélectionnez ou recherchez l’abonnement dans lequel vous souhaitez utiliser les données Customer Insights. Dès qu’un abonnement est sélectionné, vous pouvez également sélectionner **Espace de travail**, **Compte de stockage** et **Conteneur**.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)] Pour configurer l’exportation avec une connexion partagée, vous avez besoin au moins des autorisations **Contributeur** dans Customer Insights.

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Azure Synapse Analytics. Contactez un administrateur si aucune connexion n’est disponible.

1. Indiquez un **nom d’affichage** reconnaissable pour votre exportation et un **nom de base de données**. L’exportation créera une nouvelle [base de données de lac Azure Synapse](/azure/synapse-analytics/database-designer/concepts-lake-database) dans l’espace de travail défini dans la connexion.

1. Sélectionnez les entités que vous souhaitez exporter vers Azure Synapse Analytics.
   > [!NOTE]
   > Les sources de données basées sur un [dossier Common Data Model](connect-common-data-model.md) ne sont pas pris en charge.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Pour interroger les données exportées vers Synapse Analytics, il faut que le **Lecteur de données d’objets blob de stockage** puisse accéder au stockage destination sur l’espace de travail des exports.

## <a name="update-an-export"></a>Mettre à jour une exportation

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Modifier** pour l’exportation que vous souhaitez mettre à jour.

   - **Ajoutez** ou **supprimez** des entités de la sélection. Si des entités sont supprimées de la sélection, elles ne sont pas supprimées de la base de données Synapse Analytics. Cependant, les futures actualisations des données ne mettront pas à jour les entités supprimées dans cette base de données.

   - **Changer le nom de la base de données** crée une nouvelle base de données Synapse Analytics. La base de données avec le nom qui a été configuré auparavant ne recevra aucune mise à jour lors des actualisations ultérieures.

[!INCLUDE [footer-include](includes/footer-banner.md)]
