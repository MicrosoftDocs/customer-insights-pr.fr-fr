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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896002"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="c2bf9-103">Enrichissement des profils clients (aperçu)</span><span class="sxs-lookup"><span data-stu-id="c2bf9-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="c2bf9-104">Utilisez des données provenant de sources telles que Microsoft et d’autres partenaires pour enrichir vos données client.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Page du Centre d’enrichissement":::

<span data-ttu-id="c2bf9-106">Dans les informations sur l’audience, accédez à **Données** > **Enrichissement** pour utiliser les options d’enrichissement.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="c2bf9-107">Vous devez disposer des autorisations Collaborateur ou Administrateur pour créer ou modifier des enrichissements.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="c2bf9-108">Pour plus d’informations, voir [Autorisations](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c2bf9-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="c2bf9-109">Sur l’onglet **Découvrir**, vous trouverez les enrichissements suivants :</span><span class="sxs-lookup"><span data-stu-id="c2bf9-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="c2bf9-110">[Marques](enrichment-microsoft.md) fournies par Microsoft</span><span class="sxs-lookup"><span data-stu-id="c2bf9-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="c2bf9-111">[Intérêts](enrichment-microsoft.md) fournis par Microsoft</span><span class="sxs-lookup"><span data-stu-id="c2bf9-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="c2bf9-112">[Données de la société](enrichment-leadspace.md) fournies par Leadspace</span><span class="sxs-lookup"><span data-stu-id="c2bf9-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="c2bf9-113">[Données démographiques](enrichment-experian.md) fournies par Experian</span><span class="sxs-lookup"><span data-stu-id="c2bf9-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="c2bf9-114">[Données de localisation](enrichment-here.md) fournies par HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="c2bf9-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="c2bf9-115">[Données personnalisées](enrichment-SFTP-custom-import.md) via SFTP (Secure File Transfer Protocol)</span><span class="sxs-lookup"><span data-stu-id="c2bf9-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="c2bf9-116">Sur l’onglet **Mes enrichissements**, vous pouvez voir les enrichissements que vous avez configurés et modifier leurs propriétés.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="c2bf9-117">Gérer les enrichissements existants</span><span class="sxs-lookup"><span data-stu-id="c2bf9-117">Manage existing enrichments</span></span>

<span data-ttu-id="c2bf9-118">Allez à **Mes enrichissements** pour voir tous les enrichissements configurés.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="c2bf9-119">Chaque enrichissement est représenté sous la forme d’une ligne contenant des informations supplémentaires sur l’enrichissement.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="c2bf9-120">Sélectionnez un enrichissement pour voir les options disponibles.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="c2bf9-121">Vous pouvez également sélectionner les points de suspension (...) d’un élément de liste pour voir les options.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Options pour gérer les enrichissements dans la liste des enrichissements":::

- <span data-ttu-id="c2bf9-123">**Affichez** les détails de l’enrichissement avec le nombre de profils clients enrichis.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="c2bf9-124">**Modifiez** la configuration de l’enrichissement.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="c2bf9-125">**Exécutez** l’enrichissement pour mettre à jour les profils clients avec les dernières données.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="c2bf9-126">**Désactivez** un enrichissement existant pour empêcher qu’il s’actualise automatiquement à chaque actualisation programmée.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="c2bf9-127">(Les données de la dernière actualisation réussie restent disponibles.)</span><span class="sxs-lookup"><span data-stu-id="c2bf9-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="c2bf9-128">**Activez** un enrichissement inactif pour redémarrer l’actualisation automatique à chaque actualisation programmée.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="c2bf9-129">**Supprimez** un enrichissement.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="c2bf9-130">Vous pouvez exécuter ou désactiver plusieurs enrichissements à la fois en les sélectionnant dans la liste.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="c2bf9-131">Les options d’affichage et de modification ne sont pas disponibles en tant qu’action en bloc et ne fonctionnent que pour un enrichissement à la fois.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="c2bf9-132">Enrichissements et connexions</span><span class="sxs-lookup"><span data-stu-id="c2bf9-132">Enrichments and connections</span></span>

<span data-ttu-id="c2bf9-133">Les enrichissements tiers sont configurés à l’aide de [connexions](connections.md), qu’un administrateur configure avec les informations d’identification et donne son consentement pour les transferts de données.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="c2bf9-134">La connexion peut être utilisée par les administrateurs et les contributeurs pour configurer les enrichissements.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="c2bf9-135">Enrichissements multiples du même type</span><span class="sxs-lookup"><span data-stu-id="c2bf9-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="c2bf9-136">L’entité à enrichir est spécifiée lors de la configuration de l’enrichissement, ce qui vous permet d’enrichir uniquement un sous-ensemble de vos profils.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="c2bf9-137">Par exemple, enrichissez les données uniquement pour un segment spécifique.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="c2bf9-138">Vous pouvez configurer plusieurs enrichissements du même type et réutiliser la même connexion.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="c2bf9-139">Certains enrichissements auront des limites au nombre d’enrichissements du même type pouvant être créés.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="c2bf9-140">Les limites et l’utilisation actuelle sont visibles sur la page **Enrichissement**.</span><span class="sxs-lookup"><span data-stu-id="c2bf9-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
