---
title: Enrichissement des profils d'entreprise avec l'enrichissement tiers de Leadspace
description: Informations générales sur l'enrichissement tiers de Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668720"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Enrichissement des profils d'entreprise avec Leadspace (aperçu)

Leadspace est une entreprise de science des données qui fournit une plateforme de données client B2B. Elle permet aux clients ayant un profil client unifié pour les entreprises d'enrichir leurs données. Les enrichissements comprennent des attributs supplémentaires tels que la taille de l'entreprise, sa localisation, son secteur d'activité, etc.

## <a name="prerequisites"></a>Conditions préalables

Pour configurer Leadspace, les conditions préalables suivantes doivent être respectées :

- Vous disposez d'une licence Leadspace active et de la « clé perpétuelle » (appelée **Jeton Leadspace**). Contactez directement [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) pour en savoir plus sur leur produit.
- Vous disposez d'autorisations [Administrateur](permissions.md#administrator).
- Vous avez des [profils clients unifiés](customer-profiles.md) pour les entreprises.

## <a name="configuration"></a>configuration

1. Dans Audience Insights, accédez à **Données** > **Enrichissement**.

1. Sélectionnez **Enrichir mes données** sur la vignette Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Capture d'écran de la vignette de Leadspace.":::

1. Sélectionnez **Démarrer**, puis entrez un **Jeton Leadspace** actif (clé perpétuelle). Vérifiez et donnez votre consentement pour **Confidentialité et conformité des données** en cochant la case **J'accepte**. Confirmez les deux entrées en sélectionnant **Se connecter à Leadspace**.

1. Sélectionnez **Mapper les données** et définissez quels champs de vos profils unifiés doivent être utilisés pour rechercher les données d'entreprise correspondantes de Leadspace. Le champ **Nom de la société** est obligatoire. Pour une plus grande précision de la correspondance, jusqu'à deux autres champs, **Site web de la société** et **Emplacement de la société**, peuvent être ajoutés.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Volet de mappage de champ de Leadspace.":::
   
1. Sélectionnez **Appliquer** pour terminer le mappage de champ.

1. Sélectionnez **Exécuter** pour enrichir les profils d'entreprise. La durée d'un enrichissement dépend du nombre de profils clients unifiés.

## <a name="enrichment-results"></a>Résultats d'enrichissement

Après avoir actualisé l'enrichissement, vous pouvez consulter les données d'entreprise nouvellement enrichies sous [Mes enrichissements](enrichment-hub.md). Vous pouvez trouver l'heure de la dernière mise à jour et le nombre de profils enrichis.

Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.

Pour plus d’informations, voir [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Étapes suivantes

Exploitez vos données client enrichies. Créez des [Segments](segments.md), des [Mesures](measures.md), voire [Exportez des données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Leadspace, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Leadspace respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d'informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour interrompre l'utilisation de cette fonctionnalité.