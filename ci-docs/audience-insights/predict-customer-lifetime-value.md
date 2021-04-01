---
title: Prédiction de la valeur de la durée de vie du client
description: Prévoyez le potentiel de revenus des clients actifs à l’avenir.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 835a9f3371a8c1b1a10d5c6901c03e1df5379d3d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595804"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a>Prédiction de la valeur de durée de vie du client (version préliminaire)

Prévoyez la valeur potentielle (revenus) que les clients actifs individuels apporteront à votre entreprise sur une période future définie. Cette fonctionnalité peut vous aider à atteindre divers objectifs : 
- Identifier les clients à forte valeur ajoutée et traitez ces informations
- Créer des segments de clientèle stratégiques en fonction de leur valeur potentielle pour mener des campagnes personnalisées avec des efforts de vente, de marketing et de soutien ciblés
- Guider le développement de produits en se concentrant sur les fonctionnalités qui augmentent la valeur client
- Optimiser la stratégie de vente ou de marketing et allouer le budget plus précisément pour la sensibilisation des clients
- Reconnaître et récompenser les clients de grande valeur grâce à des programmes de fidélité ou de récompenses 

## <a name="prerequisites"></a>Conditions préalables

Avant de commencer, réfléchissez à ce que signifie la valeur de durée de vie du client pour votre entreprise. Actuellement, nous prenons en charge la prédiction de la valeur de durée de vie du client basée sur les transactions. La valeur prédite d’un client est basée sur l’historique des transactions commerciales. Pour créer la prédiction, vous devez au moins des autorisations des [contributeurs](permissions.md).

Étant donné que la configuration et l’exécution d’un modèle de valeur de durée de vie du client ne prennent pas beaucoup de temps, envisagez de créer plusieurs modèles avec des préférences d’entrée variables et comparez les résultats du modèle pour voir quel scénario de modèle correspond le mieux aux besoins de votre entreprise.

###  <a name="data-requirements"></a>Exigences au niveau des données

Les données suivantes sont obligatoires et, lorsqu’elles sont marquées comme facultatives, recommandées pour améliorer les performances du modèle. Plus le modèle peut traiter de données, plus la prévision sera précise. Par conséquent, nous vous encourageons à intégrer davantage de données sur l’activité des clients, le cas échéant.

- ID client : identificateur unique pour faire correspondre les transactions à un client individuel

- Historique des transactions : journal des transactions historiques avec le schéma de données sémantique ci-dessous
    - ID de transaction : identifiant unique de chaque transaction
    - Date de transaction : date, de préférence un horodatage de chaque transaction
    - Montant de la transaction : valeur monétaire (par exemple, chiffre d’affaires ou marge bénéficiaire) de chaque transaction
    - Libellé affecté aux retours (facultatif) : valeur booléenne indiquant si la transaction est un retour 
    - ID produit (facultatif) : ID produit du produit impliqué dans la transaction

- Données supplémentaires (facultatives), par exemple
    - Activités web : historique des visites du site web, historique des e-mails
    - Activités de fidélisation : historique d’accumulation et d’échange de points de fidélité
    - Journal du service clientèle, appel de service, réclamation ou historique des retours
- Données sur les activités client (facultatif) :
    - Identificateurs d’activité pour distinguer les activités du même type
    - ID client pour faire correspondre les activités à vos clients
    - Informations sur l’activité contenant le nom et la date de l’activité
    - Le schéma de données sémantique pour les activités comprend : 
        - Clé primaire : Identificateur unique pour une activité
        - Horodatage : date et heure de l’événement, identifiées par la clé primaire
        - Événement (nom de l’activité) : nom de l’événement que vous souhaitez utiliser
        - Détails (montant ou valeur) : détails sur l’activité du client

## <a name="create-a-customer-lifetime-value-prediction"></a>Créer une prédiction de la valeur de durée de vie du client

1. Dans les informations sur l’audience, accédez à **Intelligence** > **Prédictions**.

1. Sélectionnez la vignette **Valeur de la durée de vie du client** et sélectionnez **Utiliser le modèle**. 

1. Dans le volet **Valeur de la durée de vie du client (aperçu)**, sélectionnez **Démarrer**.

1. **Nommez ce modèle** et le **Nom de l’entité de sortie** pour les distinguer des autres modèles ou entités.

1. Cliquez sur **Suivant**.

### <a name="define-model-preferences"></a>Définir les préférences de modèle

1. Définissez une **Période de prédiction** pour définir à quelle distance dans le futur vous souhaitez prédire la Valeur de la durée de vie du client.    
   Par défaut, l’unité est définie sur les mois. Vous pouvez le changer en années pour regarder plus loin dans le futur.

   > [!TIP]
   > Pour prédire avec précision la Valeur de la durée de vie du client pour la période que vous avez définie, vous avez besoin d’une période comparable de données historiques. Par exemple, si vous souhaitez prévoir pour les 12 prochains mois, il est recommandé de disposer d’au moins 18 à 24 mois de données historiques.

1. Précisez ce que **Clients actifs** signifie pour votre entreprise. Définissez le délai d’exécution dans lequel un client doit avoir eu au moins une transaction pour être considéré comme actif. Le modèle ne prédira la Valeur de la durée de vie du client que pour les clients actifs. 
   - **Laisser le modèle calculer l’intervalle d’achat (recommandé)**  : Le modèle analyse vos données et détermine une période en fonction de l’historique des achats.
   - **Définir manuellement l’intervalle** : Si vous avez une définition commerciale spécifique d’un client actif, choisissez cette option et définissez la période en conséquence.

1. Définissez le centile de **Client à forte valeur ajoutée** pour permettre au modèle de fournir des résultats qui correspondent à la définition de votre entreprise.
    - **Calcul du modèle (recommandé)**  : Le modèle analyse vos données et détermine ce que pourrait être un client à forte valeur ajoutée pour votre entreprise en fonction de l’historique des transactions de vos clients. Le modèle utilise une règle heuristique (inspirée de la règle 80/20 ou du principe de pareto) pour trouver la proportion de clients à forte valeur ajoutée. Le pourcentage de clients ayant contribué à 80 % des revenus cumulés de votre entreprise au cours de la période historique est considéré comme des clients à forte valeur ajoutée. En règle générale, moins de 30 % à 40 % des clients contribuent à 80 % des revenus cumulés. Cependant, ce nombre peut varier en fonction de votre entreprise et de votre secteur d’activité.    
    - **Pourcentage des principaux clients actifs** : Définissez les clients à forte valeur ajoutée pour votre entreprise en tant que centile des principaux clients payants actifs. Par exemple, vous pouvez utiliser cette option pour définir les clients à forte valeur comme 20 % des futurs clients payants.

    Si votre entreprise définit les clients à forte valeur ajoutée d’une manière différente, [donnez-vous votre avis, car nous aimerions le savoir](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Sélectionnez **Suivant** et passez à l’étape suivante.

### <a name="add-required-data"></a>Ajouter les données requises

1. Dans l’étape **Données requises**, sélectionnez **Ajouter des données** pour **Historique des transactions client** et choisissez l’entité qui fournit les informations sur l’historique des transactions comme décrit dans les [conditions préalables](#prerequisites).

1. Mappez les champs sémantiques aux attributs de votre entité d’historique des achats et sélectionnez **Suivant**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Image de l’étape de configuration pour mapper les attributs de données pour les données requises.":::
 
1. Si les champs ci-dessous ne sont pas renseignés, configurez la relation entre votre entité d’historique des achats et l’entité *Client* et sélectionnez **Enregistrer**.
    1. Sélectionnez l’Entité d’historique des transactions.
    1. Sélectionnez le champ qui identifie un client dans l’entité d’historique des achats. Il doit être lié à l’ID client principal de votre entité client.
    1. Sélectionnez l’entité qui correspond à votre entité de client principale.
    1. Entrez un nom qui décrit la relation.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Image de l’étape de configuration pour définir la relation avec l’entité client.":::

1. Cliquez sur **Suivant**.

### <a name="add-optional-data"></a>Ajouter des données facultatives

Les données reflétant les interactions client clés (comme le web, le service clientèle et les journaux d’événements) ajoutent du contexte aux enregistrements de transaction. Plus de modèles trouvés dans vos données d’activité client peuvent améliorer la précision des prévisions. 

1. Dans l’étape **Données supplémentaires (facultatif)**, sélectionnez **Ajouter des données**. Choisissez l’activité client qui fournit les informations sur les activités client comme décrit dans les [conditions préalables](#prerequisites).

1. Mappez les champs sémantiques aux attributs de votre entité d’activités client et sélectionnez **Suivant**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Image de l’étape de configuration pour mapper les champs pour des données supplémentaires.":::

1. Sélectionnez un type d’activité qui correspond au type d’activité client que vous ajoutez. Choisissez parmi les types d’activité existants ou ajoutez un nouveau type d’activité.

1. Configurez la relation entre votre entité d’activité client et l’entité *Client*.
    
    1. Sélectionnez le champ qui identifie le client dans la table des activités client. Il peut être directement lié à l’ID client principal de votre entité *Client*.
    1. Sélectionnez l’entité *Client* qui correspond à votre entité *Client* principale.
    1. Entrez un nom qui décrit la relation.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Image de l’étape dans le flux de configuration pour ajouter des données supplémentaires et configurer l’activité avec des exemples remplis.":::

1. Sélectionnez **Enregistrer**.    
    Ajoutez plus de données si vous souhaitez inclure d’autres activités client.

1. Cliquez sur **Suivant**.

### <a name="set-update-schedule"></a>Définir le planning de mise à jour

1. Dans l’étape **Calendrier de mise à jour des données**, choisissez la fréquence de renouvellement de l’entraînement de votre modèle en fonction des dernières données. Ce paramètre est important pour mettre à jour la précision des prédictions lorsque de nouvelles données sont ingérées dans les informations sur l’audience. La plupart des entreprises peuvent se réentraîner une fois par mois et obtenir une bonne précision pour leur prédiction.

1. Cliquez sur **Suivant**.


### <a name="review-and-run-the-model-configuration"></a>Examiner et exécuter la configuration du modèle

1. Dans l’étape **Vérifier les détails de votre modèle**, validez la configuration du prédiction. Vous pouvez revenir à n’importe quelle partie de la configuration de prédiction en sélectionnant **Modifier** sous la valeur indiquée. Vous pouvez également sélectionner une étape de configuration à partir de l’indicateur de progression.

1. Si toutes les valeurs sont correctement configurées, sélectionnez **Enregistrer et exécuter** pour commencer à exécuter le modèle. Sur l’onglet **Mes prédictions**, vous pouvez voir le statut du processus de prédiction. Le processus peut prendre plusieurs heures pour se terminer selon la quantité de données utilisées dans la prédiction.

## <a name="review-prediction-status-and-results"></a>Examiner le statut et les résultats des prédictions

### <a name="review-prediction-status"></a>Revoir le statut de la prédiction

1.  Accédez à **Intelligence** > **Prédictions** et sélectionnez l’onglet **Mes prédictions**.
2.  Sélectionnez la prédiction à réviser.

- **Nom de la prédiction :** Nom de la prédiction fournie lors de sa création.
- **Type de prédiction :** Type de modèle utilisé pour la prédiction
- **Entité de sortie** : Nom de l’entité destinée à stocker la sortie de la prédiction. Aller à **Données** > **Entités** pour trouver l’entité avec ce nom.
- **Champ prédit :** Ce champ n’est renseigné que pour certains types de prédictions et n’est pas utilisé dans la prédiction de la valeur de la durée de vie du client.
- **Statut :** Statut de l’exécution de la prédiction.
    - **Mis en file d’attente :** La prédiction attend l’achèvement des autres processus.
    - **Actualisation en cours :** La prédiction est en cours d’exécution pour créer des résultats qui seront envoyés vers l’entité de sortie.
    - **Échec :** L’exécution de la prédiction a échoué. [Consultez les journaux](#troubleshoot-a-failed-prediction) pour plus de détails.
    - **Réussite :** La prédiction a réussi. Sélectionnez **Afficher** sous les points de suspension verticaux pour consulter les résultats de prédiction.
- **Modifié :** Date de modification de la configuration de la prédiction.
- **Dernière actualisation :** Date d’actualisation de la prédiction dans l’entité en sortie.


### <a name="review-prediction-results"></a>Revoir les résultats de la prédiction

1. Accédez à **Intelligence** > **Prédictions** et sélectionnez l’onglet **Mes prédictions**.

1. Sélectionnez le prédiction pour lequel vous souhaitez consulter les résultats.

La page de résultats comporte trois sections principales de données.

- **Performance du modèle d’entraînement** : A, B ou C sont des notes possibles. Cette note indique les performances du prédiction et peut vous aider à prendre la décision d’utiliser les résultats stockés dans l’entité de sortie. Sélectionnez **En savoir plus sur ce score** pour mieux comprendre les mesures de performance du modèle sous-jacent et comment la note de performance finale du modèle a été obtenue.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Image de la zone d’informations du score du modèle avec la note A.":::

  À l’aide de la définition des clients à forte valeur ajoutée fournie lors de la configuration de prédiction, le système évalue les performances du modèle IA pour prédire les clients à forte valeur ajoutée par rapport à un modèle de base.    

  Les notes sont calculées selon les règles suivantes :
  - A lorsque le modèle a prédit avec précision au moins 5 % de clients à forte valeur ajoutée en plus par rapport au modèle de référence.
  - B lorsque le modèle a prédit avec précision entre 0 % et 5 % de clients à forte valeur ajoutée en plus par rapport au modèle de référence.
  - C lorsque le modèle a prédit avec précision moins de clients à forte valeur ajoutée en plus par rapport au modèle de référence.

  Le volet **Évaluation du modèle** affiche des détails supplémentaires sur les performances du modèle IA et le modèle de base. Le modèle de base utilise une approche non basée sur l’IA pour calculer la valeur de la durée de vie du client en se basant principalement sur les achats historiques effectués par les clients.     
  Formule standard utilisée pour calculer la valeur de la durée de vie du client par le modèle de référence :    

  *Valeur de la durée de vie du client pour chaque client = Achat mensuel moyen effectué par le client dans la fenêtre client actif x Nombre de mois dans la période de prédiction de la valeur de la durée de vie du client x Taux de rétention global de tous les clients*

  Le modèle IA est comparé au modèle de base sur la base de deux mesures de performance du modèle.
  
  - **Taux de réussite de la prédiction des clients à forte valeur ajoutée**

    Voyez la différence entre la prévision des clients à forte valeur ajoutée à l’aide du modèle IA et le modèle de référence. Par exemple, un taux de réussite de 84 % signifie que sur tous les clients à forte valeur ajoutée dans les données d’entraînement, le modèle IA a pu capturer avec une précision 84 %. Nous comparons ensuite ce taux de réussite avec le taux de réussite du modèle de référence pour rendre compte du changement relatif. Cette valeur est utilisée pour attribuer une note au modèle.

  - **Mesures d’erreur**
    
    Une autre métrique vous permet d’examiner les performances globales du modèle en termes d’erreur de prédiction des valeurs futures. Nous utilisons la métrique globale de l’erreur quadratique moyenne (RMSE) pour évaluer cette erreur. La RMSE est un moyen standard de mesurer l’erreur d’un modèle dans la prédiction de données quantitatives. La RMSE du modèle IA est comparée à la RMSE du modèle de base et la différence relative est rapportée.

  Le modèle IA donne la priorité au classement précis des clients en fonction de la valeur qu’ils apportent à votre entreprise. Ainsi, seul le taux de réussite de la prédiction des clients à forte valeur ajoutée est utilisé pour calculer la note finale du modèle. La métrique RMSE est sensible aux valeurs aberrantes. Dans les scénarios où vous avez un petit pourcentage de clients avec des valeurs d’achat extrêmement élevées, la métrique RMSE globale peut ne pas donner une image complète des performances du modèle.   

- **Valeur des clients par centile** : En utilisant votre définition de clients à forte valeur ajoutée, les clients sont regroupés en clients à faible et à forte valeur ajoutée, en fonction de leurs prédictions de valeur de la durée de vie du client, et affichés dans un graphique. En survolant les barres de l’histogramme, vous pouvez voir le nombre de clients dans chaque groupe et la valeur de la durée de vie du client moyenne de ce groupe. Ces données peuvent vous aider si vous souhaitez [créer des segments de clients](segments.md) sur la base de leurs prévisions de valeur de la durée de vie du client.

- **Facteurs les plus influents** : Différents facteurs sont pris en compte lors de la création de votre prédiction de valeur de la durée de vie du client en fonction des données d’entrée fournies au modèle IA. Chacun de ces facteurs a son importance calculée pour les prévisions agrégées qu’un modèle crée. Vous pouvez utiliser ces facteurs pour valider les résultats de votre prédiction. Ces facteurs permettent également de mieux comprendre les facteurs les plus influents qui ont contribué à prédire la valeur de la durée de vie du client pour tous vos clients.

## <a name="refresh-a-prediction"></a>Actualiser une prédiction

Les prédictions s’actualisent automatiquement sur le même [Planning des actualisations de vos données](system.md#schedule-tab) tel que configuré dans les paramètres. Vous pouvez également les actualiser manuellement.

1. Accédez à **Intelligence** > **Prédictions** et sélectionnez l’onglet **Mes prédictions**.
2. Sélectionnez les ellipses verticales à côté de la prédiction que vous souhaitez actualiser.
3. Cliquez sur **Actualiser**.

## <a name="delete-a-prediction"></a>Supprimer une prédiction

La suppression d’une prédiction entraîne également la suppression de son entité de sortie.

1. Accédez à **Intelligence** > **Prédictions** et sélectionnez l’onglet **Mes prédictions**.
2. Sélectionnez les ellipses verticales à côté de la prédiction que vous souhaitez supprimer.
3. Sélectionnez **Supprimer**.

## <a name="troubleshoot-a-failed-prediction"></a>Résoudre les problèmes liés à un échec de prédiction

1. Accédez à **Intelligence** > **Prédictions** et sélectionnez l’onglet **Mes prédictions**.
2. Sélectionnez les points de suspension verticaux en regard de la prédiction pour laquelle vous souhaitez afficher les journaux d’erreurs.
3. Sélectionnez **Journaux**.
4. Passez toutes les erreurs en revue. Plusieurs types d’erreurs peuvent survenir et décrivent la condition à l’origine de l’erreur. Par exemple, une erreur indiquant qu’il n’y a pas assez de données pour des prédictions précises est généralement résolue en chargeant des données supplémentaires dans les informations sur l’audience.


[!INCLUDE[footer-include](../includes/footer-banner.md)]