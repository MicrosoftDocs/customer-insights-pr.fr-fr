---
title: Segments suggérés basés sur les mesures (version préliminaire)
description: Laissez Machine Learning vous aider à trouver de nouveaux segments intéressants en fonction des attributs des clients.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170954"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Segments suggérés basés sur les mesures (version préliminaire)

Découvrez des segments intéressants de vos clients à l’aide d’un modèle IA. Cette fonctionnalité optimisée par Machine Learning suggère des segments basés sur des mesures ou des attributs client. Cela peut vous aider à améliorer vos Indicateurs de performance clés (KPI) ou à mieux comprendre l’influence des attributs dans le contexte d’autres attributs.

> [!NOTE]
> La fonctionnalité des segments suggérés utilise des moyens automatisés pour évaluer les données et faire des prédictions basées sur ces données. Par conséquent, il a la capacité d’être utilisé comme méthode de profilage, tel que ce terme est défini par le Règlement général sur la protection des données (« RGPD »). Votre utilisation de cette fonctionnalité pour traiter des données peut être soumise au RGPD ou à d’autres lois ou réglementations. Vous êtes tenu de vous assurer que votre utilisation de Dynamics 365 Customer Insights, notamment cette fonctionnalité, est conforme à toutes les lois et réglementations applicables, notamment les lois relatives à la confidentialité, aux données personnelles, aux données biométriques, à la protection des données et à la confidentialité des communications.

:::image type="content" source="media/suggested-segments.png" alt-text="Page Segments suggérés qui affiche les détails d'une suggestion dans un volet latéral.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segments suggérés pour améliorer vos Indicateurs de performance clés

Si vous utilisez les [mesures créées](measures.md) pour faciliter le suivi de vos KPI, créez des segments pour afficher les influences sur le KPI. Vous pouvez utiliser ces informations pour lancer une campagne très ciblée.

Par exemple, vous suivez une mesure appelée *TotalSpendPerCustomer*. En tant qu’entreprise, vous aimeriez voir ce nombre augmenter. Le choix d’une mesure comme attribut principal vous permet de sélectionner les attributs dont vous souhaitez évaluer l’influence. Disons *niveau d’adhésion*, *période d’adhésion*, et *profession*. Customer Insights peut alors suggérer un segment qui vous indique qui est la plus grande influence de cette mesure. Par exemple, les *Comptables* qui sont membres *Or*, et qui travaillent avec votre entreprise depuis *au moins cinq ans* sont les plus grands influenceurs de *TotalSpendPerCustomer*. Vous obtiendrez une taille de segment estimée pour chaque suggestion. Vous pouvez utiliser ces informations pour créer des campagnes pour les publics ciblés.

## <a name="understand-what-influences-a-customer-attribute"></a>Comprendre ce qui influence un attribut client

Vous pouvez choisir un attribut client au lieu d’une mesure comme attribut principal. En fonction de votre choix d’attributs d’influence, le modèle IA crée une série de suggestions qui montrent comment les attributs sélectionnés influencent l’attribut principal.

Par exemple, vous choisissez *Membres récompensés (Oui/Non)* comme attribut principal. *Mandat*, *Profession* et *Nombre de tickets de support* sont définis comme d’autres attributs influents. Le modèle IA pourrait suggérer des segments indiquant que la plupart des professionnels de l’informatique ayant un mandat de plus de deux ans sont des membres récompensés. Une autre suggestion pourrait mettre en évidence que les comptables ayant plus d’un an et moins de trois tickets de soutien sont des membres récompensés.

## <a name="artificial-intelligence-usage"></a>Utilisation de l’intelligence artificielle

En utilisant l’attribut principal et les attributs d’influence, un algorithme d’arbre de décision suggère des segments intéressants. Les suggestions sont basées sur des règles ou des modèles qui ont été repris par l’algorithme d’IA. Seuls les segments qui diffèrent significativement de la population moyenne sont indiqués comme suggestions. La comparaison avec la population moyenne est basée sur la mesure ou l’attribut principal sélectionné.

### <a name="responsible-ai"></a>IA responsable

Les segments suggérés vous permettent de sélectionner des attributs pour créer des segments et traiter les données que vous sélectionnez. Lorsque vous choisissez des attributs, y compris des attributs sensibles tels que la race, l’orientation sexuelle ou le sexe, vous devez vous assurer que vous pouvez et devez traiter ces données. Vous êtes responsable de vous conformer à toutes les lois applicables à votre organisation et d’adhérer aux principes et politiques de confidentialité de votre organisation.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Différents résultats pour les attributs primaires avec des valeurs catégorielles et numériques

Les suggestions de segment sont différentes si vous choisissez un attribut numérique ou un attribut catégoriel comme attribut principal. Les valeurs d’un attribut catégoriel contiennent au moins deux catégories ou types. Un attribut numérique contient des données quantitatives et a un sens de la mesure qui lui est associé.

Avec un attribut numérique comme *revenu annuel* ou *période d’adhésion* comme attribut principal, le système suggère des segments qui ont une valeur moyenne supérieure ou inférieure de l’attribut numérique par rapport à tous les clients.

Un attribut catégorique comme *satisfaction du client*, car l’attribut principal entraîne des segments suggérés qui ont un pourcentage supérieur ou inférieur de clients appartenant à une catégorie particulière par rapport au pourcentage de tous les clients appartenant à cette même catégorie. Par exemple, *satisfaction du client* est choisi comme attribut principal et se compose de trois catégories (*Faible*, *Moyen* et *Élevé*). Pour chaque catégorie, des segments seront suggérés qui ont un pourcentage plus ou moins élevé de clients appartenant à cette catégorie par rapport à la proportion de tous les clients dans la même catégorie. Si 22 % de tous les clients affiche une satisfaction *Élevée*, alors, seuls les segments qui ont une proportion plus ou moins élevée de clients avec une satisfaction *Élevée* par rapport à 22 % seront suggérés pour cette catégorie. De même, des segments seront suggérés pour chacune des autres catégories (*Faible* et *Moyen*) s’ils sont statistiquement significatifs.

> [!NOTE]
> Actuellement, nous ne prenons en charge que les attributs catégoriels principaux qui ont jusqu’à 10 catégories. Si vous souhaitez afficher des suggestions de segment basées sur un attribut principal avec plus de 10 catégories, nous vous recommandons de regrouper certaines des catégories pour réduire le nombre de catégories à 10 ou moins. Cette limitation s’applique uniquement aux attributs principaux. Pour influencer les attributs catégoriels, nous prenons actuellement en charge un maximum de 100 catégories.

## <a name="generate-suggested-segments"></a>Générer des segments suggérés

1. Accédez à **Segments** et sélectionnez l’onglet **Suggestions (version préliminaire)**.

1. Sélectionnez **Rechercher de nouvelles suggestions** et choisissez **Améliorer une mesure/métrique**. Cliquez sur **Démarrer**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Choisir d’améliorer la mesure sur les segments suggérés.":::

1. Choisissez une mesure ou un attribut client comme attribut principal et cliquez sur **Suivant**.

1. Sélectionnez les attributs influents et sélectionnez **Exécuter**.

   > [!TIP]
   > La sélection de plusieurs attributs influents améliore les chances d’évaluer comment ils influencent l’attribut principal. N’incluez pas les attributs qui n’ont aucune influence sur l’attribut principal. Par exemple, si tous vos clients proviennent d’un pays spécifique, n’incluez pas l’attribut *pays*, car il n’aura aucun impact sur la sortie.

Selon le nombre de profils client et les attributs sélectionnés, le traitement des attributs sélectionnés peut prendre quelques minutes.

## <a name="manage-suggested-segments"></a>Gérer les segments suggérés

Accédez à **Segments** et sélectionnez l’onglet **Suggestions (aperçu)**. Dans la section **Suggestions de segments basées sur les attributs**, sélectionnez un segment suggéré pour afficher les actions disponibles.

- **Affichez** les détails du segment suggéré et les valeurs d’attribut ou les règles apprises par le modèle IA.
- **Enregistrer en tant que segment** la suggestion en tant que segment. Il s’affiche sur l’onglet **Tous les segments** et peut être [actualisé, modifié ou supprimé](segments.md).
- **Modifier les attributs** et modifiez les attributs configurés qui remplaceront les suggestions actuelles.
- **Actualiser les suggestions** pour actualiser les suggestions tout en conservant les attributs configurés.

## <a name="limitations"></a>Limitations

1. Incompatibilité de taille de segment estimée : si vous choisissez un attribut principal contenant des valeurs vides, cela peut affecter la taille de segment estimée dans les suggestions de segment. Lors de l’enregistrement d’un tel segment, la taille réelle du segment peut être différente de l’estimation d’origine.

2. Les attributs principaux de type booléen ne fonctionnent pas : actuellement, nous ne prenons en charge que les types de données chaîne et numérique comme attribut principal.

3. Les segments suggérés ne sont pas assez distincts : gardez à l’esprit que les attributs sélectionnés et la distribution des valeurs de ces attributs influencent les résultats. Vous pouvez modifier vos attributs d’influence ou même votre attribut principal pour obtenir des résultats différents.

[!INCLUDE [footer-include](includes/footer-banner.md)]