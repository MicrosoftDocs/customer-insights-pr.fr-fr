---
title: Tâches partagées pour les scénarios prédiction
description: Apprenez à gérer, dépanner et affiner les prédictions.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315875"
---
# <a name="manage-predictions"></a><span data-ttu-id="d1976-103">Gérer les prédictions</span><span class="sxs-lookup"><span data-stu-id="d1976-103">Manage predictions</span></span>

<span data-ttu-id="d1976-104">Cet article traite de certaines tâches partagées par la plupart des scénarios de prédiction.</span><span class="sxs-lookup"><span data-stu-id="d1976-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="d1976-105">Résoudre les problèmes liés à un échec de prédiction</span><span class="sxs-lookup"><span data-stu-id="d1976-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="d1976-106">Accédez à **Intelligence** > **Prédictions** et sélectionnez l’onglet **Mes prédictions**.</span><span class="sxs-lookup"><span data-stu-id="d1976-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d1976-107">Sélectionnez les points de suspension verticaux en regard de la prédiction pour laquelle vous souhaitez afficher les journaux d’erreurs.</span><span class="sxs-lookup"><span data-stu-id="d1976-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="d1976-108">Sélectionnez **Journaux**.</span><span class="sxs-lookup"><span data-stu-id="d1976-108">Select **Logs**.</span></span>

1. <span data-ttu-id="d1976-109">Passez toutes les erreurs en revue.</span><span class="sxs-lookup"><span data-stu-id="d1976-109">Review all the errors.</span></span> <span data-ttu-id="d1976-110">Plusieurs types d’erreurs peuvent survenir et décrivent la condition à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="d1976-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="d1976-111">Par exemple, une erreur pour laquelle il n’y a pas suffisamment de données à prévoir avec précision est généralement résolue en chargeant des données supplémentaires dans Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d1976-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="d1976-112">Rapport d’utilisation des données d’entrée</span><span class="sxs-lookup"><span data-stu-id="d1976-112">Input data usability report</span></span>

<span data-ttu-id="d1976-113">Le rapport d'utilisation des données d'entrée fournit une vue consolidée des erreurs et des avertissements que vos prédictions prêtes à l'emploi peuvent générer.</span><span class="sxs-lookup"><span data-stu-id="d1976-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="d1976-114">Il donne également des recommandations sur la manière d'améliorer les performances du modèle.</span><span class="sxs-lookup"><span data-stu-id="d1976-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="d1976-115">Le rapport est disponible une fois qu'un modèle a terminé son processus d'entraînement.</span><span class="sxs-lookup"><span data-stu-id="d1976-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="d1976-116">Il est créé pour chaque modèle séparément, qu'il soit terminé avec succès ou non.</span><span class="sxs-lookup"><span data-stu-id="d1976-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="d1976-117">Afficher le rapport d’utilisation des données d’entrée</span><span class="sxs-lookup"><span data-stu-id="d1976-117">View the input data usability report</span></span>

<span data-ttu-id="d1976-118">Une fois qu'un modèle prêt à l'emploi a terminé son étape d'entraînement, affichez le rapport :</span><span class="sxs-lookup"><span data-stu-id="d1976-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="d1976-119">Sélectionnez les points de suspension à côté du nom du modèle et choisissez **Rapport d'utilisation des données d'entrée**.</span><span class="sxs-lookup"><span data-stu-id="d1976-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="d1976-120">Sélectionnez le statut d'un modèle et sélectionnez **Voir le rapport d’utilisation des données d’entrée** dans le volet latéral.</span><span class="sxs-lookup"><span data-stu-id="d1976-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="d1976-121">Sélectionnez l'un des modèles dans la liste et sélectionnez **Rapport d'utilisation des données d'entrée** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="d1976-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="d1976-122">Ouvrez la page de résultats du modèle et sélectionnez **Rapport d'utilisation des données d'entrée** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="d1976-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="d1976-123">Information dans le rapport d’utilisation des données d’entrée</span><span class="sxs-lookup"><span data-stu-id="d1976-123">Information in the input data usability report</span></span>

<span data-ttu-id="d1976-124">Les colonnes suivantes du rapport contiennent des informations utiles pour améliorer les données du modèle.</span><span class="sxs-lookup"><span data-stu-id="d1976-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemple de rapport d'utilisation des données d'entrée montrant un tableau avec des erreurs, des avertissements et des recommandations.":::

- <span data-ttu-id="d1976-126">Nom : nom descriptif de l'erreur, de l'avertissement ou de la recommandation.</span><span class="sxs-lookup"><span data-stu-id="d1976-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="d1976-127">Étape : phase, entraînement ou score du modèle auquel l'information fait référence.</span><span class="sxs-lookup"><span data-stu-id="d1976-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="d1976-128">État : gravité de l'information (erreur, avertissement, recommandation).</span><span class="sxs-lookup"><span data-stu-id="d1976-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="d1976-129">Nom de la colonne : colonne dans une entité qui doit être modifiée pour améliorer les performances du modèle.</span><span class="sxs-lookup"><span data-stu-id="d1976-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="d1976-130">Nom de l'entité : nom de l'entité qui doit être modifiée pour améliorer les performances du modèle.</span><span class="sxs-lookup"><span data-stu-id="d1976-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="d1976-131">Détails : détails sur l'erreur, l'avertissement ou la recommandation.</span><span class="sxs-lookup"><span data-stu-id="d1976-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="d1976-132">Actualiser une prédiction</span><span class="sxs-lookup"><span data-stu-id="d1976-132">Refresh a prediction</span></span>

<span data-ttu-id="d1976-133">Les prédictions seront automatiquement actualisées sur le même paramètre [planifier vos actualisations de données](system.md#schedule-tab) comme configuré dans les paramètres.</span><span class="sxs-lookup"><span data-stu-id="d1976-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="d1976-134">Vous pouvez également les actualiser manuellement.</span><span class="sxs-lookup"><span data-stu-id="d1976-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="d1976-135">Accédez à **Intelligence** > **Prédictions** et sélectionnez l’onglet **Mes prédictions**.</span><span class="sxs-lookup"><span data-stu-id="d1976-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d1976-136">Sélectionnez les ellipses verticales à côté de la prédiction que vous souhaitez actualiser.</span><span class="sxs-lookup"><span data-stu-id="d1976-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="d1976-137">Cliquez sur **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="d1976-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="d1976-138">Supprimer une prédiction</span><span class="sxs-lookup"><span data-stu-id="d1976-138">Delete a prediction</span></span>

<span data-ttu-id="d1976-139">La suppression d’une prédiction entraîne également la suppression de son entité de sortie.</span><span class="sxs-lookup"><span data-stu-id="d1976-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="d1976-140">Accédez à **Intelligence** > **Prédictions** et sélectionnez l’onglet **Mes prédictions**.</span><span class="sxs-lookup"><span data-stu-id="d1976-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d1976-141">Sélectionnez les ellipses verticales à côté de la prédiction que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="d1976-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="d1976-142">Sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="d1976-142">Select **Delete**.</span></span>
