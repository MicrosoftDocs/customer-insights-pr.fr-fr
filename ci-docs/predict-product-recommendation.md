---
title: Prédire les recommandations de produits
description: Prédisez les produits qu’un client est susceptible d’acheter ou avec lesquels interagir.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610279"
---
# <a name="predict-product-recommendations"></a>Prédire les recommandations de produits

Le modèle de recommandation de produit crée des ensembles de recommandations de produit prédictives. Les recommandations sont basées sur le comportement d’achat précédent et les clients ayant des modèles d’achat similaires. Ce modèle est destiné aux consommateurs individuels (B2C).

Vous devez avoir des connaissances sur les différents types de produits pour votre entreprise et comment vos clients interagissent avec eux. Nous soutenons la recommandation de produits qui ont déjà été achetés par vos clients ou des recommandations de nouveaux produits.

Les recommandations de produits peuvent être soumises aux lois et réglementations locales ainsi qu’aux attentes des clients, que le modèle n’est pas conçu pour prendre spécifiquement en compte. Par conséquent, **vous devez revoir les recommandations avant de les fournir à vos clients** pour vous assurer d’être en conformité avec les lois ou réglementations applicables, ainsi qu’avec les attentes des clients concernant vos éventuelles recommandations.

La sortie de ce modèle fournit des recommandations basées sur l’ID du produit. Votre mécanisme de remise doit mapper les ID de produit prévus au contenu approprié pour que vos clients puissent tenir compte de la localisation, du contenu des images et d’autres contenus ou comportements spécifiques à l’entreprise.

> [!TIP]
> Essayez la prédiction de recommandation de produit en utilisant des exemples de données : [Exemple de guide de prédiction de recommandation de produit](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Conditions préalables

- Au moins des [autorisations contributeur](permissions.md)
- Au moins 100 clients, de préférence plus de 10 000 clients.
- ID client, un identificateur unique pour faire correspondre les transactions à un client individuel
- Au moins un an de données transactionnelles, de préférence deux à trois ans pour inclure une certaine saisonnalité. Dans l’idéal, au moins trois transactions ou plus par ID client. L’historique des transactions doit inclure :
  - **ID de transaction** : identificateur unique d’un achat ou d’une transaction.
  - **Date de la transaction** : date de l’achat ou de la transaction.
  - **Valeur de la transaction :** valeur numérique de l’achat ou de la transaction.
  - **ID de produit unique** : ID du produit ou service acheté si vos données se trouvent au niveau d’un élément de ligne.
  - **Achat ou retour** : valeur booléenne vrai/faux où *vrai* identifie qu’une transaction était un retour. Si les données d’achat ou de retour ne sont pas fournies dans le modèle et la **Valeur de la transaction** est négative, nous déduisons un retour.
- Une entité de données du catalogue de produits à utiliser comme filtre de produit.

> [!NOTE]
> - Le modèle nécessite l’historique des transactions de vos clients où la transaction désigne toute donnée décrivant une interaction entre l’utilisateur et le produit. Par exemple, acheter un produit, suivre un cours ou assister à un événement.
> - Une seule entité de l’historique des transactions peut être configurée. S’il existe plusieurs entités d’achats, combinez-les dans Power Query avant l’ingestion des données.
> - Si la commande et les détails de la commande sont des entités différentes, associez-les avant de les utiliser dans le modèle. Le modèle ne fonctionne pas avec uniquement un ID de commande ou un ID de reçu dans une entité.

## <a name="create-a-product-recommendation-prediction"></a>Créer une prédiction de recommandation de produit

Sélectionnez **Enregistrer le brouillon** à tout moment pour enregistrer la prédiction en tant que brouillon. Le brouillon de prédiction s’affiche dans l’onglet **Mes prédictions**.

1. Accédez à **Intelligence** > **Prédictions**.

1. Dans l’onglet **Créer**, sélectionnez **Utiliser le modèle** dans **Recommandations de produit (version préliminaire)**.

1. Cliquez sur **Démarrer**.

1. **Nommez ce modèle** et le **Nom de l’entité de sortie** pour les distinguer des autres modèles ou entités.

1. Cliquez sur **Suivant**.

### <a name="define-product-recommendation-preferences"></a>Définir les préférences de recommandation de produit

1. Définissez le **Nombre de produits** à recommander à un client. Cette valeur dépend de la manière dont votre méthode de livraison remplit les données.

1. Choisissez si vous souhaitez inclure les produits que les clients ont précédemment achetés dans le champ **Achats répétés attendus**.

1. Définissez la **Fenêtre de consultation** avec la période que le modèle considère avant de recommander à nouveau le produit à l’utilisateur. Par exemple, indiquez qu’un client achète un ordinateur portable tous les deux ans. Le modèle examine l’historique des achats sur les deux dernières années, et s’il trouve un article, celui-ci est filtré des recommandations.

1. Sélectionnez **Suivant**.

### <a name="add-purchase-history"></a>Ajouter l’historique d’achat

1. Sélectionnez **Ajouter des données** pour **Historique des transactions client**.

1. Sélectionnez le type d’activité sémantique **SalesOrderLine** qui contient les informations requises sur l’historique des transactions ou des achats. Si l’activité n’a pas été configurée, sélectionnez **ici** et créez-la.

1. Sous **Activités**, si les attributs d’activité ont été mappés sémantiquement lors de la création de l’activité, choisissez l’entité ou les attributs spécifiques sur lesquels vous souhaitez que le calcul se concentre. Si le mappage sémantique ne s’est pas produit, sélectionnez **Modifier** et mappez vos données.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Volet latéral affichant le choix d’activités spécifiques de type sémantique.":::

1. Sélectionnez **Suivant** et vérifiez les attributs requis pour ce modèle.

1. Cliquez sur **Enregistrer**.

1. Cliquez sur **Suivant**.

### <a name="add-product-information-and-filters"></a>Ajouter des informations et filtres de produit

Parfois, seuls certains produits sont utiles ou appropriés au type de prédiction que vous créez. Utilisez les filtres de produit pour identifier un sous-ensemble de produits avec des caractéristiques spécifiques à recommander à vos clients. Le modèle utilisera tous les produits disponibles pour apprendre des modèles, mais n’utilisera que les produits correspondant au filtre de produit dans sa sortie.

1. Ajoutez votre entité de catalogue de produits qui contient des informations pour chaque produit. Mappez les informations requises et sélectionnez **Enregistrer**.

1. Cliquez sur **Suivant**.

1. Sélectionnez **Filtres de produit** :

   - **Aucun filtre** : utilisez tous les produits dans la prédiction de recommandation de produits.

   - **Définir des filtres de produit spécifiques** : utilisez des produits spécifiques dans la prédiction de recommandation de produits. Dans le volet **Attributs du catalogue de produits**, sélectionnez les attributs de votre entité de catalogue de produits que vous souhaitez inclure dans le filtre.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Volet latéral affichant les attributs de l’entité de catalogue de produits à sélectionner pour les filtres de produit.":::

1. Choisissez si vous souhaitez que le filtre de produit utilise **et** ou **ou** pour combiner logiquement votre sélection d’attributs du catalogue de produits.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Exemple de configuration de filtres de produit combinés à des connecteurs logiques AND.":::

1. Cliquez sur **Suivant**.

### <a name="set-update-schedule"></a>Définir le planning de mise à jour

1. Choisissez une fréquence pour renouveler l’entraînement de votre modèle. Ce paramètre est important pour mettre à jour la précision des prédictions lorsque de nouvelles données sont ingérées dans Customer Insights. La plupart des entreprises peuvent se réentraîner une fois par mois et obtenir une bonne précision pour leur prédiction.

1. Cliquez sur **Suivant**.

### <a name="review-and-run-the-model-configuration"></a>Examiner et exécuter la configuration du modèle

L’étape **Réviser et exécuter** affiche un résumé de la configuration et offre la possibilité d’apporter des modifications avant de créer la prédiction.

1. Sélectionnez **Modifier** dans l’une des étapes pour réviser et apporter des modifications.

1. Si vous êtes satisfait de vos sélections, sélectionnez **Enregistrer et exécuter** pour commencer à exécuter le modèle. Cliquez sur **Terminé**. L’onglet **Mes prédictions** s’affiche pendant la création de la prédiction. Le processus peut prendre plusieurs heures pour se terminer selon la quantité de données utilisées dans la prédiction.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Afficher les résultats de la prédiction

1. Accédez à **Intelligence** > **Prédictions**.

1. Dans l’onglet **Mes prédictions**, sélectionnez la prédiction que vous souhaitez afficher.

Il existe cinq sections principales de données dans la page de résultats.

- **Performances du modèle** : les notes A, B et C indiquent les performances de la prédiction et peuvent vous aider à prendre la décision d’utiliser les résultats stockés dans l’entité de sortie.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Image du résultat des performances du modèle avec la note A.":::

  Les notes sont calculées selon les règles suivantes :
  - **A** lorsque la mesure « Success @ K » est supérieure d’au moins 10 % à la valeur de référence.
  - **B** lorsque la mesure « Success @ K » est de 0 % à 10 % supérieure à la valeur de référence.
  - **C** lorsque la mesure « Success @ K » est inférieure à la valeur de référence.
  - **Valeur de référence** : produits les plus recommandés par nombre d’achats pour tous les clients + règles apprises identifiées par le modèle = un ensemble de recommandations pour les clients. Les prévisions sont ensuite comparées aux meilleurs produits, calculées par le nombre de clients ayant acheté le produit. Si un client a au moins un produit dans ses produits recommandés qui a également été vu dans les produits les plus achetés, il est considéré comme faisant partie de la base de référence. Par exemple, si 10 de ces clients avaient acheté un produit recommandé sur un total de 100 clients, la référence est de 10 %.
  - **Success @ K** : des recommandations sont créées pour tous les clients et comparées à un ensemble de périodes de validation des transactions. Par exemple, dans une période de 12 mois, le 12e mois est mis de côté comme ensemble de données de validation. Si le modèle prédit au moins une chose que vous achèteriez au cours du 12e mois en fonction de ce qu’il a appris des 11 mois précédents, le client augmentera la métrique "Success @ K".

- **Produits les plus suggérés (avec décompte) :** les cinq principaux produits qui ont été prédits pour vos clients.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Graphique montrant les 5 produits les plus recommandés.":::

- **Facteurs de recommandation clés :** le modèle utilise l’historique des transactions des clients pour faire des recommandations de produits. Il apprend des modèles basés sur les achats passés et trouve des similitudes entre les clients et les produits. Ces similitudes sont ensuite utilisées pour générer des recommandations de produits.
  Les facteurs suivants sont susceptibles d’influencer une recommandation de produits générée par le modèle.
  - **Transactions passées** : un produit recommandé était basé sur des modèles d’achat dans le passé. Par exemple, le modèle peut recommander une *Souris Arc Surface* si quelqu’un a récemment acheté un *Surface Book 3* et un *Stylet Surface*. Le modèle a appris que, historiquement, de nombreux clients avaient acheté une *Souris Arc Surface* après avoir acheté un *Surface Book 3* et un *Stylet Surface*.
  - **Similitude de clients** : historiquement, un produit recommandé a été acheté par d’autres clients qui présentent des modèles d’achat similaires. Par exemple, les *Écouteurs Surface 2* ont été recommandés à John, car Jennifer et Brad ont récemment acheté des *Écouteurs Surface 2*. Le modèle pense que John est similaire à Jennifer et Brad, car ils ont historiquement eu des modèles d’achat similaires.
  - **Similitude de produits** : un produit recommandé est similaire à d’autres produits que le client avait précédemment achetés. Le modèle considère que deux produits sont similaires s’ils ont été achetés ensemble ou par des clients similaires. Par exemple, quelqu’un reçoit une recommandation pour un *Lecteur de stockage USB*, car il a précédemment acheté un *Adaptateur USB-C vers USB* et le modèle estime que le *Lecteur de stockage USB* est similaire à l’*Adaptateur USB-C vers USB* sur la base des modèles d’achat historiques.

  Chaque recommandation de produits est influencée par un ou plusieurs de ces facteurs. Le pourcentage de recommandations dans lesquelles chaque facteur d’influence a joué un rôle est visualisé dans un graphique. Dans l’exemple suivant, 100 % des recommandations ont été influencées par les transactions passées, 60 % par la similitude de clients et 22 % par la similitude de produits. Pointez la souris sur les barres du graphique pour voir le pourcentage exact dans lequel les facteurs d’influence ont contribué.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Facteurs de recommandation clés appris par le modèle pour générer des recommandations de produits.":::

- **Statistiques de données** : description générale du nombre de transactions, de clients et de produits pris en compte par le modèle. Il est basé sur les données d’entrée utilisées pour apprendre des modèles et générer des recommandations de produits.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Statistiques de données sur les données d’entrée utilisées par le modèle pour apprendre des modèles.":::
  
  Le modèle utilise toutes les données disponibles pour apprendre des modèles. Par conséquent, si vous utilisez le filtrage de produits dans la configuration du modèle, cette section indique le nombre total de produits analysés par le modèle pour apprendre des modèles, qui peut différer du nombre de produits correspondant aux critères de filtrage définis. Le filtrage s’applique à la sortie générée par le modèle.

- **Exemples de recommandations de produits** : un échantillon de recommandations qui, selon le modèle, sont susceptibles d’être achetées par le client. Si un catalogue de produits est ajouté, les ID de produits sont remplacés par les noms de produits.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Liste présentant des suggestions hautement fiables pour un ensemble sélectionné de clients individuels.":::

> [!NOTE]
> Dans l’entité de sortie de ce modèle; *Score* indique une mesure quantitative de la recommandation. Le modèle recommande des produits avec un score plus élevé par rapport aux produits avec un score plus faible. Pour voir le score, accédez à **Données** > **Entités** et affichez l’onglet de données de l’entité de sortie que vous avez définie pour ce modèle.

[!INCLUDE [footer-include](includes/footer-banner.md)]
