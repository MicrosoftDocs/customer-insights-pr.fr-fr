---
title: Analyse des sentiments des commentaires clients
description: Découvrez comment utiliser un modèle d’analyse des sentiments sur les commentaires des clients dans Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: e51225bbfcd445180b12661cba12256c3f042045
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646269"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analyser le sentiment dans les commentaires des clients (Version préliminaire)

De nos jours, les clients attendent des produits, des services et des expériences de haute qualité. Surtout les clients qui font part de leurs commentaires. Il est très difficile pour les organisations d’analyser un volume croissant de données sans réduire la précision et augmenter les coûts de main-d’œuvre. Dynamics 365 Customer Insights propose un modèle d’analyse des sentiments pour les commentaires des clients ; il permet aux organisations d’analyser leurs données avec plus de précision et à moindre coût.

L’analyse des sentiments vous permet de synthétiser les sentiments des clients et d’identifier les aspects commerciaux qui sont des fenêtres d’amélioration. Cette fonctionnalité de Customer Insights vous aide à comprendre ce qui fonctionne bien et les problèmes que vous devez résoudre. Concentrez-vous sur les domaines d’activité les plus pertinents et les plus impactants pour améliorer l’expérience de vos clients. Au bout du compte, cela pourra vous aider à mener des actions commerciales ouvrant sur des expériences qui se traduisent par des niveaux élevés de satisfaction et de fidélité des clients.

## <a name="overview"></a>Résumé

La fonction d’analyse des sentiments génère deux informations dérivées par ID client. Un score de sentiment (de -5 à 5) et une liste d’aspects commerciaux applicables (domaines d’activité) vous aident à mieux comprendre les commentaires des clients. 

Ces informations vous permettent d’atteindre les résultats suivants : 
- Obtenir une vue d’ensemble des sentiments des clients envers une marque ou une organisation
- Identifier les clients ayant un sentiment négatif pour cibler vos campagnes et démarches d’engagement et les optimiser pour un rendement plus élevé  
- Identifier les aspects commerciaux présentant les problèmes signalés par les clients  
- Segmenter les clients en fonction de leur sentiment pour lancer des campagnes personnalisées avec des efforts de vente, de marketing et de support ciblés
- Optimiser les opérations commerciales en traitant les domaines de préoccupation ou les opportunités qui ont été mentionnés par les clients
- Reconnaître les aspects commerciaux qui fonctionnent bien et récompenser les clients satisfaits grâce à des programmes de fidélité et de promotion

Pour vous assurer de pouvoir faire confiance aux résultats des modèles, nous fournissons des informations transparentes sur la façon dont les modèles prennent des décisions. Vous recevrez une liste de mots qui ont affecté la décision des modèles d’attribuer un score de sentiment particulier ou un aspect commercial aux commentaires reçus.  

Nous utilisons deux **Modèles de traitement du langage naturel (NLP)**  : le premier attribue à chaque commentaire un score de sentiment. Le deuxième modèle associe chaque retour d’information à tous les aspects commerciaux applicables. Les modèles sont entraînés sur des données publiques provenant de sources issues des réseaux sociaux, des commerces de détail, de la restauration, des produits de consommation et des industries automobiles.    
  
Les aspects commerciaux prédéfinis que le modèle doit associer aux données de rétroaction incluent :
-   Gestion de compte
-   Règlement et paiement
-   Service clientèle
-   Prélèvement en magasin
-   Expédition et récupération de l’emballage
-   Précommande
-   Tarif
-   Confidentialité et sécurité
-   Promotions et récompenses
-   Reçu et garantie
-   Échange de retour et annulation
-   Exactitude de l’exécution
-   Qualité du site Web/de l’application

> [!NOTE]
> Actuellement, nous ne prenons en charge que l’analyse des sentiments sur les commentaires des clients rédigés en anglais. D’autres langues seront prises en charge à l’avenir. Si des commentaires dans d’autres langues sont chargés, le modèle renverra quand-même des résultats. Cependant, ces résultats ne seront pas exacts. 

## <a name="prerequisites"></a>Conditions préalables

L’analyse des sentiments est basée sur les données des commentaires textuels qui sont passés par le [processus d’unification des données](data-unification.md). Nous vous recommandons fortement de [configurer vos entités de données de commentaires en tant qu’entités d’activité de type sémantique](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (Type Commentaires) au préalable. 

Pour configurer un modèle d’analyse des sentiments, vous avez besoin au moins des [autorisations Contributeur](permissions.md).

Customer Insights peut traiter jusqu’à 10 millions d’enregistrements de commentaires pour une seule exécution de modèle. Le modèle peut analyser les commentaires de rétroaction contenant jusqu’à 128 mots. Si un commentaire est plus long, l’analyse ne prend en compte que les 128 premiers mots.

### <a name="data-requirements"></a>Exigences au niveau des données
  
Les attributs de données suivants sont requis :
- ID client unifié (UCID) pour faire correspondre les enregistrements de données textuelles commentaire à un client individuel. Cet ID est le résultat du [processus d’unification des données](data-unification.md).
- ID de commentaires
- Horodatage des commentaires
- Texte du commentaire   

> [!TIP]
> L’analyse des sentiments nécessite de disposer du texte des commentaires de vos clients. Il n’est actuellement possible de configurer qu’une seule entité de commentaires. S’il existe plusieurs entités de commentaires, vous pouvez les réunir dans Power Query avant le début de l’ingestion des données.

## <a name="configure-a-sentiment-analysis"></a>Configuration d’une analyse des sentiments 

1. Dans Customer Insights, accédez à **Intelligence** > **Prédictions**.

1. Sur la vignette **Analyse du sentiment des clients**, sélectionnez **Utiliser le modèle**.

1. Dans le volet **Analyse du sentiment des clients (version préliminaire)**, sélectionnez **Démarrer**.

1. À l’étape **Nom du modèle**, indiquez un **Nom** pour votre analyse. 

1. Indiquez le **Nom de l’entité de sortie des aspects commerciaux** et le **Nom de l’entité de sortie du score de sentiment**, puis sélectionnez **Suivant**.

1. À l’étape **Données requises**, sélectionnez **Ajouter des données**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Ajouter un flux de données au modèle d’analyse des sentiments.":::

1. Dans le volet **Ajouter des données**, choisissez le type sémantique **Commentaires** dans la liste.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Étape de configuration pour sélectionner les activités de rétroaction pour l’analyse des sentiments.":::

1. Sélectionnez les activités à utiliser cette analyse des sentiments, puis sélectionnez **Suivant**.
 
1. Mappez les attributs de vos données sur les attributs du modèle. Sélectionnez **Enregistrer** pour appliquer vos sélections. 

1. Vous voyez l’état du mappage des données. Cliquez sur **Suivant** pour continuer. 

1. À l’étape **Vérifier les détails de votre modèle**, validez la configuration de votre analyse des sentiments. Vous pouvez revenir à n’importe quelle partie de la configuration de la prédiction. Sélectionnez **Enregistrer et exécuter** pour démarrer l’analyse. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Étape de révision du modèle de sentiment affichant tous les éléments configurés.":::

1. Sélectionnez **Terminé** pour quitter l’expérience de configuration. Le processus peut prendre plusieurs heures pour se terminer selon la quantité de données utilisées. 

## <a name="review-analysis-status"></a>Examen du statut de l’analyse

1.  Accédez à **Intelligence** > **Prédictions** et sélectionnez l’onglet **Mes prédictions**.
2.  Sélectionnez la prédiction à réviser.
- **Nom de la prédiction :** Nom de la prédiction fournie lors de sa création.
- **Type de prédiction :** type de modèle utilisé pour la prédiction.
- **Entité de sortie** : Nom de l’entité destinée à stocker la sortie de la prédiction. Aller à **Données** > **Entités** pour trouver l’entité avec ce nom.
- **Champ prédit :** Ce champ n’est renseigné que pour certains types de prédictions et n’est pas utilisé dans la prédiction de la valeur de la durée de vie du client.
- **Statut :** Statut de l’exécution de la prédiction.
  - **Mis en file d’attente :** La prédiction attend l’achèvement des autres processus.
  - **Actualisation en cours :** La prédiction est en cours d’exécution pour créer des résultats qui seront envoyés vers l’entité de sortie.
  - **Échec :** L’exécution de la prédiction a échoué. Consultez les journaux pour plus de détails.
  - **Réussite :** La prédiction a réussi. Sélectionnez Afficher sous les points de suspension verticaux pour consulter les résultats de prédiction.
- **Modifié :** Date de modification de la configuration de la prédiction.
- **Dernière actualisation** : date à laquelle la prédiction a actualisé les résultats dans l’entité de sortie.

## <a name="manage-sentiment-analysis"></a>Gérer l’analyse des sentiments

Vous pouvez optimiser, dépanner, actualiser ou supprimer des prédictions. Consultez un rapport d'utilisation des données d'entrée pour découvrir comment rendre un prédiction plus rapide et plus fiable. Pour plus d’informations, consultez [Gérer les prédictions](manage-predictions.md).

## <a name="review-analysis-results"></a>Examen des résultats d’analyse
 
1. Accédez à **Intelligence** > **Prédictions** et sélectionnez l’onglet **Mes prédictions**. 
1. Sélectionnez le nom de la prédiction pour laquelle vous souhaitez examiner les résultats. Dans ce cas, sélectionnez l’analyse des sentiments que vous souhaitez examiner. 

### <a name="summary-tab"></a>Onglet Résumé

La page de résultats comporte quatre sections principales de données. 

- **Score de sentiment moyen** : vous aide à comprendre le sentiment général de tous les clients. Les scores de sentiment sont regroupés en trois catégories : 
  1.    Négatif (-5 > 2)
  2.    Neutre (-1 > 1)
  3.    Positif (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Représentation visuelle du sentiment global des clients.":::

- **Répartition des clients par score de sentiment** : les clients sont classés en groupes négatif, neutre et positif en fonction de leur score de sentiment. Survolez les barres de l’histogramme pour voir le nombre de clients et le score de sentiment moyen dans chaque groupe. Ces données peuvent vous aider à [créer des segments de clientèle](segments.md) en fonction de leurs scores de sentiment.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Graphique à barres montrant le sentiment du client dans les trois groupes de sentiment.":::

- **Score de sentiment moyen au fil du temps** : le sentiment des clients peut évoluer au fil du temps. Nous fournissons des tendances des sentiments de vos clients pour l’intervalle de temps de vos données. Cette vue peut vous aider à évaluer l’effet des promotions saisonnières, des lancements de produits ou d’autres interventions limitées dans le temps sur le sentiment des clients. Consultez le graphique en sélectionnant l’année d’intérêt dans le menu déroulant. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Graphique historique avec le score de sentiment au fil du temps, représenté sous forme de ligne.":::
 
- **Sentiment à travers les aspects commerciaux** : ce tableau répertorie le sentiment moyen quant aux aspects commerciaux. Cela peut vous aider à évaluer les aspects de votre activité qui satisfont déjà les clients ou les aspects qui nécessitent plus d’attention. Les enregistrements de commentaires qui ne correspondent à aucun des aspects commerciaux pris en charge sont classés sous **Autre**. Le tableau est trié par ordre alphabétique par défaut. Vous pouvez modifier le tri en sélectionnant un en-tête de tableau.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Liste des aspects commerciaux avec la valeur du sentiment associé et le nombre de clients le mentionnant.":::
 
  Sélectionnez le nom d’un aspect commercial pour afficher des informations supplémentaires sur la façon dont il est identifié par le modèle. Ce volet comporte deux parties : 

  - **Mots influents** : présente les principaux mots qui ont influencé l’identification par le modèle IA d’un aspect commercial dans les commentaires des clients. 
    **Afficher les mots offensants** : vous permet d’inclure des mots offensants dans la liste à partir des données d’origine des commentaires des clients. Par défaut, cette option est désactivée.  Le masquage des mots offensants est appuyé sur un modèle IA ; il peut ne pas détecter tous les mots offensants. Nous continuons à itérer et à former le classificateur pour des performances optimales. Si vous détectez un mot offensant qui n’a pas été filtré comme prévu, faites-le nous savoir. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Liste des mots influents avec le bouton à bascule pour afficher ou masquer les mots offensants.":::
 
  - **Exemples de commentaires** : affiche les enregistrements de commentaires réels présents dans vos données. Les mots sont codés par couleur en fonction de leur influence sur l’identification d’un aspect commercial. 


### <a name="influential-words-analysis-tab"></a>Onglet d’analyse des mots influents

Trois sections d’informations supplémentaires expliquent le fonctionnement du modèle de sentiment.
  
1. **Principaux mots contribuant à un sentiment positif** : affiche les principaux mots qui ont influencé l’identification du sentiment positif par le modèle IA dans les commentaires des clients.  
2. **Principaux mots contribuant à un sentiment négatif** : affiche les principaux mots qui ont influencé l’identification du sentiment négatif par le modèle IA dans les commentaires des clients.  
3. **Exemples de commentaires** : affiche des enregistrements de commentaires réels, un avec un sentiment négatif et un avec un sentiment positif. Les mots dans les enregistrements de commentaires sont mis en surbrillance en fonction de leur contribution au score de sentiment attribué. Les mots qui contribuent à un score de sentiment positif sont surlignés en vert. Les mots contribuant à un score négatif sont surlignés en rouge.
   Sélectionnez **Afficher plus** pour charger plus d’échantillons de commentaires qui vous fourniront plus d’informations et de contexte sur le fonctionnement du modèle de sentiment.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Exemples d’analyse de sentiment sur les commentaires des clients.":::
 
**Afficher les mots offensants** : vous permet d’inclure des mots offensants dans la liste à partir des données d’origine des commentaires des clients. Par défaut, cette option est désactivée.  Le masquage des mots offensants est appuyé sur un modèle IA ; il peut ne pas détecter tous les mots offensants. Nous continuons à itérer et à former le classificateur pour des performances optimales. Si vous détectez un mot offensant qui n’a pas été filtré comme prévu, faites-le nous savoir. 

## <a name="act-on-analysis-results"></a>Action après les résultats de l’analyse

Vous pouvez facilement commencer à créer de nouveaux segments de clients à partir de la page des résultats de l’analyse des sentiments en sélectionnant **Créer des segments** en haut de la page de résultats du modèle.

:::image type="content" source="media/create-segment-model.png" alt-text="Barre de commandes avec options concernant les modèles prédiction.":::
 
## <a name="potential-bias"></a>Biais potentiel

Comme pour toute fonctionnalité qui utilise l’intelligence artificielle prédictive, vous devez être conscient de l’existence de biais potentiel dans les données que vous utilisez pour prédire le sentiment des clients. Par exemple, si vous ne collectez les commentaires que par voie numérique, vous pouvez manquer les commentaires des clients qui font principalement affaire avec vous en personne, ce qui pourrait affecter le résultat de la fonctionnalité.

Comme cette fonctionnalité utilise des moyens automatisés pour évaluer les données et faire des prédictions selon ces données, elle peut être utilisée comme méthode de profilage, de la manière dont ce terme est défini par le Réglement général sur la protection des données (RGPD). Votre utilisation de cette fonctionnalité pour traiter des données peut être soumise au RGPD ou à d’autres lois ou réglementations. Vous devez veiller à ce que votre utilisation de Dynamics 365 Customer Insights, y compris la fonction d’analyse des sentiments, soit conforme à toutes les lois et réglementations applicables, y compris les lois relatives à la vie privée, aux données personnelles, aux données biométriques, à la protection des données et à la confidentialité des communications.

[!INCLUDE [footer-include](includes/footer-banner.md)]

