---
title: Créer et gérer des environnements
description: Découvrez comment souscrire au service et comment gérer des environnements.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270109"
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

Pour créer un environnement :

1. Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.

1. Cliquez sur **Nouveau**.

   > [!div class="mx-imgBorder"]
   > ![Paramètres de l’environnement](media/environment-settings-dialog.png)

1. Dans la boîte de dialogue **Créer un environnement**, sélectionnez **Nouvel environnement**.

   Si vous souhaitez [copier les données de l’environnement actuel](#additional-considerations-for-copy-configuration-preview), sélectionnez **Copier à partir d’un environnement existant**. Vous voyez la liste de tous les environnements disponibles dans votre organisation à partir desquels vous pouvez copier des données.

1. Indiquez les détails suivants :
   - **Nom** : nom de cet environnement. Ce champ est déjà rempli si vous copiez à partir d’un environnement existant, mais vous pouvez le modifier.
   - **Région** : Région dans laquelle le service est déployé et hébergé.
   - **Type** : Indiquez si vous souhaitez créer un environnement de Production ou Sandbox.

2. Vous pouvez éventuellement sélectionner **Paramètres avancés** :

   - **Enregistrer toutes les données dans** : Spécifie où vous souhaitez stocker les données de sortie générées à partir de Customer Insights. Vous aurez deux options : **Stockage Customer Insights** (un Azure Data Lake géré par l’équipe Customer Insights) et **Azure Data Lake Storage Gen2** (votre propre Azure Data Lake Storage). Par défaut, l’option de stockage Customer Insights est sélectionnée.

   > [!NOTE]
   > En enregistrant des données dans Azure Data Lake Storage, vous acceptez que les données soient transférées et stockées dans l’emplacement géographique approprié pour ce compte de stockage Azure, ce qui peut différer de l’emplacement de stockage des données dans Dynamics 365 Customer Insights. [En savoir plus sur le Microsoft Trust Center.](https://www.microsoft.com/trust-center)
   >
   > Actuellement, les entités ingérées sont toujours stockées dans le lac de données géré par Customer Insights.
   > Nous ne prenons en charge que les comptes de stockage Azure Data Lake Gen2 situés dans la même région Azure que celle vous avez sélectionnée lors de la création de l’environnement.
   > Nous prenons uniquement en charge les comptes de stockage compatibles HNS (Hierarchical Name Space) d’Azure Data Lake Gen2.

   - Pour l’option Azure Data Lake Storage Gen2, vous pouvez choisir entre une option basée sur une ressource et une option basée sur un abonnement pour l’authentification. Pour plus d’informations, consultez [Connecter les informations sur l’audience à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure](connect-service-principal.md). Le nom du **Conteneur** ne peut pas être modifié et sera « customerinsights ».
   
   - Si vous souhaitez utiliser des [prédictions](predictions.md) ou configurer le partage de données avec des applications et des solutions basées sur Microsoft Dataverse, fournissez l’URL d’environnement Microsoft Dataverse sous **Configurer le partage de données avec Microsoft Dataverse et activer des capacités supplémentaires**. Sélectionnez **Activer le partage de données** pour partager les données de sortie Customer Insights avec un lac de données géré Microsoft Dataverse.

     > [!NOTE]
     > - Le partage de données avec le lac de données géré Microsoft Dataverse n’est actuellement pas pris en charge lorsque vous enregistrez toutes les données dans votre propre Azure Data Lake Storage.
     > - La [prédiction de valeurs manquantes dans une entité](predictions.md) n’est actuellement pas prise en charge lorsque vous activez le partage de données avec le lac de données géré Microsoft Dataverse.

     > [!div class="mx-imgBorder"]
     > ![Options de configuration pour activer le partage de données avec Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)

   Lorsque vous exécutez des processus, tels que l’ingestion de données ou la création de segments, les dossiers correspondants seront créés dans le compte de stockage que vous avez spécifié ci-dessus. Les fichiers de données et les fichiers model.json sont créés et ajoutés aux sous-dossiers respectifs en fonction du processus que vous exécutez.

   Si vous créez plusieurs environnements de Customer Insights et choisissez d’enregistrer les entités de sortie de ces environnements dans votre compte de stockage, des dossiers distincts seront créés pour chaque environnement avec ci_<environmentid> dans le conteneur.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Considérations supplémentaires pour la configuration de la copie (version préliminaire)

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
- Sources de données du dossier Common Data Model et du lac géré Common Data Service. Vous devez créer ces sources de données manuellement avec le même nom que dans l’environnement source.

Lorsque vous copiez un environnement, vous voyez un message de confirmation de création du nouvel environnement. Sélectionnez **Accéder aux sources de données** pour voir la liste des sources de données.

Toutes les sources de données affichent un statut **Identifiants requis**. Modifiez les sources de données et entrez les informations d’identification pour les actualiser.

> [!div class="mx-imgBorder"]
> ![Sources de données copiées](media/data-sources-copied.png)

Après avoir actualisé les sources de données, accédez à **Données** > **Unifier**. Vous trouverez ici les paramètres de l’environnement source. Modifiez-les selon vos besoins ou sélectionnez **Exécuter** pour démarrer le processus d’unification des données et créer l’entité client unifiée.

Une fois l’unification des données terminée, accédez à **Mesures** et **Segments** pour les actualiser.

## <a name="edit-an-existing-environment"></a>Modifier un environnement existant

Vous pouvez modifier certains détails des environnements existants.

1.  Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.

2.  Sélectionnez l’icône **Modifier**.

3. Dans la zone **Modifier l’environnement**, vous pouvez mettre à jour le **Nom d’affichage** de l’environnement, mais vous ne pouvez pas changer la **Région** ou le **Type**.

4. Si un environnement est configuré pour stocker des données dans Azure Data Lake Storage Gen2, vous pouvez mettre à jour la **Clé de compte**. Cependant, vous ne pouvez pas modifier le **Nom du compte** ou le nom **Conteneur**.

5. Vous pouvez éventuellement mettre à jour une connexion basée sur une clé de compte vers une connexion basée sur une ressource ou un abonnement. Une fois mise à niveau, vous ne pouvez pas rétablir la clé de compte après la mise à jour. Pour plus d’informations, consultez [Connecter les informations sur l’audience à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure](connect-service-principal.md). Vous ne pouvez pas modifier les informations du **Conteneur** lors de la mise à jour de la connexion.

## <a name="reset-an-existing-environment"></a>Réinitialiser un environnement existant

En tant qu’administrateur, vous pouvez réinitialiser un environnement à un état vide si vous souhaitez supprimer toutes les configurations et supprimer les données ingérées.

1.  Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application. 

2.  Sélectionnez l’environnement à réinitialiser, puis les points de suspension **...**. 

3. Choisissez l’option **Réinitialiser**. 

4.  Pour confirmer la suppression, entrez le nom de l’environnement et sélectionnez **Réinitialiser**.

## <a name="delete-an-existing-environment-available-only-for-admins"></a>Supprimer un environnement existant (disponible uniquement pour les administrateurs)

En tant qu’administrateur, vous pouvez supprimer un environnement que vous administrez.

1.  Cliquez sur le sélecteur **Environnement** dans l’en-tête de l’application.

2.  Sélectionnez l’environnement à réinitialiser, puis les points de suspension **...**. 

3. Choisissez l’option **Supprimer**. 

4.  Pour confirmer la suppression, sélectionnez le nom de l’environnement et sélectionnez **Supprimer**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]