---
title: Fonctionnalités nouvelles et mises à jour
description: Informations sur les nouvelles fonctionnalités, les améliorations et les corrections de bogues.
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: d06f8be114f558d7adadf2913107c5fd69686875
ms.sourcegitcommit: 9dd767051014e06d8d9f2f616e248573f24df4cb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8843344"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Nouveautés de Dynamics 365 Customer Insights

Nous sommes ravis d’annoncer nos mises à jour les plus récentes ! Cet article résume les fonctionnalités de version préliminaire publique, les améliorations de la disponibilité générale et les mises à jour de fonctionnalités. Pour connaître les plans de fonctionnalités à long terme, consultez les [Plans de versions Dynamics 365 et Power Platform](/dynamics365/release-plans/).

Nous déployons des mises à jour région par région. Ainsi, certaines régions peuvent voir des fonctionnalités avant d’autres. Sauf indication contraire, vous n’avez rien à faire et nous mettrons à jour l’application automatiquement sans interruption.

> [!TIP]
> Pour envoyer et voter sur les demandes de fonctionnalités et les suggestions de produits, accédez au [portail Idées d’application Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="may-2022-updates"></a>Mises à jour de mai 2022

Les mises à jour de mai 2022 incluent de nouvelles fonctionnalités, des améliorations de performances et des corrections de bugs.

### <a name="updated-data-unification-experience"></a>Expérience d'unification des données mise à jour

 L’unification des données vous permet d’unifier des sources de données qui étaient auparavant disparates en un seul jeu de données principal qui en fournit une vue unifiée. Les données peuvent être unifiées sur une ou plusieurs entités. D'abord, [sélectionnez les entités et les champs source](map-entities.md), [supprimez les enregistrements en double](remove-duplicates.md), spécifiez les règles pour les [conditions de correspondance](match-entities.md) et définissez quels [champs à inclure dans les profils clients unifiés](merge-entities.md).

Pour en savoir plus, consultez [Vue d’ensemble de l'unification des données](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Actualisation de la page d'accueil dans Customer Insights

**Accueil** vous guide tout au long du processus de configuration des fonctionnalités clés et fournit une vue d’ensemble des segments, des mesures et des données d’enrichissement. Nous avons actualisé l'expérience pour fournir des informations plus pertinentes en un coup d'œil.

Pour plus d’informations, voir [Explorer Customer Insights](home.md).

### <a name="track-usage-of-a-segment"></a>Suivre l’utilisation d’un segment

Vous pouvez désormais [suivre l'utilisation d'un segment](segments.md#track-usage-of-a-segment) dans les applications qui sont basées sur la même organisation Dataverse connectée à Customer Insights. Pour les [segments Customer Insights utilisés dans les parcours du client de Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), le système vous informe de l’utilisation de ce segment.

### <a name="export-to-criteo"></a>Exporter vers Criteo

Criteo est une plateforme en ligne qui aide les utilisateurs à gérer la publicité numérique. Vous pouvez désormais exporter des segments de profils clients unifiés pour générer des campagnes, fournir un marketing par e-mail et utiliser des groupes de clients spécifiques avec Criteo.

Pour plus d'informations, voir [Exporter des segments vers Criteo (version préliminaire)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Structure de documentation raffinée pour la création d'environnement

Nous avons revu les documents d'aide liés à la création et à la gestion des environnements dans Customer Insights. Les articles sont maintenant regroupés sous le nœud Environnements dans la table des matières. Les articles restructurés fournissent plus de conseils sur les différentes manières de configurer des environnements et ont une structure plus claire. Si vous avez des commentaires à partager, faites-le nous savoir via les contrôles vers la fin des articles d'aide.

Pour plus d’informations, consultez [Procédure : Créer un environnement](create-environment.md).

## <a name="april-2022-updates"></a>Mises à jour d’avril 2022

Les mises à jour d’avril 2022 incluent de nouvelles fonctionnalités, des améliorations de performances et des corrections de bugs.

### <a name="dun--bradstreet-enrichment-preview"></a>Enrichissement de Dun&Bradstreet (version préliminaire)

Dun & Bradstreet fournit des données commerciales, des analyses et des informations aux entreprises. Elle permet aux clients ayant un profil client unifié pour les entreprises d’enrichir leurs données. Les enrichissements incluent des attributs tels que le numéro DUNS, la taille de la société, son emplacement, son secteur d’activité, et plus encore.

Pour plus d’informations, voir [Enrichissement des profils d’entreprise avec Dun & Bradstreet (version préliminaire)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Définir le type de mesure lors de la création d’une nouvelle mesure

Vous pouvez désormais faire la distinction entre les mesures pour les profils individuels et les mesures pour l’ensemble de votre entreprise. Alors que les mesures commerciales s’affichent sur la page d’accueil de Customer Insights, les mesures client sont exposées dans les vues client détaillées.

Pour plus d’informations, voir [Utiliser le générateur de mesures pour créer des mesures à partir de zéro](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Consolidation de la documentation Customer Insights

Nous avons revu nos articles de documentation et supprimé les mentions sur les fonctionnalités d’informations sur l’engagement et l’audience À l’avenir, nous nous référerons systématiquement au nom du produit Customer Insights lorsque nous traiterons des fonctionnalités principales de l’application. Cette modification entraîne également une restructuration importante de la table des matières, de la structure des URL et des chemins d’accès aux fichiers dans le référentiel de documentation sous-jacent. Tous vos signets ou liens existants continuent de fonctionner et redirigent vers les URL mises à jour.

Si vous souhaitez nous faire savoir comment vous percevez ce changement ou si vous remarquez que quelque chose ne fonctionne pas comme prévu, dites-le nous en [soumettant des commentaires pour cette page](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Mises à jour de mars 2022

Les mises à jour de mars 2022 incluent de nouvelles fonctionnalités, des améliorations de performances et des corrections de bugs.

### <a name="liveramp-abilitec-enrichment-preview"></a>Enrichissement AbiliTec LiveRamp (version préliminaire)

LiveRamp fournit une résolution d’identité et une consolidation des données client. Vous pouvez mapper des identifiants personnels dans vos données client avec le graphique d’identité AbiliTec et recevoir des identifiants AbiliTec. Vous pouvez ensuite utiliser ces identifiants pour une meilleure unification de vos données clients.

Pour plus d’informations, voir [Enrichir les profils de clients avec les données d’identité de LiveRamp (version préliminaire)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organiser les segments et les mesures avec des étiquettes et des filtres

Si votre organisation gère de nombreux segments ou mesures, il peut parfois être difficile de trouver le bon. Cette nouvelle fonctionnalité vous permet d’organiser des listes à l’aide d’étiquettes et de colonnes. Il aide à trouver des données rapidement et facilement, ainsi qu’à personnaliser les vues.

Pour plus d’informations, consultez [Utiliser des étiquettes et des colonnes](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Activer le partage de données avec Dataverse lors de l’utilisation de votre propre compte de stockage

Si votre environnement utilise Azure Data Lake Storage pour stocker les données Customer Insights, le partage de données avec Microsoft Dataverse nécessite une configuration supplémentaire.
Auparavant, vous ne pouviez activer le partage de données qu’avec Dataverse lorsque vos données étaient stockées dans notre lac de données géré.

Pour plus d’informations, consultez [Activer le partage de données avec Dataverse à partir de votre propre Azure Data Lake Storage (version préliminaire)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Nouvelles destinations d’exportation : Iterable et Braze

Nous continuons d’étendre notre écosystème de destinations d’exportation avec de nouvelles connexions. Vous pouvez maintenant exporter des segments vers Iterable et Braze pour utiliser leurs services d’activation.

Pour plus d’informations, consultez [Exporter des segments vers Iterable (version préliminaire)](export-iterable.md) et [Exporter des segments vers Braze (version préliminaire)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Améliorations de l’exportation Marketo et Google Ads

La modification des API dans les services connectés entraîne des mises à jour de façon à ce que les connecteurs fonctionnent de manière fiable et fluide. Nous avons publié quelques mises à jour pour les exportations vers les services Marketo et Google Ads :

- Google Ads : la nouvelle version du connecteur d’exportation Google Ads simplifie l’expérience d’authentification et vous permet désormais de créer automatiquement de nouvelles audiences Google Ads. 
- Marketo : la nouvelle version du connecteur d’exportation Marketo prend en charge l’ID Marketo, ce qui vous permet d’éviter la duplication des données, de mettre à jour les enregistrements existants et de créer de nouveaux enregistrements dans Marketo. 

## <a name="february-2022-updates"></a>Mises à jour de février 2022

Les mises à jour de février 2022 incluent de nouvelles fonctionnalités, des améliorations de performances et des corrections de bugs.

### <a name="general-availability-for-prediction-models"></a>Disponibilité générale pour les modèles de prédiction

Les modèles de prédiction prêts à l’emploi, y compris l’**attrition des abonnements**, l’**attrition transactionnelle**, et la **valeur de durée de vie du client (CLV)** sont mis à la disposition générale dans le cadre de Customer Insights. 

Pour plus d’informations, voir [Présentation des prédictions](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Nouvelle source de données : Intégration avec Azure Synapse Analytics (version préliminaire)

Azure Synapse Analytics est un service d’analyse d’entreprise qui accélère l’obtention d’informations entre entrepôts de données et systèmes de Big Data.

Les organisations qui utilisent déjà Azure Synapse Analytics peut ingérer ces données dans Customer Insights. 

Pour plus d’informations, voir [Connecter une source de données Azure Synapse (version préliminaire)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Enrichissement LiveRamp (version préliminaire)

LiveRamp fournit une résolution d’identité et une consolidation des données client. Vous pouvez mapper des identifiants personnels dans vos données client avec le graphique d’identité AbiliTec et recevoir des identifiants AbiliTec. Vous pouvez ensuite utiliser ces identifiants pour une meilleure unification de vos données clients.

Pour plus d’informations, voir [Enrichir les profils de clients avec les données d’identité de LiveRamp (version préliminaire)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Enrichissement des sources de données (version préliminaire)

Utilisez des données provenant de sources telles que Microsoft et d’autres partenaires pour enrichir vos données client avant l’unification des données. Les enrichissements de sources de données permettent de produire des données plus complètes et de meilleure qualité, ce qui peut aider à obtenir de meilleurs résultats une fois que vous avez unifié vos données.

Pour plus d’informations, voir [Enrichissement des sources de données (version préliminaire)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Changer le propriétaire de l’environnement

Bien que plusieurs utilisateurs puissent disposer d’autorisations d’administration dans Customer Insights, un seul utilisateur est propriétaire d’un environnement. Une expérience améliorée vous permet de changer les propriétaires d’un environnement et de revendiquer la propriété si un ancien propriétaire a quitté l’organisation. 

Pour plus d’informations, voir [Changer le propriétaire d’un environnement](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Le processus de préparation des données répertorie les raisons de la corruption des enregistrements corrompus

La préparation des données affiche désormais la raison de la corruption pour tous les champs contenant des données corrompues. Ces informations sont fournies au niveau de l’enregistrement individuel afin de faciliter l’identification. 

Pour plus d’informations, voir [Sources de données endommagées](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Fin de l’aperçu des fonctionnalités de création de rapports dans la fonctionnalité d’informations sur l’engagement

La fonctionnalité en version préliminaire d’informations sur l’engagement de Dynamics 365 Customer Insights a pris fin le 15 février 2022.  
Ce changement signifie que l’expérience d’évaluation de Customer Insights n’inclut plus la possibilité de créer des entonnoirs ni d’autres fonctionnalités de création de rapports.

Nous vous invitons à explorer et à évaluer les nombreuses autres fonctionnalités de [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), la plateforme de données client (CDP) de Microsoft.    
 
Pendant une période de transition, les participants à la version préliminaire auront toujours accès à certaines capacités et fonctionnalités de la version préliminaire :

- Obtenir du code pour instrumenter un site web ou une application mobile 
- Afficher les événements et les propriétés d’événement 
- Améliorer les profils unifiés avec des événements ingérés et raffinés pour bénéficier pleinement de la valeur des données clients
  
Pendant la période de transition, les événements capturés seront toujours diffusés vers le Data Lake connecté. Une fois que cette fonctionnalité est désactivée, le partage de données s’arrêtera et aucun nouvel événement ne sera envoyé vers le stockage connecté.
Contactez directement l’équipe chargée de votre compte Microsoft si vous avez des questions sur la fin de la version préliminaire de la fonctionnalité. L’équipe chargée de votre compte vous tiendra au courant des prochains lancements. 

## <a name="january-2022-updates"></a>Mises à jour de janvier 2022

Les mises à jour de janvier 2022 incluent de nouvelles fonctionnalités, des améliorations de performances et des corrections de bugs.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analyse des sentiments des commentaires de vos clients

Customer Insights fournit une nouvelle fonctionnalité basée sur l'IA pour synthétiser le sentiment des clients et identifier des aspects commerciaux spécifiques comme opportunités d'améliorations ciblées. En analysant les commentaires écrits de vos clients, vous pouvez obtenir des informations précises à moindre coût. L’analyse des sentiments alimentée par des modèles de traitement du langage naturel (NLP) qui génèrent deux informations dérivées pour chaque ID client. Un score de sentiment (de -5 à 5) et une liste des aspects commerciaux applicables. 

Pour plus d’informations, voir [Analyser le sentiment dans les commentaires des clients (version préliminaire)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]