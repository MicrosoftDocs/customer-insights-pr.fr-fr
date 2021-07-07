---
title: Enrichissement de l’amélioration des adresses
description: Enrichissez et normalisez les informations sur les adresses des profils client avec les modèles Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305429"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="80f53-103">Enrichissement des profils client avec des adresses améliorées</span><span class="sxs-lookup"><span data-stu-id="80f53-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="80f53-104">Les adresses dans vos données peuvent être non structurées, incomplètes ou incorrectes.</span><span class="sxs-lookup"><span data-stu-id="80f53-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="80f53-105">Utilisez les modèles de Microsoft pour normaliser et enrichir vos adresses dans le [format Common Data Model](/common-data-model/schema/core/applicationcommon/address) pour une meilleure précision et une meilleure compréhension.</span><span class="sxs-lookup"><span data-stu-id="80f53-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="80f53-106">Valorisation des adresses</span><span class="sxs-lookup"><span data-stu-id="80f53-106">How we enhance addresses</span></span>

<span data-ttu-id="80f53-107">Notre modèle passe par un processus en deux étapes pour améliorer une adresse.</span><span class="sxs-lookup"><span data-stu-id="80f53-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="80f53-108">Tout d’abord, il analyse l’adresse pour identifier ses composants et les met dans un format structuré.</span><span class="sxs-lookup"><span data-stu-id="80f53-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="80f53-109">Ensuite, nous utilisons l’IA pour corriger, compléter et normaliser les valeurs de l’adresse.</span><span class="sxs-lookup"><span data-stu-id="80f53-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="80f53-110">Exemple</span><span class="sxs-lookup"><span data-stu-id="80f53-110">Example</span></span>

<span data-ttu-id="80f53-111">Les informations d’adresse peuvent avoir un format non standard et contenir des fautes d’orthographe.</span><span class="sxs-lookup"><span data-stu-id="80f53-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="80f53-112">Le modèle peut résoudre ces problèmes et créer des adresses cohérentes dans des profils client unifiés.</span><span class="sxs-lookup"><span data-stu-id="80f53-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="80f53-113">Limitations</span><span class="sxs-lookup"><span data-stu-id="80f53-113">Limitations</span></span>

<span data-ttu-id="80f53-114">Les adresses améliorées ne fonctionnent qu’avec les valeurs qui existent déjà dans vos données d’adresse ingérées.</span><span class="sxs-lookup"><span data-stu-id="80f53-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="80f53-115">Le modèle :</span><span class="sxs-lookup"><span data-stu-id="80f53-115">The model doesn't:</span></span> 

1. <span data-ttu-id="80f53-116">ne vérifie pas si l’adresse est une adresse valide ;</span><span class="sxs-lookup"><span data-stu-id="80f53-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="80f53-117">ne vérifie pas si les valeurs, telles que les codes postaux ou les noms de rue, sont valides ;</span><span class="sxs-lookup"><span data-stu-id="80f53-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="80f53-118">ne change pas les valeurs qu’il ne reconnaît pas.</span><span class="sxs-lookup"><span data-stu-id="80f53-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="80f53-119">Le modèle utilise des techniques basées sur le Machine Learning pour améliorer les adresses.</span><span class="sxs-lookup"><span data-stu-id="80f53-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="80f53-120">Bien que nous appliquions un seuil de confiance élevé lorsque le modèle modifie une valeur d’entrée, comme pour tout modèle basé sur Machine Learning, une précision de 100 % n’est pas garantie.</span><span class="sxs-lookup"><span data-stu-id="80f53-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="80f53-121">Pays ou régions pris en charge</span><span class="sxs-lookup"><span data-stu-id="80f53-121">Supported countries or regions</span></span>

<span data-ttu-id="80f53-122">Nous soutenons actuellement l’enrichissement des adresses dans les pays ou régions suivants :</span><span class="sxs-lookup"><span data-stu-id="80f53-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="80f53-123">Australie</span><span class="sxs-lookup"><span data-stu-id="80f53-123">Australia</span></span>
- <span data-ttu-id="80f53-124">Canada</span><span class="sxs-lookup"><span data-stu-id="80f53-124">Canada</span></span>
- <span data-ttu-id="80f53-125">Royaume-Uni</span><span class="sxs-lookup"><span data-stu-id="80f53-125">United Kingdom</span></span>
- <span data-ttu-id="80f53-126">États-Unis</span><span class="sxs-lookup"><span data-stu-id="80f53-126">United States</span></span>

<span data-ttu-id="80f53-127">Les adresses doivent contenir une valeur de pays/région.</span><span class="sxs-lookup"><span data-stu-id="80f53-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="80f53-128">Nous ne traitons pas les adresses de pays ou de régions qui ne sont pas pris en charge et les adresses pour lesquelles aucun pays ou région n’a été fourni.</span><span class="sxs-lookup"><span data-stu-id="80f53-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="80f53-129">Configurer l’enrichissement</span><span class="sxs-lookup"><span data-stu-id="80f53-129">Configure the enrichment</span></span>

1. <span data-ttu-id="80f53-130">Accédez à **Données** > **Enrichissement**.</span><span class="sxs-lookup"><span data-stu-id="80f53-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="80f53-131">Sélectionnez **Enrichir mes données** sur la vignette **Adresses améliorées**.</span><span class="sxs-lookup"><span data-stu-id="80f53-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Capture d’écran de la vignette Adresses améliorées.":::

1. <span data-ttu-id="80f53-133">Sélectionnez le **jeu de données client** et choisissez l’entité contenant les adresses que vous souhaitez enrichir.</span><span class="sxs-lookup"><span data-stu-id="80f53-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="80f53-134">Vous pouvez sélectionner l’entité *Client* pour enrichir les adresses de tous vos profils client ou sélectionner une entité de segment pour enrichir les adresses uniquement dans les profils client contenus dans ce segment.</span><span class="sxs-lookup"><span data-stu-id="80f53-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="80f53-135">Sélectionnez la mise en forme des adresses dans votre jeu de données.</span><span class="sxs-lookup"><span data-stu-id="80f53-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="80f53-136">Choisissez **Adresse à attribut unique** si les adresses de vos données utilisent un seul champ.</span><span class="sxs-lookup"><span data-stu-id="80f53-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="80f53-137">Choisissez **Adresse à attributs multiples** si les adresses de vos données utilisent plusieurs champs de données.</span><span class="sxs-lookup"><span data-stu-id="80f53-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="80f53-138">Le pays ou la région est obligatoire à la fois dans les adresses à attribut unique et à attributs multiples.</span><span class="sxs-lookup"><span data-stu-id="80f53-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="80f53-139">Les adresses qui ne contiennent pas de valeurs de pays ou de région valides ou prises en charge ne seront pas enrichies.</span><span class="sxs-lookup"><span data-stu-id="80f53-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="80f53-140">Mappez les champs d’adresse de votre entité client unifiée.</span><span class="sxs-lookup"><span data-stu-id="80f53-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Page de mappage de champs d’adresse améliorée.":::

1. <span data-ttu-id="80f53-142">Sélectionnez **Suivant** pour terminer le mappage de champs.</span><span class="sxs-lookup"><span data-stu-id="80f53-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="80f53-143">Fournissez un nom pour l’enrichissement et pour l’entité de sortie.</span><span class="sxs-lookup"><span data-stu-id="80f53-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="80f53-144">Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.</span><span class="sxs-lookup"><span data-stu-id="80f53-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="80f53-145">Résultats d’enrichissement</span><span class="sxs-lookup"><span data-stu-id="80f53-145">Enrichment results</span></span>

<span data-ttu-id="80f53-146">Pour démarrer le processus d’enrichissement, sélectionnez **Exécuter** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="80f53-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="80f53-147">Vous pouvez également laisser le système exécuter l’enrichissement automatiquement dans le cadre d’une [actualisation programmée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="80f53-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="80f53-148">Le temps de traitement dépend de la taille de vos données client.</span><span class="sxs-lookup"><span data-stu-id="80f53-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="80f53-149">Une fois le processus d’enrichissement terminé, vous pouvez consulter les données des profils clients nouvellement enrichis sous **Mes enrichissements**.</span><span class="sxs-lookup"><span data-stu-id="80f53-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="80f53-150">De plus, vous trouverez l’heure de la dernière mise à jour et le nombre de profils enrichis.</span><span class="sxs-lookup"><span data-stu-id="80f53-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="80f53-151">Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.</span><span class="sxs-lookup"><span data-stu-id="80f53-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="80f53-152">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="80f53-152">Next steps</span></span>

<span data-ttu-id="80f53-153">Exploitez vos données client enrichies.</span><span class="sxs-lookup"><span data-stu-id="80f53-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="80f53-154">Créez des [segments](segments.md) et des [mesures](measures.md) et [exportez les données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.</span><span class="sxs-lookup"><span data-stu-id="80f53-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
