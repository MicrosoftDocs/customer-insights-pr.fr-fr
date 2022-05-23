---
title: Enrichissement des profils d’entreprise avec Dun & Bradstreet
description: Informations générales sur l’enrichissement tiers de Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c738c2657d4cda213342629156ddc8104366bd8a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755397"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Enrichissement des profils d’entreprise avec Dun & Bradstreet (version préliminaire)

Dun & Bradstreet fournit des données commerciales, des analyses et des informations aux entreprises. Elle permet aux clients ayant un profil client unifié pour les entreprises d’enrichir leurs données. Les enrichissements incluent des attributs tels que le numéro DUNS, la taille de la société, son emplacement, son secteur d’activité, et plus encore.

## <a name="prerequisites"></a>Conditions préalables

Pour configurer un enrichissement Dun & Bradstreet, les conditions préalables suivantes doivent être remplies :

- Vous avez une licence [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) active.
- Vous avez des [profils clients unifiés](customer-profiles.md) pour les entreprises.
- Une [connexion](connections.md) Dun & Bradstreet est configurée par un administrateur. Vous pouvez la créer si vous disposez d’autorisations [administrateur](permissions.md#admin) et des informations d’identification de Dun & Bradstreet Connect.

## <a name="setting-up-your-dun--bradstreet-project"></a>Configuration de votre projet Dun & Bradstreet

En tant qu’utilisateur sous licence de Dun & Bradstreet, vous pouvez configurer un projet dans [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).


1. Connectez-vous à [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Pour récupérer les informations d’identification, [restaurez votre mot de passe](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Téléchargez [notre fichier de modèle csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) qui sera utilisé pour mapper les champs Customer Insights sur les champs correspondants de Dun & Bradstreet.

1. Chargez le fichier dans l’étape **Charger les données** de l’expérience de création du projet Dun & Bradstreet.

1. Sélectionnez les points horizontaux sous la **source** appropriée dans le projet Dun & Bradstreet nouvellement créé pour voir les options disponibles.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Capture d’écran des points dans un projet Dun & Bradstreet.":::

1. Choisissez **Obtenir les détails S3**. Conservez ces informations dans un endroit sûr. Vous en aurez besoin pour [configurer la connexion pour l’enrichissement](#configure-a-connection-for-dun--bradstreet) dans Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Capture d’écran de la sélection des informations s3 dans un projet Dun & Bradstreet.":::

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement

1. Accédez à **Données** > **Enrichissement**.

1. Sélectionnez **Enrichir mes données** sur la vignette Dun & Bradstreet et sélectionnez **Démarrer**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Capture d’écran de la vignette Dun & Bradstreet.":::

1. Sélectionnez une [connexion](connections.md) dans la liste déroulante. Contactez un administrateur si aucune connexion n’est disponible. Si vous êtes un administrateur, vous pouvez créer une connexion. Sélectionnez **Ajouter une connexion** et choisissez **Dun & Bradstreet**.

1. Sélectionnez **Se connecter à Dun & Bradstreet** pour confirmer la connexion.

1. Sélectionnez **Suivant** et choisissez le **Jeu de données client** que vous souhaitez enrichir avec les données d’entreprise de Dun & Bradstreet. Vous pouvez sélectionner l’entité **Client** pour enrichir tous vos profils clients ou sélectionner une entité de segment pour enrichir uniquement les profils clients unifiés contenus dans ce segment.

1. Sélectionnez **Suivant** et définissez les champs de vos profils unifiés qui sont utilisés pour rechercher les données d’entreprise correspondantes de Dun & Bradstreet. Les champs **Numéro DUNS** ou **Nom de la société** et **Pays** sont obligatoires. Le champ de pays prend en charge les [codes pays à deux ou trois lettres](https://www.iso.org/iso-3166-country-codes.html), le nom du pays en anglais, le nom du pays dans la langue native et l’indicatif téléphonique. Certaines variantes de pays courantes incluent :

- US : États-Unis d’Amérique, États-Unis, USA, Amérique.
- CA : Canada.
- GB : Royaume-Uni, R-U, Grande-Bretagne, GB, Royaume-Uni de Grande-Bretagne et d’Irlande du Nord, Royaume-Uni de Grande-Bretagne.
- AU : Australie, Commonwealth d’Australie.
- FR : France, République française.
- DE : Allemagne, allemand, Deutschland, République fédérale d’Allemagne, République d’Allemagne.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Volet de mappage de champs Dun & Bradstreet.":::

1. Sélectionnez **Suivant** pour terminer le mappage de champs.

1. Fournissez un nom pour l’enrichissement et sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.

## <a name="configure-a-connection-for-dun--bradstreet"></a>Configurer une connexion pour Dun & Bradstreet

Vous devez être un administrateur pour configurer les connexions. Sélectionnez **Ajouter une connexion** lors de la configuration d’un enrichissement *ou* accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** sur la vignette Dun & Bradstreet.

1. Cliquez sur **Démarrer**.

1. Entrez un nom pour la connexion dans la zone **Nom d’affichage**.

1. Fournissez des informations d’identification Dun & Bradstreet valides et les détails du projet Dun & Bradstreet, comme la *Région, le chemin d’accès au dossier de dépôt et le nom du dossier de dépôt*. Vous [obtenez ces informations](#setting-up-your-dun--bradstreet-project) du projet Dun & Bradstreet.

1. Vérifiez et donnez votre consentement pour **Confidentialité et conformité des données** en sélectionnant **J’accepte**.

1. Sélectionnez **Vérifier** pour valider la configuration.

1. Une fois la vérification terminée, sélectionnez **Enregistrer**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Page de configuration de la connexion Dun & Bradstreet.":::

## <a name="enrichment-results"></a>Résultats d’enrichissement

Après avoir actualisé l’enrichissement, vous pouvez consulter les données d’entreprise nouvellement enrichies sous [Mes enrichissements](enrichment-hub.md). Vous pouvez trouver l’heure de la dernière mise à jour et le nombre de profils enrichis.

Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.

## <a name="next-steps"></a>Étapes suivantes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Dun & Bradstreet, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous devez vous assurer que Dun & Bradstreet respecte toutes les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour ne plus utiliser cette fonctionnalité.

[!INCLUDE[footer-include](includes/footer-banner.md)]
