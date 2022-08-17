---
title: Enrichir les profils clients avec HERE Technologies (version préliminaire)
description: Informations générales sur l’enrichissement tiers de HERE Technologies.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237855"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Enrichir les profils clients avec HERE Technologies (version préliminaire)

HERE Technologies est une société de plateforme de localisation qui fournit des données et des services axés sur la localisation. Les services d'enrichissement des données de HERE Technologies améliorent la précision des informations de localisation de vos clients. Il fournit la normalisation des adresses, l'extraction de la latitude et de la longitude, etc.

## <a name="prerequisites"></a>Conditions préalables

- Un abonnement HERE Technologies actif. Pour obtenir un abonnement, [inscrivez-vous ici](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [contactez HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directement. [En savoir plus sur l’enrichissement de la localisation de HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Une [connexion](connections.md) HERE est [configurée](#configure-the-connection-for-here-technologies) par un administrateur.

## <a name="configure-the-connection-for-here-technologies"></a>Configurer la connexion pour HERE Technologies

Vous devez être un [administrateur](permissions.md#admin) dans Customer Insights et avoir une clé API HERE Technologies active.

1. Sélectionnez **Ajouter une connexion** lors de la configuration d’un enrichissement ou accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** sur la vignette de HERE Technologies.

1. Entrez un nom pour la connexion et une clé API HERE Technologies valide.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Vérifier** pour valider la configuration, puis sélectionnez **Enregistrer**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Page de configuration de la connexion de HERE technologies.":::

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement

1. Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.

1. Sélectionnez **Enrichir mes données** pour l'**Emplacement** dans la vignette HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Vignette de HERE Technologies.":::

1. Passez la synthèse en revue et sélectionnez **Suivant**.

1. Sélectionnez la connexion. Contactez un administrateur si aucune connexion n’est disponible.

1. Cliquez sur **Suivant**.

1. Sélectionnez le **Jeu de données client**, puis choisissez le profil ou segment que vous souhaitez enrichir avec les données d'entreprise à partir de HERE Technologies. L’entité *Client* enrichit tous vos profils clients tandis qu'un segment enrichit uniquement les profils clients contenus dans ce segment.

1. Définissez le type de champs de vos profils unifiés à utiliser pour la mise en correspondance : l'adresse principale et/ou secondaire. Vous pouvez spécifier un mappage de champs pour les deux adresses et enrichir les profils pour les deux adresses séparément. Par exemple, pour une adresse personnelle et une adresse professionnelle. Cliquez sur **Suivant**.

1. Mappez vos champs aux données d'entreprise à partir de HERE Technologies. Les champs **Rue 1** et **Code postal** sont obligatoires pour l’adresse principale et/ou secondaire sélectionnée. Pour une plus grande précision de correspondance, ajoutez plus de champs.

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
