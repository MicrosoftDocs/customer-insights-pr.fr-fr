---
title: Créer et modifier des événements affinés
description: Comment créer et modifier des événements affinés.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ea2940ef79871ce9dedc3091b95515d5b8a7ecce
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555704"
---
# <a name="create-and-modify-refined-events"></a>Créer et modifier des événements affinés

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Un événement est une donnée qui représente le comportement de l'utilisateur, comme l'activité sur un site Web.

- Un événement de *base* enregistre lorsqu'un utilisateur consulte une page (événement d'affichage) ou interagit avec le contenu (événement d'action).
- Un événement *affiné* est une vue virtuelle d'un événement de base. Vous devez définir des événements affinés en supprimant et en ajoutant des propriétés ou en filtrant les événements en fonction des valeurs de propriété.

Utilisez des événements affinés pour réduire la portée d'un événement de base pour [exporter](export-events.md) ou supprimer les propriétés qui ne sont pas nécessaires pour l'exposition.

## <a name="create-refined-events"></a>Créer des événements raffinés

Il existe trois façons de créer un événement affiné à partir d'un événement de base. 

1. Accédez à **Données**> **Événements** et choisissez l'une des options suivantes :
    - Sélectionnez **Nouveaux événements**, puis **Créer des événements affinés**.
    - Sélectionnez un événement de base pour ouvrir une vue détaillée et sélectionnez **Créer des événements affinés** dans le menu du haut.
    - Sélectionnez **Plus [...]** pour ouvrir le menu contextuel d'un événement de base. Puis sélectionnez **Créer des événements affinés**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Options pour créer des événements affinés.":::

1. Dans la boîte de dialogue **Créer des événements affinés**, tapez les informations suivantes :

- Sélectionnez un événement dans la liste déroulante **Événements de base** si vous créez un nouvel événement.
- Entrez un nom dans la zone **Nom d’affichage des événements affinés**.
- Vous pouvez si vous le souhaitez mettre à jour le **Nom réel** sans utiliser d'espaces.

3. Sélectionnez **Créer** pour appliquer vos paramètres.

1. Dans la vue détaillée de votre événement affiné, sélectionnez **Ajouter et supprimer des propriétés** pour ouvrir le volet **Modifier les propriétés**. 

1. Utilisez les cases à cocher pour sélectionner les propriétés que vous souhaitez afficher et celles que vous souhaitez masquer. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Modifier les propriétés des événements affinés.":::

1. Sélectionnez **Confirmer** pour appliquer votre sélection.

1. Sélectionnez **Enregistrer** pour enregistrer la configuration.

## <a name="edit-refined-events"></a>Modifier les événements affinés

Vous pouvez modifier le nom et les propriétés d'un événement affiné.

### <a name="edit-event-name"></a>Modifier le nom d'un événement

1. Allez dans **Données** > **Événements**. 
1. Sélectionnez **Plus [...]** pour un événement et sélectionnez **Modifier le nom**.
1. Mettez à jour le nom de l'événement et sélectionnez **Renommer**.

### <a name="edit-selected-properties"></a>Modifier les propriétés sélectionnées

1. Allez dans **Données** > **Événements** et sélectionnez les événements affinés pour ouvrir la vue détaillée.
1. Sélectionnez **Ajouter et supprimer des propriétés**. 
1. Modifiez la sélection des cases à cocher.
1. Sélectionnez **Confirmer**, puis **Enregistrer** pour appliquer les modifications.

Pour plus d'informations sur l'exportation des événements, voir [Exporter des événements](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
