---
title: Mapper des entités pour l'unification des données
description: Mappez des données pour créer des profils clients unifiés.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: e98c7717f7707d43a9fd1fc6f6b0e9c49e4e7ee0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405673"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="7e315-103">Mapper les entités et attributs</span><span class="sxs-lookup"><span data-stu-id="7e315-103">Map entities and attributes</span></span>

<span data-ttu-id="7e315-104">Le **Mappage** est la première étape du processus d'unification des données de Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="7e315-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="7e315-105">Le mappage comprend trois phases :</span><span class="sxs-lookup"><span data-stu-id="7e315-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="7e315-106">*Sélection d’entité* : Identifier les entités pouvant être combinées et qui peuvent conduire à un jeu de données contenant des informations plus complètes sur vos clients.</span><span class="sxs-lookup"><span data-stu-id="7e315-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="7e315-107">*Sélection d’attribut* : Pour chaque entité, identifiez les colonnes à combiner et les réconcilier lors des étapes d’unification suivantes, à savoir la *mise en correspondance* et la *fusion*.</span><span class="sxs-lookup"><span data-stu-id="7e315-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="7e315-108">Ces colonnes sont appelées *Attributs*.</span><span class="sxs-lookup"><span data-stu-id="7e315-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="7e315-109">*Sélection de la clé primaire et du type de sémantique* : Pour chaque entité, identifiez un attribut que vous souhaitez définir comme clé primaire pour cette entité, et pour chaque attribut, identifiez un type de sémantique qui décrit le mieux cet attribut.</span><span class="sxs-lookup"><span data-stu-id="7e315-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="7e315-110">Pour plus d’informations sur le flux général d’unification des données, consultez [Unifier ](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="7e315-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="7e315-111">Sélectionner les premières entités</span><span class="sxs-lookup"><span data-stu-id="7e315-111">Select the first entities</span></span>

1. <span data-ttu-id="7e315-112">Dans Audience Insights, accédez à **Données** > **Unifier** > **Mapper**.</span><span class="sxs-lookup"><span data-stu-id="7e315-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="7e315-113">Lancer la phase de mappage en sélectionnant **Sélectionner des entités**.</span><span class="sxs-lookup"><span data-stu-id="7e315-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="7e315-114">Sélectionnez les entités et attributs que vous souhaitez utiliser dans les phases *mettre en correspondance* et *fusionner*.</span><span class="sxs-lookup"><span data-stu-id="7e315-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="7e315-115">Vous pouvez sélectionner les attributs requis individuellement à partir d’une entité ou inclure tous les attributs d’une entité en cochant la case **Inclure tous les champs** au niveau de l’entité.</span><span class="sxs-lookup"><span data-stu-id="7e315-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="7e315-116">Nous vous recommandons de sélectionner au moins deux entités pour bénéficier du processus d’unification des données.</span><span class="sxs-lookup"><span data-stu-id="7e315-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7e315-117">![Ajouter des entités - Exemple](media/data-manager-configure-map-add-entities-example.png "Ajouter des entités - Exemple")</span><span class="sxs-lookup"><span data-stu-id="7e315-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="7e315-118">Dans cet exemple, nous ajoutons les entités **eCommerceContacts** et **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="7e315-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="7e315-119">En choisissant ces entités, vous pouvez obtenir des informations sur les clients professionnels en ligne qui sont membres du programme de fidélité.</span><span class="sxs-lookup"><span data-stu-id="7e315-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="7e315-120">Vous pouvez rechercher des mots-clés dans tous les attributs et entités pour sélectionner les attributs requis que vous souhaitez mapper.</span><span class="sxs-lookup"><span data-stu-id="7e315-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7e315-121">![Exemple de champs de recherche](media/data-manager-configure-map-search-fields-example.png "Exemple de champs de recherche")</span><span class="sxs-lookup"><span data-stu-id="7e315-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="7e315-122">Sélectionnez **Appliquer** pour confirmer vos sélections.</span><span class="sxs-lookup"><span data-stu-id="7e315-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="7e315-123">Sélectionnez la clé primaire et le type de sémantique pour les attributs</span><span class="sxs-lookup"><span data-stu-id="7e315-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="7e315-124">Après avoir sélectionné vos entités, la page **Mapper** répertorie les entités sélectionnées pour votre examen.</span><span class="sxs-lookup"><span data-stu-id="7e315-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="7e315-125">Définissez la clé primaire d’une entité et identifiez le type de sémantique d’un attribut dans l’entité.</span><span class="sxs-lookup"><span data-stu-id="7e315-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="7e315-126">**Clé primaire** : Sélectionnez un attribut comme clé primaire pour chacune de vos entités.</span><span class="sxs-lookup"><span data-stu-id="7e315-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="7e315-127">Pour qu’un attribut soit une clé primaire valide, il ne doit inclure aucune valeur en double, aucune valeur manquante, ni aucune valeur nulle.</span><span class="sxs-lookup"><span data-stu-id="7e315-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="7e315-128">Les attributs de type de données Chaîne, Entier et GUID sont pris en charge en tant que clés primaires et seront affichés dans un champ dans lequel vous pourrez effectuer votre sélection.</span><span class="sxs-lookup"><span data-stu-id="7e315-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="7e315-129">**Type de sémantique d’attribut :** Catégories dans lesquelles tombent vos attributs, telles que l’adresse de messagerie ou le nom.</span><span class="sxs-lookup"><span data-stu-id="7e315-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="7e315-130">Pour utiliser des modèles IA pour la prédiction intelligente de la sémantique, gagner du temps et améliorer la précision, définissez **Mappage intelligent** sur **Activé**.</span><span class="sxs-lookup"><span data-stu-id="7e315-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="7e315-131">Le mappage intelligent met en évidence la recommandation sémantique basée sur l'IA dans le champ **Type**.</span><span class="sxs-lookup"><span data-stu-id="7e315-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="7e315-132">Si vous définissez cette option sur **Désactivé**, vous verrez nos recommandations de mappage normales.</span><span class="sxs-lookup"><span data-stu-id="7e315-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="7e315-133">Vous pouvez sélectionner n'importe quel type sémantique dans la liste des options disponibles et remplacer la sélection suggérée.</span><span class="sxs-lookup"><span data-stu-id="7e315-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7e315-134">![Type d'attribut et prédiction sémantique](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Type d'attribut et prédiction sémantique")</span><span class="sxs-lookup"><span data-stu-id="7e315-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="7e315-135">Il est aussi possible d’ajouter un type de sémantique personnalisé.</span><span class="sxs-lookup"><span data-stu-id="7e315-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="7e315-136">Sélectionnez le champ de type pour un attribut, puis tapez le nom de votre type de sémantique.</span><span class="sxs-lookup"><span data-stu-id="7e315-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="7e315-137">De cette manière, vous pouvez également modifier les types d’attributs qui ont été identifiés par le système.</span><span class="sxs-lookup"><span data-stu-id="7e315-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="7e315-138">Tous les attributs pour lesquels un type de sémantique est automatiquement identifié sont regroupés dans la section **Examiner les champs mappés**.</span><span class="sxs-lookup"><span data-stu-id="7e315-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="7e315-139">Passez en revue ces attributs et leurs types de sémantiques, car ils seront utilisés pour combiner vos entités lors de l’étape de fusion de l’unification des données.</span><span class="sxs-lookup"><span data-stu-id="7e315-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="7e315-140">Les attributs qui ne sont pas automatiquement mappés à un type de sémantique sont regroupés dans la section **Définir les données dans les champs non mappés**.</span><span class="sxs-lookup"><span data-stu-id="7e315-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="7e315-141">Sélectionnez le champ de type de sémantique pour les attributs non mappés ou entrez votre nom de type d’attribut personnalisé.</span><span class="sxs-lookup"><span data-stu-id="7e315-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7e315-142">![Clé primaire et type d'attribut](media/data-manager-configure-map-add-attributes.png "Clé primaire et type d’attribut")</span><span class="sxs-lookup"><span data-stu-id="7e315-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="7e315-143">Un champ doit correspondre au type de sémantique Person.FullName pour renseigner le nom du client dans la fiche client.</span><span class="sxs-lookup"><span data-stu-id="7e315-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="7e315-144">Sinon, les cartes client apparaîtront sans nom.</span><span class="sxs-lookup"><span data-stu-id="7e315-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="7e315-145">Ajouter et supprimer des attributs et des entités</span><span class="sxs-lookup"><span data-stu-id="7e315-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="7e315-146">Sur **Unifier** > **Mapper**, sélectionnez **Modifier les champs**.</span><span class="sxs-lookup"><span data-stu-id="7e315-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="7e315-147">Dans le volet **Modifier les champs**, ajoutez ou supprimez des attributs et des entités.</span><span class="sxs-lookup"><span data-stu-id="7e315-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="7e315-148">Utilisez la recherche ou faites défiler la liste des attributs et des entités qui vous intéressent.</span><span class="sxs-lookup"><span data-stu-id="7e315-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="7e315-149">Vous ne pouvez pas supprimer un attribut ou une entité s’ils ont déjà été mis en correspondance.</span><span class="sxs-lookup"><span data-stu-id="7e315-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7e315-150">![Ajouter ou supprimer des attributs](media/configure-data-map-edit.png "Ajouter ou supprimer des attributs")</span><span class="sxs-lookup"><span data-stu-id="7e315-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="7e315-151">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="7e315-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="7e315-152">Ajouter des images aux profils</span><span class="sxs-lookup"><span data-stu-id="7e315-152">Add images to profiles</span></span>

<span data-ttu-id="7e315-153">Si une entité contient des URL vers des images de profil ou des logos accessibles au public, vous pouvez les ajouter au profil client unifié.</span><span class="sxs-lookup"><span data-stu-id="7e315-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="7e315-154">Sélectionnez l’entité et recherchez le champ contenant l’URL vers l’image du profil.</span><span class="sxs-lookup"><span data-stu-id="7e315-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="7e315-155">Dans le champ de saisie **Type**, entrez manuellement la valeur suivante :</span><span class="sxs-lookup"><span data-stu-id="7e315-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="7e315-156">Pour une personne : Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="7e315-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="7e315-157">Pour une organisation : Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="7e315-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="7e315-158">Poursuivez les étapes d’unification et assurez-vous que l’attribut qui contient l’URL de l’image est également ajouté à l’étape [Fusionner](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="7e315-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="7e315-159">Définir des attributs pour des organisations</span><span class="sxs-lookup"><span data-stu-id="7e315-159">Set attributes for organizations</span></span>

<span data-ttu-id="7e315-160">Pour les organisations (version préliminaire), le type d’attribut doit être mis en correspondance avec « Organization.Name »</span><span class="sxs-lookup"><span data-stu-id="7e315-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="7e315-161">![Clé primaire et type d’attribut B2B](media/configure-data-map-edit-b2b.png "Clé primaire et type d’attribut B2B")</span><span class="sxs-lookup"><span data-stu-id="7e315-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="7e315-162">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="7e315-162">Next step</span></span>

<span data-ttu-id="7e315-163">Dans le cadre du processus d’unification des données, accédez à la page **Mettre en correspondance**.</span><span class="sxs-lookup"><span data-stu-id="7e315-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="7e315-164">Consultez [**Mettre en correspondance**](match-entities.md) pour vous familiariser avec cette phase.</span><span class="sxs-lookup"><span data-stu-id="7e315-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="7e315-165">Consultez la vidéo suivante : [Mise en route : Création d’un profil client unifié](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="7e315-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>
