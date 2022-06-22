---
title: Enrichir les profils clients avec les marques et les données d'intérêts de Microsoft
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
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953762"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Enrichir les profils clients avec des affinités et le partage de voix (version préliminaire)

Utilisez les données propriétaires de Microsoft pour enrichir vos données clients avec des affinités de marques, des affinités d’intérêt et le partage de voix (PdV). Ces affinités et le PdV sont basés sur les données des personnes présentant des caractéristiques démographiques similaires à celles de vos clients. Ces informations vous aident à mieux comprendre et segmenter vos clients en fonction de leurs affinités ou du PdV pour des marques et des intérêts spécifiques.

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

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement

1. Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.

   - Pour configurer les affinités de marque et l’enrichissement de PdV, sélectionnez **Enrichir mes données** sur la vignette **Marques**.

   - Pour configurer les affinités d'intérêt et l’enrichissement de PdV, sélectionnez **Enrichir mes données** sur la vignette **Intérêts**.

   > [!div class="mx-imgBorder"]
   > ![Vignettes de marques et d’intérêts.](media/BrandsInterest-tile-Hub.png "Vignettes de marques et d’intérêts")

1. Passez la synthèse en revue et sélectionnez **Suivant**.

1. Pour changer de pays ou de région, sélectionnez **Changer** en regard de **Pays/Région**. Dans le volet **Pays/Paramètres régionaux**, choisissez un.e [pays/région pris.e en charge](#supported-countriesregions), puis sélectionnez **Appliquer**.

   > [!NOTE]
   > Lorsque vous choisissez vos propres marques, le système fournit des suggestions en fonction du pays ou de la région sélectionnés. Lorsque vous choisissez un secteur d’activité, vous obtenez les marques ou centres d’intérêt les plus pertinents en fonction du pays ou de la région sélectionné.

1. Choisissez jusqu’à cinq marques ou centres d’intérêt en utilisant l’une ou les deux options suivantes :

   - **Secteur d’activité** : sélectionnez votre secteur d’activité dans la liste déroulante, puis choisissez parmi les principaux intérêts et marques pour ce secteur d’activité.
   - **Choisir les vôtres** : saisissez une marque ou un centre d’intérêt pertinent pour votre organisation, puis choisissez parmi les suggestions correspondantes. Si nous ne répertorions pas une marque ou un intérêt que vous recherchez, envoyez-nous vos commentaires en utilisant le lien **Suggérer**.

1. Sélectionnez **Suivant** et passez en revue vos préférences d'enrichissement par défaut et mettez-les à jour si nécessaire.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Capture d’écran de la fenêtre des préférences d’enrichissement.":::

1. Cliquez sur **Suivant**.

1. Sélectionnez le **Jeu de données client**, puis choisissez le profil ou segment que vous souhaitez enrichir avec les données démographiques à partir de Microsoft. L’entité *Client* enrichit tous vos profils clients tandis qu'un segment enrichit uniquement les profils clients contenus dans ce segment.

1. Cliquez sur **Suivant**.

1. Mappez vos champs de votre entité client unifiée aux données Microsoft.

   > [!NOTE]
   > Au moins les attributs Date de naissance ou Sexe sont requis. Le pays/la région et au moins la ville (et l'état/la province) ou le code postal sont requis. Nous vous recommandons de convertir la date de naissance en type DateTime lors de l'ingestion des données. Sinon, il peut s’agir d’une chaîne au format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) « aaaa-MM-jj » ou « aaaa-MM-jjTHH:mm:ss ».

1. Sélectionnez **Suivant** pour terminer le mappage de champs.

1. Fournissez un nom pour l’enrichissement. Le **nom de l’entité de sortie** est sélectionné automatiquement.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Page de révision des intérêts et d’affectation d’un nom.":::

1. Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.

1. Sélectionnez **Exécuter** pour démarrer le processus d'enrichissement ou fermer pour revenir à la page **Enrichissements**.

   Lors de l’enrichissement des profils, nous enrichirons tous les profils client pour lesquels nous obtenons des données pour les marques et les intérêts sélectionnés, y compris les profils qui ne se trouvent pas dans le pays ou la région sélectionné. Par exemple, si vous avez sélectionné l’Allemagne, nous enrichirons les profils situés aux États-Unis si des données sont disponibles pour les marques et les intérêts sélectionnés aux États-Unis.

## <a name="enrichment-results"></a>Résultats d’enrichissement

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Aperçu des résultats après l’exécution du processus d’enrichissement.":::

Les résultats comprennent les graphiques **Niveau d'affinité** ou **Partage de voix**.

Les entités créées à partir des enrichissements sont listées sous le groupe **Enrichissement** dans **Données** > **Entités**. Les données enrichies pour les marques vont aux entités **BrandAffinityFromMicrosoft** et **BrandShareOfVoiceFromMicrosoft**. Les données relatives aux intérêts se trouvent dans les entités **InterestAffinityFromMicrosoft** et **InterestShareOfVoiceFromMicrosoft**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Voir les données d’enrichissement sur la carte client

Le PdV de marque et d’intérêt peut également être consulté sur des cartes client individuelles. Accédez à **Clients** et sélectionnez un profil client. La carte client contient des graphiques pour le PdV de marque ou d’intérêt en fonction des personnes présentes dans le profil démographique de ce client.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Carte client avec données enrichies.":::

## <a name="next-steps"></a>Étapes suivantes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
