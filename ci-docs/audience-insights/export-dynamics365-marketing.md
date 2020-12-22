---
title: Exporter des données Customer Insights vers Dynamics 365 Marketing
description: Découvrez comment configurer la connexion à Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643770"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="cfffa-103">Connecteur pour Dynamics 365 Marketing (préversion)</span><span class="sxs-lookup"><span data-stu-id="cfffa-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="cfffa-104">Utilisez des [segments](segments.md) pour générer des campagnes et contacter des groupes de clients spécifiques avec Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="cfffa-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="cfffa-105">Pour plus d’informations, voir [Utiliser des segments de Dynamics 365 Customer Insights avec Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments).</span><span class="sxs-lookup"><span data-stu-id="cfffa-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="cfffa-106">Éléments requis</span><span class="sxs-lookup"><span data-stu-id="cfffa-106">Prerequisite</span></span>

<span data-ttu-id="cfffa-107">Enregistrements de contact [de Dynamics 365 Marketing ingérés à l'aide de Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="cfffa-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="cfffa-108">Configurer le connecteur pour Marketing</span><span class="sxs-lookup"><span data-stu-id="cfffa-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="cfffa-109">Dans Audience Insights, accédez à **Administration** > **Destinations d'exportation**.</span><span class="sxs-lookup"><span data-stu-id="cfffa-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="cfffa-110">Sous **Dynamics 365 Marketing**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="cfffa-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="cfffa-111">Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="cfffa-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="cfffa-112">Entrez l’URL marketing de votre organisation dans le champ **Adresse du serveur**.</span><span class="sxs-lookup"><span data-stu-id="cfffa-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="cfffa-113">Dans la section **Compte administrateur du serveur**, sélectionnez **Se connecter** et choisissez un compte Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="cfffa-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="cfffa-114">Mappez un champ d'ID de client à l'ID de contact Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cfffa-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="cfffa-115">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="cfffa-115">Select **Next**.</span></span>

1. <span data-ttu-id="cfffa-116">Choisissez un ou plusieurs segments.</span><span class="sxs-lookup"><span data-stu-id="cfffa-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="cfffa-117">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="cfffa-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="cfffa-118">Exporter les données</span><span class="sxs-lookup"><span data-stu-id="cfffa-118">Export the data</span></span>

<span data-ttu-id="cfffa-119">Vous pouvez [exporter les données à la demande](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="cfffa-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="cfffa-120">L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cfffa-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
