---
title: Créer et configurer une licence payante de Customer Insights
description: Étapes pour obtenir un abonnement sous licence pour Dynamics 365 Customer Insights et le configurer.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034449"
---
# <a name="get-started-with-a-paid-subscription"></a>Mise en route de votre abonnement payant

Cet article explique comment créer un environnement une fois que votre organisation a acheté un abonnement Dynamics 365 Customer Insights. Si vous souhaitez acheter Customer Insights, nos options de contact sont répertoriées sur le [site Web Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/). 

Si vous souhaitez essayer le service et les fonctionnalités, consultez [Configurer un environnement de version d’essai](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Créer un environnement dans une organisation existante

Après avoir acheté une licence d’abonnement pour Customer Insights, l’administrateur global du client Microsoft 365 reçoit un e-mail l’invitant à créer l’environnement. Accédez à [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) pour commencer. 

Customer Insights n’étant pas concédé sous licence par utilisateur, il ne s’affiche pas dans la zone Licences. Si vous recherchez la licence dans le Centre d’administration Microsoft 365, accédez à **Vos produits**. 

> [!NOTE]
> Les organisations peuvent créer *deux* environnements pour chaque licence Customer Insights. Si votre organisation achète plus d’une licence, [contactez notre équipe de support](https://go.microsoft.com/fwlink/?linkid=2079641) pour augmenter le nombre d’environnements disponibles. Pour plus d’informations sur la capacité et la capacité d’extension, téléchargez le [Guide des licences Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Pour créer un environnement :

1. Dans la boîte de dialogue **Créer un environnement**, sélectionnez **Nouvel environnement**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Boîte de dialogue pour créer un environnement Customer Insights.":::

   Nous vous recommandons de commencer à configurer un environnement à partir de zéro. Cependant, si vous êtes administrateur ou membre d’un environnement de version dֹ’essai, vous pouvez [copier les données depuis un autre environnement](manage-environments.md#copy-the-environment-configuration), en sélectionnant **Copier à partir de l’environnement existant**. Vous voyez la liste de tous les environnements disponibles dans votre organisation à partir desquels vous pouvez copier des données.

1. Indiquez les détails suivants :
   - **Nom** : nom de cet environnement. Ce champ est déjà rempli si vous copiez à partir d’un environnement existant, mais vous pouvez le modifier.
   - **Région** : Région dans laquelle le service est déployé et hébergé.
   - **Type** : Indiquez si vous souhaitez créer un environnement de Production ou Sandbox. Les environnements sandbox n’autorisent pas l’actualisation planifiée des données et sont destinés à la pré-implémentation et aux tests.
   
1. Vous pouvez éventuellement sélectionner **Paramètres avancés** :

   - **Enregistrer toutes les données dans** : Spécifie où vous souhaitez stocker les données de sortie générées à partir de Customer Insights. Vous aurez deux options : **Stockage Customer Insights** (un Azure Data Lake géré par l’équipe Customer Insights) et **Azure Data Lake Storage** (votre propre Azure Data Lake Storage). Par défaut, l’option de stockage Customer Insights est sélectionnée.

     > [!NOTE]
     > En enregistrant des données dans Azure Data Lake Storage, vous acceptez que les données soient transférées et stockées dans l’emplacement géographique approprié pour ce compte de stockage Azure, ce qui peut différer de l’emplacement de stockage des données dans Dynamics 365 Customer Insights. [En savoir plus sur le Microsoft Trust Center.](https://www.microsoft.com/trust-center)
     >
     > Actuellement, les entités ingérées depuis les flux de données Power BI sont stockées dans le Data Lake géré par Microsoft Dataverse. 
     > 
     > Nous ne prenons en charge que les comptes Azure Data Lake Storage de la même région Azure que celle sélectionnée lors de la création de l’environnement. 
     > 
     > Nous ne prenons en charge que les comptes Azure Data Lake Storage pour lesquels l’espace de noms hiérarchique est activé.


   - Pour l’option Azure Data Lake Storage, vous pouvez choisir entre une option basée sur une ressources et une option basée sur un abonnement pour l’authentification. Pour plus d’informations, consultez [Connecter les informations sur l’audience à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure](connect-service-principal.md). Le nom du **Conteneur** ne peut pas être modifié et sera `customerinsights`.
   
   - Si vous voulez utiliser les [modèles prêts à l’emploi](predictions-overview.md#out-of-box-models), configurez le partage de données avec Microsoft Dataverse, ou activez l’ingestion des données à partir des sources de données locales, renseignez l’URL de l’environnement Microsoft Dataverse sous **Configurer le partage de données avec Microsoft Dataverse et activer des capacités supplémentaires**. Sélectionnez **Activer le partage de données** pour partager les données de sortie Customer Insights avec un lac de données géré Microsoft Dataverse.

     > [!NOTE]
     > - Le partage de données avec un Data Lake géré par Microsoft Dataverse n’est actuellement pas pris en charge lorsque vous enregistrez toutes les données dans votre propre Azure Data Lake Storage.
     > - La [prédiction des valeurs manquantes dans une entité](predictions.md) n’est actuellement pas prise en charge lorsque vous activez le partage de données avec un Data Lake géré par Microsoft Dataverse.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Options de configuration pour activer le partage de données avec Microsoft Dataverse.":::

   Lorsque les processus système tels que l’ingestion des données sont terminés, le système crée les dossiers correspondants dans le compte de stockage que vous avez spécifié. Les fichiers de données et les fichiers model.json sont créés et ajoutés aux dossiers en fonction du nom du processus.

   Si vous créez plusieurs environnements de Customer Insights et choisissez d’enregistrer les entités de sortie de ces environnements dans votre compte de stockage, des dossiers distincts seront créés pour chaque environnement avec ci_<environmentid> dans le conteneur.

1. Sélectionnez **Créer** pour configurer l’environnement. 

## <a name="configure-an-environment"></a>Configurer un environnement

Consultez les articles suivants pour vous aider à démarrer avec la configuration de Customer Insights. 

- [Ajoutez plus d’utilisateurs et attribuez des autorisations](permissions.md).
- [Ingérez vos sources de données](data-sources.md) et faites-les passer par le [processus d’unification des données](data-unification.md) pour obtenir des [profils clients unifiés](customer-profiles.md).
- [Enrichissez les profils clients unifiés](enrichment-hub.md) ou [exécutez des modèles prédictifs](predictions-overview.md).
- Créez des [segments](segments.md) pour grouper les clients et des [mesures](measures.md) pour passer en revue les KPI.
- Configurez les [connexions](connections.md) et les [exportations](export-destinations.md) pour traiter des sous-ensembles de vos données dans d’autres applications.
