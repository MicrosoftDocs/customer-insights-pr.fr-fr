---
title: Exporter des données Customer Insights vers Dynamics 365 Marketing
description: Découvrez comment configurer la connexion à Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269051"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="a9c4e-103">Connecteur pour Dynamics 365 Marketing (préversion)</span><span class="sxs-lookup"><span data-stu-id="a9c4e-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a9c4e-104">Utilisez des [segments](segments.md) pour générer des campagnes et contacter des groupes de clients spécifiques avec Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a9c4e-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="a9c4e-105">Pour plus d’informations, voir [Utiliser des segments de Dynamics 365 Customer Insights avec Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments).</span><span class="sxs-lookup"><span data-stu-id="a9c4e-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="a9c4e-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="a9c4e-106">Prerequisite</span></span>

- <span data-ttu-id="a9c4e-107">Les enregistrements de contact doivent être présents dans Dynamics 365 Marketing avant de pouvoir exporter un segment de Customer Insights vers Marketing.</span><span class="sxs-lookup"><span data-stu-id="a9c4e-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="a9c4e-108">En savoir plus sur la façon d’intégrer des contacts dans [Dynamics 365 Marketing utilisant Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a9c4e-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a9c4e-109">L’exportation de segments des informations sur l’audience vers Marketing ne créera pas des enregistrements de contact dans les instances Marketing.</span><span class="sxs-lookup"><span data-stu-id="a9c4e-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="a9c4e-110">Les enregistrements de contact de Marketing doivent être intégrés aux informations sur l’audience et utilisés comme source de données.</span><span class="sxs-lookup"><span data-stu-id="a9c4e-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="a9c4e-111">Ils doivent également être inclus dans l’entité Client unifiée pour mapper les ID client avec les ID de contact avant que les segments puissent être exportés.</span><span class="sxs-lookup"><span data-stu-id="a9c4e-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="a9c4e-112">Configurer le connecteur pour Marketing</span><span class="sxs-lookup"><span data-stu-id="a9c4e-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="a9c4e-113">Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="a9c4e-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a9c4e-114">Sous **Dynamics 365 Marketing**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="a9c4e-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="a9c4e-115">Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="a9c4e-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a9c4e-116">Entrez l’URL marketing de votre organisation dans le champ **Adresse du serveur**.</span><span class="sxs-lookup"><span data-stu-id="a9c4e-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a9c4e-117">Dans la section **Compte administrateur du serveur**, sélectionnez **Se connecter** et choisissez un compte Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a9c4e-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="a9c4e-118">Mappez un champ d’ID de client à l’ID de contact Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a9c4e-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a9c4e-119">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a9c4e-119">Select **Next**.</span></span>

1. <span data-ttu-id="a9c4e-120">Choisissez un ou plusieurs segments.</span><span class="sxs-lookup"><span data-stu-id="a9c4e-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="a9c4e-121">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="a9c4e-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a9c4e-122">Exporter les données</span><span class="sxs-lookup"><span data-stu-id="a9c4e-122">Export the data</span></span>

<span data-ttu-id="a9c4e-123">Vous pouvez [exporter les données à la demande](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a9c4e-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a9c4e-124">L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a9c4e-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]