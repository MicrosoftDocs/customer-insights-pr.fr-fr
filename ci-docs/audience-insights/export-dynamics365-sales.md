---
title: Exporter des données Customer Insights vers Dynamics 365 Sales
description: Découvrez comment configurer la connexion à Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598106"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="cf106-103">Connecteur pour Dynamics 365 Sales (préversion)</span><span class="sxs-lookup"><span data-stu-id="cf106-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="cf106-104">Utilisez vos données client pour créer des listes marketing, effectuer le suivi de workflows et publier des promotions avec Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="cf106-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="cf106-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="cf106-105">Prerequisite</span></span>

1. <span data-ttu-id="cf106-106">Les enregistrements de contact doivent être présents dans Dynamics 365 Sales avant de pouvoir exporter un segment de Customer Insights vers Sales.</span><span class="sxs-lookup"><span data-stu-id="cf106-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="cf106-107">En savoir plus sur la façon d’intégrer des contacts dans [Dynamics 365 Sales utilisant Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="cf106-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="cf106-108">L’exportation de segments des informations sur l’audience vers Sales ne créera pas des enregistrements de contact dans les instances Sales.</span><span class="sxs-lookup"><span data-stu-id="cf106-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="cf106-109">Les enregistrements de contact de Sales doivent être intégrés aux informations sur l’audience et utilisés comme source de données.</span><span class="sxs-lookup"><span data-stu-id="cf106-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="cf106-110">Ils doivent également être inclus dans l’entité Client unifiée pour mapper les ID client avec les ID de contact avant que les segments puissent être exportés.</span><span class="sxs-lookup"><span data-stu-id="cf106-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="cf106-111">Configurer le connecteur pour Sales</span><span class="sxs-lookup"><span data-stu-id="cf106-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="cf106-112">Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="cf106-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="cf106-113">Sous **Dynamics 365 Sales**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="cf106-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="cf106-114">Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="cf106-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="cf106-115">Entrez l’URL Sales de votre organisation dans le champ **Adresse du serveur**.</span><span class="sxs-lookup"><span data-stu-id="cf106-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="cf106-116">Dans la section **Compte administrateur du serveur**, sélectionnez **Se connecter** et choisissez un compte Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="cf106-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="cf106-117">Mappez un champ d’ID de client à l’ID de contact Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cf106-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="cf106-118">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cf106-118">Select **Next**.</span></span>

1. <span data-ttu-id="cf106-119">Choisissez un ou plusieurs segments.</span><span class="sxs-lookup"><span data-stu-id="cf106-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="cf106-120">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="cf106-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="cf106-121">Exporter les données</span><span class="sxs-lookup"><span data-stu-id="cf106-121">Export the data</span></span>

<span data-ttu-id="cf106-122">Vous pouvez [exporter les données à la demande](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="cf106-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="cf106-123">L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cf106-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]