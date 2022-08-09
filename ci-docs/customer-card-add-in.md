---
title: Complément de carte client pour les applications Dynamics 365 (version préliminaire) (contient une vidéo)
description: Affichez les données de profil client de Customer Insights dans les applications Dynamics 365 avec ce complément.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 8b3b6a0d54b80d7df454e9dc925f14cc3c39684c
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9194920"
---
# <a name="customer-card-add-in-for-dynamics-365-apps-preview"></a>Complément de carte client pour les applications Dynamics 365 (version préliminaire)

Obtenez une vue globale de vos clients directement dans les applications Dynamics 365. Avec le complément Customer Card installé dans une application Dynamics 365 prise en charge, vous pouvez choisir d’afficher les champs de profil client, les informations et la chronologie des activités. Le complément récupérera les données de Customer Insights sans affecter les données de l’application Dynamics 365 connectée.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Conditions préalables

- Applications pilotées par modèle Dynamics 365, telles que Sales ou Customer Service, versions 9.0 et ultérieures.
- Pour que vos données Dynamics 365 soient mappées aux profils client Customer Insights, nous vous recommandons de les [ingérer à partir de l’application Dynamics 365 avec le connecteur Microsoft Dataverse](connect-power-query.md). Si vous utilisez une méthode différente pour ingérer des contacts (ou des comptes) Dynamics 365, vous devez vous assurer que le champ `contactid` (ou `accountid`) est défini comme la [clé primaire pour cette source de données pendant le processus d’unification des données](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Tous les utilisateurs Dynamics 365 du complément de carte client doivent être [ajoutés en tant qu’utilisateurs](permissions.md) dans Customer Insights pour voir les données.
- [Fonctions de recherche et de filtrage configurées](search-filter-index.md) dans Customer Insights.
- Chaque contrôle de complément s’appuie sur des données spécifiques dans Customer Insights. Certaines données et certains contrôles ne sont disponibles que dans des environnements de types spécifiques. La configuration du complément vous informera si un contrôle n’est pas disponible en raison du type d’environnement sélectionné. En savoir plus sur les [cas d’utilisation de l’environnement](work-with-business-accounts.md).
  - **Contrôle de mesure** : a besoin [de mesures configurées](measures.md).
  - **Contrôle de l’intelligence** : nécessite des données générées à l’aide de [prédictions ou de modèles personnalisés](predictions-overview.md).
  - **Contrôle des détails du client** : affiche tous les champs du profil disponibles dans le profil client unifié.
  - **Contrôle d’enrichissement** : nécessite des [enrichissements](enrichment-hub.md) actifs appliqués aux profils clients. Le complément de carte prend en charge ces enrichissements : [Marques](enrichment-microsoft.md) fournies par Microsoft, [Intérêts](enrichment-microsoft.md) fournis par Microsoft et [Données d’engagement Office](enrichment-office.md) fournies par Microsoft.
  - **Contrôle des contacts** : nécessite la définition d’un type d’entité sémantique de contact.
  - **Contrôle de chronologie** : nécessite des [activités configurées](activities.md).

## <a name="install-the-customer-card-add-in"></a>Installer le complément Fiche client

Le complément de carte client est une solution pour les applications Customer Engagement dans Dynamics 365. Pour installer la solution :

1. Accédez à AppSource et recherchez **Carte client Dynamics**.

1. Sélectionnez le [Complément Carte client sur AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) et sélectionnez **Obtenir maintenant**.

Vous devrez peut-être vous connecter avec vos informations d’identification d’administrateur à l’application Dynamics 365 pour installer la solution. L’installation de la solution dans votre environnement peut prendre un certain temps.

## <a name="configure-the-customer-card-add-in"></a>Configurer le complément Carte client

1. En tant qu’administrateur, accédez à la section **Paramètres** de Dynamics 365 et sélectionnez **Solutions**.

1. Sélectionnez le lien **Nom d’affichage** pour la solution **Complément Carte client Dynamics 365 Customer Insights (version préliminaire)**.

   > [!div class="mx-imgBorder"]
   > ![Sélectionnez le nom d’affichage.](media/select-display-name.png "Sélectionnez le nom d’affichage.")

1. Sélectionnez **Se connecter** et entrez les identifiants du compte d’administrateur que vous utilisez pour configurer Customer Insights.

   > [!NOTE]
   > Vérifiez que le bloqueur de fenêtres publicitaires de votre navigateur ne bloque pas la fenêtre d’authentification lorsque vous cliquez sur le bouton **Se connecter**.

1. Sélectionnez l’environnement Customer Insights à partir duquel vous souhaitez extraire des données.

1. Définissez le mappage de champ aux enregistrements dans l’application Dynamics 365. En fonction de vos données dans Customer Insights, vous pouvez choisir de mapper les options suivantes :
   - Pour effectuer un mappage avec un contact, sélectionnez le champ dans l’entité Client correspondant à l’ID de votre entité de contact.
   - Pour effectuer un mappage avec un compte, sélectionnez le champ dans l’entité Client correspondant à l’ID de votre entité de compte.

   > [!div class="mx-imgBorder"]
   > ![Champ ID de contact.](media/contact-id-field.png "Champ ID de contact.")

1. Sélectionnez **Enregistrer la configuration** pour enregistrer les paramètres.

1. Ensuite, vous devez affecter des rôles de sécurité dans Dynamics 365 afin que les utilisateurs puissent personnaliser et afficher la carte client. Dans Dynamics 365, accédez à **Paramètres** > **Sécurité** > **Utilisateurs**. Sélectionnez les utilisateurs pour modifier les rôles d’utilisateur et sélectionnez **Gérer les rôles**.

1. Attribuez le rôle **Personnalisateur de carte Customer Insights** aux utilisateurs qui personnaliseront le contenu à afficher sur la carte pour l’ensemble de l’organisation.

## <a name="add-customer-card-controls-to-forms"></a>Ajouter des contrôles Carte client aux formulaires

Selon votre scénario, vous pouvez choisir d’ajouter des contrôles soit au formulaire **Contact** ou au formulaire **Compte**. Si votre environnement Customer Insights est destiné aux comptes professionnels, nous vous recommandons d’ajouter les contrôles au formulaire Compte. Dans ce cas, remplacez « contact » dans les étapes ci-dessous par « compte ».

1. Pour ajouter les contrôles Carte client à votre formulaire Contact, accédez à **Paramètres** > **Personnalisations** dans Dynamics 365.

1. Sélectionnez **Personnaliser le système**.

1. Accédez à l’entité **Contact**, développez-la, puis sélectionnez **Formulaires**.

1. Sélectionnez le formulaire de contact auquel vous souhaitez ajouter les contrôles de carte client.

    > [!div class="mx-imgBorder"]
    > ![Sélectionnez le formulaire Contact.](media/contact-active-forms.png "Sélectionnez le formulaire Contact.")

1. Pour ajouter un contrôle, dans l’éditeur de formulaires, faites glisser un champ de l’**Explorateur de champs** vers l’emplacement où vous souhaitez faire apparaître le contrôle.

1. Sélectionnez le champ sur le formulaire que vous venez d’ajouter, puis sélectionnez **Modifier les propriétés**.

1. Accédez à l’onglet **Contrôles** et sélectionnez **Ajouter un contrôle**. Choisissez l’un des contrôles personnalisés disponibles et sélectionnez **Ajouter**.

1. Dans la boîte de dialogue **Propriétés du champ**, désactivez la case à cocher **Afficher l’étiquette sur le formulaire**.

1. Sélectionnez l’option **Web** pour le contrôle. Pour le contrôle d’enrichissement, sélectionnez le type d’enrichissement que vous souhaitez afficher en configurant le champ **enrichmentType**. Ajoutez un contrôle d’enrichissement distinct pour chaque type d’enrichissement.

1. Sélectionnez **Enregistrer** et **Publier** pour publier le formulaire de contact mis à jour.

1. Accédez au formulaire de contact publié. Le nouveau contrôle ajouté s’affiche. Vous pouvez devoir vous connecter la première fois que vous l’utiliserez.

1. Pour personnaliser ce que vous souhaitez afficher sur le contrôle personnalisé, sélectionnez le bouton Modifier dans le coin supérieur droit.

## <a name="upgrade-customer-card-add-in"></a>Mettre à niveau le complément de carte client

Le complément de carte client ne se met pas à niveau automatiquement. Pour effectuer une mise à niveau vers la dernière version, suivez ces étapes dans l’application Dynamics 365 sur laquelle le complément est installé.

1. Dans l’application Dynamics 365, accédez à **Paramètres** > **Personnalisation** et sélectionnez **Solutions**.

1. Dans le tableau des compléments, recherchez **CustomerInsightsCustomerCard** et sélectionnez la ligne.

1. Sélectionnez **Appliquer la mise à niveau de la solution** dans la barre d’action.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Mettez à niveau la solution dans la zone de personnalisation des applications Dynamics 365.":::

1. Après le démarrage du processus de mise à niveau, vous verrez un indicateur de chargement jusqu’à la fin de la mise à niveau. S’il n’y a pas de version plus récente, la mise à niveau affichera un message d’erreur.

## <a name="troubleshooting"></a>Dépannage

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Les contrôles du complément de carte client ne trouvent pas de données

**Problème :**

Même avec des champs d’ID correctement configurés, les contrôles ne peuvent trouver de données pour aucun client.  

**Solution :**

1. Assurez-vous d’avoir configuré le complément de carte conformément aux instructions : [Configurer le complément de carte client](#configure-the-customer-card-add-in)

1. Vérifiez la configuration de l’ingestion de données. Modifiez la source de données pour le système Dynamics 365 qui contient le GUID d’ID de contact. Si le GUID de l’ID de contact s’affiche avec des caractères majuscules dans l’éditeur Power Query, procédez comme suit :
    1. Modifiez la source de données pour ouvrir la source de données dans l’éditeur Power Query.
    1. Sélectionnez la colonne ID de contact.
    1. Sélectionnez **Transformer** dans la barre d’en-tête pour voir les actions disponibles.
    1. Sélectionnez **minuscule**. Vérifiez si les GUID du tableau sont désormais en minuscules.
    1. Enregistrez la source de données.
    1. Exécutez l’ingestion de données, l’unification et les processus en aval pour propager les modifications au GUID.

Une fois l’actualisation complètement terminée, les contrôles du complément de carte client doivent afficher les données attendues.

[!INCLUDE [footer-include](includes/footer-banner.md)]
