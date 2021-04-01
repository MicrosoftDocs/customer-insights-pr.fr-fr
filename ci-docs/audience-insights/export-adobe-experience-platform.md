---
title: Exporter les données Customer Insights vers Adobe Experience Platform
description: Découvrez comment utiliser les segments des informations sur l’audience dans Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596266"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="01563-103">Utiliser les segments Customer Insights dans Adobe Experience Platform (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="01563-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="01563-104">En tant qu’utilisateur d’informations sur l’audience pour Dynamics 365 Customer Insights, vous avez peut-être créé des segments pour rendre vos campagnes marketing plus efficaces en ciblant des audiences pertinentes.</span><span class="sxs-lookup"><span data-stu-id="01563-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="01563-105">Pour utiliser un segment des informations sur l’audience dans Adobe Experience Platform et dans des applications comme Adobe Campaign Standard, vous devez suivre quelques étapes décrites dans cet article.</span><span class="sxs-lookup"><span data-stu-id="01563-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Schéma du processus des étapes décrites dans cet article.":::

## <a name="prerequisites"></a><span data-ttu-id="01563-107">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="01563-107">Prerequisites</span></span>

-   <span data-ttu-id="01563-108">Licence Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="01563-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="01563-109">Licence Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="01563-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="01563-110">Licence Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="01563-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="01563-111">Compte de stockage Blob Azure</span><span class="sxs-lookup"><span data-stu-id="01563-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="01563-112">Vue d’ensemble de la campagne</span><span class="sxs-lookup"><span data-stu-id="01563-112">Campaign Overview</span></span>

<span data-ttu-id="01563-113">Pour mieux comprendre comment utiliser des segments des informations sur l’audience dans Adobe Experience Platform, examinons un exemple de campagne fictif.</span><span class="sxs-lookup"><span data-stu-id="01563-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="01563-114">Supposons que votre entreprise offre un service mensuel basé sur un abonnement à vos clients aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="01563-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="01563-115">Vous souhaitez identifier les clients dont les abonnements doivent être renouvelés dans les huit prochains jours, mais qui n’ont pas encore renouvelé leur abonnement.</span><span class="sxs-lookup"><span data-stu-id="01563-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="01563-116">Pour fidéliser ces clients, vous souhaitez leur envoyer une offre promotionnelle par e-mail, à l’aide d’Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="01563-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="01563-117">Dans cet exemple, nous souhaitons exécuter la campagne d’e-mails promotionnels une seule fois.</span><span class="sxs-lookup"><span data-stu-id="01563-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="01563-118">Cet article ne couvre pas le cas d’utilisation de l’exécution de la campagne plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="01563-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="01563-119">Identifier votre audience cible</span><span class="sxs-lookup"><span data-stu-id="01563-119">Identify your target audience</span></span>

<span data-ttu-id="01563-120">Dans notre scénario, nous supposons que les adresses e-mail des clients sont disponibles dans les informations sur l’audience et que les préférences promotionnelles des clients ont été analysées pour identifier les membres du segment.</span><span class="sxs-lookup"><span data-stu-id="01563-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="01563-121">Le [segment que vous avez défini dans les informations sur l’audience](segments.md) est appelé **ChurnProneCustomers** et vous prévoyez d’envoyer à ces clients la promotion par e-mail.</span><span class="sxs-lookup"><span data-stu-id="01563-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Capture d’écran de la page des segments avec le segment ChurnProneCustomers créé.":::

<span data-ttu-id="01563-123">L’e-mail d’offre que vous souhaitez envoyer contiendra le prénom, le nom et la date de fin d’abonnement du client.</span><span class="sxs-lookup"><span data-stu-id="01563-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="01563-124">Il informe les clients de la réduction qu’ils obtiendront s’ils renouvellent leur abonnement avant qu’il ne se termine.</span><span class="sxs-lookup"><span data-stu-id="01563-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="01563-125">Exporter votre audience cible</span><span class="sxs-lookup"><span data-stu-id="01563-125">Export your target audience</span></span>

<span data-ttu-id="01563-126">Une fois notre audience cible identifiée, nous pouvons configurer l’exportation des informations sur l’audience vers un compte de stockage Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="01563-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="01563-127">Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="01563-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="01563-128">Dans la vignette **Stockage Blob Azure**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="01563-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Vignette de configuration pour Stockage Blob Azure.":::

1. <span data-ttu-id="01563-130">Renseignez un **Nom d’affichage** pour cette nouvelle destination d’exportation, puis saisissez le **Nom du compte**, la **Clé de compte** et le **Conteneur** du compte de stockage Blob Azure vers lequel vous souhaitez exporter le segment.</span><span class="sxs-lookup"><span data-stu-id="01563-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Capture d’écran de la configuration du compte de stockage. "::: 

   - <span data-ttu-id="01563-132">Pour en savoir plus sur la recherche du nom et de la clé de compte de stockage Blob Azure, consultez [Gérer les paramètres du compte de stockage dans le portail Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="01563-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="01563-133">Pour savoir comment créer un conteneur, voir [Créer un conteneur](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="01563-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="01563-134">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="01563-134">Select **Next**.</span></span>

1. <span data-ttu-id="01563-135">Choisissez le segment que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="01563-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="01563-136">Dans cet exemple, il s’agit de **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="01563-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Capture d’écran de l’interface utilisateur de sélection de segment avec le segment ChurnProneCustomers sélectionné.":::

1. <span data-ttu-id="01563-138">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="01563-138">Select **Save**.</span></span>

<span data-ttu-id="01563-139">Après avoir enregistré la destination d’exportation, vous la trouvez sur **Administration** > **Exportations** > **Mes destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="01563-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Capture d’écran montrant la liste des exportations et l’exemple de segment en surbrillance.":::

<span data-ttu-id="01563-141">Vous pouvez maintenant [exporter le segment à la demande](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="01563-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="01563-142">L'exportation sera également exécutée à chaque [actualisation planifiée](system.md).</span><span class="sxs-lookup"><span data-stu-id="01563-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="01563-143">Assurez-vous que le nombre d’enregistrements dans le segment exporté se situe dans la limite autorisée de votre licence Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="01563-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="01563-144">Les données exportées sont stockées dans le conteneur de stockage Blob Azure que vous avez configuré ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="01563-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="01563-145">Le chemin d’accès aux dossiers suivant est créé automatiquement dans votre conteneur :</span><span class="sxs-lookup"><span data-stu-id="01563-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="01563-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="01563-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="01563-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="01563-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="01563-148">Le fichier *model.json* pour les entités exportées réside au niveau *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="01563-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="01563-149">Exemple : Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="01563-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="01563-150">Définir le modèle de données d’expérience utilisateur dans Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="01563-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="01563-151">Avant que les données exportées des informations sur l’audience puissent être utilisées dans Adobe Experience Platform, nous devons définir le schéma du modèle de données d’expérience et [configurer les données pour le profil client en temps réel](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="01563-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="01563-152">Découvrez [le modèle de données d’expérience utilisateur](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) et les [principes de base de la composition de schémas](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="01563-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="01563-153">Importer des données dans Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="01563-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="01563-154">Maintenant que tout est en place, nous devons importer les données d’audience préparées à partir des informations sur l’audience dans Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="01563-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="01563-155">Tout d’abord, [créez une connexion source Stockage Blob Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="01563-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="01563-156">Après avoir défini la connexion source, [configurez un dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pour une connexion par lots de stockage cloud afin d’importer la sortie de segment des informations sur l’audience dans Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="01563-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="01563-157">Créer une audience dans Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="01563-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="01563-158">Pour envoyer l’e-mail de cette campagne, nous utiliserons Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="01563-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="01563-159">Après avoir importé les données dans Adobe Experience Platform, nous devons [créer un audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) dans Adobe Campaign Standard en utilisant les données d’Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="01563-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="01563-160">Découvrez comment [utiliser le générateur de segments](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) dans Adobe Campaign Standard pour définir une audience basée sur les données d’Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="01563-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="01563-161">Créer et envoyer l’e-mail à l’aide d’Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="01563-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="01563-162">Créez le contenu de l’e-mail, puis [testez et envoyez](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) votre e-mail.</span><span class="sxs-lookup"><span data-stu-id="01563-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemple d’e-mail avec l’offre de renouvellement d’Adobe Campaign Standard.":::