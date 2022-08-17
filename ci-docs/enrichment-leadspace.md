---
title: Enrichir les profils clients avec Leadspace (version préliminaire)
description: Informations générales sur l’enrichissement tiers de Leadspace.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f45fabc036775e11fc439f69513678d0607729d0
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237947"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Enrichir les profils clients avec Leadspace (version préliminaire)

Leadspace est une société de science des données qui fournit une plateforme de données client B2B. Cela permet aux environnements avec des profils clients unifiés basés sur les comptes d’enrichir leurs données. Enrichissez les *Profils clients* avec des attributs tels que la taille, l’emplacement ou le secteur de l’entreprise. Enrichissez *Profils de contact* avec des attributs tels que le titre, le personnage ou la vérification par e-mail.

## <a name="prerequisites"></a>Conditions préalables

- Une licence Leadspace active.
- [Profils clients unifiés](customer-profiles.md) sur la base des comptes.
- Une [connexion](connections.md) Leadspace est [configurée](#configure-the-connection-for-leadspace) par un administrateur. Contactez [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) directement pour obtenir des détails sur leur produit.

## <a name="configure-the-connection-for-leadspace"></a>Configurer la connexion pour Leadspace

Vous devez être un [Administrateur](permissions.md#admin) dans Customer Insights et possèdent la "clé perpétuelle" (appelée **Jeton Leadspace**).

1. Sélectionnez **Ajouter une connexion** lors de la configuration d’un enrichissement ou accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** sur la vignette de Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Page de configuration de la connexion de Leadspace.":::

1. Entrez un nom pour la connexion et un jeton Leadspace valide.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Vérifier** pour valider la configuration, puis sélectionnez **Enregistrer**.

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement

1. Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.

1. Sélectionnez **Enrichir mes données** dans **Données d’entreprise** sur la vignette Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Capture d’écran de la vignette de Leadspace.":::

1. Passez la synthèse en revue et sélectionnez **Suivant**.

1. Sélectionnez la connexion. Contactez un administrateur si aucune connexion n’est disponible.

1. Cliquez sur **Suivant**.

1. Sélectionnez le **Jeu de données client**, puis choisissez le profil ou segment que vous souhaitez enrichir avec les données d'entreprise à partir de Leadspace. L’entité *Client* enrichit tous vos profils clients tandis qu'un segment enrichit uniquement les profils clients contenus dans ce segment.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Capture d’écran lors du choix du jeu de données client.":::

1. Définissez le type de champs de vos profils unifiés à utiliser pour la mise en correspondance : l'adresse principale et/ou secondaire. Vous pouvez spécifier un mappage de champs pour les deux adresses et enrichir les profils pour les deux adresses séparément. Par exemple, pour une adresse personnelle et une adresse professionnelle. Cliquez sur **Suivant**.

1. Mappez vos champs aux données d'entreprise à partir de Leadspace. Le champ **Nom de la société** est obligatoire. Pour une plus grande précision de la correspondance, jusqu’à deux autres champs, **Site web de la société** et **Emplacement de la société**, peuvent être ajoutés.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Volet de mappage de champ de Leadspace.":::

1. Sélectionnez **Suivant** pour terminer le mappage de champs.

1. Cochez la case si vous souhaitez enrichir des *Profils de contact*. Customer Insights mettra automatiquement en correspondance les champs requis.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Enrichissement des enregistrements de contacts Leadspace.":::

1. Cliquez sur **Suivant**.

1. Fournissez un **Nom** pour l’enrichissement et pour le **Nom de l'entité de sortie**.

1. Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.

1. Sélectionnez **Exécuter** pour démarrer le processus d'enrichissement ou fermer pour revenir à la page **Enrichissements**.

## <a name="view-enrichment-results"></a>Afficher les résultats de l’enrichissement

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Pour plus d’informations, voir [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Étapes suivantes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
