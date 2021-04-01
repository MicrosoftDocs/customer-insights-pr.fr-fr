---
title: Se connecter à un compte Azure Data Lake Storage Gen2 avec un principal de service
description: Utilisez un principal de service Azure pour les informations sur l’audience pour vous connecter à votre propre lac de données lorsque vous l’associez aux informations sur l’audience.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596496"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="d9fee-103">Se connecter à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure pour les informations sur l’audience</span><span class="sxs-lookup"><span data-stu-id="d9fee-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="d9fee-104">Les outils automatisés qui utilisent les services Azure doivent toujours avoir des autorisations restreintes.</span><span class="sxs-lookup"><span data-stu-id="d9fee-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="d9fee-105">Au lieu que les applications se connectent en tant qu’utilisateur entièrement privilégié, Azure propose des principaux de service.</span><span class="sxs-lookup"><span data-stu-id="d9fee-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="d9fee-106">Lisez cet article pour savoir comment connecter les informations sur l’audience avec un compte Azure Data Lake Storage Gen2 en utilisant un principal de service Azure au lieu de clés de compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="d9fee-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="d9fee-107">Vous pouvez utiliser le principal du service pour [ajouter ou modifier un dossier Common Data Model comme source de données](connect-common-data-model.md) ou [créer un nouvel environnement ou mettre à jour un environnement existant](manage-environments.md#create-an-environment-in-an-existing-organization) en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="d9fee-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="d9fee-108">Le compte de stockage Azure Data Lake Gen2 qui prévoit d’utiliser le principal de service doit avoir un [Espace de nom hiérarchique activé](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="d9fee-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="d9fee-109">Des autorisations administrateur pour votre abonnement Azure sont nécessaires pour créer le principal de service.</span><span class="sxs-lookup"><span data-stu-id="d9fee-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="d9fee-110">Créer un principal de service Azure pour les informations sur l’audience</span><span class="sxs-lookup"><span data-stu-id="d9fee-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="d9fee-111">Avant de créer un nouveau principal de service pour les informations sur l’audience, vérifiez s’il existe déjà dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d9fee-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="d9fee-112">Rechercher un principal de service existant</span><span class="sxs-lookup"><span data-stu-id="d9fee-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="d9fee-113">Accédez au [Portail d’administration Azure](https://portal.azure.com) et connectez-vous à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d9fee-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="d9fee-114">Sélectionnez **Azure Active Directory** dans les services Azure.</span><span class="sxs-lookup"><span data-stu-id="d9fee-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="d9fee-115">Sous **Gérer**, sélectionnez **Applications d’entreprise**.</span><span class="sxs-lookup"><span data-stu-id="d9fee-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="d9fee-116">Recherchez l’ID de l’application interne des informations sur l’audience `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ou le nom `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="d9fee-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="d9fee-117">Si vous trouvez un enregistrement correspondant, cela signifie que le principal de service pour les informations sur l’audience existe.</span><span class="sxs-lookup"><span data-stu-id="d9fee-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="d9fee-118">Il n’est pas nécessaire de le créer à nouveau.</span><span class="sxs-lookup"><span data-stu-id="d9fee-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Capture d’écran illustrant le principal de service existant.":::
   
6. <span data-ttu-id="d9fee-120">Si aucun résultat n’est renvoyé, créez un nouveau principal de service.</span><span class="sxs-lookup"><span data-stu-id="d9fee-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="d9fee-121">Créer un nouveau principal de service</span><span class="sxs-lookup"><span data-stu-id="d9fee-121">Create a new service principal</span></span>

1. <span data-ttu-id="d9fee-122">Installez la dernière version de **Azure Active Directory PowerShell for Graph**.</span><span class="sxs-lookup"><span data-stu-id="d9fee-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="d9fee-123">Pour plus d’informations, consultez [Installer Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="d9fee-123">For more information, see [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="d9fee-124">Sur votre PC, sélectionnez la touche Windows du clavier et recherchez **Windows PowerShell** et **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="d9fee-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="d9fee-125">Dans la fenêtre PowerShell qui s’ouvre, entrez `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="d9fee-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="d9fee-126">Créez le principal de service pour les informations sur l’audience avec le module Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9fee-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="d9fee-127">Dans la fenêtre PowerShell, entrez `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="d9fee-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="d9fee-128">Remplacez « votre ID de client » par l’ID réel du client sur lequel vous souhaitez créer le principal de service.</span><span class="sxs-lookup"><span data-stu-id="d9fee-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="d9fee-129">Le paramètre de nom d’environnement `AzureEnvironmentName` est facultatif.</span><span class="sxs-lookup"><span data-stu-id="d9fee-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="d9fee-130">Entrez `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="d9fee-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="d9fee-131">Cette commande crée le principal de service pour les informations sur l’audience sur le client sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d9fee-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="d9fee-132">Accorder des autorisations au principal de service pour accéder au compte de stockage</span><span class="sxs-lookup"><span data-stu-id="d9fee-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="d9fee-133">Accédez au portail Azure pour accorder des autorisations au principal de service pour le compte de stockage que vous souhaitez utiliser dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="d9fee-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="d9fee-134">Accédez au [Portail d’administration Azure](https://portal.azure.com) et connectez-vous à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d9fee-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="d9fee-135">Ouvrez le compte de stockage auquel vous souhaitez que le principal de service pour les informations sur l’audience puisse accéder.</span><span class="sxs-lookup"><span data-stu-id="d9fee-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="d9fee-136">Sélectionnez **Contrôle d’accès (IAM)** dans le volet de navigation et sélectionnez **Ajouter** > **Ajouter une attribution de rôle**.</span><span class="sxs-lookup"><span data-stu-id="d9fee-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Capture d’écran illustrant le portail Azure lors de l’ajout d’une attribution de rôle.":::
   
1. <span data-ttu-id="d9fee-138">Dans le volet **Ajouter une attribution de rôle**, définissez les propriétés suivantes :</span><span class="sxs-lookup"><span data-stu-id="d9fee-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="d9fee-139">Rôle : *Contributeur de données Blob de stockage*</span><span class="sxs-lookup"><span data-stu-id="d9fee-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="d9fee-140">Attribuer l’accès à : *Utilisateur, groupe ou principal de service*</span><span class="sxs-lookup"><span data-stu-id="d9fee-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="d9fee-141">Sélectionner : *Dynamics 365 AI for Customer Insights* (le [principal de service que vous avez créé](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="d9fee-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="d9fee-142">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d9fee-142">Select **Save**.</span></span>

<span data-ttu-id="d9fee-143">La propagation des modifications peut prendre jusqu’à 15 minutes.</span><span class="sxs-lookup"><span data-stu-id="d9fee-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="d9fee-144">Entrez l’ID de ressource Azure ou les détails de l’abonnement Azure dans la pièce jointe aux informations sur l’audience du compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="d9fee-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="d9fee-145">Associez un compte de stockage Azure Data Lake aux informations sur l’audience pour [stocker les données de sortie](manage-environments.md) ou [l’utiliser comme source de données](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="d9fee-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="d9fee-146">Le choix de l’option Azure Data Lake vous permet de choisir entre une approche basée sur une ressource ou une approche basée sur un abonnement.</span><span class="sxs-lookup"><span data-stu-id="d9fee-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="d9fee-147">Suivez les étapes ci-dessous pour fournir les informations requises sur l’approche sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d9fee-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="d9fee-148">Connexion du compte de stockage basée sur des ressources</span><span class="sxs-lookup"><span data-stu-id="d9fee-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="d9fee-149">Accédez au [Portail d’administration Azure](https://portal.azure.com), connectez-vous à votre abonnement et ouvrez le compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="d9fee-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="d9fee-150">Accédez à **Paramètres** > **Propriétés** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="d9fee-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="d9fee-151">Copiez la valeur de l’ID de ressource du compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="d9fee-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copiez l’ID de ressource du compte de stockage.":::

1. <span data-ttu-id="d9fee-153">Dans les informations sur l’audience, insérez l’ID de ressource dans le champ de ressource affiché dans l’écran de connexion du compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="d9fee-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Entrez les informations sur l’ID de ressource du compte de stockage.":::   
   
1. <span data-ttu-id="d9fee-155">Poursuivez avec les étapes restantes dans les informations sur l’audience pour associer le compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="d9fee-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="d9fee-156">Connexion du compte de stockage basée sur un abonnement</span><span class="sxs-lookup"><span data-stu-id="d9fee-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="d9fee-157">Accédez au [Portail d’administration Azure](https://portal.azure.com), connectez-vous à votre abonnement et ouvrez le compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="d9fee-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="d9fee-158">Accédez à **Paramètres** > **Propriétés** dans le volet de navigation.</span><span class="sxs-lookup"><span data-stu-id="d9fee-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="d9fee-159">Passez en revue les champs **Abonnement**, **Groupe de ressources** et **Nom** du compte de stockage pour vous assurer de sélectionner les valeurs appropriées dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="d9fee-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="d9fee-160">Dans les informations sur l’audience, choisissez les valeurs des champs correspondants lors de l’association du compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="d9fee-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="d9fee-161">Poursuivez avec les étapes restantes dans les informations sur l’audience pour associer le compte de stockage.</span><span class="sxs-lookup"><span data-stu-id="d9fee-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]