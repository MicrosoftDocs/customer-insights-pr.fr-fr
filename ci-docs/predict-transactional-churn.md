---
title: Prédiction de l’attrition des transactions (contient une vidéo)
description: Prédisez si un client risque de ne plus acheter vos produits ou services.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610509"
---
# <a name="predict-transaction-churn"></a>Prédire l’attrition des transactions

La prédiction de l’attrition transactionnelle aide à prédire si un client n’achètera plus vos produits ou services sur une période donnée.

Vous devez avoir des connaissances des affaires pour comprendre ce que le désabonnement signifie pour votre entreprise. Nous prenons en charge les définitions de l’attrition basées sur le temps, ce qui signifie qu’un client est considéré comme perdu après une période sans achats.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Pour les environnements basés sur des comptes d’entreprise, nous pouvons prédire l’attrition transactionnelle pour un compte et également une combinaison de compte et d’un autre niveau d’informations, comme la catégorie de produit. Par exemple, l’ajout d’une dimension peut aider à déterminer la probabilité que le compte « Contoso » cesse d’acheter la catégorie de produits « articles de bureau ». En outre, pour les comptes professionnels, nous pouvons également utiliser l’IA pour générer une liste de raisons potentielles pour lesquelles un compte est susceptible d’abandonner une catégorie d’informations de niveau secondaire.

> [!TIP]
> Essayez la prédiction de l’attrition des transactions en utilisant des exemples de données : [Exemple de guide de prédiction de l’attrition des transactions](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Conditions préalables

- Au moins des [autorisations contributeur](permissions.md).
- Au moins 10 profils client, de préférence plus de 1 000 clients uniques.
- ID client, identificateur unique pour faire correspondre les transactions à vos clients.
- Données de transaction pour au moins le double de la période de temps sélectionnée, par exemple deux à trois ans d’historique des transactions. Dans l’idéal, au moins deux transactions par client. L’historique des transactions doit inclure :
  - **ID de transaction** : identificateur unique d’un achat ou d’une transaction.
  - **Date de la transaction** : date de l’achat ou de la transaction.
  - **Valeur de la transaction** : montant de la devise ou de la valeur numérique de la transaction.
  - **ID de produit unique** : ID du produit ou service acheté si vos données se trouvent au niveau d’un élément de ligne.
  - **Indique si cette transaction était un retour** : champ vrai/faux qui identifie si la transaction était un retour ou non. Si la **Valeur de la transaction** est négative, nous en déduisons un retour.
- Données d’activité du client :
  - ID client, identificateur unique pour mapper les activités à vos clients.
  - **Clé primaire :** identificateur unique d’une activité. Par exemple, une visite du site web ou un enregistrement d’utilisation montrant que le client a essayé un échantillon de votre produit.
  - **Horodateur :** date et heure de l’événement identifié par la clé primaire.
  - **Événement :** nom de l’événement que vous souhaitez utiliser. Par exemple, un champ appelé « UserAction » dans une épicerie peut être un coupon utilisé par le client.
  - **Détails :** Informations détaillées sur l’événement. Par exemple, un champ appelé « CouponValue » dans une épicerie peut être la valeur monétaire du coupon.
- Moins de 20 % des valeurs manquantes dans le champ de données de l’entité fournie

Pour les comptes professionnels (B2B), ajoutez des données client alignées sur des attributs plus statiques pour vous assurer que le modèle fonctionne de manière optimale :
- **CustomerID :** identificateur unique d’un client.
- **Date de création :** date à laquelle le client a été initialement ajouté.
- **État ou province :** état ou province d’un client.
- **Pays :** pays d’un client.
- **Secteur d’activité :** type de secteur d’activité d’un client. Par exemple, un champ intitulé « Secteur d’activité » dans un torréfacteur peut indiquer si le client était un détaillant.
- **Classification :** catégorisation d’un client pour votre entreprise. Par exemple, un champ appelé « ValueSegment » dans un torréfacteur peut être le niveau du client en fonction de la taille du client.

> [!NOTE]
> Pour une entreprise avec une fréquence d’achat élevée des clients (toutes les semaines), il est recommandé de sélectionner une période de prédiction plus courte et une définition d’attrition. Pour une faible fréquence d’achat (tous les mois ou une fois par an), choisissez une période de prédiction plus longue et une définition d’attrition.

## <a name="create-a-transaction-churn-prediction"></a>Créer une prédiction d’attrition des transactions

1. Accédez à **Intelligence** > **Prédictions**.

1. Dans l’onglet **Créer**, sélectionnez **Utiliser le modèle** dans la vignette **Modèle d’attrition clients**.

1. Sélectionnez **Transaction** pour le type d’attrition, puis **Démarrer**.

1. **Nommez ce modèle** et le **Nom de l’entité de sortie** pour les distinguer des autres modèles ou entités.

1. Cliquez sur **Suivant**.

### <a name="define-customer-churn"></a>Définir l’attrition client

Sélectionnez **Enregistrer le brouillon** à tout moment pour enregistrer la prédiction en tant que brouillon. Le brouillon de prédiction s’affiche dans l’onglet **Mes prédictions**.

1. Définissez la **Fenêtre de prédiction**. Par exemple, prédisez le risque d’attrition de vos clients au cours des 90 prochains jours pour vous aligner sur vos efforts de fidélisation avec le marketing. Prédire le risque d’attrition sur une période plus ou moins longue peut rendre plus difficile de prendre en compte les facteurs de votre profil de risque d’attrition, mais cela dépend des besoins spécifiques à votre entreprise.

1. Saisissez le nombre de jours pour définir l’attrition dans le champ **Définition de l’attrition**. Par exemple, si un client n’a pas effectué d’achat au cours des 30 derniers jours, il peut être considéré comme perdu pour votre entreprise.

1. Cliquez sur **Suivant**.

### <a name="add-purchase-history"></a>Ajouter l’historique d’achat

1. Sélectionnez **Ajouter des données** pour **Historique des transactions client**.

1. Sélectionnez le type d’activité sémantique, **SalesOrder** ou **SalesOrderLine**, qui contient les informations sur l’historique des transactions. Si l’activité n’a pas été configurée, sélectionnez **ici** et créez-la.

1. Sous **Activités**, si les attributs d’activité ont été mappés sémantiquement lors de la création de l’activité, choisissez l’entité ou les attributs spécifiques sur lesquels vous souhaitez que le calcul se concentre. Si le mappage sémantique ne s’est pas produit, sélectionnez **Modifier** et mappez vos données.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Volet latéral affichant le choix d’activités spécifiques de type sémantique.":::

1. Sélectionnez **Suivant** et vérifiez les attributs requis pour ce modèle.

1. Cliquez sur **Enregistrer**.

1. Ajoutez d’autres activités ou sélectionnez **Suivant**.

# <a name="individual-consumers-b-to-c"></a>[Consommateurs individuels (B-to-C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Ajouter des données supplémentaires (facultatif)

1. Sélectionnez **Ajouter des données** pour **Activités client**.

1. Sélectionnez le type d’activité sémantique contenant les données que vous souhaitez utiliser. Si l’activité n’a pas été configurée, sélectionnez **ici** et créez-la.

1. Sous **Activités**, si les attributs d’activité ont été mappés sémantiquement lors de la création de l’activité, choisissez l’entité ou les attributs spécifiques sur lesquels vous souhaitez que le calcul se concentre. Si le mappage sémantique ne s’est pas produit, sélectionnez **Modifier** et mappez vos données.

1. Sélectionnez **Suivant** et vérifiez les attributs requis pour ce modèle.

1. Cliquez sur **Enregistrer**.

1. Sélectionnez **Suivant**.

# <a name="business-accounts-b-to-b"></a>[Comptes d’entreprise (B-to-B)](#tab/b2b)

### <a name="select-prediction-level"></a>Sélectionner le niveau de prédiction

La plupart des prédictions sont créées au niveau du client. Dans certaines situations, cela peut ne pas être suffisamment granulaire pour répondre aux besoins de votre entreprise. Utilisez cette fonctionnalité pour prédire l’attrition pour une succursale d’un client par exemple, plutôt que pour le client dans son ensemble.

1. Sélectionnez **Sélectionner une entité pour un niveau secondaire**. Si l’option n’est pas disponible, assurez-vous d’avoir rempli la section précédente.

1. Développez les entités à partir desquelles vous souhaitez choisir le niveau secondaire ou utilisez la zone de filtre de recherche pour filtrer les options sélectionnées.

1. Choisissez l’attribut que vous souhaitez utiliser comme niveau secondaire, puis sélectionnez **Ajouter**

1. Sélectionnez **Suivant**.

> [!NOTE]
> Les entités disponibles dans cette section sont affichées car elles ont une relation avec l’entité que vous avez choisie dans la section précédente. Si vous ne voyez pas l’entité que vous souhaitez ajouter, assurez-vous qu’elle a une relation valide présente dans **Relations**. Seuls les types de relation un-à-un et plusieurs-à-un sont valides pour cette configuration.

### <a name="add-additional-data-optional"></a>Ajouter des données supplémentaires (facultatif)

1. Sélectionnez **Ajouter des données** pour **Activités client**.

1. Sélectionnez le type d’activité sémantique contenant les données que vous souhaitez utiliser. Si l’activité n’a pas été configurée, sélectionnez **ici** et créez-la.

1. Sous **Activités**, si les attributs d’activité ont été mappés sémantiquement lors de la création de l’activité, choisissez l’entité ou les attributs spécifiques sur lesquels vous souhaitez que le calcul se concentre. Si le mappage sémantique ne s’est pas produit, sélectionnez **Modifier** et mappez vos données.

1. Sélectionnez **Suivant** et vérifiez les attributs requis pour ce modèle.

1. Cliquez sur **Enregistrer**.

1. Sélectionnez **Suivant**.

1. En option, sélectionnez **Ajouter des données** pour **Données clients**.

1. Mappez les attributs sémantiques aux champs de vos propres données client telles qu’identifiées. Les données des champs utilisés ne doivent pas changer souvent pour garantir les meilleures performances du modèle. Par exemple, la sélection d’un champ pour « Classification », qui changeait tous les mois, n’aurait que la dernière valeur utilisée dans le prédiction, même si, historiquement, la même valeur peut ne pas s’appliquer au client lors de la création des modèles de prédiction.

1. Sélectionnez **Suivant**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Fournir une liste facultative de comptes de référence

Ajoutez une liste de vos clients et comptes professionnels que vous souhaitez utiliser comme références. Les [détails de ces comptes de référence](#view-prediction-results)comprennent leur score d’attrition et les fonctionnalités les plus influentes qui ont eu un impact sur la prédiction de leur attrition.

1. Sélectionnez **+ Ajouter des clients**.

1. Choisissez les clients qui servent de référence.

1. Cliquez sur **Suivant**.

---

### <a name="set-update-schedule"></a>Définir le planning de mise à jour

1. Pour l’étape **Mises à jour des données**, choisissez une fréquence pour renouveler l’entraînement de votre modèle. Ce paramètre est important pour mettre à jour la précision des prédictions lorsque de nouvelles données sont ingérées dans Customer Insights. La plupart des entreprises peuvent se réentraîner une fois par mois et obtenir une bonne précision pour leur prédiction.

1. Cliquez sur **Suivant**.

### <a name="review-and-run-the-model-configuration"></a>Examiner et exécuter la configuration du modèle

L’étape **Réviser et exécuter** affiche un résumé de la configuration et offre la possibilité d’apporter des modifications avant de créer la prédiction.

1. Sélectionnez **Modifier** dans l’une des étapes pour réviser et apporter des modifications.

1. Si vous êtes satisfait de vos sélections, sélectionnez **Enregistrer et exécuter** pour commencer à exécuter le modèle. Cliquez sur **Terminé**. L’onglet **Mes prédictions** s’affiche pendant la création de la prédiction. Le processus peut prendre plusieurs heures pour se terminer selon la quantité de données utilisées dans la prédiction.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Afficher les résultats de la prédiction

1. Accédez à **Intelligence** > **Prédictions**.

1. Dans l’onglet **Mes prédictions**, sélectionnez la prédiction que vous souhaitez afficher.

# <a name="individual-consumers-b-to-c"></a>[Consommateurs individuels (B-to-C)](#tab/b2c)

La page de résultats comporte trois sections principales de données :

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Comptes d’entreprise (B-to-B)](#tab/b2b)

La page de résultats comporte trois sections principales de données :

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Une page d’informations **Analyse des fonctionnalités influentes** contient quatre sections de données :

- Dans le volet droit, sélectionnez un élément dans **Meilleurs clients** ou **Clients de référence**. Les deux listes sont classées par valeur décroissante du score d’attrition, que le score soit uniquement pour le client ou un score combiné pour les clients et un niveau secondaire comme une catégorie de produits. L’élément sélectionné détermine le contenu de cette page.

  - **Meilleurs clients** : Liste de 10 clients qui présentent le risque le plus élevé d’attrition et le risque le plus faible en fonction de leurs scores d’attrition.
  - **Clients de référence** : Liste contenant jusqu’à 10 clients qui ont été sélectionnés lors de la configuration du modèle.

- **Score d’attrition :** Affiche le score d’attrition de l’élément sélectionné dans le volet de droite.

- **Répartition du score d’attrition :** affiche la répartition du risque d’attrition entre les clients et le centile dans lequel se trouve le client sélectionné.

- **Principales fonctionnalités augmentant et diminuant le risque d’attrition :** répertorie les cinq principales fonctionnalités qui ont augmenté et diminué le risque d’attrition pour l’élément sélectionné dans le volet de droite. Affiche la valeur de la fonctionnalité pour cet élément et son influence sur le score d’attrition pour chaque fonctionnalité influente. La valeur moyenne de chaque fonctionnalité sur les segments client d’attrition faible, moyen et élevé est également affichée. Cela permet de mieux contextualiser les valeurs des caractéristiques les plus influentes pour l’élément sélectionné et de les comparer aux segments client d’attrition faible, moyen et élevé.

  - Faible : comptes ou combinaisons de comptes et de niveau secondaire avec un score d’attrition compris entre 0 et 0,33.
  - Moyen : comptes ou combinaisons de comptes et de niveaux secondaires avec un score d’attrition compris entre 0,33 et 0,66.
  - Élevé : comptes ou combinaisons de comptes et de niveaux secondaires avec un score d’attrition supérieur à 0,66.

  Lorsque vous prédisez l’attrition au niveau du compte, tous les comptes sont pris en compte dans la dérivation des valeurs de fonctionnalités moyennes pour les segments d’attrition. Pour les prédictions d’attrition au niveau secondaire pour chaque compte, la dérivation des segments d’attrition dépend du niveau secondaire de l’élément sélectionné dans le volet latéral. Par exemple, si un élément a un niveau secondaire de catégorie de produits (fournitures de bureau), seuls les éléments ayant des fournitures de bureau comme catégorie de produits sont pris en compte lors de la dérivation des valeurs de fonctionnalités moyennes pour les segments d’attrition. Cette logique est appliquée pour garantir une comparaison équitable des valeurs des fonctionnalités de l’éléments avec les valeurs moyennes sur les segments d’attrition faible, moyen et élevé.

  Dans certains cas, la valeur moyenne des segments d’attrition faible, moyen ou élevé est vide ou n’est pas disponible car aucun élément n’appartient aux segments d’attrition correspondants sur la base de la définition ci-dessus.

  L’interprétation des valeurs des colonnes faible, moyen, élevé habituelles est différente pour les caractéristiques catégoriques telles que le pays ou le secteur. Étant donné que la notion de valeur de caractéristique « moyenne » ne s’applique pas aux caractéristiques catégoriques, les valeurs de ces colonnes sont la proportion de clients dans les segments à taux de désabonnement faible, moyen ou élevé qui ont la même valeur pour la caractéristique catégorique par rapport à l’article sélectionné dans le panneau latéral.

---

 > [!NOTE]
 > Dans l’entité de sortie de ce modèle, *ChurnScore* indique la probabilité prédite d’attrition et *IsChurn* est une étiquette binaire basée sur *ChurnScore* avec un seuil de 0,5. Si ce seuil par défaut ne fonctionne pas pour votre scénario, [créez un nouveau segment](segments.md#create-a-segment) avec votre seuil préféré. Tous les clients ne sont pas nécessairement des clients actifs. Certains d’entre eux n’ont peut-être pas eu d’activité pendant un certain temps et sont déjà considérés comme perdus, selon votre définition d’attrition. Prédire le risque d’attrition pour les clients qui ont déjà abandonné n’est pas utile car ils ne sont pas l’audience d’intérêt.
>
> Pour voir le score d’attrition, accédez à **Données** > **Entités** et affichez l’onglet de données de l’entité de sortie que vous avez définie pour ce modèle.

[!INCLUDE [footer-include](includes/footer-banner.md)]
