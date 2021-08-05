---
title: Créer et gérer des environnements
description: Découvrez comment souscrire au service et comment gérer des environnements.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2f115269b9d07dd118ec18cc48b55de8aea9b5bb
ms.sourcegitcommit: 98267da3f3eddbdfbc89600a7f54e5e664a8f069
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/28/2021
ms.locfileid: "6683470"
---
# <a name="manage-environments"></a>Gérer des environnements

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Changer d’environnements

Sélectionnez le contrôle **Environnement** dans le coin supérieur droit de la page pour changer d’environnement.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Capture d’écran du contrôle pour changer d’environnement.":::

Les administrateurs peuvent [créer](get-started-paid.md) et gérer des environnements.

## <a name="edit-an-existing-environment"></a>Modifier un environnement existant

Vous pouvez modifier certains détails des environnements existants.

1.  Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.

2.  Sélectionnez l’icône **Modifier**.

3. Dans la zone **Modifier l’environnement**, vous pouvez mettre à jour le **Nom d’affichage** de l’environnement, mais vous ne pouvez pas changer la **Région** ou le **Type**.

4. Si un environnement est configuré pour stocker des données dans Azure Data Lake Storage, vous pouvez mettre à jour la **Clé de compte**. Cependant, vous ne pouvez pas modifier le **Nom du compte** ou le nom **Conteneur**.

5. Vous pouvez éventuellement mettre à jour une connexion basée sur une clé de compte vers une connexion basée sur une ressource ou un abonnement. Une fois mise à niveau, vous ne pouvez pas rétablir la clé de compte après la mise à jour. Pour plus d’informations, consultez [Connecter les informations sur l’audience à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure](connect-service-principal.md). Vous ne pouvez pas modifier les informations du **Conteneur** lors de la mise à jour de la connexion.

6. Vous pouvez éventuellement fournir une URL de l’environnement Microsoft Dataverse dans **Configurer le partage de données avec Microsoft Dataverse et activer des fonctionnalités supplémentaires**. Ces fonctionnalités comprennent le partage de données avec les applications et les solutions basées sur Microsoft Dataverse, l’ingestion de données à partir de sources de données locales ou l’utilisation de [prédictions](predictions.md). Sélectionnez **Activer le partage de données** pour partager les données de sortie Customer Insights avec un Data Lake géré par Microsoft Dataverse.

   > [!NOTE]
   > - Le partage de données avec un Data Lake géré par Microsoft Dataverse n’est actuellement pas pris en charge lorsque vous enregistrez toutes les données dans votre propre Azure Data Lake Storage.
   > - [Prédiction de la valeur manquante dans une entité](predictions.md) et les rapports PowerBI intégrés dans les informations sur l’audience (si activés sur votre environnement) ne sont actuellement pas pris en charge lorsque vous activez le partage de données avec le lac de données géré Microsoft Dataverse.

   Après l’activation du partage de données avec Microsoft Dataverse, une actualisation complète de vos sources de données et d’autres processus démarre. Si des processus sont actuellement en cours d’exécution, vous ne voyez pas l’option pour activer le partage de données avec Microsoft Dataverse. Attendez la fin de ces processus ou les annuler pour activer le partage de données. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Options de configuration pour activer le partage de données avec Microsoft Dataverse.":::
   
   Lorsque vous exécutez des processus, tels que l’ingestion de données ou la création de segments, les dossiers correspondants seront créés dans le compte de stockage que vous avez spécifié ci-dessus. Les fichiers de données et les fichiers model.json seront créés et ajoutés aux sous-dossiers respectifs, selon le processus que vous exécutez.

## <a name="copy-the-environment-configuration"></a>Copier la configuration de l’environnement

Lorsque vous créez un environnement, vous pouvez choisir de copier la configuration à partir d’un environnement existant. 

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
- Actualisation planifiée
- Enrichissements
- Gestion des modèles
- Attributions de rôles

Les données suivantes ne sont *pas* copiées :

- Profils client.
- Informations d’identification d’une source de données. Vous devrez fournir les informations d’identification pour chaque source de données et actualiser les sources de données manuellement.
- Sources de données du dossier Common Data Model et Data Lake géré par Dataverse. Vous devez créer ces sources de données manuellement avec le même nom que dans l’environnement source.

Lorsque vous copiez un environnement, vous voyez un message de confirmation de création du nouvel environnement. Sélectionnez **Accéder aux sources de données** pour voir la liste des sources de données.

Toutes les sources de données affichent un statut **Identifiants requis**. Modifiez les sources de données et entrez les informations d’identification pour les actualiser.

:::image type="content" source="media/data-sources-copied.png" alt-text="Liste des sources de données qui ont été copiées et qui nécessitent une authentification.":::

Après avoir actualisé les sources de données, accédez à **Données** > **Unifier**. Vous trouverez ici les paramètres de l’environnement source. Modifiez-les selon vos besoins ou sélectionnez **Exécuter** pour démarrer le processus d’unification des données et créer l’entité client unifiée.

Une fois l’unification des données terminée, accédez à **Mesures** et **Segments** pour les actualiser.

## <a name="reset-an-existing-environment"></a>Réinitialiser un environnement existant

En tant qu’administrateur, vous pouvez réinitialiser un environnement à un état vide si vous souhaitez supprimer toutes les configurations et supprimer les données ingérées.

1.  Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application. 

2.  Sélectionnez l’environnement à réinitialiser, puis les points de suspension (**...**). 

3. Choisissez l’option **Réinitialiser**. 

4.  Pour confirmer la suppression, entrez le nom de l’environnement et sélectionnez **Réinitialiser**.

## <a name="delete-an-existing-environment"></a>Supprimer un environnement existant

En tant qu’administrateur, vous pouvez supprimer un environnement que vous administrez.

1.  Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.

2.  Sélectionnez l’environnement à réinitialiser, puis les points de suspension (**...**). 

3. Choisissez l’option **Supprimer**. 

4.  Pour confirmer la suppression, sélectionnez le nom de l’environnement et sélectionnez **Supprimer**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
