---
title: Créer un nouvel environnement
description: Étapes pour créer des environnements dans Dynamics 365 Customer Insights.
ms.date: 08/15/2022
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
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304240"
---
# <a name="create-a-new-environment"></a>Créer un nouvel environnement

Après avoir [acheté une licence d’abonnement pour Dynamics 365 Customer Insights](paid-license.md), l’administrateur général du locataire Microsoft 365 reçoit un e-mail l’invitant à créer l’environnement. Accédez à [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) pour commencer. Dans ce scénario, commencez par l’[Étape 1 : Fournir les informations de base](#step-1-provide-basic-information).

Une fois le premier environnement créé, l’administrateur général du locataire Microsoft 365 peut [ajouter des utilisateurs de son organisation en tant qu’administrateurs](permissions.md). Ces administrateurs pourront ensuite gérer les utilisateurs et les environnements. Si votre organisation achète plusieurs licences pour Customer Insights, [contactez notre équipe de support](https://go.microsoft.com/fwlink/?linkid=2079641) pour augmenter le nombre d’environnements disponibles. Pour plus d’informations sur la capacité et la capacité du module complémentaire, consultez le [Guide des licences Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). Une fois que vous avez la possibilité de créer des environnements supplémentaires, accédez à [Démarrer le processus de création de l’environnement](#start-the-environment-creation-process).

> [!TIP]
> Si vous souhaitez essayer le service, consultez [Mettre en place un environnement d’essai](trial-signup.md).

## <a name="prerequisites"></a>Conditions préalables

[Autorisations d’administrateur](permissions.md) dans Customer Insights

## <a name="start-the-environment-creation-process"></a>Démarrer le processus de création de l’environnement

1. Ouvrez le sélecteur d’environnements et sélectionnez **+ Nouveau**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Sélectionnez le sélectionneur d’environnement.":::

1. Suivez l’expérience guidée décrite dans les sections suivantes pour fournir toutes les informations requises pour un nouvel environnement.

## <a name="step-1-provide-basic-information"></a>Étape 1 : Fournir les informations de base

1. Choisissez si vous voulez créer un environnement à partir de zéro ou copier des données d’un autre environnement. [Copier des données depuis un autre environnement](#copy-the-environment-configuration) nécessite des étapes supplémentaires.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Boîte de dialogue pour créer un environnement Customer Insights.":::

1. Indiquez les détails suivants :

   - **Nom** : nom de cet environnement. Ce champ est déjà rempli si vous copiez à partir d’un environnement existant, mais vous pouvez le modifier.
   - **Choisissez votre activité** : audience principale pour le nouvel environnement : les clients particuliers (B2C) et les [comptes professionnels](work-with-business-accounts.md) (B2B). Si votre organisation traite principalement avec des individus, comme un détaillant ou un café, choisissez des consommateurs individuels. Si votre audience principale est constituée d’autres entreprises, comme un constructeur automobile ou une papeterie, choisissez des comptes professionnels.
   - **Type** : type d’environnement (production ou Sandbox). Les environnements sandbox n’autorisent pas l’actualisation planifiée des données et sont destinés à la pré-implémentation et aux tests. Les environnements de bac à sable utilisent la même audience principale que l’environnement de production actuellement sélectionné.
   - **Région** : région dans laquelle le service est déployé et hébergé. Pour [utiliser votre propre compte Azure Data Lake Storage](own-data-lake-storage.md) ou pour [vous connecter à une organisation Microsoft Dataverse existante](customer-insights-dataverse.md), l’environnement Customer Insights doit être dans la même région.

1. Cliquez sur **Suivant**.

## <a name="step-2-configure-data-storage"></a>Étape 2 : Configurer le stockage des données

1. Choisissez où stocker les données Customer Insights :

   - **Stockage Customer Insights** : le stockage des données est géré automatiquement. Il s’agit de l’option par défaut et, à moins qu’il existe des exigences spécifiques pour stocker les données dans votre propre compte de stockage, nous vous recommandons d’utiliser cette option.
   - **Azure Data Lake Storage** : votre propre compte Azure Data Lake Storage pour stocker les données afin d’avoir un contrôle total sur l’emplacement de stockage des données. Suivez les étapes indiquées dans [Utiliser votre propre compte Azure Data Lake Storage](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Choisissez l’option préférée pour stocker vos données.":::

1. Cliquez sur **Suivant**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Étape 3 : Connexion à Microsoft Dataverse

Si vous disposez d’un environnement Dataverse, connectez Customer Insights. Partagez des données avec Dataverse pour les utiliser avec des applications métier basées sur Dataverse, telles que Dynamics 365 Marketing, ou des applications pilotées par modèle dans Power Apps.

1. Suivez les étapes indiquées dans [Travailler avec les données Customer Insights dans Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="Partage de données avec Microsoft Dataverse activé automatiquement pour les nouveaux environnements.":::

1. Cliquez sur **Suivant**.

## <a name="step-4-finalize-the-settings"></a>Étape 4 : Finaliser les paramètres

Passer en revue les paramètres spécifiés. Lorsque tout semble terminé, sélectionnez **Créer** pour mettre en place l’environnement.

Pour modifier certains paramètres ultérieurement, consultez [Gérer les environnements](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Travailler avec votre nouvel environnement

Consultez les articles suivants pour commencer la configuration de Customer Insights :

- [Ajoutez plus d’utilisateurs et attribuez des autorisations](permissions.md).
- [Ingérez vos sources de données](data-sources.md) et faites-les passer par le [processus d’unification des données](data-unification.md) pour obtenir des [profils clients unifiés](customer-profiles.md).
- [Enrichissez les profils clients unifiés](enrichment-hub.md) ou [exécutez des modèles prédictifs](predictions-overview.md).
- [Créez des segments](segments.md) pour grouper des clients et des [mesures](measures.md) pour passer en revue les KPI.
- [Configurez les connexions](connections.md) et les [exportations](export-destinations.md) pour traiter des sous-ensembles de vos données dans d’autres applications.

## <a name="copy-the-environment-configuration"></a>Copier la configuration de l’environnement

En tant qu’administrateur, si vous avez choisi de copier la configuration à partir d’un environnement existant, sélectionnez-le dans la liste des environnements disponibles dans votre organisation.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Capture d’écran des options de paramètres dans les paramètres d’environnement.":::

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

### <a name="set-up-a-copied-environment"></a>Configurer un environnement copié

Lorsque vous copiez la configuration d’un environnement, un message de confirmation s’affiche lorsque l’environnement copié a été créé. Pour confirmer les informations d’identification, procédez comme suit.

1. Sélectionnez **Accéder aux sources de données** pour voir la liste des sources de données. Toutes les sources de données affichent un état **Informations d’identification requises**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Liste des sources de données qui ont été copiées et qui nécessitent une authentification.":::

1. Modifiez les sources de données et entrez les informations d’identification pour les actualiser. Les sources de données du dossier Common Data Model et de Dataverse doivent être créées manuellement avec le même nom que dans l’environnement source.

1. Après avoir actualisé les sources de données, accédez à **Données** > **Unifier**. Vous trouverez ici les paramètres de l’environnement source. Modifiez-les selon vos besoins ou sélectionnez **Unifier** > **Unifier les profils clients et les dépendances** pour démarrer le processus d’unification des données et créer l’entité client unifiée.

   > [!TIP]
   > Pour les comptes et les contacts, sélectionnez **Unifier les comptes** > **Unifier les profils et les dépendances**.

1. Une fois l’unification des données terminée, accédez à **Mesures** et **Segments** pour les actualiser.

1. Accédez à **Administrateur** > **Connexions** pour réauthentifier les connexions dans votre nouvel environnement.

1. Accédez à **Données** > **Enrichissement** et **Données** > **Exportations** pour les réactiver.

[!INCLUDE [footer-include](includes/footer-banner.md)]
