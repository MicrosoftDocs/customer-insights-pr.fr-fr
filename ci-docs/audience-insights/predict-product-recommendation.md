---
title: Prédiction de recommandation de produit
description: Prédisez les produits qu’un client est susceptible d’acheter ou avec lesquels interagir.
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270489"
---
# <a name="product-recommendation-prediction-preview"></a>Prédiction de recommandation de produit (version préliminaire)

Le modèle de recommandation de produit crée des ensembles de recommandations de produit prédictives. Les recommandations sont basées sur le comportement d’achat précédent et les clients ayant des modèles d’achat similaires. Vous pouvez créer des prédictions de recommandation de produit sur la page **Intelligence** > **Prédictions**. Sélectionnez **Mes prédictions** pour voir les autres prédictions que vous avez créées.

Les recommandations de produits peuvent être soumises aux lois et réglementations locales ainsi qu’aux attentes des clients, que le modèle n’est pas conçu pour prendre spécifiquement en compte.  En tant qu’utilisateur de cette capacité prédictive, **vous devez revoir les recommandations avant de les livrer à vos clients** pour vous assurer que vous vous conformez à toutes les lois ou réglementations applicables, ainsi qu’aux attentes des clients concernant ce que vous pouvez recommander. 

De plus, la sortie de ce modèle vous donnera des recommandations basées sur l’ID du produit. Votre mécanisme de livraison devra prendre les ID de produit prédits et les mapper au contenu approprié pour que vos clients tiennent compte de la localisation, du contenu d’image et d’autres contenus ou comportements spécifiques à l’entreprise.

## <a name="sample-guide"></a>Exemple de guide

Si vous souhaitez essayer cette fonctionnalité mais que vous ne disposez pas de données pour remplir les conditions ci-dessous, vous pouvez [créer un exemple d’implémentation](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Conditions préalables

- Au minimum [Autorisations collaborateur](permissions.md) dans Customer Insights.
- Connaissances commerciales pour comprendre différents types de produits pour votre entreprise et comment vos clients interagissent avec eux. Nous soutenons la recommandation de produits qui ont déjà été achetés par vos clients ou des recommandations de nouveaux produits.
- Données sur vos transactions, achats et leur historique :
    - Identificateurs de transaction pour distinguer les achats ou transactions.
    - Identificateurs client pour mapper les transactions à vos clients.
    - Dates des événements de transaction qui spécifient les dates de la transaction.
    - (Facultatif) Informations sur l’ID de produit de la transaction.
    - (Facultatif) Si une transaction est un retour ou non.
    - Le schéma de données sémantique nécessite les informations suivantes :
        - **ID de transaction :** identifiant unique d’un achat ou d’une transaction.
        - **Date de la transaction :** date de l’achat ou de la transaction.
        - **Valeur de la transaction :** valeur numérique de l’achat ou de la transaction.
        - **ID de produit unique :** ID du produit ou service acheté si vos données se trouvent au niveau d’un élément de ligne.
        - (Facultatif) **Achat ou retour :** champ vrai/faux qui identifie si la transaction était un retour ou non. Si la **Valeur de la transaction** est négative, nous utiliserons également ces informations pour déduire un retour.


## <a name="create-a-product-recommendation-prediction"></a>Créer une prédiction de recommandation de produit

1. Dans Customer Insights, accédez à **Intelligence** > **Prédictions**.

1. Sélectionnez la vignette **Modèle de recommandations de produits (version préliminaire)** et sélectionnez **Utiliser ce modèle**.
   > [!div class="mx-imgBorder"]
   > ![Vignette de modèle de recommandation de produit avec le bouton Utiliser ce modèle](media/product-recommendation-usethismodel.PNG "Vignette de modèle de recommandation de produit avec le bouton Utiliser ce modèle")

1. Passez en revue les informations sur les exigences du modèle. Si vous disposez des données requises, sélectionnez **Démarrer**.

### <a name="name-model"></a>Nommer le modèle

1. Donnez un nom au modèle pour le distinguer des autres modèles.

1. Entrez un nom pour l’entité de sortie en utilisant uniquement des lettres et des chiffres, sans aucun espace. Il s’agit du nom que l’entité modèle utilisera. Ensuite, cliquez sur **Suivant**.

### <a name="define-product-recommendation-configuration"></a>Définir la configuration des recommandations de produits

1. Définissez le **Nombre de produits** que vous souhaitez recommander à un client. Cette valeur dépend de la manière dont votre méthode de livraison remplit les données. Si vous pouvez recommander trois produits, définissez cette valeur en conséquence.
   
   >[!TIP]
   > Vous pouvez sélectionner **Enregistrer et fermer** à tout moment pour enregistrer la prédiction en tant que brouillon. Vous trouverez le brouillon de prédiction dans l’onglet **Mes prédictions**.

1. Choisissez si vous souhaitez **Suggérer des produits que les clients ont récemment achetés**.

1. Si vous avez choisi de *ne pas* recommander des produits récemment achetés, définissez la **Fenêtre de consultation**. Ce paramètre spécifie le délai d’exécution que le modèle considère avant de recommander à nouveau le produit à l’utilisateur. Par exemple, indiquez qu’un client achète un ordinateur portable tous les 2 ans. Cette fenêtre examinera l’historique des achats des 2 dernières années, et s’ils trouvent un article, l’article sera filtré à partir des recommandations.

1. Cliquez sur **Suivant**.

### <a name="add-required-data"></a>Ajouter les données requises

1. Sélectionnez **Ajouter des données** pour **Historique des transactions utilisateur** et choisissez l’entité qui fournit les informations sur l’historique des transactions/achats comme décrit dans les [conditions préalables](#prerequisites).

1. Mappez les champs sémantiques aux attributs de votre entité d’historique des achats et sélectionnez **Suivant**. Pour une obtenir une description des champs, consultez les [conditions préalables](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Définir la relation entre les entités](media/product-recommendation-purchasehistorymapping.PNG "Page d’historique des achats affichant les attributs sémantiques mappés aux champs de l’entité d’historique des achats sélectionnée")

1. Si les champs ne sont pas renseignés, configurez la relation entre votre entité d’historique des achats et l’entité *Client*.
    1. Sélectionnez l’**Entité d’historique des achats**.
    1. Sélectionnez le **Champ** qui identifie le client dans l’entité d’historique des achats. Il doit être lié à l’ID client principal de votre entité *client*.
    1. Sélectionnez l’**Entité client** qui correspond à votre entité client principale.
    1. Entrez un nom qui décrit la relation.
       > [!div class="mx-imgBorder"]
       > ![Page Historique des achats illustrant la création d’une relation avec le client](media/model-purchase-join.png "Page Historique des achats illustrant la création d’une relation avec le client")

1. Sélectionnez **Enregistrer**.

1. Cliquez sur **Suivant**.

### <a name="set-schedule-and-review-configuration"></a>Définir le calendrier et revoir la configuration

1. Définissez une fréquence pour renouveler l’entraînement de votre modèle. Ce paramètre est important pour mettre à jour la précision des prédictions lorsque de nouvelles données sont importées dans Customer Insights. La plupart des entreprises peuvent se réentraîner une fois par mois et obtenir une bonne précision pour leur prédiction.

1. Cliquez sur **Suivant**.

1. Vérifiez la configuration. Vous pouvez revenir à n’importe quelle partie de la configuration de prédiction en sélectionnant **Modifier** sous la valeur indiquée. Ou vous pouvez sélectionner une étape de configuration dans l’indicateur de progression.

1. Si toutes les valeurs sont configurées correctement, sélectionnez **Enregistrer et exécuter** pour commencer le processus de prédiction. Sur l’onglet **Mes prédictions**, vous pouvez voir l’état de vos prévisions. Le processus peut prendre plusieurs heures pour se terminer selon la quantité de données utilisées dans la prédiction.

## <a name="review-a-prediction-status-and-results"></a>Examiner l’état et les résultats de la prédiction

1. Accédez à l’onglet **Mes prédictions** sur **Intelligence** > **Prédictions**.
   > [!div class="mx-imgBorder"]
   > ![Affichage de la page Mes prédictions](media/product-recommendation-mypredictions.PNG "Affichage de la page Mes prédictions")

1. Sélectionnez la prédiction à réviser.
   - **Nom de la prédiction :** Nom de la prédiction fourni lors de sa création.
   - **Type de prédiction :** Type de modèle utilisé pour la prédiction
   - **Entité de sortie :** Nom de l’entité pour stocker la sortie de la prédiction. Vous pouvez trouver une entité portant ce nom sur **Données** > **Entités**.
   - **Champ prédit :** ce champ n’est renseigné que pour certains types de prédictions et n’est pas utilisé dans la prédiction de l’attrition.
   - **Statut :** Statut actuel de l’exécution de la prédiction.
        - **Mis en file d’attente :** La prédiction attend actuellement l’exécution d’autres processus.
        - **Actualisation :** La prédiction exécute actuellement l’étape de « notation » du traitement pour produire des résultats qui iront dans l’entité de sortie.
        - **Échec :** La prédiction a échoué. Sélectionnez **Journaux** pour obtenir plus de détails.
        - **Réussite :** La prédiction a réussi. Sélectionnez **Afficher** sous les ellipses verticales pour revoir la prédiction
   - **Modifié :** Date de modification de la configuration de la prédiction.
   - **Dernière actualisation :** Date d’actualisation de la prédiction dans l’entité en sortie.

1. Sélectionnez les ellipses verticales à côté de la prédiction pour laquelle vous souhaitez consulter les résultats et sélectionnez **Afficher**.
   > [!div class="mx-imgBorder"]
   > ![Affichage des options dans le menu ellipses verticales pour une prédiction, y compris modifier, actualiser, afficher, journaux et supprimer](media/product-recommendation-verticalellipses.PNG "Affichage des options dans le menu ellipses verticales pour une prédiction, y compris modifier, actualiser, afficher, journaux et supprimer")

1. La page de résultats comporte trois sections principales de données :
    1. **Performance du modèle de formation :** A, B ou C sont des scores possibles. Ce score indique les performances de la prédiction et peut vous aider à prendre la décision d’utiliser les résultats stockés dans l’entité de sortie.
        - Les scores sont calculés selon les règles suivantes :
            - **A** Le modèle sera considéré de qualité **A** si la métrique "Success @ K" est supérieure d’au moins 10 % à la valeur de référence. 
            - **B** Le modèle sera considéré de qualité **B** si la métrique "Success @ K" est de 0 % à 10 % supérieure à la valeur de référence.
            - **C** Le modèle sera considéré de qualité **C** si la métrique "Success @ K" est inférieure à la valeur de référence.
               
               > [!div class="mx-imgBorder"]
               > ![Vue du résultat des performances du modèle](media/product-recommendation-modelperformance.PNG "Vue du résultat des performances du modèle")
            - **Valeur de référence** : Le modèle prend les produits les plus recommandés par nombre d’achats pour tous les clients et utilise des règles apprises identifiées par le modèle pour créer un ensemble de recommandations pour les clients. Les prévisions sont ensuite comparées aux meilleurs produits, calculées par le nombre de clients ayant acheté le produit. Si un client a au moins un produit dans ses produits recommandés qui a également été vu dans les produits les plus achetés, il est considéré comme faisant partie de la base de référence. Si 10 de ces clients avaient acheté un produit recommandé sur un total de 100 clients, la référence serait de 10 %.
            - **Success @ K** : À l’aide d’un ensemble de périodes de validation des transactions, des recommandations sont créées pour tous les clients et comparées à l’ensemble de validation des transactions. Par exemple, dans une période de 12 mois, le 12e mois peut être mis de côté comme ensemble de données de validation. Si le modèle prédit au moins une chose que vous achèteriez au cours du 12e mois en fonction de ce qu’il a appris des 11 mois précédents, le client augmentera la métrique "Success @ K".
    
    1. **Produits les plus suggérés (avec décompte) :** Les 5 meilleurs produits prévus pour vos clients.
       > [!div class="mx-imgBorder"]
       > ![Graphique montrant les 5 produits les plus recommandés](media/product-recommendation-topproducts.PNG "Graphique montrant les 5 produits les plus recommandés")
    
    1. **Recommandations de produits hautement fiables :** Un échantillon de recommandations fournies à vos clients qui, selon le modèle, sont susceptibles d’être achetées par le client.
       > [!div class="mx-imgBorder"]
       > ![Liste présentant des suggestions hautement fiables pour un ensemble sélectionné de clients individuels](media/product-recommendation-highconfidence.PNG "Liste présentant des suggestions hautement fiables pour un ensemble sélectionné de clients individuels")

## <a name="fix-a-failed-prediction"></a>Correction d’une prédiction ayant échoué

1. Accédez à l’onglet **Mes prédictions** sur **Intelligence** > **Prédictions**.

1. Sélectionnez la prédiction pour laquelle vous souhaitez afficher les journaux d’erreurs et sélectionnez **Journaux**.

1. Passez toutes les erreurs en revue. Plusieurs types d’erreurs peuvent survenir et décrivent la condition à l’origine de l’erreur. Par exemple, une erreur pour laquelle il n’y a pas suffisamment de données à prévoir avec précision est généralement résolue en chargeant des données supplémentaires dans Customer Insights.

## <a name="refresh-a-prediction"></a>Actualiser une prédiction

Les prédictions s’actualisent automatiquement sur le même [Planning des actualisations de vos données](system.md#schedule-tab) tel que configuré dans les paramètres.

1. Accédez à l’onglet **Mes prédictions** sur **Intelligence** > **Prédictions**.

1. Sélectionnez les ellipses verticales à côté de la prédiction que vous souhaitez actualiser.

1. Cliquez sur **Actualiser**.

## <a name="delete-a-prediction"></a>Supprimer une prédiction

La suppression d’une prédiction entraînera également la suppression de son entité de sortie.

1. Accédez à l’onglet **Mes prédictions** sur **Intelligence** > **Prédictions**.

1. Sélectionnez les ellipses verticales à côté de la prédiction que vous souhaitez supprimer.

1. Sélectionnez **Supprimer**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]