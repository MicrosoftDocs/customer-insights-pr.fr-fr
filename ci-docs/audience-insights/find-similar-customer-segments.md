---
title: Trouver des clients similaires avec l’IA
description: Recherchez des segments de client similaires grâce à l’intelligence artificielle.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: b9b2e7fa862b595c6a364a7208e42295b4f9df83
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268867"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="05614-103">Clients similaires (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="05614-103">Similar Customers (preview)</span></span>

<span data-ttu-id="05614-104">Cette fonctionnalité vous permet de trouver des clients similaires dans votre clientèle en utilisant l’intelligence artificielle.</span><span class="sxs-lookup"><span data-stu-id="05614-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="05614-105">Vous devez avoir créé au moins un segment pour utiliser cette fonction.</span><span class="sxs-lookup"><span data-stu-id="05614-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="05614-106">L’élargissement des critères d’un segment existant permet de trouver des clients similaires à ce segment.</span><span class="sxs-lookup"><span data-stu-id="05614-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="05614-107">*Rechercher des clients similaires* utilise des moyens automatisés pour évaluer les données et faire des prévisions sur la base de ces données, et a donc la capacité d’être utilisé comme méthode de profilage, tel que ce terme est défini par le Règlement général sur la protection des données (« RGPD »).</span><span class="sxs-lookup"><span data-stu-id="05614-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="05614-108">L’utilisation par le client de cette fonctionnalité pour traiter des données peut être soumise au RGPD ou à d’autres lois ou réglementations.</span><span class="sxs-lookup"><span data-stu-id="05614-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="05614-109">Vous êtes tenu de vous assurer que votre utilisation de Dynamics 365 Customer Insights, notamment les prédictions, est conforme à toutes les lois et réglementations applicables, notamment les lois relatives à la confidentialité, aux données personnelles, aux données biométriques, à la protection des données et à la confidentialité des communications.</span><span class="sxs-lookup"><span data-stu-id="05614-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="05614-110">Rechercher les clients similaires</span><span class="sxs-lookup"><span data-stu-id="05614-110">Finding similar customers</span></span>

1. <span data-ttu-id="05614-111">Dans les informations sur l’audience, accédez à **Segments** et sélectionnez le segment sur lequel vous souhaitez baser votre nouveau segment.</span><span class="sxs-lookup"><span data-stu-id="05614-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="05614-112">C’est votre *segment source*.</span><span class="sxs-lookup"><span data-stu-id="05614-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="05614-113">Dans la barre d’actions, sélectionnez **Rechercher des clients similaires**.</span><span class="sxs-lookup"><span data-stu-id="05614-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="05614-114">Vérifiez le nom suggéré pour votre nouveau segment et modifiez-le si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="05614-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="05614-115">Passez en revue les champs qui définissent votre nouveau segment.</span><span class="sxs-lookup"><span data-stu-id="05614-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="05614-116">Ces champs définissent la base sur laquelle le système tentera de trouver des clients similaires à votre segment source.</span><span class="sxs-lookup"><span data-stu-id="05614-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="05614-117">Le système sélectionnera les champs recommandés par défaut.</span><span class="sxs-lookup"><span data-stu-id="05614-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="05614-118">Les champs susceptibles de réduire considérablement les performances du modèle sont automatiquement exclus :</span><span class="sxs-lookup"><span data-stu-id="05614-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="05614-119">Champs avec les types de données suivants : StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="05614-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="05614-120">Champs avec une cardinalité (le nombre d’éléments dans un champ) inférieure à 2 ou supérieure à 30</span><span class="sxs-lookup"><span data-stu-id="05614-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="05614-121">Choisissez si vous souhaitez inclure **Tous les clients** ou seulement des clients dans un **Segment existant spécifique** dans votre nouveau segment.</span><span class="sxs-lookup"><span data-stu-id="05614-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="05614-122">Excluez les clients dans votre segment source en sélectionnant la case **Exclure tout le monde dans le segment source**.</span><span class="sxs-lookup"><span data-stu-id="05614-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="05614-123">Par défaut, le système suggère d’inclure seulement 20 % de la taille cible audience dans votre sortie.</span><span class="sxs-lookup"><span data-stu-id="05614-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="05614-124">Modifiez ce seuil si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="05614-124">Edit this threshold as needed.</span></span> <span data-ttu-id="05614-125">L’augmentation du seuil réduira la précision.</span><span class="sxs-lookup"><span data-stu-id="05614-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="05614-126">Sélectionnez **Exécuter** en bas de la page pour démarrer une tâche de classification binaire (une méthode de Machine Learning) qui analyse le jeu de données.</span><span class="sxs-lookup"><span data-stu-id="05614-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="05614-127">Voir le segment similaire</span><span class="sxs-lookup"><span data-stu-id="05614-127">View the similar segment</span></span>

<span data-ttu-id="05614-128">Après avoir traité le segment similaire, vous rechercherez le nouveau segment répertorié sur la page **Segments**.</span><span class="sxs-lookup"><span data-stu-id="05614-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="05614-129">![Segment des clients similaires](media/expanded-segment.png "Segment des clients similaires")</span><span class="sxs-lookup"><span data-stu-id="05614-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="05614-130">Sélectionnez **Vue** dans la barre d’action pour ouvrir le détail du segment.</span><span class="sxs-lookup"><span data-stu-id="05614-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="05614-131">Cette vue contient des informations sur la distribution des résultats sur les [scores de similarité](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="05614-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="05614-132">Vous trouverez également les valeurs des scores de similarité dans l’**Aperçu des membres du segment**.</span><span class="sxs-lookup"><span data-stu-id="05614-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="05614-133">Utiliser la sortie d’un segment similaire</span><span class="sxs-lookup"><span data-stu-id="05614-133">Use the output of a similar segment</span></span>

<span data-ttu-id="05614-134">Vous pouvez [utiliser le résultat d’un segment similaire](segments.md) comme vous le faites avec d’autres segments.</span><span class="sxs-lookup"><span data-stu-id="05614-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="05614-135">Par exemple, exportez le segment ou créez une mesure.</span><span class="sxs-lookup"><span data-stu-id="05614-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="05614-136">Actualiser et modifier un segment similaire</span><span class="sxs-lookup"><span data-stu-id="05614-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="05614-137">Pour actualiser un segment similaire, sélectionnez-le sur la page **Segments** et sélectionnez **Actualiser** dans la barre d’actions.</span><span class="sxs-lookup"><span data-stu-id="05614-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="05614-138">La modification d’un segment similaire retraitera vos données.</span><span class="sxs-lookup"><span data-stu-id="05614-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="05614-139">Le segment précédemment créé est mis à jour avec des données actualisées.</span><span class="sxs-lookup"><span data-stu-id="05614-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="05614-140">Pour modifier un segment similaire, sélectionnez-le sur la page **Segments** et sélectionnez **Modifier** dans la barre d’actions.</span><span class="sxs-lookup"><span data-stu-id="05614-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="05614-141">Appliquez vos modifications et sélectionnez **Exécuter** pour démarrer le traitement.</span><span class="sxs-lookup"><span data-stu-id="05614-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="05614-142">Supprimer un segment similaire</span><span class="sxs-lookup"><span data-stu-id="05614-142">Delete a similar segment</span></span>

<span data-ttu-id="05614-143">Sélectionnez le segment sur la page **Segments** et sélectionnez **Supprimer** dans la barre d’actions.</span><span class="sxs-lookup"><span data-stu-id="05614-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="05614-144">Puis confirmez votre suppression.</span><span class="sxs-lookup"><span data-stu-id="05614-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="05614-145">À propos des scores de similarité</span><span class="sxs-lookup"><span data-stu-id="05614-145">About similarity scores</span></span>

<span data-ttu-id="05614-146">Le modèle de classification binaire Machine Learning attribue un score aux clients du segment similaire.</span><span class="sxs-lookup"><span data-stu-id="05614-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="05614-147">Le score est basé sur la similitude avec les clients du segment source.</span><span class="sxs-lookup"><span data-stu-id="05614-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="05614-148">Les scores de similarité inférieurs à 0,55 sont des clients classés comme *différents* aux clients du segment source.</span><span class="sxs-lookup"><span data-stu-id="05614-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="05614-149">Les scores de similarité entre 0,55 et 0,7 sont classés comme *peu similaires*.</span><span class="sxs-lookup"><span data-stu-id="05614-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="05614-150">Les scores de similarité entre 0,7 et 0,85 sont classés comme *similaires*.</span><span class="sxs-lookup"><span data-stu-id="05614-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="05614-151">Les scores de similarité entre 0,85 et 1 sont des clients classés comme *très similaires*.</span><span class="sxs-lookup"><span data-stu-id="05614-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="05614-152">Les clients avec des scores de similarité inférieurs à 0,4 ne sont pas inclus dans la sortie du modèle.</span><span class="sxs-lookup"><span data-stu-id="05614-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="05614-153">Le système ne les considère pas suffisamment similaires au segment source.</span><span class="sxs-lookup"><span data-stu-id="05614-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]