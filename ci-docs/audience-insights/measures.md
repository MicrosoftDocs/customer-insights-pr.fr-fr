---
title: Créer et gérer des mesures
description: Définir des mesures pour analyser et refléter la performance de votre entreprise.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654729"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="73094-103">Définir et gérer des mesures</span><span class="sxs-lookup"><span data-stu-id="73094-103">Define and manage measures</span></span>

<span data-ttu-id="73094-104">Les mesures vous aident à mieux comprendre les comportements des clients et les performances commerciales en récupérant les valeurs pertinentes des [profils unifiés](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="73094-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="73094-105">Par exemple, une entreprise souhaite voir le *total des dépenses par client* pour comprendre l’historique d’achat de chaque client.</span><span class="sxs-lookup"><span data-stu-id="73094-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="73094-106">Ou mesurer le *total des ventes de l’entreprise* pour comprendre les revenus au niveau agrégé dans l’ensemble de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="73094-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="73094-107">Les mesures sont créées à l’aide du générateur de mesures, une plateforme de requête de données avec divers opérateurs et des options de mappage simples.</span><span class="sxs-lookup"><span data-stu-id="73094-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="73094-108">Elle vous permet de filtrer les données, de regrouper les résultats, de détecter les [chemins d’accès aux relations d’entités](relationships.md) et prévisualisez la sortie.</span><span class="sxs-lookup"><span data-stu-id="73094-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="73094-109">Utilisez le générateur de mesures pour planifier les activités commerciales en interrogeant les données client et en extrayant des informations.</span><span class="sxs-lookup"><span data-stu-id="73094-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="73094-110">Par exemple, créer une mesure de *total des dépenses par client* et de *total des retours par client* aide à identifier un groupe de clients avec des dépenses élevées mais un rendement élevé.</span><span class="sxs-lookup"><span data-stu-id="73094-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="73094-111">Vous pouvez [créer un segment](segments.md) pour conduire les meilleures actions suivantes.</span><span class="sxs-lookup"><span data-stu-id="73094-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="73094-112">Créer une mesure</span><span class="sxs-lookup"><span data-stu-id="73094-112">Create a measure</span></span>

<span data-ttu-id="73094-113">Cette section vous guide tout au long de la création d’une mesure à partir de zéro.</span><span class="sxs-lookup"><span data-stu-id="73094-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="73094-114">Vous pouvez créer une mesure avec des attributs de données à partir d’entités de données ayant une relation configurée pour se connecter à l’entité Client.</span><span class="sxs-lookup"><span data-stu-id="73094-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="73094-115">Dans les informations sur l’audience, accédez à **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="73094-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="73094-116">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="73094-116">Select **New**.</span></span>

1. <span data-ttu-id="73094-117">Sélectionnez **Modifier le nom** et fournissez un **Nom** pour la mesure.</span><span class="sxs-lookup"><span data-stu-id="73094-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="73094-118">Si votre nouvelle configuration de mesure ne comporte que deux champs, par exemple, CustomerID et un calcul, la sortie sera ajoutée en tant que nouvelle colonne à l’entité générée par le système appelée Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="73094-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="73094-119">Et vous pourrez voir la valeur de la mesure dans le profil client unifié.</span><span class="sxs-lookup"><span data-stu-id="73094-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="73094-120">D’autres mesures généreront leurs propres entités.</span><span class="sxs-lookup"><span data-stu-id="73094-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="73094-121">Dans la zone de configuration, choisissez la fonction d’agrégation dans le menu déroulant **Sélectionnez la fonction**.</span><span class="sxs-lookup"><span data-stu-id="73094-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="73094-122">Les fonctions d’agrégation comprennent :</span><span class="sxs-lookup"><span data-stu-id="73094-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="73094-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="73094-123">**Sum**</span></span>
   - <span data-ttu-id="73094-124">**Moyenne**</span><span class="sxs-lookup"><span data-stu-id="73094-124">**Average**</span></span>
   - <span data-ttu-id="73094-125">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="73094-125">**Count**</span></span>
   - <span data-ttu-id="73094-126">**Nombre Unique**</span><span class="sxs-lookup"><span data-stu-id="73094-126">**Count Unique**</span></span>
   - <span data-ttu-id="73094-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="73094-127">**Max**</span></span>
   - <span data-ttu-id="73094-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="73094-128">**Min**</span></span>
   - <span data-ttu-id="73094-129">**Première** : prend la première valeur de l’enregistrement de données</span><span class="sxs-lookup"><span data-stu-id="73094-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="73094-130">**Dernière** : prend la dernière valeur ajoutée à l’enregistrement de données</span><span class="sxs-lookup"><span data-stu-id="73094-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Opérateurs pour les calculs de mesures.":::

1. <span data-ttu-id="73094-132">Sélectionnez **Ajouter un attribut** pour sélectionner les données dont vous avez besoin pour créer cette mesure.</span><span class="sxs-lookup"><span data-stu-id="73094-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="73094-133">Sélectionnez l’onglet **Attributs**.</span><span class="sxs-lookup"><span data-stu-id="73094-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="73094-134">Entité Data : Choisissez l’entité qui comprend l’attribut selon lequel vous souhaitez mesurer.</span><span class="sxs-lookup"><span data-stu-id="73094-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="73094-135">Attribut de données : choisissez l’attribut que vous souhaitez utiliser dans la fonction d’agrégation pour calculer la mesure.</span><span class="sxs-lookup"><span data-stu-id="73094-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="73094-136">Vous ne pouvez sélectionner qu’un attribut à la fois.</span><span class="sxs-lookup"><span data-stu-id="73094-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="73094-137">Vous pouvez également sélectionner un attribut de données à partir d’une mesure existante en sélectionnant l’onglet **Mesures**. Sinon, vous pouvez rechercher un nom d’entité ou de mesure.</span><span class="sxs-lookup"><span data-stu-id="73094-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="73094-138">Sélectionnez **Ajouter** pour ajouter l’attribut sélectionné à la mesure.</span><span class="sxs-lookup"><span data-stu-id="73094-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Sélectionnez un attribut à utiliser dans les calculs.":::

1. <span data-ttu-id="73094-140">Pour créer des mesures plus complexes, vous pouvez ajouter plus d’attributs ou utiliser des opérateurs mathématiques sur votre fonction de mesure.</span><span class="sxs-lookup"><span data-stu-id="73094-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Créez une mesure complexe avec des opérateurs mathématiques.":::

1. <span data-ttu-id="73094-142">Pour ajouter des filtres, sélectionnez le **Filtre** dans la zone de configuration.</span><span class="sxs-lookup"><span data-stu-id="73094-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="73094-143">Dans la section **Ajouter un attribut** du volet **Filtres**, sélectionnez l’attribut que vous souhaitez utiliser pour créer des filtres.</span><span class="sxs-lookup"><span data-stu-id="73094-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="73094-144">Définissez les opérateurs de filtre pour définir le filtre pour chaque attribut sélectionné.</span><span class="sxs-lookup"><span data-stu-id="73094-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="73094-145">Sélectionnez **Appliquer** pour ajouter les filtres à la mesure.</span><span class="sxs-lookup"><span data-stu-id="73094-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="73094-146">Pour ajouter des dimensions, sélectionnez **Dimension** dans la zone de configuration.</span><span class="sxs-lookup"><span data-stu-id="73094-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="73094-147">Les dimensions s’affichent sous forme de colonnes dans l’entité de sortie de mesure.</span><span class="sxs-lookup"><span data-stu-id="73094-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="73094-148">Sélectionnez **Modifier les dimensions** pour ajouter des attributs de données par lesquels vous souhaitez regrouper les valeurs de mesure.</span><span class="sxs-lookup"><span data-stu-id="73094-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="73094-149">Par exemple, ville ou sexe.</span><span class="sxs-lookup"><span data-stu-id="73094-149">For example, city or gender.</span></span> <span data-ttu-id="73094-150">Par défaut, la dimension *CustomerID* est sélectionnée pour créer des *mesures au niveau du client*.</span><span class="sxs-lookup"><span data-stu-id="73094-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="73094-151">Vous pouvez supprimer la dimension par défaut si vous souhaitez créer des *mesures au niveau de l’entreprise*.</span><span class="sxs-lookup"><span data-stu-id="73094-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="73094-152">Sélectionnez **Terminé** pour ajouter les dimensions à la mesure.</span><span class="sxs-lookup"><span data-stu-id="73094-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="73094-153">S’il existe plusieurs chemins d’accès entre l’entité de données que vous avez mappée et l’entité *Client*, vous devez choisir l’un des [chemins d’accès de relation d’entité](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="73094-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="73094-154">Les résultats de la mesure peuvent varier en fonction du chemin sélectionné.</span><span class="sxs-lookup"><span data-stu-id="73094-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="73094-155">Sélectionnez **Préférences de données** et choisissez le chemin de l’entité à utiliser pour identifier votre mesure.</span><span class="sxs-lookup"><span data-stu-id="73094-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="73094-156">S’il n’y a qu’un seul chemin vers l’entité *Client*, ce contrôle ne s’affichera pas.</span><span class="sxs-lookup"><span data-stu-id="73094-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="73094-157">Sélectionnez **Terminé** pour appliquer votre sélection.</span><span class="sxs-lookup"><span data-stu-id="73094-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Sélectionnez le chemin d’accès pour la mesure.":::

1. <span data-ttu-id="73094-159">Pour ajouter d’autres calculs pour la mesure, sélectionnez **Nouveau calcul**.</span><span class="sxs-lookup"><span data-stu-id="73094-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="73094-160">Vous ne pouvez utiliser des entités sur le même chemin d’entité que pour les nouveaux calculs.</span><span class="sxs-lookup"><span data-stu-id="73094-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="73094-161">Des calculs supplémentaires s’affichent sous forme de nouvelles colonnes dans l’entité de sortie de mesure.</span><span class="sxs-lookup"><span data-stu-id="73094-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="73094-162">Sélectionnez **...** sur le calcul pour **Dupliquer**, **Renommer** ou **Supprimer** un calcul à partir d’une mesure.</span><span class="sxs-lookup"><span data-stu-id="73094-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="73094-163">Dans la zone **Aperçu**, vous verrez le schéma de données de l’entité de sortie de mesure, y compris les filtres et les dimensions.</span><span class="sxs-lookup"><span data-stu-id="73094-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="73094-164">L’aperçu réagit de manière dynamique aux modifications de la configuration.</span><span class="sxs-lookup"><span data-stu-id="73094-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="73094-165">Sélectionnez **Exécuter** pour calculer les résultats de la mesure configurée.</span><span class="sxs-lookup"><span data-stu-id="73094-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="73094-166">Sélectionnez **Enregistrer et fermer** si vous souhaitez conserver la configuration actuelle et exécuter la mesure ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="73094-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="73094-167">Aller à **Mesures** pour voir la mesure nouvellement créée dans la liste.</span><span class="sxs-lookup"><span data-stu-id="73094-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="73094-168">Gérer vos mesures</span><span class="sxs-lookup"><span data-stu-id="73094-168">Manage your measures</span></span>

<span data-ttu-id="73094-169">Après avoir [créé une mesure](#create-a-measure), vous verrez une liste de mesures sur la page **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="73094-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="73094-170">Vous trouverez des informations sur le type de mesure, le créateur, la date de création, le statut et l’état.</span><span class="sxs-lookup"><span data-stu-id="73094-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="73094-171">Lorsque vous sélectionnez une mesure dans la liste, vous pouvez prévisualiser la sortie et télécharger un fichier .CSV.</span><span class="sxs-lookup"><span data-stu-id="73094-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="73094-172">Pour actualiser toutes vos mesures en même temps, sélectionnez **Actualiser tout** sans sélectionner une mesure spécifique.</span><span class="sxs-lookup"><span data-stu-id="73094-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="73094-173">![Actions pour gérer des mesures uniques](media/measure-actions.png "Actions pour gérer des mesures uniques")</span><span class="sxs-lookup"><span data-stu-id="73094-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="73094-174">Choisissez une mesure parmi la liste des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="73094-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="73094-175">Sélectionner le nom de la mesure pour afficher ses détails.</span><span class="sxs-lookup"><span data-stu-id="73094-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="73094-176">**Modifier** la configuration de la mesure.</span><span class="sxs-lookup"><span data-stu-id="73094-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="73094-177">**Actualisez** la mesure basée sur les dernières données.</span><span class="sxs-lookup"><span data-stu-id="73094-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="73094-178">**Renommer** la mesure.</span><span class="sxs-lookup"><span data-stu-id="73094-178">**Rename** the measure.</span></span>
- <span data-ttu-id="73094-179">**Supprimer** la mesure.</span><span class="sxs-lookup"><span data-stu-id="73094-179">**Delete** the measure.</span></span>
- <span data-ttu-id="73094-180">**Activer** ou **Désactiver**.</span><span class="sxs-lookup"><span data-stu-id="73094-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="73094-181">Les mesures inactives ne seront pas actualisées pendant une [actualisation programmée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="73094-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="73094-182">Il existe [six types de statuts](system.md#status-types) pour les tâches/processus.</span><span class="sxs-lookup"><span data-stu-id="73094-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="73094-183">En outre, la plupart des processus [dépendent d’autres processus en aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="73094-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="73094-184">Vous pouvez sélectionner le statut d’un processus pour afficher des détails sur la progression de toute la tâche.</span><span class="sxs-lookup"><span data-stu-id="73094-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="73094-185">Après avoir sélectionné **Voir les détails** pour l’une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.</span><span class="sxs-lookup"><span data-stu-id="73094-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="73094-186">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="73094-186">Next step</span></span>

<span data-ttu-id="73094-187">Vous pouvez utiliser des mesures existantes pour créer [un segment de clientèle](segments.md).</span><span class="sxs-lookup"><span data-stu-id="73094-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]