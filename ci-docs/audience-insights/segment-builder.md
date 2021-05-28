---
title: Créer et gérer des segments
description: Créez des segments de clients pour les regrouper en fonction de divers attributs.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064934"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="b2a86-103">Créer et gérer des segments</span><span class="sxs-lookup"><span data-stu-id="b2a86-103">Create and manage segments</span></span>

<span data-ttu-id="b2a86-104">Définissez des filtres complexes autour de l’entité de client unifié et ses entités liées.</span><span class="sxs-lookup"><span data-stu-id="b2a86-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="b2a86-105">Chaque segment, après le traitement, crée un ensemble d’enregistrement d’entité client que vous pouvez exporter et utiliser pour entreprendre des actions.</span><span class="sxs-lookup"><span data-stu-id="b2a86-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="b2a86-106">Les segments sont gérés sur la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="b2a86-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="b2a86-107">L’exemple suivant illustre la fonctionnalité de segmentation.</span><span class="sxs-lookup"><span data-stu-id="b2a86-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="b2a86-108">Nous avons défini un segment pour les clients qui ont commandé au moins 500 USD de marchandises au cours des 90 derniers jours *et* qui ont été appelés par le service clientèle.</span><span class="sxs-lookup"><span data-stu-id="b2a86-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Capture d’écran de l’interface utilisateur du générateur de segments avec deux groupes qui spécifient un segment de clientèle.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="b2a86-110">Créer un segment</span><span class="sxs-lookup"><span data-stu-id="b2a86-110">Create a new segment</span></span>

<span data-ttu-id="b2a86-111">Il existe plusieurs façons de créer un segment.</span><span class="sxs-lookup"><span data-stu-id="b2a86-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="b2a86-112">Cette section décrit comment créer un *segment vide* à partir de zéro.</span><span class="sxs-lookup"><span data-stu-id="b2a86-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="b2a86-113">Vous pouvez également créer un *segment rapide* basé sur des entités existantes ou utiliser des modèles Machine Learning pour obtenir des *segments suggérés*.</span><span class="sxs-lookup"><span data-stu-id="b2a86-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="b2a86-114">Pour en savoir plus, consultez [Présentation des segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="b2a86-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="b2a86-115">Lors de la création d’un segment, vous pouvez enregistrer un brouillon.</span><span class="sxs-lookup"><span data-stu-id="b2a86-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="b2a86-116">Il sera enregistré en tant que segment inactif et ne peut pas être activé s’il est terminé avec une configuration valide.</span><span class="sxs-lookup"><span data-stu-id="b2a86-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="b2a86-117">Accédez à la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="b2a86-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="b2a86-118">Sélectionnez **Nouveau** > **Segment vide**.</span><span class="sxs-lookup"><span data-stu-id="b2a86-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="b2a86-119">Dans le volet **Nouveau segment**, choisissez un type de segment :</span><span class="sxs-lookup"><span data-stu-id="b2a86-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="b2a86-120">Les **Segments dynamiques** [sont actualisés](segments.md#refresh-segments) selon un calendrier récurrent.</span><span class="sxs-lookup"><span data-stu-id="b2a86-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="b2a86-121">Les **Segments statiques** sont exécutés une fois lorsque vous les créez.</span><span class="sxs-lookup"><span data-stu-id="b2a86-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="b2a86-122">Indiquez un **Nom de l’entité de sortie** pour le segment.</span><span class="sxs-lookup"><span data-stu-id="b2a86-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="b2a86-123">Vous pouvez aussi fournir un nom complet et une description qui aide à identifier le segment.</span><span class="sxs-lookup"><span data-stu-id="b2a86-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="b2a86-124">Sélectionnez **Suivant** pour arriver sur la page **Générateur de segments** où vous devez définir un groupe.</span><span class="sxs-lookup"><span data-stu-id="b2a86-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="b2a86-125">Un groupe est un ensemble de clients.</span><span class="sxs-lookup"><span data-stu-id="b2a86-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="b2a86-126">Choisissez l’entité qui comprend l’attribut selon lequel vous souhaitez segmenter.</span><span class="sxs-lookup"><span data-stu-id="b2a86-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="b2a86-127">Choisissez l’attribut de segmentation.</span><span class="sxs-lookup"><span data-stu-id="b2a86-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="b2a86-128">Cet attribut peut avoir un des quatre types de valeur : numérique, chaîne, date ou booléen.</span><span class="sxs-lookup"><span data-stu-id="b2a86-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="b2a86-129">Choisissez un opérateur et une valeur pour l’attribut sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b2a86-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b2a86-130">![Filtre de groupe personnalisé](media/customer-group-numbers.png "Filtre du groupe de clients")</span><span class="sxs-lookup"><span data-stu-id="b2a86-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="b2a86-131">Nombre</span><span class="sxs-lookup"><span data-stu-id="b2a86-131">Number</span></span> |<span data-ttu-id="b2a86-132">Définition</span><span class="sxs-lookup"><span data-stu-id="b2a86-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="b2a86-133">1</span><span class="sxs-lookup"><span data-stu-id="b2a86-133">1</span></span>     |<span data-ttu-id="b2a86-134">Entity</span><span class="sxs-lookup"><span data-stu-id="b2a86-134">Entity</span></span>          |
   |<span data-ttu-id="b2a86-135">2</span><span class="sxs-lookup"><span data-stu-id="b2a86-135">2</span></span>     |<span data-ttu-id="b2a86-136">Attribut</span><span class="sxs-lookup"><span data-stu-id="b2a86-136">Attribute</span></span>          |
   |<span data-ttu-id="b2a86-137">3</span><span class="sxs-lookup"><span data-stu-id="b2a86-137">3</span></span>    |<span data-ttu-id="b2a86-138">Opérateur</span><span class="sxs-lookup"><span data-stu-id="b2a86-138">Operator</span></span>         |
   |<span data-ttu-id="b2a86-139">4</span><span class="sxs-lookup"><span data-stu-id="b2a86-139">4</span></span>    |<span data-ttu-id="b2a86-140">valeur</span><span class="sxs-lookup"><span data-stu-id="b2a86-140">Value</span></span>         |

   1. <span data-ttu-id="b2a86-141">Pour ajouter plus de conditions à un groupe, vous pouvez utiliser deux opérateurs logiques :</span><span class="sxs-lookup"><span data-stu-id="b2a86-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="b2a86-142">Opérateur **ET** : Les deux conditions doivent être remplies dans le cadre du processus de segmentation.</span><span class="sxs-lookup"><span data-stu-id="b2a86-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="b2a86-143">Cette option est particulièrement utile lorsque vous définissez des conditions sur différentes entités.</span><span class="sxs-lookup"><span data-stu-id="b2a86-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="b2a86-144">Opérateur **OU** : L’une ou l’autre des conditions doit être satisfaite dans le cadre de le processus de segmentation.</span><span class="sxs-lookup"><span data-stu-id="b2a86-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="b2a86-145">Cette option est très utile lorsque vous définissez plusieurs conditions pour la même entité.</span><span class="sxs-lookup"><span data-stu-id="b2a86-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="b2a86-146">![Opérateur OU où l'une ou l'autre des conditions doit être remplie](media/segmentation-either-condition.png "Opérateur OU où l’une ou l’autre des conditions doit être remplie")</span><span class="sxs-lookup"><span data-stu-id="b2a86-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="b2a86-147">Il est actuellement possible d’imbriquer un opérateur **OU** sous un opérateur **ET**, mais pas l’inverse.</span><span class="sxs-lookup"><span data-stu-id="b2a86-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="b2a86-148">Chaque groupe correspond à un ensemble de clients.</span><span class="sxs-lookup"><span data-stu-id="b2a86-148">Each group matches set of customers.</span></span> <span data-ttu-id="b2a86-149">Vous pouvez combiner des groupes pour inclure les clients requis pour votre scénario professionnel.</span><span class="sxs-lookup"><span data-stu-id="b2a86-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="b2a86-150">Sélectionnez **Ajouter un groupe**.</span><span class="sxs-lookup"><span data-stu-id="b2a86-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="b2a86-151">![Groupe de clients - Ajouter un groupe](media/customer-group-add-group.png "Groupe de clients - Ajouter un groupe")</span><span class="sxs-lookup"><span data-stu-id="b2a86-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="b2a86-152">Sélectionnez l’un des opérateurs définis : **Union**, **Intersection** ou **Exception**.</span><span class="sxs-lookup"><span data-stu-id="b2a86-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b2a86-153">![Groupe de clients - Ajouter une union](media/customer-group-union.png "Groupe de clients - Ajouter une union")</span><span class="sxs-lookup"><span data-stu-id="b2a86-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="b2a86-154">**Union** unit les deux groupes.</span><span class="sxs-lookup"><span data-stu-id="b2a86-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="b2a86-155">**Intersection** fait se chevaucher les deux groupes.</span><span class="sxs-lookup"><span data-stu-id="b2a86-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="b2a86-156">Seules les données qui *sont communes* aux deux groupes sont conservées dans le groupe unifié.</span><span class="sxs-lookup"><span data-stu-id="b2a86-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="b2a86-157">**Exception** combine les deux groupes.</span><span class="sxs-lookup"><span data-stu-id="b2a86-157">**Except** combines the two groups.</span></span> <span data-ttu-id="b2a86-158">Seules les données du groupe A qui *ne sont pas communes* aux données du groupe B sont conservées.</span><span class="sxs-lookup"><span data-stu-id="b2a86-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="b2a86-159">Si l’entité est connectée à l’entité client unifiée par le biais de [relations](relationships.md), vous devez définir le chemin d’accès de la relation pour créer un segment valide.</span><span class="sxs-lookup"><span data-stu-id="b2a86-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="b2a86-160">Ajoutez les entités à partir du chemin d’accès de la relation jusqu’à ce que vous puissiez sélectionner l’entité **Client : CustomerInsights** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="b2a86-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="b2a86-161">Choisissez ensuite **Tous les enregistrements** pour chaque étape.</span><span class="sxs-lookup"><span data-stu-id="b2a86-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b2a86-162">![Chemin d’accès de la relation lors de la création d’un segment](media/segments-multiple-relationships.png "Chemin d’accès de la relation lors de la création d’un segment")</span><span class="sxs-lookup"><span data-stu-id="b2a86-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="b2a86-163">Par défaut, les segments génèrent une entité de sortie qui contient tous les attributs des profils client qui correspondent aux filtres définis.</span><span class="sxs-lookup"><span data-stu-id="b2a86-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="b2a86-164">Si un segment est basé sur d’autres entités que l’entité *Client*, vous pouvez ajouter d’autres attributs de ces entités à l’entité de sortie.</span><span class="sxs-lookup"><span data-stu-id="b2a86-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="b2a86-165">Sélectionnez **Attributs du projet** pour choisir les attributs qui seront ajoutés à l’entité de sortie.</span><span class="sxs-lookup"><span data-stu-id="b2a86-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="b2a86-166">Exemple : un segment est basé sur une entité qui contient des données d’activité client liées à l’entité *Client*.</span><span class="sxs-lookup"><span data-stu-id="b2a86-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="b2a86-167">Le segment recherche tous les clients qui ont appelé le service d’assistance au cours des 60 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="b2a86-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="b2a86-168">Vous pouvez choisir d’ajouter la durée de l’appel et le nombre d’appels à tous les enregistrements client correspondants dans l’entité de sortie.</span><span class="sxs-lookup"><span data-stu-id="b2a86-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="b2a86-169">Ces informations peuvent être utiles pour envoyer un e-mail contenant des liens utiles vers des articles d’aide en ligne et des questions fréquentes (FAQ) aux clients qui ont appelé fréquemment.</span><span class="sxs-lookup"><span data-stu-id="b2a86-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="b2a86-170">Les attributs projetés ne fonctionnent que pour les entités qui ont une relation un-à-plusieurs avec l’entité client.</span><span class="sxs-lookup"><span data-stu-id="b2a86-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="b2a86-171">Par exemple, un client peut avoir plusieurs abonnements.</span><span class="sxs-lookup"><span data-stu-id="b2a86-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="b2a86-172">Vous ne pouvez projeter que les attributs d’une entité utilisée dans chaque groupe de requête de segment que vous créez.</span><span class="sxs-lookup"><span data-stu-id="b2a86-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="b2a86-173">Les attributs projetés sont pris en compte lors de l’utilisation d’opérateurs définis.</span><span class="sxs-lookup"><span data-stu-id="b2a86-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="b2a86-174">Sélectionnez **Enregistrer** pour enregistrer votre segment.</span><span class="sxs-lookup"><span data-stu-id="b2a86-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="b2a86-175">Votre segment sera enregistré et traité si toutes les exigences sont validées.</span><span class="sxs-lookup"><span data-stu-id="b2a86-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="b2a86-176">Sinon, il sera enregistré en tant que brouillon.</span><span class="sxs-lookup"><span data-stu-id="b2a86-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="b2a86-177">Sélectionnez **Revenir aux segments** pour revenir à la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="b2a86-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="b2a86-178">Segments rapides</span><span class="sxs-lookup"><span data-stu-id="b2a86-178">Quick segments</span></span>

<span data-ttu-id="b2a86-179">Les segments rapides vous permettent de créer rapidement des segments simples avec un seul opérateur pour des informations plus rapides.</span><span class="sxs-lookup"><span data-stu-id="b2a86-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="b2a86-180">Sur la page **Segments**, sélectionnez **Nouveau** > **Créer à partir de**.</span><span class="sxs-lookup"><span data-stu-id="b2a86-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="b2a86-181">Sélectionnez l’option **Profils** pour créer un segment basé sur l’entité *client unifié*.</span><span class="sxs-lookup"><span data-stu-id="b2a86-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="b2a86-182">Sélectionnez l’option **Mesures** pour créer un segment autour des mesures que vous avez précédemment créées.</span><span class="sxs-lookup"><span data-stu-id="b2a86-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="b2a86-183">Sélectionnez l’option **Intelligence** pour créer un segment autour de l’une des entités de sortie que vous avez générées à l’aide des fonctionnalités **Prédictions** ou **Modèles personnalisés**.</span><span class="sxs-lookup"><span data-stu-id="b2a86-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="b2a86-184">Dans la boîte de dialogue **Nouveau segment rapide**, sélectionnez un attribut dans la liste déroulante **Champ**.</span><span class="sxs-lookup"><span data-stu-id="b2a86-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="b2a86-185">Le système fournit des informations supplémentaires qui vous permettent de créer de meilleurs segments de vos clients.</span><span class="sxs-lookup"><span data-stu-id="b2a86-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="b2a86-186">Pour les champs de catégorie, nous affichons les 10 meilleurs clients.</span><span class="sxs-lookup"><span data-stu-id="b2a86-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="b2a86-187">Choisissez une **Valeur** et sélectionnez **Réviser**.</span><span class="sxs-lookup"><span data-stu-id="b2a86-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="b2a86-188">Pour un attribut numérique, le système affiche la valeur d’attribut correspondant au centile de chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b2a86-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="b2a86-189">Choisissez un **Opérateur** et une **Valeur**, puis sélectionnez **Réviser**.</span><span class="sxs-lookup"><span data-stu-id="b2a86-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="b2a86-190">Le système vous fournira une **taille estimée du segment**.</span><span class="sxs-lookup"><span data-stu-id="b2a86-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="b2a86-191">Vous pouvez choisir de générer le segment que vous avez défini ou de le revoir pour obtenir une taille de segment différente.</span><span class="sxs-lookup"><span data-stu-id="b2a86-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b2a86-192">![Nom et estimation pour un segment rapide](media/quick-segment-name.png "Nom et estimation pour un segment rapide")</span><span class="sxs-lookup"><span data-stu-id="b2a86-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="b2a86-193">Fournissez un **Nom** pour votre segment.</span><span class="sxs-lookup"><span data-stu-id="b2a86-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="b2a86-194">Indiquez éventuellement un **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="b2a86-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="b2a86-195">Sélectionnez **Enregistrer** pour créer votre segment.</span><span class="sxs-lookup"><span data-stu-id="b2a86-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="b2a86-196">Une fois le segment terminé, vous pouvez l’afficher comme tout autre segment que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="b2a86-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b2a86-197">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="b2a86-197">Next steps</span></span>

<span data-ttu-id="b2a86-198">[Exportez un segment](export-destinations.md) et explorer la [carte client](customer-card-add-in.md) et les [connecteurs](export-power-bi.md) pour obtenir des informations sur le niveau du client.</span><span class="sxs-lookup"><span data-stu-id="b2a86-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
