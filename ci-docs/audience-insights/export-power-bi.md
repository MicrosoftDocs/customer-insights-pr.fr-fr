---
title: Connecteur Power BI
description: Découvrez comment utiliser le connecteur Dynamics 365 Customer Insights dans Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405641"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="c00bd-103">Connecteur pour Power BI (préversion)</span><span class="sxs-lookup"><span data-stu-id="c00bd-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="c00bd-104">Créez des visualisations pour vos données avec Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="c00bd-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="c00bd-105">Générez des informations supplémentaires et créez des rapports avec vos données client unifiées.</span><span class="sxs-lookup"><span data-stu-id="c00bd-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c00bd-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="c00bd-106">Prerequisites</span></span>

- <span data-ttu-id="c00bd-107">Vous disposez de profils clients unifiés.</span><span class="sxs-lookup"><span data-stu-id="c00bd-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="c00bd-108">La dernière version de [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) est installée sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="c00bd-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="c00bd-109">[En savoir plus sur Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="c00bd-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="c00bd-110">Configurer le connecteur pour Power BI</span><span class="sxs-lookup"><span data-stu-id="c00bd-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="c00bd-111">Dans Power BI Desktop, sélectionnez **Fichier** > **Obtenir les données**.</span><span class="sxs-lookup"><span data-stu-id="c00bd-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="c00bd-112">Sélectionnez **Afficher plus** et recherchez **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="c00bd-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="c00bd-113">Sélectionnez le résultat et sélectionnez **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="c00bd-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="c00bd-114">**Connectez-vous** à l’aide du compte d’organisation que vous utilisez pour Customer Insights et sélectionnez **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="c00bd-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="c00bd-115">Le compte que vous indiquez à cette étape est utilisé pour récupérer les données de Customer Insights et n'a pas besoin d'être le même que celui avec lequel vous êtes connecté à Power BI.</span><span class="sxs-lookup"><span data-stu-id="c00bd-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="c00bd-116">Pour réinitialiser le compte utilisé pour la récupération de données, ouvrez Power BI et accédez à **Fichier** > **Options** > **Paramètres** > **Paramètres de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="c00bd-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="c00bd-117">Dans la liste des sources de données, sélectionnez **Connexion à Dynamics 365 Customer Insights** et sélectionnez **Effacer les autorisations**.</span><span class="sxs-lookup"><span data-stu-id="c00bd-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="c00bd-118">La boîte de dialogue **Navigateur** affiche</span><span class="sxs-lookup"><span data-stu-id="c00bd-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="c00bd-119">la liste de tous les environnements auxquels vous pouvez accéder.</span><span class="sxs-lookup"><span data-stu-id="c00bd-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="c00bd-120">Développez un environnement et ouvrez l'un des dossiers (entités, mesures, segments, enrichissements).</span><span class="sxs-lookup"><span data-stu-id="c00bd-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="c00bd-121">Par exemple, ouvrez le dossier **Entités**, pour voir toutes les entités que vous pouvez importer.</span><span class="sxs-lookup"><span data-stu-id="c00bd-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="c00bd-122">![Connecteur Power BI Navigateur](media/power-bi-navigator.png "Connecteur Power BI Navigateur")</span><span class="sxs-lookup"><span data-stu-id="c00bd-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="c00bd-123">Activez les cases à cocher en regard des entités à inclure et **Charger**.</span><span class="sxs-lookup"><span data-stu-id="c00bd-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="c00bd-124">Vous pouvez sélectionner plusieurs entités depuis plusieurs environnements.</span><span class="sxs-lookup"><span data-stu-id="c00bd-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="c00bd-125">La boîte de dialogue de chargement s’affiche pendant le chargement de vos entités.</span><span class="sxs-lookup"><span data-stu-id="c00bd-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="c00bd-126">Une fois que toutes les entités sélectionnées sont chargées, vous pouvez utiliser les fonctionnalités de Power BI pour visualiser les données.</span><span class="sxs-lookup"><span data-stu-id="c00bd-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="c00bd-127">Jeux de données volumineux</span><span class="sxs-lookup"><span data-stu-id="c00bd-127">Large data sets</span></span>

<span data-ttu-id="c00bd-128">Le connecteur Customer Insights pour Power BI est conçu pour fonctionner avec des jeux de données contenant jusqu’à 1 million de profils client.</span><span class="sxs-lookup"><span data-stu-id="c00bd-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="c00bd-129">L’importation de jeux de données plus volumineux peut fonctionner, mais cela prend beaucoup de temps.</span><span class="sxs-lookup"><span data-stu-id="c00bd-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="c00bd-130">De plus, le processus peut s’exécuter dans un délai d’attente en raison des limites de Power BI.</span><span class="sxs-lookup"><span data-stu-id="c00bd-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="c00bd-131">Pour plus d’informations, voir [Power BI : Recommandations concernant les jeux de données volumineux](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="c00bd-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="c00bd-132">Utiliser un sous-ensemble de données</span><span class="sxs-lookup"><span data-stu-id="c00bd-132">Work with a subset of data</span></span>

<span data-ttu-id="c00bd-133">Envisagez d'utiliser un sous-ensemble de vos données.</span><span class="sxs-lookup"><span data-stu-id="c00bd-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="c00bd-134">Par exemple, vous pouvez créer des [segments](segments.md) au lieu d'exporter tous les enregistrements clients vers Power BI.</span><span class="sxs-lookup"><span data-stu-id="c00bd-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
