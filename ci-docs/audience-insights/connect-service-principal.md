---
title: Se connecter à un compte Azure Data Lake Storage en utilisant un principal de service
description: Utilisez un principal de service Azure pour vous connecter à votre lac de données personnel.
ms.date: 09/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b901d799dbd73841a6ddbae754c4e4275f61146a
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645169"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Se connecter à un compte Azure Data Lake Storage en utilisant un principal de service Azure

Les outils automatisés qui utilisent les services Azure doivent toujours avoir des autorisations restreintes. Au lieu que les applications se connectent en tant qu’utilisateur entièrement privilégié, Azure propose des principaux de service. Lisez la suite pour savoir comment connecter Dynamics 365 Customer Insights à un compte Azure Data Lake Storage en utilisant un principal de service Azure à la place de clés de compte de stockage. 

Utilisez le principal du service pour [ajouter ou modifier un dossier Common Data Model en tant que source de données](connect-common-data-model.md) de manière sécurisée ou pour [créer ou mettre à jour un environnement](create-environment.md).

> [!IMPORTANT]
> - Le compte Data Lake Storage qui utilisera le principal de service doit avoir [activé l’espace de noms hiérarchique](/azure/storage/blobs/data-lake-storage-namespace).
> - Des autorisations administrateur pour votre abonnement Azure sont nécessaires pour créer le principal de service.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Créer un principal de service Azure pour Customer Insights

Avant de créer un principal de service pour les informations sur l’audience ou pour les informations sur l’engagement, vérifiez s’il existe déjà dans l’organisation.

### <a name="look-for-an-existing-service-principal"></a>Rechercher un principal de service existant

1. Accédez au [Portail d’administration Azure](https://portal.azure.com) et connectez-vous à votre organisation.

2. Dans **Services Azure**, sélectionnez **Azure Active Directory**.

3. Sous **Gérer**, sélectionnez **Applications d’entreprise**.

4. Recherchez l’ID de l’application Microsoft :
   - Informations sur l’audience : `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` avec le nom `Dynamics 365 AI for Customer Insights`
   - Informations sur l’engagement : `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` avec le nom `Dynamics 365 AI for Customer Insights engagement insights`

5. Si vous trouvez un enregistrement correspondant, cela signifie que le principal de service existe déjà. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Capture d’écran montrant un principal de service existant.":::
   
6. Si aucun résultat n’est renvoyé, créez un nouveau principal de service.

>[!NOTE]
>Pour utiliser pleinement le potentiel de Dynamics 365 Customer Insights, nous vous suggérons d’ajouter les deux applications au principal de service.

### <a name="create-a-new-service-principal"></a>Créer un nouveau principal de service

1. Installez la dernière version d’Azure Active Directory PowerShell for Graph. Pour plus d’informations, accédez à [Installer Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Sur votre PC, sélectionnez la touche Windows du clavier et recherchez **Windows PowerShell**, puis sélectionnez **Exécuter en tant qu’administrateur**.
   
   1. Dans la fenêtre PowerShell qui s’ouvre, entrez `Install-Module AzureAD`.

2. Créez le principal de service pour Customer Insights avec le module Azure AD PowerShell.

   1. Dans la fenêtre PowerShell, entrez `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Remplacez *[votre ID de client]* par l’ID réel du client dans lequel vous souhaitez créer le principal de service. Le paramètre de nom d’environnement, `AzureEnvironmentName`, est facultatif.
  
   1. Entrez `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Cette commande crée le principal de service pour les informations sur l’audience sur le client sélectionné. 

   1. Entrez `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Cette commande crée le principal de service pour les informations sur l’engagement dans le client sélectionné.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Accorder des autorisations au principal de service pour accéder au compte de stockage

Accédez au portail Azure pour accorder des autorisations au principal de service pour le compte de stockage que vous souhaitez utiliser dans les informations sur l’audience.

1. Accédez au [Portail d’administration Azure](https://portal.azure.com) et connectez-vous à votre organisation.

1. Ouvrez le compte de stockage auquel vous souhaitez que le principal de service pour les informations sur l’audience puisse accéder.

1. Dans le volet de gauche, sélectionnez **Contrôle d’accès (IAM)**, puis sélectionnez **Ajouter** > **Ajouter une attribution de rôle**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Capture d’écran montrant le portail Azure lors de l’ajout d’une attribution de rôle.":::

1. Dans le volet **Ajouter une attribution de rôle**, définissez les propriétés suivantes :
   - Rôle : **Contributeur de données Blob de stockage**
   - Attribuer l’accès à : **Utilisateur, groupe ou principal de service**
   - Sélectionnez : **Dynamics 365 AI pour Customer Insights** et **Dynamics 365 AI pour les informations sur l’engagement de Customer Insights** (les deux [principaux de service](#create-a-new-service-principal) que vous venez de créer dans cette procédure)

1.  Sélectionnez **Enregistrer**.

La propagation des modifications peut prendre jusqu’à 15 minutes.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Entrer l’ID de ressource Azure ou les détails sur l’abonnement Azure dans la pièce du compte de stockage jointe aux informations sur l’audience

Vous pouvez associer un compte Data Lake Storage aux informations sur l’audience pour [stocker les données de sortie](manage-environments.md) ou pour [les utiliser comme source de données](connect-common-data-service-lake.md). Cette option permet de choisir entre une approche basée sur les ressources ou basée sur l’abonnement. Selon l’approche choisie, suivez la procédure décrite dans l’une des sections suivantes.

### <a name="resource-based-storage-account-connection"></a>Connexion du compte de stockage basée sur des ressources

1. Accédez au [portail d’administration Azure](https://portal.azure.com), connectez-vous à votre abonnement et ouvrez le compte de stockage.

1. Dans le volet de gauche, accédez à **Paramètres** > **Propriétés**.

1. Copiez la valeur de l’ID de ressource du compte de stockage.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copiez l’ID de ressource du compte de stockage.":::

1. Dans les informations sur l’audience, insérez l’ID de ressource dans le champ de ressource affiché sur l’écran de connexion du compte de stockage.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Entrez les informations sur l’ID de ressource du compte de stockage.":::   

1. Poursuivez avec les étapes restantes dans les informations sur l’audience pour associer le compte de stockage.

### <a name="subscription-based-storage-account-connection"></a>Connexion du compte de stockage basée sur un abonnement

1. Accédez au [portail d’administration Azure](https://portal.azure.com), connectez-vous à votre abonnement et ouvrez le compte de stockage.

1. Dans le volet de gauche, accédez à **Paramètres** > **Propriétés**.

1. Passez en revue les champs **Abonnement**, **Groupe de ressources** et **Nom** du compte de stockage pour vous assurer de sélectionner les valeurs appropriées dans les informations sur l’audience.

1. Dans les informations sur l’audience, choisissez les valeurs des champs correspondants lors de l’ajout du compte de stockage.

1. Poursuivez avec les étapes restantes dans les informations sur l’audience pour associer le compte de stockage.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
