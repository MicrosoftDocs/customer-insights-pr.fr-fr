---
title: Actualisation incrémentielle des sources de données basées sur Power Query
description: Actualisez les données nouvelles et mises à jour pour les sources de données volumineuses basées sur Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268545"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="0125d-103">Actualisation incrémentielle pour les sources de données basées sur Power Query</span><span class="sxs-lookup"><span data-stu-id="0125d-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="0125d-104">L’actualisation incrémentielle des sources de données offre les avantages suivants :</span><span class="sxs-lookup"><span data-stu-id="0125d-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="0125d-105">**Actualisations plus rapides** - Seules les données modifiées ont été actualisées.</span><span class="sxs-lookup"><span data-stu-id="0125d-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="0125d-106">Par exemple, vous pouvez actualiser uniquement les cinq derniers jours d’un historique jeu de données.</span><span class="sxs-lookup"><span data-stu-id="0125d-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="0125d-107">**Fiabilité accrue** - Avec des actualisations plus petites, vous n’avez pas besoin de maintenir les connexions aux systèmes sources volatils aussi longtemps, ce qui réduit le risque de problèmes de connexion.</span><span class="sxs-lookup"><span data-stu-id="0125d-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="0125d-108">**Réduction de la consommation de ressources** - Actualiser uniquement un sous-ensemble de vos données totales permet une utilisation plus efficace des ressources informatiques et diminue l’empreinte environnementale.</span><span class="sxs-lookup"><span data-stu-id="0125d-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="0125d-109">Configurer l’actualisation incrémentielle</span><span class="sxs-lookup"><span data-stu-id="0125d-109">Configure incremental refresh</span></span>

<span data-ttu-id="0125d-110">Les informations sur l’audience permettent une actualisation incrémentielle des sources de données importées via Power Query qui prennent en charge l’ingestion incrémentielle.</span><span class="sxs-lookup"><span data-stu-id="0125d-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="0125d-111">Par exemple, des bases de données SQL Azure avec des champs de date et d’heure, qui indiquent quand les enregistrements de données ont été mis à jour pour la dernière fois.</span><span class="sxs-lookup"><span data-stu-id="0125d-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="0125d-112">[Créer une source de données basée sur Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="0125d-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="0125d-113">Offrez un nom pour la source de données.</span><span class="sxs-lookup"><span data-stu-id="0125d-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="0125d-114">Sélectionnez une source de données qui prend en charge l’actualisation incrémentielle, telle qu’une base de données Azure SQL.</span><span class="sxs-lookup"><span data-stu-id="0125d-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="0125d-115">Sélectionnez les entités ou les tables à ingérer.</span><span class="sxs-lookup"><span data-stu-id="0125d-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="0125d-116">Terminez les étapes de transformation et sélectionnez **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="0125d-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="0125d-117">Dans la boîte de dialogue **Configurer une actualisation incrémentielle**, sélectionnez **Configurer** pour ouvrir **Paramètres d’actualisation incrémentielle**.</span><span class="sxs-lookup"><span data-stu-id="0125d-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="0125d-118">Si vous sélectionnez **Ignorer**, la source de données actualisera l’intégralité du jeu de données.</span><span class="sxs-lookup"><span data-stu-id="0125d-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="0125d-119">Vous pouvez également appliquer une actualisation incrémentielle ultérieurement en modifiant une source de données existante.</span><span class="sxs-lookup"><span data-stu-id="0125d-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="0125d-120">Sur **Paramètres d’actualisation incrémentielle**, vous allez configurer l’actualisation incrémentielle pour toutes les entités que vous avez sélectionnées lors de la création de la source de données.</span><span class="sxs-lookup"><span data-stu-id="0125d-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0125d-121">![Configurer des entités dans une source de données pour une actualisation incrémentielle](media/incremental-refresh-settings.png "Configurer des entités dans une source de données pour une actualisation incrémentielle")</span><span class="sxs-lookup"><span data-stu-id="0125d-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="0125d-122">Sélectionnez une entité et fournissez les détails suivants :</span><span class="sxs-lookup"><span data-stu-id="0125d-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="0125d-123">**Définir la clé primaire** : Sélectionnez une clé primaire pour l’entité ou la table.</span><span class="sxs-lookup"><span data-stu-id="0125d-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="0125d-124">**Définir le champ « dernière mise à jour »**  : Ce champ n’affichera que les attributs de type date ou heure.</span><span class="sxs-lookup"><span data-stu-id="0125d-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="0125d-125">Sélectionnez un attribut qui indique la dernière mise à jour des enregistrements.</span><span class="sxs-lookup"><span data-stu-id="0125d-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="0125d-126">Il sera utilisé pour identifier les enregistrements faisant partie de la fenêtre temporelle de l’actualisation incrémentielle.</span><span class="sxs-lookup"><span data-stu-id="0125d-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="0125d-127">**Rechercher des mises à jour toutes les** : Spécifiez la durée du délai d’exécution de l’actualisation incrémentielle.</span><span class="sxs-lookup"><span data-stu-id="0125d-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="0125d-128">Sélectionnez **Enregistrer** pour terminer la création de la source de données.</span><span class="sxs-lookup"><span data-stu-id="0125d-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="0125d-129">L’actualisation initiale des données sera une actualisation complète.</span><span class="sxs-lookup"><span data-stu-id="0125d-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="0125d-130">Ensuite, l’actualisation incrémentielle des données se produit comme configuré à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="0125d-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]