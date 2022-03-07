---
title: Enrichir les profils clients avec les données de localisation d’Azure Maps
description: Informations générales sur l’enrichissement tiers Azure Maps.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 63f241c27ec86f357c83a301d6797f9ff87c2241
ms.sourcegitcommit: 2acda3c5adf40bc3f5bbb4b2b4b6c22f84371da7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466759"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Enrichissement de profils clients avec Azure Maps (version préliminaire)

Azure Maps fournit des données et des services centrés sur la localisation pour offrir des expériences basées sur les données géospatiales avec l’intelligence de localisation intégrée. Les services d’enrichissement de données Azure Maps améliorent la précision des informations de localisation de vos clients. Il fournit des fonctionnalités telles que la normalisation de l’adresse et l’extraction de la latitude et de la longitude dans Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Conditions préalables

Pour configurer l’enrichissement de données Azure Maps, les conditions préalables suivantes doivent être remplies :

- Vous disposez d’un abonnement Azure Maps actif. Pour souscrire un abonnement, vous pouvez vous [inscrire ou obtenir un essai gratuit](https://azure.microsoft.com/services/azure-maps/).

- Une [connexion](connections.md) Azure Maps est disponible, *ou* vous disposez d’autorisations [administrateur](permissions.md#administrator) et d’une clé d’API Azure Maps active.

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement

1. Accédez à **Données** > **Enrichissement**. 

1. Sur la vignette **Emplacement**, sélectionnez **Enrichir mes données**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Vignette Azure Maps.":::

1. Sélectionnez une [connexion](connections.md) dans la liste déroulante. Contactez un administrateur si aucune connexion Azure Maps n’est disponible. Si vous êtes un administrateur, vous pouvez [configurer la connexion pour Azure Maps](#configure-the-connection-for-azure-maps). 

1. Sélectionnez **Suivant** pour confirmer la sélection.

1. Choisissez le **jeu de données client** que vous souhaitez enrichir avec les données de localisation d’Azure Maps. Vous pouvez sélectionner l’entité **Client** pour enrichir tous vos profils clients unifiés, ou sélectionner une entité de segment pour n’enrichir que les profils clients contenus dans ce segment.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Capture d’écran lors du choix du jeu de données client.":::

1. Choisissez si vous souhaitez mapper les champs à l’adresse principale et/ou secondaire. Vous pouvez spécifier un mappage de champ pour les deux adresses et enrichir les profils pour les deux adresses séparément (par exemple, pour une adresse personnelle et une adresse professionnelle). Sélectionnez **Suivant**.

1. Définissez quels champs de vos profils unifiés utiliser pour rechercher les données de localisation correspondantes depuis Azure Maps. Les champs **Rue 1** et **Code postal** sont obligatoires pour l’adresse principale ou secondaire sélectionnée. Pour une plus grande précision de la correspondance, vous pouvez ajouter d’autres champs.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Page de configuration de l’enrichissement Azure Maps.":::

1. Sélectionnez **Suivant** pour terminer le mappage de champs.

1. Évaluez si vous souhaitez modifier les **Paramètres avancés**. Ceux-ci sont fournis pour offrir une flexibilité maximale pour gérer les cas d’utilisation avancés, mais les valeurs par défaut seront adéquates dans la plupart des cas :
   - **Type d’adresses** : le comportement par défaut est que l’enrichissement renverra la meilleure correspondance d’adresse même si elle est incomplète. Pour obtenir uniquement les adresses complètes, par exemple, les adresses incluant le numéro de la maison, décochez toutes les cases sauf **Adresses des points**. 
   - **Langue** : par défaut, les adresses sont renvoyées dans la langue de la région à laquelle l’adresse a été déterminée comme appartenant. Pour appliquer une langue d’adresse normalisée, sélectionnez la langue dans le menu déroulant. Par exemple, si vous sélectionnez **Anglais**, **Copenhague, Danemark** sera renvoyé au lieu de **København, Danemark**.

1. Fournissez un nom pour l’enrichissement.

1. Vérifiez vos choix, puis sélectionnez **Enregistrer l’enrichissement**.

## <a name="configure-the-connection-for-azure-maps"></a>Configurer la connexion pour Azure Maps

Vous devez être un administrateur dans les informations sur l’audience pour configurer les connexions. Sélectionnez **Ajouter une connexion** lors de la configuration d’un enrichissement ou accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** dans la vignette Azure Maps.

1. Dans la zone **Nom d’affichage**, entrez un nom pour la connexion.

1. Fournissez une clé d’API Azure Maps valide.

1. Vérifiez et donnez votre consentement pour la **Confidentialité et conformité des données** en cochant la case **J’accepte**

1. Sélectionnez **Vérifier** pour valider la configuration.

1. Une fois la vérification terminée, sélectionnez **Enregistrer**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Page de configuration de la connexion Azure Maps.":::

## <a name="enrichment-results"></a>Résultats d’enrichissement

Pour démarrer le processus d’enrichissement, sélectionnez **Exécuter** dans la barre de commandes. Vous pouvez également laisser le système exécuter l’enrichissement automatiquement dans le cadre d’une [actualisation programmée](system.md#schedule-tab). Le temps de traitement dépendra de la taille de vos données clientes et des temps de réponse de l’API.

Une fois le processus d’enrichissement terminé, vous pouvez consulter les données des profils clients nouvellement enrichis sous **Mes enrichissements**. De plus, vous trouverez l’heure de la dernière mise à jour et le nombre de profils enrichis.

Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.

## <a name="next-steps"></a>Étapes suivantes

Exploitez vos données client enrichies. Créez des [Segments](segments.md), des [Mesures](measures.md), voire [Exportez des données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données à Azure Maps, vous autorisez le transfert de données en dehors de la limite de conformité pour Dynamics 365 Customer Insights, y compris les données potentiellement sensibles telles que les données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer qu’Azure Maps respecte vos éventuelles obligations de confidentialité ou de sécurité. Pour plus d’informations, voir [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour interrompre l’utilisation de cette fonctionnalité.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
