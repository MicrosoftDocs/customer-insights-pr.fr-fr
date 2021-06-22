---
title: Relations entre des entités et des chemins d’accès d’entités
description: Créez et gérez les relations entre des entités à partir de plusieurs sources de données.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171161"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="31ec3-103">Relations entre les entités</span><span class="sxs-lookup"><span data-stu-id="31ec3-103">Relationships between entities</span></span>

<span data-ttu-id="31ec3-104">Les relations connectent les entités et définissent un graphique de vos données lorsque les entités partagent un identifiant commun, une clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="31ec3-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="31ec3-105">Cette clé étrangère peut être référencée d'une entité à une autre.</span><span class="sxs-lookup"><span data-stu-id="31ec3-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="31ec3-106">Les entités connectées permettent de définir des segments et des mesures en fonction de plusieurs sources de données.</span><span class="sxs-lookup"><span data-stu-id="31ec3-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="31ec3-107">Il existe trois types de relations :</span><span class="sxs-lookup"><span data-stu-id="31ec3-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="31ec3-108">Relations système non modifiables, créées par le système dans le cadre du processus d'unification des données</span><span class="sxs-lookup"><span data-stu-id="31ec3-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="31ec3-109">Relations hérités non modifiables, qui sont créés automatiquement à partir de sources de données d'ingestion</span><span class="sxs-lookup"><span data-stu-id="31ec3-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="31ec3-110">Relations personnalisées modifiables, créées et configurées par les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="31ec3-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="31ec3-111">Relations système non modifiables</span><span class="sxs-lookup"><span data-stu-id="31ec3-111">Non-editable system relationships</span></span>

<span data-ttu-id="31ec3-112">Lors de l'unification des données, les relations système sont créées automatiquement sur la base d'une correspondance intelligente.</span><span class="sxs-lookup"><span data-stu-id="31ec3-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="31ec3-113">Ces relations permettent d’associer les enregistrements du profil client avec les enregistrements correspondants.</span><span class="sxs-lookup"><span data-stu-id="31ec3-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="31ec3-114">Le diagramme suivant illustre la création de trois relations basées sur le système.</span><span class="sxs-lookup"><span data-stu-id="31ec3-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="31ec3-115">L'entité Client est mise en correspondance avec d'autres entités pour produire l'entité *Client*.</span><span class="sxs-lookup"><span data-stu-id="31ec3-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagramme avec les chemins de relation pour l'entité Client avec trois Relations 1-n.":::

- <span data-ttu-id="31ec3-117">La **relation *CustomerToContact*** a été créée entre l’entité *Client* et l’entité *Contact*.</span><span class="sxs-lookup"><span data-stu-id="31ec3-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="31ec3-118">L’entité *Client* reçoit le champ clé **Contact_contactId** pour se lier au champ clé **contactID** de l’entité *Contact*.</span><span class="sxs-lookup"><span data-stu-id="31ec3-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="31ec3-119">La **relation *CustomerToAccount*** a été créée entre l’entité *Client* et l’entité *Compte*.</span><span class="sxs-lookup"><span data-stu-id="31ec3-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="31ec3-120">L’entité *Client* reçoit le champ clé **Account_accountID** pour se lier au champ clé **accountID** de l’entité *Compte*.</span><span class="sxs-lookup"><span data-stu-id="31ec3-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="31ec3-121">La **relation *CustomerToWebAccount*** a été créée entre l’entité *Client* et l’entité *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="31ec3-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="31ec3-122">L’entité *Client* reçoit le champ clé **WebAccount_webaccountID** pour se lier au champ clé **webaccountID** l’entité *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="31ec3-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="31ec3-123">Relations héritées non modifiables</span><span class="sxs-lookup"><span data-stu-id="31ec3-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="31ec3-124">Pendant le processus d'ingestion de données, le système vérifie les sources de données pour les relations existantes.</span><span class="sxs-lookup"><span data-stu-id="31ec3-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="31ec3-125">Si aucune relation n'existe, le système les crée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="31ec3-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="31ec3-126">Ces relations sont également utilisées dans les processus en aval.</span><span class="sxs-lookup"><span data-stu-id="31ec3-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="31ec3-127">Créer une relation personnalisée</span><span class="sxs-lookup"><span data-stu-id="31ec3-127">Create a custom relationship</span></span>

<span data-ttu-id="31ec3-128">La relation consiste en une *entité source* contenant la clé étrangère et une *entité cible* vers laquelle pointe la clé étrangère de l'entité source.</span><span class="sxs-lookup"><span data-stu-id="31ec3-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="31ec3-129">Dans les informations sur l’audience, accédez à **Données** > **Relations**.</span><span class="sxs-lookup"><span data-stu-id="31ec3-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="31ec3-130">Sélectionnez **Nouvelle relation**.</span><span class="sxs-lookup"><span data-stu-id="31ec3-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="31ec3-131">Dans le volet **Nouvelle relation**, fournissez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="31ec3-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Volet latéral Nouvelle relation avec des champs de saisie vides.":::

   - <span data-ttu-id="31ec3-133">**Nom de la relation** : Nom qui reflète l'objectif de la relation.</span><span class="sxs-lookup"><span data-stu-id="31ec3-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="31ec3-134">Exemple : CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="31ec3-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="31ec3-135">**Description** : Description de la relation.</span><span class="sxs-lookup"><span data-stu-id="31ec3-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="31ec3-136">**Entité source** : Entité utilisée comme source dans la relation.</span><span class="sxs-lookup"><span data-stu-id="31ec3-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="31ec3-137">Exemple : SupportCase.</span><span class="sxs-lookup"><span data-stu-id="31ec3-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="31ec3-138">**Entité cible** : Entité utilisée comme cible dans la relation.</span><span class="sxs-lookup"><span data-stu-id="31ec3-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="31ec3-139">Exemple : Client.</span><span class="sxs-lookup"><span data-stu-id="31ec3-139">Example: Customer.</span></span>
   - <span data-ttu-id="31ec3-140">**Cardinalité de la source** : Spécifie la cardinalité de l'entité source.</span><span class="sxs-lookup"><span data-stu-id="31ec3-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="31ec3-141">La cardinalité décrit le nombre d'éléments possibles dans un ensemble.</span><span class="sxs-lookup"><span data-stu-id="31ec3-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="31ec3-142">Elle se rapporte toujours à la cardinalité cible.</span><span class="sxs-lookup"><span data-stu-id="31ec3-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="31ec3-143">Vous pouvez choisir les valeurs **Une** et **Plusieurs**.</span><span class="sxs-lookup"><span data-stu-id="31ec3-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="31ec3-144">Seuls les types de relation plusieurs-à-un et un-à-un sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="31ec3-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="31ec3-145">Plusieurs-à-un : plusieurs enregistrements source peuvent être liés à un seul enregistrement cible.</span><span class="sxs-lookup"><span data-stu-id="31ec3-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="31ec3-146">Exemple : plusieurs cas d'assistance d'un même client.</span><span class="sxs-lookup"><span data-stu-id="31ec3-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="31ec3-147">Un-à-un : un seul enregistrement source se rapporte à un seul enregistrement cible.</span><span class="sxs-lookup"><span data-stu-id="31ec3-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="31ec3-148">Exemple : un ID de fidélité pour un même client.</span><span class="sxs-lookup"><span data-stu-id="31ec3-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="31ec3-149">Les relations Plusieurs-à-plusieurs peuvent être créées à l'aide de deux relations Plusieurs-à-un et une entité de liaison, qui se connecte à l'entité source et l'entité cible.</span><span class="sxs-lookup"><span data-stu-id="31ec3-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="31ec3-150">**Cardinalité cible** : Sélectionnez la cardinalité des enregistrement de l’entité cible.</span><span class="sxs-lookup"><span data-stu-id="31ec3-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="31ec3-151">**Champ de clé source** : champ de clé étrangère dans l'entité source.</span><span class="sxs-lookup"><span data-stu-id="31ec3-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="31ec3-152">Exemple : SupportCase peut utiliser CaseID comme champ de clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="31ec3-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="31ec3-153">**Champ de clé cible** : champ de clé de l’entité cible.</span><span class="sxs-lookup"><span data-stu-id="31ec3-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="31ec3-154">Par exemple, Client peut utiliser le champ de clé **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="31ec3-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="31ec3-155">Sélectionnez **Enregistrer** pour créer la relation personnalisée.</span><span class="sxs-lookup"><span data-stu-id="31ec3-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="31ec3-156">Afficher les relations</span><span class="sxs-lookup"><span data-stu-id="31ec3-156">View relationships</span></span>

<span data-ttu-id="31ec3-157">La page Relations répertorie toutes les relations qui ont été créées.</span><span class="sxs-lookup"><span data-stu-id="31ec3-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="31ec3-158">Chaque ligne représente une relation, qui inclut également des détails sur l'entité source, l'entité cible et la cardinalité.</span><span class="sxs-lookup"><span data-stu-id="31ec3-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Liste des relations et options dans la barre d'action de la page Relations.":::

<span data-ttu-id="31ec3-160">Cette page propose un ensemble d'options pour les relations existants et nouvelles :</span><span class="sxs-lookup"><span data-stu-id="31ec3-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="31ec3-161">**Nouvelle relation** : [Créer une relation personnalisée](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="31ec3-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="31ec3-162">**Visualiseur** : [Explorez le visualiseur de relations](#explore-the-relationship-visualizer) pour voir un diagramme réseau des relations existantes et de leur cardinalité.</span><span class="sxs-lookup"><span data-stu-id="31ec3-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="31ec3-163">**Filtrer par** : Choisissez le type de relations à afficher dans la liste.</span><span class="sxs-lookup"><span data-stu-id="31ec3-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="31ec3-164">**Rechercher des relations** : Utilisez une recherche textuelle sur les propriétés des relations.</span><span class="sxs-lookup"><span data-stu-id="31ec3-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="31ec3-165">Explorez le visualiseur de relations</span><span class="sxs-lookup"><span data-stu-id="31ec3-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="31ec3-166">Le visualiseur de relations montre un diagramme réseau des relations existantes entre les entités connectées et de leur cardinalité.</span><span class="sxs-lookup"><span data-stu-id="31ec3-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="31ec3-167">Pour personnaliser l'affichage, vous pouvez modifier la position des cases en les faisant glisser sur le canevas.</span><span class="sxs-lookup"><span data-stu-id="31ec3-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Capture d'écran du diagramme réseau du visualiseur de relations avec les connexions entre les entités associées.":::

<span data-ttu-id="31ec3-169">Options disponibles :</span><span class="sxs-lookup"><span data-stu-id="31ec3-169">Available options:</span></span> 
- <span data-ttu-id="31ec3-170">**Exporter en tant qu'image** : enregistre la vue actuelle en tant que fichier image.</span><span class="sxs-lookup"><span data-stu-id="31ec3-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="31ec3-171">**Changer en disposition horizontale/verticale** : Modifiez l'alignement des entités et des relations.</span><span class="sxs-lookup"><span data-stu-id="31ec3-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="31ec3-172">**Modifier** : Mettez à jour les propriétés des relations personnalisées dans le volet d'édition et enregistrez les modifications.</span><span class="sxs-lookup"><span data-stu-id="31ec3-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="31ec3-173">Gérer les relations existantes</span><span class="sxs-lookup"><span data-stu-id="31ec3-173">Manage existing relationships</span></span> 

<span data-ttu-id="31ec3-174">Sur la page Relations, chaque relation est représentée par une ligne.</span><span class="sxs-lookup"><span data-stu-id="31ec3-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="31ec3-175">Sélectionnez une relation et choisissez l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="31ec3-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="31ec3-176">**Modifier** : Mettez à jour les propriétés des relations personnalisées dans le volet d'édition et enregistrez les modifications.</span><span class="sxs-lookup"><span data-stu-id="31ec3-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="31ec3-177">**Supprimer** : Supprimez les relations personnalisées.</span><span class="sxs-lookup"><span data-stu-id="31ec3-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="31ec3-178">**Afficher** : Affichez les relations créées par le système et les relations héritées.</span><span class="sxs-lookup"><span data-stu-id="31ec3-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="31ec3-179">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="31ec3-179">Next step</span></span>

<span data-ttu-id="31ec3-180">Les relations système et personnalisées sont utilisées pour [créer des segments](segments.md) à partir de plusieurs sources de données qui ne sont plus en silos.</span><span class="sxs-lookup"><span data-stu-id="31ec3-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
