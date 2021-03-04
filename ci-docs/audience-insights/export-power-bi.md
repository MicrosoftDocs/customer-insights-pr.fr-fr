---
title: Connecteur Power BI
description: Découvrez comment utiliser le connecteur Dynamics 365 Customer Insights dans Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477085"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="354d6-103">Connecteur pour Power BI (préversion)</span><span class="sxs-lookup"><span data-stu-id="354d6-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="354d6-104">Créez des visualisations pour vos données avec Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="354d6-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="354d6-105">Générez des informations supplémentaires et créez des rapports avec vos données client unifiées.</span><span class="sxs-lookup"><span data-stu-id="354d6-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="354d6-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="354d6-106">Prerequisites</span></span>

- <span data-ttu-id="354d6-107">Vous disposez de profils clients unifiés.</span><span class="sxs-lookup"><span data-stu-id="354d6-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="354d6-108">La dernière version de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) est installée sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="354d6-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="354d6-109">[En savoir plus sur Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="354d6-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="354d6-110">Configurer le connecteur pour Power BI</span><span class="sxs-lookup"><span data-stu-id="354d6-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="354d6-111">Dans Power BI Desktop, sélectionnez **Fichier** > **Obtenir les données**.</span><span class="sxs-lookup"><span data-stu-id="354d6-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="354d6-112">Sélectionnez **Afficher plus** et recherchez **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="354d6-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="354d6-113">Cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="354d6-113">Select **Connect**.</span></span>

1. <span data-ttu-id="354d6-114">**Connectez-vous** à l’aide du compte d’organisation que vous utilisez pour Customer Insights et sélectionnez **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="354d6-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="354d6-115">Le compte que vous indiquez à cette étape est utilisé pour récupérer les données de Customer Insights et n’a pas besoin d’être le même que celui avec lequel vous êtes connecté à Power BI.</span><span class="sxs-lookup"><span data-stu-id="354d6-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="354d6-116">Pour réinitialiser le compte utilisé pour la récupération de données, ouvrez Power BI et accédez à **Fichier** > **Options** > **Paramètres** > **Paramètres de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="354d6-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="354d6-117">Dans la liste des sources de données, sélectionnez **Connexion à Dynamics 365 Customer Insights** et sélectionnez **Effacer les autorisations**.</span><span class="sxs-lookup"><span data-stu-id="354d6-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="354d6-118">La boîte de dialogue **Navigateur** affiche</span><span class="sxs-lookup"><span data-stu-id="354d6-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="354d6-119">la liste de tous les environnements auxquels vous pouvez accéder.</span><span class="sxs-lookup"><span data-stu-id="354d6-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="354d6-120">Développez un environnement et ouvrez l’un des dossiers (entités, mesures, segments, enrichissements).</span><span class="sxs-lookup"><span data-stu-id="354d6-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="354d6-121">Par exemple, ouvrez le dossier **Entités**, pour voir toutes les entités que vous pouvez importer.</span><span class="sxs-lookup"><span data-stu-id="354d6-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="354d6-122">![Connecteur Power BI Navigateur](media/power-bi-navigator.png "Connecteur Power BI Navigateur")</span><span class="sxs-lookup"><span data-stu-id="354d6-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="354d6-123">Activez les cases à cocher en regard des entités à inclure et **Charger**.</span><span class="sxs-lookup"><span data-stu-id="354d6-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="354d6-124">Vous pouvez sélectionner plusieurs entités depuis plusieurs environnements.</span><span class="sxs-lookup"><span data-stu-id="354d6-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="354d6-125">La boîte de dialogue de chargement s’affiche pendant le chargement de vos entités.</span><span class="sxs-lookup"><span data-stu-id="354d6-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="354d6-126">Une fois que toutes les entités sélectionnées sont chargées, vous pouvez utiliser les fonctionnalités de Power BI pour visualiser les données.</span><span class="sxs-lookup"><span data-stu-id="354d6-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="354d6-127">Jeux de données volumineux</span><span class="sxs-lookup"><span data-stu-id="354d6-127">Large data sets</span></span>

<span data-ttu-id="354d6-128">Le connecteur Customer Insights pour Power BI est conçu pour fonctionner avec des jeux de données contenant jusqu’à 1 million de profils client.</span><span class="sxs-lookup"><span data-stu-id="354d6-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="354d6-129">L’importation de jeux de données plus volumineux peut fonctionner, mais cela prend beaucoup de temps.</span><span class="sxs-lookup"><span data-stu-id="354d6-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="354d6-130">De plus, le processus peut s’exécuter dans un délai d’attente en raison des limites de Power BI.</span><span class="sxs-lookup"><span data-stu-id="354d6-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="354d6-131">Pour plus d’informations, voir [Power BI : Recommandations concernant les jeux de données volumineux](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="354d6-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="354d6-132">Utiliser un sous-ensemble de données</span><span class="sxs-lookup"><span data-stu-id="354d6-132">Work with a subset of data</span></span>

<span data-ttu-id="354d6-133">Envisagez d’utiliser un sous-ensemble de vos données.</span><span class="sxs-lookup"><span data-stu-id="354d6-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="354d6-134">Par exemple, vous pouvez créer des [segments](segments.md) au lieu d’exporter tous les enregistrements clients vers Power BI.</span><span class="sxs-lookup"><span data-stu-id="354d6-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="354d6-135">Dépannage</span><span class="sxs-lookup"><span data-stu-id="354d6-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="354d6-136">L’environnement Customer Insights ne s’affiche pas dans Power BI</span><span class="sxs-lookup"><span data-stu-id="354d6-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="354d6-137">Les environnements qui ont plus d’une [relation](relationships.md) définie entre deux entités identiques dans les informations sur l’audience ne seront pas disponibles dans le connecteur Power BI.</span><span class="sxs-lookup"><span data-stu-id="354d6-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="354d6-138">Vous pouvez identifier et supprimer les relations en double.</span><span class="sxs-lookup"><span data-stu-id="354d6-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="354d6-139">Dans les informations sur l’audience, accédez à **Données** > **Relations** sur l’environnement dans lequel vous manquez Power BI.</span><span class="sxs-lookup"><span data-stu-id="354d6-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="354d6-140">Identifiez les relations dupliqués :</span><span class="sxs-lookup"><span data-stu-id="354d6-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="354d6-141">Vérifiez si plusieurs relations sont définies entre les deux mêmes entités.</span><span class="sxs-lookup"><span data-stu-id="354d6-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="354d6-142">Vérifiez s’il existe une relation créée entre deux entités qui sont toutes deux incluses dans le processus d’unification.</span><span class="sxs-lookup"><span data-stu-id="354d6-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="354d6-143">Il existe une relation implicite définie entre toutes les entités incluses dans le processus d’unification.</span><span class="sxs-lookup"><span data-stu-id="354d6-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="354d6-144">Supprimez toutes les relations en double identifiées.</span><span class="sxs-lookup"><span data-stu-id="354d6-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="354d6-145">Après avoir supprimé les relations dupliquées, essayez de reconfigurer le connecteur Power BI.</span><span class="sxs-lookup"><span data-stu-id="354d6-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="354d6-146">L’environnement devrait être disponible dès maintenant.</span><span class="sxs-lookup"><span data-stu-id="354d6-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

