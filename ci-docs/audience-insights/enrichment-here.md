---
title: Enrichissement avec l'enrichissement tiers de HERE Technologies
description: Informations générales sur l'enrichissement tiers de HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668675"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Enrichissement de profils clients avec HERE Technologies (version préliminaire)

HERE Technologies est une société de plateforme de localisation qui fournit des données et des services axés sur la localisation. Avec les services d'enrichissement de données de HERE Technologies, vous pouvez avoir une idée plus précise de la localisation de vos clients avec la normalisation de l'adresse, l'extraction de la latitude et la longitude, etc.

## <a name="prerequisites"></a>Conditions préalables

Pour configurer des enrichissements HERE Technologies, les conditions préalables suivantes doivent être remplies :

- Vous disposez d'un abonnement HERE Technologies actif. Pour obtenir un abonnement, vous pouvez vous [inscrire ici](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [contacter HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directement. [En savoir plus sur l'enrichissement de la localisation de HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Vous disposez de la clé API de HERE Technologies.

- Vous disposez d'autorisations [Administrateur](permissions.md#administrator).

## <a name="configuration"></a>configuration

1. Accédez à **Données** > **Enrichissement**.

1. Sélectionnez **Enrichir mes données** sur la vignette de HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![Vignette de HERE Technologies](media/HERE-tile.png "Vignette de HERE Technologies")

1. Entrez une **Clé API HERE Technologies** active. Vérifiez et donnez votre consentement pour **Confidentialité et conformité des données** en cochant la case **J'accepte**. 

1. Confirmez les deux entrées en sélectionnant **Se connecter à HERE**.

1. Sélectionnez **Ajouter des données** et choisissez si vous souhaitez mapper les champs à l'adresse principale et/ou secondaire. Vous pouvez spécifier un mappage de champ pour les deux adresses (par exemple, une adresse personnelle et professionnelle) et enrichir les profils pour les deux adresses séparément. Cliquez sur **Suivant**.

1. Définissez quels champs de vos profils unifiés doivent être utilisés pour rechercher les données de localisation correspondantes de HERE Technologies. Les champs **Rue 1** et **Code postal** sont obligatoires pour l'adresse principale et/ou secondaire sélectionnée. Pour une plus grande précision de la correspondance, des champs supplémentaires peuvent être ajoutés.

   > [!div class="mx-imgBorder"]
   > ![Page de configuration de l'enrichissement de HERE Technologies](media/enrichment-HERE-configuration.png "Page de configuration de l'enrichissement de HERE Technologies")

1. Sélectionnez **Appliquer** pour terminer le mappage de champ.

## <a name="enrichment-results"></a>Résultats d'enrichissement

Pour démarrer le processus d'enrichissement, sélectionnez **Exécuter** dans la barre de commandes. Vous pouvez également laisser le système exécuter l'enrichissement automatiquement dans le cadre d'une [actualisation programmée](system.md#schedule-tab). Le temps de traitement dépendra de la taille de vos données client et des temps de réponse de l'API de HERE Technologies.

Une fois le processus d'enrichissement terminé, vous pouvez consulter les données des profils clients nouvellement enrichis sous **Mes enrichissements**. De plus, vous trouverez l'heure de la dernière mise à jour et le nombre de profils enrichis.

Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.

## <a name="next-steps"></a>Étapes suivantes

Exploitez vos données client enrichies. Créez des [Segments](segments.md), des [Mesures](measures.md), voire [Exportez des données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers HERE Technologies, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que HERE Technologies respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d'informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour interrompre l'utilisation de cette fonctionnalité.
