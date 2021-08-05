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
ms.openlocfilehash: cc94ad49f12067d513db4663bff60620d6501eb0
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692110"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Se connecter à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure pour les informations sur l’audience

Les outils automatisés qui utilisent les services Azure doivent toujours avoir des autorisations restreintes. Au lieu que les applications se connectent en tant qu’utilisateur entièrement privilégié, Azure propose des principaux de service. Lisez cet article pour savoir comment connecter les informations sur l’audience avec un compte Azure Data Lake Storage Gen2 en utilisant un principal de service Azure au lieu de clés de compte de stockage. 

Vous pouvez utiliser le principal du service pour [ajouter ou modifier un dossier Common Data Model comme source de données](connect-common-data-model.md) ou [créer un nouvel environnement ou mettre à jour un environnement existant](get-started-paid.md) en toute sécurité.

> [!IMPORTANT]
> - Le compte de stockage Azure Data Lake Gen2 qui prévoit d’utiliser le principal de service doit avoir un [Espace de nom hiérarchique activé](/azure/storage/blobs/data-lake-storage-namespace).
> - Des autorisations administrateur pour votre abonnement Azure sont nécessaires pour créer le principal de service.

## <a name="create-azure-service-principal-for-audience-insights"></a>Créer un principal de service Azure pour les informations sur l’audience

Avant de créer un nouveau principal de service pour les informations sur l’audience, vérifiez s’il existe déjà dans votre organisation.

### <a name="look-for-an-existing-service-principal"></a>Rechercher un principal de service existant

1. Accédez au [Portail d’administration Azure](https://portal.azure.com) et connectez-vous à votre organisation.

2. Sélectionnez **Azure Active Directory** dans les services Azure.

3. Sous **Gérer**, sélectionnez **Applications d’entreprise**.

4. Recherchez l’ID de l’application interne des informations sur l’audience `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ou le nom `Dynamics 365 AI for Customer Insights`.

5. Si vous trouvez un enregistrement correspondant, cela signifie que le principal de service pour les informations sur l’audience existe. Il n’est pas nécessaire de le créer à nouveau.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Capture d’écran illustrant le principal de service existant.":::
   
6. Si aucun résultat n’est renvoyé, créez un nouveau principal de service.

### <a name="create-a-new-service-principal"></a>Créer un nouveau principal de service

1. Installez la dernière version de **Azure Active Directory PowerShell for Graph**. Pour plus d’informations, consultez [Installer Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   - Sur votre PC, sélectionnez la touche Windows du clavier et recherchez **Windows PowerShell** et **Exécuter en tant qu’administrateur**.
   
   - Dans la fenêtre PowerShell qui s’ouvre, entrez `Install-Module AzureAD`.

2. Créez le principal de service pour les informations sur l’audience avec le module Azure AD PowerShell.
   - Dans la fenêtre PowerShell, entrez `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Remplacez « votre ID de client » par l’ID réel du client sur lequel vous souhaitez créer le principal de service. Le paramètre de nom d’environnement `AzureEnvironmentName` est facultatif.
  
   - Entrez `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Cette commande crée le principal de service pour les informations sur l’audience sur le client sélectionné.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Accorder des autorisations au principal de service pour accéder au compte de stockage

Accédez au portail Azure pour accorder des autorisations au principal de service pour le compte de stockage que vous souhaitez utiliser dans les informations sur l’audience.

1. Accédez au [Portail d’administration Azure](https://portal.azure.com) et connectez-vous à votre organisation.

1. Ouvrez le compte de stockage auquel vous souhaitez que le principal de service pour les informations sur l’audience puisse accéder.

1. Sélectionnez **Contrôle d’accès (IAM)** dans le volet de navigation et sélectionnez **Ajouter** > **Ajouter une attribution de rôle**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Capture d’écran illustrant le portail Azure lors de l’ajout d’une attribution de rôle.":::
   
1. Dans le volet **Ajouter une attribution de rôle**, définissez les propriétés suivantes :
   - Rôle : *Contributeur de données Blob de stockage*
   - Attribuer l’accès à : *Utilisateur, groupe ou principal de service*
   - Sélectionner : *Dynamics 365 AI for Customer Insights* (le [principal de service que vous avez créé](#create-a-new-service-principal))

1.  Sélectionnez **Enregistrer**.

La propagation des modifications peut prendre jusqu’à 15 minutes.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Entrez l’ID de ressource Azure ou les détails de l’abonnement Azure dans la pièce jointe aux informations sur l’audience du compte de stockage.

Associez un compte de stockage Azure Data Lake aux informations sur l’audience pour [stocker les données de sortie](manage-environments.md) ou [l’utiliser comme source de données](connect-dataverse-managed-lake.md). Le choix de l’option Azure Data Lake vous permet de choisir entre une approche basée sur une ressource ou une approche basée sur un abonnement.

Suivez les étapes ci-dessous pour fournir les informations requises sur l’approche sélectionnée.

### <a name="resource-based-storage-account-connection"></a>Connexion du compte de stockage basée sur des ressources

1. Accédez au [Portail d’administration Azure](https://portal.azure.com), connectez-vous à votre abonnement et ouvrez le compte de stockage.

1. Accédez à **Paramètres** > **Propriétés** dans le volet de navigation.

1. Copiez la valeur de l’ID de ressource du compte de stockage.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copiez l’ID de ressource du compte de stockage.":::

1. Dans les informations sur l’audience, insérez l’ID de ressource dans le champ de ressource affiché dans l’écran de connexion du compte de stockage.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Entrez les informations sur l’ID de ressource du compte de stockage.":::   
   
1. Poursuivez avec les étapes restantes dans les informations sur l’audience pour associer le compte de stockage.

### <a name="subscription-based-storage-account-connection"></a>Connexion du compte de stockage basée sur un abonnement

1. Accédez au [Portail d’administration Azure](https://portal.azure.com), connectez-vous à votre abonnement et ouvrez le compte de stockage.

1. Accédez à **Paramètres** > **Propriétés** dans le volet de navigation.

1. Passez en revue les champs **Abonnement**, **Groupe de ressources** et **Nom** du compte de stockage pour vous assurer de sélectionner les valeurs appropriées dans les informations sur l’audience.

1. Dans les informations sur l’audience, choisissez les valeurs des champs correspondants lors de l’association du compte de stockage.
   
1. Poursuivez avec les étapes restantes dans les informations sur l’audience pour associer le compte de stockage.


[!INCLUDE[footer-include](../includes/footer-banner.md)]