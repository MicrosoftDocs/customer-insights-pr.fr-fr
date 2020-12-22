---
title: Exporter des données Customer Insights vers Dynamics 365 Sales
description: Découvrez comment configurer la connexion à Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643815"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="87a73-103">Connecteur pour Dynamics 365 Sales (préversion)</span><span class="sxs-lookup"><span data-stu-id="87a73-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="87a73-104">Utilisez vos données client pour créer des listes marketing, effectuer le suivi de workflows et publier des promotions avec Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="87a73-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="87a73-105">Éléments requis</span><span class="sxs-lookup"><span data-stu-id="87a73-105">Prerequisite</span></span>

<span data-ttu-id="87a73-106">Enregistrements de contact [de Dynamics 365 Sales ingérés à l'aide de Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="87a73-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="87a73-107">Configurer le connecteur pour Sales</span><span class="sxs-lookup"><span data-stu-id="87a73-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="87a73-108">Dans Audience Insights, accédez à **Administration** > **Destinations d'exportation**.</span><span class="sxs-lookup"><span data-stu-id="87a73-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="87a73-109">Sous **Dynamics 365 Sales**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="87a73-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="87a73-110">Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="87a73-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="87a73-111">Entrez l’URL Sales de votre organisation dans le champ **Adresse du serveur**.</span><span class="sxs-lookup"><span data-stu-id="87a73-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="87a73-112">Dans la section **Compte administrateur du serveur**, sélectionnez **Se connecter** et choisissez un compte Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="87a73-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="87a73-113">Mappez un champ d'ID de client à l'ID de contact Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="87a73-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="87a73-114">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="87a73-114">Select **Next**.</span></span>

1. <span data-ttu-id="87a73-115">Choisissez un ou plusieurs segments.</span><span class="sxs-lookup"><span data-stu-id="87a73-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="87a73-116">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="87a73-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="87a73-117">Exporter les données</span><span class="sxs-lookup"><span data-stu-id="87a73-117">Export the data</span></span>

<span data-ttu-id="87a73-118">Vous pouvez [exporter les données à la demande](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="87a73-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="87a73-119">L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="87a73-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
