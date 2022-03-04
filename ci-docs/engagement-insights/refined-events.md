---
title: Créer et modifier des événements
description: Procédure de création et de modification d’événements.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: dbafa2231daa82c34ee2ec8292111575e95af675
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228200"
---
# <a name="create-and-modify-events"></a>Créer et modifier des événements

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Un événement est une donnée qui représente le comportement de l'utilisateur, comme l'activité sur un site Web.

- Un événement de *base* enregistre lorsqu'un utilisateur consulte une page (événement d'affichage) ou interagit avec le contenu (événement d'action).
- Un événement *affiné* est une vue virtuelle d'un événement de base. Vous devez définir des événements affinés en supprimant et en ajoutant des propriétés ou en filtrant les événements en fonction des valeurs de propriété.

## <a name="prerequisites"></a>Conditions préalables

Pour obtenir des événements, commencez par connecter les données de votre site web aux informations sur l’engagement à l’aide d’un extrait de code. Pour plus d’informations, consultez [Installer le Kit de développement logiciel (SDK) web sur un site web](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Commencez par connecter vos données.":::

## <a name="create-refined-events"></a>Créer des événements affinés

Utilisez des événements affinés pour réduire la portée d'un événement de base pour [exporter](export-events.md) ou supprimer les propriétés qui ne sont pas nécessaires pour l'exposition.

> [!NOTE]
> Une fois que vous avez ajouté le Kit de développement logiciel (SDK) web à votre site web, vous pouvez afficher vos événements de base et créer des événements affinés. 

Pour afficher vos événements de base :

1. Accédez à **Données** dans le volet de navigation de gauche.

1. Sélectionnez **Événements** pour voir la liste de tous les événements dans l’espace de travail.

    :::image type="content" source="media/data-events.png" alt-text="Affichez les événements.":::

Pour créer un événement raffiné à partir d’un événement de base : 

1. Accédez à **Données** > **Événements** et sélectionnez **+ Nouveaux événements** en haut de l’écran.

1. Dans la boîte de dialogue **Nouveaux événements**, sélectionnez **Créer des événements affinés**, puis sélectionnez **Suivant**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Assistant Nouveaux événements.":::
     
1. Dans la boîte de dialogue **Nouveaux événements**, entrez les informations suivantes :

   - Sélectionnez un événement dans la liste déroulante **Événements de base**.
   - Entrez un nom dans la zone **Nom d’affichage des événements affinés**.
   - Vous pouvez si vous le souhaitez mettre à jour le **Nom réel** sans utiliser d'espaces.

1. Sélectionnez **Créer** pour appliquer vos paramètres.

L’événement affiné apparaît maintenant dans votre liste **Événements**.

### <a name="edit-event-name"></a>Modifier le nom d'un événement

Vous pouvez modifier le nom et les propriétés d’un événement de base ou affiné.

1. Allez dans **Données** > **Événements**. 

1. Sélectionnez **Plus [...]** pour un événement et sélectionnez **Modifier le nom**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Options pour créer des événements affinés.":::

3. Mettez à jour le nom de l'événement et sélectionnez **Renommer**.

### <a name="view-the-details-of-a-refined-event"></a>Afficher les détails d’un événement affiné :

1. Dans la liste **Événement**, sélectionnez votre événement de base ou affiné. 

1. Sélectionnez **Ajouter et supprimer des propriétés** en haut de l’écran pour ouvrir le volet **Modifier les propriétés**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Ajoutez et supprimez des propriétés.":::

1. Utilisez les cases à cocher pour sélectionner les propriétés que vous souhaitez afficher et celles que vous souhaitez masquer. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Modifier les propriétés des événements affinés.":::

1. Sélectionnez **Confirmer** pour appliquer votre sélection, puis sélectionnez **Enregistrer**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Modifier les propriétés sélectionnées pour un événement affiné

1. Allez dans **Données** > **Événements** et sélectionnez les événements affinés pour ouvrir la vue détaillée.
1. Sélectionnez **Ajouter et supprimer des propriétés**. 
1. Modifiez la sélection des cases à cocher.
1. Sélectionnez **Confirmer**, puis **Enregistrer** pour appliquer les modifications.

Pour plus d'informations sur l'exportation des événements, voir [Exporter des événements](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
