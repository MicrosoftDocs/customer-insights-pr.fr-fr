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
ms.openlocfilehash: e98aea3b3f3a2c4788346deab1b7ad7d1167110d
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054337"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Segments suggérés basés sur les données d’activité (version préliminaire)

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
Si vous travaillez dans le secteur de la santé et que vous fournissez des soins de santé publics, votre objectif est de minimiser les dépenses pour les patients individuels. Pour cela, vous pouvez réduire les visites récurrentes en offrant les meilleurs soins possibles en limitant le plus possible le nombre de visites. Dans ce cas, votre objectif est de maintenir la fréquence des visites à un faible niveau et de minimiser les coûts récurrents pour les patients. Ou vous pouvez identifier des segments de patients qui ont des rendez-vous fréquents et des coûts récurrents élevés, et analyser ces cas pour améliorer le traitement des individus. 

## <a name="required-data"></a>Données requises

Des suggestions sont générées en fonction des données d’entrée sélectionnées. 

- Profils clients : tous les clients ou membres d’un segment spécifique. 

- Période : le mois dernier, l’année dernière ou tout délai d’exécution personnalisé.

- Type d’activité : achats, transactions de détail, transactions en ligne, cas de support client, abonnements, etc.  

- Entité dans Customer Insights qui contient les données d’activité : l’entité UnifiedActivity ou l’entité pour une activité spécifique. 

- Dimensions à inclure : récence, fréquence ou dimension monétaire, en fonction des besoins de votre entreprise.

## <a name="generate-suggested-segments"></a>Générer des segments suggérés

1. Accédez à **Segments**.

1. Sélectionnez l’onglet **Suggestions (version préliminaire)**.

1. Sélectionnez **Rechercher de nouvelles suggestions** et choisissez **Afficher ou anticiper le comportement du client**. Sélectionnez **Démarrer** pour exécuter l’expérience guidée.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Première étape de l’assistant de configuration pour un segment suggéré en fonction de l’activité.":::

1. Fournissez les données d’entrée requises et sélectionnez **Suivant** pour poursuivre.

   - Choisissez les clients : incluez tous les clients ou un segment spécifique.
   - Choisissez l’activité : sélectionnez le type d’activité et les entités qui décrivent l’activité.
   - Préférences : définissez la période à prendre en compte, les facteurs de suggestions et mappez les attributs.

1. Passez en revue votre entrée et sélectionnez **Exécuter** pour exécuter le modèle et générer des suggestions.

1. En fonction du nombre de profils clients et des activités sélectionnées, cela peut prendre quelques minutes. 

Après avoir généré les suggestions, vous pouvez les filtrer en fonction de la dimension ou de la valeur qui vous intéresse le plus. 

## <a name="view-details-of-a-suggested-segment"></a>Afficher les détails d’un segment suggéré

Une fois les suggestions générées, elles sont répertoriées dans **Segments** > **Suggestions (version préliminaire)** dans la section **Suggestions basées sur les activités**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Volet latéral développé affichant les données détaillées d’un segment suggéré.":::

Sélectionnez **Afficher la suggestion** sur un segment suggéré pour afficher les détails de ce segment. Le volet latéral fournit des détails comme l’étendue de chaque dimension par rapport au groupe cible. Il met également en évidence le nombre de membres potentiels dans le segment et le pourcentage correspondant du nombre total de clients. Si vous souhaitez conserver la suggestion sous forme de segment, sélectionnez **Créer un segment**.    

## <a name="save-a-suggestion-as-a-segment"></a>Enregistrer une suggestion en tant que segment

1. Aller à **Segments** > **Suggestions (aperçu)**.

1. Sélectionnez le segment à enregistrer. 

1. Dans le volet latéral, sélectionnez **Créer un segment**. 

1. Lorsque vous avez enregistré le segment, il s’affiche dans la liste des segments de l’onglet **Tous les segments**. Il peut alors être [actualisé ou supprimé comme n’importe quel autre segment](segments.md). Vous ne pouvez pas modifier les détails du segment. Cependant, vous pouvez modifier les critères d’entrée des suggestions et générer différentes suggestions.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Actualiser ou modifier un ensemble de suggestions

1. Accédez à **Segments** > **Suggestions (version préliminaire)** et recherchez le segment dans la section **Suggestions basées sur les activités**.

1. Sélectionnez **Actualiser les suggestions** pour actualiser les suggestions tout en conservant les attributs configurés. Ou sélectionnez **Modifier les suggestions** pour modifier les attributs configurés. Le système réexécutera le processus, générera des suggestions de segment basées sur les dernières données et remplacera les suggestions actuelles.

[!INCLUDE [footer-include](includes/footer-banner.md)]
