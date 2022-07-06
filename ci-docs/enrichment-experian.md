---
title: Enrichir les profils client avec les données démographiques de Experian (version préliminaire)
description: Informations générales sur l’enrichissement tiers d’Experian.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: a30e98b06ed07590ab95cae1d8db8023e49ff7f9
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053018"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enrichir les profils client avec les données démographiques de Experian (version préliminaire)

Experian est un leader mondial des services de marketing et de reporting relatifs aux crédits accordés aux consommateurs et aux entreprises. Les services d’enrichissement de données d’Experian vous aident à mieux comprendre vos clients en enrichissant vos profils client avec des données démographiques telles que la taille du foyer, les revenus, et plus encore.

## <a name="supported-countriesregions"></a>Pays/régions pris en charge

Nous prenons actuellement en charge l’enrichissement des profils client aux États-Unis uniquement.

## <a name="prerequisites"></a>Conditions préalables

- Un abonnement Experian actif. Pour souscrire un abonnement, [contactez Experian](https://www.experian.com/marketing-services/contact) directement. [En savoir plus sur l’enrichissement de données d’Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Une [connexion Experian](connections.md) est [configurée par un administrateur](#configure-the-connection-for-experian) par un administrateur.

- ID de partie, numéro de modèle et ID utilisateur Experian de votre compte Secure Transport (ST) compatible SSH créé par Experian pour vous.

## <a name="configure-the-connection-for-experian"></a>Configurer la connexion pour Experian

Vous devez être un [administrateur](permissions.md#admin) dans Customer Insights et avoir un ID de partie, un numéro de modèle et un ID utilisateur Experian.

1. Sélectionnez **Ajouter une connexion** lors de la configuration d’un enrichissement ou accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** dans la vignette Experian.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Volet de configuration de la connexion Experian.":::

1. Saisissez un nom pour la connexion et un ID utilisateur, un ID de partie et un numéro de modèle valides pour votre Compte Transport Sécurisé Experian.

1. Vérifiez et donnez votre consentement pour [Confidentialité et conformité des données](#data-privacy-and-compliance) en sélectionnant **J’accepte**.

1. Sélectionnez **Vérifier** pour valider la configuration, puis sélectionnez **Enregistrer**.

### <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données à Experian, vous autorisez le transfert de données en dehors de la limite de conformité pour Dynamics 365 Customer Insights, y compris les données potentiellement sensibles telles que les données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer qu’Experian respecte vos éventuelles obligations de confidentialité ou de sécurité. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour ne plus utiliser cette fonctionnalité.

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement

1. Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.

1. Sélectionnez **Enrichir mes données** dans **Démographie** dans la vignette Experian.

   :::image type="content" source="media/experian-tile.png" alt-text="Vignette Experian dans la page de présentation de l'enrichissement. ":::

1. Passez la synthèse en revue et sélectionnez **Suivant**.

1. Sélectionnez la connexion. Contactez un Administrateur si aucun n'est disponible.

1. Cliquez sur **Suivant**.

1. Sélectionnez le **Jeu de données client**, puis choisissez le profil ou segment que vous souhaitez enrichir avec les données démographiques à partir de Experian. L’entité *Client* enrichit tous vos profils clients tandis qu'un segment enrichit uniquement les profils clients contenus dans ce segment.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Capture d’écran lors du choix du jeu de données client.":::

1. Définissez le type de champs de vos profils unifiés à utiliser pour rechercher les données démographiques à partir de Experian. Au moins un des champs **Nom et adresse**, **Téléphone** ou **E-mail** est obligatoire. Pour une plus grande précision de correspondance, ajoutez d'autres champs. Cliquez sur **Suivant**.

1. Mappez vos champs aux données démographiques à partir de Experian.

1. Sélectionnez **Suivant** pour terminer le mappage de champs.

1. Fournissez un **Nom** pour l’enrichissement et pour le **Nom de l'entité de sortie**.

1. Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.

1. Sélectionnez **Exécuter** pour démarrer le processus d'enrichissement ou fermer pour revenir à la page **Enrichissements**.

## <a name="view-enrichment-results"></a>Afficher les résultats de l’enrichissement

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Le paramètre **Nombre de clients enrichis par champ** fournit une analyse détaillée de la couverture de chaque champ enrichi.

## <a name="next-steps"></a>Étapes suivantes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
