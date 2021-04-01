---
title: Exporter les données Customer Insights vers Adobe Campaign Standard
description: Découvrez comment utiliser les segments des informations sur l’audience dans Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596312"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="77321-103">Utiliser les segments Customer Insights dans Adobe Campaign Standard (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="77321-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="77321-104">En tant qu’utilisateur d’informations sur l’audience pour Dynamics 365 Customer Insights, vous avez peut-être créé des segments pour rendre vos campagnes marketing plus efficaces en ciblant des audiences pertinentes.</span><span class="sxs-lookup"><span data-stu-id="77321-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="77321-105">Pour utiliser un segment des informations sur l’audience dans Adobe Experience Platform et dans des applications comme Adobe Campaign Standard, vous devez suivre quelques étapes décrites dans cet article.</span><span class="sxs-lookup"><span data-stu-id="77321-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Schéma du processus des étapes décrites dans cet article.":::

## <a name="prerequisites"></a><span data-ttu-id="77321-107">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="77321-107">Prerequisites</span></span>

-   <span data-ttu-id="77321-108">Licence Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="77321-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="77321-109">Licence Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="77321-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="77321-110">Compte de stockage Blob Azure</span><span class="sxs-lookup"><span data-stu-id="77321-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="77321-111">Vue d’ensemble de la campagne</span><span class="sxs-lookup"><span data-stu-id="77321-111">Campaign Overview</span></span>

<span data-ttu-id="77321-112">Pour mieux comprendre comment utiliser des segments des informations sur l’audience dans Adobe Experience Platform, examinons un exemple de campagne fictif.</span><span class="sxs-lookup"><span data-stu-id="77321-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="77321-113">Supposons que votre entreprise offre un service mensuel basé sur un abonnement à vos clients aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="77321-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="77321-114">Vous souhaitez identifier les clients dont les abonnements doivent être renouvelés dans les huit prochains jours, mais qui n’ont pas encore renouvelé leur abonnement.</span><span class="sxs-lookup"><span data-stu-id="77321-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="77321-115">Pour fidéliser ces clients, vous souhaitez leur envoyer une offre promotionnelle par e-mail, à l’aide d’Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="77321-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="77321-116">Dans cet exemple, nous souhaitons exécuter la campagne d’e-mails promotionnels une seule fois.</span><span class="sxs-lookup"><span data-stu-id="77321-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="77321-117">Cet article ne couvre pas le cas d’utilisation de l’exécution de la campagne plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="77321-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="77321-118">Cependant, les informations sur l’audience et Adobe Campaign Standard peuvent également être configurées pour fonctionner pour un scénario de campagne récurrent.</span><span class="sxs-lookup"><span data-stu-id="77321-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="77321-119">Identifier votre audience cible</span><span class="sxs-lookup"><span data-stu-id="77321-119">Identify your target audience</span></span>

<span data-ttu-id="77321-120">Dans notre scénario, nous supposons que les adresses e-mail des clients sont disponibles dans les informations sur l’audience et que les préférences promotionnelles des clients ont été analysées pour identifier les membres du segment.</span><span class="sxs-lookup"><span data-stu-id="77321-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="77321-121">Le [segment que vous avez défini dans les informations sur l’audience](segments.md) est appelé **ChurnProneCustomers** et vous prévoyez d’envoyer à ces clients la promotion par e-mail.</span><span class="sxs-lookup"><span data-stu-id="77321-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Capture d’écran de la page des segments avec le segment ChurnProneCustomers créé.":::

<span data-ttu-id="77321-123">L’e-mail d’offre que vous souhaitez envoyer contiendra le prénom, le nom et la date de fin d’abonnement du client.</span><span class="sxs-lookup"><span data-stu-id="77321-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="77321-124">Il informe les clients de la réduction qu’ils obtiendront s’ils renouvellent leur abonnement avant qu’il ne se termine.</span><span class="sxs-lookup"><span data-stu-id="77321-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="77321-125">Exporter votre audience cible</span><span class="sxs-lookup"><span data-stu-id="77321-125">Export your target audience</span></span>

<span data-ttu-id="77321-126">Une fois notre audience cible identifiée, nous pouvons configurer l’exportation des informations sur l’audience vers un compte de stockage Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="77321-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="77321-127">Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="77321-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="77321-128">Dans la vignette **Adobe Campaign**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="77321-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Vignette de configuration pour Adobe Campaign Standard.":::

1. <span data-ttu-id="77321-130">Renseignez un **Nom d’affichage** pour cette nouvelle destination d’exportation, puis saisissez le **Nom du compte**, la **Clé de compte** et le **Conteneur** du compte de stockage Blob Azure vers lequel vous souhaitez exporter le segment.</span><span class="sxs-lookup"><span data-stu-id="77321-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Capture d’écran de la configuration du compte de stockage. "::: 

   - <span data-ttu-id="77321-132">Pour en savoir plus sur la recherche du nom et de la clé de compte de stockage Blob Azure, consultez [Gérer les paramètres du compte de stockage dans le portail Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="77321-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="77321-133">Pour savoir comment créer un conteneur, voir [Créer un conteneur](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="77321-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="77321-134">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="77321-134">Select **Next**.</span></span>

1. <span data-ttu-id="77321-135">Choisissez le segment que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="77321-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="77321-136">Dans cet exemple, il s’agit de **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="77321-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Capture d’écran de l’interface utilisateur de sélection de segment avec le segment ChurnProneCustomers sélectionné.":::

1. <span data-ttu-id="77321-138">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="77321-138">Select **Next**.</span></span>

1. <span data-ttu-id="77321-139">Maintenant, nous mappons les champs **Source** du segment des informations sur l’audience au champ **Cible** du schéma de profil Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="77321-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mappage de champs pour le connecteur Adobe Campaign Standard.":::

   <span data-ttu-id="77321-141">Si vous souhaitez ajouter d’autres attributs, sélectionnez **Ajouter un attribut**.</span><span class="sxs-lookup"><span data-stu-id="77321-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="77321-142">Le nom de la cible peut être différent du nom du champ de la source, afin que vous puissiez toujours mapper la sortie du segment des informations sur l’audience à Adobe Campaign Standard si les champs ne portent pas le même nom dans les deux systèmes.</span><span class="sxs-lookup"><span data-stu-id="77321-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="77321-143">L’adresse e-mail est utilisée comme champ d’identité, mais vous pouvez utiliser tout autre identificateur de votre profil client des informations sur l’audience pour mapper des données à Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="77321-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="77321-144">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="77321-144">Select **Save**.</span></span>

<span data-ttu-id="77321-145">Après avoir enregistré la destination d’exportation, vous la trouvez sur **Administration** > **Exportations** > **Mes destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="77321-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Capture d’écran montrant la liste des exportations et l’exemple de segment en surbrillance.":::

<span data-ttu-id="77321-147">Vous pouvez maintenant [exporter le segment à la demande](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="77321-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="77321-148">L'exportation sera également exécutée à chaque [actualisation planifiée](system.md).</span><span class="sxs-lookup"><span data-stu-id="77321-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="77321-149">Assurez-vous que le nombre d’enregistrements dans le segment exporté se situe dans la limite autorisée de votre licence Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="77321-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="77321-150">Les données exportées sont stockées dans le conteneur de stockage Blob Azure que vous avez configuré ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="77321-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="77321-151">Le chemin d’accès aux dossiers suivant est créé automatiquement dans votre conteneur :</span><span class="sxs-lookup"><span data-stu-id="77321-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="77321-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="77321-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="77321-153">Exemple : Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="77321-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="77321-154">Configurer Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="77321-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="77321-155">Lorsqu’un segment des informations sur l’audience est exporté, il contient les colonnes que vous avez sélectionnées lors de la définition de la destination d’exportation à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="77321-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="77321-156">Ces données peuvent être utilisées pour [créer des profils dans Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="77321-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="77321-157">Pour utiliser le segment dans Adobe Campaign Standard, nous devons étendre le schéma de profil dans Adobe Campaign Standard pour inclure deux champs supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="77321-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="77321-158">Découvrez comment [étendre la ressource de profil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) avec de nouveaux champs dans Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="77321-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="77321-159">Dans notre exemple, ces champs sont *Nom du segment et Date du segment (facultatif).*</span><span class="sxs-lookup"><span data-stu-id="77321-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="77321-160">Nous utiliserons ces champs pour identifier les profils dans Adobe Campaign Standard que nous souhaitons cibler pour cette campagne.</span><span class="sxs-lookup"><span data-stu-id="77321-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="77321-161">S’il n’y a pas d’autres enregistrements dans Adobe Campaign Standard, autres que ceux que vous allez importer, vous pouvez ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="77321-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="77321-162">Importer des données dans Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="77321-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="77321-163">Maintenant que tout est en place, nous devons importer les données d’audience préparées à partir des informations sur l’audience dans Adobe Campaign Standard pour créer des profils.</span><span class="sxs-lookup"><span data-stu-id="77321-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="77321-164">Découvrez [comment importer des profils dans Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) en utilisant un workflow.</span><span class="sxs-lookup"><span data-stu-id="77321-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="77321-165">Le workflow d’importation dans l’image ci-dessous a été configuré pour s’exécuter toutes les 8 heures et recherche les segments des informations sur l’audience exportés (fichier .csv dans le stockage Blob Azure).</span><span class="sxs-lookup"><span data-stu-id="77321-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="77321-166">Le workflow extrait le contenu du fichier .csv dans un ordre de colonne spécifié.</span><span class="sxs-lookup"><span data-stu-id="77321-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="77321-167">Ce workflow a été conçu pour effectuer une gestion des erreurs de base et garantir que chaque enregistrement possède une adresse e-mail avant d’hydrater les données dans Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="77321-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="77321-168">Le workflow extrait également le nom du segment du nom de fichier avant de les insérer dans les données de profil ACS.</span><span class="sxs-lookup"><span data-stu-id="77321-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Capture d’écran d’un workflow d’importation dans l’interface utilisateur d’Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="77321-170">Récupérer l’audience dans Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="77321-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="77321-171">Une fois les données importées dans Adobe Campaign Standard, vous [pouvez créer un workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) et [interroger](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) les clients en fonction des données *Nom du segment* et *Date du segment* pour sélectionner les profils identifiés pour notre exemple de campagne.</span><span class="sxs-lookup"><span data-stu-id="77321-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="77321-172">Créer et envoyer l’e-mail à l’aide d’Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="77321-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="77321-173">Créez le contenu de l’e-mail, puis [testez et envoyez](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) votre e-mail.</span><span class="sxs-lookup"><span data-stu-id="77321-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemple d’e-mail avec l’offre de renouvellement d’Adobe Campaign Standard.":::