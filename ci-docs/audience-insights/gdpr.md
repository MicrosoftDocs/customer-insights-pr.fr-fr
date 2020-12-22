---
title: Demandes de droits de la personne concernée dans le cadre du RGPD | Microsoft Docs
description: Répondez aux demandes de la personne concernée pour la fonctionnalité Audience Insights de Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405667"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="1e6b2-103">Demandes de droits de la personne concernée dans le cadre du RGPD</span><span class="sxs-lookup"><span data-stu-id="1e6b2-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="1e6b2-104">Répondre aux demandes de suppression de la personne concernée dans le cadre du RGPD pour la fonctionnalité Audience Insights de Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="1e6b2-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="1e6b2-105">Le « droit d'effacement », par la suppression des données personnelles dans les données client d'une entreprise est un élément de protection essentiel du Règlement général sur la protection des données (RGPD).</span><span class="sxs-lookup"><span data-stu-id="1e6b2-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="1e6b2-106">La suppression des données personnelles inclut toutes les données personnelles et journaux générés par le système, à l'exception des informations des journaux d'audit.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="1e6b2-107">Gestion des demandes de suppression des personnes concernées</span><span class="sxs-lookup"><span data-stu-id="1e6b2-107">Manage data subject delete requests</span></span>

<span data-ttu-id="1e6b2-108">Audience Insights offre les fonctionnalités intégrées suivantes pour supprimer les données personnelles d'un client ou d'un utilisateur spécifique :</span><span class="sxs-lookup"><span data-stu-id="1e6b2-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="1e6b2-109">**Gérer les demandes de suppression de données client** : Les données client dans Customer Insights sont ingérées à partir de sources de données d'origine externes à Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="1e6b2-110">Toutes les demandes de suppression du RGPD doivent être effectuées dans la source de données d'origine.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="1e6b2-111">**Gérer les demandes de suppression de données utilisateur de Customer Insights** : les données des utilisateurs sont créées par Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="1e6b2-112">Toutes les demandes de suppression du RGPD doivent être effectuées dans Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="1e6b2-113">Gérer les demandes de suppression de données client</span><span class="sxs-lookup"><span data-stu-id="1e6b2-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="1e6b2-114">Un administrateur Customer Insights peut suivre ces étapes pour supprimer les données client qui ont été supprimées dans le source de données :</span><span class="sxs-lookup"><span data-stu-id="1e6b2-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="1e6b2-115">Connectez-vous à Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="1e6b2-116">Dans Audience Insights, accédez à **Données** > **Sources de données**</span><span class="sxs-lookup"><span data-stu-id="1e6b2-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="1e6b2-117">Pour chaque source de données de la liste contenant des données client supprimées, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1e6b2-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="1e6b2-118">Sélectionnez (...), puis sélectionnez **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="1e6b2-119">Vérifiez le statut de la source de données sous **Statut**.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="1e6b2-120">Une coche signifie que l'actualisation a réussi.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="1e6b2-121">Un triangle d'avertissement indique que quelque chose n'a pas fonctionné.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="1e6b2-122">Si un triangle d'avertissement s'affiche, contactez D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1e6b2-123">![Gestion des demandes de suppression de données client dans le cadre du RGPD](media/gdpr-data-sources.png "Gestion des demandes de suppression de données client dans le cadre du RGPD")</span><span class="sxs-lookup"><span data-stu-id="1e6b2-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="1e6b2-124">Gérer les demandes de suppression de données utilisateur</span><span class="sxs-lookup"><span data-stu-id="1e6b2-124">Manage delete requests for user data</span></span>

<span data-ttu-id="1e6b2-125">Un administrateur Customer Insights peut procéder de la manière suivante pour supprimer les données d'utilisateur Customer Insights :</span><span class="sxs-lookup"><span data-stu-id="1e6b2-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="1e6b2-126">Connectez-vous à Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="1e6b2-127">Dans Audience Insights, accédez à **Administration** > **Autorisations**.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="1e6b2-128">Activez la case à cocher correspondant à l'utilisateur que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="1e6b2-129">Cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1e6b2-130">![Gestion des demandes de suppression de données utilisateur dans le cadre du RGPD](media/gdpr-permissions.png "Gestion des demandes de suppression de données utilisateur dans le cadre du RGPD")</span><span class="sxs-lookup"><span data-stu-id="1e6b2-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="1e6b2-131">Répondre aux demandes d'exportation de la personne concernée dans le cadre du RGPD</span><span class="sxs-lookup"><span data-stu-id="1e6b2-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="1e6b2-132">Dans le cadre de notre engagement à vous accompagner le long de votre parcours de conformité au Règlement général sur la protection des données (RGPD), nous avons élaboré une documentation pour vous aider à vous préparer.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="1e6b2-133">Cette documentation décrit les étapes que vous pouvez suivre pour assurer la conformité au RGPD lorsque vous utilisez Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="1e6b2-134">Gérer les demandes de visualisation et d'exportation</span><span class="sxs-lookup"><span data-stu-id="1e6b2-134">Manage export and view requests</span></span>

<span data-ttu-id="1e6b2-135">Le droit à la portabilité des données permet à une personne concernée de demander une copie de ses données personnelles dans un format électronique (à savoir, un format « structuré, répandu, lisible sur ordinateur et interopérable ») transmissible à un autre contrôleur de données.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="1e6b2-136">Exporter des données client (administrateur du client)</span><span class="sxs-lookup"><span data-stu-id="1e6b2-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="1e6b2-137">Un administrateur du client peut exécuter la procédure suivante pour exporter des données :</span><span class="sxs-lookup"><span data-stu-id="1e6b2-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="1e6b2-138">Envoyer un e-mail à D365CI@microsoft.com en indiquant l'adresse de messagerie du client dans la demande.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="1e6b2-139">L'équipe Customer Insights enverra un e-mail à l'adresse de messagerie enregistrée de l'administrateur du client, en demandant confirmation de l'exportation des données.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="1e6b2-140">Acquitter la confirmation de l'exportation des données pour le client demandé.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="1e6b2-141">Recevoir les données exportées via l'adresse de messagerie de l'administrateur du client.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="1e6b2-142">Exporter des données utilisateur (administrateur du client)</span><span class="sxs-lookup"><span data-stu-id="1e6b2-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="1e6b2-143">Envoyer un e-mail à D365CI@microsoft.com en indiquant l'adresse de messagerie de l'utilisateur dans la demande.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="1e6b2-144">L'équipe Customer Insights enverra un e-mail à l'adresse de messagerie enregistrée de l'administrateur du client, en demandant confirmation de l'exportation des données.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="1e6b2-145">Acquitter la confirmation de l'exportation des données pour l'utilisateur demandé.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="1e6b2-146">Recevoir les données exportées via l'adresse de messagerie de l'administrateur du client.</span><span class="sxs-lookup"><span data-stu-id="1e6b2-146">Receive the exported data through the tenant admin email address.</span></span>
