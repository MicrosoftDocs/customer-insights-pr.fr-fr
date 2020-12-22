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
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643950"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="0a746-103">Vue d'ensemble des sources de données</span><span class="sxs-lookup"><span data-stu-id="0a746-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0a746-104">La fonctionnalité Audience Insights de Dynamics 365 Customer Insights se connecte aux données d'un large éventail de sources.</span><span class="sxs-lookup"><span data-stu-id="0a746-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="0a746-105">La connexion à une source de données est souvent appelée processus d'*ingestion de données*.</span><span class="sxs-lookup"><span data-stu-id="0a746-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="0a746-106">Après avoir ingéré les données, vous pouvez les [unifier](data-unification.md) et agir dessus.</span><span class="sxs-lookup"><span data-stu-id="0a746-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="0a746-107">Ajouter une source de données</span><span class="sxs-lookup"><span data-stu-id="0a746-107">Add a data source</span></span>

<span data-ttu-id="0a746-108">Reportez-vous aux articles détaillés sur la façon d'ajouter une source de données, selon l'option que vous choisissez.</span><span class="sxs-lookup"><span data-stu-id="0a746-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="0a746-109">Vous pouvez ajouter une source de données de trois manières principales :</span><span class="sxs-lookup"><span data-stu-id="0a746-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="0a746-110">Grâce à des dizaines de connecteurs Power Query</span><span class="sxs-lookup"><span data-stu-id="0a746-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="0a746-111">À partir d'un dossier Common Data Model</span><span class="sxs-lookup"><span data-stu-id="0a746-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="0a746-112">À partir de votre propre lac Common Data Service</span><span class="sxs-lookup"><span data-stu-id="0a746-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="0a746-113">Vous ne pouvez pas encore ajouter de données à partir de sources de données locales.</span><span class="sxs-lookup"><span data-stu-id="0a746-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="0a746-114">Évaluer les données ingérées</span><span class="sxs-lookup"><span data-stu-id="0a746-114">Review ingested data</span></span>

<span data-ttu-id="0a746-115">Vous avez accès au nom de chaque source de données ingérée, à son statut et à la dernière date d'actualisation des données pour cette source de données.</span><span class="sxs-lookup"><span data-stu-id="0a746-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="0a746-116">Vous pouvez trier la liste des sources de données par colonne.</span><span class="sxs-lookup"><span data-stu-id="0a746-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0a746-117">![Source de données ajoutée](media/configure-data-datasource-added.png "Source de données ajoutée")</span><span class="sxs-lookup"><span data-stu-id="0a746-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="0a746-118">État </span><span class="sxs-lookup"><span data-stu-id="0a746-118">Status</span></span>  |<span data-ttu-id="0a746-119">Description</span><span class="sxs-lookup"><span data-stu-id="0a746-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="0a746-120">Opération réussie</span><span class="sxs-lookup"><span data-stu-id="0a746-120">Successful</span></span>   |<span data-ttu-id="0a746-121">La source de données a été ingérée avec succès si une heure est mentionnée dans la colonne **Actualisé**.</span><span class="sxs-lookup"><span data-stu-id="0a746-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="0a746-122">Non démarré(e)</span><span class="sxs-lookup"><span data-stu-id="0a746-122">Not started</span></span>   |<span data-ttu-id="0a746-123">La source de données n'a pas encore de données ingérées ou est toujours en mode brouillon.</span><span class="sxs-lookup"><span data-stu-id="0a746-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="0a746-124">Actualisation</span><span class="sxs-lookup"><span data-stu-id="0a746-124">Refreshing</span></span>    |<span data-ttu-id="0a746-125">L’ingestion de données est en cours.</span><span class="sxs-lookup"><span data-stu-id="0a746-125">Data ingestion is in progress.</span></span> <span data-ttu-id="0a746-126">Vous pouvez annuler cette opération en sélectionnant **Arrêter l'actualisation** dans la colonne **Actions**.</span><span class="sxs-lookup"><span data-stu-id="0a746-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="0a746-127">L'arrêt de l'actualisation d'une source de données la ramènera à son dernier état d'actualisation.</span><span class="sxs-lookup"><span data-stu-id="0a746-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="0a746-128">Échoué</span><span class="sxs-lookup"><span data-stu-id="0a746-128">Failed</span></span>     |<span data-ttu-id="0a746-129">L'ingestion de données s'est heurtée à des erreurs.</span><span class="sxs-lookup"><span data-stu-id="0a746-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="0a746-130">Sélectionnez **Statut d'actualisation** pour examiner plus de détails sur le statut d'actualisation, notamment les détails de l'erreur et les mises à jour du processus en aval.</span><span class="sxs-lookup"><span data-stu-id="0a746-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="0a746-131">Le chargement des données peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="0a746-131">Loading data can take some time.</span></span> <span data-ttu-id="0a746-132">Après une actualisation réussie, les données ingérées peuvent être consultées à partir de la page **Entités**.</span><span class="sxs-lookup"><span data-stu-id="0a746-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="0a746-133">Pour plus d'informations, voir [Entités](entities.md).</span><span class="sxs-lookup"><span data-stu-id="0a746-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="0a746-134">Actualiser une source de données</span><span class="sxs-lookup"><span data-stu-id="0a746-134">Refresh a data source</span></span>

<span data-ttu-id="0a746-135">Les sources de données peuvent être actualisées selon un calendrier automatique ou actualisées manuellement à la demande.</span><span class="sxs-lookup"><span data-stu-id="0a746-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="0a746-136">Accédez à **Administration** > **Système** > [**Planification**](system.md#schedule-tab) pour configurer des actualisations programmées de toutes vos sources de données ingérées.</span><span class="sxs-lookup"><span data-stu-id="0a746-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="0a746-137">Pour actualiser une source de données à la demande, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0a746-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="0a746-138">Dans Audience Insights, accédez à **Données** > **Sources de données**</span><span class="sxs-lookup"><span data-stu-id="0a746-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="0a746-139">Sélectionnez les points de suspension verticaux en regard de la source de données que vous souhaitez actualiser, puis sélectionnez **Actualiser** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="0a746-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="0a746-140">La source de données est maintenant déclenchée pour une actualisation manuelle.</span><span class="sxs-lookup"><span data-stu-id="0a746-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="0a746-141">L'actualisation d'une source de données mettra à jour le schéma de l'entité ainsi que les données de toutes les entités spécifiées dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="0a746-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="0a746-142">Sélectionnez **Arrêtez l'actualisation** si vous souhaitez annuler une actualisation existante et rétablir le dernier statut d'actualisation de la source de données.</span><span class="sxs-lookup"><span data-stu-id="0a746-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="0a746-143">Supprimer une source de données</span><span class="sxs-lookup"><span data-stu-id="0a746-143">Delete a data source</span></span>

1. <span data-ttu-id="0a746-144">Dans Audience Insights, accédez à **Données** > **Sources de données**.</span><span class="sxs-lookup"><span data-stu-id="0a746-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="0a746-145">Sélectionnez les points de suspension en regard de la source de données que vous souhaitez supprimer et sélectionnez **Supprimer** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="0a746-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="0a746-146">Confirmez votre suppression.</span><span class="sxs-lookup"><span data-stu-id="0a746-146">Confirm your deletion.</span></span>
