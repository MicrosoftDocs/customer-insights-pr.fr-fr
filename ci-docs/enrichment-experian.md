---
title: Enrichissement avec l’enrichissement tiers d’Experian
description: Informations générales sur l’enrichissement tiers d’Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f5aa45316b9e0e99c7ba4389353063e9d3ce06c
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645979"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enrichir les profils client avec les données démographiques de Experian (version préliminaire)

Experian est un leader mondial des services de marketing et de reporting relatifs aux crédits accordés aux consommateurs et aux entreprises. Les services d’enrichissement de données d’Experian vous aident à mieux comprendre vos clients en enrichissant vos profils client avec des données démographiques telles que la taille du foyer, les revenus, et plus encore.

## <a name="prerequisites"></a>Conditions préalables

Pour configurer Experian, les conditions préalables suivantes doivent être remplies :

- Vous disposez d’un abonnement Experian actif. Pour souscrire un abonnement, [contactez Experian](https://www.experian.com/marketing-services/contact) directement. [En savoir plus sur l’enrichissement de données d’Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Une connexion Experian a déjà été configurée par un administrateur *ou* vous disposez d’autorisations [administrateur](permissions.md#admin). Vous avez également besoin de l’ID utilisateur, de l’ID de partie et du numéro de modèle de votre compte de transport sécuritsé (ST) compatible SSH qu’Experian a créé pour vous.

## <a name="supported-countriesregions"></a>Pays/régions pris en charge

Nous prenons actuellement en charge l’enrichissement des profils client aux États-Unis uniquement.

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement

1. Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.

1. Sélectionnez **Enrichir mes données** dans la vignette Experian.

   > [!div class="mx-imgBorder"]
   > ![Vignette Experian.](media/experian-tile.png "Experian tile")
   > 

1. Sélectionnez une [connexion](connections.md) dans la liste déroulante. Contactez un administrateur si aucune connexion n’est disponible. Si vous êtes un administrateur, vous pouvez créer une connexion en sélectionnant **Ajouter une connexion** et en choisissant Experian dans la liste déroulante. 

1. Sélectionnez **Se connecter à Experian** pour confirmer la sélection de la connexion.

1.  Sélectionnez **Suivant** et choisissez le **Jeu de données client** que vous souhaitez enrichir avec les données démographiques d’Experian. Vous pouvez sélectionner l’entité **Client** pour enrichir tous vos profils clients ou sélectionner une entité segment pour enrichir uniquement les profils clients contenus dans ce segment.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Capture d’écran lors du choix du jeu de données client.":::

1. Sélectionnez **Suivant** et définissez le type de champs de vos profils unifiés à utiliser pour rechercher les données démographiques correspondantes d’Experian. Au moins un des champs **Nom et adresse**, **Téléphone** ou **E-mail** est obligatoire. Pour une plus grande précision de la correspondance, vous pouvez ajouter jusqu’à deux autres champs. Cette sélection affectera les champs de mappage auxquels vous avez accès dans l’étape suivante.

    > [!TIP]
    > Si vous envoyez plus d’attributs d’identificateur de clé à Experian, un taux de correspondance plus élevé sera probablement généré.

1. Sélectionnez **Suivant** pour démarrer le mappage de champs.

1. Définissez les champs de vos profils unifiés à utiliser pour rechercher les données démographiques correspondantes d’Experian. Les champs obligatoires sont marqués.

1. Fournissez un nom pour l’enrichissement et un nom pour l’entité de sortie.

1. Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.

## <a name="configure-the-connection-for-experian"></a>Configurer la connexion pour Experian 

Vous devez être un administrateur pour configurer les connexions. Sélectionnez **Ajouter une connexion** lors de la configuration d’un enrichissement *ou* accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** dans la vignette Experian.

1. Cliquez sur **Démarrer**.

1. Entrez un nom pour la connexion dans la zone **Nom d’affichage**.

1. Saisissez un ID utilisateur, un ID de partie et un numéro de modèle valides pour votre compte de transport sécurisé Experian.

1. Vérifiez et donnez votre consentement pour **Confidentialité et conformité des données** en sélectionnant **J’accepte**.

1. Sélectionnez **Vérifier** pour valider la configuration.

1. Une fois la vérification terminée, sélectionnez **Enregistrer**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Volet de configuration de la connexion Experian.":::

## <a name="enrichment-results"></a>Résultats d’enrichissement

Pour démarrer le processus d’enrichissement, sélectionnez **Exécuter** dans la barre de commandes. Vous pouvez également laisser le système exécuter l’enrichissement automatiquement dans le cadre d’une [actualisation programmée](system.md#schedule-tab). Le temps de traitement dépendra de la taille des données de vos clients et des processus d’enrichissement configurés pour votre compte par Experian.

Une fois le processus d’enrichissement terminé, vous pouvez consulter les données des profils clients nouvellement enrichis sous **Mes enrichissements**. De plus, vous trouverez l’heure de la dernière mise à jour et le nombre de profils enrichis.

Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.

## <a name="next-steps"></a>Étapes suivantes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données à Experian, vous autorisez le transfert de données en dehors de la limite de conformité pour Dynamics 365 Customer Insights, y compris les données potentiellement sensibles telles que les données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer qu’Experian respecte vos éventuelles obligations de confidentialité ou de sécurité. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour ne plus utiliser cette fonctionnalité.


[!INCLUDE [footer-include](includes/footer-banner.md)]
