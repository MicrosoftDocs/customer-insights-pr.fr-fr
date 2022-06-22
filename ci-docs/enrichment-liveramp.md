---
title: Enrichissement des données d’identité LiveRamp
description: Enrichissez les profils de clients avec des données LiveRamp.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e8a130865267b57c89157b44be3d4bba3dc2fb4e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953992"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Enrichir les profils de clients avec les données d’identité de LiveRamp (version préliminaire)

LiveRamp fournit une résolution d’identité hors ligne déterministe et une consolidation des données client. Vous pouvez mapper des identifiants personnels dans vos données client avec le graphique d’identité AbiliTec et recevoir des identifiants AbiliTec. Vous pouvez ensuite utiliser ces identifiants pour une meilleure unification de vos données clients.

## <a name="supported-countriesregions"></a>Pays/régions pris en charge

Nous prenons actuellement en charge l’enrichissement des profils clients avec les données LiveRamp aux États-Unis uniquement.

## <a name="prerequisites"></a>Conditions préalables

- Un abonnement LiveRamp actif. Pour obtenir un abonnement, contactez votre équipe de compte LiveRamp ou [dynamics@liveramp.com](mailto:dynamics@liveramp.com) pour plus d’informations.

- Un abonnement AbiliTec actif avec un ID client et un secret pour accéder à l’API. Pour plus d’informations, voir [Hub développeur d’API AbiliTec](https://developers.liveramp.com/abilitec-api/).

- Une [connection](connections.md) LiveRamp est [configurée](#configure-the-connection-for-liveramp) par un administrateur.

## <a name="configure-the-connection-for-liveramp"></a>Configurer la connexion pour LiveRamp

Vous devez être un [Administrateur](permissions.md#admin) dans Customer Insights et avoir un ID et un secret de client LiveRamp actifs.

1. Sélectionnez **Ajouter une connexion** lors de la configuration d'un enrichissement ou accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** sur la vignette LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Volet de configuration pour paramétrer la connexion au service LiveRamp AbiliTec. ":::

1. Saisissez un nom pour la connexion, un ID client LiveRamp valide et un secret.

1. Vérifiez et donnez votre consentement pour [Confidentialité et conformité des données](#data-privacy-and-compliance) en sélectionnant **J’accepte**.

1. Sélectionnez **Vérifier** pour valider la configuration, puis sélectionnez **Enregistrer**.

### <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers LiveRamp, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous devez vous assurer que LiveRamp respecte toutes les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, voir [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour interrompre l’utilisation de cette fonctionnalité.

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement

1. Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.

1. Sélectionnez **Enrichir mes données** pour l'**Identité** dans la vignette LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Vignette d’identité dans la page de présentation de l’enrichissement.":::

1. Passez la synthèse en revue et sélectionnez **Suivant**.

1. Sélectionnez la connexion. Contactez un Administrateur si aucun n'est disponible.

1. Cliquez sur **Suivant**.

1. Sélectionnez le **Jeu de données client**, puis choisissez le profil ou segment que vous souhaitez enrichir avec les données de LiveRamp. L’entité *Client* enrichit tous vos profils clients tandis qu'un segment enrichit uniquement les profils clients contenus dans ce segment.

1. Définissez le type de champs de vos profils unifiés à utiliser pour rechercher les données d'identité correspondantes de LiveRamp. Au moins l'un des champs **Nom et adresse**, **E-mail** ou **Téléphone** est requis. Pour une plus grande précision de correspondance, ajoutez d'autres champs. Cliquez sur **Suivant**.

1. Mappez vos champs aux données d'identification de LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Options de mappage de données pour l’enrichissement LiveRamp.":::

1. Sélectionnez **Suivant** pour terminer le mappage de champs.

1. Fournissez un **Nom** pour l’enrichissement et pour le **Nom de l'entité de sortie**.

1. Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.

1. Sélectionnez **Exécuter** pour démarrer le processus d'enrichissement ou fermer pour revenir à la page **Enrichissements**.

## <a name="enrichment-results"></a>Résultats d’enrichissement

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Le paramètre **Nombre de clients enrichis par champ** fournit une analyse détaillée de la couverture de chaque champ enrichi.

## <a name="next-steps"></a>Étapes suivantes

Exploitez vos données client enrichies. Utilisez les identifiants AbiliTec pour consolider les profils des clients dans une vue basée sur la personne.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
