---
title: Enrichir les profils client avec les données de Microsoft
description: Utilisez les données propriétaires de Microsoft pour enrichir vos données clients avec des affinités et le partage de voix.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 12704ec46832e9463e6115db6c4df64e72bf4f97
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8372670"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Enrichir les profils clients avec des affinités et le partage de voix (version préliminaire)

Utilisez les données propriétaires de Microsoft pour enrichir vos données clients avec des affinités de marques, des affinités d’intérêt et le partage de voix (PdV). Ces affinités et le PdV sont basés sur les données des personnes présentant des caractéristiques démographiques similaires à celles de vos clients. Ces informations vous aident à mieux comprendre et segmenter vos clients en fonction de leurs affinités ou du PdV pour des marques et des intérêts spécifiques.

Dans les informations sur l’audience, accédez à **Données** > **Enrichissement** pour [configurer et afficher les enrichissements](enrichment-hub.md).

Pour configurer les affinités de marque et l’enrichissement de PdV, rendez-vous sur l’onglet **Découvrir** et sélectionnez **Enrichir mes données** sur la vignette **Marques**.

Pour configurer les affinités d’intérêt et l’enrichissement de PdV, rendez-vous sur l’onglet **Découvrir** et sélectionnez **Enrichir mes données** sur la vignette **Intérêts**.

   > [!div class="mx-imgBorder"]
   > ![Vignettes de marques et d’intérêts.](media/BrandsInterest-tile-Hub.png "Vignettes de marques et d’intérêts")

## <a name="how-we-determine-affinities-and-sov"></a>Comment nous déterminons les affinités et le PdV

Nous utilisons les données de recherche en ligne de Microsoft pour trouver des affinités et le PdV pour les marques et les intérêts dans divers segments démographiques (définis par âge, sexe ou emplacement). Le volume de recherche en ligne pour une marque ou un intérêt constitue la base pour déterminer l’affinité ou le PdV. Cependant, chacun offre une perspective différente pour comprendre vos clients.

- L’affinité est une comparaison entre des segments démographiques. Vous pouvez utiliser ces informations pour identifier les segments démographiques qui ont la plus grande affinité pour une marque ou un intérêt donné, par rapport à d’autres segments.

- Le partage de voix est un comparatif de vos marques ou intérêts sélectionnés. Vous pouvez utiliser ces informations pour identifier quelle marque ou quel intérêt a le partage de voix le plus élevé pour un segment démographique donné, par rapport aux autres marques ou intérêts que vous avez sélectionnés.

## <a name="affinity-level-and-score"></a>Niveau d’affinité et score

Dans chaque profil client enrichi, nous fournissons deux valeurs associées : le niveau d’affinité et le score d’affinité. Ces valeurs vous aident à déterminer la force de l’affinité pour le segment démographique de ce profil, pour une marque ou un centre d’intérêt, par rapport à d’autres segments démographiques.

*Niveau d’affinité* se compose de quatre niveaux et *score d’affinité* est calculé sur une échelle de 100 points qui correspond aux niveaux d’affinité.


|Niveau d’affinité |Score d’affinité  |
|---------|---------|
|Très élevé     | 85-100       |
|Forte     | 70-84        |
|Medium     | 35-69        |
|Faible     | 1-34        |

En fonction de la granularité que vous souhaitez pour mesurer l’affinité, vous pouvez utiliser le niveau d’affinité ou le score. Le score d’affinité vous donne un contrôle plus précis.

## <a name="share-of-voice-sov"></a>Partage de voix (PdV)

Nous calculons le PdV sur une échelle de 100 points. Le PdV total pour toutes les marques ou tous les intérêts pour chaque profil client enrichi s’élève à 100. Contrairement aux affinités, le PdV est relatif aux marques et aux intérêts que vous sélectionnez. Par exemple, les valeurs PdV pour « Microsoft » peuvent être différentes si les marques sélectionnées sont (« Microsoft », « GitHub ») par rapport à (« Microsoft », « LinkedIn »).

## <a name="supported-countriesregions"></a>Pays/régions pris en charge

Nous prenons actuellement en charge les options de pays/région suivantes : Australie, Canada (anglais), France, Allemagne, Royaume-Uni ou États-Unis (anglais).

Pour sélectionner un pays ou une région, ouvrez **Enrichissement des marques** ou **Enrichissement des intérêts** et sélectionnez **Changer** en regard de **Pays/Région**. Dans le volet **Paramètres de pays/région**, choisissez une option et sélectionnez **Appliquer**.

### <a name="implications-related-to-country-selection"></a>Implications liées à la sélection du pays

- Lorsque [vous choisissez vos propres marques](#define-your-brands-or-interests), le système fournit des suggestions en fonction du pays ou de la région sélectionnés.

- Lorsque [vous choisissez un secteur d’activité](#define-your-brands-or-interests), vous obtenez les marques ou centres d’intérêt les plus pertinents en fonction du pays ou de la région sélectionné.

- Lors de l’[enrichissement des profils](#refresh-enrichment), nous enrichirons tous les profils client pour lesquels nous obtenons des données pour les marques et les intérêts sélectionnés, y compris les profils qui ne se trouvent pas dans le pays ou la région sélectionné. Par exemple, si vous avez sélectionné l’Allemagne, nous enrichirons les profils situés aux États-Unis si des données sont disponibles pour les marques et les intérêts sélectionnés aux États-Unis.

## <a name="configure-enrichment"></a>Configurer l’enrichissement

Une expérience guidée vous aide tout au long de la configuration des enrichissements. 

### <a name="define-your-brands-or-interests"></a>Définir vos marques ou centres d’intérêt

Choisissez jusqu’à cinq marques ou centres d’intérêt en utilisant l’une ou les deux options suivantes :

- **Secteur d’activité** : sélectionnez votre secteur d’activité dans la liste déroulante, puis choisissez parmi les principaux intérêts et marques pour ce secteur d’activité.
- **Choisir les vôtres** : saisissez une marque ou un centre d’intérêt pertinent pour votre organisation, puis choisissez parmi les suggestions correspondantes. Si nous ne répertorions pas une marque ou un intérêt que vous recherchez, envoyez-nous vos commentaires en utilisant le lien **Suggérer**.

### <a name="review-enrichment-preferences"></a>Examiner les préférences d’enrichissement

Passez en revue vos préférences d’enrichissement par défaut et mettez-les à jour si nécessaire.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Capture d’écran de la fenêtre des préférences d’enrichissement.":::

### <a name="select-entity-to-enrich"></a>Sélectionner une entité à enrichir

Sélectionnez **Entité enrichie** et choisissez le jeu de données que vous souhaitez enrichir avec les données de Microsoft. Vous pouvez sélectionner l’entité Client pour enrichir tous vos profils clients ou sélectionner une entité segment pour enrichir uniquement les profils clients contenus dans ce segment.

### <a name="map-your-fields"></a>Mapper vos champs

Mappez les champs de votre entité client unifiée pour définir le segment démographique que vous souhaitez que le système utilise pour enrichir vos données client. Mappez le pays ou la région et au moins les attributs de date de naissance ou de sexe. De plus, vous devez mapper au moins un des codes de ville (et département/province) ou postal. Sélectionnez **Modifier** pour définir le mappage des champs et sélectionnez **Appliquer** quand vous avez fini. Sélectionnez **Enregistrer** pour terminer le mappage de champs.

Les formats et valeurs suivants sont pris en charge (les valeurs ne sont pas sensibles à la casse) :

- **Date de naissance** : nous vous recommandons de convertir la date de naissance en type DateTime lors de l’ingestion de données. Sinon, il peut s’agir d’une chaîne au format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) « aaaa-MM-jj » ou « aaaa-MM-jjTHH:mm:ss ».
- **Sexe** : homme, femme, inconnu.
- **Code postal** : codes postaux à cinq chiffres pour les États-Unis, code postal standard partout ailleurs.
- **Ville** : nom de la ville en anglais.
- **État/Province** : abréviation à deux lettres pour les États-Unis et le Canada. Abréviation de deux ou trois lettres pour l’Australie. Non applicable pour la France, l’Allemagne ou le Royaume-Uni.
- **Pays/Région** :

  - US : États-Unis d’Amérique, États-Unis, États-Unis, États-Unis, Amérique
  - CA : Canada, CA
  - GB : Royaume-Uni, R-U, Grande-Bretagne, GB, Royaume-Uni de Grande-Bretagne et d’Irlande du Nord, Royaume-Uni de Grande-Bretagne
  - AU : Australie, AU, Commonwealth d’Australie
  - FR : France, FR, République française
  - DE : Allemagne, allemand, Deutschland, DE, République fédérale d’Allemagne, République d’Allemagne

## <a name="review-and-name-the-enrichment"></a>Réviser et nommer l’enrichissement

Enfin, vous révisez les informations et fournissez un nom pour l’enrichissement.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Page de révision des intérêts et d’affectation d’un nom.":::

## <a name="refresh-enrichment"></a>Actualisation de l’enrichissement

Exécutez l’enrichissement après avoir configuré les marques, les intérêts et le mappage de champs pour les données démographiques. Pour démarrer le processus, sélectionnez **Exécuter** sur la page de configuration de la marque ou du centre d’intérêt. De plus, vous pouvez laisser le système exécuter l’enrichissement automatiquement dans le cadre d’une actualisation planifiée.

Selon la taille de vos données client, un cycle d’enrichissement peut prendre plusieurs minutes.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Résultats d’enrichissement

Après avoir exécuté le processus d’enrichissement, allez dans **Mes enrichissements** pour examiner le nombre total de clients enrichis et la répartition des marques ou des centres d’intérêt dans les profils client enrichis.

:::image type="content" source="media/my-enrichments.png" alt-text="Aperçu des résultats après l’exécution du processus d’enrichissement.":::

Vous y trouverez un graphique avec le nombre de profils clients enrichis au fil du temps et des aperçus des entités enrichies. Passez en revue les données enrichies en sélectionnant **Voir plus** dans les graphiques **Niveau d’affinité** ou **Partage de voix**. Les données enrichies pour les marques vont aux entités **BrandAffinityFromMicrosoft** et **BrandShareOfVoiceFromMicrosoft**. Les données relatives aux intérêts se trouvent dans les entités **InterestAffinityFromMicrosoft** et **InterestShareOfVoiceFromMicrosoft**. Vous trouverez également ces entités répertoriées dans le groupe **Enrichissement** dans **Données** > **Entités**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Voir les données d’enrichissement sur la carte client

Le PdV de marque et d’intérêt peut également être consulté sur des cartes client individuelles. Accédez à **Clients** et sélectionnez un profil client. La carte client contient des graphiques pour le PdV de marque ou d’intérêt en fonction des personnes présentes dans le profil démographique de ce client.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Carte client avec données enrichies.":::

## <a name="next-steps"></a>Étapes suivantes

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
