---
title: Ingestion de données en temps réel et limitations
description: Informations générales sur les fonctionnalités en temps réel dans les informations sur l’audience.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270277"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="52870-103">Ingestion de données en temps réel (préversion)</span><span class="sxs-lookup"><span data-stu-id="52870-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="52870-104">La fonctionnalité en temps quasi réel vous permet de voir, en quelques secondes, les dernières interactions de vos clients avec vos produits ou services.</span><span class="sxs-lookup"><span data-stu-id="52870-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="52870-105">Les [actualisations programmées](system.md#schedule-tab) comprennent un grand nombre d’enregistrements et plusieurs opérations complexes.</span><span class="sxs-lookup"><span data-stu-id="52870-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="52870-106">Tout d’abord, les données sont extraites de la source de données.</span><span class="sxs-lookup"><span data-stu-id="52870-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="52870-107">Ensuite, les données sont unifiées, puis enrichies avec des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="52870-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="52870-108">Chaque exécution de ce processus peut prendre quelques minutes à plusieurs heures.</span><span class="sxs-lookup"><span data-stu-id="52870-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="52870-109">La fonctionnalité en temps réel fournit des données immédiatement pour la consommation, jusqu’à ce que l’actualisation programmée suivante extrait ces données de la source de données.</span><span class="sxs-lookup"><span data-stu-id="52870-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="52870-110">Les mises à jour en temps réel ont un délai d’expiration au-delà duquel elles ne remplacent plus la valeur de la source de données :</span><span class="sxs-lookup"><span data-stu-id="52870-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="52870-111">Les mises à jour du profil seront conservées pendant 4 heures</span><span class="sxs-lookup"><span data-stu-id="52870-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="52870-112">Les activités seront conservées pendant 30 jours</span><span class="sxs-lookup"><span data-stu-id="52870-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="52870-113">Ces valeurs sont des paramètres d’appel API que vous pouvez modifier.</span><span class="sxs-lookup"><span data-stu-id="52870-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="52870-114">Elles visent à garantir que vos données sources demeurent votre source de référence.</span><span class="sxs-lookup"><span data-stu-id="52870-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="52870-115">Si vous souhaitez que les mises à jour en temps réel soient conservées plus longtemps, vous devez les ajouter à une source de données afin qu’elles soient extraites lors de la prochaine actualisation programmée.</span><span class="sxs-lookup"><span data-stu-id="52870-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="52870-116">Mise à jour en temps réel des champs de profil client unifié</span><span class="sxs-lookup"><span data-stu-id="52870-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="52870-117">Les profils mis à jour s’afficheront dans la vue de la carte client, ou dans toute autre visualisation, en quelques secondes.</span><span class="sxs-lookup"><span data-stu-id="52870-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="52870-118">Étant donné que les opérations en temps réel ont lieu après l’unification des données, elles ne s’appliquent qu’aux profils client unifiés.</span><span class="sxs-lookup"><span data-stu-id="52870-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="52870-119">Par conséquent, les modifications de profil en temps réel ne mettront pas à jour les mesures, l’appartenance du segment ou les enrichissements.</span><span class="sxs-lookup"><span data-stu-id="52870-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="52870-120">Limitations</span><span class="sxs-lookup"><span data-stu-id="52870-120">Limitations</span></span>

- <span data-ttu-id="52870-121">Vous pouvez mettre à jour les profils client, mais vous ne pouvez pas les créer ni les supprimer.</span><span class="sxs-lookup"><span data-stu-id="52870-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="52870-122">L’exportation des mises à jour en temps réel vers des systèmes externes, comme Power BI, n’est pas possible pour le moment.</span><span class="sxs-lookup"><span data-stu-id="52870-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="52870-123">Création d’activités en temps réel</span><span class="sxs-lookup"><span data-stu-id="52870-123">Real-time creation of activities</span></span>

<span data-ttu-id="52870-124">L’API en temps réel vous permet de publier une nouvelle activité de votre système source (un enregistrement source individuel) vers un profil client unifié.</span><span class="sxs-lookup"><span data-stu-id="52870-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="52870-125">La nouvelle activité est disponible en tant qu’activité unifiée dans la chronologie de ce profil client unifié en quelques secondes.</span><span class="sxs-lookup"><span data-stu-id="52870-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="52870-126">Vous pouvez voir la chronologie dans la vue de la carte client ou dans toute autre intégration de chronologie que vous avez configurée.</span><span class="sxs-lookup"><span data-stu-id="52870-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="52870-127">Les activités sont immuables.</span><span class="sxs-lookup"><span data-stu-id="52870-127">Activities are immutable.</span></span> <span data-ttu-id="52870-128">Elles ne changent pas une fois créées.</span><span class="sxs-lookup"><span data-stu-id="52870-128">They don't change once created.</span></span>
> - <span data-ttu-id="52870-129">Pour le moment, les segments et les mesures ne sont pas mis à jour en fonction de la nouvelle activité.</span><span class="sxs-lookup"><span data-stu-id="52870-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="52870-130">Les activités ajoutées uniquement via l’API en temps réel ne font pas partie des exportations et ne s’affichent pas dans PowerBI.</span><span class="sxs-lookup"><span data-stu-id="52870-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="52870-131">Vous pouvez vous connecter à l’API en temps réel de deux façons :</span><span class="sxs-lookup"><span data-stu-id="52870-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="52870-132">[indirectement](#connect-via-the-dynamics-365-customer-insights-connector), en utilisant le connecteur [Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="52870-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="52870-133">[directement](#connect-directly-to-the-real-time-api), avec un code</span><span class="sxs-lookup"><span data-stu-id="52870-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="52870-134">Les deux façons partagent les conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="52870-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="52870-135">Un environnement Customer Insights</span><span class="sxs-lookup"><span data-stu-id="52870-135">A Customer Insights environment</span></span>
- <span data-ttu-id="52870-136">Profils client unifiés</span><span class="sxs-lookup"><span data-stu-id="52870-136">Unified customer profiles</span></span>
- <span data-ttu-id="52870-137">Activités configurées et exécutées</span><span class="sxs-lookup"><span data-stu-id="52870-137">Activities configured and run</span></span>
- <span data-ttu-id="52870-138">Autorisations Contributeur ou Administrateur pour authentifier votre compte</span><span class="sxs-lookup"><span data-stu-id="52870-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="52870-139">Connexion via le connecteur Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="52870-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="52870-140">L’API en temps réel peut ingérer des données à partir d’un connecteur dédié Power Platform, le [connecteur Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/), sans qu’il soit nécessaire d’écrire et de déployer du code.</span><span class="sxs-lookup"><span data-stu-id="52870-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="52870-141">Le connecteur peut effectuer les mêmes actions en temps réel que l’API.</span><span class="sxs-lookup"><span data-stu-id="52870-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="52870-142">Une licence valide est nécessaire pour les connecteurs premium.</span><span class="sxs-lookup"><span data-stu-id="52870-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="52870-143">Pour plus d’informations, voir [FAQ sur les licences Power Apps et Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="52870-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="52870-144">Power Platform [Power Apps et/ou Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="52870-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="52870-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="52870-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="52870-146">Pour plus d’informations sur la création de flux, consultez la [documentation de Power Automate](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="52870-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="52870-147">Connexion directe à l’API en temps réel</span><span class="sxs-lookup"><span data-stu-id="52870-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="52870-148">Vous pouvez utiliser les fonctionnalités en temps réel en créant votre propre pipeline et en le connectant directement à l’API en temps réel.</span><span class="sxs-lookup"><span data-stu-id="52870-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="52870-149">Vous pouvez publier une activité au format de votre système source ou au format UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="52870-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="52870-150">Procurez-vous le format en effectuant un appel d’API vers /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="52870-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="52870-151">Les détails de cette API, notamment les paramètres et les réponses, sont disponibles dans la section **EntityData** du [Guide de référence des API de Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="52870-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="52870-152">Pour plus d’informations, consultez [Utiliser les API de Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="52870-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="52870-153">Comprendre votre utilisation en temps réel avec la télémétrie</span><span class="sxs-lookup"><span data-stu-id="52870-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="52870-154">Obtenez une vue d’ensemble du volume de demandes adressées à l’API en temps réel ainsi que des informations sur les problèmes que le système peut rencontrer.</span><span class="sxs-lookup"><span data-stu-id="52870-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="52870-155">Vous pouvez [accéder à la télémétrie en temps réel](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="52870-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]