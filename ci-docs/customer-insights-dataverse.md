---
title: Utiliser des données Customer Insights dans Microsoft Dataverse
description: Apprenez à connecter Customer Insights et Microsoft Dataverse et comprenez les entités de sortie exportées vers Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: dfa63110fc5291f2b63aebf588d6fdd20ed4ab67
ms.sourcegitcommit: 134aac66e3e0b77b2e96a595d6acbb91bf9afda2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2022
ms.locfileid: "9424306"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Utiliser des données Customer Insights dans Microsoft Dataverse

Customer Insights offre la possibilité de rendre les entités de sortie disponibles dans [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Cette intégration facilite le partage de données et permet un développement personnalisé grâce à une approche low code/sans code. Les [entités de sortie](#output-entities) sont disponibles sous forme de tableaux dans un environnement Dataverse. Vous pouvez utiliser les données pour toute autre application basée sur les tables Dataverse. Ces tables permettent des scénarios tels que des flux de travail automatisés via Power Automate ou la création d’applications avec Power Apps.

La connexion à votre environnement Dataverse vous permet également [d’ingérer des données à partir de sources de données locales à l’aide de flux de données et de passerelles Power Platform](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Conditions préalables

- Les environnements Customer Insights et Dataverse doivent être hébergés dans la même région.
- Un rôle d’administrateur global défini dans l’environnement Dataverse. Vérifiez si cet [environnement Dataverse est associé](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) à certains groupes de sécurité et assurez-vous d’être ajouté à ces groupes de sécurité.
- Aucun autre environnement Customer Insights n’est déjà associé à l’environnement Dataverse auquel vous souhaitez vous connecter. Découvrez comment [supprimer une connexion existante à un environnement Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Un environnement Microsoft Dataverse connecté à un seul compte de stockage si vous configurez l’environnement pour [utiliser votre Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Autorisation de capacité de stockage Dataverse

Un abonnement Customer Insights vous donne droit à une capacité supplémentaire pour les ressources existantes de votre organisation [capacité de stockage Dataverse](/power-platform/admin/capacity-storage). La capacité supplémentaire dépend du nombre de profils utilisés par votre abonnement.

**Exemple :**

En supposant que vous obteniez 15 Go de stockage de base de données et 20 Go de stockage de fichiers pour 100 000 profils clients. Si votre abonnement comprend 300 000 profils clients, votre capacité de stockage totale est de 45 Go (3 x 15 Go) de stockage de base de données et de 60 Go de stockage de fichiers (3 x 20 Go). De même, si vous avez un abonnement B-to-B avec 30 000 comptes, votre capacité de stockage totale est de 45 Go (3 x 15 Go) de stockage de base de données et de 60 Go de stockage de fichiers (3 x 20 Go).

La capacité de journalisation n’est pas incrémentielle et fixe pour votre organisation.

Pour en savoir sur les autorisations de capacité détaillées, consultez le [Guide des licences Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Connecter un environnement Dataverse à Customer Insights

L’étape **Microsoft Dataverse** vous permet de connecter Customer Insights à votre environnement Dataverse lors de la [création d’un environnement Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Partage de données avec Microsoft Dataverse activé automatiquement pour les nouveaux environnements.":::

1. Fournissez l’URL de votre environnement Dataverse ou laissez cet espace vide pour qu’une URL soit créée pour vous.

   > [!NOTE]
   > Après avoir établi la connexion entre Customer Insights et Dataverse, ne modifiez pas le nom de l’organisation pour l’environnement Dataverse. Le nom de l’organisation est utilisé dans l’URL de Dataverse et un nom modifié rompt la connexion avec Customer Insights.

   [Les administrateurs Power Platform peuvent contrôler qui peut créer des environnements Dataverse](/power-platform/admin/control-environment-creation). Si vous essayez de configurer un nouvel environnement Customer Insights sans succès, l’administrateur a peut-être désactivé la création d’environnements Dataverse pour tous les utilisateurs sauf les administrateurs.

1. Si vous utilisez votre propre compte Data Lake Storage, procédez comme suit :
   1. Sélectionnez **Activer le partage de données** avec Dataverse.
   1. Saisissez l’**identifiant des autorisations**. Pour obtenir l’identifiant des autorisations, [activez le partage des données avec Dataverse depuis votre propre Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Activer le partage de données avec Dataverse à partir de votre propre Azure Data Lake Storage (version préliminaire)

Dans [votre propre compte Azure Data Lake Storage](own-data-lake-storage.md), vérifiez que l’utilisateur qui configure l’environnement Customer Insights dispose au moins des autorisations **Lecteur des données blob de stockage** sur le conteneur `customerinsights` dans le compte de stockage.

### <a name="limitations"></a>Limitations

- Il existe seulement un mappage un à un entre une organisation Dataverse et un compte Azure Data Lake Storage. Une fois qu’une organisation Dataverse est connectée à un compte de stockage, elle ne peut pas se connecter à un autre compte de stockage. Cette limitation empêche Dataverse de renseigner plusieurs comptes de stockage.
- Le partage de données ne fonctionnera pas si une configuration Azure Private Link est nécessaire pour accéder à votre compte Azure Data Lake Storage, car il se trouve derrière un pare-feu. Dataverse ne prend pas actuellement en charge la connexion à des points de terminaison privés via Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Configurez des groupes de sécurité sur votre Azure Data Lake Storage

1. Créez deux groupes de sécurité dans votre abonnement Azure : un groupe de sécurité **Lecteur** et un groupe de sécurité **Contributeur** et définissez le service Microsoft Dataverse en tant que propriétaire des deux groupes de sécurité.

1. Gérez la liste de contrôle d’accès (ACL) dans le conteneur `customerinsights` de votre compte de stockage via ces groupes de sécurité.
   1. Ajoutez le service Microsoft Dataverse et les applications métier basées sur Dataverse comme Dynamics 365 Marketing au goupe de sécurité **Lecteur** avec des autorisations de **lecture seule**.
   1. Ajoutez *uniquement* l’application Customers Insights au groupe de sécurité **Contributeur** pour accorder à la fois des autorisations de **lecture et écriture** pour écrire les profils et les informations.

### <a name="set-up-powershell"></a>Configurer PowerShell

Configurer PowerShell pour exécuter des scripts PowerShell.

1. Installez la version la plus récente de [Azure Active Directory PowerShell pour Graph](/powershell/azure/active-directory/install-adv2).
   1. Sur votre PC, sélectionnez la touche Windows du clavier et recherchez **Windows PowerShell**, puis sélectionnez **Exécuter en tant qu’administrateur**.
   1. Dans la fenêtre PowerShell qui s’ouvre, entrez `Install-Module AzureAD`.

1. Importez trois modules.
   1. Dans la fenêtre Powershell, entrez `Install-Module -Name Az.Accounts` et suivez les étapes.
   1. Répétez pour `Install-Module -Name Az.Resources` et `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Exécuter des scripts PowerShell et obtenir l’identificateur d’autorisation

1. Téléchargez les deux scripts PowerShell que vous devez exécuter à partir du [référentiel GitHub](https://github.com/trin-msft/byol) pour les ingérieurs.
   - `CreateSecurityGroups.ps1` : nécessite des autorisations d’administration du client
   - `ByolSetup.ps1` : nécessite des autorisations de propriétaire de données Storage Blob au niveau du compte de stockage/du conteneur. Ce script créera l’autorisation pour vous. Votre attribution de rôle peut être supprimée manuellement après l’exécution réussie du script.

1. Exécutez `CreateSecurityGroups.ps1` PowerShell dans Windows PowerShell en fournissant l’ID d’abonnement Azure contenant votre Azure Data Lake Storage. Ouvrez le script PowerShell dans un éditeur pour consulter les informations supplémentaires et la logique implémentée.

   Ce script crée deux groupes de sécurité sur votre abonnement Azure : un pour le groupe Lecteur et un autre pour le groupe Contributeur. Le service Microsoft Dataverse est le propriétaire de ces deux groupes de sécurité.

1. Enregistrez les deux valeurs d’ID de groupe de sécurité générées par ce script, afin de les utiliser dans le script `ByolSetup.ps1`.

   > [!NOTE]
   > La création de groupes de sécurité peut être désactivée dans votre locataire. Dans ce cas, une configuration manuelle sera nécessaire et votre administrateur Azure AD devra [activer la création de groupes de sécurité](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Exécutez `ByolSetup.ps1` dans Windows PowerShell en fournissant l’ID d’abonnement Azure contenant votre Azure Data Lake Storage, le nom du compte de stockage, le nom du groupe de ressources et les valeurs d’ID du groupe de sécurité Lecteur et Contributeur. Ouvrez le script PowerShell dans un éditeur pour consulter les informations supplémentaires et la logique implémentée.

   Ce script ajoute le contrôle d’accès en fonction du rôle (RBAC) requis pour le service Microsoft Dataverse et les applications métier basées sur Dataverse. Il met également à jour la liste de contrôle d’accès (ACL) sur le conteneur `customerinsights` pour les groupes de sécurité créés avec le script `CreateSecurityGroups.ps1`. Le groupe Contributeur aura l’autorisation *rwx* et le groupe Lecteur aura l’autorisation *r-x* uniquement.

1. Copiez la chaîne de sortie qui doit se présenter comme suit : `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Entrez la chaîne de sortie copiée dans le champ **Identificateur d’autorisations** de l’étape de configuration de l’environnement pour Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Options de configuration pour activer le partage de données à partir de votre propre Azure Data Lake Storage avec Microsoft Dataverse .":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Supprimer une connexion existante à un environnement Dataverse

Lors de la connexion à un environnement Dataverse, le message d’erreur **Cette organisation CDS est déjà associée à une autre instance Customer Insights** signifie que l’environnement Dataverse est déjà utilisé dans un environnement Customer Insights. Vous pouvez supprimer la connexion existante en tant qu’administrateur global de l’environnement Dataverse. Quelques heures sont nécessaires pour remplir les modifications.

1. Accédez à [Power Apps](https://make.powerapps.com).
1. Sélectionnez l’environnement dans le sélecteur d’environnement.
1. Accédez à **Solutions**.
1. Désinstallez ou supprimez la solution nommée **Complément de carte client Dynamics 365 Customer Insights (version préliminaire)**.

OU

1. Ouvrez votre environnement Dataverse.
1. Accédez à **Paramètres avancés** > **Solutions**.
1. Désinstallez la solution **CustomerInsightsCustomerCard**.

Si la suppression de la connexion échoue en raison des dépendances, vous devez également supprimer les dépendances. Pour plus d’informations, consultez [Suppression des dépendances](/power-platform/alm/removing-dependencies)

## <a name="output-entities"></a>Entités de sortie

Certaines entités de sortie de Customer Insights sont disponibles en tant que tables dans Dataverse. Les sections ci-dessous décrivent le schéma attendu de ces tables.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enrichissement](#enrichment)
- [Prédiction](#prediction)
- [Appartenance aux segments](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Cette table contient le profil client unifié de Customer Insights. Le schéma d’un profil client unifié dépend des entités et des attributs utilisés dans le processus d’unification des données. Le schéma d’un profil client contient généralement un sous-ensemble des attributs de la [définition Common Data Model de CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Pour le scénario B2B, le profil client contient des comptes unifiés et le schéma contient généralement un sous-ensemble des attributs depuis la [Définition de Common Data Model du compte](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>ContactProfile

Un ContactProfile contient des informations unifiées sur un contact. Les contacts sont [les individus mappés à un compte](data-unification-contacts.md) dans un scénario B2B.

| Column                       | Type                | Description     |
| ---------------------------- | ------------------- | --------------- |
|   BirthDate            | DateHeure       |  Date de naissance du contact               |
|  Ville                  | Text |  Ville de l’adresse du contact               |
|   ContactId            | Text |  ID du profil du contact               |
|  ContactProfileId     | Identificateur unique   |  GUID du contact               |
|  CountryOrRegion      | Text |  Pays/région de l’adresse du contact               |
|  Customerid           | Text |  ID du compte auquel le contact est associé               |
|  Nom de l’entité           | Text |  Entité d’où proviennent les données                |
|  FirstName            | Text |  Prénom du contact               |
|  Genre               | Text |  Sexe du contact               |
|  Id                   | Text |  GUID déterministe basé sur `Identifier`               |
|  Identificateur           | Text |  ID interne du profil du contact : `ContactProfile|CustomerId|ContactId`               |
|  Intitulé             | Text |  Fonction du contact               |
|  LastName             | Text |  Nom du contact               |
|  PostalCode           | Text |  Code ZIP de l’adresse du contact               |
|  PrimaryEmail         | Text |  Adresse e-mail du contact               |
|  PrimaryPhone         | Text |  Numéro de téléphone du contact               |
|  StateOrProvince      | Text |  Département ou province de l’adresse du contact               |
|  StreetAddress        | Text |  Rue de l’adresse du contact               |

### <a name="alternatekey"></a>AlternateKey

La table AlternateKey contient les clés des entités qui ont participé au processus d’unification.

|Column  |Type  |Description  |
|---------|---------|---------|
|DataSourceName    |Text         | Nom de la source de données. Par exemple : `datasource5`        |
|Nom de l’entité        | Text        | Nom de l’entité dans Customer Insights. Par exemple : `contact1`        |
|AlternateValue    |Text         |ID alternatif mappé à l’ID client. Exemple : `cntid_1078`         |
|KeyRing           | Text        | Valeur JSON  </br> Exemple : [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|Customerid         | Text        | ID du profil client unifié.         |
|AlternateKeyId     | Identificateur unique        |  GUID déterministe AlternateKey basé sur `Identifier`      |
|Identificateur |   Text      |   `DataSourceName|EntityName|AlternateValue`  </br> Exemple : `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Cette table contient les activités des utilisateurs qui sont disponibles dans Customer Insights.

| Column            | Type        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| Customerid        | Text      | ID profil client                                                                      |
| ActivityId        | Text      | ID interne de l’activité client (clé primaire)                                       |
| SourceEntityName  | Text      | Nom de l’entité source                                                                |
| SourceActivityId  | Text      | Clé primaire de l’entité source                                                       |
| ActivityType      | Text      | Type d’activité sémantique ou nom de l’activité personnalisée                                        |
| ActivityTimeStamp | DateHeure    | Horodatage de l’activité                                                                      |
| Civilité             | Text      | Titre ou non de l’activité                                                               |
| Description       | Text      | Description de l’activité                                                                     |
| URL                | Text      | Lien vers une URL externe spécifique à l’activité                                         |
| SemanticData      | Text | Comprend une liste de paires clé-valeur pour les champs de mappage sémantique spécifiques au type d’activité |
| RangeIndex        | Text      | Horodatage Unix utilisé pour trier la chronologie des activités et les requêtes de plage effective |
| UnifiedActivityId   | Identificateur unique | ID interne de l’activité client (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Cette table contient les données de sortie des mesures basées sur les attributs du client.

| Column             | Type             | Description                 |
|--------------------|------------------|-----------------------------|
| Customerid         | Text           | ID profil client        |
| Mesures           | Text      | Inclut une liste de paires clé-valeur pour le nom de la mesure et les valeurs pour le client donné |
| Identificateur | Text           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Identificateur unique     | ID profil client |

### <a name="enrichment"></a>Enrichissement

Cette table contient le résultat du processus d’enrichissement.

| Column               | Type             |  Description                                          |
|----------------------|------------------|------------------------------------------------------|
| Customerid           | Text           | ID profil client                                 |
| EnrichmentProvider   | Text           | Nom du fournisseur pour l’enrichissement                                  |
| EnrichmentType       | Text           | Type d’enrichissement                                      |
| Valeurs               | Text      | Liste des attributs produits par le processus d’enrichissement |
| EnrichmentId | Identificateur unique            | GUID déterministe généré à partir de `Identifier` |
| Identificateur   | Text           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prédiction

Cette table contient le résultat des prédictions de modèle.

| Column               | Type        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| Customerid           | Text      | ID profil client                                  |
| ModelProvider        | Text      | Nom du fournisseur du modèle                                      |
| Modèle                | Text      | Nom du modèle                                                |
| Valeurs               | Text | Liste des attributs produits par le modèle |
| PredictionId | Identificateur unique       | GUID déterministe généré à partir de `Identifier` |
| Identificateur   | Text      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Appartenance aux segments

Ce tableau contient des informations sur l’appartenance aux segments des profils clients.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| Customerid        | Text       | ID profil client        |
| SegmentProvider      | Text       | Application qui publie les segments.      |
| SegmentMembershipType | Text       | Type de client que cette appartenance aux segments enregistre. Prend en charge plusieurs types tels que Client, Contact ou Compte. Par défaut : Client  |
| Segments       | Text  | Liste des segments uniques dont le profil client est membre      |
| Identificateur  | Text   | Identificateur unique de l’enregistrement sur l’appartenance aux segments. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Identificateur unique      | GUID déterministe généré à partir de `Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
