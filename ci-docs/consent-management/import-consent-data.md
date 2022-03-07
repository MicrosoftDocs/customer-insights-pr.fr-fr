---
title: Importer des données vers la capacité de gestion du consentement
description: Découvrez comment importer des données dans la capacité de gestion du consentement de Customer Insights et sur les champs requis pour les deux types de données.
ms.date: 12/03/2021
ms.service: customer-insights
ms.subservice: consent-management
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b1e6a56e4cb9bfbaf50da161e6fcad1fbfa8ce28
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884122"
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

Modèle de données avec types de données : 

|     Nom                          |     Type        |     Requise    |     Commentaires        |
|----------------------------------|-----------------|-----------------|---------------------|
|     DataSubjectIdentifierType    |     string      |     Oui         |     Ce champ définit le type d’identificateur de la personne concernée. Par exemple, numéro de téléphone, adresse e-mail ou ID utilisateur. La gestion du consentement prend actuellement en charge trois types d’identificateur de la personne concernée : « Téléphone », « ID utilisateur » et « E-mail » (qui respectent tous la casse).     |
|     DataSubjectIdentifier        |     string      |     Oui         |     Valeur de l’identificateur de la personne concernée. Par example, marie@contoso.com, +1-444-444-4444 ou CONTACT_ID_123.            |
|     Abonnement                 |     string      |     Oui         |     Nom de l’abonnement pour lequel le consentement a été recueilli.             |
|     SubscriptionStartDate        |     DateTime    |     No          |    Champ facultatif pour spécifier la date et l’heure de début de l’abonnement. Par exemple, vous pouvez avoir un abonnement créé pour une offre qui s’exécute sur une période de temps limitée. Vous pouvez utiliser ce champ pour indiquer la date et l’heure de début de cet abonnement.           |
|     SubscriptionEndDate          |     DateTime    |     No          |     Champ facultatif pour spécifier la date et l’heure de fin d’un abonnement.  |
|     ConsentStatus                |     string      |     Oui         |     Valeur du statut du consentement. Il peut s’agir de n’importe quelle valeur que votre système d’enregistrement de consentement a stockée pour le consentement spécifique.         |
|     ConsentDate                  |     DateTime    |     Oui         |     Date et heure de capture du consentement.    |



### <a name="purpose-consent-data"></a>Données de consentement d'objet

Champs de données obligatoires : 

- Nom de l’objectif des données
- Adresse e-mail ou numéro de téléphone
- Méthode de contact (e-mail ou téléphone)
- Statut du consentement
- Quand le consentement a été saisi
- Source du consentement saisi


Modèle de données avec types de données : 
 
|     Nom                          |     Type        |     Requise    |     Commentaires               |
|----------------------------------|-----------------|-----------------|----------------------|
|     DataSubjectIdentifierType    |     string      |     Oui         |     Ce champ définit le type d’identificateur de la personne concernée. Par exemple, numéro de téléphone, adresse e-mail ou ID utilisateur. La gestion du consentement prend actuellement en charge trois types d’identificateur de la personne concernée : « Téléphone », « ID utilisateur » et « E-mail » (qui respectent tous la casse).     |
|     DataSubjectIdentifier        |     string      |     Oui         |     Valeur de l’identificateur de la personne concernée. Par example, marie@contoso.com, +1-444-444-4444 ou CONTACT_ID_123.            |
|     DataUsePurpose               |     string      |     Oui         |     Nom de l’objectif pour lequel le consentement a été recueilli.         |
|     ConsentStatus                |     string      |     Oui         |     Valeur du statut du consentement. Il peut s’agir de n’importe quelle valeur que votre système d’enregistrement de consentement a stockée pour le consentement spécifique.         |
|     ConsentDate                  |     DateTime    |     Oui         |     Date et heure de capture du consentement.    |