---
title: Enrichir les profils clients avec Microsoft Graph
description: Utilisez les données propriétaires de Microsoft Graph pour enrichir vos données client avec les affinités pour des marques et des intérêts.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405648"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Enrichir les profils client avec les affinités pour des marques et des intérêts (préversion)

Utilisez les données propriétaires de Microsoft Graph pour enrichir vos données client avec les affinités pour des marques et des intérêts. Ces affinités sont déterminées en fonction des données de personnes ayant des caractéristiques démographiques similaires à celles de vos clients. Ces informations vous aident à mieux comprendre et segmenter vos clients en fonction de leurs affinités avec des marques et des intérêts spécifiques.

Dans Audience Insights, accédez à **Données** > **Enrichissement** pour [configurer et afficher les enrichissements](enrichment-hub.md).

Pour configurer l'enrichissement des affinités pour les marques, accédez à l'onglet **Découvrir** et sélectionnez **Enrichir mes données** sur l'onglet **Marques**.

Pour configurer l'enrichissement des affinités pour des centres intérêts, accédez à l'onglet **Découvrir** et sélectionnez **Enrichir mes données** sur l'onglet **Intérêts**.

   > [!div class="mx-imgBorder"]
   > ![Vignettes Marques et centres d'intérêt](media/BrandsInterest-tile-Hub.png "Vignettes Marques et Centres d'intérêt")

## <a name="about-microsoft-graph"></a>À propos de Microsoft Graph

Nous utilisons les données de recherche en ligne de Microsoft Graph pour trouver des affinités avec des marques et des intérêts dans divers segments démographiques (définis selon l'âge, le sexe ou le lieu). Le volume de recherche en ligne pour une marque ou un intérêt détermine le degré d'affinité d'un segment démographique, par rapport à d'autres segments, pour cette marque ou cet intérêt.

[En savoir plus sur Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Score d'affinité et confiance

Le **score d'affinité** est calculé sur une échelle de 100 points, 100 représentant le segment ayant la plus forte affinité pour une marque ou un intérêt.

La **confiance de l'affinité** est également calculée sur une échelle de 100 points. Elle indique le niveau de confiance du système pour un segment présentant une affinité pour la marque ou l'intérêt. Le niveau de confiance est basé sur la taille et la granularité du segment. La taille d'un segment est déterminée par la quantité de données dont nous disposons pour un segment donné. La granularité du segment est déterminée par le nombre d'attributs (âge, sexe, lieu) disponibles dans un profil.

Nous ne normalisons pas les scores de votre jeu de données. Par conséquent, vous ne verrez peut-être pas toutes les valeurs de score d'affinité possibles pour votre jeu de données. Par exemple, Il n'y a peut-être aucun profil client enrichi avec un score d'affinité de 100 dans vos données. Cela est possible si aucun client dans le segment démographique n'a obtenu un score de 100 pour une marque ou un intérêt donné.

> [!TIP]
> Lors de la [création de segments](segments.md) à l'aide des scores d'affinité, passez en revue la distribution des scores d'affinité pour votre jeu de données avant de décider des seuils de score appropriés. Par exemple, un score d'affinité de 10 peut être considéré comme significatif dans un jeu de données qui a un score d'affinité le plus élevé de seulement 25 pour une marque ou un intérêt donné.

## <a name="supported-countriesregions"></a>Pays/régions pris en charge

Nous prenons actuellement en charge les options de pays/région suivantes : Australie, Canada (anglais), France, Allemagne, Royaume-Uni ou États-Unis (anglais).

Pour sélectionner un pays, ouvrez **Enrichissement des marques** ou **Enrichissement des intérêts** et sélectionnez **Changement** à côté de **Pays/Région**. Dans le volet **Paramètres de pays/région**, choisissez une option et sélectionnez **Appliquer**.

### <a name="implications-related-to-country-selection"></a>Implications liées à la sélection du pays

- Pour [choisir vos propres marques](#define-your-brands-or-interests), nous fournissons des suggestions basées sur le pays/la région sélectionné.

- Au moment de [choisir un secteur](#define-your-brands-or-interests), nous identifierons les marques ou centres d'intérêt les plus pertinents en fonction du pays ou de la région sélectionné.

- Pour [cartographier vos champs](#map-your-fields), si le champ Pays/Région n'est pas mappé, nous utilisons les données Microsoft Graph du pays/région sélectionné pour enrichir vos profils clients. Nous utilisons également cette sélection pour enrichir vos profils clients qui ne disposent pas de données de pays/région.

- Pour [enrichir les profils](#refresh-enrichment), nous enrichissons tous les profils clients pour lesquels nous disposons de données Microsoft Graph pour les marques et centres d'intérêt sélectionnés, y compris les profils qui ne se trouvent pas dans le pays/la région sélectionné. Par exemple, si vous avez sélectionné l'Allemagne, nous enrichissons les profils situés aux États-Unis si nous disposons de données Microsoft Graph pour les marques et centres d'intérêt sélectionnés aux États-Unis.

## <a name="configure-enrichment"></a>Configurer l'enrichissement

La configuration de l'enrichissement des marques ou des centres d'intérêt se compose de deux étapes :

### <a name="define-your-brands-or-interests"></a>Définir vos marques ou centres d'intérêt

Sélectionnez l’une des options suivantes :

- **Secteur** : Le système identifie les principaux centres d'intérêts ou marques pertinents pour votre secteur et enrichit vos données client avec ceux-ci.
- **Choisir votre propre** : Sélectionnez jusqu'à cinq éléments dans la liste des marques ou centres d'intérêts les plus pertinents pour votre organisation.

Pour ajouter une marque ou un intérêt, entrez-le dans la zone de saisie pour obtenir des suggestions en fonction des termes correspondants. Si nous ne répertorions pas une marque ou un intérêt que vous recherchez, envoyez-nous vos commentaires en utilisant le lien **Suggérer**.

### <a name="map-your-fields"></a>Mapper vos champs

Mappez les champs de votre entité client unifiée avec au moins deux attributs pour définir le segment démographique que nous devons utiliser pour enrichir vos données client. Sélectionnez **Modifier** pour définir le mappage des champs et sélectionnez **Appliquer** quand vous avez fini. Sélectionnez **Enregistrer** pour terminer le mappage de champs.

Les formats et valeurs suivants sont pris en charge, les valeurs ne sont pas sensibles à la casse :

- **Date de naissance** : nous vous recommandons de convertir la date de naissance en type DateTime lors de l'ingestion de données. Il peut également s'agir d'une chaîne au format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) « aaaa-MM-jj » ou « aaaa-MM-jjHH : mm : ss ».
- **Sexe** : Homme, Femme, Inconnu
- **Code postal** : codes postaux à cinq chiffres pour les États-Unis, code postal standard partout ailleurs
- **Ville** : nom de la ville en anglais
- **État/Province** : abréviation à deux lettres pour les États-Unis et le Canada. Abréviation de deux ou trois lettres pour l'Australie. Non applicable pour la France, l'Allemagne ou le Royaume-Uni.
- **Pays/Région** :

  - US : États-Unis d'Amérique, États-Unis, États-Unis, États-Unis, Amérique
  - CA : Canada, CA
  - GB : Royaume-Uni, R-U, Grande-Bretagne, GB, Royaume-Uni de Grande-Bretagne et d'Irlande du Nord, Royaume-Uni de Grande-Bretagne
  - AU : Australie, AU, Common Wealth of Australia
  - FR : France, FR, République française
  - DE : Allemagne, allemand, Deutschland, DE, République fédérale d'Allemagne, République d'Allemagne

## <a name="refresh-enrichment"></a>Actualisation de l'enrichissement

Exécutez l'enrichissement après avoir configuré les marques, les intérêts et le mappage de champs pour les données démographiques. Pour démarrer le processus, sélectionnez **Exécuter** sur la page de configuration de la marque ou du centre d'intérêt. De plus, vous pouvez laisser le système exécuter l'enrichissement automatiquement dans le cadre d'une actualisation planifiée.
Selon la taille de vos données client, un cycle d'enrichissement peut prendre plusieurs minutes.

> [!TIP]
> Il existe [six types de statuts](system.md#status-types) pour les tâches/processus. En outre, la plupart des processus [dépendent d'autres processus en aval](system.md#refresh-policies). Vous pouvez sélectionner le statut d'un processus pour afficher des détails sur la progression de toute la tâche. Après avoir sélectionné **Voir les détails** pour l'une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.

## <a name="enrichment-results"></a>Résultats d'enrichissement

Après avoir exécuté le processus d'enrichissement, allez dans **Mes enrichissements** pour examiner le nombre total de clients enrichis et la répartition des marques ou des centres d'intérêt dans les profils client enrichis.

:::image type="content" source="media/my-enrichments.png" alt-text="Aperçu des résultats après l'exécution du processus d'enrichissement":::

Consultez les données enrichies en sélectionnant **Afficher les données enrichies** dans le graphique. Les données enrichies pour les marques vont dans l'entité **MarqueAffinitéDeMicrosoft**. Les données pour les intérêts se trouvent dans l'entité **InterestAffinityFromMicrosoft**. Vous trouverez également ces entités répertoriées dans le groupe **Enrichissement** dans **Données** > **Entités**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Voir les données d'enrichissement sur la carte client

Les affinités de marque et d'intérêt peuvent également être consultées sur les cartes client individuelles. Accédez à **Clients** et sélectionnez un profil client. Dans la carte client, vous trouverez des graphiques pour les marques ou les centres d'intérêt pour lesquels les membres du profil démographique de ce client ont une affinité.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Carte client avec données enrichies":::

## <a name="next-steps"></a>Étapes suivantes

Exploitez vos données client enrichies. Créez des [Segments](segments.md), [Mesures](measures.md), voire [Exportez des données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.
