---
title: Créer et gérer des environnements
description: Découvrez comment souscrire au service et comment gérer des environnements.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: fcdb7f073ff73322ff69d0a8684391819a809d00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646308"
---
# <a name="manage-environments"></a>Gérer des environnements

## <a name="switch-environments"></a>Changer d’environnements

Sélectionnez le contrôle **Environnement** dans le coin supérieur droit de la page pour changer d’environnement.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Capture d’écran du contrôle pour changer d’environnement.":::

Les administrateurs peuvent [créer](create-environment.md) et gérer des environnements.

## <a name="edit-an-existing-environment"></a>Modifier un environnement existant

Vous pouvez modifier certains détails des environnements existants.

1.  Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.

2.  Sélectionnez l’icône **Modifier**.

3. Dans la zone **Modifier l’environnement**, vous pouvez mettre à jour les paramètres de l’environnement.

Pour plus d’informations sur les paramètres d’environnement, consultez [Créer un environnement](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Se connecter à Microsoft Dataverse
   
L’étape **Microsoft Dataverse** vous permet de connecter Customer Insights à votre environnement Dataverse. 

Configurez votre environnement Microsoft Dataverse de manière à partager des données (profils et informations) avec des applications métier basées sur Dataverse, telles que Dynamics 365 Marketing ou des applications pilotées par modèle dans Power Apps.

Pour utiliser [des modèles de prédiction prêts à l’emploi](predictions-overview.md#out-of-box-models), configurez le partage de données avec Dataverse. Vous pouvez également activer l’ingestion de données à partir des sources de données local, en fournissant l’URL d’environnement Microsoft Dataverse administrée par votre organisation.

Si vous activez le partage de données avec Microsoft Dataverse en cochant la case de partage de données, une actualisation complète unique de vos sources de données et de tous les autres processus sera déclenchée.

> [!IMPORTANT]
> 1. Customer Insights et Dataverse doivent se trouver dans la même région pour activer le partage de données.
> 1. Vous devez avoir un rôle d’administrateur global dans l’environnement Dataverse. Vérifiez si cet [environnement Dataverse est associé](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) à certains groupes de sécurité et assurez-vous d’être ajouté à ces groupes de sécurité.
> 1. Aucun environnement Customer Insights existant n’est déjà associé à cet environnement Dataverse. Découvrez comment [supprimer une connexion existante à un environnement Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Options de configuration pour activer le partage de données avec Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Activer le partage de données avec Dataverse à partir de votre propre Azure Data Lake Storage (version préliminaire)

Si votre environnement est configuré pour utiliser votre propre Azure Data Lake Storage pour stocker les données Customer Insights, l’activation du partage de données avec Microsoft Dataverse nécessite une configuration supplémentaire.

1. Créez deux groupes de sécurité dans votre abonnement Azure : un groupe de sécurité **Lecteur** et un groupe de sécurité **Contributeur** et définissez le service Microsoft Dataverse en tant que propriétaire des deux groupes de sécurité.
2. Gérez la liste de contrôle d’accès (ACL) dans le conteneur CustomerInsights de votre compte de stockage via ces groupes de sécurité. Ajoutez le service Microsoft Dataverse et les applications métier basées sur Dataverse comme Dynamics 365 Marketing au goupe de sécurité **Lecteur** avec des autorisations de **lecture seule**. Ajoutez *uniquement* l’application Customers Insights au groupe de sécurité **Contributeur** pour accorder à la fois des autorisations de **lecture et écriture** pour écrire les profils et les informations.
   
#### <a name="prerequisites"></a>Conditions préalables

Pour exécuter les scripts PowerShell, les trois modules suivants doivent être importés. 

1. Installez la version la plus récente de [Azure Active Directory PowerShell pour Graph](/powershell/azure/active-directory/install-adv2).
   1. Sur votre PC, sélectionnez la touche Windows du clavier et recherchez **Windows PowerShell**, puis sélectionnez **Exécuter en tant qu’administrateur**.
   1. Dans la fenêtre PowerShell qui s’ouvre, entrez `Install-Module AzureAD`.
2. Importez trois modules.
    1. Dans la fenêtre Powershell, entrez `Install-Module -Name Az.Accounts` et suivez les étapes. 
    1. Répétez pour `Install-Module -Name Az.Resources` et `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Étapes de configuration

1. Téléchargez les deux scripts PowerShell que vous devez exécuter à partir du [référentiel GitHub](https://github.com/trin-msft/byol) pour les ingérieurs.
    1. `CreateSecurityGroups.ps1`
       - Vous devez disposer d’autorisations d’*administration de clients* pour exécuter ce script PowerShell. 
       - Ce script PowerShell crée deux groupes de sécurité dans votre abonnement Azure. Un pour le groupe Lecteur et un autre pour le groupe Contributeur et le service Microsoft Dataverse deviendra le propriétaire de ces deux groupes de sécurité.
       - Exécutez ce script PowerShell dans Windows PowerShell en fournissant l’ID d’abonnement Azure contenant votre Azure Data Lake Storage. Ouvrez le script PowerShell dans un éditeur pour consulter les informations supplémentaires et la logique implémentée.
       - Enregistrez les deux valeurs d’ID de groupe de sécurité générées par ce script, car nous les utiliserons dans le script `ByolSetup.ps1`.
       
        > [!NOTE]
        > La création de groupes de sécurité peut être désactivée dans votre locataire. Dans ce cas, une configuration manuelle sera nécessaire et votre administrateur Azure AD devra [activer la création de groupes de sécurité](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Les autorisations de *Propriétaire des données d’objet blob de stockage* au niveau du compte/conteneur de stockage sont nécessaires pour exécuter ce script ou ce script en créera une pour vous. Votre attribution de rôle peut être supprimée manuellement après l’exécution réussie du script.
        - Ce script PowerShell ajoute le contrôle d’accès en fonction du rôle (RBAC) requis pour le service Microsoft Dataverse et les applications métier basées sur Dataverse. Il met également à jour la liste de contrôle d’accès (ACL) sur le conteneur CustomerInsights pour les groupes de sécurité créés avec le script `CreateSecurityGroups.ps1`. Le groupe Contributeur aura l’autorisation *rwx* et le groupe Lecteur aura l’autorisation *r-x* uniquement.
        - Exécutez ce script PowerShell dans Windows PowerShell en fournissant l’ID d’abonnement Azure contenant votre Azure Data Lake Storage, le nom du compte de stockage, le nom du groupe de ressources et les valeurs d’ID du groupe de sécurité Lecteur et Contributeur. Ouvrez le script PowerShell dans un éditeur pour consulter les informations supplémentaires et la logique implémentée.
        - Copiez la chaîne de sortie après avoir exécuté correctement le script. La chaîne de sortie doit se présenter comme suit : `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Entrez la chaîne de sortie copiée ci-dessus dans le champ **Identifiant d’autorisations** de l’étape de configuration de l’environnement pour Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Options de configuration pour activer le partage de données à partir de votre propre Azure Data Lake Storage avec Microsoft Dataverse .":::

Customer Insights ne prend pas en charge les scénarios de partage de données suivants :
- Si vous activez le partage de données avec Dataverse, vous ne pourrez pas [créer des valeurs prédites ou manquantes dans une entité](predictions.md).
- Si vous activez le partage de données avec Dataverse, vous ne pourrez pas afficher les rapports PowerBI Embedded facultatifs dans votre environnement Customer Insights.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Supprimer une connexion existante à un environnement Dataverse

Lors de la connexion à un environnement Dataverse, le message d’erreur **Cette organisation CDS est déjà associée à une autre instance Customer Insights** signifie que l’environnement Dataverse est déjà utilisé dans un environnement Customer Insights. Vous pouvez supprimer la connexion existante en tant qu’administrateur global de l’environnement Dataverse. Quelques heures sont nécessaires pour remplir les modifications.

1. Accédez à [Power Apps](https://make.powerapps.com).
1. Sélectionnez l’environnement dans le sélecteur d’environnement.
1. Accédez à **Solutions**
1. Désinstallez ou supprimez la solution nommée **Complément de carte client Dynamics 365 Customer Insights (version préliminaire)**.

OU 

1. Ouvrez votre environnement Dataverse.
1. Accédez à **Paramètres avancés** > **Solutions**.
1. Désinstallez la solution **CustomerInsightsCustomerCard**.

## <a name="copy-the-environment-configuration"></a>Copier la configuration de l’environnement

En tant qu’administrateur, vous pouvez choisir de copier la configuration d’un environnement existant lorsque vous en créez un nouveau. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Capture d’écran des options de paramètres dans les paramètres d’environnement.":::

Vous voyez la liste de tous les environnements disponibles dans votre organisation à partir desquels vous pouvez copier des données.

Les paramètres de configuration suivants sont copiés :

- Sources de données ingérées/importées
- Configuration de l’unification des données (mappage, correspondance, fusion)
- Segments
- Mesures
- Relations
- Activités
- Index Rechercher et filtrer
- Destinations d’exportation
- Actualisation programmée
- Enrichissements
- Gestion des modèles
- Attributions de rôles

## <a name="set-up-a-copied-environment"></a>Configurer un environnement copié

Lorsque vous copiez la configuration de l’environnement, les données suivantes *ne sont pas* copiées :

- Profils client.
- Informations d’identification d’une source de données. Vous devrez fournir les informations d’identification pour chaque source de données et actualiser les sources de données manuellement.
- Sources de données du dossier Common Data Model et Dataverse - lac de données géré. Vous devez créer ces sources de données manuellement avec le même nom que dans l’environnement source.
- Secrets de connexion utilisés pour les exportations et les enrichissements. Vous devez réauthentifier les connexions puis réactiver les enrichissements et les exportations. 

Lorsque vous copiez un environnement, vous voyez un message de confirmation de création du nouvel environnement. Sélectionnez **Accéder aux sources de données** pour voir la liste des sources de données.

Toutes les sources de données affichent un statut **Identifiants requis**. Modifiez les sources de données et entrez les informations d’identification pour les actualiser.

:::image type="content" source="media/data-sources-copied.png" alt-text="Liste des sources de données qui ont été copiées et qui nécessitent une authentification.":::

Après avoir actualisé les sources de données, accédez à **Données** > **Unifier**. Vous trouverez ici les paramètres de l’environnement source. Modifiez-les selon vos besoins ou sélectionnez **Exécuter** pour démarrer le processus d’unification des données et créer l’entité client unifiée.

Une fois l’unification des données terminée, accédez à **Mesures** et **Segments** pour les actualiser.

Avant de réactiver les exportations et les enrichissements, accédez à **Administrateur** > **Connexions** pour réauthentifier les connexions dans votre nouvel environnement.

## <a name="change-the-owner-of-an-environment"></a>Changer le propriétaire d’un environnement

Bien que plusieurs utilisateurs puissent disposer d’autorisations d’administration dans Customer Insights, un seul utilisateur est propriétaire d’un environnement. Par défaut, il s’agit de l’administrateur qui crée initialement un environnement. En tant qu’administrateur d’un environnement, vous pouvez attribuer la propriété à un autre utilisateur avec des autorisations d’administrateur.

1. Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.

1. Sélectionnez l’icône **Modifier**.

1. Dans la zone **Modifier l’environnement**, allez à l’étape **Informations de base**.

1. Dans le champ **Changer le propriétaire de l’environnement**, choisissez le nouveau propriétaire de l’environnement.  

1. Sélectionnez **Réviser et terminer**, puis **Mettre à jour** pour appliquer les changements. 

## <a name="claim-ownership-of-an-environment"></a>Revendiquer la propriété d’un environnement

Si le propriétaire d’un environnement quitte l’organisation ou si son compte utilisateur est supprimé, l’environnement n’aura plus de propriétaire. Un utilisateur disposant d’autorisations d’administrateur peut revendiquer la propriété et devenir le nouveau propriétaire. Il peut continuer à être propriétaire de l’environnement ou [attribuer la propriété à un autre administrateur](#change-the-owner-of-an-environment). 

Pour revendiquer la propriété, cliquez sur le bouton **Prendre possession** qui s’affiche en haut de chaque page dans Customer Insights lorsque le propriétaire d’origine a quitté l’organisation.

## <a name="reset-an-existing-environment"></a>Réinitialiser un environnement existant

En tant que propriétaire d’un environnement, vous pouvez réinitialiser un environnement à un état vide si vous souhaitez supprimer toutes les configurations et les données ingérées.

1.  Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application. 

2.  Sélectionnez l’environnement à réinitialiser, puis les points de suspension (**...**). 

3. Choisissez l’option **Réinitialiser**. 

4.  Pour confirmer la suppression, entrez le nom de l’environnement et sélectionnez **Réinitialiser**.

## <a name="delete-an-existing-environment"></a>Supprimer un environnement existant

En tant que propriétaire d’un environnement, vous pouvez supprimer un environnement que vous administrez.

1.  Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.

2.  Sélectionnez l’environnement à réinitialiser, puis les points de suspension (**...**). 

3. Choisissez l’option **Supprimer**. 

4.  Pour confirmer la suppression, sélectionnez le nom de l’environnement et sélectionnez **Supprimer**.

> [!NOTE]
> La suppression d’un environnement n’entraîne pas la suppression de l’association à un environnement Dataverse. Découvrez comment [supprimer une connexion existante à un environnement Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE [footer-include](includes/footer-banner.md)]
