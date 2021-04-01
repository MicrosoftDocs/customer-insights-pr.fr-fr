---
title: Créer et gérer des environnements
description: Découvrez comment souscrire au service et comment gérer des environnements.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 1c2dfdd2889b5cb6c5285b4d7cc7f52a3d6de4d1
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598290"
---
# <a name="manage-environments"></a><span data-ttu-id="11851-103">Gérer des environnements</span><span class="sxs-lookup"><span data-stu-id="11851-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="11851-104">Cet article explique comment créer une nouvelle organisation et comment mettre en service un environnement.</span><span class="sxs-lookup"><span data-stu-id="11851-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="11851-105">S’inscrire et créer une organisation</span><span class="sxs-lookup"><span data-stu-id="11851-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="11851-106">Accédez au site Web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="11851-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="11851-107">Sélectionnez **Mise en route**.</span><span class="sxs-lookup"><span data-stu-id="11851-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="11851-108">Choisissez votre scénario d’inscription préféré et sélectionnez le lien correspondant.</span><span class="sxs-lookup"><span data-stu-id="11851-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="11851-109">Acceptez les conditions générales et sélectionnez **Continuer** pour commencer à créer l’organisation.</span><span class="sxs-lookup"><span data-stu-id="11851-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="11851-110">Une fois l’environnement créé, vous serez redirigé vers [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="11851-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="11851-111">Utilisez l’environnement de démonstration pour explorer l’application ou créez un nouvel environnement en suivant les étapes de la section suivante.</span><span class="sxs-lookup"><span data-stu-id="11851-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="11851-112">Après avoir spécifié les paramètres d’environnement, sélectionnez **Créer**.</span><span class="sxs-lookup"><span data-stu-id="11851-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="11851-113">Vous serez connecté une fois l’environnement créé avec succès.</span><span class="sxs-lookup"><span data-stu-id="11851-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="11851-114">Créer un environnement dans une organisation existante</span><span class="sxs-lookup"><span data-stu-id="11851-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="11851-115">Il existe deux façons de créer un environnement.</span><span class="sxs-lookup"><span data-stu-id="11851-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="11851-116">Vous pouvez soit spécifier une toute nouvelle configuration, soit copier certains paramètres de configuration à partir d’un environnement existant.</span><span class="sxs-lookup"><span data-stu-id="11851-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="11851-117">Pour créer un environnement :</span><span class="sxs-lookup"><span data-stu-id="11851-117">To create an environment:</span></span>

1. <span data-ttu-id="11851-118">Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.</span><span class="sxs-lookup"><span data-stu-id="11851-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="11851-119">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="11851-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11851-120">![Paramètres de l’environnement](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="11851-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="11851-121">Dans la boîte de dialogue **Créer un environnement**, sélectionnez **Nouvel environnement**.</span><span class="sxs-lookup"><span data-stu-id="11851-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="11851-122">Si vous souhaitez [copier les données de l’environnement actuel](#additional-considerations-for-copy-configuration-preview), sélectionnez **Copier à partir d’un environnement existant**.</span><span class="sxs-lookup"><span data-stu-id="11851-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="11851-123">Vous voyez la liste de tous les environnements disponibles dans votre organisation à partir desquels vous pouvez copier des données.</span><span class="sxs-lookup"><span data-stu-id="11851-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="11851-124">Indiquez les détails suivants :</span><span class="sxs-lookup"><span data-stu-id="11851-124">Provide the following details:</span></span>
   - <span data-ttu-id="11851-125">**Nom** : nom de cet environnement.</span><span class="sxs-lookup"><span data-stu-id="11851-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="11851-126">Ce champ est déjà rempli si vous copiez à partir d’un environnement existant, mais vous pouvez le modifier.</span><span class="sxs-lookup"><span data-stu-id="11851-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="11851-127">**Région** : Région dans laquelle le service est déployé et hébergé.</span><span class="sxs-lookup"><span data-stu-id="11851-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="11851-128">**Type** : Indiquez si vous souhaitez créer un environnement de Production ou Sandbox.</span><span class="sxs-lookup"><span data-stu-id="11851-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="11851-129">Vous pouvez éventuellement sélectionner **Paramètres avancés** :</span><span class="sxs-lookup"><span data-stu-id="11851-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="11851-130">**Enregistrer toutes les données dans** : Spécifie où vous souhaitez stocker les données de sortie générées à partir de Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="11851-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="11851-131">Vous aurez deux options : **Stockage Customer Insights** (un Azure Data Lake géré par l’équipe Customer Insights) et **Azure Data Lake Storage Gen2** (votre propre Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="11851-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="11851-132">Par défaut, l’option de stockage Customer Insights est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="11851-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="11851-133">En enregistrant des données dans Azure Data Lake Storage, vous acceptez que les données soient transférées et stockées dans l’emplacement géographique approprié pour ce compte de stockage Azure, ce qui peut différer de l’emplacement de stockage des données dans Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="11851-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="11851-134">En savoir plus sur le Microsoft Trust Center.</span><span class="sxs-lookup"><span data-stu-id="11851-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="11851-135">Actuellement, les entités ingérées sont toujours stockées dans le lac de données géré par Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="11851-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="11851-136">Nous ne prenons en charge que les comptes de stockage Azure Data Lake Gen2 situés dans la même région Azure que celle vous avez sélectionnée lors de la création de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="11851-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="11851-137">Nous prenons uniquement en charge les comptes de stockage compatibles HNS (Hierarchical Name Space) d’Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="11851-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="11851-138">Pour l’option Azure Data Lake Storage Gen2, vous pouvez choisir entre une option basée sur une ressource et une option basée sur un abonnement pour l’authentification.</span><span class="sxs-lookup"><span data-stu-id="11851-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="11851-139">Pour plus d’informations, consultez [Connecter les informations sur l’audience à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="11851-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="11851-140">Le nom du **Conteneur** ne peut pas être modifié et sera « customerinsights ».</span><span class="sxs-lookup"><span data-stu-id="11851-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="11851-141">Si vous souhaitez utiliser des [prédictions](predictions.md) ou configurer le partage de données avec des applications et des solutions basées sur Microsoft Dataverse, fournissez l’URL d’environnement Microsoft Dataverse sous **Configurer le partage de données avec Microsoft Dataverse et activer des capacités supplémentaires**.</span><span class="sxs-lookup"><span data-stu-id="11851-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="11851-142">Sélectionnez **Activer le partage de données** pour partager les données de sortie Customer Insights avec un lac de données géré Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="11851-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="11851-143">Le partage de données avec le lac de données géré Microsoft Dataverse n’est actuellement pas pris en charge lorsque vous enregistrez toutes les données dans votre propre Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="11851-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="11851-144">La [prédiction de valeurs manquantes dans une entité](predictions.md) n’est actuellement pas prise en charge lorsque vous activez le partage de données avec le lac de données géré Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="11851-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="11851-145">![Options de configuration pour activer le partage de données avec Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="11851-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="11851-146">Lorsque vous exécutez des processus, tels que l’ingestion de données ou la création de segments, les dossiers correspondants seront créés dans le compte de stockage que vous avez spécifié ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="11851-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="11851-147">Les fichiers de données et les fichiers model.json sont créés et ajoutés aux sous-dossiers respectifs en fonction du processus que vous exécutez.</span><span class="sxs-lookup"><span data-stu-id="11851-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="11851-148">Si vous créez plusieurs environnements de Customer Insights et choisissez d’enregistrer les entités de sortie de ces environnements dans votre compte de stockage, des dossiers distincts seront créés pour chaque environnement avec ci_<environmentid> dans le conteneur.</span><span class="sxs-lookup"><span data-stu-id="11851-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="11851-149">Considérations supplémentaires pour la configuration de la copie (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="11851-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="11851-150">Les paramètres de configuration suivants sont copiés :</span><span class="sxs-lookup"><span data-stu-id="11851-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="11851-151">Configurations des fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="11851-151">Feature configurations</span></span>
- <span data-ttu-id="11851-152">Sources de données ingérées/importées</span><span class="sxs-lookup"><span data-stu-id="11851-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="11851-153">Configuration de l’unification des données (mappage, correspondance, fusion)</span><span class="sxs-lookup"><span data-stu-id="11851-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="11851-154">Segments</span><span class="sxs-lookup"><span data-stu-id="11851-154">Segments</span></span>
- <span data-ttu-id="11851-155">Mesures</span><span class="sxs-lookup"><span data-stu-id="11851-155">Measures</span></span>
- <span data-ttu-id="11851-156">Relations</span><span class="sxs-lookup"><span data-stu-id="11851-156">Relationships</span></span>
- <span data-ttu-id="11851-157">Activités</span><span class="sxs-lookup"><span data-stu-id="11851-157">Activities</span></span>
- <span data-ttu-id="11851-158">Index Rechercher et filtrer</span><span class="sxs-lookup"><span data-stu-id="11851-158">Search & filter Index</span></span>
- <span data-ttu-id="11851-159">Destinations d’exportation</span><span class="sxs-lookup"><span data-stu-id="11851-159">Export destinations</span></span>
- <span data-ttu-id="11851-160">Actualisation planifiée</span><span class="sxs-lookup"><span data-stu-id="11851-160">Scheduled refresh</span></span>
- <span data-ttu-id="11851-161">Enrichissements</span><span class="sxs-lookup"><span data-stu-id="11851-161">Enrichments</span></span>
- <span data-ttu-id="11851-162">Gestion des modèles</span><span class="sxs-lookup"><span data-stu-id="11851-162">Model management</span></span>
- <span data-ttu-id="11851-163">Attributions de rôles</span><span class="sxs-lookup"><span data-stu-id="11851-163">Role assignments</span></span>

<span data-ttu-id="11851-164">Les paramètres suivants ne sont *pas* copiés :</span><span class="sxs-lookup"><span data-stu-id="11851-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="11851-165">Profils client.</span><span class="sxs-lookup"><span data-stu-id="11851-165">Customer profiles.</span></span>
- <span data-ttu-id="11851-166">Informations d’identification d’une source de données.</span><span class="sxs-lookup"><span data-stu-id="11851-166">Data source credentials.</span></span> <span data-ttu-id="11851-167">Vous devrez fournir les informations d’identification pour chaque source de données et actualiser les sources de données manuellement.</span><span class="sxs-lookup"><span data-stu-id="11851-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="11851-168">Sources de données du dossier Common Data Model et du lac géré Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="11851-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="11851-169">Vous devez créer ces sources de données manuellement avec le même nom que dans l’environnement source.</span><span class="sxs-lookup"><span data-stu-id="11851-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="11851-170">Lorsque vous copiez un environnement, vous voyez un message de confirmation de création du nouvel environnement.</span><span class="sxs-lookup"><span data-stu-id="11851-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="11851-171">Sélectionnez **Accéder aux sources de données** pour voir la liste des sources de données.</span><span class="sxs-lookup"><span data-stu-id="11851-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="11851-172">Toutes les sources de données affichent un statut **Identifiants requis**.</span><span class="sxs-lookup"><span data-stu-id="11851-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="11851-173">Modifiez les sources de données et entrez les informations d’identification pour les actualiser.</span><span class="sxs-lookup"><span data-stu-id="11851-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11851-174">![Sources de données copiées](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="11851-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="11851-175">Après avoir actualisé les sources de données, accédez à **Données** > **Unifier**.</span><span class="sxs-lookup"><span data-stu-id="11851-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="11851-176">Vous trouverez ici les paramètres de l’environnement source.</span><span class="sxs-lookup"><span data-stu-id="11851-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="11851-177">Modifiez-les selon vos besoins ou sélectionnez **Exécuter** pour démarrer le processus d’unification des données et créer l’entité client unifiée.</span><span class="sxs-lookup"><span data-stu-id="11851-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="11851-178">Une fois l’unification des données terminée, accédez à **Mesures** et **Segments** pour les actualiser.</span><span class="sxs-lookup"><span data-stu-id="11851-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="11851-179">Modifier un environnement existant</span><span class="sxs-lookup"><span data-stu-id="11851-179">Edit an existing environment</span></span>

<span data-ttu-id="11851-180">Vous pouvez modifier certains détails des environnements existants.</span><span class="sxs-lookup"><span data-stu-id="11851-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="11851-181">Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.</span><span class="sxs-lookup"><span data-stu-id="11851-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="11851-182">Sélectionnez l’icône **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="11851-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="11851-183">Dans la zone **Modifier l’environnement**, vous pouvez mettre à jour le **Nom d’affichage** de l’environnement, mais vous ne pouvez pas changer la **Région** ou le **Type**.</span><span class="sxs-lookup"><span data-stu-id="11851-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="11851-184">Si un environnement est configuré pour stocker des données dans Azure Data Lake Storage Gen2, vous pouvez mettre à jour la **Clé de compte**.</span><span class="sxs-lookup"><span data-stu-id="11851-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="11851-185">Cependant, vous ne pouvez pas modifier le **Nom du compte** ou le nom **Conteneur**.</span><span class="sxs-lookup"><span data-stu-id="11851-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="11851-186">Vous pouvez éventuellement mettre à jour une connexion basée sur une clé de compte vers une connexion basée sur une ressource ou un abonnement.</span><span class="sxs-lookup"><span data-stu-id="11851-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="11851-187">Une fois mise à niveau, vous ne pouvez pas rétablir la clé de compte après la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="11851-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="11851-188">Pour plus d’informations, consultez [Connecter les informations sur l’audience à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="11851-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="11851-189">Vous ne pouvez pas modifier les informations du **Conteneur** lors de la mise à jour de la connexion.</span><span class="sxs-lookup"><span data-stu-id="11851-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="11851-190">Réinitialiser un environnement existant</span><span class="sxs-lookup"><span data-stu-id="11851-190">Reset an existing environment</span></span>

<span data-ttu-id="11851-191">En tant qu’administrateur, vous pouvez réinitialiser un environnement à un état vide si vous souhaitez supprimer toutes les configurations et supprimer les données ingérées.</span><span class="sxs-lookup"><span data-stu-id="11851-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="11851-192">Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.</span><span class="sxs-lookup"><span data-stu-id="11851-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="11851-193">Sélectionnez l’environnement à réinitialiser, puis les points de suspension **...**.</span><span class="sxs-lookup"><span data-stu-id="11851-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="11851-194">Choisissez l’option **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="11851-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="11851-195">Pour confirmer la suppression, entrez le nom de l’environnement et sélectionnez **Réinitialiser**.</span><span class="sxs-lookup"><span data-stu-id="11851-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="11851-196">Supprimer un environnement existant (disponible uniquement pour les administrateurs)</span><span class="sxs-lookup"><span data-stu-id="11851-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="11851-197">En tant qu’administrateur, vous pouvez supprimer un environnement que vous administrez.</span><span class="sxs-lookup"><span data-stu-id="11851-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="11851-198">Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.</span><span class="sxs-lookup"><span data-stu-id="11851-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="11851-199">Sélectionnez l’environnement à réinitialiser, puis les points de suspension **...**.</span><span class="sxs-lookup"><span data-stu-id="11851-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="11851-200">Choisissez l’option **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="11851-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="11851-201">Pour confirmer la suppression, sélectionnez le nom de l’environnement et sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="11851-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]