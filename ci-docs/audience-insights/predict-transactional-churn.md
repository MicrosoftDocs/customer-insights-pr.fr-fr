---
title: Prédiction de l’attrition transactionnelle
description: Prédisez si un client risque de ne plus acheter vos produits ou services.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 28c89693239393d93b7a816535b8c3fffe353935
ms.sourcegitcommit: e57d51ae3cc233f7b6185c074c66efd9800c02c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2021
ms.locfileid: "6559402"
---
# <a name="transactional-churn-prediction-preview"></a>Prédiction de l’attrition transactionnelle (version préliminaire)

La prédiction de l’attrition transactionnelle aide à prédire si un client n’achètera plus vos produits ou services sur une période donnée. Vous pouvez créer de nouvelles prédictions de l’attrition en cliquant sur **Intelligence** > **Prédictions**. Sélectionnez **Mes prédictions** pour voir les autres prédictions que vous avez créées.

> [!TIP]
> Essayez le didacticiel de prédiction de l’attrition transactionnelle en utilisant des exemples de données : [Exemple de guide de prédiction de l’attrition transactionnelle (version préliminaire)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Conditions préalables

- Au minimum [Autorisations collaborateur](permissions.md) dans Customer Insights.
- Connaissance des affaires pour comprendre ce que le désabonnement signifie pour votre entreprise. Nous prenons en charge les définitions de l’attrition basées sur le temps, ce qui signifie qu’un client est considéré comme perdu après une période sans achats.
- Données sur vos transactions/achats et leur historique :
    - Identificateurs de transaction pour distinguer les achats/transactions.
    - Identificateurs client pour faire correspondre les transactions à vos clients.
    - Dates des événements de transaction, qui définissent les dates de la transaction.
    - Le schéma de données sémantique pour les achats/transactions nécessite les informations suivantes :
        - **ID de transaction :** identifiant unique d’un achat ou d’une transaction.
        - **Date de la transaction :** date de l’achat ou de la transaction.
        - **Valeur de la transaction :** montant de la valeur monétaire/numérique de la transaction/de l’article.
        - (Facultatif) **ID de produit unique :** ID du produit ou service acheté si vos données se trouvent au niveau d’un élément de ligne.
        - (Facultatif) **Indique si cette transaction était un retour :** champ vrai/faux qui identifie si la transaction était un retour ou non. Si la **Valeur de la transaction** est négative, nous utiliserons également ces informations pour déduire un retour.
- (Facultatif) Données sur les activités client :
    - Identificateurs d’activité pour distinguer les activités du même type.
    - Identifiants client pour faire correspondre les activités à vos clients.
    - Informations sur l’activité contenant le nom et la date de l’activité.
    - Le schéma de données sémantique pour les activités client comprend :
        - **Clé primaire :** Identifiant unique pour une activité. Par exemple, une visite du site web ou un enregistrement d’utilisation montrant que le client a essayé un échantillon de votre produit.
        - **Horodatage :** Date et heure de l’événement identifiées par la clé primaire.
        - **Événement :** Nom de l’événement que vous souhaitez utiliser. Par exemple, un champ appelé « UserAction » dans une épicerie peut être un coupon utilisé par le client.
        - **Détails :** Informations détaillées sur l’événement. Par exemple, un champ appelé « CouponValue » dans une épicerie peut être la valeur monétaire du coupon.
- Caractéristiques des données suggérées :
    - Données historiques suffisantes : données de transaction pour au moins le double de la période de temps sélectionnée. De préférence, deux à trois ans d’historique des transactions. 
    - Achats multiples par client : dans l’idéal, au moins deux transactions par client.
    - Nombre de clients : au moins 10 profils client, de préférence plus de 1 000 clients uniques. Le modèle échouera s’il y a moins de 10 clients et des données historiques insuffisantes.
    - Intégrité des données : moins de 20 % des valeurs manquantes dans le champ de données de l’entité fournie.

> [!NOTE]
> Pour une entreprise avec une fréquence d’achat élevée des clients (toutes les semaines), il est recommandé de sélectionner une période de prédiction plus courte et une définition d’attrition. Pour une faible fréquence d’achat (tous les mois ou une fois par an), choisissez une période de prédiction plus longue et une définition d’attrition.

## <a name="create-a-transactional-churn-prediction"></a>Créer une prédiction de l’attrition transactionnelle

1. Dans Customer Insights, accédez à **Intelligence** > **Prédictions**.

1. Sélectionnez la vignette **Modèle d’attrition clients (version préliminaire)** et sélectionnez **Utiliser ce modèle**.
   
1. Dans le volet **Modèle d’attrition clients**, choisissez **Transactionnel** et sélectionnez **Démarrer**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Capture d’écran avec l’option transactionnelle sélectionnée dans le volet Modèle d’attrition clients.":::

### <a name="name-model"></a>Nommer le modèle

1. Donnez un nom au modèle pour le distinguer des autres modèles.

1. Donnez un nom à l’entité en sortie en utilisant uniquement des lettres et des chiffres, sans espaces. Il s’agit du nom que l’entité modèle utilisera. 

1. Cliquez sur **Suivant**.

### <a name="define-customer-churn"></a>Définir l’attrition client

1. Définissez une fenêtre de jours pour prédire l’attrition dans le champ **Identifiez les clients que vous risquez de perdre dans la prochaine**. Par exemple, prédisez le risque d’attrition de vos clients au cours des 90 prochains jours pour vous aligner sur vos efforts de fidélisation avec le marketing. Prédire le risque d’attrition sur une période plus ou moins longue peut rendre plus difficile de prendre en compte les facteurs de votre profil de risque d’attrition, mais cela dépend des besoins spécifiques à votre entreprise. 
   >[!TIP]
   > Vous pouvez sélectionner **Enregistrer et fermer** à tout moment pour enregistrer la prédiction en tant que brouillon. Vous trouverez le projet de prédiction dans l’onglet **Mes prédictions** pour continuer.

1. Entrez le nombre de jours pour définir l’attrition dans le champ **Un client est perdu s’il n’a pas effectué d’achats dans**. Par exemple, si un client n’a pas effectué d’achats au cours des 30 derniers jours, il peut être considéré comme perdu pour votre entreprise. 

1. Sélectionner **Suivant** pour continuer

### <a name="add-required-data"></a>Ajouter les données requises

1. Sélectionnez **Ajouter des données** pour **Historique des achats** et choisissez l’entité qui fournit les informations sur l’historique des transactions/achats comme décrit dans les [conditions préalables](#prerequisites).

1. Mappez les champs sémantiques aux attributs de votre entité d’historique des achats et sélectionnez **Suivant**. Pour une obtenir une description des champs, consultez les [conditions préalables](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Mappez les champs sémantiques de l’entité d’achat.":::

1. Si les champs ci-dessous ne sont pas renseignés, configurez la relation entre votre entité d’historique des achats et l’entité Client.
    1. Sélectionnez l’**Entité d’historique des achats**.
    1. Sélectionnez le **Champ** qui identifie le client dans l’entité d’historique des achats. Il doit être lié à l’ID client principal de votre entité client.
    1. Sélectionnez l’**Entité client** qui correspond à votre entité client principale.
    1. Entrez un nom qui décrit la relation.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Page Historique des achats illustrant la création d’une relation avec le client.":::
   
1. Cliquez sur **Suivant**.

1. Vous pouvez éventuellement sélectionner **Ajouter des données** pour **Activités client**. Choisissez l’entité qui fournit les informations sur les activités client comme décrit dans les conditions préalables.

1. Mappez les champs sémantiques aux attributs de votre entité d’activités client et sélectionnez **Suivant**. Pour une obtenir une description des champs, consultez les [conditions préalables](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Mappez les champs client pour les données transactionnelles.":::

1. Sélectionnez un type d’activité correspondant au type d’activité du client que vous configurez. Sélectionnez **Créer** et choisissez un type d’activité disponible ou créez un nouveau type.

1. Vous devrez configurer la relation entre votre entité d’activité client et l’entité Client.
    1. Sélectionnez le champ qui identifie le client dans la table des activités client. Il peut être directement lié à l’ID de client principal de votre entité Client.
    1. Sélectionnez l’Entité client qui correspond à votre entité Client principale.
    1. Entrez un nom qui décrit la relation.

1. Sélectionnez **Enregistrer**.

1. Si vous avez d’autres activités client que vous souhaitez inclure, répétez les étapes ci-dessus.

1. Cliquez sur **Suivant**.

### <a name="set-schedule-and-review-configuration"></a>Définir le calendrier et revoir la configuration

1. Définissez une fréquence pour renouveler l’entraînement de votre modèle. Ce paramètre est important pour mettre à jour la précision des prédictions lorsque de nouvelles données sont ingérées. La plupart des entreprises peuvent se réentraîner une fois par mois et obtenir une bonne précision pour leur prédiction.

1. Cliquez sur **Suivant**.

1. Passez en revue la configuration de la prédiction. Vous pouvez revenir aux étapes précédentes en sélectionnant **Modifier** sous la valeur indiquée. Ou vous pouvez sélectionner une étape de configuration dans l’indicateur de progression.

1. Si toutes les valeurs sont configurées correctement, sélectionnez **Enregistrer et exécuter** pour commencer le processus de prédiction. Sur l’onglet **Mes prédictions**, vous pouvez voir l’état de vos prévisions. Le processus peut prendre plusieurs heures pour se terminer selon la quantité de données utilisées dans la prédiction.

## <a name="review-a-prediction-status-and-results"></a>Examiner l’état et les résultats de la prédiction

1. Accédez à **Intelligence** > **Prédictions** et sélectionnez l’onglet **Mes prédictions**.

1. Sélectionnez la prédiction à réviser.
   - **Nom de la prédiction :** nom de la prédiction fournie lors de sa création.
   - **Type de prédiction :** type de modèle utilisé pour la prédiction
   - **Entité de sortie :** Nom de l’entité pour stocker la sortie de la prédiction. Vous pouvez trouver une entité portant ce nom sur **Données** > **Entités**.    
     Dans l’entité de sortie, *ChurnScore* est la probabilité prédite d’attrition et *IsChurn* est une étiquette binaire basée sur *ChurnScore* avec un seuil de 0,5. Le seuil par défaut peut ne pas fonctionner pour votre scénario. [Créez un nouveau segment](segments.md#create-a-new-segment) avec votre seuil préféré.
     Tous les clients ne sont pas nécessairement des clients actifs. Certains d’entre eux n’ont peut-être pas eu d’activité pendant un certain temps et sont déjà considérés comme perdus, selon votre définition d’attrition. Prédire le risque d’attrition des clients qui sont déjà perdus n’est pas utile, car ce n’est pas une audience qui présente un intérêt.
   - **Champ prédit :** ce champ n’est renseigné que pour certains types de prédictions et n’est pas utilisé dans la prédiction de l’attrition.
   - **Statut :** statut de l’exécution de la prédiction.
        - **Mis en file d’attente :** la prédiction attend l’exécution des autres processus.
        - **Actualisation en cours :** la prédiction est en cours d’exécution pour produire des résultats qui seront envoyés vers l’entité de sortie.
        - **Échec :** l’exécution de la prédiction a échoué. [Consultez les journaux](manage-predictions.md#troubleshoot-a-failed-prediction) pour plus de détails.
        - **Réussite :** la prédiction a réussi. Sélectionnez **Afficher** sous les ellipses verticales pour revoir la prédiction
   - **Modifié :** Date de modification de la configuration de la prédiction.
   - **Dernière actualisation :** Date d’actualisation de la prédiction dans l’entité en sortie.

1. Sélectionnez les ellipses verticales à côté de la prédiction pour laquelle vous souhaitez consulter les résultats et sélectionnez **Afficher**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Affichez le contrôle pour voir les résultats d’une prédiction.":::   

1. La page de résultats comporte trois sections principales de données :
    1. **Performance du modèle de formation :** A, B ou C sont des scores possibles. Ce score indique les performances de la prédiction et peut vous aider à prendre la décision d’utiliser les résultats stockés dans l’entité de sortie. Les scores sont déterminés en fonction des règles suivantes :
         
         - **A** lorsque le modèle a prédit avec précision au moins 50 % des prédictions totales et que le pourcentage de prédictions précises pour les clients perdus est supérieur d’au moins 10 % au taux de référence.
            
         - **B** lorsque le modèle a prédit avec précision au moins 50 % des prédictions totales et que le pourcentage de prédictions précises pour les clients perdus est jusqu’à 10 % supérieur au taux de référence.
            
         - **C** lorsque le modèle a prédit avec précision moins de 50 % des prédictions totales ou que le pourcentage de prédictions précises pour les clients perdus est inférieur au taux de référence.
               
         - **Référence** prend l’entrée de l’intervalle de temps de prédiction pour le modèle (par exemple, un an) et le modèle crée différentes fractions de temps en le divisant par 2 jusqu’à ce qu’il atteigne un mois ou moins. Il utilise ces fractions pour créer une règle métier pour les clients qui n’ont pas effectué d’achats sur cette période. Ces clients sont considérés comme perdus. La règle métier basée sur le temps ayant la plus grande capacité à prédire qui présente un risque d’attrition est choisie comme modèle de référence.
            
    1. **Probabilité de désabonnement (nombre de clients) :** Groupes de clients en fonction du risque de désabonnement prévu. Ces données peuvent vous aider ultérieurement si vous souhaitez créer un segment de clients à haut risque de désabonnement. Ces segments aident à comprendre où doit se situer votre limite pour l’appartenance à un segment.
       
    1. **Facteurs les plus influents :** De nombreux facteurs sont pris en compte lors de la création de votre prédiction. Chacun des facteurs a son importance calculée pour les prédictions regroupées créées par un modèle. Vous pouvez utiliser ces facteurs pour aider à valider vos résultats de prédiction. Ou vous pouvez utiliser ces informations ultérieurement pour [créer des segments](segments.md) qui pourraient contribuer à influer sur le risque de désabonnement des clients

## <a name="manage-predictions"></a>Gérer les prédictions

Il est possible d'optimiser, de dépanner, d'actualiser ou de supprimer des prédictions. Consultez un rapport d'utilisation des données d'entrée pour découvrir comment rendre un prédiction plus rapide et plus fiable. Pour plus d’informations, consultez [Gérer les prédictions](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
