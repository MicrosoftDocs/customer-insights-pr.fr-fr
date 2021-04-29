---
title: Exporter les données Customer Insights vers Adobe Campaign Standard
description: Découvrez comment utiliser les segments des informations sur l’audience dans Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760278"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="c03ee-103">Utiliser les segments Customer Insights dans Adobe Campaign Standard (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="c03ee-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="c03ee-104">En tant qu’utilisateur d’informations sur l’audience pour Dynamics 365 Customer Insights, vous avez peut-être créé des segments pour rendre vos campagnes marketing plus efficaces en ciblant des audiences pertinentes.</span><span class="sxs-lookup"><span data-stu-id="c03ee-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="c03ee-105">Pour utiliser un segment des informations sur l’audience dans Adobe Experience Platform et dans des applications comme Adobe Campaign Standard, vous devez suivre quelques étapes décrites dans cet article.</span><span class="sxs-lookup"><span data-stu-id="c03ee-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Schéma du processus des étapes décrites dans cet article.":::

## <a name="prerequisites"></a><span data-ttu-id="c03ee-107">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="c03ee-107">Prerequisites</span></span>

-   <span data-ttu-id="c03ee-108">Licence Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="c03ee-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="c03ee-109">Licence Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c03ee-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="c03ee-110">Compte de stockage Blob Azure</span><span class="sxs-lookup"><span data-stu-id="c03ee-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="c03ee-111">Vue d’ensemble de la campagne</span><span class="sxs-lookup"><span data-stu-id="c03ee-111">Campaign Overview</span></span>

<span data-ttu-id="c03ee-112">Pour mieux comprendre comment utiliser des segments des informations sur l’audience dans Adobe Experience Platform, examinons un exemple de campagne fictif.</span><span class="sxs-lookup"><span data-stu-id="c03ee-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="c03ee-113">Supposons que votre entreprise offre un service mensuel basé sur un abonnement à vos clients aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="c03ee-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="c03ee-114">Vous souhaitez identifier les clients dont les abonnements doivent être renouvelés dans les huit prochains jours, mais qui n’ont pas encore renouvelé leur abonnement.</span><span class="sxs-lookup"><span data-stu-id="c03ee-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="c03ee-115">Pour fidéliser ces clients, vous souhaitez leur envoyer une offre promotionnelle par e-mail, à l’aide d’Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c03ee-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="c03ee-116">Dans cet exemple, nous souhaitons exécuter la campagne d’e-mails promotionnels une seule fois.</span><span class="sxs-lookup"><span data-stu-id="c03ee-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="c03ee-117">Cet article ne couvre pas le cas d’utilisation de l’exécution de la campagne plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="c03ee-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="c03ee-118">Cependant, les informations sur l’audience et Adobe Campaign Standard peuvent également être configurées pour fonctionner pour un scénario de campagne récurrent.</span><span class="sxs-lookup"><span data-stu-id="c03ee-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="c03ee-119">Identifier votre audience cible</span><span class="sxs-lookup"><span data-stu-id="c03ee-119">Identify your target audience</span></span>

<span data-ttu-id="c03ee-120">Dans notre scénario, nous supposons que les adresses e-mail des clients sont disponibles dans les informations sur l’audience et que les préférences promotionnelles des clients ont été analysées pour identifier les membres du segment.</span><span class="sxs-lookup"><span data-stu-id="c03ee-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="c03ee-121">Le [segment que vous avez défini dans les informations sur l’audience](segments.md) est appelé **ChurnProneCustomers** et vous prévoyez d’envoyer à ces clients la promotion par e-mail.</span><span class="sxs-lookup"><span data-stu-id="c03ee-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Capture d’écran de la page des segments avec le segment ChurnProneCustomers créé.":::

<span data-ttu-id="c03ee-123">L’e-mail d’offre que vous souhaitez envoyer contiendra le prénom, le nom et la date de fin d’abonnement du client.</span><span class="sxs-lookup"><span data-stu-id="c03ee-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="c03ee-124">Il informe les clients de la réduction qu’ils obtiendront s’ils renouvellent leur abonnement avant qu’il ne se termine.</span><span class="sxs-lookup"><span data-stu-id="c03ee-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="c03ee-125">Exporter votre audience cible</span><span class="sxs-lookup"><span data-stu-id="c03ee-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="c03ee-126">Configurer une connexion</span><span class="sxs-lookup"><span data-stu-id="c03ee-126">Configure a connection</span></span>

<span data-ttu-id="c03ee-127">Une fois notre audience cible identifiée, nous pouvons configurer l’exportation des informations sur l’audience vers un compte de stockage Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="c03ee-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="c03ee-128">Dans Audience insights, accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="c03ee-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c03ee-129">Sélectionnez **Ajouter une connexion** et choisissez **Adobe Campaign** pour configurer la connexion ou sélectionnez **Configurer** dans la vignette **Adobe Campaign**</span><span class="sxs-lookup"><span data-stu-id="c03ee-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Vignette de configuration pour Adobe Campaign Standard.":::

1. <span data-ttu-id="c03ee-131">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="c03ee-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c03ee-132">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="c03ee-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c03ee-133">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="c03ee-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c03ee-134">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="c03ee-134">Choose who can use this connection.</span></span> <span data-ttu-id="c03ee-135">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="c03ee-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c03ee-136">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c03ee-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c03ee-137">Entrez le **Nom du compte**, la **Clé du compte** et le **Conteneur** du compte de stockage Blob Azure vers lequel vous souhaitez exporter le segment.</span><span class="sxs-lookup"><span data-stu-id="c03ee-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Capture d’écran de la configuration du compte de stockage. "::: 

   - <span data-ttu-id="c03ee-139">Pour en savoir plus sur la recherche du nom et de la clé de compte de stockage Blob Azure, consultez [Gérer les paramètres du compte de stockage dans le portail Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="c03ee-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="c03ee-140">Pour savoir comment créer un conteneur, voir [Créer un conteneur](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="c03ee-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="c03ee-141">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="c03ee-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="c03ee-142">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="c03ee-142">Configure an export</span></span>

<span data-ttu-id="c03ee-143">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="c03ee-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c03ee-144">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c03ee-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c03ee-145">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="c03ee-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c03ee-146">Pour créer une nouvelle exportation, sélectionnez **Ajouter une exportation**.</span><span class="sxs-lookup"><span data-stu-id="c03ee-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="c03ee-147">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="c03ee-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="c03ee-148">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="c03ee-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c03ee-149">Choisissez le segment que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="c03ee-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="c03ee-150">Dans cet exemple, il s’agit de **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c03ee-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Capture d’écran de l’interface utilisateur de sélection de segment avec le segment ChurnProneCustomers sélectionné.":::

1. <span data-ttu-id="c03ee-152">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="c03ee-152">Select **Next**.</span></span>

1. <span data-ttu-id="c03ee-153">Maintenant, nous mappons les champs **Source** du segment des informations sur l’audience au champ **Cible** du schéma de profil Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c03ee-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mappage de champs pour le connecteur Adobe Campaign Standard.":::

   <span data-ttu-id="c03ee-155">Si vous souhaitez ajouter d’autres attributs, sélectionnez **Ajouter un attribut**.</span><span class="sxs-lookup"><span data-stu-id="c03ee-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="c03ee-156">Le nom de la cible peut être différent du nom du champ de la source, afin que vous puissiez toujours mapper la sortie du segment des informations sur l’audience à Adobe Campaign Standard si les champs ne portent pas le même nom dans les deux systèmes.</span><span class="sxs-lookup"><span data-stu-id="c03ee-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c03ee-157">L’adresse e-mail est utilisée comme champ d’identité, mais vous pouvez utiliser tout autre identificateur de votre profil client des informations sur l’audience pour mapper des données à Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c03ee-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="c03ee-158">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="c03ee-158">Select **Save**.</span></span>

<span data-ttu-id="c03ee-159">Une fois la destination d’exportation enregistrée, vous la trouverez dans **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="c03ee-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="c03ee-160">Vous pouvez maintenant [exporter le segment à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c03ee-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="c03ee-161">L'exportation sera également exécutée à chaque [actualisation planifiée](system.md).</span><span class="sxs-lookup"><span data-stu-id="c03ee-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c03ee-162">Assurez-vous que le nombre d’enregistrements dans le segment exporté se situe dans la limite autorisée de votre licence Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c03ee-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="c03ee-163">Les données exportées sont stockées dans le conteneur de stockage Blob Azure que vous avez configuré ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="c03ee-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="c03ee-164">Le chemin d’accès aux dossiers suivant est créé automatiquement dans votre conteneur :</span><span class="sxs-lookup"><span data-stu-id="c03ee-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="c03ee-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="c03ee-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="c03ee-166">Exemple : Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="c03ee-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="c03ee-167">Configurer Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c03ee-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="c03ee-168">Lorsqu’un segment des informations sur l’audience est exporté, il contient les colonnes que vous avez sélectionnées lors de la définition de la destination d’exportation à l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="c03ee-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="c03ee-169">Ces données peuvent être utilisées pour [créer des profils dans Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="c03ee-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="c03ee-170">Pour utiliser le segment dans Adobe Campaign Standard, nous devons étendre le schéma de profil dans Adobe Campaign Standard pour inclure deux champs supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="c03ee-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="c03ee-171">Découvrez comment [étendre la ressource de profil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) avec de nouveaux champs dans Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c03ee-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="c03ee-172">Dans notre exemple, ces champs sont *Nom du segment et Date du segment (facultatif).*</span><span class="sxs-lookup"><span data-stu-id="c03ee-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="c03ee-173">Nous utiliserons ces champs pour identifier les profils dans Adobe Campaign Standard que nous souhaitons cibler pour cette campagne.</span><span class="sxs-lookup"><span data-stu-id="c03ee-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="c03ee-174">S’il n’y a pas d’autres enregistrements dans Adobe Campaign Standard, autres que ceux que vous allez importer, vous pouvez ignorer cette étape.</span><span class="sxs-lookup"><span data-stu-id="c03ee-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="c03ee-175">Importer des données dans Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c03ee-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="c03ee-176">Maintenant que tout est en place, nous devons importer les données d’audience préparées à partir des informations sur l’audience dans Adobe Campaign Standard pour créer des profils.</span><span class="sxs-lookup"><span data-stu-id="c03ee-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="c03ee-177">Découvrez [comment importer des profils dans Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) en utilisant un workflow.</span><span class="sxs-lookup"><span data-stu-id="c03ee-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="c03ee-178">Le workflow d’importation dans l’image ci-dessous a été configuré pour s’exécuter toutes les 8 heures et recherche les segments des informations sur l’audience exportés (fichier .csv dans le stockage Blob Azure).</span><span class="sxs-lookup"><span data-stu-id="c03ee-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="c03ee-179">Le workflow extrait le contenu du fichier .csv dans un ordre de colonne spécifié.</span><span class="sxs-lookup"><span data-stu-id="c03ee-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="c03ee-180">Ce workflow a été conçu pour effectuer une gestion des erreurs de base et garantir que chaque enregistrement possède une adresse e-mail avant d’hydrater les données dans Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c03ee-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="c03ee-181">Le workflow extrait également le nom du segment du nom de fichier avant de les insérer dans les données de profil ACS.</span><span class="sxs-lookup"><span data-stu-id="c03ee-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Capture d’écran d’un workflow d’importation dans l’interface utilisateur d’Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="c03ee-183">Récupérer l’audience dans Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c03ee-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="c03ee-184">Une fois les données importées dans Adobe Campaign Standard, vous [pouvez créer un workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) et [interroger](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) les clients en fonction des données *Nom du segment* et *Date du segment* pour sélectionner les profils identifiés pour notre exemple de campagne.</span><span class="sxs-lookup"><span data-stu-id="c03ee-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="c03ee-185">Créer et envoyer l’e-mail à l’aide d’Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c03ee-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="c03ee-186">Créez le contenu de l’e-mail, puis [testez et envoyez](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) votre e-mail.</span><span class="sxs-lookup"><span data-stu-id="c03ee-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemple d’e-mail avec l’offre de renouvellement d’Adobe Campaign Standard.":::
