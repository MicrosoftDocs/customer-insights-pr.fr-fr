---
title: Enrichir les profils clients avec les données de localisation d’Azure Maps
description: Informations générales sur l’enrichissement tiers Azure Maps.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a806b2d0c791972c967c90694527608b4def9f3f
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953625"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Enrichissement de profils clients avec Azure Maps (version préliminaire)

Azure Maps fournit des données et services axés sur l’emplacement pour offrir des expériences basées sur des données géospatiales avec une intelligence de localisation intégrée. Les services d’enrichissement de données Azure Maps améliorent la précision des informations de localisation de vos clients. Il fournit des fonctionnalités telles que la normalisation de l’adresse et l’extraction de la latitude et de la longitude dans Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Conditions préalables

- Un abonnement Azure Maps actif. Pour obtenir un abonnement, [inscrivez-vous ou obtenez une évaluation gratuite](https://azure.microsoft.com/services/azure-maps/).

- Une [connexion](connections.md) Azure Maps est [configurée](#configure-the-connection-for-azure-maps) par un administrateur.

## <a name="configure-the-connection-for-azure-maps"></a>Configurer la connexion pour Azure Maps

Vous devez être un [administrateur](permissions.md#admin) dans Customer Insights et avoir une clé API Azure Maps active.

1. Sélectionnez **Ajouter une connexion** lors de la configuration d’un enrichissement ou accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** dans la vignette Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Page de configuration de la connexion Azure Maps.":::

1. Entrez un nom pour la connexion et une clé API Azure Maps valide.

1. Vérifiez et donnez votre consentement pour [Confidentialité et conformité des données](#data-privacy-and-compliance) en sélectionnant **J’accepte**.

1. Sélectionnez **Vérifier** pour valider la configuration, puis sélectionnez **Enregistrer**.

### <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données à Azure Maps, vous autorisez le transfert de données en dehors de la limite de conformité pour Dynamics 365 Customer Insights, y compris les données potentiellement sensibles telles que les données personnelles. Microsoft transférera ces données selon vos instructions, mais vous devez vous assurer qu’Azure Maps respecte toutes les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, voir [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour interrompre l’utilisation de cette fonctionnalité.

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement

1. Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.

1. Sélectionnez **Enrichir mes données** pour l'**Emplacement** dans la vignette Microsoft Azure Maps.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Vignette Azure Maps.":::

1. Passez la synthèse en revue et sélectionnez **Suivant**.

1. Sélectionnez la connexion. Contactez un administrateur si aucune connexion n’est disponible.

1. Cliquez sur **Suivant**.

1. Sélectionnez le **Jeu de données client**, puis choisissez le profil ou segment que vous souhaitez enrichir avec les données démographiques à partir de Microsoft. L’entité *Client* enrichit tous vos profils clients tandis qu'un segment enrichit uniquement les profils clients contenus dans ce segment.

1. Définissez le type de champs de vos profils unifiés à utiliser pour la mise en correspondance : l'adresse principale et/ou secondaire. Vous pouvez spécifier un mappage de champs pour les deux adresses et enrichir les profils pour les deux adresses séparément. Par exemple, pour une adresse personnelle et une adresse professionnelle. Cliquez sur **Suivant**.

1. Mappez vos champs aux données de localisation à partir d'Azure Maps. Les champs **Rue 1** et **Code postal** sont obligatoires pour l’adresse principale et/ou secondaire sélectionnée. Pour une plus grande précision de correspondance, ajoutez plus de champs.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Mappage d'attributs Azure Maps.":::

1. Sélectionnez **Suivant** pour terminer le mappage de champs.

1. Consultez **Paramètres avancés** qui offrent une flexibilité maximale pour gérer les cas d'utilisation avancés. Cependant, les valeurs par défaut suivantes n'ont généralement pas besoin d'être modifiées.

   - **Type d'adresses** : la meilleure correspondance d'adresse est renvoyée même si elle est incomplète. Pour obtenir uniquement les adresses complètes, par exemple, les adresses incluant le numéro de la maison, décochez toutes les cases sauf **Adresses des points**.
   - **Langue** : les adresses sont renvoyées dans la langue en fonction de la région de l'adresse. Pour appliquer une langue d’adresse normalisée, sélectionnez la langue dans le menu déroulant. Par exemple, la sélection de **Anglais** renvoie **Copenhague, Danemark** à la place de **København, Danemark**.
   - **Nombre maximal de résultats** : Nombre de résultats par adresse.

1. Cliquez sur **Suivant**.

1. Fournissez un **Nom** pour l’enrichissement et pour le **Nom de l'entité de sortie**.

1. Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.

1. Sélectionnez **Exécuter** pour démarrer le processus d'enrichissement ou fermer pour revenir à la page **Enrichissements**.

## <a name="enrichment-results"></a>Résultats d’enrichissement

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Le paramètre **Nombre de clients enrichis par champ** fournit une analyse détaillée de la couverture de chaque champ enrichi.

## <a name="next-steps"></a>Étapes suivantes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
