---
title: Prédiction de recommandation de produit
description: Prédisez les produits qu’un client est susceptible d’acheter ou avec lesquels interagir.
ms.date: 05/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 9b3e60c49d294d031f43ef0594cb69707bb64019
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762729"
---
# <a name="product-recommendation-prediction"></a>Prédiction de recommandation de produit

Le modèle de recommandation de produit crée des ensembles de recommandations de produit prédictives. Les recommandations sont basées sur le comportement d’achat précédent et les clients ayant des modèles d’achat similaires. Vous pouvez créer des prédictions de recommandation de produit sur la page **Intelligence** > **Prédictions**. Sélectionnez **Mes prédictions** pour voir les autres prédictions que vous avez créées.

Les recommandations de produits peuvent être soumises aux lois et réglementations locales ainsi qu’aux attentes des clients, que le modèle n’est pas conçu pour prendre spécifiquement en compte.  En tant qu’utilisateur de cette fonctionnalité prédictive, **vous devez revoir les recommandations avant de les fournir à vos clients** pour vous assurer d’être en conformité avec les lois ou réglementations applicables, ainsi qu’avec les attentes des clients concernant vos éventuelles recommandations.

De plus, la sortie de ce modèle vous donnera des recommandations basées sur l’ID du produit. Votre mécanisme de remise devra mapper les ID de produit prévus au contenu approprié pour que vos clients puissent tenir compte de la localisation, du contenu des images et d’autres contenus ou comportements spécifiques à l’entreprise.

## <a name="sample-guide"></a>Exemple de guide

Si vous souhaitez essayer cette fonctionnalité mais que vous ne disposez pas de données pour remplir les conditions ci-dessous, vous pouvez [créer un exemple d’implémentation](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Conditions préalables

- Au minimum [Autorisations collaborateur](permissions.md) dans Customer Insights.

- Connaissances commerciales pour comprendre différents types de produits pour votre entreprise et comment vos clients interagissent avec eux. Nous soutenons la recommandation de produits qui ont déjà été achetés par vos clients ou des recommandations de nouveaux produits.

- Votre environnement doit être configuré pour l’audience cible principale **clients particuliers**.

- Données sur vos transactions, achats et leur historique :
  - Identificateurs de transaction pour distinguer les achats ou transactions.
  - Identificateurs client pour mapper les transactions à vos clients.
  - Dates des événements de transaction qui spécifient les dates de la transaction.
  - Informations sur l’ID de produit pour la transaction.
  - (Facultatif) Une entité de données du catalogue de produits pour utiliser un filtre de produit.
  - (Facultatif) Si une transaction est un retour ou non.
  - Le schéma de données sémantique nécessite les informations suivantes :
    - **ID de transaction :** identifiant unique d’un achat ou d’une transaction.
    - **Date de la transaction :** date de l’achat ou de la transaction.
    - **Valeur de la transaction :** valeur numérique de l’achat ou de la transaction.
    - **ID de produit unique :** ID du produit ou service acheté si vos données se trouvent au niveau d’un élément de ligne.
    - (Facultatif) **Achat ou retour :** champ booléen dans lequel la valeur *true* identifie qu’une transaction était un retour. Si les données d’achat ou de retour ne sont pas fournies et la **Valeur de la transaction** est négative, nous utiliserons également ces informations pour déduire un retour.
- Caractéristiques des données suggérées :
  - Données historiques suffisantes : au moins un an de données transactionnelles, de préférence deux à trois ans pour inclure une certaine saisonnalité.
  - Achats multiples par client : trois transactions ou plus par ID de client
  - Nombre de clients : au moins 100 clients, de préférence plus de 10 000 clients. Le modèle échouera s’il y a moins de 100 clients.

> [!NOTE]
>
> - Le modèle nécessite l’historique des transactions de vos clients. La définition d’une transaction est assez flexible. Toute donnée qui décrit une interaction entre l’utilisateur et le produit peut fonctionner comme entrée. Par exemple, acheter un produit, suivre un cours ou assister à un événement.
> - Une seule entité de l’historique des transactions peut être configurée actuellement. S’il existe plusieurs entités d’achats, réunissez-les dans Power Query avant l’ingestion des données.
> - Si la commande et les détails de la commande sont des entités différentes, associez-les avant de les utiliser dans le modèle. Le modèle ne fonctionne pas avec uniquement un ID de commande ou un ID de reçu dans une entité.

## <a name="create-a-product-recommendation-prediction"></a>Créer une prédiction de recommandation de produit

1. Dans Customer Insights, accédez à **Intelligence** > **Prédictions**.

1. Sélectionnez la vignette **Modèle de recommandation de produit** et sélectionnez **Utiliser ce modèle**.
   > [!div class="mx-imgBorder"]
   > ![Vignette de modèle de recommandation de produit avec le bouton Utiliser ce modèle.](media/product-recommendation-usethismodel.PNG "Vignette de modèle de recommandation de produit avec le bouton Utiliser ce modèle")

1. Passez en revue les informations sur les exigences du modèle. Si vous disposez des données requises, sélectionnez **Démarrer**.

### <a name="name-model"></a>Nommer le modèle

1. Donnez un nom au modèle pour le distinguer des autres modèles.

1. Entrez un nom pour l’entité de sortie en utilisant uniquement des lettres et des chiffres, sans aucun espace. Il s’agit du nom que l’entité modèle utilisera. Ensuite, cliquez sur **Suivant**.

### <a name="define-product-recommendation-configuration"></a>Définir la configuration des recommandations de produits

1. Définissez le **Nombre de produits** que vous souhaitez recommander à un client. Cette valeur dépend de la manière dont votre méthode de livraison remplit les données. Si vous pouvez recommander trois produits, définissez cette valeur en conséquence.

   >[!TIP]
   > Vous pouvez sélectionner **Enregistrer le brouillon** à tout moment pour enregistrer la prédiction en tant que brouillon. Vous trouverez le brouillon de prédiction dans l’onglet **Mes prédictions**.

1. Choisissez si vous souhaitez inclure les produits que les clients ont récemment achetés dans le champ **Achats répétés attendus**.

1. Définissez la **Fenêtre de consultation**. Ce paramètre spécifie le délai d’exécution que le modèle considère avant de recommander à nouveau le produit à l’utilisateur. Par exemple, indiquez qu’un client achète un ordinateur portable tous les deux ans. Cette fenêtre examinera l’historique des achats sur les deux dernières années, et si elle trouve un article, celui-ci sera filtré des recommandations.

1. Sélectionnez **Suivant**.

### <a name="add-required-data"></a>Ajouter les données requises

1. Sélectionnez **Ajouter des données** et choisissez le type d’activité dans le volet latéral qui contient les informations requises sur l’historique des transactions ou des achats.

1. Sous **Choisir les activités**, choisissez les activités spécifiques de l’activité sélectionnée sur lesquelles vous souhaitez que le calcul se concentre.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Volet latéral affichant le choix d’activités spécifiques de type sémantique.":::

1. Si vous n’avez pas encore associé l’activité à un type sémantique, sélectionnez **Modifier**. L’expérience guidée pour associer les activités sémantiques s’ouvre. Associez vos données aux champs correspondants dans le type d’activité sélectionné.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Page définissant le type d’activité.":::

1. Après avoir associé l’activité au type sémantique correspondant, sélectionnez **Suivant** pour continuer.

1. Associez les attributs sémantiques aux champs requis pour exécuter le modèle.

1. Sélectionnez **Enregistrer**.

1. Sélectionnez **Suivant**.

### <a name="configure-product-filters"></a>Configurer les filtres de produit

Parfois, seuls certains produits sont utiles ou appropriés au type de prédiction que vous créez. Les filtres de produit vous permettent d’identifier un sous-ensemble de produits avec des caractéristiques spécifiques à recommander à vos clients. Le modèle utilisera tous les produits disponibles pour apprendre des modèles, mais n’utilisera que les produits correspondant au filtre de produit dans sa sortie.

1. Dans l’étape **Ajouter des informations sur les produits**, ajoutez votre catalogue de produits avec des informations pour chaque produit. Mappez les informations requises et sélectionnez **Suivant**.

1. Dans l’étape **Filtres de produit**, choisissez parmi les options suivantes.

   - **Aucun filtre** : utilisez tous les produits dans la prédiction de recommandation de produits.

   - **Définir des filtres de produit spécifiques** : utilisez des produits spécifiques dans la prédiction de recommandation de produits.

1. Cliquez sur **Suivant**.

1. Si vous choisissez de définir un filtre de produit, vous devez le définir maintenant. Dans le volet **Attributs du catalogue de produits**, sélectionnez les attributs de votre *Entité de catalogue de produits* que vous souhaitez inclure dans le filtre.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Volet latéral affichant les attributs de l’entité de catalogue de produits à sélectionner pour les filtres de produit.":::

1. Choisissez si vous souhaitez que le filtre de produit utilise des connecteurs **et** ou **ou** pour combiner logiquement votre sélection d’attributs du catalogue de produits.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Exemple de configuration de filtres de produit combinés à des connecteurs logiques AND.":::

1. Cliquez sur **Suivant**.

### <a name="set-update-schedule-and-review-configuration"></a>Définir la planification des mises à jour et revoir la configuration

1. Définissez une fréquence pour renouveler l’entraînement de votre modèle. Ce paramètre est important pour mettre à jour la précision des prédictions lorsque de nouvelles données sont importées dans Customer Insights. La plupart des entreprises peuvent se réentraîner une fois par mois et obtenir une bonne précision pour leur prédiction.

1. Cliquez sur **Suivant**.

1. Vérifiez la configuration. Vous pouvez revenir à n’importe quelle partie de la configuration de prédiction en sélectionnant **Modifier** sous la valeur indiquée. Ou vous pouvez sélectionner une étape de configuration dans l’indicateur de progression.

1. Si toutes les valeurs sont configurées correctement, sélectionnez **Enregistrer et exécuter** pour commencer le processus de prédiction. Sur l’onglet **Mes prédictions**, vous pouvez voir l’état de vos prévisions. Le processus peut prendre plusieurs heures pour se terminer selon la quantité de données utilisées dans la prédiction.

## <a name="review-a-prediction-status-and-results"></a>Examiner l’état et les résultats de la prédiction

1. Accédez à l’onglet **Mes prédictions** sur **Intelligence** > **Prédictions**.
   > [!div class="mx-imgBorder"]
   > ![Affichage de la page Mes prédictions.](media/product-recommendation-mypredictions.PNG "Affichage de la page Mes prédictions")

1. Sélectionnez la prédiction à réviser.
   - **Nom de la prédiction :** Nom de la prédiction fourni lors de sa création.
   - **Type de prédiction :** Type de modèle utilisé pour la prédiction
   - **Entité de sortie :** Nom de l’entité pour stocker la sortie de la prédiction. Vous pouvez trouver une entité portant ce nom sur **Données** > **Entités**.
      *Score* dans l’entité de sortie est une mesure quantitative de la recommandation. Le modèle recommande des produits avec un score plus élevé par rapport aux produits avec un score plus faible.
   - **Champ prédit** : ce champ n’est renseigné que pour certains types de prédictions, et il n’est pas utilisé dans la prédiction de recommandation de produits.
   - **Statut :** Statut actuel de l’exécution de la prédiction.
        - **Mis en file d’attente :** La prédiction attend actuellement l’exécution d’autres processus.
        - **Actualisation :** La prédiction exécute actuellement l’étape de « notation » du traitement pour produire des résultats qui iront dans l’entité de sortie.
        - **Échec :** La prédiction a échoué. Sélectionnez **Journaux** pour obtenir plus de détails.
        - **Réussite :** La prédiction a réussi. Sélectionnez **Afficher** sous les ellipses verticales pour revoir la prédiction
   - **Modifié :** Date de modification de la configuration de la prédiction.
   - **Dernière actualisation :** Date d’actualisation de la prédiction dans l’entité en sortie.

1. Sélectionnez les ellipses verticales à côté de la prédiction pour laquelle vous souhaitez consulter les résultats et sélectionnez **Afficher**.
   > [!div class="mx-imgBorder"]
   > ![Affichage des options dans le menu ellipses verticales pour une prédiction, y compris modifier, actualiser, afficher, journaux et supprimer.](media/product-recommendation-verticalellipses.PNG "Affichage des options dans le menu ellipses verticales pour une prédiction, y compris modifier, actualiser, afficher, journaux et supprimer")

1. Il existe cinq sections principales de données dans la page de résultats :
    1. **Performance du modèle de formation :** A, B ou C sont des scores possibles. Ce score indique les performances de la prédiction et peut vous aider à prendre la décision d’utiliser les résultats stockés dans l’entité de sortie.
        - Les scores sont calculés selon les règles suivantes :
            - **A** Le modèle sera considéré de qualité **A** si la métrique "Success @ K" est supérieure d’au moins 10 % à la valeur de référence. 
            - **B** Le modèle sera considéré de qualité **B** si la mesure « Success @ K » est de 0 % à 10 % supérieure à la valeur de référence.
            - **C** Le modèle sera considéré de qualité **C** si la mesure « Success @ K » est inférieure à la valeur de référence.

               > [!div class="mx-imgBorder"]
               > ![Vue du résultat des performances du modèle.](media/product-recommendation-modelperformance.PNG "Vue du résultat des performances du modèle")
            - **Valeur de référence** : Le modèle prend les produits les plus recommandés par nombre d’achats pour tous les clients et utilise des règles apprises identifiées par le modèle pour créer un ensemble de recommandations pour les clients. Les prévisions sont ensuite comparées aux meilleurs produits, calculées par le nombre de clients ayant acheté le produit. Si un client a au moins un produit dans ses produits recommandés qui a également été vu dans les produits les plus achetés, il est considéré comme faisant partie de la base de référence. Si 10 de ces clients avaient acheté un produit recommandé sur un total de 100 clients, la référence serait de 10 %.
            - **Success @ K** : À l’aide d’un ensemble de périodes de validation des transactions, des recommandations sont créées pour tous les clients et comparées à l’ensemble de validation des transactions. Par exemple, dans une période de 12 mois, le 12e mois peut être mis de côté comme ensemble de données de validation. Si le modèle prédit au moins une chose que vous achèteriez au cours du 12e mois en fonction de ce qu’il a appris des 11 mois précédents, le client augmentera la métrique "Success @ K".

    1. **Produits les plus suggérés (avec décompte) :** les cinq principaux produits qui ont été prédits pour vos clients.
       > [!div class="mx-imgBorder"]
       > ![Graphique montrant les 5 produits les plus recommandés.](media/product-recommendation-topproducts.PNG "Graphique montrant les 5 produits les plus recommandés")

    1. **Facteurs de recommandation clés :** le modèle utilise l’historique des transactions des clients pour faire des recommandations de produits. Il apprend des modèles basés sur les achats passés et trouve des similitudes entre les clients et les produits. Ces similitudes sont ensuite utilisées pour générer des recommandations de produits.
    Voici les facteurs susceptibles d’influencer une recommandation de produits générée par le modèle.
        - **Transactions passées** : le modèle a utilisé les modèles d’achat dans le passé pour générer des recommandations de produits. Par exemple, le modèle peut recommander une *Souris Arc Surface* si quelqu’un a récemment acheté un *Surface Book 3* et un *Stylet Surface*. Le modèle a appris que, historiquement, de nombreux clients avaient acheté une *Souris Arc Surface* après avoir acheté un *Surface Book 3* et un *Stylet Surface*.
        - **Similitude de clients** : historiquement, un produit recommandé a été acheté par d’autres clients qui présentent des modèles d’achat similaires. Par exemple, les *Écouteurs Surface 2* ont été recommandés à John, car Jennifer et Brad ont récemment acheté des *Écouteurs Surface 2*. Le modèle pense que John est similaire à Jennifer et Brad, car ils ont historiquement eu des modèles d’achat similaires.
        - **Similitude de produits** : un produit recommandé est similaire à d’autres produits que le client avait précédemment achetés. Le modèle considère que deux produits sont similaires s’ils ont été achetés ensemble ou par des clients similaires. Par exemple, quelqu’un reçoit une recommandation pour un *Lecteur de stockage USB*, car il a précédemment acheté un *Adaptateur USB-C vers USB* et le modèle estime que le *Lecteur de stockage USB* est similaire à l’*Adaptateur USB-C vers USB* sur la base des modèles d’achat historiques.

        Chaque recommandation de produits est influencée par un ou plusieurs de ces facteurs. Le pourcentage de recommandations dans lesquelles chaque facteur d’influence a joué un rôle est visualisé dans un graphique. Dans l’exemple suivant, 100 % des recommandations ont été influencées par les transactions passées, 60 % par la similitude de clients et 22 % par la similitude de produits. Pointez la souris sur les barres du graphique pour voir le pourcentage exact dans lequel les facteurs d’influence ont contribué.

        > [!div class="mx-imgBorder"]
        > ![Principaux facteurs de recommandation.](media/product-recommendation-keyrecommendationfactors.png "Facteurs de recommandation clés appris par le modèle pour générer des recommandations de produits")

   1. **Statistiques de données** : donne une description générale du nombre de transactions, de clients et de produits pris en compte par le modèle. Il est basé sur les données d’entrée utilisées pour apprendre des modèles et générer des recommandations de produits.

      > [!div class="mx-imgBorder"]
      > ![Statistiques des données.](media/product-recommendation-datastatistics.png "Statistiques de données sur les données d’entrée utilisées par le modèle pour apprendre des modèles")

      Cette section affiche les statistiques sur les points de données qui ont été utilisés par le modèle pour apprendre des modèles et générer des recommandations de produits. Le filtrage, tel qu’il est configuré dans la configuration du modèle, s’appliquera à la sortie générée par le modèle. Cependant, le modèle utilise toutes les données disponibles pour apprendre des modèles. Par conséquent, si vous utilisez le filtrage de produits dans la configuration du modèle, cette section indiquera le nombre total de produits analysés par le modèle pour apprendre des modèles, qui peut différer du nombre de produits correspondant aux critères de filtrage définis.

   1. **Recommandations de produits hautement fiables :** Un échantillon de recommandations fournies à vos clients qui, selon le modèle, sont susceptibles d’être achetées par le client.    
      Si un catalogue de produits est ajouté, les ID de produits sont remplacés par les noms de produits. Les noms de produit fournissent des informations plus exploitables et intuitives sur les prédictions.
       > [!div class="mx-imgBorder"]
       > ![Liste présentant des suggestions hautement fiables pour un ensemble sélectionné de clients individuels.](media/product-recommendation-highconfidence.PNG "Liste présentant des suggestions hautement fiables pour un ensemble sélectionné de clients individuels")

## <a name="manage-predictions"></a>Gérer les prédictions

Il est possible d’optimiser, de dépanner, d’actualiser ou de supprimer des prédictions. Consultez un rapport d’utilisation des données d’entrée pour découvrir comment rendre un prédiction plus rapide et plus fiable. Pour plus d’informations, consultez [Gérer les prédictions](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]