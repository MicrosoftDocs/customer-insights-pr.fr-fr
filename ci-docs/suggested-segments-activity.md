---
title: Segments suggérés basés sur l’activité (version préliminaire)
description: Laissez le Machine Learning vous aider à trouver de nouveaux segments intéressants en fonction de l’activité des clients.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170586"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Segments suggérés basés sur l’activité (version préliminaire)

Découvrez des segments intéressants de vos clients en fonction des données d’activité client ingérées dans Customer Insights. Les transactions, la durée des appels au support, les achats ou les retours sont des exemples de données d’activité. Pour suggérer des segments, la récence, la fréquence et la valeur monétaire (ou durée) des données d’activité sont analysées. Vous pouvez également générer des [segments suggérés pour améliorer une mesure ou mieux comprendre ce qui influence un attribut](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Onglet Segments suggérés affichant des suggestions de segments pour les segments basés sur l’activité et sur les attributs.":::

## <a name="categorize-customers-by-activity"></a>Catégoriser les clients par activité

Avec les [données d’activité](activities.md) disponibles dans Customer Insights, nous pouvons générer des suggestions qui représentent des groupes de clients :

- Les clients les plus actifs 
- Les clients qui ont effectué le plus d’achats 
- Les clients qui ont généré le plus de revenus 
- Les clients qui n’ont pas été actifs ces derniers temps 
- Les clients qui interagissent fréquemment avec votre entreprise  

Si vous avez une entreprise de vente au détail, vous pouvez découvrir quels clients génèrent le plus de revenus et les récompenser avec un coupon. Ou vous pouvez identifier des clients occasionnels et leur proposer de rejoindre un programme de récompenses afin qu’ils visitent votre entreprise plus souvent.
Si vous fournissez des soins de santé publics et que votre objectif est de minimiser les dépenses pour les patients individuels, vous pouvez essayer de réduire les visites récurrentes en fournissant les meilleurs soins possibles en aussi peu de visites que possible. Dans ce cas, votre objectif est de maintenir la fréquence des visites à un faible niveau et de minimiser les coûts récurrents pour les patients. Ou vous pouvez identifier des segments de patients qui ont des rendez-vous fréquents et des coûts récurrents élevés, et analyser ces cas pour améliorer le traitement des individus.

## <a name="required-data"></a>Données requises

Des suggestions sont générées en fonction des données d’entrée sélectionnées.

- Profils clients : tous les clients ou membres d’un segment spécifique.

- Période : le mois dernier, l’année dernière ou tout délai d’exécution personnalisé.

- Type d’activité : achats, transactions de détail, transactions en ligne, cas de support client, abonnements, etc.  

- Entité dans Customer Insights qui contient les données d’activité : l’entité UnifiedActivity ou l’entité pour une activité spécifique.

- Dimensions à inclure : récence, fréquence ou dimension monétaire, en fonction des besoins de votre entreprise.

## <a name="generate-suggested-segments"></a>Générer des segments suggérés

1. Accédez à **Segments** et sélectionnez l’onglet **Suggestions (version préliminaire)**.

1. Sélectionnez **Rechercher de nouvelles suggestions** et choisissez **Afficher ou anticiper le comportement du client**. Cliquez sur **Démarrer**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Première étape de l’assistant de configuration pour un segment suggéré en fonction de l’activité.":::

1. Fournissez les données d’entrée requises et sélectionnez **Suivant**.

   - Choisissez les clients : incluez tous les clients ou un segment spécifique.
   - Choisissez l’activité : sélectionnez le type d’activité et les entités qui décrivent l’activité.
   - Préférences : définissez la période à prendre en compte, les facteurs de suggestions et mappez les attributs.

1. Passez en revue votre entrée et sélectionnez **Exécuter** pour exécuter le modèle et générer des suggestions.

En fonction du nombre de profils clients et des activités sélectionnées, cela peut prendre quelques minutes.

Après avoir généré les suggestions, vous pouvez les filtrer en fonction de la dimension ou de la valeur qui vous intéresse le plus.

## <a name="manage-suggested-segments"></a>Gérer les segments suggérés

Accédez à **Segments** et sélectionnez l’onglet **Suggestions (aperçu)**. Dans la section **Suggestions basées sur l’activité**, sélectionnez un segment suggéré pour afficher les actions disponibles.

- **Afficher la suggestion** pour afficher les détails de ce segment, comme l’étendue de chaque dimension par rapport au groupe cible. Il met également en évidence le nombre de membres potentiels dans le segment et le pourcentage correspondant du nombre total de clients.
- **Créer un segment** pour enregistrer la suggestion en tant que segment. Il s’affiche sur l’onglet **Tous les segments** et peut être [actualisé ou supprimé](segments.md). Vous ne pouvez pas modifier les détails du segment. Cependant, vous pouvez modifier les critères d’entrée des suggestions et générer différentes suggestions.
- **Modifier les suggestions** pour modifier les attributs configurés qui remplaceront les suggestions actuelles.
- **Actualiser les suggestions** pour actualiser les suggestions tout en conservant les attributs configurés.

[!INCLUDE [footer-include](includes/footer-banner.md)]
