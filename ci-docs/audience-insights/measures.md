---
title: Créer et gérer des mesures
description: Définir des mesures pour analyser et refléter la performance de votre entreprise.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049247"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="3d24d-103">Définir et gérer des mesures</span><span class="sxs-lookup"><span data-stu-id="3d24d-103">Define and manage measures</span></span>

<span data-ttu-id="3d24d-104">Les mesures vous aident à mieux comprendre les comportements des clients et les performances commerciales.</span><span class="sxs-lookup"><span data-stu-id="3d24d-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="3d24d-105">Elles examinent les valeurs pertinentes des [profils unifiés](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="3d24d-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="3d24d-106">Par exemple, une entreprise souhaite voir les *dépenses totales par client* pour comprendre l’historique des achats d’un client individuel ou mesurer les *ventes totales de la société* pour comprendre le revenu au niveau agrégé dans l’ensemble de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="3d24d-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="3d24d-107">Les mesures sont créées à l’aide du générateur de mesures, une plateforme de requête de données avec divers opérateurs et des options de mappage simples.</span><span class="sxs-lookup"><span data-stu-id="3d24d-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="3d24d-108">Elle vous permet de filtrer les données, de regrouper les résultats, de détecter les [chemins d’accès aux relations d’entités](relationships.md) et prévisualisez la sortie.</span><span class="sxs-lookup"><span data-stu-id="3d24d-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="3d24d-109">Utilisez le générateur de mesures pour planifier les activités commerciales en interrogeant les données client et en extrayant des informations.</span><span class="sxs-lookup"><span data-stu-id="3d24d-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="3d24d-110">Par exemple, créer une mesure de *total des dépenses par client* et de *total des retours par client* aide à identifier un groupe de clients avec des dépenses élevées mais un rendement élevé.</span><span class="sxs-lookup"><span data-stu-id="3d24d-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="3d24d-111">Vous pouvez [créer un segment](segments.md) pour conduire les meilleures actions suivantes.</span><span class="sxs-lookup"><span data-stu-id="3d24d-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="3d24d-112">Créer votre propre mesure à partir de zéro</span><span class="sxs-lookup"><span data-stu-id="3d24d-112">Build your own measure from scratch</span></span>

<span data-ttu-id="3d24d-113">Cette section vous guide tout au long de la création d’une mesure à partir de zéro.</span><span class="sxs-lookup"><span data-stu-id="3d24d-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="3d24d-114">Vous pouvez créer une mesure avec des attributs de données à partir d’entités de données ayant une relation configurée pour se connecter à l’entité Client.</span><span class="sxs-lookup"><span data-stu-id="3d24d-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="3d24d-115">Dans Audience Insights, accédez à **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="3d24d-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="3d24d-116">Sélectionnez **Nouveau** et choisissez **Créer le vôtre**.</span><span class="sxs-lookup"><span data-stu-id="3d24d-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="3d24d-117">Sélectionnez **Modifier le nom** et fournissez un **Nom** pour la mesure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="3d24d-118">Si votre nouvelle configuration de mesure ne comporte que deux champs, par exemple, CustomerID et un calcul, la sortie sera ajoutée en tant que nouvelle colonne à l’entité générée par le système appelée Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-118">If your new measure configuration has only two fields, for example, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="3d24d-119">Et vous pourrez voir la valeur de la mesure dans le profil client unifié.</span><span class="sxs-lookup"><span data-stu-id="3d24d-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="3d24d-120">D’autres mesures généreront leurs propres entités.</span><span class="sxs-lookup"><span data-stu-id="3d24d-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="3d24d-121">Dans la zone de configuration, choisissez la fonction d’agrégation dans le menu déroulant **Sélectionnez la fonction**.</span><span class="sxs-lookup"><span data-stu-id="3d24d-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="3d24d-122">Les fonctions d’agrégation comprennent :</span><span class="sxs-lookup"><span data-stu-id="3d24d-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="3d24d-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="3d24d-123">**Sum**</span></span>
   - <span data-ttu-id="3d24d-124">**Moyenne**</span><span class="sxs-lookup"><span data-stu-id="3d24d-124">**Average**</span></span>
   - <span data-ttu-id="3d24d-125">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="3d24d-125">**Count**</span></span>
   - <span data-ttu-id="3d24d-126">**Nombre Unique**</span><span class="sxs-lookup"><span data-stu-id="3d24d-126">**Count Unique**</span></span>
   - <span data-ttu-id="3d24d-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="3d24d-127">**Max**</span></span>
   - <span data-ttu-id="3d24d-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="3d24d-128">**Min**</span></span>
   - <span data-ttu-id="3d24d-129">**Première** : prend la première valeur de l’enregistrement de données</span><span class="sxs-lookup"><span data-stu-id="3d24d-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="3d24d-130">**Dernière** : prend la dernière valeur ajoutée à l’enregistrement de données</span><span class="sxs-lookup"><span data-stu-id="3d24d-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Opérateurs pour les calculs de mesures.":::

1. <span data-ttu-id="3d24d-132">Sélectionnez **Ajouter un attribut** pour sélectionner les données dont vous avez besoin pour créer cette mesure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="3d24d-133">Sélectionnez l’onglet **Attributs**.</span><span class="sxs-lookup"><span data-stu-id="3d24d-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="3d24d-134">Entité Data : Choisissez l’entité qui comprend l’attribut selon lequel vous souhaitez mesurer.</span><span class="sxs-lookup"><span data-stu-id="3d24d-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="3d24d-135">Attribut de données : choisissez l’attribut que vous souhaitez utiliser dans la fonction d’agrégation pour calculer la mesure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="3d24d-136">Vous ne pouvez sélectionner qu’un attribut à la fois.</span><span class="sxs-lookup"><span data-stu-id="3d24d-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="3d24d-137">Vous pouvez également sélectionner un attribut de données à partir d’une mesure existante en sélectionnant l’onglet **Mesures**. Sinon, vous pouvez rechercher un nom d’entité ou de mesure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="3d24d-138">Sélectionnez **Ajouter** pour ajouter l’attribut sélectionné à la mesure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Sélectionnez un attribut à utiliser dans les calculs.":::

1. <span data-ttu-id="3d24d-140">Pour créer des mesures plus complexes, vous pouvez ajouter plus d’attributs ou utiliser des opérateurs mathématiques sur votre fonction de mesure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Créez une mesure complexe avec des opérateurs mathématiques.":::

1. <span data-ttu-id="3d24d-142">Pour ajouter des filtres, sélectionnez le **Filtre** dans la zone de configuration.</span><span class="sxs-lookup"><span data-stu-id="3d24d-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="3d24d-143">Dans la section **Ajouter un attribut** du volet **Filtres**, sélectionnez l’attribut que vous souhaitez utiliser pour créer des filtres.</span><span class="sxs-lookup"><span data-stu-id="3d24d-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="3d24d-144">Définissez les opérateurs de filtre pour définir le filtre pour chaque attribut sélectionné.</span><span class="sxs-lookup"><span data-stu-id="3d24d-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="3d24d-145">Sélectionnez **Appliquer** pour ajouter les filtres à la mesure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="3d24d-146">Pour ajouter des dimensions, sélectionnez **Dimension** dans la zone de configuration.</span><span class="sxs-lookup"><span data-stu-id="3d24d-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="3d24d-147">Les dimensions s’affichent sous forme de colonnes dans l’entité de sortie de mesure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="3d24d-148">Sélectionnez **Modifier les dimensions** pour ajouter des attributs de données par lesquels vous souhaitez regrouper les valeurs de mesure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="3d24d-149">Par exemple, ville ou sexe.</span><span class="sxs-lookup"><span data-stu-id="3d24d-149">For example, city or gender.</span></span> <span data-ttu-id="3d24d-150">Par défaut, la dimension *CustomerID* est sélectionnée pour créer des *mesures au niveau du client*.</span><span class="sxs-lookup"><span data-stu-id="3d24d-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="3d24d-151">Vous pouvez supprimer la dimension par défaut si vous souhaitez créer des *mesures au niveau de l’entreprise*.</span><span class="sxs-lookup"><span data-stu-id="3d24d-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="3d24d-152">Sélectionnez **Terminé** pour ajouter les dimensions à la mesure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="3d24d-153">Si des valeurs de vos données doivent être remplacées par un entier, par exemple, remplacer *null* par *0*, sélectionnez **Règles**.</span><span class="sxs-lookup"><span data-stu-id="3d24d-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="3d24d-154">Configurez la règle et assurez-vous de ne choisir que des nombres entiers comme valeurs de remplacement.</span><span class="sxs-lookup"><span data-stu-id="3d24d-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="3d24d-155">S’il existe plusieurs chemins d’accès entre l’entité de données que vous avez mappée et l’entité *Client*, vous devez choisir l’un des [chemins d’accès de relation d’entité](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="3d24d-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="3d24d-156">Les résultats de la mesure peuvent varier en fonction du chemin sélectionné.</span><span class="sxs-lookup"><span data-stu-id="3d24d-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="3d24d-157">Sélectionnez **Préférences de données** et choisissez le chemin de l’entité à utiliser pour identifier votre mesure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="3d24d-158">S’il n’y a qu’un seul chemin vers l’entité *Client*, ce contrôle ne s’affichera pas.</span><span class="sxs-lookup"><span data-stu-id="3d24d-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="3d24d-159">Sélectionnez **Terminé** pour appliquer votre sélection.</span><span class="sxs-lookup"><span data-stu-id="3d24d-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Sélectionnez le chemin d’accès pour la mesure.":::

1. <span data-ttu-id="3d24d-161">Pour ajouter d’autres calculs pour la mesure, sélectionnez **Nouveau calcul**.</span><span class="sxs-lookup"><span data-stu-id="3d24d-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="3d24d-162">Vous ne pouvez utiliser des entités sur le même chemin d’entité que pour les nouveaux calculs.</span><span class="sxs-lookup"><span data-stu-id="3d24d-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="3d24d-163">Des calculs supplémentaires s’affichent sous forme de nouvelles colonnes dans l’entité de sortie de mesure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="3d24d-164">Sélectionnez **...** sur le calcul pour **Dupliquer**, **Renommer** ou **Supprimer** un calcul à partir d’une mesure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="3d24d-165">Dans la zone **Aperçu**, vous verrez le schéma de données de l’entité de sortie de mesure, y compris les filtres et les dimensions.</span><span class="sxs-lookup"><span data-stu-id="3d24d-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="3d24d-166">L’aperçu réagit de manière dynamique aux modifications de la configuration.</span><span class="sxs-lookup"><span data-stu-id="3d24d-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="3d24d-167">Sélectionnez **Exécuter** pour calculer les résultats de la mesure configurée.</span><span class="sxs-lookup"><span data-stu-id="3d24d-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="3d24d-168">Sélectionnez **Enregistrer et fermer** si vous souhaitez conserver la configuration actuelle et exécuter la mesure ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="3d24d-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="3d24d-169">Aller à **Mesures** pour voir la mesure nouvellement créée dans la liste.</span><span class="sxs-lookup"><span data-stu-id="3d24d-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="3d24d-170">Utiliser un modèle pour créer une mesure</span><span class="sxs-lookup"><span data-stu-id="3d24d-170">Use a template to build a measure</span></span>

<span data-ttu-id="3d24d-171">Vous pouvez utiliser des modèles prédéfinis de mesures couramment utilisées pour les créer.</span><span class="sxs-lookup"><span data-stu-id="3d24d-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="3d24d-172">Les descriptions détaillées des modèles et une expérience guidée vous aident à créer des mesures de manière efficace.</span><span class="sxs-lookup"><span data-stu-id="3d24d-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="3d24d-173">Les modèles reposent sur les données mappées de l’entité *Activité unifiée*.</span><span class="sxs-lookup"><span data-stu-id="3d24d-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="3d24d-174">Assurez-vous donc d’avoir configuré les [activités client](activities.md) avant de créer une mesure à partir d’un modèle.</span><span class="sxs-lookup"><span data-stu-id="3d24d-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="3d24d-175">Modèles de mesure disponibles :</span><span class="sxs-lookup"><span data-stu-id="3d24d-175">Available measure templates:</span></span> 
- <span data-ttu-id="3d24d-176">Valeur moyenne de la transaction (ATV)</span><span class="sxs-lookup"><span data-stu-id="3d24d-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="3d24d-177">Valeur totale des transactions</span><span class="sxs-lookup"><span data-stu-id="3d24d-177">Total transaction value</span></span>
- <span data-ttu-id="3d24d-178">Revenu quotidien moyen</span><span class="sxs-lookup"><span data-stu-id="3d24d-178">Average daily revenue</span></span>
- <span data-ttu-id="3d24d-179">Revenu annuel moyen</span><span class="sxs-lookup"><span data-stu-id="3d24d-179">Average yearly revenue</span></span>
- <span data-ttu-id="3d24d-180">Nombre de transactions</span><span class="sxs-lookup"><span data-stu-id="3d24d-180">Transaction count</span></span>
- <span data-ttu-id="3d24d-181">Points de fidélité gagnés</span><span class="sxs-lookup"><span data-stu-id="3d24d-181">Loyalty points earned</span></span>
- <span data-ttu-id="3d24d-182">Points de fidélité utilisés</span><span class="sxs-lookup"><span data-stu-id="3d24d-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="3d24d-183">Solde des points de fidélité</span><span class="sxs-lookup"><span data-stu-id="3d24d-183">Loyalty points balance</span></span>
- <span data-ttu-id="3d24d-184">Durée de vie active du client</span><span class="sxs-lookup"><span data-stu-id="3d24d-184">Active customer lifespan</span></span>
- <span data-ttu-id="3d24d-185">Durée d’adhésion au programme de fidélité</span><span class="sxs-lookup"><span data-stu-id="3d24d-185">Loyalty membership duration</span></span>
- <span data-ttu-id="3d24d-186">Durée écoulée depuis le dernier achat</span><span class="sxs-lookup"><span data-stu-id="3d24d-186">Time since last purchase</span></span>

<span data-ttu-id="3d24d-187">La procédure suivante décrit les étapes pour créer une nouvelle mesure à l’aide d’un modèle.</span><span class="sxs-lookup"><span data-stu-id="3d24d-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="3d24d-188">Dans Audience Insights, accédez à **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="3d24d-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="3d24d-189">Sélectionnez **Nouveau** et sélectionnez **Choisir un modèle**.</span><span class="sxs-lookup"><span data-stu-id="3d24d-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Capture d’écran du menu déroulant lors de la création d’une nouvelle mesure avec le modèle mis en surbrillance.":::

1. <span data-ttu-id="3d24d-191">Recherchez le modèle correspondant à vos besoins et sélectionnez **Choisir le modèle**.</span><span class="sxs-lookup"><span data-stu-id="3d24d-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="3d24d-192">Vérifiez les données requises et sélectionnez **Démarrer** si toutes les données sont en place.</span><span class="sxs-lookup"><span data-stu-id="3d24d-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="3d24d-193">Dans le volet **Modifier le nom**, définissez le nom de votre mesure et l’entité de sortie.</span><span class="sxs-lookup"><span data-stu-id="3d24d-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="3d24d-194">Cliquez sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="3d24d-194">Select **Done**.</span></span>

1. <span data-ttu-id="3d24d-195">Dans la section **Définir la période de temps**, définissez la période de temps des données à utiliser.</span><span class="sxs-lookup"><span data-stu-id="3d24d-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="3d24d-196">Choisissez si vous souhaitez que la nouvelle mesure couvre l’ensemble du jeu de données en sélectionnant **Tout le temps**.</span><span class="sxs-lookup"><span data-stu-id="3d24d-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="3d24d-197">Ou si vous souhaitez que la mesure se concentre sur une **Période de temps spécifique**.</span><span class="sxs-lookup"><span data-stu-id="3d24d-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Capture d’écran montrant la section de la période de temps lors de la configuration d’une mesure à partir d’un modèle.":::

1. <span data-ttu-id="3d24d-199">Dans la section suivante, sélectionnez **Ajouter des données** pour choisir les activités et mapper les données correspondantes de votre entité *Activité unifiée*.</span><span class="sxs-lookup"><span data-stu-id="3d24d-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="3d24d-200">Étape 1 sur 2 : dans **Type d’activité**, choisissez le type d’entité que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="3d24d-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="3d24d-201">Pour **Activités**, sélectionnez les entités que vous souhaitez mapper.</span><span class="sxs-lookup"><span data-stu-id="3d24d-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="3d24d-202">Étape 2 sur 2 : choisissez l’attribut de l’entité *Activité unifiée* pour le composant requis par la formule.</span><span class="sxs-lookup"><span data-stu-id="3d24d-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="3d24d-203">Par exemple, pour la valeur de transaction moyenne, il s’agit de l’attribut représentant la valeur de la transaction.</span><span class="sxs-lookup"><span data-stu-id="3d24d-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="3d24d-204">Pour **Horodateur de l’activité**, choisissez l’attribut de l’entité Activité unifiée qui représente la date et l’heure de l’activité.</span><span class="sxs-lookup"><span data-stu-id="3d24d-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="3d24d-205">Une fois le mappage des données terminé, vous pouvez voir le statut défini sur **Terminer** et le nom des activités et des attributs mappés.</span><span class="sxs-lookup"><span data-stu-id="3d24d-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Capture d’écran d’une configuration de modèle de mesure terminée.":::

1. <span data-ttu-id="3d24d-207">Vous pouvez maintenant sélectionner **Exécuter** pour calculer les résultats de la mesure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="3d24d-208">Pour l’affiner ultérieurement, sélectionnez **Enregistrer le brouillon**.</span><span class="sxs-lookup"><span data-stu-id="3d24d-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="3d24d-209">Gérer vos mesures</span><span class="sxs-lookup"><span data-stu-id="3d24d-209">Manage your measures</span></span>

<span data-ttu-id="3d24d-210">Vous trouverez la liste des mesures sur la page **Mesures**.</span><span class="sxs-lookup"><span data-stu-id="3d24d-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="3d24d-211">Vous trouverez des informations sur le type de mesure, le créateur, la date de création, le statut et l’état.</span><span class="sxs-lookup"><span data-stu-id="3d24d-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="3d24d-212">Lorsque vous sélectionnez une mesure dans la liste, vous pouvez prévisualiser la sortie et télécharger un fichier .CSV.</span><span class="sxs-lookup"><span data-stu-id="3d24d-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="3d24d-213">Pour actualiser toutes vos mesures en même temps, sélectionnez **Actualiser tout** sans sélectionner une mesure spécifique.</span><span class="sxs-lookup"><span data-stu-id="3d24d-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3d24d-214">![Actions pour gérer des mesures uniques](media/measure-actions.png "Actions pour gérer des mesures uniques")</span><span class="sxs-lookup"><span data-stu-id="3d24d-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="3d24d-215">Choisissez une mesure parmi la liste des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="3d24d-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="3d24d-216">Sélectionner le nom de la mesure pour afficher ses détails.</span><span class="sxs-lookup"><span data-stu-id="3d24d-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="3d24d-217">**Modifier** la configuration de la mesure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="3d24d-218">**Actualisez** la mesure basée sur les dernières données.</span><span class="sxs-lookup"><span data-stu-id="3d24d-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="3d24d-219">**Renommer** la mesure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-219">**Rename** the measure.</span></span>
- <span data-ttu-id="3d24d-220">**Supprimer** la mesure.</span><span class="sxs-lookup"><span data-stu-id="3d24d-220">**Delete** the measure.</span></span>
- <span data-ttu-id="3d24d-221">**Activer** ou **Désactiver**.</span><span class="sxs-lookup"><span data-stu-id="3d24d-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="3d24d-222">Les mesures inactives ne seront pas actualisées pendant une [actualisation programmée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3d24d-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="3d24d-223">Il existe [six types de statuts](system.md#status-types) pour les tâches/processus.</span><span class="sxs-lookup"><span data-stu-id="3d24d-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3d24d-224">En outre, la plupart des processus [dépendent d’autres processus en aval](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="3d24d-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3d24d-225">Vous pouvez sélectionner le statut d’un processus pour afficher des détails sur la progression de toute la tâche.</span><span class="sxs-lookup"><span data-stu-id="3d24d-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3d24d-226">Après avoir sélectionné **Voir les détails** pour l’une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.</span><span class="sxs-lookup"><span data-stu-id="3d24d-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="3d24d-227">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="3d24d-227">Next step</span></span>

<span data-ttu-id="3d24d-228">Vous pouvez utiliser des mesures existantes pour créer [un segment de clientèle](segments.md).</span><span class="sxs-lookup"><span data-stu-id="3d24d-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
