---
title: Enrichir les profils clients unifiés
description: Utilisez des fonctionnalités pour enrichir vos données client.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305245"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="fb4a2-103">Enrichissement des profils clients (aperçu)</span><span class="sxs-lookup"><span data-stu-id="fb4a2-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="fb4a2-104">Utilisez des données provenant de sources telles que Microsoft et d’autres partenaires pour enrichir vos données client.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Page du Centre d’enrichissement":::

<span data-ttu-id="fb4a2-106">Dans les informations sur l’audience, accédez à **Données** > **Enrichissement** pour utiliser les options d’enrichissement.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>  

<span data-ttu-id="fb4a2-107">Vous devez disposer des autorisations Collaborateur ou Administrateur pour créer ou modifier des enrichissements.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="fb4a2-108">Pour plus d’informations, voir [Autorisations](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="fb4a2-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="fb4a2-109">Sur l’onglet **Découvrir**, vous trouverez les enrichissements suivants :</span><span class="sxs-lookup"><span data-stu-id="fb4a2-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="fb4a2-110">[Marques](enrichment-microsoft.md) fournies par Microsoft</span><span class="sxs-lookup"><span data-stu-id="fb4a2-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="fb4a2-111">[Intérêts](enrichment-microsoft.md) fournis par Microsoft</span><span class="sxs-lookup"><span data-stu-id="fb4a2-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="fb4a2-112">[Adresses améliorées](enrichment-enhanced-addresses.md) fournies par Microsoft</span><span class="sxs-lookup"><span data-stu-id="fb4a2-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="fb4a2-113">[Données de la société](enrichment-leadspace.md) fournies par Leadspace</span><span class="sxs-lookup"><span data-stu-id="fb4a2-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="fb4a2-114">[Données démographiques](enrichment-experian.md) fournies par Experian</span><span class="sxs-lookup"><span data-stu-id="fb4a2-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="fb4a2-115">[Données de localisation](enrichment-here.md) fournies par HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="fb4a2-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="fb4a2-116">[Données personnalisées](enrichment-SFTP-custom-import.md) via SFTP (Secure File Transfer Protocol)</span><span class="sxs-lookup"><span data-stu-id="fb4a2-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="fb4a2-117">Sur l’onglet **Mes enrichissements**, vous pouvez voir les enrichissements que vous avez configurés et modifier leurs propriétés.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="fb4a2-118">Gérer les enrichissements existants</span><span class="sxs-lookup"><span data-stu-id="fb4a2-118">Manage existing enrichments</span></span>

<span data-ttu-id="fb4a2-119">Accédez à l’onglet **Mes enrichissements** pour voir tous les enrichissements configurés.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-119">Go to the **My enrichments** tab to see all configured enrichments.</span></span> <span data-ttu-id="fb4a2-120">Chaque enrichissement est représenté sous la forme d’une ligne contenant des informations supplémentaires sur l’enrichissement.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="fb4a2-121">Sélectionnez un enrichissement pour voir les options disponibles.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="fb4a2-122">Vous pouvez également sélectionner les points de suspension (...) d’un élément de liste pour voir les options.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Options pour gérer les enrichissements dans la liste des enrichissements":::

- <span data-ttu-id="fb4a2-124">**Affichez** les détails de l’enrichissement avec le nombre de profils clients enrichis.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="fb4a2-125">**Modifiez** la configuration de l’enrichissement.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="fb4a2-126">**Exécutez** l’enrichissement pour mettre à jour les profils clients avec les dernières données.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="fb4a2-127">**Désactivez** un enrichissement existant pour empêcher qu’il s’actualise automatiquement à chaque actualisation programmée.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="fb4a2-128">(Les données de la dernière actualisation réussie restent disponibles.)</span><span class="sxs-lookup"><span data-stu-id="fb4a2-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="fb4a2-129">**Activez** un enrichissement inactif pour redémarrer l’actualisation automatique à chaque actualisation programmée.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="fb4a2-130">**Supprimez** un enrichissement.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="fb4a2-131">Vous pouvez exécuter ou désactiver plusieurs enrichissements à la fois en les sélectionnant dans la liste.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="fb4a2-132">Les options d’affichage et de modification ne sont pas disponibles en tant qu’action en bloc et ne fonctionnent que pour un enrichissement à la fois.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="fb4a2-133">Enrichissements et connexions</span><span class="sxs-lookup"><span data-stu-id="fb4a2-133">Enrichments and connections</span></span>

<span data-ttu-id="fb4a2-134">Les enrichissements tiers sont configurés à l’aide de [connexions](connections.md), qu’un administrateur configure avec les informations d’identification et donne son consentement pour les transferts de données.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="fb4a2-135">La connexion peut être utilisée par les administrateurs et les contributeurs pour configurer les enrichissements.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="fb4a2-136">Enrichissements multiples du même type</span><span class="sxs-lookup"><span data-stu-id="fb4a2-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="fb4a2-137">L’entité à enrichir est spécifiée lors de la configuration de l’enrichissement, ce qui vous permet d’enrichir uniquement un sous-ensemble de vos profils.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="fb4a2-138">Par exemple, enrichissez les données uniquement pour un segment spécifique.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-138">For example, enrich data only for a specific segment.</span></span> <span data-ttu-id="fb4a2-139">Vous pouvez configurer plusieurs enrichissements du même type et réutiliser la même connexion.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="fb4a2-140">Certains enrichissements auront des limites au nombre d’enrichissements du même type pouvant être créés.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="fb4a2-141">Les limites et l’utilisation actuelle sont visibles sur la page **Enrichissement**.</span><span class="sxs-lookup"><span data-stu-id="fb4a2-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
