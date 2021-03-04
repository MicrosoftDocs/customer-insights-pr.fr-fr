---
title: Activités du client
description: Définissez les activités client et affichez-les dans la chronologie client.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267429"
---
# <a name="customer-activities"></a>Activités du client

Combinez les activités clientes de [différentes sources de données](data-sources.md) dans Dynamics 365 Customer Insights pour créer une chronologie client qui répertorie les activités par ordre chronologique. Vous pouvez inclure la chronologie dans les applications Customer Engagement dans Dynamics 365 via le [Complément de carte client](customer-card-add-in.md), ou dans un tableau de bord Power BI.

## <a name="define-an-activity"></a>Définir une activité

Vos sources de données incluent des entités avec des données transactionnelles et d’activité provenant de plusieurs sources de données. Identifiez ces entités et sélectionnez les activités que vous souhaitez afficher sur la chronologie du client. Sélectionnez l’entité qui comprend votre activité ou vos activités cibles.

1. Dans les informations sur l’audience, accédez à **Données** > **Activités**.

1. Sélectionnez **Ajouter une activité**.

   > [!NOTE]
   > Une entité doit avoir au moins un attribut de type **Date** à inclure dans une chronologie client et vous ne pouvez pas ajouter d’entités sans champs **Date**. Le contrôle **Ajouter une activité** est désactivé si aucune entité de ce type n’est trouvée.

1. Dans le volet **Ajouter une activité**, définissez les valeurs des champs suivants :

   - **Entité** : Sélectionnez une entité qui contient des données transactionnelles ou d’activité.
   - **Clé primaire** : Sélectionnez le champ qui identifie de manière unique un enregistrement. Il ne doit contenir aucune valeur en double, vide ou manquante.
   - **Horodateur** : Sélectionnez le champ qui représente l’heure de début de votre activité.
   - **Événement** : Sélectionnez le champ représentant l’événement de l’activité.
   - **Adresse Web** : Sélectionnez le champ qui représente une URL fournissant des informations supplémentaires sur cette activité. Par exemple, le système transactionnel d’où provient cette activité. Cette URL peut être n’importe quel champ de la source de données, ou elle peut être construite comme un nouveau champ à l’aide d’une transformation Power Query. Ces données URL seront stockées dans l’entité Activité unifiée, qui peut être consommée en aval à l’aide d’API.
   - **Détails** : Vous pouvez éventuellement sélectionner ce champ pour fournir plus de détails.
   - **Icône** : Vous pouvez éventuellement sélectionner l’icône représentant cette activité.
   - **Type d’activité** : Définissez la référence du type d’activité au Common Data Model qui décrit le mieux la définition sémantique de l’activité.

1. Dans la section **Définir la relation**, configurez les détails permettant de connecter vos données d’activité à leur client correspondant.

    - **Champ d’entité d’activité** : Sélectionnez le champ de votre entité d’activité qui permettra d’établir une relation avec une autre entité.
    - **Entité client** : Sélectionnez l’entité client source correspondante avec laquelle votre entité d’activité sera en relation. Vous ne pouvez créer une relation qu’avec les entités client sources utilisées dans le processus d’unification des données.
    - **Champ d’entité client** : Ce champ affiche la clé primaire de l’entité client source sélectionnée dans le processus de mise en correspondance. Ce champ de clé primaire dans l’entité client source permet d’établir une relation avec l’entité d’activité.
    - **Nom** : S’il existe déjà une relation entre cette entité d’activité et l’entité client source sélectionnée, le nom de la relation sera en mode lecture seule. S’il n’existe aucune relation de ce type, une nouvelle relation sera créée avec le nom fourni ici.
   
   > [!div class="mx-imgBorder"]
   > ![Définir la relation entre les entités](media/activities-entities-define.png "Définir la relation entre les entités")

1. Sélectionnez **Enregistrer** pour appliquer vos modifications.

1. Dans la page **Activité**, sélectionnez **Exécuter**.

> [!TIP]
> Il existe [six types de statuts](system.md#status-types) pour les tâches/processus. En outre, la plupart des processus [dépendent d’autres processus en aval](system.md#refresh-policies). Vous pouvez sélectionner le statut d’un processus pour afficher des détails sur la progression de toute la tâche. Après avoir sélectionné **Voir les détails** pour l’une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.

## <a name="edit-an-activity"></a>Modifier une activité

1. Dans les informations sur l’audience, accédez à **Données** > **Activités**.

2. Sélectionnez l’entité d’activité que vous souhaitez modifier et sélectionnez **Modifier**. Vous pouvez également pointer sur la ligne d’entité et sélectionner l’icône **Modifier**.

3. Cliquez sur l’icône **Modifier**.

4. Dans le volet **Modifier l’activité**, mettez à jour les valeurs et sélectionnez **Enregistrer**.

5. Dans la page **Activité**, sélectionnez **Exécuter**.

## <a name="delete-an-activity"></a>Supprimer une activité

1. Dans les informations sur l’audience, accédez à **Données** > **Activités**.

2. Sélectionnez l’entité d’activité que vous souhaitez supprimer et sélectionnez **Supprimer**. Vous pouvez également pointer sur la ligne d’entité et sélectionner l’icône **Supprimer**. En outre, vous pouvez sélectionner simultanément plusieurs entités d’activité à supprimer.
   > [!div class="mx-imgBorder"]
   > ![Modifier ou supprimer la relation d’entité](media/activities-entities-edit-delete.png "Modifier ou supprimer la relation d’entité")

3. Sélectionnez l’icône **Supprimer**.

4. Confirmez votre suppression.


[!INCLUDE[footer-include](../includes/footer-banner.md)]