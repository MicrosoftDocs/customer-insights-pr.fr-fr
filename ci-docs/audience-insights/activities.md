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
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667226"
---
# <a name="customer-activities"></a><span data-ttu-id="1cae9-103">Activités du client</span><span class="sxs-lookup"><span data-stu-id="1cae9-103">Customer activities</span></span>

<span data-ttu-id="1cae9-104">Combinez les activités clientes de [différentes sources de données](data-sources.md) dans Dynamics 365 Customer Insights pour créer une chronologie client qui répertorie les activités par ordre chronologique.</span><span class="sxs-lookup"><span data-stu-id="1cae9-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="1cae9-105">Vous pouvez inclure la chronologie dans les applications Customer Engagement dans Dynamics 365 via le [Complément de carte client](customer-card-add-in.md), ou dans un tableau de bord Power BI.</span><span class="sxs-lookup"><span data-stu-id="1cae9-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="1cae9-106">Définir une activité</span><span class="sxs-lookup"><span data-stu-id="1cae9-106">Define an activity</span></span>

<span data-ttu-id="1cae9-107">Vos sources de données incluent des entités avec des données transactionnelles et d'activité provenant de plusieurs sources de données.</span><span class="sxs-lookup"><span data-stu-id="1cae9-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="1cae9-108">Identifiez ces entités et sélectionnez les activités que vous souhaitez afficher sur la chronologie du client.</span><span class="sxs-lookup"><span data-stu-id="1cae9-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="1cae9-109">Sélectionnez l'entité qui comprend votre activité ou vos activités cibles.</span><span class="sxs-lookup"><span data-stu-id="1cae9-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="1cae9-110">Dans Audience Insights, accédez à **Données** > **Activités**.</span><span class="sxs-lookup"><span data-stu-id="1cae9-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="1cae9-111">Sélectionnez **Ajouter une activité**.</span><span class="sxs-lookup"><span data-stu-id="1cae9-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1cae9-112">Une entité doit avoir au moins un attribut de type **Date** à inclure dans une chronologie client et vous ne pouvez pas ajouter d'entités sans champs **Date**.</span><span class="sxs-lookup"><span data-stu-id="1cae9-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="1cae9-113">Le contrôle **Ajouter une activité** est désactivé si aucune entité de ce type n'est trouvée.</span><span class="sxs-lookup"><span data-stu-id="1cae9-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="1cae9-114">Dans le volet **Ajouter une activité**, définissez les valeurs des champs suivants :</span><span class="sxs-lookup"><span data-stu-id="1cae9-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="1cae9-115">**Entité** : Sélectionnez une entité qui contient des données transactionnelles ou d'activité.</span><span class="sxs-lookup"><span data-stu-id="1cae9-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="1cae9-116">**Clé primaire** : Sélectionnez le champ qui identifie de manière unique un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="1cae9-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="1cae9-117">Il ne doit contenir aucune valeur en double, vide ou manquante.</span><span class="sxs-lookup"><span data-stu-id="1cae9-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="1cae9-118">**Horodateur** : Sélectionnez le champ qui représente l'heure de début de votre activité.</span><span class="sxs-lookup"><span data-stu-id="1cae9-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="1cae9-119">**Événement** : Sélectionnez le champ représentant l'événement de l'activité.</span><span class="sxs-lookup"><span data-stu-id="1cae9-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="1cae9-120">**Adresse Web** : Sélectionnez le champ qui représente une URL fournissant des informations supplémentaires sur cette activité.</span><span class="sxs-lookup"><span data-stu-id="1cae9-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="1cae9-121">Par exemple, le système transactionnel d'où provient cette activité.</span><span class="sxs-lookup"><span data-stu-id="1cae9-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="1cae9-122">Cette URL peut être n'importe quel champ de la source de données, ou elle peut être construite comme un nouveau champ à l'aide d'une transformation Power Query.</span><span class="sxs-lookup"><span data-stu-id="1cae9-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="1cae9-123">Ces données URL seront stockées dans l'entité Activité unifiée, qui peut être consommée en aval à l'aide d'API.</span><span class="sxs-lookup"><span data-stu-id="1cae9-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="1cae9-124">**Détails** : Vous pouvez éventuellement sélectionner ce champ pour fournir plus de détails.</span><span class="sxs-lookup"><span data-stu-id="1cae9-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="1cae9-125">**Icône** : Vous pouvez éventuellement sélectionner l'icône représentant cette activité.</span><span class="sxs-lookup"><span data-stu-id="1cae9-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="1cae9-126">**Type d'activité** : Définissez la référence du type d'activité au Common Data Model qui décrit le mieux la définition sémantique de l'activité.</span><span class="sxs-lookup"><span data-stu-id="1cae9-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="1cae9-127">Dans la section **Définir la relation**, configurez les détails permettant de connecter vos données d'activité à leur client correspondant.</span><span class="sxs-lookup"><span data-stu-id="1cae9-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1cae9-128">![Définir la relation entre les entités](media/activities-entities-define.png "Définir la relation entre les entités")</span><span class="sxs-lookup"><span data-stu-id="1cae9-128">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

    - <span data-ttu-id="1cae9-129">**Champ d'entité d'activité** : Sélectionnez le champ de votre entité d'activité qui permettra d'établir une relation avec une autre entité.</span><span class="sxs-lookup"><span data-stu-id="1cae9-129">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="1cae9-130">**Entité client** : Sélectionnez l'entité client source correspondante avec laquelle votre entité d'activité sera en relation.</span><span class="sxs-lookup"><span data-stu-id="1cae9-130">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="1cae9-131">Vous ne pouvez créer une relation qu'avec les entités client sources utilisées dans le processus d'unification des données.</span><span class="sxs-lookup"><span data-stu-id="1cae9-131">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="1cae9-132">**Champ d'entité client** : Ce champ affiche la clé primaire de l'entité client source sélectionnée dans le processus de mise en correspondance.</span><span class="sxs-lookup"><span data-stu-id="1cae9-132">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="1cae9-133">Ce champ de clé primaire dans l'entité client source permet d'établir une relation avec l'entité d'activité.</span><span class="sxs-lookup"><span data-stu-id="1cae9-133">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="1cae9-134">**Nom** : S'il existe déjà une relation entre cette entité d'activité et l'entité client source sélectionnée, le nom de la relation sera en mode lecture seule.</span><span class="sxs-lookup"><span data-stu-id="1cae9-134">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="1cae9-135">S'il n'existe aucune relation de ce type, une nouvelle relation sera créée avec le nom fourni ici.</span><span class="sxs-lookup"><span data-stu-id="1cae9-135">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>

1. <span data-ttu-id="1cae9-136">Sélectionnez **Enregistrer** pour appliquer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="1cae9-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="1cae9-137">Dans la page **Activité**, sélectionnez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="1cae9-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="1cae9-138">Il existe [six types de statuts](system.md#status-types) pour les tâches/processus.</span><span class="sxs-lookup"><span data-stu-id="1cae9-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="1cae9-139">En outre, la plupart des processus [dépendent d'autres processus en aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="1cae9-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="1cae9-140">Vous pouvez sélectionner le statut d'un processus pour afficher des détails sur la progression de toute la tâche.</span><span class="sxs-lookup"><span data-stu-id="1cae9-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="1cae9-141">Après avoir sélectionné **Voir les détails** pour l'une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.</span><span class="sxs-lookup"><span data-stu-id="1cae9-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="1cae9-142">Modifier une activité</span><span class="sxs-lookup"><span data-stu-id="1cae9-142">Edit an activity</span></span>

1. <span data-ttu-id="1cae9-143">Dans Audience Insights, accédez à **Données** > **Activités**.</span><span class="sxs-lookup"><span data-stu-id="1cae9-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="1cae9-144">Sélectionnez l'entité d'activité que vous souhaitez modifier et sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="1cae9-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="1cae9-145">Vous pouvez également pointer sur la ligne d'entité et sélectionner l'icône **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="1cae9-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="1cae9-146">Cliquez sur l'icône **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="1cae9-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="1cae9-147">Dans le volet **Modifier l'activité**, mettez à jour les valeurs et sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1cae9-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="1cae9-148">Dans la page **Activité**, sélectionnez **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="1cae9-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="1cae9-149">Supprimer une activité</span><span class="sxs-lookup"><span data-stu-id="1cae9-149">Delete an activity</span></span>

1. <span data-ttu-id="1cae9-150">Dans Audience Insights, accédez à **Données** > **Activités**.</span><span class="sxs-lookup"><span data-stu-id="1cae9-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="1cae9-151">Sélectionnez l'entité d'activité que vous souhaitez supprimer et sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="1cae9-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="1cae9-152">Vous pouvez également pointer sur la ligne d'entité et sélectionner l'icône **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="1cae9-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="1cae9-153">En outre, vous pouvez sélectionner simultanément plusieurs entités d'activité à supprimer.</span><span class="sxs-lookup"><span data-stu-id="1cae9-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1cae9-154">![Modifier ou supprimer la relation d'entité](media/activities-entities-edit-delete.png "Modifier ou supprimer la relation d'entité")</span><span class="sxs-lookup"><span data-stu-id="1cae9-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="1cae9-155">Sélectionnez l'icône **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="1cae9-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="1cae9-156">Confirmez votre suppression.</span><span class="sxs-lookup"><span data-stu-id="1cae9-156">Confirm your deletion.</span></span>
