---
title: Connecter les données Common Data Model à un compte Azure Data Lake
description: Utilisez les données Common Data Model avec Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596542"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Se connecter à un dossier Common Data Model à l’aide d’un compte Azure Data Lake

Cet article fournit des informations sur l’ingestion de données à partir d’un dossier Common Data Model en utilisant votre compte Azure Data Lake Storage Gen2.

## <a name="important-considerations"></a>Remarques importantes

- Les données de votre lac de données Azure Data Lake doivent respecter la norme Common Data Model. Les autres formats ne sont pas pris en charge pour le moment.

- L’ingestion de données prend en charge les comptes de stockage Azure Data Lake *Gen2* exclusivement. Vous ne pouvez pas utiliser les comptes de stockage Azure Data Lake Gen1 pour ingérer des données.

- Pour vous authentifier dans un principal de service Azure, assurez-vous que celui-ci est configuré dans votre client. Pour plus d’informations, consultez [Connecter les informations sur l’audience à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure](connect-service-principal.md).

- Le compte Azure Data Lake à partir duquel vous souhaitez vous connecter et ingérer des données doit se trouver dans la même région Azure que l’environnement Dynamics 365 Customer Insights. Les connexions à un dossier Common Data Model à partir d’un lac de données situé dans une autre région Azure ne sont pas prises en charge. Pour connaître la région Azure de l’environnement, accédez à **Administrateur** > **Système** > **À propos de** dans les informations sur l’audience.

- Les données stockées dans les services en ligne peuvent être stockées dans un emplacement différent de celui où les données sont traitées ou stockées dans Dynamics 365 Customer Insights. En important ou en vous connectant aux données stockées dans les services en ligne, vous acceptez que les données puissent être transférées et stockées avec Dynamics 365 Customer Insights. [En savoir plus sur le Centre de gestion de la confidentialité Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Se connecter à un dossier Common Data Model

1. Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.

1. Sélectionnez **Ajouter une source de données**.

1. Sélectionnez **Se connecter à un dossier Common Data Model**, entrez un **Nom** pour la source de données et sélectionnez **Suivant**. Instructions relatives au nom : 
   - Commencez par une lettre.
   - Utilisez uniquement des lettres et des chiffres. Les espaces et caractères spéciaux ne sont pas autorisés.
   - Utilisez entre 3 et 64 caractères.

1. Vous pouvez choisir entre une option basée sur une ressource et une option basée sur un abonnement pour l’authentification. Pour plus d’informations, consultez [Connecter les informations sur l’audience à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure](connect-service-principal.md). Entrez les informations du **Conteneur** et sélectionnez **Suivant**.
   > [!div class="mx-imgBorder"]
   > ![Boîte de dialogue pour entrer de nouveaux détails de connexion pour Azure Data Lake](media/enter-new-storage-details.png)
   > [!NOTE]
   > Vous avez besoin de l’un des rôles suivants pour le conteneur ou le compte de stockage mentionné ci-dessus pour pouvoir vous connecter et créer une source de données :
   >  - Lecteur de données d’objets BLOB de stockage
   >  - Propriétaire de données d’objets BLOB de stockage
   >  - Contributeur de données BLOB de stockage

1. Dans la boîte de dialogue **Sélectionner un dossier Common Data Model**, sélectionnez le fichier model.json ou manifest.json à partir duquel importer les données, puis sélectionnez **Suivant**.
   > [!NOTE]
   > Tout fichier model.json ou manifest.json associé à une autre source de données dans l’environnement n’apparaîtra pas dans la liste.

1. Vous obtiendrez une liste des entités disponibles dans le fichier model.json ou manifest.json sélectionné. Vous pouvez vérifier et sélectionner à partir de la liste des entités disponibles et sélectionnez **Enregistrer**. Toutes les entités sélectionnées seront ingérées à partir de la nouvelle source de données.
   > [!div class="mx-imgBorder"]
   > ![Boîte de dialogue affichant une liste d’entités à partir d’un fichier model.json](media/review-entities.png)

8. Indiquez pour quelles entités de données vous souhaitez activer le profilage des données, puis sélectionnez **Enregistrer**. Le profilage des données permet l’analyse et d’autres fonctionnalités. Vous pouvez sélectionner toute l’entité, ce qui entraîne la sélection de tous les attributs de l’entité, ou sélectionner certains attributs de votre choix. Par défaut, aucune entité n’est activée pour le profilage des données.
   > [!div class="mx-imgBorder"]
   > ![Boîte de dialogue illustrant un profilage des données](media/dataprofiling-entities.png)

9. Après avoir enregistré vos sélections, la page **Source d’informations** s’ouvre. Vous devriez maintenant voir la connexion au dossier Common Data Model en tant que source de données.

> [!NOTE]
> Un fichier model.json ou manifest.json ne peut être associé qu’à une seule source de données dans le même environnement. Cependant, le même fichier model.json ou manifest.json peut être utilisé pour les sources de données dans plusieurs environnements.

## <a name="edit-a-common-data-model-folder-data-source"></a>Modifier une source de données de dossier Common Data Model

Vous pouvez mettre à jour la clé d’accès du compte de stockage contenant le dossier Common Data Model. Vous pouvez également modifier le fichier model.json ou manifest.json. Pour vous connecter à un autre conteneur à partir de votre compte de stockage ou modifier le nom du compte, [créer une connexion de source de données](#connect-to-a-common-data-model-folder).

1. Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.

2. En regard de la source de données que vous souhaitez mettre à jour, sélectionnez les points de suspension.

3. Sélectionnez l’option **Modifier** dans la liste.

4. Éventuellement, mettez à jour la **Clé d’accès** et sélectionnez **Suivant**.

   ![Boîte de dialogue permettant de modifier et mettre à jour une clé d’accès pour une source de données existante](media/edit-access-key.png)

5. Vous pouvez éventuellement mettre à jour une connexion de clé de compte vers une connexion basée sur une ressource ou un abonnement. Pour plus d’informations, consultez [Connecter les informations sur l’audience à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure](connect-service-principal.md). Vous ne pouvez pas modifier les informations du **Conteneur** lors de la mise à jour de la connexion.
   > [!div class="mx-imgBorder"]

   > ![Boîte de dialogue pour entrer les détails de connexion d’Azure Data Lake à un compte de stockage existant](media/enter-existing-storage-details.png)

   > [!NOTE]
   > Vous avez besoin de l’un des rôles suivants pour le conteneur ou le compte de stockage mentionné ci-dessus pour pouvoir vous connecter et créer une source de données :
   >  - Lecteur de données d’objets BLOB de stockage
   >  - Propriétaire de données d’objets BLOB de stockage
   >  - Contributeur de données BLOB de stockage


6. Vous pouvez également choisir un fichier model.json ou manifest.json différent avec un ensemble d’entités différent du conteneur.

7. Vous pouvez éventuellement sélectionner des entités supplémentaires à ingérer. Vous pouvez également supprimer toutes les entités déjà sélectionnées s’il n’y a pas de dépendances.

   > [!IMPORTANT]
   > S’il existe des dépendances sur le fichier model.json ou manifest.json existant et sur l’ensemble d’entités, vous verrez un message d’erreur et vous ne pourrez pas sélectionner un autre fichier model.json ou manifest.json. Supprimez ces dépendances avant de modifier le fichier model.json ou manifest.json ou créez une source de données avec le fichier model.json ou manifest.json que vous souhaitez utiliser pour éviter de supprimer les dépendances.

8. Vous pouvez éventuellement sélectionner des attributs ou entités supplémentaires pour activer le profilage des données, ou désactiver ceux déjà sélectionnés.   


[!INCLUDE[footer-include](../includes/footer-banner.md)]