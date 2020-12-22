---
title: Enrichir les profils clients unifiés
description: Utilisez des fonctionnalités pour enrichir vos données client.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667091"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="406b2-103">Enrichissement des profils clients (aperçu)</span><span class="sxs-lookup"><span data-stu-id="406b2-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="406b2-104">Utilisez des données provenant de sources telles que Microsoft et d'autres partenaires pour enrichir vos données client.</span><span class="sxs-lookup"><span data-stu-id="406b2-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Page du Centre d'enrichissement":::

<span data-ttu-id="406b2-106">Dans Audience Insights, accédez à **Données** > **Enrichissement** pour utiliser les options d'enrichissement.</span><span class="sxs-lookup"><span data-stu-id="406b2-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="406b2-107">Vous devez disposer des autorisations Collaborateur ou Administrateur pour créer ou modifier des enrichissements.</span><span class="sxs-lookup"><span data-stu-id="406b2-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="406b2-108">Pour plus d’informations, voir [Autorisations](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="406b2-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="406b2-109">Sur l'onglet **Découvrir**, vous trouverez les enrichissements suivants :</span><span class="sxs-lookup"><span data-stu-id="406b2-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="406b2-110">[Marques](enrichment-microsoft-graph.md) fournies par Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="406b2-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="406b2-111">[Centres d'intérêt](enrichment-microsoft-graph.md) fournis par Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="406b2-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="406b2-112">[Données de la société](enrichment-leadspace.md) fournies par Leadspace</span><span class="sxs-lookup"><span data-stu-id="406b2-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="406b2-113">[Données démographiques](enrichment-experian.md) fournies par Experian</span><span class="sxs-lookup"><span data-stu-id="406b2-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="406b2-114">[Données de localisation](enrichment-here.md) fournies par HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="406b2-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="406b2-115">[Données personnalisées](enrichment-SFTP-custom-import.md) via SFTP (Secure File Transfer Protocol)</span><span class="sxs-lookup"><span data-stu-id="406b2-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="406b2-116">Sur l'onglet **Mes enrichissements**, vous pouvez voir les enrichissements que vous avez configurés et modifier leurs propriétés.</span><span class="sxs-lookup"><span data-stu-id="406b2-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="406b2-117">Gérer les enrichissements existants</span><span class="sxs-lookup"><span data-stu-id="406b2-117">Manage existing enrichments</span></span>

<span data-ttu-id="406b2-118">Allez à **Mes enrichissements** pour voir tous les enrichissements configurés.</span><span class="sxs-lookup"><span data-stu-id="406b2-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="406b2-119">Chaque enrichissement est représenté sous la forme d'une ligne contenant des informations supplémentaires sur l'enrichissement.</span><span class="sxs-lookup"><span data-stu-id="406b2-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="406b2-120">Sélectionnez un enrichissement pour voir les options disponibles.</span><span class="sxs-lookup"><span data-stu-id="406b2-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="406b2-121">Vous pouvez également sélectionner les points de suspension (...) sur un élément de liste pour voir les options.</span><span class="sxs-lookup"><span data-stu-id="406b2-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Options pour gérer les enrichissements dans la liste des enrichissements":::

- <span data-ttu-id="406b2-123">**Affichez** les détails de l'enrichissement avec le nombre de profils clients enrichis.</span><span class="sxs-lookup"><span data-stu-id="406b2-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="406b2-124">**Modifiez** la configuration de l'enrichissement.</span><span class="sxs-lookup"><span data-stu-id="406b2-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="406b2-125">**Exécutez** l'enrichissement pour mettre à jour les profils clients avec les dernières données.</span><span class="sxs-lookup"><span data-stu-id="406b2-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="406b2-126">**Désactivez** un enrichissement existant pour empêcher qu'il s'actualise automatiquement à chaque actualisation programmée.</span><span class="sxs-lookup"><span data-stu-id="406b2-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="406b2-127">Les données de la dernière actualisation réussie resteront disponibles.</span><span class="sxs-lookup"><span data-stu-id="406b2-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="406b2-128">**Activez** un enrichissement inactif pour redémarrer l'actualisation automatique à chaque actualisation programmée.</span><span class="sxs-lookup"><span data-stu-id="406b2-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="406b2-129">**Supprimez** un enrichissement.</span><span class="sxs-lookup"><span data-stu-id="406b2-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="406b2-130">Vous pouvez exécuter ou désactiver plusieurs enrichissements à la fois en les sélectionnant dans la liste.</span><span class="sxs-lookup"><span data-stu-id="406b2-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="406b2-131">Les options d'affichage et de modification ne sont pas disponibles en tant qu'action en bloc et ne fonctionnent que pour un enrichissement à la fois.</span><span class="sxs-lookup"><span data-stu-id="406b2-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>
