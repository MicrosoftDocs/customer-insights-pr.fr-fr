---
title: Complément de carte client pour les applications Dynamics 365
description: Affichez les données des informations sur l’audience dans les applications Dynamics 365 avec ce complément.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059585"
---
# <a name="customer-card-add-in-preview"></a>Complément Carte client (préversion)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Obtenez une vue globale de vos clients directement dans les applications Dynamics 365. Avec le complément de carte client installé dans une application Dynamics 365 prise en charge, vous pouvez choisir d’afficher des données démographiques, des informations et des calendriers d’activité. Le complément récupérera les données de Customer Insights sans affecter les données de l’application Dynamics 365 connectée. 

## <a name="prerequisites"></a>Conditions préalables

- Le complément fonctionne uniquement avec les applications pilotées par modèle Dynamics 365, telles que Sales ou Customer Service, versions 9.0 et ultérieures.
- Pour que vos données Dynamics 365 soient mappées aux profils client d’informations sur l’audience, elles doivent être [intégrées à partir de l’application Dynamics 365 à l’aide du connecteur Common Data Service](connect-power-query.md).
- Tous les utilisateurs Dynamics 365 du complément de carte client doivent être [ajoutés en tant qu’utilisateurs](permissions.md) dans les informations sur l’audience pour voir les données.
- [Les fonctions de recherche et de filtrage configurées](search-filter-index.md) dans les informations sur l’audience sont nécessaires pour que la recherche de données fonctionne.
- Chaque contrôle de complément repose sur des données spécifiques dans les informations sur l’audience :
  - Contrôle de mesure : nécessite des [mesures configurées](measures.md).
  - Contrôle de l’intelligence : nécessite des données générées à l’aide de [prédictions](predictions.md) ou de [modèles personnalisés](custom-models.md).
  - Contrôle démographique : les champs démographiques (tels que l’âge ou le sexe) sont disponibles dans le profil client unifié.
  - Contrôle d’enrichissement : nécessite des [enrichissements](enrichment-hub.md) actifs appliqués aux profils clients.
  - Contrôle de chronologie : nécessite des [activités configurées](activities.md).

## <a name="install-the-customer-card-add-in"></a>Installer le complément Fiche client

Le complément de carte client est une solution pour les applications Customer Engagement dans Dynamics 365. Pour installer la solution, accédez à AppSource et recherchez **Carte client Dynamics**. Sélectionnez le [Complément Carte client sur AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) et sélectionnez **Obtenir maintenant**.

Vous devrez peut-être vous connecter avec vos informations d’identification d’administrateur à l’application Dynamics 365 pour installer la solution.

L’installation de la solution dans votre environnement peut prendre un certain temps.

## <a name="configure-the-customer-card-add-in"></a>Configurer le complément Carte client

1. En tant qu’administrateur, accédez à la section **Paramètres** de Dynamics 365 et sélectionnez **Solutions**.

1. Sélectionnez le lien **Nom complet** pour la solution **Complément Carte client Dynamics 365 Customer Insights (préversion)**.

   > [!div class="mx-imgBorder"]
   > ![Sélectionner le nom complet](media/select-display-name.png "Sélectionner le nom complet")

1. Sélectionnez **Se connecter** et entrez les identifiants du compte d’administrateur que vous utilisez pour configurer Customer Insights.

   > [!NOTE]
   > Vérifiez que le bloqueur de fenêtres publicitaires de votre navigateur ne bloque pas la fenêtre d’authentification lorsque vous cliquez sur le bouton **Se connecter**.

1. Sélectionnez l’environnement Customer Insights à partir duquel vous souhaitez extraire des données.

1. Définissez le mappage de champ aux enregistrements dans l’application Dynamics 365. En fonction de vos données dans Customer Insights, vous pouvez choisir de mapper les options suivantes :
   - Pour effectuer un mappage avec un contact, sélectionnez le champ dans l’entité Client correspondant à l’ID de votre entité de contact.
   - Pour effectuer un mappage avec un compte, sélectionnez le champ dans l’entité Client correspondant à l’ID de votre entité de compte.

   > [!div class="mx-imgBorder"]
   > ![Champ ID de contact](media/contact-id-field.png "Champ ID de contact")

1. Sélectionnez **Enregistrer la configuration** pour enregistrer les paramètres.

1. Ensuite, vous devez affecter des rôles de sécurité dans Dynamics 365 afin que les utilisateurs puissent personnaliser et afficher la carte client. Dans Dynamics 365, accédez à **Paramètres** > **Sécurité** > **Utilisateurs**. Sélectionnez les utilisateurs pour modifier les rôles d’utilisateur et sélectionnez **Gérer les rôles**.

1. Attribuez le rôle **Personnalisateur de carte Customer Insights** aux utilisateurs qui personnaliseront le contenu à afficher sur la carte pour l’ensemble de l’organisation.

## <a name="add-customer-card-controls-to-forms"></a>Ajouter des contrôles Carte client aux formulaires
  
1. Pour ajouter les contrôles Carte client à votre formulaire Contact, accédez à **Paramètres** > **Personnalisations** dans Dynamics 365.

1. Sélectionnez **Personnaliser le système**.

1. Accédez à l’entité **Contact**, développez-la, puis sélectionnez **Formulaires**.

1. Sélectionnez le formulaire de contact auquel vous souhaitez ajouter les contrôles Carte client.

    > [!div class="mx-imgBorder"]
    > ![Sélectionner le formulaire Contact](media/contact-active-forms.png "Sélectionner le formulaire Contact")

1. Pour ajouter un contrôle, dans l’éditeur de formulaires, faites glisser un champ de l’**Explorateur de champs** vers l’emplacement où vous souhaitez faire apparaître le contrôle.

1. Sélectionnez le champ sur le formulaire que vous venez d’ajouter, puis sélectionnez **Modifier les propriétés**.

1. Accédez à l’onglet **Contrôles** et sélectionnez **Ajouter un contrôle**. Choisissez l’un des contrôles personnalisés disponibles et sélectionnez **Ajouter**.

1. Dans la boîte de dialogue **Propriétés du champ**, désactivez la case à cocher **Afficher l’étiquette sur le formulaire**.

1. Sélectionnez l’option **Web** pour le contrôle. Pour le contrôle d’enrichissement, sélectionnez le type d’enrichissement que vous souhaitez afficher en configurant le champ **enrichmentType**. Ajoutez un contrôle d’enrichissement distinct pour chaque type d’enrichissement.

1. Sélectionnez **Enregistrer** et **Publier** pour publier le formulaire de contact mis à jour.

1. Accédez au formulaire de contact publié. Le nouveau contrôle ajouté s’affiche. Vous pouvez devoir vous connecter la première fois que vous l’utiliserez.

1. Pour personnaliser ce que vous souhaitez afficher sur le contrôle personnalisé, sélectionnez le bouton Modifier dans le coin supérieur droit.

## <a name="upgrade-customer-card-add-in"></a>Mettre à niveau le complément de carte client
Le complément de carte client ne se met pas à niveau automatiquement. Pour mettre à niveau vers la dernière version, suivez cette procédure dans l’application Dynamics 365 sur laquelle le complément est installé.

1. Dans l’application Dynamics 365, accédez à **Paramètres** > **Personnalisation** et sélectionnez **Solutions**.

1. Dans le tableau des compléments, recherchez **CustomerInsightsCustomerCard** et sélectionnez la ligne.

1. Sélectionnez **Appliquer la mise à niveau de la solution** dans la barre d’action.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Mettez à niveau la solution dans la zone de personnalisation des applications Dynamics 365":::

1. Après le démarrage du processus de mise à niveau, vous verrez un indicateur de chargement jusqu’à la fin de la mise à niveau. S’il n’y a pas de version plus récente, la mise à niveau affichera un message d’erreur.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
