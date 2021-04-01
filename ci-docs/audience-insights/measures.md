---
title: Créer et gérer des mesures
description: Définir des mesures pour analyser et refléter la performance de votre entreprise.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654729"
---
# <a name="define-and-manage-measures"></a>Définir et gérer des mesures

Les mesures vous aident à mieux comprendre les comportements des clients et les performances commerciales en récupérant les valeurs pertinentes des [profils unifiés](data-unification.md). Par exemple, une entreprise souhaite voir le *total des dépenses par client* pour comprendre l’historique d’achat de chaque client. Ou mesurer le *total des ventes de l’entreprise* pour comprendre les revenus au niveau agrégé dans l’ensemble de l’entreprise.  

Les mesures sont créées à l’aide du générateur de mesures, une plateforme de requête de données avec divers opérateurs et des options de mappage simples. Elle vous permet de filtrer les données, de regrouper les résultats, de détecter les [chemins d’accès aux relations d’entités](relationships.md) et prévisualisez la sortie.

Utilisez le générateur de mesures pour planifier les activités commerciales en interrogeant les données client et en extrayant des informations. Par exemple, créer une mesure de *total des dépenses par client* et de *total des retours par client* aide à identifier un groupe de clients avec des dépenses élevées mais un rendement élevé. Vous pouvez [créer un segment](segments.md) pour conduire les meilleures actions suivantes. 

## <a name="create-a-measure"></a>Créer une mesure

Cette section vous guide tout au long de la création d’une mesure à partir de zéro. Vous pouvez créer une mesure avec des attributs de données à partir d’entités de données ayant une relation configurée pour se connecter à l’entité Client. 

1. Dans les informations sur l’audience, accédez à **Mesures**.

1. Cliquez sur **Nouveau**.

1. Sélectionnez **Modifier le nom** et fournissez un **Nom** pour la mesure. 
   > [!NOTE]
   > Si votre nouvelle configuration de mesure ne comporte que deux champs, par exemple, CustomerID et un calcul, la sortie sera ajoutée en tant que nouvelle colonne à l’entité générée par le système appelée Customer_Measure. Et vous pourrez voir la valeur de la mesure dans le profil client unifié. D’autres mesures généreront leurs propres entités.

1. Dans la zone de configuration, choisissez la fonction d’agrégation dans le menu déroulant **Sélectionnez la fonction**. Les fonctions d’agrégation comprennent : 
   - **Sum**
   - **Moyenne**
   - **Nombre**
   - **Nombre Unique**
   - **Max**
   - **Min**
   - **Première** : prend la première valeur de l’enregistrement de données
   - **Dernière** : prend la dernière valeur ajoutée à l’enregistrement de données

   :::image type="content" source="media/measure-operators.png" alt-text="Opérateurs pour les calculs de mesures.":::

1. Sélectionnez **Ajouter un attribut** pour sélectionner les données dont vous avez besoin pour créer cette mesure.
   
   1. Sélectionnez l’onglet **Attributs**. 
   1. Entité Data : Choisissez l’entité qui comprend l’attribut selon lequel vous souhaitez mesurer. 
   1. Attribut de données : choisissez l’attribut que vous souhaitez utiliser dans la fonction d’agrégation pour calculer la mesure. Vous ne pouvez sélectionner qu’un attribut à la fois.
   1. Vous pouvez également sélectionner un attribut de données à partir d’une mesure existante en sélectionnant l’onglet **Mesures**. Sinon, vous pouvez rechercher un nom d’entité ou de mesure. 
   1. Sélectionnez **Ajouter** pour ajouter l’attribut sélectionné à la mesure.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Sélectionnez un attribut à utiliser dans les calculs.":::

1. Pour créer des mesures plus complexes, vous pouvez ajouter plus d’attributs ou utiliser des opérateurs mathématiques sur votre fonction de mesure.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Créez une mesure complexe avec des opérateurs mathématiques.":::

1. Pour ajouter des filtres, sélectionnez le **Filtre** dans la zone de configuration. 
  
   1. Dans la section **Ajouter un attribut** du volet **Filtres**, sélectionnez l’attribut que vous souhaitez utiliser pour créer des filtres.
   1. Définissez les opérateurs de filtre pour définir le filtre pour chaque attribut sélectionné.
   1. Sélectionnez **Appliquer** pour ajouter les filtres à la mesure.

1. Pour ajouter des dimensions, sélectionnez **Dimension** dans la zone de configuration. Les dimensions s’affichent sous forme de colonnes dans l’entité de sortie de mesure.
   1. Sélectionnez **Modifier les dimensions** pour ajouter des attributs de données par lesquels vous souhaitez regrouper les valeurs de mesure. Par exemple, ville ou sexe. Par défaut, la dimension *CustomerID* est sélectionnée pour créer des *mesures au niveau du client*. Vous pouvez supprimer la dimension par défaut si vous souhaitez créer des *mesures au niveau de l’entreprise*.
   1. Sélectionnez **Terminé** pour ajouter les dimensions à la mesure.

1. S’il existe plusieurs chemins d’accès entre l’entité de données que vous avez mappée et l’entité *Client*, vous devez choisir l’un des [chemins d’accès de relation d’entité](relationships.md). Les résultats de la mesure peuvent varier en fonction du chemin sélectionné. 
   1. Sélectionnez **Préférences de données** et choisissez le chemin de l’entité à utiliser pour identifier votre mesure. S’il n’y a qu’un seul chemin vers l’entité *Client*, ce contrôle ne s’affichera pas.
   1. Sélectionnez **Terminé** pour appliquer votre sélection. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Sélectionnez le chemin d’accès pour la mesure.":::

1. Pour ajouter d’autres calculs pour la mesure, sélectionnez **Nouveau calcul**. Vous ne pouvez utiliser des entités sur le même chemin d’entité que pour les nouveaux calculs. Des calculs supplémentaires s’affichent sous forme de nouvelles colonnes dans l’entité de sortie de mesure.

1. Sélectionnez **...** sur le calcul pour **Dupliquer**, **Renommer** ou **Supprimer** un calcul à partir d’une mesure.

1. Dans la zone **Aperçu**, vous verrez le schéma de données de l’entité de sortie de mesure, y compris les filtres et les dimensions. L’aperçu réagit de manière dynamique aux modifications de la configuration.

1. Sélectionnez **Exécuter** pour calculer les résultats de la mesure configurée. Sélectionnez **Enregistrer et fermer** si vous souhaitez conserver la configuration actuelle et exécuter la mesure ultérieurement.

1. Aller à **Mesures** pour voir la mesure nouvellement créée dans la liste.

## <a name="manage-your-measures"></a>Gérer vos mesures

Après avoir [créé une mesure](#create-a-measure), vous verrez une liste de mesures sur la page **Mesures**.

Vous trouverez des informations sur le type de mesure, le créateur, la date de création, le statut et l’état. Lorsque vous sélectionnez une mesure dans la liste, vous pouvez prévisualiser la sortie et télécharger un fichier .CSV.

Pour actualiser toutes vos mesures en même temps, sélectionnez **Actualiser tout** sans sélectionner une mesure spécifique.

> [!div class="mx-imgBorder"]
> ![Actions pour gérer des mesures uniques](media/measure-actions.png "Actions pour gérer des mesures uniques")

Choisissez une mesure parmi la liste des options suivantes :

- Sélectionner le nom de la mesure pour afficher ses détails.
- **Modifier** la configuration de la mesure.
- **Actualisez** la mesure basée sur les dernières données.
- **Renommer** la mesure.
- **Supprimer** la mesure.
- **Activer** ou **Désactiver**. Les mesures inactives ne seront pas actualisées pendant une [actualisation programmée](system.md#schedule-tab).

> [!TIP]
> Il existe [six types de statuts](system.md#status-types) pour les tâches/processus. En outre, la plupart des processus [dépendent d’autres processus en aval](system.md#refresh-policies). Vous pouvez sélectionner le statut d’un processus pour afficher des détails sur la progression de toute la tâche. Après avoir sélectionné **Voir les détails** pour l’une des tâches du travail, vous voyez des informations complémentaires : la durée de traitement, la date du dernier traitement et toutes les erreurs et avertissements associés à la tâche.

## <a name="next-step"></a>Étape suivante

Vous pouvez utiliser des mesures existantes pour créer [un segment de clientèle](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]