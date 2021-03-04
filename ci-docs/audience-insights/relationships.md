---
title: Relations entre des entités et des chemins d’accès d’entités
description: Créez et gérez les relations entre des entités à partir de plusieurs sources de données.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269871"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="34792-103">Relations entre les entités</span><span class="sxs-lookup"><span data-stu-id="34792-103">Relationships between entities</span></span>

<span data-ttu-id="34792-104">Avec les relations, connectez les entités entre elles et générez des graphiques de vos données lorsque les entités partagent un identificateur commun (clé étrangère) qui peut être référencé d’une entité à une autre.</span><span class="sxs-lookup"><span data-stu-id="34792-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="34792-105">Les entités connectées vous permettent de définir des segments et des mesures à partir de sources de données multiples.</span><span class="sxs-lookup"><span data-stu-id="34792-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="34792-106">Il existe deux types de relations :</span><span class="sxs-lookup"><span data-stu-id="34792-106">There are two types of relationships.</span></span> <span data-ttu-id="34792-107">Relations du système non modifiable, qui sont créées automatiquement, et relations personnalisées, créées et configurées par les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="34792-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="34792-108">Pendant les processus de mise en correspondance et de fusion, les relations système sont créées en coulisse en fonction de la mise en correspondance intelligente.</span><span class="sxs-lookup"><span data-stu-id="34792-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="34792-109">Ces relations permettent d’associer les enregistrements du profil client avec d’autres enregistrements d’entités correspondantes.</span><span class="sxs-lookup"><span data-stu-id="34792-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="34792-110">Le schéma suivant illustre la création de trois relations système quand l’entité Client est mise en correspondance avec d’autres entités pour générer l’entité finale Profil du client.</span><span class="sxs-lookup"><span data-stu-id="34792-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="34792-111">![Création d’une relation](media/relationships-entities-merge.png "Création d’une relation")</span><span class="sxs-lookup"><span data-stu-id="34792-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="34792-112">La **relation *CustomerToContact*** a été créée entre l’entité Client et l’entité Contact.</span><span class="sxs-lookup"><span data-stu-id="34792-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="34792-113">L’entité Client reçoit le champ clé **Contact_contactId** pour se lier au champ clé **contactId** de l’entité Contact.</span><span class="sxs-lookup"><span data-stu-id="34792-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="34792-114">La **relation *CustomerToAccount*** a été créée entre l’entité Client et l’entité Compte.</span><span class="sxs-lookup"><span data-stu-id="34792-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="34792-115">L’entité Client reçoit le champ clé **Account_accountId** pour se lier au champ clé **accountId** de l’entité Compte.</span><span class="sxs-lookup"><span data-stu-id="34792-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="34792-116">La **relation *CustomerToWebAccount*** a été créée entre l’entité Client et l’entité Compte Web.</span><span class="sxs-lookup"><span data-stu-id="34792-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="34792-117">L’entité Client reçoit le champ clé **WebAccount_webaccountId** pour se lier au champ clé **webaccountId** de l’entité Compte Web.</span><span class="sxs-lookup"><span data-stu-id="34792-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="34792-118">Créer une relation</span><span class="sxs-lookup"><span data-stu-id="34792-118">Create a relationship</span></span>

<span data-ttu-id="34792-119">Définissez des relations personnalisées sur la page **Relations**.</span><span class="sxs-lookup"><span data-stu-id="34792-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="34792-120">Chaque relation se compose d’une entité source (l’entité qui détient la clé étrangère) et d’une entité cible (l’entité vers laquelle pointe la clé étrangère de l’entité source).</span><span class="sxs-lookup"><span data-stu-id="34792-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="34792-121">Dans les informations sur l’audience, accédez à **Données** > **Relations**.</span><span class="sxs-lookup"><span data-stu-id="34792-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="34792-122">Sélectionnez **Nouvelle relation**.</span><span class="sxs-lookup"><span data-stu-id="34792-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="34792-123">Dans le volet **Ajouter une relation**, fournissez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="34792-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="34792-124">![Entrer les détails de la relation](media/relationships-add.png "Entrer les détails de la relation")</span><span class="sxs-lookup"><span data-stu-id="34792-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="34792-125">**Nom de la relation** : Indiquez un nom qui reflète l’objectif de la relation (par exemple, **Journauxcompteweb**).</span><span class="sxs-lookup"><span data-stu-id="34792-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="34792-126">**Description** : Description de la relation.</span><span class="sxs-lookup"><span data-stu-id="34792-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="34792-127">**Entité source** : Sélectionnez l’entité qui sert de source dans la relation (par exemple, Journalweb).</span><span class="sxs-lookup"><span data-stu-id="34792-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="34792-128">**Cardinalité** : Sélectionnez la cardinalité des enregistrement de l’entité source.</span><span class="sxs-lookup"><span data-stu-id="34792-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="34792-129">Par exemple, « Beaucoup » signifie que plusieurs enregistrements de journal web sont associés à un Compte web.</span><span class="sxs-lookup"><span data-stu-id="34792-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="34792-130">**Champ Clé source** : Représente le champ de clé étrangère dans l’entité source.</span><span class="sxs-lookup"><span data-stu-id="34792-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="34792-131">Par exemple, Journalweb possède le champ de clé étrangère **accountId**.</span><span class="sxs-lookup"><span data-stu-id="34792-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="34792-132">**Entité cible** : Sélectionnez l’entité qui sert de cible dans la relation (par exemple, Compte web).</span><span class="sxs-lookup"><span data-stu-id="34792-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="34792-133">**Cardinalité cible** : Sélectionnez la cardinalité des enregistrement de l’entité cible.</span><span class="sxs-lookup"><span data-stu-id="34792-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="34792-134">Par exemple, « Un » signifie que plusieurs enregistrements de journal web sont associées à un Compte web.</span><span class="sxs-lookup"><span data-stu-id="34792-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="34792-135">**Champ de clé cible** : ce champ représente le champ de clé de l’entité cible.</span><span class="sxs-lookup"><span data-stu-id="34792-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="34792-136">Par exemple, Compte web possède le champ de clé **accountId**.</span><span class="sxs-lookup"><span data-stu-id="34792-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="34792-137">Seuls les types de relation plusieurs-à-un et un-à-un sont pris en charge.</span><span class="sxs-lookup"><span data-stu-id="34792-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="34792-138">Les relations Plusieurs-à-plusieurs peuvent être créées à l’aide de deux relations plusieurs-à-un et une entité de liaison (une entité qui sert à connecter l’entité source et l’entité cible).</span><span class="sxs-lookup"><span data-stu-id="34792-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="34792-139">Supprimer une relation</span><span class="sxs-lookup"><span data-stu-id="34792-139">Delete a relationship</span></span>

1. <span data-ttu-id="34792-140">Dans les informations sur l’audience, accédez à **Données** > **Relations**.</span><span class="sxs-lookup"><span data-stu-id="34792-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="34792-141">Activez les cases à cocher correspondant aux relations que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="34792-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="34792-142">Sélectionnez **Supprimer** en haut de la table **Relations**.</span><span class="sxs-lookup"><span data-stu-id="34792-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="34792-143">Confirmez votre suppression.</span><span class="sxs-lookup"><span data-stu-id="34792-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="34792-144">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="34792-144">Next step</span></span>

<span data-ttu-id="34792-145">Les relations système et personnalisées sont utilisées pour créer des segments à partir de plusieurs sources de données qui ne sont plus en silos.</span><span class="sxs-lookup"><span data-stu-id="34792-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="34792-146">Pour plus d’informations, voir [Segments](segments.md).</span><span class="sxs-lookup"><span data-stu-id="34792-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]