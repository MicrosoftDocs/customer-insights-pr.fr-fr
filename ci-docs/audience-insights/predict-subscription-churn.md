---
title: Prédiction de la résiliation d’abonnement
description: Déterminez si un client risque de ne plus utiliser les produits ou services d’abonnement de votre société.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 4e7065b61940ef0d7b2a30f96f6225df29e30383
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095645"
---
# <a name="subscription-churn-prediction-preview"></a>Prédiction du taux de désabonnement (aperçu)

La prédiction du taux de désabonnement permet de déterminer si un client risque de ne plus utiliser les produits ou services d’abonnement de votre société. Vous pouvez créer une nouvelle prédiction du taux de désabonnement sur la page **Intelligence** > **Prédictions**. Sélectionnez **Mes prédictions** pour voir les autres prédictions que vous avez créées.

> [!TIP]
> Essayez le didacticiel de prédiction de l’attrition des abonnements en utilisant des exemples de données : [Exemple de guide de prédiction de l’attrition des abonnements](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Conditions préalables

- Au moins des [autorisations contributeur](permissions.md).
- Connaissance des affaires pour comprendre ce que le désabonnement signifie pour votre entreprise. Nous prenons en charge les définitions de désabonnement basées sur le temps, ce qui signifie qu’un client est considéré comme ayant perdu un certain temps après la fin de son abonnement.
- Données sur vos abonnements et leur historique :
    - Identifiants d’abonnement pour distinguer les abonnements.
    - Identifiants client pour faire correspondre les abonnements à vos clients.
    - Dates des événements d’abonnement, qui définissent les dates de début, de fin et les dates auxquelles les événements d’abonnement se sont produits.
    - Informations sur l’abonnement pour définir s’il s’agit d’un abonnement récurrent et à quelle fréquence il se renouvelle.
    - Le schéma de données sémantique pour les abonnements nécessite les informations suivantes :
        - **ID d’abonnement :** Identifiant unique d’un abonnement.
        - **Date de fin d’abonnement :** Date d’expiration de l’abonnement pour le client.
        - **Date de début d’abonnement :** Date de début de l’abonnement pour le client.
        - **Date de la transaction :** Date à laquelle un changement d’abonnement s’est produit. Par exemple, un client achetant ou annulant un abonnement.
        - **S’agit-il d’un abonnement récurrent :** Champ booléen vrai/faux qui détermine si l’abonnement sera renouvelé avec le même ID d’abonnement sans intervention du client
        - **Fréquence de périodicité de cumul (en heures) :** Pour les abonnements récurrents, il s’agit de la période pendant laquelle l’abonnement sera renouvelé. Elle est représentée en mois. Par exemple, un abonnement annuel qui se renouvelle automatiquement pour un client chaque année pour une autre année a la valeur 12.
        - (Facultatif) **Montant de l’abonnement :** Montant de devise qu’un client paie pour le renouvellement de son abonnement. Il peut aider à identifier les modèles pour différents niveaux d’abonnement.
- Données sur les activités des clients :
    - Identificateurs d’activité pour distinguer les activités du même type.
    - Identifiants client pour faire correspondre les activités à vos clients.
    - Informations sur l’activité contenant le nom et la date de l’activité.
    - Le schéma de données sémantique pour les activités client comprend :
        - **Clé primaire :** Identifiant unique pour une activité. Par exemple, une visite d’un site Web ou un enregistrement d’utilisation montrant que le client a regardé un épisode d’une émission de télévision.
        - **Horodatage :** Date et heure de l’événement identifiées par la clé primaire.
        - **Événement :** Nom de l’événement que vous souhaitez utiliser. Par exemple, un champ appelé « UserAction » dans un service de vidéo en streaming peut avoir la valeur « Affiché ».
        - **Détails :** Informations détaillées sur l’événement. Par exemple, un champ appelé « ShowTitle » dans un service de vidéo en streaming peut avoir la valeur d’une vidéo regardée par un client.
- Caractéristiques des données suggérées :
    - Données historiques suffisantes : données d’abonnement pour au moins le double de la période de temps sélectionnée. De préférence, deux à trois ans de données d’abonnement.
    - Statut de l’abonnement : les données comprennent les abonnements actifs et inactifs pour chaque client ; il y a donc plusieurs entrées par ID de client.
    - Nombre de clients : au moins 10 profils client, de préférence plus de 1 000 clients uniques. Le modèle échouera s’il y a moins de 10 clients et des données historiques insuffisantes.
    - Intégrité des données : moins de 20 % des valeurs manquantes dans le champ de données de l’entité fournie.
   
   > [!NOTE]
   > Vous aurez besoin d’au moins deux enregistrements d’activité pour 50 % des clients pour lesquels vous souhaitez calculer le taux d’attrition.

## <a name="create-a-subscription-churn-prediction"></a>Créer une prédiction du taux de désabonnement

1. Dans les informations sur l’audience, accédez à **Intelligence** > **Prédictions**.
1. Sélectionnez la vignette **Modèle de taux de désabonnement (aperçu)** et sélectionnez **Utiliser ce modèle**.
   > [!div class="mx-imgBorder"]
   > ![Vignette modèle de taux de désabonnement avec le bouton Utiliser ce modèle](media/subscription-churn-usethismodel.PNG "Vignette modèle de taux de désabonnement avec le bouton Utiliser ce modèle")

### <a name="name-model"></a>Nommer le modèle

1. Donnez un nom au modèle pour le distinguer des autres modèles.
1. Donnez un nom à l’entité en sortie en utilisant uniquement des lettres et des chiffres, sans espaces. Il s’agit du nom que l’entité modèle utilisera. Ensuite, cliquez sur **Suivant**.

### <a name="define-customer-churn"></a>Définir l’attrition client

1. Entrez le nombre de **Jours depuis la fin de l’abonnement** qu’un client est parti selon votre entreprise. Cette période est généralement significative pour les activités commerciales, telles que les offres ou autres efforts de marketing visant à éviter de perdre le client.
1. Entrez le nombre de **Jours à rechercher dans le futur pour prédire le taux d’attrition** pour définir une fenêtre pour laquelle prédire le taux d’attrition. Par exemple, pour prédire le risque d’attrition de vos clients au cours des 90 prochains jours afin de vous aligner sur vos efforts de rétention marketing. Prédire le risque d’attrition sur des périodes plus ou moins longues peut rendre plus difficile de prendre en compte les facteurs de votre profil de risque d’attrition, en fonction des exigences spécifiques de votre entreprise. Sélectionner **Suivant** pour continuer
   >[!TIP]
   > Vous pouvez sélectionner **Enregistrer et fermer** à tout moment pour enregistrer la prédiction en tant que brouillon. Vous trouverez le projet de prédiction dans l’onglet **Mes prédictions** pour continuer.

### <a name="add-required-data"></a>Ajouter les données requises

1. Sélectionnez **Ajouter des données** pour **Historique d’abonnement** et choisissez l’entité qui fournit les informations d’historique d’abonnement comme décrit dans les [conditions préalables](#prerequisites).
1. Si les champs ci-dessous ne sont pas remplis, configurez la relation entre votre entité d’historique d’abonnement et l’entité client.
    1. Sélectionnez l’**Entité d’historique d’abonnement**.
    1. Sélectionnez le **Champ** qui identifie le client dans l’entité d’historique d’abonnement. Il doit être lié à l’ID client principal de votre entité client.
    1. Sélectionnez l’**Entité client** qui correspond à votre entité client principale.
    1. Entrez un nom qui décrit la relation.
       > [!div class="mx-imgBorder"]
       > ![Page d’historique d’abonnement montrant la création d’une relation client](media/subscription-churn-subscriptionhistoryrelationship.PNG "Page d’historique d’abonnement montrant la création d’une relation client")
1. Cliquez sur **Suivant**.
1. Mappez les champs sémantiques aux attributs de votre entité d’historique d’abonnement et sélectionnez **Enregistrer**. Pour une obtenir une description des champs, consultez les [conditions préalables](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Page d’historique d’abonnement affichant les attributs sémantiques mappés aux champs de l’entité d’historique d’abonnement sélectionnée](media/subscription-churn-subscriptionhistorymapping.PNG "Page d’historique d’abonnement affichant les attributs sémantiques mappés aux champs de l’entité d’historique d’abonnement sélectionnée")
1. Sélectionnez **Ajouter des données** pour **Activités du client** et choisissez l’entité qui fournit les informations sur les activités du client comme décrit dans les conditions préalables.
1. Sélectionnez un type d’activité correspondant au type d’activité du client que vous configurez.  Sélectionnez **Créer** et donnez un nom si vous ne voyez pas une option qui correspond au type d’activité dont vous avez besoin.
1. Vous devrez configurer la relation entre votre entité d’activité client et l’entité Client.
    1. Sélectionnez le champ qui identifie le client dans la table d’activité client, qui peut être directement lié à l’ID client principal de votre entité Client.
    1. Sélectionnez l’Entité client qui correspond à votre entité Client principale.
    1. Entrez un nom qui décrit la relation.
1. Cliquez sur **Suivant**.
1. Mappez les champs sémantiques aux attributs au sein de votre entité d’activité client et sélectionnez **Enregistrer**. Pour une obtenir une description des champs, consultez les [conditions préalables](#prerequisites).
1. (Facultatif) Si vous souhaitez inclure d’autres activités client, répétez les étapes ci-dessus.
   > [!div class="mx-imgBorder"]
   > ![Définir la relation entre les entités](media/subscription-churn-customeractivitiesmapping.PNG "Page d’activités du client affichant les attributs sémantiques mappés aux champs de l’entité d’activité du client sélectionnée")
1. Cliquez sur **Suivant**.

### <a name="set-schedule-and-review-configuration"></a>Définir le calendrier et revoir la configuration

1. Définissez une fréquence pour renouveler l’entraînement de votre modèle. Ce paramètre est important pour mettre à jour la précision des prédictions lorsque de nouvelles données sont ingérées dans les informations sur l’audience. La plupart des entreprises peuvent se réentraîner une fois par mois et obtenir une bonne précision pour leur prédiction.
1. Cliquez sur **Suivant**.
1. Vérifiez la configuration. Vous pouvez revenir à n’importe quelle partie de la configuration de prédiction en sélectionnant **Modifier** sous la valeur indiquée. Ou vous pouvez sélectionner une étape de configuration dans l’indicateur de progression.
1. Si toutes les valeurs sont configurées correctement, sélectionnez **Enregistrer et exécuter** pour commencer le processus de prédiction. Sur l’onglet **Mes prédictions**, vous pouvez voir l’état de vos prévisions. Le processus peut prendre plusieurs heures pour se terminer selon la quantité de données utilisées dans la prédiction.

## <a name="review-a-prediction-status-and-results"></a>Examiner l’état et les résultats de la prédiction

1. Accédez à l’onglet **Mes prédictions** sur **Intelligence** > **Prédictions**.
   > [!div class="mx-imgBorder"]
   > ![Affichage de la page Mes prédictions](media/subscription-churn-mypredictions.PNG "Affichage de la page Mes prédictions")
1. Sélectionnez la prédiction à réviser.
   - **Nom de la prédiction :** Nom de la prédiction fourni lors de sa création.
   - **Type de prédiction :** Type de modèle utilisé pour la prédiction
   - **Entité de sortie :** Nom de l’entité pour stocker la sortie de la prédiction. Vous pouvez trouver une entité portant ce nom sur **Données** > **Entités**.    
     Dans l’entité de sortie, *ChurnScore* est la probabilité prédite d’attrition et *IsChurn* est une étiquette binaire basée sur *ChurnScore* avec un seuil de 0,5. Le seuil par défaut peut ne pas fonctionner pour votre scénario. [Créez un nouveau segment](segments.md#create-a-new-segment) avec votre seuil préféré.
   - **Champ prévu :** Ce champ est renseigné uniquement pour certains types de prédictions et n’est pas utilisé dans la prédiction du taux de désabonnement.
   - **Statut :** Statut actuel de l’exécution de la prédiction.
        - **Mis en file d’attente :** La prédiction attend actuellement l’exécution d’autres processus.
        - **Actualisation :** La prédiction exécute actuellement l’étape de « notation » du traitement pour produire des résultats qui iront dans l’entité de sortie.
        - **Échec :** La prédiction a échoué. Sélectionnez **Journaux** pour obtenir plus de détails.
        - **Réussite :** La prédiction a réussi. Sélectionnez **Afficher** sous les ellipses verticales pour revoir la prédiction
   - **Modifié :** Date de modification de la configuration de la prédiction.
   - **Dernière actualisation :** Date d’actualisation de la prédiction dans l’entité en sortie.
1. Sélectionnez les ellipses verticales à côté de la prédiction pour laquelle vous souhaitez consulter les résultats et sélectionnez **Afficher**.
   > [!div class="mx-imgBorder"]
   > ![Affichage des options dans le menu ellipses verticales pour une prédiction, y compris modifier, actualiser, afficher, journaux et supprimer](media/subscription-churn-verticalellipses.PNG "Affichage des options dans le menu ellipses verticales pour une prédiction, y compris modifier, actualiser, afficher, journaux et supprimer")
1. La page de résultats comporte trois sections principales de données :
    1. **Performance du modèle de formation :** A, B ou C sont des scores possibles. Ce score indique les performances de la prédiction et peut vous aider à prendre la décision d’utiliser les résultats stockés dans l’entité de sortie.
        - Les scores sont déterminés en fonction des règles suivantes :
            - **A** lorsque le modèle a prédit avec précision au moins 50 % du total des prévisions et lorsque le pourcentage de prévisions précises pour les clients qui n’ont pas renouvelé leur abonnement est supérieur au taux de désabonnement moyen historique d’au moins 10 % du taux de désabonnement moyen historique.
            - **B** lorsque le modèle a prédit avec précision au moins 50 % du total des prévisions et lorsque le pourcentage de prévisions précises pour les clients qui n’ont pas renouvelé leur contrat est supérieur au taux de désabonnement moyen historique jusqu’à 10 % du taux de désabonnement moyen historique.
            - **C** lorsque le modèle a prédit avec précision moins de 50 % du total des prévisions, ou lorsque le pourcentage de prévisions précises pour les clients qui se sont désabonnés est inférieur au taux de désabonnement moyen historique.
               > [!div class="mx-imgBorder"]
               > ![Vue du résultat des performances du modèle](media/subscription-churn-modelperformance.PNG "Vue du résultat des performances du modèle")
    1. **Probabilité de désabonnement (nombre de clients) :** Groupes de clients en fonction du risque de désabonnement prévu. Ces données peuvent vous aider ultérieurement si vous souhaitez créer un segment de clients à haut risque de désabonnement. Ces segments aident à comprendre où doit se situer votre limite pour l’appartenance à un segment.
       > [!div class="mx-imgBorder"]
       > ![Graphique montrant la distribution des résultats de désabonnement, divisés en plages de 0 à 100 %](media/subscription-churn-resultdistribution.PNG "Graphique montrant la distribution des résultats de désabonnement, divisés en plages de 0 à 100 %")
    1. **Facteurs les plus influents :** De nombreux facteurs sont pris en compte lors de la création de votre prédiction. Chacun de ces facteurs a son importance calculée pour les prévisions agrégées qu’un modèle crée. Vous pouvez utiliser ces facteurs pour aider à valider vos résultats de prédiction. Ou vous pouvez utiliser ces informations ultérieurement pour [créer des segments](segments.md) qui pourraient contribuer à influer sur le risque de désabonnement des clients
       > [!div class="mx-imgBorder"]
       > ![Liste montrant les facteurs influents et leur importance dans la prévision du résultat du désabonnement](media/subscription-churn-influentialfactors.PNG "Liste montrant les facteurs influents et leur importance dans la prévision du résultat du désabonnement")

## <a name="manage-predictions"></a>Gérer les prédictions

Il est possible d'optimiser, de dépanner, d'actualiser ou de supprimer des prédictions. Consultez un rapport d'utilisation des données d'entrée pour découvrir comment rendre un prédiction plus rapide et plus fiable. Pour plus d’informations, consultez [Gérer les prédictions](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
