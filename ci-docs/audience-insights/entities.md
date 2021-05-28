---
title: Entités et ensembles de données
description: Affichez les données sur la page Entités.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049391"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="8413a-103">Entités dans les informations sur l’audience</span><span class="sxs-lookup"><span data-stu-id="8413a-103">Entities in audience insights</span></span>

<span data-ttu-id="8413a-104">Après la [configuration de vos sources de données](data-sources.md), accédez à la page **Entités** pour évaluer la qualité des données ingérées.</span><span class="sxs-lookup"><span data-stu-id="8413a-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="8413a-105">Les entités sont considérées comme des ensembles de données.</span><span class="sxs-lookup"><span data-stu-id="8413a-105">Entities are considered datasets.</span></span> <span data-ttu-id="8413a-106">Plusieurs fonctionnalités de Dynamics 365 Customer Insights sont basées sur ces entités.</span><span class="sxs-lookup"><span data-stu-id="8413a-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="8413a-107">Un examen approfondi peut vous aider à valider les résultats de ces fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="8413a-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="8413a-108">La page **Entités** répertorie les entités et comprend plusieurs colonnes :</span><span class="sxs-lookup"><span data-stu-id="8413a-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="8413a-109">**Nom** : Le nom de vos entités de données.</span><span class="sxs-lookup"><span data-stu-id="8413a-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="8413a-110">Si vous voyez un symbole d’avertissement en regard de l’entité, cela signifie que les données de cette entité n’ont pas été chargées correctement.</span><span class="sxs-lookup"><span data-stu-id="8413a-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="8413a-111">**Source** : le type de source de données qui a ingéré l’entité</span><span class="sxs-lookup"><span data-stu-id="8413a-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="8413a-112">**Créée par** : Le nom de l’utilisateur qui a créé l’entité.</span><span class="sxs-lookup"><span data-stu-id="8413a-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="8413a-113">**Créée** : La date et l’heure de création de l’entité</span><span class="sxs-lookup"><span data-stu-id="8413a-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="8413a-114">**Mise à jour par** : Le nom de l’utilisateur qui a mis à jour l’entité.</span><span class="sxs-lookup"><span data-stu-id="8413a-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="8413a-115">**Dernière mise à jour** : La date et l’heure de la dernière mise à jour de l’entité</span><span class="sxs-lookup"><span data-stu-id="8413a-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="8413a-116">**Dernière actualisation** : La date et l’heure de la dernière actualisation des données</span><span class="sxs-lookup"><span data-stu-id="8413a-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="8413a-117">Explorer les données d’une entité spécifique</span><span class="sxs-lookup"><span data-stu-id="8413a-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="8413a-118">Sélectionnez une entité pour explorer les différents champs et enregistrements inclus dans cette entité.</span><span class="sxs-lookup"><span data-stu-id="8413a-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8413a-119">![Sélectionner une entité](media/data-manager-entities-data.png "Sélectionner une entité")</span><span class="sxs-lookup"><span data-stu-id="8413a-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="8413a-120">L’onglet **Données** affiche un tableau répertoriant les détails des enregistrements individuels de l’entité.</span><span class="sxs-lookup"><span data-stu-id="8413a-120">The **Data** tab shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8413a-121">![Table Champs](media/data-manager-entities-fields.PNG "Table Champs")</span><span class="sxs-lookup"><span data-stu-id="8413a-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="8413a-122">L’onglet **Attributs** est sélectionné par défaut et affiche un tableau pour examiner les détails de l’entité sélectionnée, tels que les noms des champs, les types de données et les types.</span><span class="sxs-lookup"><span data-stu-id="8413a-122">The **Attributes** tab is selected by default and shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="8413a-123">La colonne **Type** affiche les types associés à Common Data Model, qui sont soit identifiés automatiquement par le système, soit [mappés manuellement](map-entities.md) par les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8413a-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="8413a-124">Il s’agit de types sémantiques qui peuvent différer des types de données des attributs (par exemple, le champ *E-mail* ci-dessous contient un type de données *Texte*, mais ce type Common Data Model (sémantique) pourrait être *E-mail* ou *Adresse e-mail*) :</span><span class="sxs-lookup"><span data-stu-id="8413a-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="8413a-125">Les deux tableaux affichent uniquement un échantillon des données de votre entité.</span><span class="sxs-lookup"><span data-stu-id="8413a-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="8413a-126">Pour afficher le jeu de données complet, accédez à la page **Sources de données**, sélectionnez une entité d’intérêt, sélectionnez **Modifier**, puis affichez les données de cette entité dans l’éditeur Power Query, comme décrit dans [Sources de données](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="8413a-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="8413a-127">Pour en savoir plus sur les données ingérées dans l’entité, la colonne **Résumé** vous fournit quelques caractéristiques importantes des données, telles que les valeurs nulles, les valeurs manquantes, les valeurs uniques, les nombres et les distributions, selon vos données.</span><span class="sxs-lookup"><span data-stu-id="8413a-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="8413a-128">Sélectionnez l’icône de graphique pour voir un récapitulatif des données.</span><span class="sxs-lookup"><span data-stu-id="8413a-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8413a-129">![Symbole récapitulatif](media/data-manager-entities-summary.png "Table Résumé des données")</span><span class="sxs-lookup"><span data-stu-id="8413a-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="8413a-130">Étape suivante</span><span class="sxs-lookup"><span data-stu-id="8413a-130">Next step</span></span>

<span data-ttu-id="8413a-131">Consultez la rubrique [Unifier](data-unification.md) pour apprendre à *mapper*, *faire correspondre* et *fusionner* les données ingérées.</span><span class="sxs-lookup"><span data-stu-id="8413a-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
