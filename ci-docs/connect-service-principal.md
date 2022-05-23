---
title: Se connecter à un compte Azure Data Lake Storage en utilisant un principal de service
description: Utilisez un principal de service Azure pour vous connecter à votre lac de données personnel.
ms.date: 04/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 776eee79c25edbd40ed119510a314f5126933c3e
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8739159"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Se connecter à un compte Azure Data Lake Storage en utilisant un principal de service Azure

Cet article décrit comment connecter Dynamics 365 Customer Insights à un compte Azure Data Lake Storage en utilisant un principal de service Azure au lieu de clés de compte de stockage. 

Les outils automatisés qui utilisent les services Azure doivent toujours avoir des autorisations restreintes. Au lieu que les applications se connectent en tant qu’utilisateur entièrement privilégié, Azure propose des principaux de service. Vous pouvez utiliser les principaux de service pour [ajouter ou modifier un dossier Common Data Model en tant que source de données](connect-common-data-model.md) ou [créer ou mettre à jour un environnement](create-environment.md) en toute sécurité.

> [!IMPORTANT]
> - Le compte Data Lake Storage qui utilisera le principal de service doit être Gen2 et avoir [l’espace de noms hiérarchique activé](/azure/storage/blobs/data-lake-storage-namespace). Les comptes de stockage Azure Data Lake Gen1 ne sont pas pris en charge.
> - Des autorisations administrateur pour votre abonnement Azure sont nécessaires pour créer un principal de service.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Créer un principal de service Azure pour Customer Insights

Avant de créer un nouveau principal de service pour Customer Insights, vérifiez s’il existe déjà dans votre organisation.

### <a name="look-for-an-existing-service-principal"></a>Rechercher un principal de service existant

1. Accédez au [Portail d’administration Azure](https://portal.azure.com) et connectez-vous à votre organisation.

2. Dans **Services Azure**, sélectionnez **Azure Active Directory**.

3. Sous **Gérer**, sélectionnez **Applications d’entreprise**.

4. Ajoutez un filtre pour **L’ID application commence par** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ou recherchez le nom `Dynamics 365 AI for Customer Insights`.

5. Si vous trouvez un enregistrement correspondant, cela signifie que le principal de service existe déjà. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Capture d’écran montrant un principal de service existant.":::
   
6. Si aucun résultat n’est renvoyé, créez un nouveau principal de service.

### <a name="create-a-new-service-principal"></a>Créer un nouveau principal de service

1. Installez la dernière version d’Azure Active Directory PowerShell for Graph. Pour plus d’informations, accédez à [Installer Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Sur votre PC, sélectionnez la touche Windows du clavier et recherchez **Windows PowerShell**, puis sélectionnez **Exécuter en tant qu’administrateur**.
   
   1. Dans la fenêtre PowerShell qui s’ouvre, entrez `Install-Module AzureAD`.

2. Créez le principal de service pour Customer Insights avec le module Azure AD PowerShell.

   1. Dans la fenêtre PowerShell, entrez `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Remplacez *[votre ID de répertoire]* par l’ID de répertoire réel de votre abonnement Azure où vous souhaitez créer le principal de service. Le paramètre de nom d’environnement, `AzureEnvironmentName`, est facultatif.
  
   1. Entrez `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Cette commande crée le principal de service pour Customer Insights dans l’abonnement Azure sélectionné. 

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Accorder des autorisations au principal de service pour accéder au compte de stockage

Accédez au portail Azure pour accorder des autorisations au principal de service pour le compte de stockage que vous souhaitez utiliser dans Customer Insights.

1. Accédez au [Portail d’administration Azure](https://portal.azure.com) et connectez-vous à votre organisation.

1. Ouvrez le compte de stockage auquel vous souhaitez que le principal de service pour Customer Insights ait accès.

1. Dans le volet de gauche, sélectionnez **Contrôle d’accès (IAM)**, puis sélectionnez **Ajouter** > **Ajouter une attribution de rôle**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Capture d’écran montrant le portail Azure lors de l’ajout d’une attribution de rôle.":::

1. Dans le volet **Ajouter une attribution de rôle**, définissez les propriétés suivantes :
   - Rôle : **Contributeur de données Blob de stockage**
   - Attribuer l’accès à : **Utilisateur, groupe ou principal de service**
   - Sélectionnez les membres : **Dynamics 365 AI for Customer Insights** (le [principal de service](#create-a-new-service-principal) que vous avez créé précédemment dans cette procédure)

1.  Sélectionnez **Examiner + Attribuer**.

La propagation des modifications peut prendre jusqu’à 15 minutes.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Entrez l’ID de ressource Azure ou les détails de l’abonnement Azure dans la pièce jointe au compte de stockage dans Customer Insights

Vous pouvez associer un compte Data Lake Storage dans Customer Insights pour [stocker les données de sortie](manage-environments.md) ou [l’utiliser comme source de données](connect-dataverse-managed-lake.md). Cette option permet de choisir entre une approche basée sur les ressources ou basée sur l’abonnement. Selon l’approche choisie, suivez la procédure décrite dans l’une des sections suivantes.

### <a name="resource-based-storage-account-connection"></a>Connexion du compte de stockage basée sur des ressources

1. Accédez au [portail d’administration Azure](https://portal.azure.com), connectez-vous à votre abonnement et ouvrez le compte de stockage.

1. Dans le volet de gauche, accédez à **Paramètres** > **Propriétés**.

1. Copiez la valeur de l’ID de ressource du compte de stockage.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copiez l’ID de ressource du compte de stockage.":::

1. Dans Customer Insights, insérez l’ID de ressource dans le champ de ressource affiché sur l’écran de connexion au compte de stockage.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Entrez les informations sur l’ID de ressource du compte de stockage.":::   

1. Continuez avec les étapes restantes dans Customer Insights pour associer le compte de stockage.

### <a name="subscription-based-storage-account-connection"></a>Connexion du compte de stockage basée sur un abonnement

1. Accédez au [portail d’administration Azure](https://portal.azure.com), connectez-vous à votre abonnement et ouvrez le compte de stockage.

1. Dans le volet de gauche, accédez à **Paramètres** > **Propriétés**.

1. Passez en revue l’**Abonnement**, le **Groupe de ressources** et le **Nom** du compte de stockage pour vous assurer de sélectionner les valeurs correctes dans Customer Insights.

1. Dans Customer Insights, choisissez les valeurs des champs correspondants lorsque vous associez le compte de stockage.

1. Continuez avec les étapes restantes dans Customer Insights pour associer le compte de stockage.


[!INCLUDE [footer-include](includes/footer-banner.md)]