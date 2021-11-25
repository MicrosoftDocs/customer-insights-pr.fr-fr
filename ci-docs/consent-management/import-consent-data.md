---
title: Importer des données vers la capacité de gestion du consentement
description: Découvrez comment importer des données dans la capacité de gestion du consentement de Customer Insights et sur les champs requis pour les deux types de données.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: consent-management
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7ccd5444ebd7241e45afddca443cb8e57080df18
ms.sourcegitcommit: 79b09498d1328e5551fb8684c44af1fb149f9881
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790808"
---
# <a name="import-consent-data"></a>Importer des données de consentement

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La gestion du consentement vous permet d’importer des données sur les accords de consentement avec vos clients. Il existe deux types de données de consentement : les abonnements et les objectifs. Les abonnements sont des canaux de communication avec les clients existants ou potentiels. Les objectifs indiquent la finalité de l'utilisation et du traitement des données.

## <a name="how-to-import-consent-data"></a>Comment importer des données de consentement

Après que vous avez [configuré la fonctionnalité de gestion des consentements](get-started.md), l’expérience de première exécution vous guide pour démarrer le processus d’importation de données. Vous pouvez également démarrer le processus en accédant à **Accueil** ou **Consentement** dans le volet gauche du Centre de consentement. Quel que soit l’endroit où vous démarrez le processus, les étapes pour importer les données de consentement sont les mêmes. 

:::image type="content" source="media/first-run-consent-data-import.PNG" alt-text="Première expérience d'exécution pour l'importation de données de consentement.":::

1. Dans le Centre de consentement, accédez à **Consentement**.

1. Sélectionnez la commande **Importer les données de consentement** et choisissez le type de données de consentement à importer. Vous pouvez choisir entre les vues **Objectif** et **Abonnement**. Selon le type sélectionné, les [exigences relatives aux données de consentement](#data-requirements-for-consent-data) sont différentes.
   
   :::image type="content" source="media/import-consent-data-control.PNG" alt-text="Option de contrôle pour démarrer le processus d'importation des données de consentement.":::

1. Fournissez un **Nom** pour identifier le source de données, puis sélectionnez **Prochain**.
   
   :::image type="content" source="media/data-source-name.PNG" alt-text="Champ d'entrée de nom pour le nom d'une nouvelle source de données.":::

1. Sélectionnez le type de source de données à partir duquel vous souhaitez importer les données de consentement. 

   :::image type="content" source="media/choose-data-source.PNG" alt-text="Présentez une liste des sources de données disponibles.":::

1. Dans cet exemple, nous avons sélectionné la source de données **Texte/CSV** à importer dans un fichier .CSV hébergé dans un dossier OneDrive partagé. Saisissez le chemin ou l'URL du fichier hébergé, puis sélectionnez **Suivant**. 
   
   :::image type="content" source="media/connection-settings-data-source.PNG" alt-text="Paramètres de donnexion pour la nouvelle source de données.":::

1. L'étape **Obtenir un aperçu des données du fichier** affiche les données importées. Cliquez sur **Suivant** pour continuer. 
  
1. L'étape **Modifier des requêtes** vous permet de renommer la requête et [d'appliquer des transformations de données à l'aide de Power Query](/power-query/power-query-ui). 
   1. Si vos données source contiennent une ligne d'en-tête, appliquez **Transformer** > **Utiliser la première ligne comme en-tête**.
   1. Mappez les données au Common Data Model. Sélectionnez **Mapper à l'entité** > **Mappage automatique (facultatif)**.
   
   Après avoir appliqué toutes les transformations nécessaires, sélectionnez **Suivant** pour continuer.
   
   :::image type="content" source="media/data-transformations.PNG" alt-text="Options pour transformer les données et attribuer des types de données.":::

1. La dernière étape pour importer une source de données est l’étape **Actualiser les paramètres** où vous indiquez au système quand rechercher des mises à jour sur la source de données. 
   
   :::image type="content" source="media/refresh-settings.PNG" alt-text="Définissez les paramètres d'actualisation de la source de données.":::
   
1. Choisissez si vous souhaitez **Actualiser manuellement** si la source de données change ou que le système **s'actualise automatiquement**. Pour une actualisation automatique, définissez votre préférence quant au moment où une actualisation doit avoir lieu.

1. Sélectionnez **Sauvegarder** pour démarrer l'importation des données. 

Selon la taille du jeu de données importé, le processus d'importation peut prendre quelques instants.

## <a name="data-requirements-for-consent-data"></a>Exigences de données pour les données de consentement

Les données de consentement seront mappées sur un schéma défini par le système ([l’entité de consentement](glossary.md#consent-entity)). Le type de source de données de consentement que vous souhaitez importer détermine les champs de données requis. 

### <a name="subscription-consent-data"></a>Données de consentement d'abonnement

Champs de données obligatoires : 

- Nom de l’abonnement
- E-mail, numéro de téléphone ou UserID
- Type d'identifiant (e-mail, numéro de téléphone ou UserID)
- Statut du consentement
- Date de début du consentement
- Date d’expiration du consentement
- Quand le consentement a été saisi
- Source du consentement saisi

### <a name="purpose-consent-data"></a>Données de consentement d'objet

Champs de données obligatoires : 

- Nom de l’objectif des données
- Adresse e-mail ou numéro de téléphone
- Méthode de contact (e-mail ou téléphone)
- Statut du consentement
- Quand le consentement a été saisi
- Source du consentement saisi
