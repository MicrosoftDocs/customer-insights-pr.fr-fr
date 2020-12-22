---
title: Enrichissement avec l'enrichissement tiers de Experian
description: Informations générales sur l'enrichissement tiers de Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668808"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enrichir les profils des clients avec les données démographiques d'Experian (version préliminaire)

Experian est un leader mondial en marketing et reporting dans le domaine du crédit aux consommateurs et aux entreprises. Avec les Services d'enrichissement de données d'Experian, vous pouvez approfondir votre compréhension de vos clients en enrichissant les profils clients avec des données démographiques telles que la taille du ménage, le revenu, etc.

## <a name="prerequisites"></a>Conditions préalables

Pour configurer Experian, les conditions préalables suivantes doivent être respectées :

- Vous avez un abonnement Experian actif. Pour obtenir un abonnement, [contactez Experian](https://www.experian.com/marketing-services/contact) directement. [Plus d’informations sur l'enrichissement des données Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)
- Vous disposez de l'ID utilisateur, de l'ID de partie et du numéro de modèle du compte Secure Transport (ST) compatible SSH créé pour vous par Experian.
- Vous disposez d'autorisations [Administrateur](permissions.md#administrator) dans Audience Insights.

## <a name="configuration"></a>configuration

1. Accédez à **Données** > **Enrichissement** et sélectionnez l'onglet **Découvrir**.

1. Sélectionnez **Enrichir mes données** sur la vignette Experian.

   > [!div class="mx-imgBorder"]
   > ![Vignette Experian](media/experian-tile.png "Vignette Experian")

1. Sélectionnez **Démarrer** et entrez l'ID utilisateur, l'ID de partie et le numéro de modèle de votre compte Experian Secure Transport. Vérifiez et donnez votre consentement pour **Confidentialité et conformité des données** en cochant la case **J'accepte**. Confirmez toutes les entrées en sélectionnant **Appliquer**.

## <a name="map-your-fields"></a>Mapper vos champs

1. Sélectionnez **Ajouter des données** et choisissez vos identifiants clés parmi **Nom et adresse**,**E-mail**, ou **Téléphone** à envoyer à Experian pour la résolution d'identité.

   > [!TIP]
   > Plus vous envoyez d'attributs d'identifiant de clé à Experian, plus le taux de correspondance a de chances d'être élevé.

1. Sélectionnez **Suivant** et mappez les attributs correspondants provenant de votre entité client unifiée pour les champs d'identificateur de clé sélectionnés.

1. Sélectionnez **Ajouter un attribut** pour mapper les attributs supplémentaires que vous souhaitez envoyer à Experian.

1.  Sélectionnez **Enregistrer** pour terminer le mappage de champs.

   > [!div class="mx-imgBorder"]
   > ![Mappage de champ Experian](media/experian-field-mapping.png "Mappage de champ Experian")

## <a name="enrichment-results"></a>Résultats d'enrichissement

Pour démarrer le processus d'enrichissement, sélectionnez **Exécuter** dans la barre de commandes. Vous pouvez également laisser le système exécuter l'enrichissement automatiquement dans le cadre d'une [actualisation programmée](system.md#schedule-tab). Le temps de traitement dépendra de la taille de vos données clients et des processus d'enrichissement mis en place pour votre compte par Experian.

Une fois le processus d'enrichissement terminé, vous pouvez consulter les données des profils clients nouvellement enrichis sous **Mes enrichissements**. De plus, vous trouverez l'heure de la dernière mise à jour et le nombre de profils enrichis.

Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.

## <a name="next-steps"></a>Étapes suivantes

Exploitez vos données client enrichies. Créez des [Segments](segments.md), des [Mesures](measures.md), voire [Exportez des données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Experian, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Experian respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d'informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour interrompre l'utilisation de cette fonctionnalité.
