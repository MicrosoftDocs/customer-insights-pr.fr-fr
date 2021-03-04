---
title: Bot pour Microsoft Teams
description: Recherchez des profils clients unifiés dans Microsoft Teams avec l’aide d’un bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267949"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="36536-103">Bot Teams pour Dynamics 365 Customer Insights (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="36536-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="36536-104">Connectez-vous à Microsoft Teams pour permettre à un bot de rechercher des profils clients unifiés dans les canaux Teams.</span><span class="sxs-lookup"><span data-stu-id="36536-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="36536-105">![Bot Teams montrant un dossier client](media/teams-bot.png "Bot Teams montrant un dossier client")</span><span class="sxs-lookup"><span data-stu-id="36536-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36536-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="36536-106">Prerequisites</span></span>

<span data-ttu-id="36536-107">Pour installer et configurer le bot, les conditions préalables suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="36536-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="36536-108">Il y a au moins une [source de données ajoutée](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="36536-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="36536-109">Le [processus d’unification](data-unification.md) est complet.</span><span class="sxs-lookup"><span data-stu-id="36536-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="36536-110">Des champs sont ajoutés à l’[index de recherche et de filtrage](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="36536-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="36536-111">Customer Insights et Teams sont dans la même organisation.</span><span class="sxs-lookup"><span data-stu-id="36536-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="36536-112">Configurer le bot</span><span class="sxs-lookup"><span data-stu-id="36536-112">Configure the bot</span></span>

1. <span data-ttu-id="36536-113">Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="36536-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="36536-114">Sur la vignette Microsoft Teams, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="36536-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="36536-115">Vous êtes redirigé vers la zone **Applications** dans Teams.</span><span class="sxs-lookup"><span data-stu-id="36536-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="36536-116">Vous pouvez également ouvrir Teams et sélectionner **Applications** dans l’angle inférieur gauche ou [l’obtenir depuis AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directement.</span><span class="sxs-lookup"><span data-stu-id="36536-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="36536-117">Recherchez **Customer Insights** et sélectionnez l’application.</span><span class="sxs-lookup"><span data-stu-id="36536-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="36536-118">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="36536-118">Select **Add**.</span></span>
1. <span data-ttu-id="36536-119">Une fois connecté à Customer Insights dans Teams, vous voyez un message de bienvenue et vous pouvez commencer.</span><span class="sxs-lookup"><span data-stu-id="36536-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="36536-120">Choses que vous pouvez faire avec le bot</span><span class="sxs-lookup"><span data-stu-id="36536-120">Things you can do with the bot</span></span>

<span data-ttu-id="36536-121">Le bot offre des capacités de recherche pour les profils client unifiés.</span><span class="sxs-lookup"><span data-stu-id="36536-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="36536-122">Saisissez **rechercher** suivi d’un nom, d’une adresse e-mail ou de tout autre champ du profil client unifié ajouté à l’index de recherche et de filtrage.</span><span class="sxs-lookup"><span data-stu-id="36536-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="36536-123">Vous obtenez une carte avec jusqu’à 15 champs de profil client résultant.</span><span class="sxs-lookup"><span data-stu-id="36536-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="36536-124">Plusieurs correspondances renvoient une liste de résultats où vous pouvez sélectionner un profil.</span><span class="sxs-lookup"><span data-stu-id="36536-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="36536-125">Vous pouvez ajouter le critère de recherche entre guillemets doubles pour rechercher une correspondance exacte.</span><span class="sxs-lookup"><span data-stu-id="36536-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="36536-126">Si votre organisation gère plusieurs environnements Customer Insights dans la même organisation, vous pouvez entrer **switchinstance** pour choisir l’environnement auquel vous souhaitez connecter le bot.</span><span class="sxs-lookup"><span data-stu-id="36536-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="36536-127">Saisissez **aide** pour voir une liste des commandes disponibles pour le bot.</span><span class="sxs-lookup"><span data-stu-id="36536-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]