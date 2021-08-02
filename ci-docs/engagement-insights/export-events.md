---
title: Exporter des événements affinés
description: Comment exporter des événements affinés et des événements de base.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 89c9ad21c7a7dba625a1dafa2f08e06700cc62d4
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555805"
---
# <a name="export-events"></a>Exporter des événements

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un événement représente le comportement d'un utilisateur. Il enregistre lorsqu'un utilisateur consulte une page (événement d'affichage) ou interagit avec le contenu (événement d'action). Lorsque vous pouvez décider quelles propriétés des données vous souhaitez afficher dans un rapport, cette vue virtuelle des données est appelée *événement affiné*. 

- Vous pouvez exporter des événements et des événements affinés vers un stockage externe. 
- Les exportations sont un flux de données vers l'avant. Vous ne pouvez pas recharger le flux. 
- Les exportations ont des schémas fixes. Si vous ajoutez des propriétés personnalisées à un événement, elles ne seront pas incluses. Vous devrez créer une nouvelle exportation.

## <a name="prerequisites"></a>Conditions préalables

Avant de configurer une exportation, vous devez disposer d'un accès et d'un abonnement actif au portail Azure. Vous aurez besoin des informations du compte de stockage pendant le processus d'exportation. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Créer un compte Azure Data Lake Storage Gen 2

1. Connectez-vous au portail Azure et [créez un compte de stockage](/azure/storage/common/storage-account-create). 

1. Vérifiez que vous avez activé **Espace de noms hiérarchique** sur l'onglet **Avancé**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Activer l'espace de noms hiérarchique dans l'onglet avancé.":::

1. Une fois qu'il a été déployé, accédez au compte de stockage nouvellement créé. Dans le volet de navigation, sélectionnez **Paramètres** > **Clés d’accès**. 

1. Copiez le **Nom du compte** et la **Clé** pour les utiliser lors de la création d'une nouvelle exportation.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Clés d'accès dans un compte de stockage.":::

## <a name="export-events"></a>Événements d’exportation

Il existe deux façons d'exporter les événements : 
- Accédez à **Données** > **Exportations** et sélectionnez **Nouvelle exportation**.
- Accédez à **Données** > **Événements**, sélectionnez **Plus [...]** en regard de l’événement que vous souhaitez exporter et sélectionnez **Exporter** dans le menu déroulant. 

Vous êtes guidé à travers les étapes de création d'une exportation :

1. Donnez un **Nom d'exportation**.

1. Dans la liste déroulante **Sélection d’événements**, choisissez les événements de base et les événements affinés à inclure dans l’exportation. 

1. En dessous de **Structure des fichiers**, sélectionnez la cadence à laquelle créer de nouveaux fichiers dans le stockage de destination. Les événements sont exportés en continu à leur arrivée.

1. Sélectionnez le format de votre exportation. Vous pouvez choisir entre le format **Common Data Model**, **CSV** et **JSON**. Pour utiliser l'exportation avec d'autres applications Dynamics 365, nous vous recommandons d'utiliser le format Common Data Model.

1. Dans l'étape **Choisir une destination**, spécifiez l'emplacement Azure Data Lake Storage Gen 2.
    1. Le nom de compte **ADLS Gen 2** représente le nom du compte de stockage dans lequel enregistrer l'exportation. 
    1. Le **Chemin du dossier** définit où l'exportation doit être stockée dans le système de fichiers et la structure de répertoires du compte de stockage.
    1. La **Clé partagée** est disponible sur le portail Azure pour le compte de stockage.

1. Examinez et confirmez vos sélections.

## <a name="view-and-manage-exports"></a>Afficher et gérer des exportations

Une fois que vous avez configuré une exportation, accédez à **Données** > **Exportations** pour la voir. Sélectionner **Plus [...]** pour toute exportation existante pour la modifier ou la supprimer.


[!INCLUDE[footer-include](../includes/footer-banner.md)]