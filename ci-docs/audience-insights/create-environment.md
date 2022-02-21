---
title: Créer des environnements dans Customer Insights
description: Étapes pour créer des environnements avec un abonnement sous licence pour Dynamics 365 Customer Insights.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: d29992c88bd54fcfcf5e6429a89a34b6f73148c8
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088099"
---
# <a name="create-an-environment-in-audience-insights"></a>Créer un environnement dans les informations sur l’audience

Cet article explique comment créer un environnement une fois que votre organisation a acheté un abonnement Dynamics 365 Customer Insights. 

Les organisations peuvent créer *deux* environnements pour chaque licence Customer Insights. Si votre organisation achète plusieurs licences, [contactez notre équipe d’assistance](https://go.microsoft.com/fwlink/?linkid=2079641) pour augmenter le nombre d’environnements disponibles. Pour plus d’informations sur la capacité et la capacité d’extension, téléchargez le [Guide des licences Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Si vous souhaitez essayer le service, consultez [Mettre en place un environnement d’essai](../trial-signup.md).

## <a name="create-a-new-environment"></a>Créer un environnement

Après l'achat d'une licence d'abonnement pour Customer Insights, l'administrateur général du locataire Microsoft 365 reçoit un e-mail l'invitant à créer l'environnement. Accédez à [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) pour commencer. 

Une expérience guidée vous aide à travers les étapes pour rassembler toutes les informations requises pour un nouvel environnement. Vous avez besoin [d’autorisations d’administrateur](permissions.md) dans les informations sur l’audience pour créer ou gérer des environnements.

1. Dans les informations sur l’audience, ouvrez le sélecteur d’environnement et sélectionnez **+ Nouveau**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Sélectionnez le sélectionneur d’environnement.":::

1. Suivez l’expérience guidée décrite dans les sections suivantes.

### <a name="step-1-provide-environment-information"></a>Étape 1 : Fournir des informations sur l’environnement

À l’étape **Informations de base**, choisissez si vous voulez créer un environnement à partir de zéro ou [copier des données d’un autre environnement](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Boîte de dialogue pour créer un environnement Customer Insights.":::

Indiquez les détails suivants :
   - **Nom** : nom de cet environnement. Ce champ est déjà rempli si vous copiez à partir d’un environnement existant, mais vous pouvez le modifier.
   - **Choisissez votre entreprise** : Choisissez l'audience principale pour le nouvel environnement. Vous pouvez travailler avec des consommateurs individuels (B2C) ou [comptes d'entreprise](work-with-business-accounts.md) (B2B).
   - **Type** : Indiquez si vous souhaitez créer un environnement de Production ou Sandbox. Les environnements sandbox n’autorisent pas l’actualisation planifiée des données et sont destinés à la pré-implémentation et aux tests. Les environnements de bac à sable utilisent la même audience principale que l’environnement de production actuellement sélectionné.
   - **Région** : Région dans laquelle le service est déployé et hébergé.

### <a name="step-2-configure-data-storage"></a>Étape 2 : Configurer le stockage des données

À l’étape **Stockage des données**, choisissez où stocker les données des informations sur l’audience.

Vous aurez deux options : **Stockage Customer Insights** (un lac de données Azure géré par l’équipe Customer Insights) et **Azure Data Lake Storage** (votre propre Azure Data Lake Storage). Par défaut, l’option de stockage Customer Insights est sélectionnée.

:::image type="content" source="media/data-storage-environment.png" alt-text="Choisir le Azure Data Lake Storage pour stocker vos données d’informations sur l’audience.":::

En enregistrant les données dans Azure Data Lake Storage, vous acceptez que les données soient transférées et stockées à l’emplacement géographique approprié pour ce compte de stockage Azure. Cet emplacement peut différer de l’endroit où les données sont stockées dans Dynamics 365 Customer Insights. En savoir plus sur le [Microsoft Trust Center](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights prend actuellement en charge les éléments suivants :
> - Entités ingérées à partir des flux de données Power BI stockés dans un Data Lake géré par Microsoft Dataverse.  
> - Les comptes Azure Data Lake Storage de la même région Azure que vous avez sélectionnée lors de la création de l’environnement.
> - Comptes Azure Data Lake Storage Gen2 dont l'*espace de noms hiérarchique* est activé. Les comptes de stockage Azure Data Lake Gen1 ne sont pas pris en charge.

Pour l’option Azure Data Lake Storage, vous pouvez choisir entre une option basée sur une ressources et une option basée sur un abonnement pour l’authentification. Pour plus d'informations, consultez [Connectez-vous à un compte Azure Data Lake Storage en utilisant un principal de service Azure](connect-service-principal.md). Le nom du **Conteneur** sera `customerinsights` et il ne peut pas être modifié.

Lorsque les processus système tels que l’ingestion de données sont terminés, le système crée les dossiers correspondants dans le compte de stockage que vous avez spécifié. Les fichiers de données et les fichiers *model.json* sont créés et ajoutés aux dossiers en fonction du nom du processus.

Si vous créez plusieurs environnements de Customer Insights et choisissez d’enregistrer les entités de sortie de ces environnements sur votre compte de stockage, Customer Insights crée des dossiers séparés pour chaque environnement avec `ci_environmentID` dans le conteneur.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Étape 3 : Connexion à Microsoft Dataverse
   
L’étape **Microsoft Dataverse** vous permet de connecter Customer Insights à votre environnement Dataverse.

Pour utiliser [des modèles de prédiction prêts à l’emploi](predictions-overview.md#out-of-box-models), configurez le partage de données avec Dataverse. Vous pouvez également activer l’ingestion de données à partir des sources de données local, en fournissant l’URL d’environnement Microsoft Dataverse administrée par votre organisation. Sélectionnez **Activer le partage de données** pour partager les données de sortie Customer Insights avec un lac de données géré par Dataverse.

> [!IMPORTANT]
> Customer Insights et Dataverse doivent se trouver dans la même région pour activer le partage de données.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Options de configuration pour activer le partage de données avec Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights ne prend pas en charge les scénarios de partage de données suivants :
> - Si vous enregistrez toutes les données dans votre Azure Data Lake Storage, vous ne pourrez pas activer le partage de données avec un lac de données géré par Dataverse.
> - Si vous activez le partage de données avec Dataverse, vous ne pourrez pas [créer des valeurs prédites ou manquantes dans une entité](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Étape 4 : Finaliser les paramètres

À l’étape **Revoir**, parcourez tous les paramètres spécifiés. Lorsque tout semble terminé, sélectionnez **Créer** pour mettre en place l’environnement. 

Vous pouvez également modifier la plupart des paramètres ultérieurement. Pour plus d’informations, voir [Gérer les environnements](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Travailler avec votre nouvel environnement

Consultez les articles suivants pour commencer la configuration de Customer Insights : 

- [Ajoutez plus d’utilisateurs et attribuez des autorisations](permissions.md).
- [Ingérez vos sources de données](data-sources.md) et faites-les passer par le [processus d’unification des données](data-unification.md) pour obtenir des [profils clients unifiés](customer-profiles.md).
- [Enrichissez les profils clients unifiés](enrichment-hub.md) ou [exécutez des modèles prédictifs](predictions-overview.md).
- [Créez des segments](segments.md) pour grouper des clients et des [mesures](measures.md) pour passer en revue les KPI.
- [Configurez les connexions](connections.md) et les [exportations](export-destinations.md) pour traiter des sous-ensembles de vos données dans d’autres applications.
