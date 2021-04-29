---
title: Fonctionnalités nouvelles et à venir
description: Informations sur les nouvelles fonctionnalités, les améliorations et les corrections de bogues.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 2159481f9355de738a7b457dcf0849a45c3e08db
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896232"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Nouveautés de la fonctionnalité d’informations sur l’audience de Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Nous sommes ravis d’annoncer nos mises à jour les plus récentes ! Cet article résume les fonctionnalités de version préliminaire publique, les améliorations de la disponibilité générale et les mises à jour de fonctionnalités. Pour connaître les plans de fonctionnalités à long terme, consultez les [Plans de versions Dynamics 365 et Power Platform](/dynamics365/release-plans/).

Nous déployons des mises à jour région par région. Ainsi, certaines régions peuvent voir des fonctionnalités avant d’autres. Sauf indication contraire, vous n’avez rien à faire et nous mettrons à jour l’application automatiquement sans interruption.

> [!TIP]
> Pour envoyer et voter sur les demandes de fonctionnalités et les suggestions de produits, accédez au [portail Idées d’application Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="march-2021-updates"></a>Mises à jour de mars 2021

Les mises à jour de mars 2021 comprennent plusieurs fonctionnalités, mises à niveau des performances et corrections de bogues.

### <a name="activities"></a>Activités

- **Assistant d’activité et types sémantiques** : nous avons amélioré et mis à jour notre expérience de mappage d’activités pour guider et simplifier la création de mappage d’activités. Dans cette nouvelle expérience, les utilisateurs bénéficient d’une expérience guidée pour les aider à terminer chaque étape du processus. Dans l’étape de mappage d’activités, en plus de choisir parmi plusieurs types d’activités, l'utilisateur peut choisir de mapper sémantiquement les données pour *Abonnement* et/ou *SalesOrderLine* aux schémas standard de l’industrie, qui peuvent être utilisés pour la consommation en aval.    
  Pour plus d’informations, voir [Activités client](activities.md).

### <a name="data-ingestion"></a>Ingestion des données

- **Se connecter aux sources de données locales à l’aide des flux de données et des passerelles Power Platform** : nous sommes ravis de vous annoncer la version préliminaire des flux de données Power Platform et de la connectivité locale en utilisant des passerelles de Customer Insights avec un environnement Power Platform ou Dataverse associé. Toute nouvelle source de données créée dans un environnement Customer Insights avec un environnement Dataverse lié utilisera par défaut les flux de données Power Platform qui incorporent la connectivité de données locale et un ensemble complet de connecteurs et de fonctionnalités de transformation.

### <a name="extensibility"></a>Extensibilité

- **Exportations organisées en connexions et exportations** : nous avons changé le nom de la page **Destinations d’exportation** en **Connexions** et ajouté une page distincte pour **Exportations**. Dans le cadre de cette mise à jour, nous convertirons les exportations existantes en paires d’une connexion et d’une exportation en utilisant cette connexion. Les administrateurs voient maintenant plus clairement les données sortantes de la page **Connexions**. Tous les rôles d’utilisateur ont accès à la page **Exportations**, mais seuls les administrateurs peuvent choisir d’autoriser les contributeurs à modifier des exportations spécifiques avec des connexions partagées.     
  Pour plus d’informations, voir [Présentation des connexions](connections.md) et [Présentation des exportations](export-destinations.md).

- **Exporter des segments vers Campaign Monitor** : ous avons étendu nos destinations d’exportation pour inclure Campaign Monitor. Vous pouvez maintenant exporter des segments de Customer Insights vers les listes Campaign Monitor et les utiliser comme référence pour vos campagnes marketing.    
   Pour plus d’informations, voir [Exporter vers Campaign Monitor](export-campaign-monitor.md).

- **Exporter des segments vers Constant Contact** : nous avons étendu nos destinations d’exportation pour inclure Constant Contact. Vous pouvez maintenant exporter des segments de Customer Insights vers les listes Constant Contact et les utiliser comme référence pour vos campagnes marketing.   
   Pour plus d’informations, voir [Exporter vers Constant Contact](export-constant-contact.md).

- **Exporter des segments vers RollWorks** : nous avons étendu nos destinations d’exportation pour inclure RollWorks. Vous pouvez maintenant exporter des segments de Customer Insights vers les audiences RollWorks et les utiliser comme référence pour vos publicités B2B.    
   Pour plus d’informations, voir [Exporter vers RollWorks](export-rollworks.md).

- **Exporter des segments vers Snapchat** : nous avons étendu nos destinations d’exportation pour inclure Snapchat. Vous pouvez maintenant exporter des segments de Customer Insights vers les audiences Snapchat et les utiliser comme référence pour vos publicités.     
   Pour plus d’informations, voir [Exporter vers Snapchat](export-snapchat.md).

### <a name="predictions"></a>Prédictions

- **Utiliser des filtres de produit dans les recommandations de produit prédictives** : nous avons ajouté la fonctionnalité permettant d’utiliser des filtres de produit dans notre modèle de recommandation de produits. Vous pouvez maintenant créer une prédiction qui n’utilise qu’un sous-ensemble de vos produits.    
   Pour plus d’informations, voir [Configurer les filtres de produit](predict-product-recommendation.md#configure-product-filters).

- **Créer des segments à partir des prédictions de modèle** : nous avons ajouté une manière rapide de créer des segments en utilisant les résultats d’un modèle de prédiction. À partir de la page de résultats du modèle, vous pouvez facilement créer un nouveau segment en sélectionnant la nouvelle option **Créer un segment**.    
  Pour plus d’informations, voir [Créer un segment basé sur un modèle de prédiction](prediction-based-segment.md).

- **Explications pour les recommandations de produits** : nous avons ajouté des informations expliquant les facteurs clés appris par le modèle d’IA pour générer des recommandations de produits, et dans quelle mesure ces facteurs contribuent aux recommandations de produits. Ces informations sont ajoutées à l’écran de résultats du modèle.    
   Pour plus d’informations, consultez [Passer en revue le statut et les résultats d’une prédiction](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Mises à jour de février 2021

Les mises à jour de février 2021 comprennent plusieurs fonctionnalités, améliorations des performances et corrections de bogues.

#### <a name="extensibility"></a>Extensibilité

- **Exporter des segments vers AdRoll**

  Nous avons étendu nos destinations d’exportation pour inclure AdRoll. Vous pouvez désormais exporter des segments de Customer Insights vers des audiences AdRoll et les utiliser comme référence pour votre publicité. Pour plus d’informations, consultez [Connecteur pour AdRoll](export-adroll.md).

#### <a name="segments"></a>Segments
 
- **Dupliquer un segment**
  
  Pour créer un nouveau segment basé sur un segment existant, vous pouvez désormais dupliquer un segment et modifier le segment dupliqué pour l’affiner davantage. 

- **Ajouter des attributs supplémentaires à un segment**

  Vous pouvez désormais inclure des attributs dans votre segment final, même si ces attributs ne font pas partie du profil client. Par exemple, incluez les ID d’abonnement dans un segment même s’il fait partie de l’entité abonnement qui a une relation M : 1 avec l’entité client. Tant que l’attribut appartient à une entité liée à l’entité client, vous pouvez désormais inclure ces attributs.  

#### <a name="predictions"></a>Prédictions

- **Créer des recommandations de produit prédictives**

  Comprendre ce que les clients souhaitent acheter est l’une des premières étapes nécessaires pour améliorer les revenus de l’entreprise et fidéliser les clients grâce à la personnalisation et à l’engagement. Fournir des recommandations pour des produits qui ne correspondent pas à ce qui intéresse votre client peut créer un sentiment de déconnexion entre le client et votre entreprise, et finalement limiter le revenu potentiel global et l’expérience d’un client. 

  En utilisant vos propres données, vous pouvez désormais créer des prédictions pour les produits que vos clients sont susceptibles d’acheter à l’avenir. Pour plus d’informations, voir [Prédiction de recommandation de produit](predict-product-recommendation.md).

#### <a name="system-administration"></a>l’administration du système ;

- **L’environnement de copie prend en charge plus de types de sources de données**

  Les administrateurs peuvent copier les configurations d’environnement dans un nouvel environnement de la même organisation. Cette fonctionnalité étend la fonctionnalité d’environnement de copie pour les cas dans lesquels les sources de données basées sur un lac de données Common Data Service ou un dossier Common Data Model sont utilisés.

## <a name="january-2021-updates"></a>Mises à jour de janvier 2021

Les mises à jour de janvier 2021 comprennent plusieurs fonctionnalités, améliorations des performances et corrections de bogues.

#### <a name="extensibility"></a>Extensibilité

- **Fonctionnalité étendue et performances améliorées pour l’exportation SFTP** Vous pouvez désormais exporter toutes les entités de sortie de Customer Insights vers un hôte SFTP. Auparavant, l’exportation était limitée aux entités de segment. De plus, les performances de l’exportation SFTP permettent plus de volume de données en moins de temps, en fonction des performances de votre hôte SFTP.    
  Pour plus d’informations, consultez [Connecteur pour SFTP (version préliminaire)](export-sftp.md).  

#### <a name="segments"></a>Segments

- **Machine Learning propulsé des segments suggérés pour améliorer les métriques** Il existe une nouvelle façon de découvrir et de créer des segments. Le système utilise un modèle IA pour suggérer des segments qui peuvent aider à améliorer une indicateur de performance clé (mesure) que vous suivez déjà. Nous montrons l’étendue de l’influence des attributs que vous sélectionnez sur une mesure ou un autre attribut principal. Ces informations permettent de trouver des segments potentiels qui présentent des opportunités.    
  Pour plus d’informations, voir [Segments suggérés (version préliminaire)](suggested-segments.md).

#### <a name="data-unification"></a>Unification des données

- **Expérience de correspondance améliorée** Dans la zone d’unification des données, l’expérience de match a été mise à jour. Il vous permet de configurer et d’afficher les règles de correspondance, y compris des statistiques détaillées pour expliquer plus en détail le fonctionnement de la correspondance. Il existe des options pour désactiver une règle de correspondance afin qu’elle ne soit plus active tout en conservant la configuration, les règles de correspondance par glisser-déplacer, etc.
  Pour plus d’informations, voir [Faire correspondre les entités](match-entities.md).

- **La sortie de déduplication du processus de correspondance est disponible en tant qu’entité** La sortie du processus de déduplication du processus de correspondance est maintenant écrite dans une entité distincte pour une analyse plus approfondie. Cette entité comprend les champs utilisés dans le processus de déduplication et l’enregistrement gagnant et les enregistrements alternatifs correspondants qui sont fusionnés avec l’enregistrement gagnant.
  Pour plus d’informations, voir [Sortie de déduplication en tant qu’entité](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Administration système

- **Partagez vos données en toute transparence avec Microsoft Dataverse** Vous pouvez désormais partager les résultats de Customer Insights avec les applications Microsoft Dataverse utilisant le lac de données géré Microsoft Dataverse . Une fois que vous associez un environnement Dataverse avec Customer Insights, vous avez la possibilité d’activer le partage de données.
  Pour plus d’informations, voir [Gérer les environnements](manage-environments.md).


## <a name="december-2020-updates"></a>Mises à jour de décembre 2020

Les mises à jour de décembre 2020 comprennent plusieurs fonctionnalités, mises à niveau des performances et corrections de bogues.

### <a name="new-and-updated-features-in-december-2020"></a>Fonctionnalités nouvelles et mises à jour en décembre 2020

#### <a name="data-enrichment"></a>Enrichissement des données

- **Amélioration des enrichissements d’affinité de marque et d’intérêt**
  
  Nous avons simplifié nos scores d’affinité pour les rendre plus faciles à comprendre et à utiliser. Vous pouvez désormais identifier rapidement les clients en fonction de leur affinité pour une marque ou un intérêt donné.

  De plus, nous avons ajouté de nouvelles options de configuration pour mieux contrôler la manière dont vous souhaitez que vos profils clients soient enrichis. 

  Pour plus d’informations, consultez [Enrichissement des profils clients avec des affinités de marque et d’intérêt](enrichment-microsoft.md).

- **Contrôlez les profils à enrichir**

  Vous pouvez désormais enrichir uniquement un sous-ensemble de vos profils client avec la possibilité de sélectionner une entité de segment au lieu de l’entité client par défaut. Créez un segment avec les profils clients que vous souhaitez enrichir et sélectionnez-le dans la configuration d’enrichissement de votre client jeu de données.
  Cette fonctionnalité n’est actuellement disponible que pour les enrichissements fournis par Experian et HERE Technologies. Nous allons bientôt permettre à cette capacité d’enrichir davantage.

  Pour plus d’informations, voir [Enrichir les profils clients avec les données démographiques d’Experian](enrichment-experian.md) ou [Enrichissement des profils clients avec HERE Technologies](enrichment-here.md).

#### <a name="extensibility"></a>Extensibilité

- **Activer vos segments via Autopilot**

  Exportez des segments vers Autopilot et utilisez-les à des fins de marketing. Pour plus d’informations, consultez [Connecteur pour Autopilot (version préliminaire)](export-autopilot.md).

- **Activer vos segments via SendGrid**

  Exportez des segments vers SendGrid et utilisez-les à des fins de marketing. Pour plus d’informations, consultez [Connecteur pour SendGrid](export-sendgrid.md).

#### <a name="system-administration"></a>Administration système

- **Expérience de gestion de l’environnement mise à jour**
  
  Vous pouvez désormais créer, modifier, supprimer et réinitialiser des environnements directement à partir du sélecteur d’environnement dans l’en-tête de l’application. 
  
  De plus, l’environnement que vous utilisez sera épinglé en haut du panneau d’environnement afin que vous n’ayez plus besoin de le rechercher.

  Pour plus d’informations, voir [Gérer les environnements](manage-environments.md).

## <a name="november-2020-updates"></a>Mises à jour de novembre 2020

Les mises à jour de novembre 2020 comprennent plusieurs fonctionnalités, mises à niveau des performances et corrections de bogues.

### <a name="new-and-updated-features-in-november-2020"></a>Fonctionnalités nouvelles et mises à jour en novembre 2020

#### <a name="data-enrichment"></a>Enrichissement des données

- **Importer vos propres données d’enrichissement via l’importation personnalisée SFTP (Secure File Transfer Protocol)**
  
  L’importation personnalisée SFTP vous permet d’importer des données d’enrichissement qui ne doivent pas passer par le processus d’unification des données. En savoir plus sur l’importation personnalisée SFTP.

  Pour plus d’informations, consultez [Enrichir les profils client avec des données personnalisées (version préliminaire)](enrichment-SFTP-custom-import.md).
 
- **Enrichir vos données client avec les données de localisation de HERE Technologies**

  Avec les services d’enrichissement de données de HERE Technologies, vous pouvez avoir une idée plus précise de la localisation de vos clients avec la normalisation de l’adresse, l’extraction de la latitude et la longitude, etc. En savoir plus sur l’enrichissement avec HERE Technologies.

  Pour plus d’informations, consultez [Enrichissement des profils client avec HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Unification des données

- **Flexibilité pour activer le profilage des données sur les entités et les champs sélectionnés à partir de votre compte de stockage**

  Vous pouvez indiquer pour quels champs et entités de données d’un dossier Common Data Model de votre compte de stockage Azure Data Lake vous souhaitez activer le profilage des données dans le cadre du processus d’ingestion des données.

  Pour plus d’informations, consultez [Se connecter à un dossier Common Data Model](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Extensibilité

- **Activer vos segments via Google Ads**

  Exportez des segments à partir des listes d’audience Google Ads et utilisez ces listes pour faire de la publicité sur Google Search, le Réseau Display de Google, YouTube et Gmail. En savoir plus sur l’activation de vos segments via Google Ads.

  Pour plus d’informations, consultez [Connecteur pour Google Ads](export-google-ads.md).

- **Activer vos segments via Marketo**

  Exportez des segments vers les audiences Marketo et utilisez ces audiences pour l’automatisation du marketing. En savoir plus sur l’activation de vos segments via Marketo. 

  Pour plus d’informations, consultez [Connecteur pour Marketo](export-marketo.md).

- **Activer vos segments via DotDigital**

  Exportez des segments vers DotDigital et utilisez-les à des fins de marketing. En savoir plus sur l’activation de vos segments via DotDigital. 

  Pour plus d’informations, consultez [Connecteur pour DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Prédictions

- **Prédire l’attrition transactionnelle**

  La fonction de prédiction de l’attrition des transactions vous permet, sans l’aide d’un scientifique des données, de prédire la probabilité qu’un client arrête d’acheter des produits ou des services.  En utilisant le score de prédiction, vous pouvez combiner d’autres informations sur vos clients, comme la valeur du client, pour créer des segments de clients à haut risque d’attrition ou à forte valeur ajoutée. Utilisez ce segment pour cibler directement des clients via des activités marketing, un support client et d’autres scénarios afin de réduire le risque d’attrition.
 
  Configurez la définition de l’attrition comme une fenêtre de temps spécifique à votre entreprise et définissez quand les clients sont considérés comme perdus. Par exemple, une épicerie peut souhaiter considérer un client comme perdu s’il n’a rien acheté au cours des 30 derniers jours.
 
  Au fur et à mesure que vous continuez à créer la prédiction, nous vous guiderons à travers les données nécessaires et nous vous permettrons de mapper les données de votre entreprise sur les champs requis pour prédire le taux d’attrition de vos clients. Vous pouvez également définir un calendrier pour entraîner à nouveau le modèle en fonction des nouvelles informations de votre système afin de vous adapter à l’évolution de la situation commerciale.
 
  Pour plus d’informations, consultez [Prédiction de l’attrition transactionnelle (version préliminaire)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Administration du système

- **Réinitialiser l’environnement**

  Réinitialisez tout dans un environnement d’une instance sélectionnée pour repartir à zéro.

  Pour plus d’informations, consultez [Réinitialiser un environnement existant](manage-environments.md#reset-an-existing-environment).


- **Se connecter à votre compte de stockage Azure Data Lake à l’aide d’un principal de service**

  Écrivez la sortie des données et lisez les données de votre compte de stockage à l’aide d’un principal de service Azure. Les connexions existantes du compte de stockage peuvent continuer à utiliser la clé de compte. Elles offrent également une option de mise à niveau pour utiliser le principal de service à l’avenir. Les nouvelles connexions seront basées sur la méthode d’authentification du principal de service pour votre compte de stockage.

  Pour plus d’informations, consultez [Se connecter à un compte Azure Data Lake Storage Gen2 avec un principal de service Azure pour les informations sur l’audience](connect-service-principal.md).

## <a name="october-2020-updates"></a>Mises à jour d’octobre 2020

Les mises à jour d’octobre 2020 comprennent plusieurs fonctionnalités, mises à niveau des performances et corrections de bogues.

### <a name="new-and-updated-features-in-october-2020"></a>Fonctionnalités nouvelles et mises à jour en octobre 2020

#### <a name="extensibility"></a>Extensibilité

- **Exporter vers Mailchimp**

Exportez des segments vers des listes d’audience existantes dans Mailchimp pour offrir une expérience de messagerie personnalisée à vos clients.

Pour plus d’informations, consultez [Connecteur pour Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Enrichissement des données

- **Dédupliquer les enregistrements sources dans une entité de mise en correspondance**

Spécifiez les règles de déduplication sur les entités utilisées dans le processus de mise en correspondance pour identifier les enregistrements en double. Fusionnez-les en un seul enregistrement et liez tous les enregistrements sources à cet enregistrement fusionné. Cet enregistrement dédupliqué sera ensuite utilisé dans le processus de mise en correspondance entre entités.

Pour plus d’informations, consultez [Définir la déduplication sur une entité de mise en correspondance](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>l’administration du système ;

- **Orchestration : nouvelle option d’actualisation de la fusion**

Jusqu’à aujourd’hui, lorsque vous exécutez le processus de fusion, le système exécutait tous les processus en aval qui dépendent de la fusion et des processus suivants. Vous pouvez maintenant vérifier la sortie du processus de fusion (l’entité de client unifié) avant de l’utiliser dans le traitement en aval comme les segments ou les mesures.
Sur la page de fusion, vous pouvez maintenant choisir d’exécuter uniquement l’étape de fusion et d’exécuter uniquement ce processus. Pour actualiser également tous les processus en aval, vous pouvez choisir d’exécuter la fusion et les processus en aval. 

## <a name="september-2020-updates"></a>Mises à jour de septembre 2020

Les mises à jour de septembre 2020 comprennent plusieurs fonctionnalités, mises à niveau des performances et corrections de bogues.

### <a name="new-and-updated-features-in-september-2020"></a>Fonctionnalités nouvelles et mises à jour en septembre 2020

#### <a name="activities"></a>Activités

- **Prédiction intelligent de la sémantique des attributs**

Cette nouvelle fonctionnalité prédit les types sémantiques d’attributs d’entrée qui sont transmis au processus d’unification des données. Elle utilise des modèles de Machine Learning qui améliorent la précision et font gagner du temps.

#### <a name="enrichments"></a>Enrichissements

- **Enrichissement des données démographiques d’Experian**

L’enrichissement des données démographique d’Experian est désormais disponible en version préliminaire. Experian est un leader mondial en marketing et reporting dans le domaine du crédit aux consommateurs et aux entreprises. Avec les [Services d’enrichissement de données d’Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), vous pouvez approfondir votre compréhension de vos clients en enrichissant les profils clients avec des données démographiques telles que la taille du ménage, le revenu, etc.

Pour utiliser cette fonctionnalité, vous devez disposer d’un abonnement Experian actif.

Pour plus d’informations, voir [Enrichir les profils des clients avec les données démographiques d’Experian](enrichment-experian.md)


#### <a name="system-administration"></a>l’administration du système ;

- **Volet Détails des tâches**

Le volet de détails des tâches vous permet d’afficher des détails sur les tâches exécutées par le système. C’est un moyen pratique d’identifier les problèmes de configuration et de trouver des solutions.
Consultez les messages d’erreur pour voir comment résoudre les problèmes potentiels.
 
- **Traitement des informations ajoutées à d’autres pages**

Cette amélioration ajoute des informations concernant le statut des entités dans les pages **Entités** et **Clients**.
 
En outre, vous pouvez trouver sur ces deux pages des détails sur la progression des processus, ainsi que les détails des tâches.

- **Améliorations de la page de statut du système**

Nous avons amélioré la structure du tableau des détails du statut dans **Système** > **Statut** lors de l’examen des exportations de données.
 
De plus, les erreurs de la colonne **Détails** sont désormais plus détaillées et exploitables. 
 
- **Annuler ramène le travail à son état précédent**

Lorsque vous annulez une tâche, par exemple, dans le processus de mise en correspondance, elle revient à son dernier état. Par exemple, si le processus de lise en correspondance s’est terminé hier et que vous l’annulez aujourd’hui, il reviendra à l’état de réussite d’hier.


## <a name="august-2020-updates"></a>Mises à jour d’août 2020

Les mises à jour d’août 2020 comprennent plusieurs fonctionnalités, mises à niveau des performances et corrections de bogues.

### <a name="new-and-updated-features-in-august-2020"></a>Fonctionnalités nouvelles et mises à jour en août 2020

#### <a name="data-unification"></a>Unification des données

- **Expérience améliorée pour la phase de carte lors de l’unification des données**

  L’expérience de la phase de carte dans le processus d’unification des données vous permet de sélectionner des entités, des attributs et de définir la sémantique de manière plus transparente.

  Les modifications sont notamment :
  
  - Moins d’interactions requises pour ajouter des entités et des champs
  - Amélioration des fonctionnalités de recherche sur la page de la carte
  - Identification visuelle et simple du type de champ suggéré

#### <a name="enrichment"></a>Enrichissement

- **Enrichissement des affinités d’intérêt disponible sur plus de marchés**

  Nous étendons la disponibilité de l’enrichissement des affinités d’intérêt au-delà des États-Unis à cinq autres marchés : le Canada, l’Australie, le Royaume-Uni, la France et l’Allemagne. Avec cette extension, vous pouvez enrichir vos données clients avec plus d’intérêts applicables à ces marchés. Nous enrichirons également les profils de vos clients situés sur ces marchés en utilisant les données propriétaires locales de Microsoft.
  Pour plus d’informations, consultez [Enrichissement des profils clients avec des affinités de marque et d’intérêt](enrichment-microsoft.md)


## <a name="july-2020-updates"></a>Mises à jour de juillet 2020

Les mises à jour de juillet 2020 comprennent plusieurs fonctionnalités, améliorations des performances et corrections de bogues.

### <a name="new-and-updated-features-in-july-2020"></a>Fonctionnalités nouvelles et mises à jour en juillet 2020

#### <a name="extensibility"></a>Extensibilité

- **Déclencheur Power Automate pour le processus d’unification**

  Nous avons étendu nos déclencheurs pour Power Automate et nous permettons de créer une notification ou une action lorsqu’une actualisation du processus d’unification (carte, correspondance, fusion) est terminée.    
  Pour plus d’informations, voir [Connecteur Power Automate](export-power-automate.md).

#### <a name="enrichment"></a>Enrichissement

- **Enrichissement des affinités de marques disponible sur plus de marchés**

  Nous étendons la disponibilité de l’enrichissement des affinités de marques au-delà des États-Unis à cinq autres marchés : le Canada, l’Australie, le Royaume-Uni, la France et l’Allemagne. Avec cette extension, vous pouvez enrichir vos données clients avec des marques locales sur ces marchés. Nous enrichirons également les profils de vos clients situés sur ces marchés en utilisant les données propriétaires locales de Microsoft.
  Pour plus d’informations, consultez [Enrichissement des profils clients avec des affinités de marque et d’intérêt](enrichment-microsoft.md)

## <a name="june-2020-updates"></a>Mises à jour de juin 2020

Les mises à jour de juin 2020 comprennent plusieurs fonctionnalités, améliorations des performances et corrections de bogues.

### <a name="new-and-updated-features-in-june-2020"></a>Fonctionnalités nouvelles et mises à jour en juin 2020

#### <a name="enrichment"></a>Enrichissement

- **Enrichissement avec les données d’entreprise de Leadspace**
  
  Définissez des champs dans les profils client unifiés qui sont utilisés pour rechercher des données d’entreprises associées à partir de Leadspace. Après l’exécution du processus d’enrichissement, les profils B2B sont enrichis de plus d’attributs, notamment la taille de l’entreprise, l’emplacement, le secteur d’activité, etc.    
  Cette collaboration vous permet d’améliorer la qualité de vos données avec l’apport de services tiers. Pour utiliser cet enrichissement, vous aurez besoin d’une licence Leadspace pour accéder à ses données d’entreprise B2B. Le système utilisera cette licence pour maintenir vos données enrichies en continu.    
  Pour plus d’informations, consultez [Enrichissement des profils d’entreprise avec Leadspace](enrichment-leadspace.md).

- **Page du Centre d’enrichissement**

  Tous les enrichissements de données disponibles auprès de fournisseurs d’enrichissement propriétaires et tiers sont configurés au même endroit. La configuration de l’enrichissement des données est une expérience transparente gérée à partir d’un emplacement commun.    
  Pour plus d’informations, consultez [Enrichissement des profils clients](enrichment-hub.md).

- **Enrichissement de l’affinité de marque et d’intérêt distincts**

  Les affinités de marques et d’intérêt sont désormais disponibles en deux enrichissements indépendants. La séparation des enrichissements vous donne la flexibilité de les configurer et de les gérer individuellement, en fonction des exigences ou des besoins de votre entreprise.    
  Pour plus d’informations, consultez [Enrichissement des profils clients avec des affinités de marque et d’intérêt](enrichment-microsoft.md).

#### <a name="extensibility"></a>Extensibilité

- **URL interactives pour les activités unifiées sur le complément de carte client Dynamics 365**

  Les activités unifiées dans le complément de carte client affichent maintenant des URL interactives si ces URL ont été définies lors de la configuration des activités.    
  Pour plus d’informations, voir [Complément de carte client](customer-card-add-in.md).

- **Affinités de marque et d’intérêt disponibles sur le complément de carte client Dynamics 365**

  Un nouveau contrôle sur le complément de carte client Dynamics 365 vous permet d’afficher des enrichissements de marque et d’intérêt sur vos contacts dans les applications d’engagement client dans Dynamics 365.    
  Pour plus d’informations, voir [Complément de carte client](customer-card-add-in.md).

- **Déclencheurs Power Automate supplémentaires**

  Nous avons étendu nos déclencheurs pour Power Automate et avons ajouté les déclencheurs suivants :
  - Recevez une notification ou effectuez une action lorsqu’une actualisation complète automatisée (sources de données, unification, segments, mesures, exportations) se termine
  - Définissez un seuil pour une mesure commerciale. Par exemple, vous pouvez créer une notification qui est envoyée lorsque le seuil défini est dépassé. De plus, le déclencheur apporte des informations qui vous permettent de créer des flux de travail plus complexes dans Power Automate.    
  Pour plus d’informations, voir [Connecteur Power Automate](export-power-automate.md).

- **Exporter vers Facebook Ads Manager**
  
  Cette fonctionnalité vous permet d’exporter des segments vers Facebook Ads Manager. Les segments sont exportés en tant qu’audiences personnalisées pour utiliser des profils client unifiés dans les campagnes marketing et les publicités Facebook. Les audiences personnalisées sont également utilisables pour créer des campagnes sur Instagram via Facebook Ads Manager.    
  Pour plus d’informations, consultez [Connecteur pour Facebook Ads Manager](export-facebook.md).

#### <a name="predictions"></a>Prédictions

- **Prédiction de la résiliation d’abonnement**

  Suivez une expérience guidée pour créer une prédiction de la résiliation dans des domaines d’abonnement tels que les services cloud, l’adhésion des clients et d’autres secteurs. 

  La fonction de prédiction de la résiliation d’abonnement vous permet de prédire la probabilité qu’un client arrête d’utiliser des produits ou services basés sur un abonnement sans engager un data scientist. En utilisant le score de prédiction, vous pouvez combiner d’autres informations sur vos clients pour créer des segments à haut risque d’attrition. Avec l’aide de ce segment, vous pouvez cibler directement des clients dans le marketing, le support client et d’autres scénarios pour réduire le risque d’attrition de clients spécifiques afin d’améliorer les revenus et de réduire les coûts.

  Dans l’expérience, vous pouvez configurer la définition du taux de désabonnement dans une fenêtre temporelle spécifique à votre entreprise. Par exemple, une entreprise de streaming vidéo qui a un processus d’abonnement mensuel peut souhaiter considérer qu’un client s’est désabonné 15 jours après l’expiration de son abonnement.

  Au fur et à mesure que vous affinez votre prédiction, nous vous guidons à travers les données nécessaires et vous permettons de mapper les données de votre entreprise sur les champs requis pour prédire le taux de désabonnement de vos clients. Au fil de l’évolution des informations sur votre entreprise, vous pouvez également définir un calendrier pour vous entraîner de nouveau sur les nouvelles informations de votre système afin de vous adapter à l’évolution de la situation commerciale.    
  Pour plus d’informations, consultez [Prédiction de la résiliation d’abonnement (version préliminaire)](predict-subscription-churn.md).

#### <a name="segments"></a>Segments

- **Trouver des clients similaires**
  
  Trouvez des clients similaires dans votre clientèle grâce à l’intelligence artificielle. Un modèle de Machine Learning de classification binaire attribue un score de similarité aux clients du segment étendu. Le score est basé sur la similitude avec les clients du segment source. En fonction du score de similarité, les profils clients sont ajoutés à un segment nouvellement créé.

  Parfois appelé modélisation sosie dans le marketing numérique, il utilise un modèle IA pour vous aider à trouver des clients similaires à un autre segment de vos clients en tenant compte de plus d’attributs. Il vous permet non seulement de choisir les attributs, mais vous permet également de spécifier le nombre maximum de clients qui doivent appartenir à ce nouveau segment. Le modèle IA calcule ensuite les scores de similarité pour chaque client en fonction des attributs sélectionnés et trouve les clients avec le score de similarité moyen le plus élevé. Le segment résultant comprendra des clients qui ressemblent au client de votre segment d’origine.    
  Pour plus d’informations, consultez [Clients similaires](find-similar-customer-segments.md).

- **Chevauchement de segments et facteurs de différenciation**

  Le chevauchement de segments vous permet de voir combien de clients, et lesquels, sont communs à deux segments ou plus. Par exemple, la façon dont un segment de clients très dépensiers recouvre partiellement un segment de clients très satisfaits, ou la façon dont un segment de clients en attrition chevauche un segment de clients peu satisfaits. En outre, vous pouvez analyser comment le chevauchement change en fonction d’un attribut supplémentaire de votre choix.

  Les facteurs de différenciation de segment révèlent ce qui différencie un segment du reste de vos clients ou d’un autre segment. Tout ce que vous avez à faire est d’identifier un segment ; le système identifiera les attributs de profil et les mesures qui distinguent le segment sous la forme d’une liste classée de facteurs de différenciation, du plus fort au plus faible.    
  Pour plus d’informations, voir [Informations sur un segment (version préliminaire)](segment-insights.md).

- **Durée de vie du segment**
  
  Définissez une planification pour activer ou désactiver un segment.    
  Pour plus d’informations, voir [Gestion des segments existants](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Mises à jour de mai 2020

Les mises à jour de mai 2020 comprennent plusieurs fonctionnalités, mises à niveau des performances et corrections de bogues.

### <a name="new-and-updated-features-in-may-2020"></a>Nouvelles fonctionnalités et fonctionnalités mises à jour en mai 2020

#### <a name="data-ingestion"></a>Ingestion des données

- **Ingestion de données en temps réel : vues historiques**

  Lorsque vous utilisez notre API pour ingérer des mises à jour en temps réel, vous pouvez voir jusqu’à 30 jours d’historique agrégé pour ces mises à jour. Vous avez accès à des agrégats de tous les appels d’API réussis ou échoués, y compris leur résultat, le système source et d’autres métadonnées utiles.    
  Pour plus d’informations, voir [Ingestion de données en temps réel](real-time-data-ingestion.md).

- **Ingestion de données en temps réel : mises à jour des profils**

  Cette extension de l’ingestion de données en temps réel vous permet de voir, en quelques secondes, les modifications apportées aux champs de profil utilisateur spécifiques.    
  En plus de la fonctionnalité en temps réel pour les activités, le système prend en charge les mises à jour à faible latence des champs de profil. Les mises à jour en temps réel des champs de profil ont un délai d’expiration et ne remplacent donc pas les actualisations planifiées.    
  Pour plus d’informations, voir [Ingestion de données en temps réel](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Extensibilité

- **Chronologie et pagination mises à jour sur le complément de carte client**

  La chronologie de la solution Complément de carte client correspond à la chronologie de l’activité. La pagination de la chronologie s’est améliorée, montrant jusqu’à 50 activités à la fois. Il permet également de charger plus d’activités dans la chronologie.    
  Pour plus d’informations, voir [Complément de carte client](customer-card-add-in.md).

- **Déclencheur Power Automate pour les modifications de segment**

  Les déclencheurs pour Power Automate définissent ce à partir de quoi vous pouvez créer un flux. Le déclencheur récemment ajouté vous permet de définir un seuil pour un segment. Par exemple, vous pouvez créer une notification qui est envoyée lorsque le seuil défini est dépassé.    
  Pour plus d’informations, voir [Connecteur Power Automate](export-power-automate.md).

- **Support partagé au sein d’une architecture mutualisée pour les modèles personnalisés**

  Configurez les flux de travail pour les modèles personnalisés avec un service Web d’un autre client Azure Machine Learning. Vous pouvez vous connecter au client Azure Machine Learning lors de la création d’un nouveau workflow pour les modèles personnalisés. Cette capacité est un ajout à la capacité existante d’intégration avec votre propre service Web Azure Machine Learning personnalisé.    
  Pour plus d’informations, voir [Modèles personnalisés Machine Learning](custom-models.md).

#### <a name="segments"></a>Segments

- **Automatisation du chemin d’entité**

  Lors de la création d’un segment, les utilisateurs doivent définir le chemin d’accès de l’entité. Cette fonctionnalité prend une première étape dans l’automatisation de la définition du chemin d’entité afin que vous puissiez vous concentrer sur les critères de segmentation que vous avez en tête.    
  Si l’entité par laquelle vous souhaitez segmenter vos clients est directement liée à l’entité client unifiée, vous n’aurez plus besoin de définir le chemin de l’entité. Cependant, s’il existe plusieurs chemins d’entité possibles, vous devez toujours le définir manuellement.

- **Actions sur plusieurs segments**
  
  Les utilisateurs peuvent sélectionner plusieurs segments et effectuer des actions sur eux, comme rafraîchir les segments, en un seul clic.    

- **Actualiser des segments**

  Les utilisateurs peuvent actualiser un seul segment ou sélectionner uniquement les segments qu’ils souhaitent actualiser.    

  
- **Améliorations des segments composés**

  Les utilisateurs peuvent créer, modifier et supprimer des segments basés sur d’autres segments. Par exemple, un segment construit sur un autre segment qui a été construit sur un troisième segment.    

- **Page de la liste des segments**

  La nouvelle conception de la page des segments utilise un format de liste qui vous permet de voir plus de segments à la fois. Un champ de recherche est ajouté pour trouver rapidement des segments. Les utilisateurs peuvent désormais appliquer des actions comme le téléchargement ou la suppression sur plusieurs segments à la fois. Une nouvelle expérience de tendance est introduite pour identifier rapidement les changements significatifs sur les segments.    
  Pour plus d’informations, consultez [Créer et gérer les segments](segments.md).

#### <a name="system-administration"></a>l’administration du système ;

- **Customer Insights disponible dans Microsoft Dynamics 365 Online Government**

  Avec de plus en plus de canaux d’interaction, les données des citoyens sont dispersées sur une myriade de systèmes, conduisant à des données cloisonnées et à une vue fragmentée des informations sur les interactions avec les citoyens. Sans une vue complète des interactions de chaque citoyen à travers les canaux, il est impossible pour les gouvernements de se moderniser à grande échelle. Microsoft s’engage à répondre aux besoins technologiques du gouvernement pour répondre aux attentes des citoyens en matière d’expériences cohérentes et réactives.    
  Avec la 1ère phase du lancement 2020, Dynamics 365 Customer Insights sera disponible pour Government Community Cloud (GCC), un environnement conçu pour répondre aux besoins de conformité plus élevés des agences gouvernementales américaines. Les agences acquièrent une vue unifiée des citoyens et utilisent l’IA prédéfinie pour obtenir des informations qui améliorent les interactions, responsabilisent les employés et transforment les communautés, tout en réduisant la complexité informatique et en répondant aux normes de conformité et de sécurité des États-Unis. Dynamics 365 Government répond aux exigences strictes du programme fédéral de gestion des risques et des autorisations des États-Unis (FedRAMP), permettant aux agences fédérales américaines de bénéficier des économies de coûts et de la sécurité rigoureuse du cloud Microsoft.

## <a name="april-2020-updates"></a>Mises à jour d’avril 2020

Les mises à jour d’avril 2020 comprennent plusieurs fonctionnalités, mises à niveau des performances et corrections de bogues.

### <a name="new-and-updated-features-in-april-2020"></a>Nouvelles fonctionnalités et fonctionnalités mises à jour en avril 2020

#### <a name="activities"></a>Activités

- **Mapper l’entité d’activité au type d’activité standard**
  
  La configuration et le stockage des activités sont actuellement basés sur une conception statique pour les afficher dans une chronologie. La signification sémantique des activités, qui a le potentiel de multiples cas d’utilisation dans les modèles d’IA, n’est pas pleinement utilisée pour le moment. Nous prévoyons de rendre la chronologie de l’activité plus dynamique, en fonction du type d’activité et d’une meilleure compréhension sémantique des activités. Cette fonctionnalité vise à identifier le type d’activité tel que défini dans Common Data Model pour toute activité ingérée.
  Pour plus d’informations, voir [Activités client](activities.md).

#### <a name="data-ingestion"></a>Ingestion des données

- **Ingestion de données en temps réel : activités**
  
  L’ingestion de données en temps réel fournit des données immédiatement pour la consommation, jusqu’à ce que l’actualisation programmée suivante extrait ces données de la source de données.    
  Pour plus d’informations, voir [Ingestion de données en temps réel](real-time-data-ingestion.md).

- **Améliorations de la préparation des données**
  
  En savoir plus sur les données ingérées dans une entité. Le résumé des données vous permet de comprendre les caractéristiques de qualité des données qui peuvent vous aider à prendre les mesures appropriées.    
  Pour plus d’informations, voir [Explorer les données de l’entité](entities.md#exploring-a-specific-entitys-data).

- **Ingérer des données analytiques à partir de Dynamics 365 avec Common Data Service**
  
  Common Data Service permet de créer des sources de données. Les clients Dynamics 365 existants peuvent ingérer des entités analytiques à partir de Common Data Service vers Customer Insights. Une seule source de données peut utiliser simultanément le même lac géré par Common Data Service dans un environnement Customer Insights.    
  Pour plus d’informations, voir [Se connecter aux données dans un lac de données géré Common Data Service](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Extensibilité

- **Exporter vers LiveRamp**

  Activez vos données dans LiveRamp® pour vous connecter à plus de 500 plateformes à travers les écosystèmes numériques, sociaux et télévisuels. Utilisez vos données dans LiveRamp pour le ciblage, la suppression et la personnalisation des campagnes publicitaires.    
  Pour plus d’informations, voir [Connecteur LiveRamp&reg;](export-liveramp.md).

- **Complément Teams Customer Insights**
  
  Le bot offre des capacités de recherche pour les profils client unifiés. Il affiche une carte avec jusqu’à 15 champs du profil client résultant. Plusieurs correspondances renvoient une liste de résultats où vous pouvez sélectionner un profil.    
  Pour plus d’informations, consultez l’[Robot Teams pour Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Mesures

- **Page de liste des mesures**
  
  Les améliorations de la page des mesures incluent la prise en charge des actions sur une seule mesure et sur plusieurs mesures à la fois. De plus, vous trouverez un champ de recherche pour trouver et suivre rapidement les mesures.    
  Pour plus d’informations, consultez [Créer et gérer les segments](segments.md).

- **Améliorations des mesures composées**
  
  Les utilisateurs peuvent créer, modifier et supprimer des mesures basées sur d’autres mesures. Par exemple, une mesure construit sur une autre mesure qui a été construite sur une troisième mesure.

#### <a name="segments"></a>Segments

- **Un autre opérateur**
  
  L’opérateur In-set permet la segmentation pour les clients par plusieurs valeurs de chaîne possibles. Avant l’ajout de cet opérateur, vous deviez construire de tels segments avec plusieurs conditions OU. L’opérateur In-set vous permet de le faire avec une seule condition.    
  Pour plus d’informations, consultez [Créer et gérer les segments](segments.md).

#### <a name="system-administration"></a>Administration du système

- **Copier les paramètres de configuration dans un nouvel environnement**
  
  Copiez votre configuration d’un environnement à un autre. Lors de la création d’un environnement, vous pouvez sélectionner un environnement existant à partir duquel vous souhaitez copier la configuration. Nous prenons actuellement en charge les sources de données, l’unification des données, les relations, les mesures et les segments à copier. Les informations d’identification source de données et les données réelles ne sont pas copiées.    
  Pour plus d’informations, voir [Gérer les environnements](manage-environments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]