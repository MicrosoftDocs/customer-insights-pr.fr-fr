---
title: Se connecter à un compte Azure Data Lake Storage en utilisant un principal de service
description: Utilisez un principal de service Azure pour vous connecter à votre lac de données personnel.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461145"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Se connecter à un compte Azure Data Lake Storage en utilisant un principal de service Azure
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Les outils automatisés qui utilisent les services Azure doivent toujours avoir des autorisations restreintes. Au lieu que les applications se connectent en tant qu’utilisateur entièrement privilégié, Azure propose des principaux de service. Lisez la suite pour savoir comment connecter Dynamics 365 Customer Insights à un compte Azure Data Lake Storage en utilisant un principal de service Azure à la place de clés de compte de stockage. 

Utilisez le principal du service pour [ajouter ou modifier un dossier Common Data Model en tant que source de données](connect-common-data-model.md) de manière sécurisée ou pour [créer ou mettre à jour un environnement](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - Le compte Data Lake Storage qui utilise<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> le principal de service doit avoir [activé l’espace de noms hiérarchique](/azure/storage/blobs/data-lake-storage-namespace).
> - Des autorisations administrateur pour votre abonnement Azure sont nécessaires pour créer le principal de service.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Créer un principal de service Azure pour Customer Insights

Avant de créer un principal de service pour les informations sur l’audience ou pour les informations sur l’engagement, vérifiez s’il existe déjà dans l’organisation.

### <a name="look-for-an-existing-service-principal"></a>Rechercher un principal de service existant

1. Accédez au [Portail d’administration Azure](https://portal.azure.com) et connectez-vous à votre organisation.

2. Dans **Services Azure**, sélectionnez **Azure Active Directory**.

3. Sous **Gérer**, sélectionnez **Applications d’entreprise**.

4. Recherchez l’ID de l’application<!--note from editor: Via Microsoft Writing Style Guide.--> Microsoft :
   - Informations sur l’audience : `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` avec le nom `Dynamics 365 AI for Customer Insights`
   - Informations sur l’engagement : `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` avec le nom `Dynamics 365 AI for Customer Insights engagement insights`

5. Si vous trouvez un enregistrement correspondant, cela signifie que le principal de service existe déjà. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Capture d’écran montrant un principal de service existant.":::
   
6. Si aucun résultat n’est renvoyé, créez un nouveau principal de service.

>[!NOTE]
>Pour utiliser pleinement le potentiel de Dynamics 365 Customer Insights, nous vous suggérons d’ajouter les deux applications au principal de service.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Créer un nouveau principal de service
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Installez la dernière version d’Azure Active Directory PowerShell for Graph. Pour plus d’informations, accédez à [Installer Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Sur votre PC, sélectionnez la touche Windows du clavier et recherchez **Windows PowerShell**, puis sélectionnez **Exécuter en tant qu’administrateur**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. Dans la fenêtre PowerShell qui s’ouvre, entrez `Install-Module AzureAD`.

2. Créez le principal de service pour Customer Insights avec le module Azure AD PowerShell.

   1. Dans la fenêtre PowerShell, entrez `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Remplacez *« [votre ID client] »*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> par l’ID réel du client dans lequel vous souhaitez créer le principal de service. Le paramètre de nom d’environnement, `AzureEnvironmentName`, est facultatif.
  
   1. Entrez `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Cette commande crée le principal de service pour les informations sur l’audience sur le client sélectionné. 

   1. Entrez `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Cette commande crée le principal de service pour les informations sur l’engagement<!--note from editor: Edit okay?--> sur le client sélectionné.

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

Vous pouvez<!--note from editor: Edit suggested only if this section is optional.--> joindre un compte Data Lake Storage aux informations sur l’audience pour [stocker les données de sortie](manage-environments.md) ou pour [les utiliser comme source de données](connect-common-data-service-lake.md). Cette option permet de choisir entre une approche basée sur les ressources ou basée sur l’abonnement. Selon l’approche choisie, suivez la procédure décrite dans l’une des sections suivantes.<!--note from editor: Suggested.-->

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