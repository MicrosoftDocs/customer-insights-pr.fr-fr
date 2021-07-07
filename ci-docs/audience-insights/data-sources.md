---
title: Utiliser des sources de données pour ingérer des données
description: Découvrez comment importer des données depuis des sources diverses.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304693"
---
# <a name="data-sources-overview"></a><span data-ttu-id="afeb9-103">Vue d’ensemble des sources de données</span><span class="sxs-lookup"><span data-stu-id="afeb9-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="afeb9-104">La fonctionnalité d’informations sur l’audience de Dynamics 365 Customer Insights se connecte aux données d’un large éventail de sources.</span><span class="sxs-lookup"><span data-stu-id="afeb9-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="afeb9-105">La connexion à une source de données est souvent appelée processus d’*ingestion de données*.</span><span class="sxs-lookup"><span data-stu-id="afeb9-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="afeb9-106">Après avoir ingéré les données, vous pouvez les [unifier](data-unification.md) et agir dessus.</span><span class="sxs-lookup"><span data-stu-id="afeb9-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="afeb9-107">Ajouter une source de données</span><span class="sxs-lookup"><span data-stu-id="afeb9-107">Add a data source</span></span>

<span data-ttu-id="afeb9-108">Reportez-vous aux articles détaillés sur la façon d’ajouter une source de données, selon l’option que vous choisissez.</span><span class="sxs-lookup"><span data-stu-id="afeb9-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="afeb9-109">Vous pouvez ajouter une source de données de trois manières principales :</span><span class="sxs-lookup"><span data-stu-id="afeb9-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="afeb9-110">Grâce à des dizaines de connecteurs Power Query</span><span class="sxs-lookup"><span data-stu-id="afeb9-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="afeb9-111">À partir d’un dossier Common Data Model</span><span class="sxs-lookup"><span data-stu-id="afeb9-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="afeb9-112">À partir de votre propre lac Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="afeb9-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="afeb9-113">Ajouter des données de sources de données locales</span><span class="sxs-lookup"><span data-stu-id="afeb9-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="afeb9-114">L’ingestion de données à partir de sources de données locales dans Audience Insights est prise en charge en fonction des flux de données Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="afeb9-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="afeb9-115">Les flux de données peuvent être activés dans Customer Insights en [fournissant l’URL de l’environnement Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) lors de la configuration de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="afeb9-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="afeb9-116">Les sources de données créées après l’association d’un environnement Dataverse à Customer Insights utiliseront les [flux de données Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) par défaut.</span><span class="sxs-lookup"><span data-stu-id="afeb9-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="afeb9-117">Les flux de données prennent en charge la connectivité locale à l’aide de la passerelle de données.</span><span class="sxs-lookup"><span data-stu-id="afeb9-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="afeb9-118">Supprimez et recréez les sources de données qui existaient avant l’association d’un environnement Dataverse pour [utiliser les passerelles de données locales](/data-integration/gateway/service-gateway-app.md).</span><span class="sxs-lookup"><span data-stu-id="afeb9-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="afeb9-119">Les passerelles de données d’un environnement Power BI ou Power Apps existant seront visibles et vous pourrez les réutiliser dans Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="afeb9-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="afeb9-120">La page des sources de données affiche des liens pour accéder à l’environnement Microsoft Power Platform dans lequel vous pouvez afficher et configurer les passerelles de données locales.</span><span class="sxs-lookup"><span data-stu-id="afeb9-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="afeb9-121">Évaluer les données ingérées</span><span class="sxs-lookup"><span data-stu-id="afeb9-121">Review ingested data</span></span>

<span data-ttu-id="afeb9-122">Vous avez accès au nom de chaque source de données ingérée, à son statut et à la dernière date d’actualisation des données pour cette source de données.</span><span class="sxs-lookup"><span data-stu-id="afeb9-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="afeb9-123">Vous pouvez trier la liste des sources de données par colonne.</span><span class="sxs-lookup"><span data-stu-id="afeb9-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="afeb9-124">![Source de données ajoutée](media/configure-data-datasource-added.png "Source de données ajoutée")</span><span class="sxs-lookup"><span data-stu-id="afeb9-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="afeb9-125">Statut</span><span class="sxs-lookup"><span data-stu-id="afeb9-125">Status</span></span>  |<span data-ttu-id="afeb9-126">Description</span><span class="sxs-lookup"><span data-stu-id="afeb9-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="afeb9-127">Opération réussie</span><span class="sxs-lookup"><span data-stu-id="afeb9-127">Successful</span></span>   |<span data-ttu-id="afeb9-128">La source de données a été ingérée avec succès si une heure est mentionnée dans la colonne **Actualisé**.</span><span class="sxs-lookup"><span data-stu-id="afeb9-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="afeb9-129">Non démarré(e)</span><span class="sxs-lookup"><span data-stu-id="afeb9-129">Not started</span></span>   |<span data-ttu-id="afeb9-130">La source de données n’a pas encore de données ingérées ou est toujours en mode brouillon.</span><span class="sxs-lookup"><span data-stu-id="afeb9-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="afeb9-131">Actualisation</span><span class="sxs-lookup"><span data-stu-id="afeb9-131">Refreshing</span></span>    |<span data-ttu-id="afeb9-132">L’ingestion de données est en cours.</span><span class="sxs-lookup"><span data-stu-id="afeb9-132">Data ingestion is in progress.</span></span> <span data-ttu-id="afeb9-133">Vous pouvez annuler cette opération en sélectionnant **Arrêter l’actualisation** dans la colonne **Actions**.</span><span class="sxs-lookup"><span data-stu-id="afeb9-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="afeb9-134">L’arrêt de l’actualisation d’une source de données la ramène à son dernier état d’actualisation.</span><span class="sxs-lookup"><span data-stu-id="afeb9-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="afeb9-135">Échoué</span><span class="sxs-lookup"><span data-stu-id="afeb9-135">Failed</span></span>     |<span data-ttu-id="afeb9-136">L’ingestion de données s’est heurtée à des erreurs.</span><span class="sxs-lookup"><span data-stu-id="afeb9-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="afeb9-137">Sélectionnez la valeur dans la colonne **Statut** de n’importe quelle source de données pour examiner plus de détails.</span><span class="sxs-lookup"><span data-stu-id="afeb9-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="afeb9-138">Dans le volet **Détails de la progression**, développez **Sources de données**.</span><span class="sxs-lookup"><span data-stu-id="afeb9-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="afeb9-139">Sélectionnez **Afficher les détails** pour obtenir plus d’informations sur le statut d’actualisation, notamment les détails de l’erreur et les mises à jour du processus en aval.</span><span class="sxs-lookup"><span data-stu-id="afeb9-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="afeb9-140">Le chargement des données peut prendre du temps.</span><span class="sxs-lookup"><span data-stu-id="afeb9-140">Loading data can take time.</span></span> <span data-ttu-id="afeb9-141">Après une actualisation réussie, les données ingérées peuvent être consultées à partir de la page **Entités**.</span><span class="sxs-lookup"><span data-stu-id="afeb9-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="afeb9-142">Pour plus d’informations, voir [Entités](entities.md).</span><span class="sxs-lookup"><span data-stu-id="afeb9-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="afeb9-143">Actualiser une source de données</span><span class="sxs-lookup"><span data-stu-id="afeb9-143">Refresh a data source</span></span>

<span data-ttu-id="afeb9-144">Les sources de données peuvent être actualisées selon un calendrier automatique ou actualisées manuellement à la demande.</span><span class="sxs-lookup"><span data-stu-id="afeb9-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="afeb9-145">Accédez à **Administration** > **Système** > [**Planification**](system.md#schedule-tab) pour configurer des actualisations programmées de toutes vos sources de données ingérées.</span><span class="sxs-lookup"><span data-stu-id="afeb9-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="afeb9-146">Pour actualiser une source de données à la demande, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="afeb9-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="afeb9-147">Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.</span><span class="sxs-lookup"><span data-stu-id="afeb9-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="afeb9-148">Sélectionnez les points de suspension verticaux en regard de la source de données que vous souhaitez actualiser et sélectionnez **Actualiser** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="afeb9-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="afeb9-149">La source de données est maintenant déclenchée pour une actualisation manuelle.</span><span class="sxs-lookup"><span data-stu-id="afeb9-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="afeb9-150">Si vous actualisez une source de données, à la fois le schéma de l’entité et les données seront mis à jour pour toutes les entités spécifiées dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="afeb9-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="afeb9-151">Sélectionnez **Arrêtez l’actualisation** si vous souhaitez annuler une actualisation existante et rétablir le dernier statut d’actualisation de la source de données.</span><span class="sxs-lookup"><span data-stu-id="afeb9-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="afeb9-152">Supprimer une source de données</span><span class="sxs-lookup"><span data-stu-id="afeb9-152">Delete a data source</span></span>

1. <span data-ttu-id="afeb9-153">Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.</span><span class="sxs-lookup"><span data-stu-id="afeb9-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="afeb9-154">Sélectionnez les points de suspension verticaux en regard de la source de données que vous souhaitez supprimer et sélectionnez **Supprimer** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="afeb9-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="afeb9-155">Confirmez votre suppression.</span><span class="sxs-lookup"><span data-stu-id="afeb9-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
