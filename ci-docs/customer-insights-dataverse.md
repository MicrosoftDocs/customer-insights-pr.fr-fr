---
title: Utiliser des données Customer Insights dans Microsoft Dataverse
description: Apprenez à connecter Customer Insights et Microsoft Dataverse et comprenez les entités de sortie exportées vers Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 252723b8c174cb1ec488388c26fd2a1d398e9002
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011517"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Utiliser des données Customer Insights dans Microsoft Dataverse

Customer Insights offre la possibilité de rendre les entités de sortie disponibles en tant que [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Cette intégration facilite le partage de données et permet un développement personnalisé grâce à une approche low code/sans code. Les [entités de sortie](#output-entities) sont disponibles sous forme de tableaux dans un environnement Dataverse. Vous pouvez utiliser les données pour toute autre application basée sur les tables Dataverse. Ces tables permettent des scénarios tels que des flux de travail automatisés via Power Automate ou la création d’applications avec Power Apps.

La connexion à votre environnement Dataverse vous permet également [d’ingérer des données à partir de sources de données locales à l’aide de flux de données et de passerelles Power Platform](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Conditions préalables

- Les environnements Customer Insights et Dataverse doivent être hébergés dans la même région.
- Vous devez avoir un rôle d’administrateur global dans l’environnement Dataverse. Vérifiez si cet [environnement Dataverse est associé](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) à certains groupes de sécurité et assurez-vous d’être ajouté à ces groupes de sécurité.
- Aucun autre environnement Customer Insights n’est déjà associé à l’environnement Dataverse auquel vous souhaitez vous connecter. Découvrez comment [supprimer une connexion existante à un environnement Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Un environnement Microsoft Dataverse ne peut se connecter qu’à un seul compte de stockage. Cela ne s’applique que si vous configurez l’environnement pour [utiliser votre Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Connecter un environnement Dataverse à Customer Insights

L’étape **Microsoft Dataverse** vous permet de connecter Customer Insights à votre environnement Dataverse lors de la [création d’un environnement Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Partage de données avec Microsoft Dataverse activé automatiquement pour les nouveaux environnements.":::

Les administrateurs peuvent configurer Customer Insights pour connecter un environnement Dataverse existant. En fournissant l’URL à l’environnement Dataverse, celui-ci est associé à leur nouvel environnement Customer Insights.

Si vous ne souhaitez pas utiliser un environnement Dataverse existant, le système crée un nouvel environnement pour les données Customer Insights dans votre locataire. [Les administrateurs Power Platform peuvent contrôler qui peut créer des environnements](/power-platform/admin/control-environment-creation). Lorsque vous configurez un nouvel environnement Customer Insights et que l’administrateur a désactivé la création d’environnements Dataverse pour tous les utilisateurs sauf les administrateurs, vous ne pourrez peut-être pas créer un nouvel environnement.

**Activez le partage de données** avec Dataverse en cochant la case de partage de données.

Si vous utilisez votre propre compte Data Lake Storage, l’**Identificateur d’autorisations** est également nécessaire. Pour plus d’informations sur l’obtention de l’identificateur d’autorisation, consultez la section suivante.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Activer le partage de données avec Dataverse à partir de votre propre Azure Data Lake Storage (version préliminaire)

L’activation du partage de données avec Microsoft Dataverse lorsque votre environnement [utilise votre propre compte Azure Data Lake Storage](own-data-lake-storage.md) nécessite une configuration supplémentaire. L’utilisateur qui configure l’environnement Customer Insights doit disposer au moins des autorisations **Lecteur des données blob de stockage** sur le conteneur *CustomerInsights* du compte Azure Data Lake Storage.

1. Créez deux groupes de sécurité dans votre abonnement Azure : un groupe de sécurité **Lecteur** et un groupe de sécurité **Contributeur** et définissez le service Microsoft Dataverse en tant que propriétaire des deux groupes de sécurité.
2. Gérez la liste de contrôle d’accès (ACL) dans le conteneur CustomerInsights de votre compte de stockage via ces groupes de sécurité. Ajoutez le service Microsoft Dataverse et les applications métier basées sur Dataverse comme Dynamics 365 Marketing au goupe de sécurité **Lecteur** avec des autorisations de **lecture seule**. Ajoutez *uniquement* l’application Customers Insights au groupe de sécurité **Contributeur** pour accorder à la fois des autorisations de **lecture et écriture** pour écrire les profils et les informations.

### <a name="limitations"></a>Limitations

Deux limitations s’appliquent à l’utilisation de Dataverse avec votre propre compte Azure Data Lake Storage :

- Il existe un mappage un à un entre une organisation Dataverse et un compte Azure Data Lake Storage. Une fois qu’une organisation Dataverse est connectée à un compte de stockage, elle ne peut pas se connecter à un autre compte de stockage. Cette limitation empêche un Dataverse de ne pas remplir plusieurs comptes de stockage.
- Le partage de données ne fonctionnera pas si une configuration Azure Private Link est nécessaire pour accéder à votre compte Azure Data Lake Storage, car il se trouve derrière un pare-feu. Dataverse ne prend pas actuellement en charge la connexion à des points de terminaison privés via Private Link.

### <a name="set-up-powershell"></a>Configurer PowerShell

Pour exécuter les scripts PowerShell, vous devez d’abord configurer PowerShell en conséquence.

1. Installez la version la plus récente de [Azure Active Directory PowerShell pour Graph](/powershell/azure/active-directory/install-adv2).
   1. Sur votre PC, sélectionnez la touche Windows du clavier et recherchez **Windows PowerShell**, puis sélectionnez **Exécuter en tant qu’administrateur**.
   1. Dans la fenêtre PowerShell qui s’ouvre, entrez `Install-Module AzureAD`.
2. Importez trois modules.
    1. Dans la fenêtre Powershell, entrez `Install-Module -Name Az.Accounts` et suivez les étapes.
    1. Répétez pour `Install-Module -Name Az.Resources` et `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Étapes de configuration

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
        - Copiez la chaîne de sortie après avoir exécuté correctement le script. La chaîne de sortie doit se présenter comme suit : `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Entrez la chaîne de sortie copiée ci-dessus dans le champ **Identifiant d’autorisations** de l’étape de configuration de l’environnement pour Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Options de configuration pour activer le partage de données à partir de votre propre Azure Data Lake Storage avec Microsoft Dataverse .":::

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

Si la suppression de la connexion échoue en raison des dépendances, vous devez également supprimer les dépendances. Pour plus d’informations, consultez [Suppression des dépendances](/power-platform/alm/removing-dependencies)

## <a name="output-entities"></a>Entités de sortie

Certaines entités de sortie de Customer Insights sont disponibles en tant que tables dans Dataverse. Les sections ci-dessous décrivent le schéma attendu de ces tables.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enrichissement](#enrichment)
- [Prédiction](#prediction)
- [Appartenance aux segments](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Cette table contient le profil client unifié de Customer Insights. Le schéma d’un profil client unifié dépend des entités et des attributs utilisés dans le processus d’unification des données. Le schéma d’un profil client contient généralement un sous-ensemble des attributs de la [définition Common Data Model de CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

La table AlternateKey contient les clés des entités qui ont participé au processus d’unification.

|Column  |Type  |Description  |
|---------|---------|---------|
|DataSourceName    |String         | Nom de la source de données. Par exemple : `datasource5`        |
|Nom de l’entité        | String        | Nom de l’entité dans Customer Insights. Par exemple : `contact1`        |
|AlternateValue    |String         |ID alternatif mappé à l’ID client. Exemple : `cntid_1078`         |
|KeyRing           | Texte multiligne        | Valeur JSON  </br> Exemple : [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|Customerid         | String        | ID du profil client unifié.         |
|AlternateKeyId     | GUID         |  GUID déterministe AlternateKey basé sur msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Exemple : `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Cette table contient les activités des utilisateurs qui sont disponibles dans Customer Insights.

| Column            | Type        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| Customerid        | String      | ID profil client                                                                      |
| ActivityId        | String      | ID interne de l’activité client (clé primaire)                                       |
| SourceEntityName  | String      | Nom de l’entité source                                                                |
| SourceActivityId  | String      | Clé primaire de l’entité source                                                       |
| ActivityType      | String      | Type d’activité sémantique ou nom de l’activité personnalisée                                        |
| ActivityTimeStamp | DATETIME    | Horodatage de l’activité                                                                      |
| Titre             | String      | Titre ou non de l’activité                                                               |
| Description       | String      | Description de l’activité                                                                     |
| URL               | String      | Lien vers une URL externe spécifique à l’activité                                         |
| SemanticData      | Chaîne JSON | Comprend une liste de paires clé-valeur pour les champs de mappage sémantique spécifiques au type d’activité |
| RangeIndex        | String      | Horodatage Unix utilisé pour trier la chronologie des activités et les requêtes de plage effective |
| mydynci_unifiedactivityid   | GUID | ID interne de l’activité client (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Cette table contient les données de sortie des mesures basées sur les attributs du client.

| Column             | Type             | Description                 |
|--------------------|------------------|-----------------------------|
| Customerid         | String           | ID profil client        |
| Mesures           | Chaîne JSON      | Inclut une liste de paires clé-valeur pour le nom de la mesure et les valeurs pour le client donné | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID profil client |


### <a name="enrichment"></a>Enrichissement

Cette table contient le résultat du processus d’enrichissement.

| Column               | Type             |  Description                                          |
|----------------------|------------------|------------------------------------------------------|
| Customerid           | String           | ID profil client                                 |
| EnrichmentProvider   | String           | Nom du fournisseur pour l’enrichissement                                  |
| EnrichmentType       | String           | Type d’enrichissement                                      |
| Valeurs               | Chaîne JSON      | Liste des attributs produits par le processus d’enrichissement |
| msdynci_enrichmentid | GUID             | GUID déterministe généré à partir de msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prédiction

Cette table contient le résultat des prédictions de modèle.

| Column               | Type        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| Customerid           | String      | ID profil client                                  |
| ModelProvider        | String      | Nom du fournisseur du modèle                                      |
| Modèle                | String      | Nom du modèle                                                |
| Valeurs               | Chaîne JSON | Liste des attributs produits par le modèle |
| msdynci_predictionid | GUID        | GUID déterministe généré à partir de msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Appartenance aux segments

Ce tableau contient des informations sur l’appartenance aux segments des profils clients.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| Customerid        | String       | ID profil client        |
| SegmentProvider      | String       | Application qui publie les segments.      |
| SegmentMembershipType | String       | Type de client que cette appartenance aux segments enregistre. Prend en charge plusieurs types tels que Client, Contact ou Compte. Par défaut : Client  |
| Segments       | Chaîne JSON  | Liste des segments uniques dont le profil client est membre      |
| msdynci_identifier  | String   | Identificateur unique de l’enregistrement sur l’appartenance aux segments. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID déterministe généré à partir de `msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
