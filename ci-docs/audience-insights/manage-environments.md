---
title: Créer et gérer des environnements
description: Découvrez comment souscrire au service et comment gérer des environnements.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304877"
---
# <a name="manage-environments"></a>Gérer des environnements

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Cet article explique comment créer une nouvelle organisation et comment mettre en service un environnement.

## <a name="sign-up-and-create-an-organization"></a>S’inscrire et créer une organisation

1. Accédez au site Web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Sélectionnez **Mise en route**.

3. Choisissez votre scénario d’inscription préféré et sélectionnez le lien correspondant.

4. Acceptez les conditions générales et sélectionnez **Continuer** pour commencer à créer l’organisation.

5. Une fois l’environnement créé, vous serez redirigé vers [Customer Insights](https://home.ci.ai.dynamics.com).

6. Utilisez l’environnement de démonstration pour explorer l’application ou créez un nouvel environnement en suivant les étapes de la section suivante.

7. Après avoir spécifié les paramètres d’environnement, sélectionnez **Créer**.

8. Vous serez connecté une fois l’environnement créé avec succès.

## <a name="create-an-environment-in-an-existing-organization"></a>Créer un environnement dans une organisation existante

Il existe deux façons de créer un environnement. Vous pouvez soit spécifier une toute nouvelle configuration, soit copier certains paramètres de configuration à partir d’un environnement existant.

> [!NOTE]
> Les organisations peuvent créer *deux* environnements pour chaque licence Customer Insights. Si votre organisation achète plus d’une licence, [contactez notre équipe de support](https://go.microsoft.com/fwlink/?linkid=2079641) pour augmenter le nombre d’environnements disponibles. Pour plus d’informations sur la capacité et la capacité supplémentaire, téléchargez le [Guide des licences Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Pour créer un environnement :

1. Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.

1. Cliquez sur **Nouveau**.

   > [!div class="mx-imgBorder"]
   > ![Paramètres de l’environnement.](media/environment-settings-dialog.png)

1. Dans la boîte de dialogue **Créer un environnement**, sélectionnez **Nouvel environnement**.

   Si vous souhaitez [copier les données de l’environnement actuel](#considerations-for-copy-configuration-preview), sélectionnez **Copier à partir d’un environnement existant**. Vous voyez la liste de tous les environnements disponibles dans votre organisation à partir desquels vous pouvez copier des données.

1. Indiquez les détails suivants :
   - **Nom** : nom de cet environnement. Ce champ est déjà rempli si vous copiez à partir d’un environnement existant, mais vous pouvez le modifier.
   - **Type** : Indiquez si vous souhaitez créer un environnement de Production ou Sandbox.
   - **Région** : Région dans laquelle le service est déployé et hébergé.
   
1. Vous pouvez éventuellement sélectionner **Paramètres avancés** :

   - **Enregistrer toutes les données dans** : Spécifie où vous souhaitez stocker les données de sortie générées à partir de Customer Insights. Vous aurez deux options : **Stockage Customer Insights** (un Azure Data Lake géré par l’équipe Customer Insights) et **Azure Data Lake Storage** (votre propre Azure Data Lake Storage). Par défaut, l’option de stockage Customer Insights est sélectionnée.

     > [!NOTE]
     > En enregistrant des données dans Azure Data Lake Storage, vous acceptez que les données soient transférées et stockées dans l’emplacement géographique approprié pour ce compte de stockage Azure, ce qui peut différer de l’emplacement de stockage des données dans Dynamics 365 Customer Insights. [En savoir plus sur le Microsoft Trust Center.](https://www.microsoft.com/trust-center)
     >
     > Actuellement, les entités ingérées sont toujours stockées dans le Data Lake géré par Customer Insights. 
     > 
     > Nous ne prenons en charge que les comptes Azure Data Lake Storage de la même région Azure que celle sélectionnée lors de la création de l’environnement. 
     > 
     > Nous ne prenons en charge que les comptes Azure Data Lake Storage pour lesquels l’espace de noms hiérarchique est activé.


   - Pour l’option Azure Data Lake Storage, vous pouvez choisir entre une option basée sur une ressources et une option basée sur un abonnement pour l’authentification. Pour plus d’informations, consultez [Connecter les informations sur l’audience à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure](connect-service-principal.md). Le nom du **Conteneur** ne peut pas être modifié et sera `customerinsights`.
   
   - Si vous souhaitez utiliser des [prédictions](predictions.md), configurer le partage de données avec Microsoft Dataverse ou activer l’ingestion de données à partir de sources de données locales, fournissez l’URL de l’environnement Microsoft Dataverse dans **Configurer le partage de données avec Microsoft Dataverse et activer des fonctionnalités supplémentaires**. Sélectionnez **Activer le partage de données** pour partager les données de sortie Customer Insights avec un lac de données géré Microsoft Dataverse.

     > [!NOTE]
     > - Le partage de données avec le lac de données géré Microsoft Dataverse n’est actuellement pas pris en charge lorsque vous enregistrez toutes les données dans votre propre Azure Data Lake Storage.
     > - La [prédiction de valeurs manquantes dans une entité](predictions.md) n’est actuellement pas prise en charge lorsque vous activez le partage de données avec le lac de données géré Microsoft Dataverse.

     > [!div class="mx-imgBorder"]
     > ![Options de configuration pour activer le partage de données avec Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)

   Lorsque vous exécutez des processus, tels que l’ingestion de données ou la création de segments, les dossiers correspondants seront créés dans le compte de stockage que vous avez spécifié ci-dessus. Les fichiers de données et les fichiers model.json seront créés et ajoutés aux dossiers en fonction du nom du processus.

   Si vous créez plusieurs environnements de Customer Insights et choisissez d’enregistrer les entités de sortie de ces environnements dans votre compte de stockage, des dossiers distincts seront créés pour chaque environnement avec ci_<environmentid> dans le conteneur.

### <a name="considerations-for-copy-configuration-preview"></a>Considérations sur la configuration de la copie (version préliminaire)

Les paramètres de configuration suivants sont copiés :

- Configurations des fonctionnalités
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

Les paramètres suivants ne sont *pas* copiés :

- Profils client.
- Informations d’identification d’une source de données. Vous devrez fournir les informations d’identification pour chaque source de données et actualiser les sources de données manuellement.
- Sources de données du dossier Common Data Model et Data Lake géré par Dataverse. Vous devez créer ces sources de données manuellement avec le même nom que dans l’environnement source.

Lorsque vous copiez un environnement, vous voyez un message de confirmation de création du nouvel environnement. Sélectionnez **Accéder aux sources de données** pour voir la liste des sources de données.

Toutes les sources de données affichent un statut **Identifiants requis**. Modifiez les sources de données et entrez les informations d’identification pour les actualiser.

> [!div class="mx-imgBorder"]
> ![Sources de données copiées.](media/data-sources-copied.png)

Après avoir actualisé les sources de données, accédez à **Données** > **Unifier**. Vous trouverez ici les paramètres de l’environnement source. Modifiez-les selon vos besoins ou sélectionnez **Exécuter** pour démarrer le processus d’unification des données et créer l’entité client unifiée.

Une fois l’unification des données terminée, accédez à **Mesures** et **Segments** pour les actualiser.

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
   > - La [prédiction des valeurs manquantes dans une entité](predictions.md) n’est actuellement pas prise en charge lorsque vous activez le partage de données avec un Data Lake géré par Microsoft Dataverse.

   Après l’activation du partage de données avec Microsoft Dataverse, une actualisation complète de vos sources de données et d’autres processus démarre. Si des processus sont actuellement en cours d’exécution, vous ne voyez pas l’option pour activer le partage de données avec Microsoft Dataverse. Attendez la fin de ces processus ou les annuler pour activer le partage de données. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Options de configuration pour activer le partage de données avec Microsoft Dataverse.":::
   
   Lorsque vous exécutez des processus, tels que l’ingestion de données ou la création de segments, les dossiers correspondants seront créés dans le compte de stockage que vous avez spécifié ci-dessus. Les fichiers de données et les fichiers model.json seront créés et ajoutés aux sous-dossiers respectifs, selon le processus que vous exécutez.

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
