---
title: Se connecter à un dossier Common Data Model à l’aide d’un compte Azure Data Lake
description: Utilisez les données Common Data Model avec Azure Data Lake Storage.
ms.date: 07/27/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: d79b2d34e425e123224209814fef6e367c77c813
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2022
ms.locfileid: "9396043"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Se connecter aux données dans Azure Data Lake Storage

Ingérez des données dans Dynamics 365 Customer Insights en utilisant votre compte Azure Data Lake Storage Gen2. L'ingestion de données peut être complète ou incrémentielle.

## <a name="prerequisites"></a>Conditions préalables

- L'ingestion de données prend en charge les comptes Azure Data Lake Storage *Gen2* exclusivement. Vous ne pouvez pas utiliser les comptes de stockage Azure Data Lake Gen1 pour ingérer des données.

- Le compte Azure Data Lake Storage doit avoir activé l'[espace de noms hiérarchique](/azure/storage/blobs/data-lake-storage-namespace). Les données doivent être stockées dans un format de dossier hiérarchique qui définit le dossier racine et comporte des sous-dossiers pour chaque entité. Les sous-dossiers peuvent contenir des données complètes ou des dossiers de données incrémentielles.

- Pour vous authentifier dans un principal de service Azure, assurez-vous que celui-ci est configuré dans votre client. Pour plus d’informations, consultez [Se connecter à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure](connect-service-principal.md).

- Le stockage Azure Data Lake Storage auquel vous allez vous connecter et à partir duquel vous allez ingérer des données doit se trouver dans la même région Azure que l’environnement Dynamics 365 Customer Insights. Les connexions à un dossier Common Data Model à partir d’un lac de données situé dans une autre région Azure ne sont pas prises en charge. Pour connaître la région Azure de l’environnement, accédez à **Administrateur** > **Système** > **À propos de** dans Customer Insights.

- Les données stockées dans des services en ligne peuvent être stockées dans un emplacement différent de celui où les données sont traitées ou stockées dans Dynamics 365 Customer Insights. En important ou en vous connectant aux données stockées dans des services en ligne, vous acceptez que les données puissent être transférées dans Dynamics 365 Customer Insights et qu’elles y soient stockées. [En savoir plus sur le Centre de gestion de la confidentialité Microsoft](https://www.microsoft.com/trust-center).

- Le principal du service Customer Insights doit être dans l'un des rôles suivants pour accéder au compte de stockage. Pour plus d'informations, voir [Accorder des autorisations au principal du service pour accéder au compte de stockage](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Lecteur de données d’objets BLOB de stockage
  - Propriétaire de données d’objets BLOB de stockage
  - Contributeur de données BLOB de stockage

- L’utilisateur qui configure la connexion source de données a besoin du minimum d’autorisations Contributeur de données Blob de stockage sur le compte de stockage.

- Les données de votre Data Lake Storage doivent suivre la norme Common Data Model pour le stockage de vos données et avoir le manifeste du modèle de données commun pour représenter le schéma des fichiers de données (*.csv ou *.parquet). Le manifeste doit fournir les détails des entités telles que les colonnes d'entité et les types de données, ainsi que l'emplacement du fichier de données et le type de fichier. Pour plus d’informations, voir [Manifeste Common Data Model](/common-data-model/sdk/manifest). Si le manifeste n'est pas présent, les utilisateurs administrateurs disposant d'un accès Propriétaire des données blob de stockage ou Contributeur de données blob de stockage peuvent définir le schéma lors de l'ingestion des données.

## <a name="connect-to-azure-data-lake-storage"></a>Se connecter à Azure Data Lake Storage

1. Accédez à **Données** > **Sources de données**.

1. Sélectionnez **Ajouter une source de données**.

1. Sélectionnez **Azure Data Lake Storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Boîte de dialogue permettant de saisir les détails de connexion pour Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Entrez le **nom** de la source de données et une **description** facultative. Le nom identifie de manière unique le source de données et est référencé dans les processus en aval et ne peut pas être modifié.

1. Choisissez l'une des options suivantes pour **Connecter votre stockage à l'aide de**. Pour plus d’informations, consultez [Connecter Customer Insights à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure](connect-service-principal.md).

   - **Ressource Azure** : Entrez l'**ID de ressource**. Facultativement, si vous souhaitez ingérer des données à partir d'un compte de stockage via une liaison Azure Private Link, sélectionnez **Activer la liaison privée**. Pour plus d’informations, consultez [Liaisons privées](security-overview.md#set-up-an-azure-private-link).
   - **Abonnement Azure** : Sélectionnez le compte **Abonnement**, puis le **Groupe de ressources** et le **Compte de stockage**. Facultativement, si vous souhaitez ingérer des données à partir d'un compte de stockage via un lien privé Azure, sélectionnez **Activer la liaison privée**. Pour plus d’informations, consultez [Liaisons privées](security-overview.md#set-up-an-azure-private-link).
  
   > [!NOTE]
   > L’un des rôles suivants pour le conteneur ou le compte de stockage est nécessaire pour créer la source de données :
   >
   >  - Le rôle Lecteur des données blob de stockage est suffisant pour lire à partir d’un compte de stockage et ingérer les données dans Customer Insights.
   >  - Le rôle Contributeur ou propriétaire des données blob de stockage est nécessaire si vous souhaitez modifier les fichiers manifeste directement dans Customer Insights.  
  
1. Choisissez le nom du **Conteneur** contenant les données et le schéma (fichier model.json ou manifest.json) à partir desquels importer les données, puis sélectionnez **Suivant**.
   > [!NOTE]
   > Tout fichier model.json ou manifest.json associé à une autre source de données dans l’environnement n’apparaîtra pas dans la liste. Cependant, le même fichier model.json ou manifest.json peut être utilisé pour les sources de données dans plusieurs environnements.

1. Pour créer un nouveau schéma, accédez à [Créer un nouveau fichier de schéma](#create-a-new-schema-file).

1. Pour utiliser un schéma existant, accédez au dossier contenant le fichier model.json ou manifest.cdm.json. Vous pouvez effectuer une recherche dans un répertoire pour trouver le fichier.

1. Sélectionnez le fichier json, puis sélectionnez **Suivant**. La liste des entités disponibles s'affiche.

   :::image type="content" source="media/review-entities.png" alt-text="Boîte de dialogue de la liste d'entités à sélectionner":::

1. Sélectionnez les entités souhaitées à inclure.

   :::image type="content" source="media/ADLS_required.png" alt-text="Boîte de dialogue indiquant Obligatoire pour la clé primaire":::

   > [!TIP]
   > Pour modifier une entité dans une interface d’édition JSON, sélectionnez-la, puis sélectionner **Modifier le fichier de schéma**. Apportez vos modifications, puis sélectionnez **Enregistrer**.

1. Pour les entités sélectionnées nécessitant une ingestion incrémentielle, **Obligatoire** s'affiche sous **Actualisation incrémentielle**. Pour chacune de ces entités, voir [Configurer une actualisation incrémentielle pour les sources de données Azure Data Lake](incremental-refresh-data-sources.md).

1. Pour les entités sélectionnées où une clé primaire n'a pas été définie, **Obligatoire** s'affiche sous **Clé primaire**. Pour chacune de ces entités :
   1. Sélectionnez **Obligatoire**. Le panneau **Modifier l'entité** s'affiche.
   1. Choisissez la **Clé primaire**. La clé primaire est un attribut unique à l’entité. Pour qu’un attribut soit une clé primaire valide, il ne doit inclure aucune valeur en double, aucune valeur manquante, ni aucune valeur nulle. Les attributs de type de données chaîne, entier et GUID sont pris en charge en tant que clés primaires.
   1. Facultativement, modifiez le modèle de partition.
   1. Sélectionnez **Fermer**, puis enregistrez et fermez le volet.

1. Sélectionnez le nombre d'**attributs** pour chaque entité incluse. La page **Gérer les attributs** s'affiche.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Boîte de dialogue pour sélectionner le profilage des données.":::

   1. Créez de nouveaux attributs, modifiez ou supprimez des attributs existants. Vous pouvez modifier le nom, le format des données ou ajouter un type sémantique.
   1. Pour activer l'analyse et d'autres fonctionnalités, sélectionnez **Profilage des données** pour l'ensemble de l'entité ou pour des attributs spécifiques. Par défaut, aucune entité n’est activée pour le profilage des données.
   1. Cliquez sur **Terminé**.

1. Cliquez sur **Enregistrer**. La page **Source de données** s'ouvre et affiche la nouvelle source de données avec le statut **Actualisation en cours**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Le chargement des données peut prendre du temps. Après une actualisation réussie, les données ingérées peuvent être consultées à partir de la page [**Entités**](entities.md).

### <a name="create-a-new-schema-file"></a>Créer un fichier de schéma

1. Sélectionnez **Nouveau fichier de schéma**.

1. Saisissez un nom pour le fichier et sélectionnez **Enregistrer**.

1. Sélectionnez **Nouvelle entité**. Le panneau **Nouvelle entité** s'affiche.

1. Entrez le nom de l'entité et choisissez l'**Emplacement des fichiers de données**.
   - **Plusieurs fichiers .csv ou .parquet** : Naviguez jusqu'au dossier racine, sélectionnez le type de motif et saisissez l'expression.
   - **Fichiers .csv ou .parquet uniques** : Naviguez jusqu'au fichier .csv ou .parquet et sélectionnez-le.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Boîte de dialogue pour créer une nouvelle entité avec l'emplacement des fichiers de données en surbrillance.":::

1. Cliquez sur **Enregistrer**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Boîte de dialogue pour définir ou générer automatiquement des attributs.":::

1. Sélectionnez **définir les attributs** pour ajouter manuellement les attributs, ou sélectionnez **les générer automatiquement**. Pour définir les attributs, entrez un nom, sélectionnez le format de données et le type sémantique facultatif. Pour les attributs générés automatiquement :

   1. Une fois les attributs générés automatiquement, sélectionnez **Examiner les attributs**. La page **Gérer les attributs** s'affiche.

   1. Assurez-vous que le format de données est correct pour chaque attribut.

   1. Pour activer l'analyse et d'autres fonctionnalités, sélectionnez **Profilage des données** pour l'ensemble de l'entité ou pour des attributs spécifiques. Par défaut, aucune entité n’est activée pour le profilage des données.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Boîte de dialogue pour sélectionner le profilage des données.":::

   1. Cliquez sur **Terminé**. La page **Sélectionner des entités** s'affiche.

1. Continuez à ajouter des entités et des attributs, le cas échéant.

1. Une fois toutes les entités ajoutées, sélectionnez **Inclure** pour inclure les entités dans l'ingestion de source de données.

   :::image type="content" source="media/ADLS_required.png" alt-text="Boîte de dialogue indiquant Obligatoire pour la clé primaire":::

1. Pour les entités sélectionnées nécessitant une ingestion incrémentielle, **Obligatoire** s'affiche sous **Actualisation incrémentielle**. Pour chacune de ces entités, voir [Configurer une actualisation incrémentielle pour les sources de données Azure Data Lake](incremental-refresh-data-sources.md).

1. Pour les entités sélectionnées où une clé primaire n'a pas été définie, **Obligatoire** s'affiche sous **Clé primaire**. Pour chacune de ces entités :
   1. Sélectionnez **Obligatoire**. Le panneau **Modifier l'entité** s'affiche.
   1. Choisissez la **Clé primaire**. La clé primaire est un attribut unique à l’entité. Pour qu’un attribut soit une clé primaire valide, il ne doit inclure aucune valeur en double, aucune valeur manquante, ni aucune valeur nulle. Les attributs de type de données chaîne, entier et GUID sont pris en charge en tant que clés primaires.
   1. Facultativement, modifiez le modèle de partition.
   1. Sélectionnez **Fermer**, puis enregistrez et fermez le volet.

1. Cliquez sur **Enregistrer**. La page **Source de données** s'ouvre et affiche la nouvelle source de données avec le statut **Actualisation en cours**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Le chargement des données peut prendre du temps. Après une actualisation réussie, les données ingérées peuvent être consultées à partir de la page [**Entités**](entities.md).

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Modifier une source de données Azure Data Lake Storage

Vous pouvez mettre à jour l'option *Se connecter au compte de stockage à l'aide de*. Pour plus d’informations, consultez [Connecter Customer Insights à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure](connect-service-principal.md). Pour vous connecter à un autre conteneur à partir de votre compte de stockage ou modifier le nom du compte, [créer une connexion de source de données](#connect-to-azure-data-lake-storage).

1. Accédez à **Données** > **Sources de données**.

1. En regard de la source de données que vous souhaitez mettre à jour, sélectionnez **Modifier**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Boîte de dialogue pour modifier une source de données Azure Data Lake.":::

1. Modifiez les informations suivantes :

   - **Description**
   - **Connectez votre stockage à l'aide de** et les informations de connexion. Vous ne pouvez pas modifier les informations du **Conteneur** lors de la mise à jour de la connexion.
      > [!NOTE]
      > L'un des rôles suivants doit être attribué au compte de stockage ou au conteneur :
        > - Lecteur de données d’objets BLOB de stockage
        > - Propriétaire de données d’objets BLOB de stockage
        > - Contributeur de données BLOB de stockage

   - **Activez la liaison privée** si vous souhaitez ingérer des données à partir d'un compte de stockage via une liaison Azure Private Link. Pour plus d’informations, consultez [Liaisons privées](security-overview.md#set-up-an-azure-private-link).

1. Cliquez sur **Suivant**.
1. Modifiez ce qui suit :
   - Accédez à un autre fichier model.json ou manifest.json avec un ensemble d'entités différent du conteneur.
   - Pour ajouter des entités supplémentaires à ingérer, sélectionnez **Nouvelle entité**.
   - Pour supprimer toutes les entités déjà sélectionnées s'il n'y a pas de dépendances, sélectionnez l'entité et **Supprimer**.
      > [!IMPORTANT]
      > S’il existe des dépendances sur le fichier model.json ou manifest.json existant et sur l’ensemble d’entités, vous verrez un message d’erreur et vous ne pourrez pas sélectionner un autre fichier model.json ou manifest.json. Supprimez ces dépendances avant de modifier le fichier model.json ou manifest.json ou créez une source de données avec le fichier model.json ou manifest.json que vous souhaitez utiliser pour éviter de supprimer les dépendances.
   - Pour modifier l'emplacement du fichier de données ou la clé primaire, sélectionnez **Modifier**.
   - Pour modifier les données d’ingestion incrémentielle, consultez [Configurer une actualisation incrémentielle pour les sources de données Azure Data Lake](incremental-refresh-data-sources.md).
   - Modifiez uniquement le nom de l’entité pour qu’il corresponde au nom de l’entité dans le fichier .json.

     > [!NOTE]
     > Conservez toujours le même nom d’entité dans Customer Insights que le nom d’entité dans le fichier model.json ou manifest.json après l’ingestion. Customer Insights valide tous les noms d’entité avec model.json ou manifest.json lors de chaque actualisation du système. Si un nom d’entité est modifié à l’intérieur ou à l’extérieur de Customer Insights, une erreur se produit car Customer Insights ne peut pas trouver le nouveau nom d’entité dans le fichier .json. Si un nom d’entité ingéré a été accidentellement modifié, modifiez le nom de l’entité dans Customer Insights pour qu’il corresponde au nom dans le fichier .json.

1. Sélectionnez **Attributs** pour ajouter ou modifier des attributs, ou pour activer le profilage des données. Puis sélectionnez **Terminé**.

1. Cliquez sur **Enregistrer** pour appliquer vos modifications et revenir à la page **Sources de données**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
