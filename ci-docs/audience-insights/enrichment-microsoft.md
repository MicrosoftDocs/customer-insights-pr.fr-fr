---
title: Enrichir les profils client avec les données de Microsoft
description: Utilisez les données propriétaires de Microsoft pour enrichir vos données client avec les affinités pour des marques et des intérêts.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 45c81a037258e42d8975e0372c104865a9d4cbfe
ms.sourcegitcommit: 2acda3c5adf40bc3f5bbb4b2b4b6c22f84371da7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466621"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Enrichir les profils client avec les affinités pour des marques et des intérêts (préversion)

Utilisez les données propriétaires de Microsoft pour enrichir vos données client avec les affinités pour des marques et des intérêts. Ces affinités sont basées sur les données de personnes présentant des données démographiques similaires à celles de vos clients. Ces informations vous aident à mieux comprendre et segmenter vos clients en fonction de leurs affinités avec des marques et des intérêts spécifiques.

Dans les informations sur l’audience, accédez à **Données** > **Enrichissement** pour [configurer et afficher les enrichissements](enrichment-hub.md).

Pour configurer l’enrichissement des affinités pour les marques, accédez à l’onglet **Découvrir** et sélectionnez **Enrichir mes données** sur l’onglet **Marques**.

Pour configurer l’enrichissement des affinités pour des centres intérêts, accédez à l’onglet **Découvrir** et sélectionnez **Enrichir mes données** sur l’onglet **Intérêts**.

   > [!div class="mx-imgBorder"]
   > ![Vignettes de marques et d’intérêts.](media/BrandsInterest-tile-Hub.png "Vignettes de marques et d’intérêts")

## <a name="how-we-determine-affinities"></a>Détermination des affinités

Nous utilisons les données de recherche en ligne de Microsoft pour trouver des affinités pour des marques et des intérêts dans divers segments démographiques (définis par âge, sexe ou lieu). Le volume de recherche en ligne pour une marque ou un intérêt détermine le degré d’affinité d’un segment démographique, par rapport à d’autres segments, pour cette marque ou cet intérêt.

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

Choisissez jusqu'à cinq marques ou centres d'intérêt en utilisant l'une ou les deux options suivantes :

- **Secteur d’activité** : sélectionnez votre secteur d’activité dans la liste déroulante, puis choisissez parmi les principaux intérêts et marques pour ce secteur d’activité.
- **Choisir les vôtres** : saisissez une marque ou un centre d'intérêt pertinent pour votre organisation, puis choisissez parmi les suggestions correspondantes. Si nous ne répertorions pas une marque ou un intérêt que vous recherchez, envoyez-nous vos commentaires en utilisant le lien **Suggérer**.

### <a name="review-enrichment-preferences"></a>Examiner les préférences d’enrichissement

Passez en revue vos préférences d’enrichissement par défaut et mettez-les à jour si nécessaire.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Capture d’écran de la fenêtre des préférences d’enrichissement.":::

### <a name="select-entity-to-enrich"></a>Sélectionner une entité à enrichir

Sélectionnez **Entité enrichie** et choisissez le jeu de données que vous souhaitez enrichir avec les données d’entreprise de Microsoft. Vous pouvez sélectionner l’entité Client pour enrichir tous vos profils clients ou sélectionner une entité segment pour enrichir uniquement les profils clients contenus dans ce segment.

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

> [!TIP]
> Il existe [six types de statuts](system.md#status-types) pour les tâches/processus. En outre, la plupart des processus [dépendent d’autres processus en aval](system.md#refresh-policies). Vous pouvez sélectionner le statut d’un processus pour afficher des détails sur la progression de toute la tâche. Une fois que vous avez sélectionné **Afficher les détails** pour l’une des tâches du projet, vous trouverez des informations supplémentaires : l’heure de traitement, la dernière date de traitement, ainsi que toutes les erreurs et tous les avertissements associés à la tâche.

## <a name="enrichment-results"></a>Résultats d’enrichissement

Après avoir exécuté le processus d’enrichissement, allez dans **Mes enrichissements** pour examiner le nombre total de clients enrichis et la répartition des marques ou des centres d’intérêt dans les profils client enrichis.

:::image type="content" source="media/my-enrichments.png" alt-text="Aperçu des résultats après l’exécution du processus d’enrichissement.":::

Consultez les données enrichies en sélectionnant **Afficher les données enrichies** dans le graphique. Les données enrichies pour les marques vont dans l’entité **MarqueAffinitéDeMicrosoft**. Les données pour les intérêts se trouvent dans l’entité **InterestAffinityFromMicrosoft**. Vous trouverez également ces entités répertoriées dans le groupe **Enrichissement** dans **Données** > **Entités**.

Vous verrez un graphique avec le nombre de profils clients enrichis au fil du temps et un aperçu de l’entité enrichie. Sélectionnez **Afficher plus** dans la vignette d’aperçu pour ouvrir l’entité enrichie.

## <a name="see-enrichment-data-on-the-customer-card"></a>Voir les données d’enrichissement sur la carte client

Les affinités de marque et d’intérêt peuvent également être consultées sur les cartes client individuelles. Accédez à **Clients** et sélectionnez un profil client. Dans la carte client, vous trouverez des graphiques pour les marques ou les centres d’intérêt pour lesquels les membres du profil démographique de ce client ont une affinité.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Carte client avec données enrichies.":::

## <a name="next-steps"></a>Étapes suivantes

Exploitez vos données client enrichies. Créez des [segments](segments.md) et des [mesures](measures.md) et [exportez les données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
