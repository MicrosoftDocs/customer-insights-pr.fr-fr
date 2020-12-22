---
title: Créer et modifier des mesures
description: Définissez des mesures relatives aux clients pour analyser et refléter la performance de certains domaines d'activité.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405679"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="688fb-103">Définir et gérer des mesures</span><span class="sxs-lookup"><span data-stu-id="688fb-103">Define and manage measures</span></span>

<span data-ttu-id="688fb-104">Les **mesures** représentent des indicateurs de performance clés (KPI) qui reflètent la performance et la santé de secteurs d'activité spécifiques.</span><span class="sxs-lookup"><span data-stu-id="688fb-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="688fb-105">Audience Insights offre une expérience intuitive pour créer différents types de mesures, en utilisant un générateur de requêtes qui ne vous demande pas d'écrire du code ou de valider manuellement vos mesures.</span><span class="sxs-lookup"><span data-stu-id="688fb-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="688fb-106">Vous pouvez suivre vos mesures commerciales sur la page **Accueil**, voir les mesures pour des clients spécifiques sur la **Carte client** et utiliser des mesures pour définir les segments de clientèle de la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="688fb-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="688fb-107">Créer une mesure</span><span class="sxs-lookup"><span data-stu-id="688fb-107">Create a measure</span></span>

<span data-ttu-id="688fb-108">Cette section vous guide à travers la création d'une mesure à partir de zéro.</span><span class="sxs-lookup"><span data-stu-id="688fb-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="688fb-109">Vous pouvez générer des mesures en exploitant des données de plusieurs sources qui sont désormais connectées via l'entité Client.</span><span class="sxs-lookup"><span data-stu-id="688fb-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="688fb-110">Certaines [limites du service](service-limits.md) s'appliquent.</span><span class="sxs-lookup"><span data-stu-id="688fb-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="688fb-111">Dans Audience Insights, accédez à **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="688fb-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="688fb-112">Sélectionnez **Nouvelle mesure**.</span><span class="sxs-lookup"><span data-stu-id="688fb-112">Select **New measure**.</span></span>

3. <span data-ttu-id="688fb-113">Choisissez la mesure **Type** :</span><span class="sxs-lookup"><span data-stu-id="688fb-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="688fb-114">**Attribut client** : Un champ unique par client qui reflète un score, une valeur, ou un état du client.</span><span class="sxs-lookup"><span data-stu-id="688fb-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="688fb-115">Les attributs de client sont créés en tant qu'attributs dans une nouvelle entité générée par le système **Customer_Measure.**</span><span class="sxs-lookup"><span data-stu-id="688fb-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="688fb-116">**Mesure client** : Informations sur le comportement des clients avec répartition par dimensions sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="688fb-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="688fb-117">Une nouvelle entité est générée par mesure, avec plusieurs enregistrements potentiels par client.</span><span class="sxs-lookup"><span data-stu-id="688fb-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="688fb-118">**Mesure d'activité** : Effectue le suivi des performances et de la santé de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="688fb-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="688fb-119">Les mesures d’activité peuvent avoir deux sorties différentes : une sortie numérique qui apparaît sur la page d'**accueil** ou une nouvelle entité que vous trouvez sur la page **Entités**.</span><span class="sxs-lookup"><span data-stu-id="688fb-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="688fb-120">Indiquez un **Nom** et un **nom complet** (en option), puis sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="688fb-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="688fb-121">Pour la section **Entités**, sélectionnez la première entité dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="688fb-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="688fb-122">À ce stade, vous devez décider si les entités supplémentaires sont nécessaires dans le cadre de la définition de votre mesure.</span><span class="sxs-lookup"><span data-stu-id="688fb-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="688fb-123">![Définition de la mesure](media/measure-definition.png "Définition de la mesure")</span><span class="sxs-lookup"><span data-stu-id="688fb-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="688fb-124">Pour ajouter plus d'entités, sélectionnez **Ajouter une entité** et sélectionnez les entités que vous souhaitez utiliser pour la mesure.</span><span class="sxs-lookup"><span data-stu-id="688fb-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="688fb-125">Vous ne pouvez sélectionner que les entités qui ont une relation avec votre entité de départ.</span><span class="sxs-lookup"><span data-stu-id="688fb-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="688fb-126">Pour plus d'informations sur la définition des relations, voir [Relations](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="688fb-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="688fb-127">Vous pouvez, si vous le souhaitez, configurer des variables.</span><span class="sxs-lookup"><span data-stu-id="688fb-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="688fb-128">Dans la section **Variables**, sélectionnez **Nouvelle variable**.</span><span class="sxs-lookup"><span data-stu-id="688fb-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="688fb-129">Les variables sont des calculs effectués sur chacun des enregistrements de vos champs sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="688fb-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="688fb-130">Par exemple, en additionnant le PDV et les ventes en ligne pour chacun de vos enregistrements client.</span><span class="sxs-lookup"><span data-stu-id="688fb-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="688fb-131">Donnez un **nom** à la variable.</span><span class="sxs-lookup"><span data-stu-id="688fb-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="688fb-132">Dans la zone **Expression**, choisissez un champ pour commencer votre calcul.</span><span class="sxs-lookup"><span data-stu-id="688fb-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="688fb-133">Saisissez une expression dans la zone **Expression** tout en choisissant plus de champs à inclure dans votre calcul.</span><span class="sxs-lookup"><span data-stu-id="688fb-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="688fb-134">Actuellement, seules les expressions arithmétiques sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="688fb-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="688fb-135">En outre, le calcul des variables n'est pas pris en charge pour les entités provenant de différents [chemins d'entité](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="688fb-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="688fb-136">Sélectionnez **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="688fb-136">Select **Done**.</span></span>

11. <span data-ttu-id="688fb-137">Dans la section **Définition de la mesure**, vous devez définir la manière dont les entités que vous avez choisies et les variables calculées sont agrégées dans une nouvelle entité de mesure ou un nouvel attribut Mesure.</span><span class="sxs-lookup"><span data-stu-id="688fb-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="688fb-138">Sélectionnez **Nouvelle dimension**.</span><span class="sxs-lookup"><span data-stu-id="688fb-138">Select **New dimension**.</span></span> <span data-ttu-id="688fb-139">Vous pouvez considérer une dimension comme une fonction *Regrouper par*.</span><span class="sxs-lookup"><span data-stu-id="688fb-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="688fb-140">Les données de votre nouvel attribut ou entité Mesure seront regroupées selon toutes vos dimensions définies.</span><span class="sxs-lookup"><span data-stu-id="688fb-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="688fb-141">![Choisir un cycle de regroupement](media/measures-businessreport-measure-definition2.png "Choisir un cycle de regroupement")</span><span class="sxs-lookup"><span data-stu-id="688fb-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="688fb-142">Sélectionnez ou entrez les informations suivantes dans le cadre de la définition de votre dimension :</span><span class="sxs-lookup"><span data-stu-id="688fb-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="688fb-143">**Entité** : Si vous définissez une entité Mesure, elle doit inclure au moins un attribut.</span><span class="sxs-lookup"><span data-stu-id="688fb-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="688fb-144">Si vous définissez un attribut Mesure, il contiendra uniquement un attribut par défaut.</span><span class="sxs-lookup"><span data-stu-id="688fb-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="688fb-145">Cette sélection a pour but de choisir l'entité contenant cet attribut.</span><span class="sxs-lookup"><span data-stu-id="688fb-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="688fb-146">**Champ** : sélectionnez l'attribut approprié à inclure dans votre entité ou votre attribut Mesure.</span><span class="sxs-lookup"><span data-stu-id="688fb-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="688fb-147">**Compartiment** : choisissez si vous voulez regrouper les données sur une base quotidienne, mensuelle ou annuelle.</span><span class="sxs-lookup"><span data-stu-id="688fb-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="688fb-148">Il s'agit d'une sélection uniquement nécessaire si vous avez sélectionné un attribut de type Date.</span><span class="sxs-lookup"><span data-stu-id="688fb-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="688fb-149">**En tant que** : Définit le nom de votre nouveau champ.</span><span class="sxs-lookup"><span data-stu-id="688fb-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="688fb-150">**Nom complet** : Définit le nom complet de votre champ.</span><span class="sxs-lookup"><span data-stu-id="688fb-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="688fb-151">Votre mesure d'activité est enregistrée en tant qu'entité à un seul chiffre et s'affiche dans la page d'**accueil**, à moins que vous ajoutiez d'autres dimensions à votre mesure.</span><span class="sxs-lookup"><span data-stu-id="688fb-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="688fb-152">Après avoir ajouté d'autres dimensions, la mesure *ne s'affichera pas* sur la page d'**accueil**.</span><span class="sxs-lookup"><span data-stu-id="688fb-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="688fb-153">Vous pouvez ajouter des fonctions d'agrégation si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="688fb-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="688fb-154">Toute agrégation que vous créez a pour résultat une nouvelle valeur dans votre entité ou votre attribut Mesures.</span><span class="sxs-lookup"><span data-stu-id="688fb-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="688fb-155">Les fonctions d'agrégation prises en charge sont : **Min**, **Max**, **Moyenne**, **Médian**, **Somme**, **Nombre Unique**, **Premier** (prend le premier enregistrement d'une valeur de dimension) et **Dernier** (prend le dernier enregistrement ajouté à une valeur de dimension).</span><span class="sxs-lookup"><span data-stu-id="688fb-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="688fb-156">Sélectionnez **Enregistrer** pour appliquer vos modifications à la mesure.</span><span class="sxs-lookup"><span data-stu-id="688fb-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="688fb-157">Gérer vos mesures</span><span class="sxs-lookup"><span data-stu-id="688fb-157">Manage your measures</span></span>

<span data-ttu-id="688fb-158">Après avoir créé au moins une mesure, vous verrez une liste de mesures sur la page **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="688fb-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="688fb-159">Vous trouverez des informations sur le type de mesure, le créateur, la date et l'heure de création, la dernière date et heure de modification, le statut (si la mesure est active, inactive ou échouée) et la dernière date et heure d'actualisation.</span><span class="sxs-lookup"><span data-stu-id="688fb-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="688fb-160">Lorsque vous sélectionnez une mesure dans la liste, vous pouvez afficher un aperçu de sa sortie.</span><span class="sxs-lookup"><span data-stu-id="688fb-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="688fb-161">Pour actualiser toutes vos mesures en même temps, sélectionnez **Actualiser tout** sans sélectionner une mesure spécifique.</span><span class="sxs-lookup"><span data-stu-id="688fb-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="688fb-162">![Actions pour gérer des mesures uniques](media/measure-actions.png "Actions pour gérer des mesures uniques")</span><span class="sxs-lookup"><span data-stu-id="688fb-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="688fb-163">Vous pouvez également sélectionner une mesure dans la liste et effectuer l'une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="688fb-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="688fb-164">Sélectionner le nom de la mesure pour afficher ses détails.</span><span class="sxs-lookup"><span data-stu-id="688fb-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="688fb-165">**Modifier** la configuration de la mesure.</span><span class="sxs-lookup"><span data-stu-id="688fb-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="688fb-166">**Renommer** la mesure.</span><span class="sxs-lookup"><span data-stu-id="688fb-166">**Rename** the measure.</span></span>
- <span data-ttu-id="688fb-167">**Supprimer** la mesure.</span><span class="sxs-lookup"><span data-stu-id="688fb-167">**Delete** the measure.</span></span>
- <span data-ttu-id="688fb-168">Sélectionner les points de suspension (...) puis **Actualiser** pour démarrer le processus d'actualisation de la mesure.</span><span class="sxs-lookup"><span data-stu-id="688fb-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="688fb-169">Sélectionner les points de suspension (...) puis **Télécharger** pour obtenir un fichier .CSV de la mesure.</span><span class="sxs-lookup"><span data-stu-id="688fb-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="688fb-170">Il existe [six types de statuts](system.md#status-types) pour les tâches/processus.</span><span class="sxs-lookup"><span data-stu-id="688fb-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="688fb-171">En outre, la plupart des processus [dépendent d'autres processus en aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="688fb-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="688fb-172">Vous pouvez sélectionner le statut d'un processus pour afficher des détails sur la progression de toute la tâche.</span><span class="sxs-lookup"><span data-stu-id="688fb-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="688fb-173">Après avoir sélectionné **Voir les détails** pour l'une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.</span><span class="sxs-lookup"><span data-stu-id="688fb-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="688fb-174">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="688fb-174">Next step</span></span>

<span data-ttu-id="688fb-175">Vous pouvez utiliser les mesures existantes pour créer votre premier segment de clientèle sur la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="688fb-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="688fb-176">Pour plus d'informations, voir [Segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="688fb-176">For more information, see [Segments](segments.md).</span></span>
