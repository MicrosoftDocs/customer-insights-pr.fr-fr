---
title: Fonctionnalités nouvelles et à venir
description: Informations sur les nouvelles fonctionnalités, les améliorations et les corrections de bogues.
ms.date: 07/19/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 1c54d74c999eb4776074951a129019843017964e
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692386"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Nouveautés de la fonctionnalité d’informations sur l’audience de Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Nous sommes ravis d’annoncer nos mises à jour les plus récentes ! Cet article résume les fonctionnalités de version préliminaire publique, les améliorations de la disponibilité générale et les mises à jour de fonctionnalités. Pour connaître les plans de fonctionnalités à long terme, consultez les [Plans de versions Dynamics 365 et Power Platform](/dynamics365/release-plans/).

Nous déployons des mises à jour région par région. Ainsi, certaines régions peuvent voir des fonctionnalités avant d’autres. Sauf indication contraire, vous n’avez rien à faire et nous mettrons à jour l’application automatiquement sans interruption.

> [!TIP]
> Pour envoyer et voter sur les demandes de fonctionnalités et les suggestions de produits, accédez au [portail Idées d’application Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="june-2021-updates"></a>Mises à jour de juin 2021

Les mises à jour de juin 2021 comprennent plusieurs fonctionnalités, améliorations des performances et corrections de bogues.

### <a name="data-ingestion"></a>Ingestion des données

- **Mises à jour améliorées de la progression de l’unification des données** Vous pouvez désormais afficher des mises à jour de statut dynamiques plus granulaires et améliorées sur les étapes du [processus d’unification des données](data-unification.md). Cette fonctionnalité vous permet de suivre la progression détaillée pour comprendre le flux du processus et prendre des mesures si une étape nécessite une attention particulière.

### <a name="extensibility"></a>Extensibilité

- **Exporter des segments et d’autres données vers Salesforce Marketing Cloud** Nous avons étendu nos destinations d’exportation pour inclure [Salesforce Marketing Cloud](export-salesforce.md). Vous pouvez désormais exporter des segments et d’autres types de données vers Salesforce Marketing Cloud via une exportation SFTP de marque. L’importation de données peut être entièrement automatisée dans Salesforce et utilisée pour créer des campagnes marketing plus efficaces.  
 
- **Exporter des segments vers ActiveCampaign** Nous avons étendu nos destinations d’exportation pour inclure [Campagne active](export-active-campaign.md). Vous pouvez maintenant exporter les segments pour générer des campagnes, exécuter le marketing par e-mail et utiliser des groupes spécifiques de clients dans ActiveCampaign.
 
- **Exporter des segments vers Sendinblue** Nous avons étendu nos destinations d’exportation pour inclure [Sendinblue](export-sendinblue.md). Vous pouvez maintenant exporter les segments pour générer des campagnes, exécuter le marketing par e-mail et utiliser des groupes spécifiques de clients dans Sendinblue.
 
### <a name="ux-updates"></a>Mises à jour UX 

- **Page des clients nouveaux et améliorés et page des détails du profil** Nous avons repensé la page Clients et les pages de détails du profil pour une meilleure expérience utilisateur et de meilleures performances. Ces modifications vous permettent d’afficher, de trier, de rechercher et de filtrer les clients. Les filtres sont désormais représentés dans l’URL pour partager les résultats de la recherche avec d’autres utilisateurs de manière transparente. Les résultats de la recherche peuvent également être enregistrés en tant que segment.    
  La page de détails des profils client regroupe désormais les données dans diverses sous-sections telles que les données démographiques, les identifiants et d'autres attributs de profil pour une meilleure lisibilité. Les autres sections de la page des détails du profil sont désormais plus interactives. Par exemple, la section activités permet désormais de filtrer et de trier.


## <a name="may-2021-updates"></a>Mises à jour de mai 2021

Les mises à jour de mai 2021 comprennent plusieurs fonctionnalités, mises à niveau des performances et corrections de bogues.

### <a name="data-ingestion"></a>Ingestion des données

- **Affichez ou modifiez les métadonnées ou la définition d'entité lorsque vous joignez des données à partir de votre Azure Data Lake Storage**. Vous pouvez désormais afficher et modifier les métadonnées ou la définition d'entité dans les informations sur l’audience lorsque vous joignez des données à partir d'un dossier Common Data Model dans votre Azure Data Lake Storage. Cette fonctionnalité fournit un retour d'information en temps réel, une validation du modèle et une vérification des erreurs. Elle vous permet de modifier à la fois model.json et manifest.json de manière transparente.

### <a name="extensibility"></a>Extensibilité

- **Exportations de segments améliorées, planification personnalisée et duplication**. Vous pouvez maintenant [voir toutes les exportations pour un segment spécifique](export-destinations.md#view-exports-and-export-details) dans une liste. Cette nouvelle vue permet de gérer l'utilisation d'un segment spécifique et d'adapter les exportations existantes ou de créer des exportations.    
  Vous pouvez [définir des planifications d’actualisation personnalisées](export-destinations.md#schedule-and-run-exports) pour des exportations individuelles ou plusieurs exportations à la fois. Jusqu'à présent, toutes les exportations étaient exécutées à chaque actualisation du système.    
  Plutôt que de créer une nouvelle exportation à partir de zéro, vous pouvez commencer à partir d'une exportation existante pour gagner du temps.

- **Exporter des segments vers Microsoft Advertising** : nous avons étendu nos destinations d’exportation pour inclure Microsoft Advertising. Créez des audiences Customer Match sur Microsoft Advertising avec vos données de profil client unifiées, et utilisez ces audiences pour vos campagnes publicitaires. Pour plus d'informations, consultez [Exporter des segments vers Microsoft Advertising](export-microsoft-advertising.md).

- **Exporter des segments vers LinkedIn Ads** Nous avons étendu nos destinations d'exportation pour inclure LinkedIn Ads et vous permettre de déverrouiller le ciblage des contacts ainsi que le ciblage des entreprises via LinkedIn en exportant vos données de profil client unifiées. Pour plus d'informations, consultez [Exporter des segments vers LinkedIn Ads](export-linkedin-ads.md).


- **Exporter des segments vers Omnisend** : nous avons étendu nos destinations d’exportation pour inclure Omnisend. Utilisez les segments créés dans les informations sur l’audience pour générer des campagnes, fournir du marketing par e-mail et utiliser certains groupes de clients avec Omnisend. Pour plus d'informations, consultez [Exporter des segments vers Omnisend](export-omnisend.md).

### <a name="predictions"></a>Prédictions

- **Rapport d’utilisation des données d’entrée** Le rapport d'utilisation des données d'entrée fournit une vue consolidée des erreurs et des avertissements que vos prédictions prêtes à l'emploi peuvent générer. Il donne également des recommandations sur la manière d'améliorer les performances du modèle.    
  Le rapport est disponible une fois qu'un modèle a terminé son processus d'entraînement. Il est créé pour chaque modèle séparément, qu'il soit terminé avec succès ou non.
  Actuellement, cette fonctionnalité n'est disponible que pour le modèle d’attrition des transactions. Pour plus d’informations, voir [Rapport d’utilisation des données d’entrée](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Relations

- **Visualiseur de relations** La vue du visualiseur de relations vous permet de voir tous les relations existants entre les entités et leur cardinalité. Les relations sont maintenant organisées en groupes : relations créées par l'utilisateur, relations système et relations héritées. Vous pouvez également exporter une vue sous forme d'image. Pour en savoir plus, consultez [Afficher les relations](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Mises à jour d’avril 2021

Les mises à jour d’avril 2021 comprennent plusieurs fonctionnalités, mises à niveau des performances et corrections de bogues.

### <a name="data-unification"></a>Unification des données
 
- **Expérience de fusion améliorée pour l’unification des données**    
  
   Nous avons maintenant une expérience utilisateur améliorée dans la configuration de fusion du processus d’unification des données. Les modifications incluent l’ordre intuitif des champs fusionnés et des statistiques détaillées sur les champs combinés et singleton.

- **Réorganisation de l’entité et configuration de tous les enregistrements source dans l’entité client**  
      
   Vous pouvez désormais réorganiser et supprimer des entités d’un plan de fusion existant dans le processus d’unification des données. Cela apporte de la flexibilité pour réorganiser les entités dans le processus de mise en correspondance en fonction des besoins de l’entreprise. De plus, nous permettons d’inclure tous les enregistrements non correspondants dans l’entité *Client* finale, ce qui permet de définir la définition du jeu de données du profil client.

### <a name="enrichments"></a>Enrichissements

 - **Nouvel enrichissement : adresses améliorées**    
  
   Nous sommes ravis de lancer un nouvel enrichissement pour améliorer les adresses dans vos données client. Les adresses dans vos données peuvent être non structurées, incomplètes ou incorrectes. Cette fonctionnalité utilise les modèles de Microsoft pour normaliser et enrichir vos adresses au format Common Data Model pour une meilleure précision et de meilleures informations.
 
   Pour plus d’informations, voir [Enrichissement des profils clients avec des adresses améliorées](enrichment-enhanced-addresses.md).

- **Expérience de configuration guidée pour les enrichissements**    
  
   Nous avons revisité l’expérience de configuration pour les enrichissements avec une expérience simple et guidée. Vous disposez désormais d’un processus étape par étape clair pour créer et modifier des enrichissements.
 
   De plus, nous avons séparé la configuration des connexions pour les enrichissements tiers afin de permettre l’utilisation de la même connexion par plusieurs enrichissements. Seuls les administrateurs peuvent configurer de nouvelles connexions, mais les connexions créées sont disponibles à la fois pour les administrateurs et les contributeurs.    

   Pour plus d’informations, voir [Présentation des connexions](connections.md).

- **Enrichissements multiples du même type**    
  
   Nous permettons désormais aux utilisateurs de créer et de gérer plusieurs enrichissements du même type d’enrichissement. Par exemple, vous pouvez désormais créer deux enrichissements d’adresses distincts pour enrichir deux segments de clientèle différents. Des limites s’appliquent au nombre d’enrichissements du même type pouvant être créés. Elles varient en fonction du type d’enrichissement.
  
   Pour plus d’informations, consultez [Enrichissement des profils clients](enrichment-hub.md).

## <a name="march-2021-updates"></a>Mises à jour de mars 2021

Les mises à jour de mars 2021 comprennent plusieurs fonctionnalités, mises à niveau des performances et corrections de bogues.

### <a name="activities"></a>Activités

- **Assistant d’activité et types sémantiques**

   Nous avons amélioré et mis à jour notre expérience de mappage d’activités pour guider et simplifier la création de mappage d’activités. Dans cette nouvelle expérience, les utilisateurs bénéficient d’une expérience guidée pour les aider à terminer chaque étape du processus. Dans l’étape de mappage d’activités, en plus de choisir parmi plusieurs types d’activités, l'utilisateur peut choisir de mapper sémantiquement les données pour *Abonnement* et/ou *SalesOrderLine* aux schémas standard de l’industrie, qui peuvent être utilisés pour la consommation en aval.   

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

  Les administrateurs peuvent copier les configurations d’environnement dans un nouvel environnement de la même organisation. Cette fonctionnalité étend la fonctionnalité de l'environnement de copie au cas où les sources de données basées sur un lac de données géré Microsoft Dataverse ou un dossier Common Data Model sont utilisés.

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




[!INCLUDE[footer-include](../includes/footer-banner.md)]