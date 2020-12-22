---
title: Se connecter à un compte Azure Data Lake Storage Gen2 avec un principal de service
description: Utilisez un principal de service Azure pour Audience Insights pour vous connecter à votre propre lac de données lorsque vous l'associez à Audience Insights.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644085"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="2bb2f-103">Se connecter à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure pour Audience Insights</span><span class="sxs-lookup"><span data-stu-id="2bb2f-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="2bb2f-104">Les outils automatisés qui utilisent les services Azure doivent toujours avoir des autorisations restreintes.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="2bb2f-105">Au lieu que les applications se connectent en tant qu'utilisateur entièrement privilégié, Azure propose des principaux de service.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="2bb2f-106">Lisez cet article pour savoir comment connecter Audience Insights avec un compte Azure Data Lake Storage Gen2 en utilisant un principal de service Azure au lieu de clés de compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="2bb2f-107">Vous pouvez utiliser le principal du service pour [ajouter ou modifier un dossier Common Data Model comme source de données](connect-common-data-model.md) ou [créer un nouvel environnement ou mettre à jour un environnement existant](manage-environments.md#create-an-environment-in-an-existing-organization) en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="2bb2f-108">Des autorisations administrateur pour votre abonnement Azure sont nécessaires pour créer le principal de service.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="2bb2f-109">Créer un principal de service Azure pour Audience Insights</span><span class="sxs-lookup"><span data-stu-id="2bb2f-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="2bb2f-110">Avant de créer un nouveau principal de service pour Audience Insights, vérifiez s'il existe déjà dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="2bb2f-111">Rechercher un principal de service existant</span><span class="sxs-lookup"><span data-stu-id="2bb2f-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="2bb2f-112">Accédez au [Portail d'administration Azure](https://portal.azure.com) et connectez-vous à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="2bb2f-113">Sélectionnez **Azure Active Directory** dans les services Azure.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="2bb2f-114">Sous **Gérer**, sélectionnez **Applications d'entreprise**.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="2bb2f-115">Recherchez l'ID de l'application interne Audience Insights `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ou le nom `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="2bb2f-116">Si vous trouvez un enregistrement correspondant, cela signifie que le principal de service pour Audience Insights existe.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="2bb2f-117">Il n'est pas nécessaire de le créer à nouveau.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Capture d'écran illustrant le principal de service existant.":::
   
6. <span data-ttu-id="2bb2f-119">Si aucun résultat n'est renvoyé, créez un nouveau principal de service.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="2bb2f-120">Créer un nouveau principal de service</span><span class="sxs-lookup"><span data-stu-id="2bb2f-120">Create a new service principal</span></span>

1. <span data-ttu-id="2bb2f-121">Installez la dernière version de **Azure Active Directory PowerShell for Graph**.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="2bb2f-122">Pour plus d'informations, consultez [Installer Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="2bb2f-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="2bb2f-123">Sur votre PC, sélectionnez la touche Windows du clavier et recherchez **Windows PowerShell** et **Exécuter en tant qu'administrateur**.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="2bb2f-124">Dans la fenêtre PowerShell qui s'ouvre, entrez `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="2bb2f-125">Créez le principal de service pour Audience Insights avec le module Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="2bb2f-126">Dans la fenêtre PowerShell, entrez `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="2bb2f-127">Remplacez « votre ID de client » par l'ID réel du client sur lequel vous souhaitez créer le principal de service.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="2bb2f-128">Le paramètre de nom d'environnement `AzureEnvironmentName` est facultatif.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="2bb2f-129">Entrez `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="2bb2f-130">Cette commande crée le principal de service pour Audience Insights sur le client sélectionné.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="2bb2f-131">Accorder des autorisations au principal de service pour accéder au compte de stockage</span><span class="sxs-lookup"><span data-stu-id="2bb2f-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="2bb2f-132">Accédez au portail Azure pour accorder des autorisations au principal de service pour le compte de stockage que vous souhaitez utiliser dans Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="2bb2f-133">Accédez au [Portail d'administration Azure](https://portal.azure.com) et connectez-vous à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="2bb2f-134">Ouvrez le compte de stockage auquel vous souhaitez que le principal de service pour Audience Insights puisse accéder.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="2bb2f-135">Sélectionnez **Contrôle d'accès (IAM)** dans le volet de navigation et sélectionnez **Ajouter** > **Ajouter une attribution de rôle**.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Capture d'écran illustrant le portail Azure lors de l'ajout d'une attribution de rôle.":::
   
1. <span data-ttu-id="2bb2f-137">Dans le volet **Ajouter une attribution de rôle**, définissez les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="2bb2f-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="2bb2f-138">Rôle : *Contributeur de données Blob de stockage*</span><span class="sxs-lookup"><span data-stu-id="2bb2f-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="2bb2f-139">Attribuer l'accès à : *Utilisateur, groupe ou principal de service*</span><span class="sxs-lookup"><span data-stu-id="2bb2f-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="2bb2f-140">Sélectionner : *Dynamics 365 AI for Customer Insights* (le [principal de service que vous avez créé](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="2bb2f-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="2bb2f-141">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-141">Select **Save**.</span></span>

<span data-ttu-id="2bb2f-142">La propagation des modifications peut prendre jusqu'à 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="2bb2f-143">Entrez l'ID de ressource Azure ou les détails de l'abonnement Azure dans la pièce jointe à Audience Insights du compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="2bb2f-144">Associez un compte de stockage Azure Data Lake à Audience Insights pour [stocker les données de sortie](manage-environments.md) ou [l'utiliser comme source de données](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="2bb2f-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="2bb2f-145">Le choix de l'option Azure Data Lake vous permet de choisir entre une approche basée sur une ressource ou une approche basée sur un abonnement.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="2bb2f-146">Suivez les étapes ci-dessous pour fournir les informations requises sur l'approche sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="2bb2f-147">Connexion du compte de stockage basée sur des ressources</span><span class="sxs-lookup"><span data-stu-id="2bb2f-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="2bb2f-148">Accédez au [Portail d'administration Azure](https://portal.azure.com), connectez-vous à votre abonnement et ouvrez le compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="2bb2f-149">Accédez à **Paramètres** > **Propriétés** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="2bb2f-150">Copiez la valeur de l'ID de ressource du compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copiez l'ID de ressource du compte de stockage.":::

1. <span data-ttu-id="2bb2f-152">Dans Audience Insights, insérez l'ID de ressource dans le champ de ressource affiché dans l'écran de connexion du compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Entrez les informations sur l'ID de ressource du compte de stockage.":::   
   
1. <span data-ttu-id="2bb2f-154">Poursuivez avec les étapes restantes dans Audience Insights pour associer le compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="2bb2f-155">Connexion du compte de stockage basée sur un abonnement</span><span class="sxs-lookup"><span data-stu-id="2bb2f-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="2bb2f-156">Accédez au [Portail d'administration Azure](https://portal.azure.com), connectez-vous à votre abonnement et ouvrez le compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="2bb2f-157">Accédez à **Paramètres** > **Propriétés** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="2bb2f-158">Passez en revue les champs **Abonnement**, **Groupe de ressources** et **Nom** du compte de stockage pour vous assurer de sélectionner les valeurs appropriées dans Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="2bb2f-159">Dans Audience Insights, choisissez les valeurs des champs correspondants lors de l'association du compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Entrez les informations sur l'ID de ressource du compte de stockage.":::
   
1. <span data-ttu-id="2bb2f-161">Poursuivez avec les étapes restantes dans Audience Insights pour associer le compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
