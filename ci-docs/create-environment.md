---
title: Procédure pour créer un nouvel environnement
description: Étapes pour créer des environnements dans Dynamics 365 Customer Insights.
ms.date: 05/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 33c8910b7a4dd8723c0d62f2e28228cd2d8df4b7
ms.sourcegitcommit: 5716025eb4828425ca237377b02a892de8689f4a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2022
ms.locfileid: "9142816"
---
# <a name="how-to-create-a-new-environment"></a>Procédure pour créer un nouvel environnement

Après avoir [acheté une licence d’abonnement pour Dynamics 365 Customer Insights](paid-license.md), l’administrateur général du locataire Microsoft 365 reçoit un e-mail l’invitant à créer l’environnement. Accédez à [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) pour commencer. Dans ce scénario, vous pouvez accéder directement à l’[Étape 1 : Fournir les informations de base](#step-1-provide-basic-information).

Une fois le premier environnement créé, l’administrateur général du locataire Microsoft 365 peut [ajouter des utilisateurs de son organisation en tant qu’administrateurs](permissions.md). Par la suite, ces administrateurs peuvent gérer les utilisateurs et les environnements. Si votre organisation achète plusieurs licences pour Customer Insights, [contactez notre équipe de support](https://go.microsoft.com/fwlink/?linkid=2079641) pour augmenter le nombre d’environnements disponibles. Pour plus d’informations sur la capacité et la capacité du module complémentaire, consultez le [Guide des licences Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Si vous souhaitez essayer le service, consultez [Mettre en place un environnement d’essai](trial-signup.md).

## <a name="prerequisites"></a>Conditions préalables

Vous avez besoin d’[autorisations administrateur](permissions.md) dans Customer Insights pour créer ou gérer des environnements.

## <a name="start-the-environment-creation-process"></a>Démarrer le processus de création de l’environnement

1. Ouvrez le sélecteur d’environnements et sélectionnez **+ Nouveau**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Sélectionnez le sélectionneur d’environnement.":::

1. Suivez l’expérience guidée décrite dans les sections suivantes pour fournir toutes les informations requises pour un nouvel environnement. Si vous avez configuré un environnement précédemment, vous pouvez également [copier la configuration](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Étape 1 : Fournir les informations de base

À l’étape **Informations de base**, choisissez si vous voulez créer un environnement à partir de zéro ou [copier des données d’un autre environnement](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Boîte de dialogue pour créer un environnement Customer Insights.":::

Indiquez les détails suivants :

- **Nom** : nom de cet environnement. Ce champ est déjà rempli si vous copiez à partir d’un environnement existant, mais vous pouvez le modifier.
- **Choisissez votre entreprise** : Choisissez l’audience principale pour le nouvel environnement. Vous pouvez travailler avec des clients particuliers (B2C) ou des [comptes professionnels](work-with-business-accounts.md) (B2B). Si votre organisation traite principalement avec des individus, comme un détaillant ou un café, choisissez des consommateurs individuels. Si votre audience principale est constituée d’autres entreprises, comme un constructeur automobile ou une papeterie, choisissez des comptes professionnels.
- **Type** : Indiquez si vous souhaitez créer un environnement de Production ou Sandbox. Les environnements sandbox n’autorisent pas l’actualisation planifiée des données et sont destinés à la pré-implémentation et aux tests. Les environnements de bac à sable utilisent la même audience principale que l’environnement de production actuellement sélectionné.
- **Région** : Région dans laquelle le service est déployé et hébergé. Pour [utiliser votre propre compte Azure Data Lake Storage](own-data-lake-storage.md) ou pour [vous connecter à une organisation Microsoft Dataverse existante](customer-insights-dataverse.md), l’environnement Customer Insights doit être dans la même région.

## <a name="step-2-configure-data-storage"></a>Étape 2 : Configurer le stockage des données

À l’étape **Stockage des données**, choisissez où stocker les données Customer Insights.

Vous avez le choix entre deux options :

- **Stockage Customer Insights** : le stockage des données est géré par l’équipe Customer Insights. Il s’agit de l’option par défaut et, à moins qu’il existe des exigences spécifiques pour stocker les données dans votre propre compte de stockage, nous vous recommandons d’utiliser cette option.
- **Azure Data Lake Storage** : spécifiez votre propre compte Azure Data Lake Storage pour stocker les données afin d’avoir un contrôle total sur l’emplacement de stockage des données. Pour plus d’informations, consultez [Utiliser votre propre compte Azure Data Lake Storage](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Choisissez l’option préférée pour stocker vos données.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Étape 3 : Connexion à Microsoft Dataverse

L’étape **Microsoft Dataverse** vous permet de connecter Customer Insights à votre environnement Dataverse. Partagez des données avec Dataverse pour les utiliser avec des applications métier basées sur Dataverse, telles que Dynamics 365 Marketing, ou des applications pilotées par modèle dans Power Apps.

Laissez ce champ vide si vous n’avez pas votre propre environnement Dataverse ; nous en créerons un pour vous.

Pour plus d’informations, consultez [Utiliser les données Customer Insights dans Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Partage de données avec Microsoft Dataverse activé automatiquement pour les nouveaux environnements.":::

### <a name="step-4-finalize-the-settings"></a>Étape 4 : Finaliser les paramètres

À l’étape **Révision**, parcourez tous les paramètres spécifiés. Lorsque tout semble terminé, sélectionnez **Créer** pour mettre en place l’environnement.

Vous pouvez modifier certains des paramètres ultérieurement. Pour plus d’informations, voir [Gérer les environnements](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Travailler avec votre nouvel environnement

Consultez les articles suivants pour commencer la configuration de Customer Insights :

- [Ajoutez plus d’utilisateurs et attribuez des autorisations](permissions.md).
- [Ingérez vos sources de données](data-sources.md) et faites-les passer par le [processus d’unification des données](data-unification.md) pour obtenir des [profils clients unifiés](customer-profiles.md).
- [Enrichissez les profils clients unifiés](enrichment-hub.md) ou [exécutez des modèles prédictifs](predictions-overview.md).
- [Créez des segments](segments.md) pour grouper des clients et des [mesures](measures.md) pour passer en revue les KPI.
- [Configurez les connexions](connections.md) et les [exportations](export-destinations.md) pour traiter des sous-ensembles de vos données dans d’autres applications.

## <a name="copy-the-environment-configuration"></a>Copier la configuration de l’environnement

En tant qu’administrateur, vous pouvez choisir de copier la configuration d’un environnement existant lorsque vous en créez un nouveau.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Capture d’écran des options de paramètres dans les paramètres d’environnement.":::

Vous voyez la liste de tous les environnements disponibles dans votre organisation à partir desquels vous pouvez copier des données.

Les paramètres de configuration suivants sont copiés :

- Sources de données importées via Power Query
- Configuration de l’unification des données
- Segments
- Mesures
- Relations
- Activités
- Index Rechercher et filtrer
- Exportations
- Actualiser le calendrier
- Enrichissements
- Modèles de prédiction
- Attributions de rôles

## <a name="set-up-a-copied-environment"></a>Configurer un environnement copié

Lorsque vous copiez la configuration de l’environnement, vous devez suivre quelques étapes supplémentaires pour confirmer les informations d’identification :

- Profils client. Commencez par authentifier et ingérer vos sources de données, puis exécutez l’unification des données pour recréer les profils clients.
- Informations d’identification d’une source de données. Vous devez fournir les informations d’identification pour chaque source de données pour authentifier et actualiser les sources de données manuellement.
- Sources de données du dossier Common Data Model et de Dataverse. Vous devez créer ces sources de données manuellement avec le même nom que dans l’environnement source.
- Secrets de connexion utilisés pour les exportations et les enrichissements. Vous devez réauthentifier les connexions puis réactiver les enrichissements et les exportations.

Vous verrez un message de confirmation lorsque l’environnement copié sera créé. Sélectionnez **Accéder aux sources de données** pour voir la liste des sources de données.

Toutes les sources de données affichent un statut **Identifiants requis**. Modifiez les sources de données et entrez les informations d’identification pour les actualiser.

:::image type="content" source="media/data-sources-copied.png" alt-text="Liste des sources de données qui ont été copiées et qui nécessitent une authentification.":::

Après avoir actualisé les sources de données, accédez à **Données** > **Unifier**. Vous trouverez ici les paramètres de l’environnement source. Modifiez-les selon vos besoins ou sélectionnez **Exécuter** pour démarrer le processus d’unification des données et créer l’entité client unifiée.

Une fois l’unification des données terminée, accédez à **Mesures** et **Segments** pour les actualiser.

Avant de réactiver les exportations et les enrichissements, accédez à **Administrateur** > **Connexions** pour réauthentifier les connexions dans votre nouvel environnement.

[!INCLUDE [footer-include](includes/footer-banner.md)]
