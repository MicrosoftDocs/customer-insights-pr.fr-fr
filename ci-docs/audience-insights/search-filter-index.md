---
title: Rechercher et filtrer des profils clients
description: Trouvez rapidement des informations sur les profils de clients unifiés et filtrez les attributs spécifiés.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597140"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="5c8fc-103">Profils client : Index Rechercher et filtrer</span><span class="sxs-lookup"><span data-stu-id="5c8fc-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="5c8fc-104">Le résultat de l’unification de vos données client est une entité de profil client qui fournit une vue unifiée de l’intégralité de votre clientèle.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="5c8fc-105">Pour rapidement [trouver des informations sur un client ou un groupe de clients spécifique](customer-profiles.md), vous pouvez configurer les capacités **Rechercher** et **Filtrer** sur la page **Clients**.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="5c8fc-106">Lisez la suite pour savoir comment les administrateurs peuvent modifier les attributs sur la page **Index Rechercher et filtrer**, disponibles pour la recherche et le filtrage.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5c8fc-107">![Filtre de recherche](media/search-filter.png "Filtre de recherche")</span><span class="sxs-lookup"><span data-stu-id="5c8fc-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="5c8fc-108">Ajouter des champs et spécifier des attributs</span><span class="sxs-lookup"><span data-stu-id="5c8fc-108">Add fields and specify attributes</span></span>

<span data-ttu-id="5c8fc-109">Si c’est la première fois que vous définissez des attributs de recherche en tant qu’administrateur, vous devez d’abord définir des champs indexés.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="5c8fc-110">Nous vous suggérons de choisir tous les attributs par lesquels les utilisateurs peuvent rechercher et filtrer les clients sur la page **Clients**.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="5c8fc-111">Vous pouvez sélectionner uniquement des attributs qui existent dans l’entité Profil client que vous avez créée pendant le processus d’unification des données.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="5c8fc-112">Ouvrez la page **Clients** et sélectionnez **Index Rechercher et filtrer**.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="5c8fc-113">Sélectionnez **+ Ajouter** pour spécifier les champs indexés.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="5c8fc-114">Dans la liste, sélectionnez les attributs à ajouter en tant que champs indexés.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="5c8fc-115">Vous pouvez toujours ajouter plus d’attributs en sélectionnant **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="5c8fc-116">Vous pouvez également supprimer tous les attributs sélectionnés en sélectionnant le symbole **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="5c8fc-117">Explorer la table Champs client indexés</span><span class="sxs-lookup"><span data-stu-id="5c8fc-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="5c8fc-118">Les informations suivantes sont fournies dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="5c8fc-119">**Nom** : Représente le nom de l’attribut comme il s’affiche dans l’entité Profil de client.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="5c8fc-120">**Type de données** : Spécifie si le type de données est une chaîne, un nombre ou une date.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="5c8fc-121">**Inclus dans la recherche** : Spécifie si l’attribut peut être utilisé pour rechercher des clients sur la page **Clients** (en utilisant le champ **Rechercher**).</span><span class="sxs-lookup"><span data-stu-id="5c8fc-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="5c8fc-122">**Ajouter un filtre** : Permet de définir la manière dont cet attribut peut être utilisé pour filtrer la page **Clients**.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="5c8fc-123">Modifier les options de filtrage pour un attribut donné</span><span class="sxs-lookup"><span data-stu-id="5c8fc-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="5c8fc-124">Le menu **Filtrer** sur la page **Clients** peut inclure un nombre variable de niveaux d’attribut (par exemple, différentes tranches d’âges à partir desquelles filtrer les clients).</span><span class="sxs-lookup"><span data-stu-id="5c8fc-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="5c8fc-125">Sélectionnez **Ajouter un filtre** pour un attribut donné sur la page **Index Rechercher et filtrer**.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="5c8fc-126">Vous pouvez définir le nombre de résultats et l’ordre dans lequel ils seront organisés.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="5c8fc-127">Selon le type de données de l’attribut, l’un des volets suivants apparaît.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="5c8fc-128">Attributs de type chaîne : spécifiez le nombre de résultats souhaités dans le volet **Options de filtre de chaîne**, ainsi que la stratégie d’ordre dans lequel ils seront organisés.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="5c8fc-129">Attributs de type numérique : spécifiez les intervalles inclus dans le volet **Options de filtre de nombre**, ainsi que la stratégie d’ordre dans lequel ils seront organisés.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="5c8fc-130">Attributs de type de date : spécifiez les intervalles inclus dans le volet **Options de filtre de date**, ainsi que la stratégie d’ordre dans lequel ils seront organisés.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="5c8fc-131">Sélectionnez **Enregistrer** pour appliquer vos modifications.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="5c8fc-132">Sélectionnez **Exécuter** une fois que vous êtes prêt(e) à appliquer vos paramètres.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5c8fc-133">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="5c8fc-133">Next steps</span></span>

<span data-ttu-id="5c8fc-134">Aller à la page **Clients** pour rechercher des profils client ou utiliser les champs indexés pour voir un sous-ensemble de tous les profils client.</span><span class="sxs-lookup"><span data-stu-id="5c8fc-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]