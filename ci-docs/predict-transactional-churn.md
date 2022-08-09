---
title: Prédiction de l’attrition des transactions (contient une vidéo)
description: Prédisez si un client risque de ne plus acheter vos produits ou services.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b8216b5a739964fdfff8cad7e6d6d7ce3f5308b5
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171092"
---
# <a name="transaction-churn-prediction"></a>Prédiction de l’attrition des transactions

La prédiction de l’attrition transactionnelle aide à prédire si un client n’achètera plus vos produits ou services sur une période donnée. Vous pouvez créer de nouvelles prédictions de l’attrition en cliquant sur **Intelligence** > **Prédictions**. Sélectionnez **Mes prédictions** pour voir les autres prédictions que vous avez créées. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Pour les environnements basés sur des comptes d’entreprise, nous pouvons prédire l’attrition transactionnelle pour un compte et également une combinaison de compte et d’un autre niveau d’informations, comme la catégorie de produit. L’ajout d’une dimension peut aider à déterminer la probabilité que le compte « Contoso » cesse d’acheter la catégorie de produits « articles de bureau ». En outre, pour les comptes professionnels, nous pouvons également utiliser l’IA pour générer une liste de raisons potentielles pour lesquelles un compte est susceptible d’abandonner une catégorie d’informations de niveau secondaire.

> [!TIP]
> Essayez le didacticiel pour une prédiction de l’attrition des transactions à l’aide d’exemples de données : [Exemple de guide de prédiction de l’attrition des transactions](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Conditions préalables

# <a name="individual-consumers-b-to-c"></a>[Consommateurs individuels (B-to-C)](#tab/b2c)

- Au minimum [Autorisations collaborateur](permissions.md) dans Customer Insights.
- Connaissance des affaires pour comprendre ce que le désabonnement signifie pour votre entreprise. Nous prenons en charge les définitions de l’attrition basées sur le temps, ce qui signifie qu’un client est considéré comme perdu après une période sans achats.
- Données sur vos transactions/achats et leur historique :
    - Identificateurs de transaction pour distinguer les achats/transactions.
    - Identificateurs client pour faire correspondre les transactions à vos clients.
    - Dates des événements de transaction, qui définissent les dates de la transaction.
    - Le schéma de données sémantique pour les achats/transactions nécessite les informations suivantes :
        - **ID de transaction** : identifiant unique d’un achat ou d’une transaction.
        - **Date de la transaction** : date de l’achat ou de la transaction.
        - **Valeur de la transaction** : montant de la valeur monétaire/numérique de la transaction/de l’article.
        - (Facultatif) **ID de produit unique** : ID du produit ou service acheté si vos données se trouvent au niveau d’un élément de ligne.
        - (Facultatif) **Indique si cette transaction était un retour** : champ vrai/faux qui identifie si la transaction était un retour ou non. Si la **Valeur de la transaction** est négative, nous utiliserons également ces informations pour déduire un retour.
- (Facultatif) Données sur les activités client :
    - Identificateurs d’activité pour distinguer les activités du même type.
    - Identifiants client pour faire correspondre les activités à vos clients.
    - Informations sur l’activité contenant le nom et la date de l’activité.
    - Le schéma de données sémantique pour les activités client comprend :
        - **Clé primaire :** Identifiant unique pour une activité. Par exemple, une visite du site web ou un enregistrement d’utilisation montrant que le client a essayé un échantillon de votre produit.
        - **Horodatage :** Date et heure de l’événement identifiées par la clé primaire.
        - **Événement :** Nom de l’événement que vous souhaitez utiliser. Par exemple, un champ appelé « UserAction » dans une épicerie peut être un coupon utilisé par le client.
        - **Détails :** Informations détaillées sur l’événement. Par exemple, un champ appelé « CouponValue » dans une épicerie peut être la valeur monétaire du coupon.

# <a name="business-accounts-b-to-b"></a>[Comptes d’entreprise (B-to-B)](#tab/b2b)

- Au minimum [Autorisations collaborateur](permissions.md) dans Customer Insights.
- Connaissance des affaires pour comprendre ce que le désabonnement signifie pour votre entreprise. Nous prenons en charge les définitions de l’attrition basées sur le temps, ce qui signifie qu’un client est considéré comme perdu après une période sans achats.
- Données sur vos transactions/achats et leur historique :
    - Identificateurs de transaction pour distinguer les achats/transactions.
    - Identificateurs client pour faire correspondre les transactions à vos clients.
    - Dates des événements de transaction, qui définissent les dates de la transaction.
    - Le schéma de données sémantique pour les achats/transactions nécessite les informations suivantes :
        - **ID de transaction** : identifiant unique d’un achat ou d’une transaction.
        - **Date de la transaction** : date de l’achat ou de la transaction.
        - **Valeur de la transaction** : montant de la valeur monétaire/numérique de la transaction/de l’article.
        - (Facultatif) **ID de produit unique** : ID du produit ou service acheté si vos données se trouvent au niveau d’un élément de ligne.
        - (Facultatif) **Indique si cette transaction était un retour** : champ vrai/faux qui identifie si la transaction était un retour ou non. Si la **Valeur de la transaction** est négative, nous utiliserons également ces informations pour déduire un retour.
- (Facultatif) Données sur les activités client :
    - Identificateurs d’activité pour distinguer les activités du même type.
    - Identifiants client pour faire correspondre les activités à vos clients.
    - Informations sur l’activité contenant le nom et la date de l’activité.
    - Le schéma de données sémantique pour les activités client comprend :
        - **Clé primaire :** Identifiant unique pour une activité. Par exemple, une visite du site web ou un enregistrement d’utilisation montrant que le client a essayé un échantillon de votre produit.
        - **Horodatage :** Date et heure de l’événement identifiées par la clé primaire.
        - **Événement :** Nom de l’événement que vous souhaitez utiliser. Par exemple, un champ appelé « UserAction » dans une épicerie peut être un coupon utilisé par le client.
        - **Détails :** Informations détaillées sur l’événement. Par exemple, un champ appelé « CouponValue » dans une épicerie peut être la valeur monétaire du coupon.
- (Facultatif) Données sur vos clients :
    - Ces données doivent s’aligner sur des attributs plus statiques pour garantir que le modèle fonctionne au mieux.
    - Le schéma de données sémantiques pour les données client comprend :
        - **CustomerID :** identificateur unique d’un client.
        - **Date de création :** date à laquelle le client a été initialement ajouté.
        - **État ou province :** état ou province d’un client.
        - **Pays :** pays d’un client.
        - **Secteur d’activité :** type d’industrie d’un client. Par exemple, un champ intitulé « Secteur d’activité » dans un torréfacteur peut indiquer si le client était un détaillant.
        - **Classification :** catégorisation d’un client pour votre entreprise. Par exemple, un champ appelé « ValueSegment » dans un torréfacteur peut être le niveau du client en fonction de la taille du client.

---

- Caractéristiques des données suggérées :
    - Données historiques suffisantes : données de transaction pour au moins le double de la période de temps sélectionnée. De préférence, deux à trois ans d’historique des transactions. 
    - Achats multiples par client : dans l’idéal, au moins deux transactions par client.
    - Nombre de clients : au moins 10 profils client, de préférence plus de 1 000 clients uniques. Le modèle échouera s’il y a moins de 10 clients et des données historiques insuffisantes.
    - Intégrité des données : moins de 20 % des valeurs manquantes dans le champ de données de l’entité fournie.

> [!NOTE]
> Pour une entreprise avec une fréquence d’achat élevée des clients (toutes les semaines), il est recommandé de sélectionner une période de prédiction plus courte et une définition d’attrition. Pour une faible fréquence d’achat (tous les mois ou une fois par an), choisissez une période de prédiction plus longue et une définition d’attrition.

## <a name="create-a-transaction-churn-prediction"></a>Créer une prédiction d’attrition des transactions

1. Dans Customer Insights, accédez à **Intelligence** > **Prédictions**.

1. Sélectionnez la vignette **Modèle d’attrition clients** et sélectionnez **Utiliser ce modèle**.

1. Dans le volet **Modèle d’attrition clients**, choisissez **Transaction** et sélectionnez **Démarrer**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Capture d’écran avec l’option de transaction sélectionnée dans le volet Modèle d’attrition clients.":::
 
### <a name="name-model"></a>Nommer le modèle

1. Donnez un nom au modèle pour le distinguer des autres modèles.

1. Donnez un nom à l’entité en sortie en utilisant uniquement des lettres et des chiffres, sans espaces. Il s’agit du nom que l’entité modèle utilisera. 

1. Cliquez sur **Suivant**.

### <a name="define-customer-churn"></a>Définir l’attrition client

1. Définissez la **Fenêtre de prédiction**. Par exemple, prédisez le risque d’attrition de vos clients au cours des 90 prochains jours pour vous aligner sur vos efforts de fidélisation avec le marketing. Prédire le risque d’attrition sur une période plus ou moins longue peut rendre plus difficile de prendre en compte les facteurs de votre profil de risque d’attrition, mais cela dépend des besoins spécifiques à votre entreprise.
   >[!TIP]
   > Vous pouvez sélectionner **Enregistrer le brouillon** à tout moment pour enregistrer la prédiction en tant que brouillon. Vous trouverez le projet de prédiction dans l’onglet **Mes prédictions** pour continuer.

1. Saisissez le nombre de jours pour définir l’attrition dans le champ **Définition de l’attrition**. Par exemple, si un client n’a pas effectué d’achats au cours des 30 derniers jours, il peut être considéré comme perdu pour votre entreprise. 

1. Cliquez sur **Suivant** pour continuer.

### <a name="add-required-data"></a>Ajouter les données requises

1. Sélectionnez **Ajouter des données** et choisissez le type d’activité dans le volet latéral qui contient les informations requises sur l’historique des transactions ou des achats.

1. En dessous de **Sélectionner des activités**, choisissez les activités spécifiques du type d’activité sélectionné sur lesquelles vous souhaitez que le calcul se concentre.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Volet latéral affichant le choix d’activités spécifiques de type sémantique.":::

   Si vous n’avez pas encore associé l’activité à un type sémantique, sélectionnez **Modifier**. L’expérience guidée pour associer les activités sémantiques s’ouvre. Associez vos données aux champs correspondants dans le type d’activité sélectionné.

1. Associez les attributs sémantiques aux champs requis pour exécuter le modèle. Si les champs ci-dessous ne sont pas renseignés, configurez la relation entre votre entité d’historique des achats et l’entité *Client*. Cliquez sur **Enregistrer**.

1. À l’étape **Ajouter les données requises**, sélectionnez **Suivant** pour continuer si vous ne souhaitez pas ajouter d’autres activités.


# <a name="individual-consumers-b-to-c"></a>[Consommateurs individuels (B-to-C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Ajouter des données supplémentaires (facultatif)

Configurez la relation entre votre entité d’activité client et l’entité *Client*.

1. Sélectionnez le champ qui identifie le client dans la table des activités client. Il peut être directement lié à l’ID client principal de votre entité *Client*.

1. Sélectionnez l’entité qui est votre entité *Client* principale.

1. Entrez un nom qui décrit la relation.

#### <a name="customer-activities"></a>Activités du client

1. Vous pouvez éventuellement sélectionner **Ajouter des données** pour **Activités client**.

1. Sélectionnez le type d’activité sémantique qui contient les données que vous souhaitez utiliser, puis sélectionnez une ou plusieurs activités dans la section **Activités**.

1. Sélectionnez un type d’activité correspondant au type d’activité du client que vous configurez. Sélectionnez **Créer** et choisissez un type d’activité disponible ou créez un nouveau type.

1. Sélectionnez **Suivant**, puis **Enregistrer**.

1. Si vous avez d’autres activités client que vous souhaitez inclure, répétez les étapes ci-dessus.

# <a name="business-accounts-b-to-b"></a>[Comptes d’entreprise (B-to-B)](#tab/b2b)

### <a name="select-prediction-level"></a>Sélectionner le niveau de prédiction

La plupart des prédictions sont créées au niveau du client. Dans certaines situations, cela peut ne pas être suffisamment granulaire pour répondre aux besoins de votre entreprise. Vous pouvez utiliser cette fonctionnalité pour prédire l’attrition pour une succursale d’un client par exemple, plutôt que pour le client dans son ensemble.

1. Pour créer un prédiction à un niveau plus granulaire que le client, sélectionnez **Sélectionner une entité pour un niveau secondaire**. Si l’option n’est pas disponible, assurez-vous d’avoir rempli la section précédente.

1. Développez les entités à partir desquelles vous souhaitez choisir le niveau secondaire ou utilisez la zone de filtre de recherche pour filtrer les options sélectionnées.

1. Choisissez l’attribut que vous souhaitez utiliser comme niveau secondaire, puis sélectionnez **Ajouter**

1. Sélectionnez **Suivant**.

> [!NOTE]
> Les entités disponibles dans cette section sont affichées car elles ont une relation avec l’entité que vous avez choisie dans la section précédente. Si vous ne voyez pas l’entité que vous souhaitez ajouter, assurez-vous qu’elle a une relation valide présente dans **Relations**. Seuls les types de relation un-à-un et plusieurs-à-un sont valides pour cette configuration.

### <a name="add-additional-data-optional"></a>Ajouter des données supplémentaires (facultatif)

Configurez la relation entre votre entité d’activité client et l’entité *Client*.

1. Sélectionnez le champ qui identifie le client dans la table des activités client. Il peut être directement lié à l’ID client principal de votre entité *Client*.

1. Sélectionnez l’entité qui est votre entité *Client* principale.

1. Entrez un nom qui décrit la relation.

#### <a name="customer-activities"></a>Activités du client

1. Vous pouvez éventuellement sélectionner **Ajouter des données** pour **Activités client**.

1. Sélectionnez le type d’activité sémantique qui contient les données que vous souhaitez utiliser, puis sélectionnez une ou plusieurs activités dans la section **Activités**.

1. Sélectionnez un type d’activité correspondant au type d’activité du client que vous configurez. Sélectionnez **Créer** et choisissez un type d’activité disponible ou créez un nouveau type.

1. Sélectionnez **Suivant**, puis **Enregistrer**.

1. Si vous avez d’autres activités client que vous souhaitez inclure, répétez les étapes ci-dessus.

#### <a name="customers-data"></a>Données des clients

1. En option, sélectionnez **Ajouter des données** pour **Données clients**.

1. Mappez les attributs sémantiques aux champs de vos propres données client telles qu’identifiées. Les données des champs utilisés ne doivent pas changer souvent pour garantir les meilleures performances du modèle. Par exemple, la sélection d’un champ pour « Classification », qui changeait tous les mois, n’aurait que la dernière valeur utilisée dans le prédiction, même si, historiquement, la même valeur peut ne pas s’appliquer au client lors de la création des modèles de prédiction.

1. Sélectionnez **Suivant**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Fournir une liste facultative de comptes de référence

Ajoutez une liste de vos clients et comptes professionnels que vous souhaitez utiliser comme références. Vous recevrez les [détails de ces comptes de référence](#review-a-prediction-status-and-results) y compris leur score d’attrition et les fonctionnalités les plus influentes qui ont eu un impact sur la prédiction de leur attrition.

1. Sélectionnez **+ Ajouter des clients**.

1. Choisissez les clients qui servent de référence.

1. Cliquez sur **Suivant** pour continuer.

---

### <a name="set-schedule-and-review-configuration"></a>Définir le calendrier et revoir la configuration

1. Définissez une fréquence pour renouveler l’entraînement de votre modèle. Ce paramètre est important pour mettre à jour la précision des prédictions lorsque de nouvelles données sont ingérées. La plupart des entreprises peuvent se réentraîner une fois par mois et obtenir une bonne précision pour leur prédiction.

1. Cliquez sur **Suivant**.

1. Passez en revue la configuration de la prédiction. Vous pouvez revenir aux étapes précédentes en sélectionnant **Modifier** sous la valeur indiquée. Ou vous pouvez sélectionner une étape de configuration dans l’indicateur de progression.

1. Si toutes les valeurs sont configurées correctement, sélectionnez **Enregistrer et exécuter** pour commencer le processus de prédiction. Sur l’onglet **Mes prédictions**, vous pouvez voir l’état de vos prévisions. Le processus peut prendre plusieurs heures pour se terminer selon la quantité de données utilisées dans la prédiction.

## <a name="review-a-prediction-status-and-results"></a>Examiner l’état et les résultats de la prédiction

1. Accédez à **Intelligence** > **Prédictions** et sélectionnez l’onglet **Mes prédictions**.

1. Sélectionnez la prédiction à réviser.
   - **Nom de la prédiction :** Nom de la prédiction fournie lors de sa création.
   - **Type de prédiction :** Type de modèle utilisé pour la prédiction
   - **Entité de sortie** : Nom de l’entité destinée à stocker la sortie de la prédiction. Vous pouvez trouver une entité portant ce nom sur **Données** > **Entités**.
     Dans l’entité de sortie, *ChurnScore* est la probabilité prédite d’attrition et *IsChurn* est une étiquette binaire basée sur *ChurnScore* avec un seuil de 0,5. Le seuil par défaut peut ne pas fonctionner pour votre scénario. [Créez un nouveau segment](segments.md#create-a-segment) avec votre seuil préféré.
     Tous les clients ne sont pas nécessairement des clients actifs. Certains d’entre eux n’ont peut-être pas eu d’activité pendant un certain temps et sont déjà considérés comme perdus, selon votre définition d’attrition. Prédire le risque d’attrition pour les clients qui ont déjà abandonné n’est pas utile car ils ne sont pas l’audience d’intérêt.
   - **Champ prédit** : ce champ n’est renseigné que pour certains types de prédictions et n’est pas utilisé dans la prédiction de l’attrition.
   - **Statut :** Statut de l’exécution de la prédiction.
        - **Mis en file d’attente** : la prédiction attend l’exécution des autres processus.
        - **Actualisation en cours** : la prédiction est en cours d’exécution pour produire des résultats qui seront envoyés vers l’entité de sortie.
        - **Échec :** L’exécution de la prédiction a échoué. [Consultez les journaux](manage-predictions.md#troubleshoot-a-failed-prediction) pour plus de détails.
        - **Réussite :** La prédiction a réussi. Sélectionnez **Afficher** sous les ellipses verticales pour revoir la prédiction
   - **Modifié :** Date de modification de la configuration de la prédiction.
   - **Dernière actualisation :** Date d’actualisation de la prédiction dans l’entité en sortie.

1. Sélectionnez les ellipses verticales à côté de la prédiction pour laquelle vous souhaitez consulter les résultats et sélectionnez **Afficher**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Affichez le contrôle pour voir les résultats d’une prédiction.":::

# <a name="individual-consumers-b-to-c"></a>[Consommateurs individuels (B-to-C)](#tab/b2c)

1. La page de résultats comporte trois sections principales de données :
   - **Performance du modèle de formation :** A, B ou C sont des scores possibles. Ce score indique les performances de la prédiction et peut vous aider à prendre la décision d’utiliser les résultats stockés dans l’entité de sortie. Les scores sont déterminés en fonction des règles suivantes : 
        - **A** lorsque le modèle a prédit avec précision au moins 50 % des prédictions totales et que le pourcentage de prédictions précises pour les clients perdus est supérieur d’au moins 10 % au taux de référence.
            
        - **B** lorsque le modèle a prédit avec précision au moins 50 % des prédictions totales et que le pourcentage de prédictions précises pour les clients perdus est jusqu’à 10 % supérieur au taux de référence.
            
        - **C** lorsque le modèle a prédit avec précision moins de 50 % des prédictions totales ou que le pourcentage de prédictions précises pour les clients perdus est inférieur au taux de référence.
               
        - **Référence** prend l’entrée de l’intervalle de temps de prédiction pour le modèle (par exemple, un an) et le modèle crée différentes fractions de temps en le divisant par 2 jusqu’à ce qu’il atteigne un mois ou moins. Il utilise ces fractions pour créer une règle métier pour les clients qui n’ont pas effectué d’achats sur cette période. Ces clients sont considérés comme perdus. La règle métier basée sur le temps ayant la plus grande capacité à prédire qui présente un risque d’attrition est choisie comme modèle de référence.
            
    - **Probabilité d’attrition (nombre de clients)**  : Groupes de clients en fonction du risque d’attrition prévu. Ces données peuvent vous aider ultérieurement si vous souhaitez créer un segment de clients à haut risque de désabonnement. Ces segments aident à comprendre où doit se situer votre limite pour l’appartenance à un segment.
       
    - **Facteurs les plus influents** : De nombreux facteurs sont pris en compte lors de la création de votre prédiction. Chacun des facteurs a son importance calculée pour les prédictions regroupées créées par un modèle. Vous pouvez utiliser ces facteurs pour valider vos résultats de prédiction, ou vous pouvez utiliser ces informations plus tard pour [créer des segments](segments.md) qui pourraient contribuer à influencer le risque d’attrition pour les clients.


# <a name="business-accounts-b-to-b"></a>[Comptes d’entreprise (B-to-B)](#tab/b2b)

1. La page de résultats comporte trois sections principales de données :
   - **Performance du modèle de formation :** A, B ou C sont des scores possibles. Ce score indique les performances de la prédiction et peut vous aider à prendre la décision d’utiliser les résultats stockés dans l’entité de sortie. Les scores sont déterminés en fonction des règles suivantes : 
        - **A** lorsque le modèle a prédit avec précision au moins 50 % des prédictions totales et que le pourcentage de prédictions précises pour les clients perdus est supérieur d’au moins 10 % au taux de référence.
            
        - **B** lorsque le modèle a prédit avec précision au moins 50 % des prédictions totales et que le pourcentage de prédictions précises pour les clients perdus est jusqu’à 10 % supérieur au taux de référence.
            
        - **C** lorsque le modèle a prédit avec précision moins de 50 % des prédictions totales ou que le pourcentage de prédictions précises pour les clients perdus est inférieur au taux de référence.
               
        - **Référence** prend l’entrée de l’intervalle de temps de prédiction pour le modèle (par exemple, un an) et le modèle crée différentes fractions de temps en le divisant par 2 jusqu’à ce qu’il atteigne un mois ou moins. Il utilise ces fractions pour créer une règle métier pour les clients qui n’ont pas effectué d’achats sur cette période. Ces clients sont considérés comme perdus. La règle métier basée sur le temps ayant la plus grande capacité à prédire qui présente un risque d’attrition est choisie comme modèle de référence.
            
    - **Probabilité d’attrition (nombre de clients)**  : Groupes de clients en fonction du risque d’attrition prévu. Ces données peuvent vous aider ultérieurement si vous souhaitez créer un segment de clients à haut risque de désabonnement. Ces segments aident à comprendre où doit se situer votre limite pour l’appartenance à un segment.
       
    - **Facteurs les plus influents** : De nombreux facteurs sont pris en compte lors de la création de votre prédiction. Chacun des facteurs a son importance calculée pour les prédictions regroupées créées par un modèle. Vous pouvez utiliser ces facteurs pour valider vos résultats de prédiction, ou vous pouvez utiliser ces informations plus tard pour [créer des segments](segments.md) qui pourraient contribuer à influencer le risque d’attrition pour les clients.


1. Pour les comptes professionnels, vous trouverez une page d’informations **Analyse des fonctionnalités influentes**. Elle contient quatre sections de données :

    - L’élément sélectionné dans le volet de droite détermine le contenu de cette page. Sélectionnez un élément parmi **Meilleurs clients** ou **Clients de référence**. Les deux listes sont classées par valeur décroissante du score d’attrition, que le score soit uniquement pour le client ou un score combiné pour les clients et un niveau secondaire comme une catégorie de produits.
        
        - **Meilleurs clients** : Liste de 10 clients qui présentent le risque le plus élevé d’attrition et le risque le plus faible en fonction de leurs scores d’attrition. 
        - **Clients de référence** : Liste contenant jusqu’à 10 clients qui ont été sélectionnés lors de la configuration du modèle.
 
    - **Score d’attrition :** Affiche le score d’attrition de l’élément sélectionné dans le volet de droite.
    
    - **Répartition du score d’attrition :** Affiche la répartition du risque d’attrition entre les clients et le centile dans lequel se trouve le client sélectionné. 
    
    - **Principales fonctionnalités augmentant et diminuant le risque d’attrition :** Pour l’élément sélectionné dans le volet de droite, les cinq principales fonctionnalités qui ont augmenté et diminué le risque d’attrition sont répertoriées. Pour chaque fonctionnalité influente, vous trouvez la valeur de la fonctionnalité pour cet élément et son influence sur le score d’attrition. La valeur moyenne de chaque fonctionnalité sur les segments client d’attrition faible, moyen et élevé est également affichée. Cela permet de mieux contextualiser les valeurs des caractéristiques les plus influentes pour l’élément sélectionné et de les comparer aux segments client d’attrition faible, moyen et élevé.

       - Faible : comptes ou combinaisons de comptes et de niveau secondaire avec un score d’attrition compris entre 0 et 0,33
       - Moyen : comptes ou combinaisons de comptes et de niveaux secondaires avec un score d’attrition compris entre 0,33 et 0,66
       - Élevé : comptes ou combinaisons de comptes et de niveaux secondaires avec un score d’attrition supérieur à 0,66
    
       Lorsque vous prédisez l’attrition au niveau du compte, tous les comptes sont pris en compte dans la dérivation des valeurs de fonctionnalités moyennes pour les segments d’attrition. Pour les prédictions d’attrition au niveau secondaire pour chaque compte, la dérivation des segments d’attrition dépend du niveau secondaire de l’élément sélectionné dans le volet latéral. Par exemple, si un élément a un niveau secondaire de catégorie de produits = fournitures de bureau, seuls les éléments ayant des fournitures de bureau comme catégorie de produits sont pris en compte lors de la dérivation des valeurs de fonctionnalités moyennes pour les segments d’attrition. Cette logique est appliquée pour garantir une comparaison équitable des valeurs des fonctionnalités de l’éléments avec les valeurs moyennes sur les segments d’attrition faible, moyen et élevé.

       Dans certains cas, la valeur moyenne des segments d’attrition faible, moyen ou élevé est vide ou n’est pas disponible car aucun élément n’appartient aux segments d’attrition correspondants sur la base de la définition ci-dessus.
       
       > [!NOTE]
       > L’interprétation des valeurs des colonnes faible, moyen, élevé habituelles est différente pour les caractéristiques catégoriques telles que le pays ou le secteur. Étant donné que la notion de valeur de caractéristique « moyenne » ne s’applique pas aux caractéristiques catégoriques, les valeurs de ces colonnes sont la proportion de clients dans les segments à taux de désabonnement faible, moyen ou élevé qui ont la même valeur pour la caractéristique catégorique par rapport à l’article sélectionné dans le panneau latéral.

---

## <a name="manage-predictions"></a>Gérer les prédictions

Il est possible d’optimiser, de dépanner, d’actualiser ou de supprimer des prédictions. Consultez un rapport d’utilisation des données d’entrée pour découvrir comment rendre un prédiction plus rapide et plus fiable. Pour plus d’informations, consultez [Gérer les prédictions](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
