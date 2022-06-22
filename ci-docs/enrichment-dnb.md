---
title: Enrichissement des profils d’entreprise avec Dun & Bradstreet
description: Informations générales sur l’enrichissement tiers de Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b1038970b6aee3bbdd7f79cc457f79aaf1c38222
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953888"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Enrichissement des profils d’entreprise avec Dun & Bradstreet (version préliminaire)

Dun & Bradstreet fournit des données commerciales, des analyses et des informations aux entreprises. Elle permet aux clients ayant un profil client unifié pour les entreprises d’enrichir leurs données. Les enrichissements incluent des attributs tels que le numéro DUNS, la taille de la société, son emplacement, son secteur d’activité, et plus encore.

## <a name="prerequisites"></a>Conditions préalables

- Une licence [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) active.
- [Profils clients unifiés](customer-profiles.md) pour les entreprises.
- Un [projet](#set-up-your-dun--bradstreet-project) Dun et Bradstreet est configuré.
- Une [connexion](connections.md) Dun & Bradstreet est [configurée](#configure-a-connection-for-dun--bradstreet) par un administrateur.

## <a name="set-up-your-dun--bradstreet-project"></a>Configurer votre projet Dun & Bradstreet

En tant qu’utilisateur sous licence de Dun & Bradstreet, vous pouvez configurer un projet dans [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Connectez-vous à [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Pour récupérer les informations d’identification, [restaurez votre mot de passe](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Téléchargez [notre fichier de modèle csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) qui sera utilisé pour mapper les champs Customer Insights sur les champs correspondants de Dun & Bradstreet.

1. Chargez le fichier dans l’étape **Charger les données** de l’expérience de création du projet Dun & Bradstreet.

1. Sélectionnez les points horizontaux sous la **source** appropriée dans le projet Dun & Bradstreet nouvellement créé pour voir les options disponibles.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Capture d’écran des points dans un projet Dun & Bradstreet.":::

1. Choisissez **Obtenir les détails S3**. Conservez ces informations dans un endroit sûr. Vous en aurez besoin pour [configurer la connexion pour l’enrichissement](#configure-a-connection-for-dun--bradstreet) dans Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Capture d’écran de la sélection des informations s3 dans un projet Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Configurer une connexion pour Dun & Bradstreet

Vous pouvez la créer si vous disposez d’autorisations [administrateur](permissions.md#admin) dans Customer Insights et des informations d’identification de Dun & Bradstreet Connect.

1. Sélectionnez **Ajouter une connexion** lors de la configuration d’un enrichissement ou accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** sur la vignette Dun & Bradstreet.

1. Saisissez un nom pour l’ensemble de connexions.

1. Fournissez des informations d’identification Dun & Bradstreet valides et les détails du projet Dun & Bradstreet, comme la *Région, le chemin d’accès au dossier de dépôt et le nom du dossier de dépôt*. Vous [obtenez ces informations](#set-up-your-dun--bradstreet-project) du projet Dun & Bradstreet.

1. Vérifiez et donnez votre consentement pour [Confidentialité et conformité des données](#data-privacy-and-compliance) en sélectionnant **J’accepte**.

1. Sélectionnez **Vérifier** pour valider la configuration, puis sélectionnez **Enregistrer**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Page de configuration de la connexion Dun & Bradstreet.":::

### <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Dun & Bradstreet, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous devez vous assurer que Dun & Bradstreet respecte toutes les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour ne plus utiliser cette fonctionnalité.

## <a name="supported-countries-or-regions"></a>Pays ou régions pris en charge

Nous prenons actuellement en charge les options de pays/région suivantes : Canada (anglais) ou États-Unis (anglais).

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement

1. Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.

1. Sélectionnez **Enrichir mes données** dans **Données d’entreprise** sur la vignette Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Capture d’écran de la vignette Dun & Bradstreet.":::

1. Passez la synthèse en revue et sélectionnez **Suivant**.

1. Sélectionnez la connexion et validez. Contactez un Administrateur si aucun n'est disponible.

1. Cliquez sur **Suivant**.

1. Sélectionnez le **Jeu de données client**, puis choisissez le profil ou segment que vous souhaitez enrichir avec les données d'entreprise à partir de Dun & Bradstreet. L’entité *Client* enrichit tous vos profils clients tandis qu'un segment enrichit uniquement les profils clients contenus dans ce segment.

1. Définissez le type de champs de vos profils unifiés à utiliser pour rechercher les données d'entreprise correspondantes de Dun & Bradstreet. Au moins un des champs **Nom et adresse**, **Téléphone** ou **E-mail** est obligatoire.

1. Sélectionnez **Suivant**.

1. Mappez les champs aux données de l'entreprise de Dun & Bradstreet. Les champs **Numéro DUNS** ou **Nom de la société** et **Pays** sont obligatoires.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Volet de mappage de champs Dun & Bradstreet.":::

1. Sélectionnez **Suivant** pour terminer le mappage de champs.

1. Fournissez un **Nom** pour l’enrichissement et pour le **Nom de l'entité de sortie**.

1. Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.

1. Sélectionnez **Exécuter** pour démarrer le processus d'enrichissement ou fermer pour revenir à la page **Enrichissements**.

## <a name="enrichment-results"></a>Résultats d’enrichissement

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Étapes suivantes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
