---
title: Analyser le sentiment pour les commentaires des clients (version préliminaire)
description: Découvrez comment utiliser un modèle d’analyse des sentiments sur les commentaires des clients dans Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610463"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analyser le sentiment dans les commentaires des clients (version préliminaire)

L’analyse des sentiments vous permet de synthétiser les sentiments des clients et d’identifier les aspects commerciaux qui sont des fenêtres d’amélioration. Cette fonctionnalité de Customer Insights vous aide à comprendre ce qui fonctionne bien et les problèmes que vous devez résoudre. Cela peut vous aider à mener des actions commerciales ouvrant sur des expériences qui se traduisent par des niveaux élevés de satisfaction et de fidélité des clients.

## <a name="overview"></a>Résumé

La fonction d’analyse des sentiments génère deux informations dérivées par ID client. Un score de sentiment (de -5 à 5) et une liste d’aspects commerciaux applicables (domaines d’activité) qui vous aident à mieux comprendre les commentaires des clients.

Cette analyse vous aide à :
- Obtenir une vue d’ensemble des sentiments des clients envers une marque ou une organisation
- Identifier les clients ayant un sentiment négatif pour cibler vos campagnes et démarches d’engagement et les optimiser pour un rendement plus élevé  
- Identifier les aspects commerciaux présentant les problèmes signalés par les clients  
- Segmenter les clients en fonction de leur sentiment pour lancer des campagnes personnalisées avec des efforts de vente, de marketing et de support ciblés
- Optimiser les opérations commerciales en traitant les domaines de préoccupation ou les opportunités qui ont été mentionnés par les clients
- Reconnaître les aspects commerciaux qui fonctionnent bien et récompenser les clients satisfaits grâce à des programmes de fidélité et de promotion

Le modèle fournit une liste de mots qui ont affecté la décision du modèle d’attribuer un score de sentiment particulier ou un aspect commercial aux commentaires reçus.  

Nous utilisons deux **Modèles de traitement du langage naturel (NLP)**  : le premier attribue à chaque commentaire un score de sentiment. Le deuxième modèle associe chaque retour d’information à tous les aspects commerciaux applicables. Les modèles sont entraînés sur des données publiques provenant de sources issues des réseaux sociaux, des commerces de détail, de la restauration, des produits de consommation et des industries automobiles.
  
Les aspects commerciaux prédéfinis que le modèle doit associer aux données de rétroaction incluent :
- Gestion de compte
- Règlement et paiement
- Service clientèle
- Prélèvement en magasin
- Expédition et récupération de l’emballage
- Précommande
- Tarif
- Confidentialité et sécurité
- Promotions et récompenses
- Reçu et garantie
- Échange de retour et annulation
- Exactitude de l’exécution
- Qualité du site Web/de l’application

> [!NOTE]
> Actuellement, nous ne prenons en charge que l’analyse des sentiments sur les commentaires des clients rédigés en anglais. D’autres langues seront prises en charge à l’avenir. Si des commentaires dans d’autres langues sont chargés, le modèle renverra quand-même des résultats. Cependant, ces résultats ne seront pas exacts.

## <a name="prerequisites"></a>Conditions préalables

- Au moins des [autorisations contributeur](permissions.md)
- Données des commentaires de texte [unifiées](data-unification.md). Nous vous recommandons fortement de [configurer vos entités de données de commentaires en tant qu’entités d’activité de type sémantique](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (type Commentaires).
- ID client unifié (UCID) de l’unification des données pour faire correspondre les enregistrements de données textuelles commentaire à un client individuel.
- ID de commentaires
- Horodatage des commentaires
- Texte du commentaire

Customer Insights peut traiter jusqu’à 10 millions d’enregistrements de commentaires pour une seule exécution de modèle. Le modèle peut analyser les commentaires de rétroaction contenant jusqu’à 128 mots. Si un commentaire est plus long, l’analyse ne prend en compte que les 128 premiers mots.

> [!NOTE]
> Il n’est possible de configurer qu’une seule entité de commentaires. S’il existe plusieurs entités de commentaires, combinez-les dans Power Query avant l’ingestion des données.

## <a name="configure-a-sentiment-analysis"></a>Configuration d’une analyse des sentiments

1. Accédez à **Intelligence** > **Prédictions**.

1. Dans l’onglet **Créer**, sélectionnez **Utiliser le modèle** dans la vignette **Analyse du sentiment du client (version préliminaire)**.

1. Cliquez sur **Démarrer**.

1. **Nommez** l’analyse et fournissez le **Nom de l’entité de sortie des aspects commerciaux** et le **Nom de l’entité de sortie du score de sentiment**.

1. Cliquez sur **Suivant**.

1. Sélectionnez **Ajouter des données** pour **Commentaires du client**.

1. Sélectionnez le type d’activité sémantique **Commentaires** qui contient les données de commentaires. Si l’activité n’a pas été configurée, sélectionnez **ici** et créez-la.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Étape de configuration pour sélectionner les activités de rétroaction pour l’analyse des sentiments.":::

1. Sélectionnez les activités à utiliser cette analyse des sentiments, puis sélectionnez **Suivant**.

1. Mappez les attributs de vos données sur les attributs du modèle. 

1. Cliquez sur **Enregistrer**.

1. Cliquez sur **Suivant**. L’étape **Réviser et exécuter** affiche un résumé de la configuration et offre la possibilité d’apporter des modifications avant de créer l’analyse.

1. Sélectionnez **Modifier** dans l’une des étapes pour réviser et apporter des modifications.

1. Si vous êtes satisfait de vos sélections, sélectionnez **Enregistrer et exécuter** pour commencer à exécuter le modèle. Cliquez sur **Terminé**. L’onglet **Mes prédictions** s’affiche pendant la création de la prédiction. Le processus peut prendre plusieurs heures pour se terminer selon la quantité de données utilisées dans la prédiction.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Afficher les résultats de l’analyse

1. Accédez à **Intelligence** > **Prédictions**.

1. Dans l’onglet **Mes prédictions**, sélectionnez la prédiction que vous souhaitez afficher.

Il y a deux onglets de résultats.

### <a name="sumary-tab"></a>Onglet Résumé

La page de résultats comporte quatre sections principales de données.

- **Score de sentiment moyen** : le score de sentiment vous aide à comprendre le sentiment général de tous les clients.
  - **Négatif** (-5 > 2)
  - **Neutre** (-1 > 1)
  - **Positif** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Représentation visuelle du sentiment global des clients.":::

- **Répartition des clients par score de sentiment** : les clients sont classés en groupes négatif, neutre et positif en fonction de leur score de sentiment. Survolez les barres de l’histogramme pour voir le nombre de clients et le score de sentiment moyen dans chaque groupe. Ces données peuvent vous aider à [créer des segments de clientèle](prediction-based-segment.md) en fonction de leurs scores de sentiment.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Graphique à barres montrant le sentiment du client dans les trois groupes de sentiment.":::

- **Score de sentiment moyen au fil du temps** : le sentiment des clients peut évoluer au fil du temps. Nous fournissons des tendances des sentiments de vos clients pour l’intervalle de temps de vos données. Cette vue vous aide à évaluer l’effet des promotions saisonnières, des lancements de produits ou d’autres interventions limitées dans le temps sur le sentiment des clients. Consultez le graphique en sélectionnant l’année d’intérêt dans le menu déroulant.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Graphique historique avec le score de sentiment au fil du temps, représenté sous forme de ligne.":::

- **Sentiment dans les aspects commerciaux** : le sentiment moyen dans les aspects commerciaux vous aide à évaluer les aspects de votre entreprise qui satisfont déjà les clients ou qui nécessitent plus d’attention. Les enregistrements de commentaires qui ne correspondent à aucun des aspects commerciaux pris en charge sont classés sous **Autre**. Triez les données en sélectionnant n’importe quelle colonne.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Liste des aspects commerciaux avec la valeur du sentiment associé et le nombre de clients le mentionnant.":::

  Sélectionnez le nom d’un aspect commercial pour voir la façon dont il est identifié par le modèle :

  - **Mots influents** : principaux mots qui ont influencé l’identification par le modèle IA d’un aspect commercial dans les commentaires des clients.
    **Afficher les mots offensants** : vous permet d’inclure des mots offensants dans la liste à partir des données d’origine des commentaires des clients. Par défaut, cette option est désactivée.  Le masquage des mots offensants est appuyé sur un modèle IA ; il peut ne pas détecter tous les mots offensants. Si vous détectez un mot offensant qui n’a pas été filtré comme prévu, faites-le nous savoir.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Liste des mots influents avec le bouton à bascule pour afficher ou masquer les mots offensants.":::

  - **Exemples de commentaires** : enregistrements de commentaires réels présents dans vos données. Les mots sont codés par couleur en fonction de leur influence sur l’identification d’un aspect commercial.

### <a name="influential-words-analysis-tab"></a>Onglet d’analyse des mots influents

Trois sections d’informations supplémentaires expliquent le fonctionnement du modèle de sentiment.
  
- **Principaux mots contribuant à un sentiment positif** : principaux mots qui ont influencé l’identification du sentiment positif par le modèle IA dans les commentaires des clients.  

- **Principaux mots contribuant à un sentiment négatif** : principaux mots qui ont influencé l’identification du sentiment négatif par le modèle IA dans les commentaires des clients.

- **Exemples de commentaires** : enregistrements de commentaires réels, un avec un sentiment négatif et un avec un sentiment positif. Les mots dans les enregistrements de commentaires sont mis en surbrillance en fonction de leur contribution au score de sentiment attribué. Les mots qui contribuent à un score de sentiment positif sont surlignés en vert. Les mots contribuant à un score négatif sont surlignés en rouge.
   Cliquez sur **Voir plus** pour charger d’autres exemples de commentaires.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Exemples d’analyse de sentiment sur les commentaires des clients.":::

**Afficher les mots offensants** : vous permet d’inclure des mots offensants dans la liste à partir des données d’origine des commentaires des clients. Par défaut, cette option est désactivée.  Le masquage des mots offensants est appuyé sur un modèle IA ; il peut ne pas détecter tous les mots offensants. Si vous détectez un mot offensant qui n’a pas été filtré comme prévu, faites-le nous savoir.

## <a name="act-on-analysis-results"></a>Action après les résultats de l’analyse

Pour créer de nouveaux segments de clients à partir des résultats de l’analyse des sentiments, sélectionnez **Créer des segments** en haut de la page de résultats du modèle.

## <a name="potential-bias"></a>Biais potentiel

Comme pour toute fonctionnalité qui utilise l’intelligence artificielle prédictive, il peut y avoir des biais potentiels dans les données que vous utilisez pour prédire le sentiment des clients. Par exemple, si vous ne collectez les commentaires que par voie numérique, vous pouvez manquer les commentaires des clients qui font principalement affaire avec vous en personne, ce qui affecte le résultat de la fonctionnalité.

Comme cette fonctionnalité utilise des moyens automatisés pour évaluer les données et faire des prédictions selon ces données, elle peut être utilisée comme méthode de profilage, de la manière dont ce terme est défini par le Réglement général sur la protection des données (RGPD). Votre utilisation de cette fonctionnalité pour traiter des données peut être soumise au RGPD ou à d’autres lois ou réglementations. Vous devez veiller à ce que votre utilisation de Dynamics 365 Customer Insights, y compris la fonction d’analyse des sentiments, soit conforme à toutes les lois et réglementations applicables, y compris les lois relatives à la vie privée, aux données personnelles, aux données biométriques, à la protection des données et à la confidentialité des communications.

[!INCLUDE [footer-include](includes/footer-banner.md)]

