---
title: Utiliser des sources de données pour ingérer des données
description: Découvrez comment importer des données depuis des sources diverses.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 68aa1b56fb634da80a0c64db72f778d57507104d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269695"
---
# <a name="data-sources-overview"></a><span data-ttu-id="c5847-103">Vue d’ensemble des sources de données</span><span class="sxs-lookup"><span data-stu-id="c5847-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c5847-104">La fonctionnalité d’informations sur l’audience de Dynamics 365 Customer Insights se connecte aux données d’un large éventail de sources.</span><span class="sxs-lookup"><span data-stu-id="c5847-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="c5847-105">La connexion à une source de données est souvent appelée processus d’*ingestion de données*.</span><span class="sxs-lookup"><span data-stu-id="c5847-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="c5847-106">Après avoir ingéré les données, vous pouvez les [unifier](data-unification.md) et agir dessus.</span><span class="sxs-lookup"><span data-stu-id="c5847-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="c5847-107">Ajouter une source de données</span><span class="sxs-lookup"><span data-stu-id="c5847-107">Add a data source</span></span>

<span data-ttu-id="c5847-108">Reportez-vous aux articles détaillés sur la façon d’ajouter une source de données, selon l’option que vous choisissez.</span><span class="sxs-lookup"><span data-stu-id="c5847-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="c5847-109">Vous pouvez ajouter une source de données de trois manières principales :</span><span class="sxs-lookup"><span data-stu-id="c5847-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="c5847-110">Grâce à des dizaines de connecteurs Power Query</span><span class="sxs-lookup"><span data-stu-id="c5847-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="c5847-111">À partir d’un dossier Common Data Model</span><span class="sxs-lookup"><span data-stu-id="c5847-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="c5847-112">À partir de votre propre lac Common Data Service</span><span class="sxs-lookup"><span data-stu-id="c5847-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="c5847-113">Vous ne pouvez pas encore ajouter de données à partir de sources de données locales.</span><span class="sxs-lookup"><span data-stu-id="c5847-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="c5847-114">Évaluer les données ingérées</span><span class="sxs-lookup"><span data-stu-id="c5847-114">Review ingested data</span></span>

<span data-ttu-id="c5847-115">Vous avez accès au nom de chaque source de données ingérée, à son statut et à la dernière date d’actualisation des données pour cette source de données.</span><span class="sxs-lookup"><span data-stu-id="c5847-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="c5847-116">Vous pouvez trier la liste des sources de données par colonne.</span><span class="sxs-lookup"><span data-stu-id="c5847-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c5847-117">![Source de données ajoutée](media/configure-data-datasource-added.png "Source de données ajoutée")</span><span class="sxs-lookup"><span data-stu-id="c5847-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="c5847-118">Statut</span><span class="sxs-lookup"><span data-stu-id="c5847-118">Status</span></span>  |<span data-ttu-id="c5847-119">Description</span><span class="sxs-lookup"><span data-stu-id="c5847-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="c5847-120">Opération réussie</span><span class="sxs-lookup"><span data-stu-id="c5847-120">Successful</span></span>   |<span data-ttu-id="c5847-121">La source de données a été ingérée avec succès si une heure est mentionnée dans la colonne **Actualisé**.</span><span class="sxs-lookup"><span data-stu-id="c5847-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="c5847-122">Non démarré(e)</span><span class="sxs-lookup"><span data-stu-id="c5847-122">Not started</span></span>   |<span data-ttu-id="c5847-123">La source de données n’a pas encore de données ingérées ou est toujours en mode brouillon.</span><span class="sxs-lookup"><span data-stu-id="c5847-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="c5847-124">Actualisation</span><span class="sxs-lookup"><span data-stu-id="c5847-124">Refreshing</span></span>    |<span data-ttu-id="c5847-125">L’ingestion de données est en cours.</span><span class="sxs-lookup"><span data-stu-id="c5847-125">Data ingestion is in progress.</span></span> <span data-ttu-id="c5847-126">Vous pouvez annuler cette opération en sélectionnant **Arrêter l’actualisation** dans la colonne **Actions**.</span><span class="sxs-lookup"><span data-stu-id="c5847-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="c5847-127">L’arrêt de l’actualisation d’une source de données la ramène à son dernier état d’actualisation.</span><span class="sxs-lookup"><span data-stu-id="c5847-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="c5847-128">Échoué</span><span class="sxs-lookup"><span data-stu-id="c5847-128">Failed</span></span>     |<span data-ttu-id="c5847-129">L’ingestion de données s’est heurtée à des erreurs.</span><span class="sxs-lookup"><span data-stu-id="c5847-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="c5847-130">Sélectionnez la valeur dans la colonne **Statut** de n’importe quelle source de données pour examiner plus de détails.</span><span class="sxs-lookup"><span data-stu-id="c5847-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="c5847-131">Dans le volet **Détails de la progression**, développez **Sources de données**.</span><span class="sxs-lookup"><span data-stu-id="c5847-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="c5847-132">Sélectionnez **Afficher les détails** pour obtenir plus d’informations sur le statut d’actualisation, notamment les détails de l’erreur et les mises à jour du processus en aval.</span><span class="sxs-lookup"><span data-stu-id="c5847-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="c5847-133">Le chargement des données peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="c5847-133">Loading data can take some time.</span></span> <span data-ttu-id="c5847-134">Après une actualisation réussie, les données ingérées peuvent être consultées à partir de la page **Entités**.</span><span class="sxs-lookup"><span data-stu-id="c5847-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="c5847-135">Pour plus d’informations, voir [Entités](entities.md).</span><span class="sxs-lookup"><span data-stu-id="c5847-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="c5847-136">Actualiser une source de données</span><span class="sxs-lookup"><span data-stu-id="c5847-136">Refresh a data source</span></span>

<span data-ttu-id="c5847-137">Les sources de données peuvent être actualisées selon un calendrier automatique ou actualisées manuellement à la demande.</span><span class="sxs-lookup"><span data-stu-id="c5847-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="c5847-138">Accédez à **Administration** > **Système** > [**Planification**](system.md#schedule-tab) pour configurer des actualisations programmées de toutes vos sources de données ingérées.</span><span class="sxs-lookup"><span data-stu-id="c5847-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="c5847-139">Pour actualiser une source de données à la demande, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="c5847-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="c5847-140">Dans les informations sur l’audience, accédez à **Données** > **Sources de données**</span><span class="sxs-lookup"><span data-stu-id="c5847-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="c5847-141">Sélectionnez les points de suspension verticaux en regard de la source de données que vous souhaitez actualiser, puis sélectionnez **Actualiser** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="c5847-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="c5847-142">La source de données est maintenant déclenchée pour une actualisation manuelle.</span><span class="sxs-lookup"><span data-stu-id="c5847-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="c5847-143">L’actualisation d’une source de données mettra à jour le schéma de l’entité ainsi que les données de toutes les entités spécifiées dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="c5847-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="c5847-144">Sélectionnez **Arrêtez l’actualisation** si vous souhaitez annuler une actualisation existante et rétablir le dernier statut d’actualisation de la source de données.</span><span class="sxs-lookup"><span data-stu-id="c5847-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="c5847-145">Supprimer une source de données</span><span class="sxs-lookup"><span data-stu-id="c5847-145">Delete a data source</span></span>

1. <span data-ttu-id="c5847-146">Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.</span><span class="sxs-lookup"><span data-stu-id="c5847-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="c5847-147">Sélectionnez les points de suspension en regard de la source de données que vous souhaitez supprimer et sélectionnez **Supprimer** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="c5847-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="c5847-148">Confirmez votre suppression.</span><span class="sxs-lookup"><span data-stu-id="c5847-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]