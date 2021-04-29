---
title: Enrichissement avec l’enrichissement tiers de Experian
description: Informations générales sur l’enrichissement tiers de Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896370"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enrichir les profils des clients avec les données démographiques d’Experian (version préliminaire)

Experian est un leader mondial en marketing et reporting dans le domaine du crédit aux consommateurs et aux entreprises. Avec les Services d’enrichissement de données d’Experian, vous pouvez approfondir votre compréhension de vos clients en enrichissant les profils clients avec des données démographiques telles que la taille du ménage, le revenu, etc.

## <a name="prerequisites"></a>Conditions préalables

Pour configurer Experian, les conditions préalables suivantes doivent être respectées :

- Vous avez un abonnement Experian actif. Pour obtenir un abonnement, [contactez Experian](https://www.experian.com/marketing-services/contact) directement. [Plus d’informations sur l’enrichissement des données Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)

- Une connexion Experian a déjà été configurée par un administrateur *ou* vous disposez d’autorisations [administrateur](permissions.md#administrator). Vous avez également besoin de l’ID d’utilisateur, de l’ID de partie et du numéro de modèle de votre compte Secure Transport (ST) compatible SSH qu’Experian a créé pour vous.

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement

1. Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.

1. Sélectionnez **Enrichir mes données** sur la vignette Experian.

   > [!div class="mx-imgBorder"]
   > ![Vignette Experian](media/experian-tile.png "Vignette Experian")
   > 

1. Sélectionnez une [connexion](connections.md) dans le menu déroulant. Contactez un administrateur si aucune connexion n’est disponible. Si vous êtes un administrateur, vous pouvez créer une connexion en sélectionnant **Ajouter une connexion** et en choisissant Experian dans le menu déroulant. 

1. Sélectionnez **Se connecter à Experian** pour confirmer la sélection de la connexion.

1.  Sélectionnez **Suivant** et choisissez le **Jeu de données client** que vous souhaitez enrichir avec les données démographiques d’Experian. Vous pouvez sélectionner l’entité **Client** pour enrichir tous vos profils clients ou sélectionner une entité segment pour enrichir uniquement les profils clients contenus dans ce segment.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Capture d’écran lors du choix du jeu de données client.":::

1. Sélectionnez **Suivant** et définissez le type de champ de vos profils unifiés à utiliser pour rechercher les données démographiques correspondantes d’Experian. Au moins un des champs **Nom et adresse**, **Téléphone** ou **E-mail** est obligatoire. Pour une plus grande précision de la correspondance, vous pouvez ajouter jusqu’à deux autres champs. Cette sélection affectera les champs de mappage auxquels vous avez accès dans l’étape suivante.

    > [!TIP]
    > Plus vous envoyez d’attributs d’identifiant de clé à Experian, plus le taux de correspondance a de chances d’être élevé.

1. Sélectionnez **Suivant** pour démarrer le mappage de champs.

1. Définissez les champs de vos profils unifiés à utiliser pour rechercher les données démographiques correspondantes d’Experian. Les champs obligatoires sont marqués.

1. Fournissez un nom pour l’enrichissement et un nom pour l’entité de sortie.

1. Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.

## <a name="configure-the-connection-for-experian"></a>Configurer la connexion pour Experian 

Vous devez être un administrateur pour configurer les connexions. Sélectionnez **Ajouter une connexion** lors de la configuration d’un enrichissement *ou* accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** sur la vignette d’Experian.

1. Cliquez sur **Démarrer**.

1. Entrez un nom pour la connexion dans la zone **Nom d’affichage**.

1. Entrez un ID d’utilisateur, un ID de partie et un numéro de modèle valides pour votre compte Secure Transport d’Experian.

1. Vérifiez et donnez votre consentement pour la **Confidentialité et conformité des données** en cochant la case **J’accepte**

1. Sélectionnez **Vérifier** pour valider la configuration.

1. Une fois la vérification terminée, sélectionnez **Enregistrer**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Volet de configuration de la connexion d’Experian.":::

## <a name="enrichment-results"></a>Résultats d’enrichissement

Pour démarrer le processus d’enrichissement, sélectionnez **Exécuter** dans la barre de commandes. Vous pouvez également laisser le système exécuter l’enrichissement automatiquement dans le cadre d’une [actualisation programmée](system.md#schedule-tab). Le temps de traitement dépendra de la taille de vos données clients et des processus d’enrichissement mis en place pour votre compte par Experian.

Une fois le processus d’enrichissement terminé, vous pouvez consulter les données des profils clients nouvellement enrichis sous **Mes enrichissements**. De plus, vous trouverez l’heure de la dernière mise à jour et le nombre de profils enrichis.

Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.

## <a name="next-steps"></a>Étapes suivantes

Exploitez vos données client enrichies. Créez des [Segments](segments.md), des [Mesures](measures.md), voire [Exportez des données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Experian, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Experian respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour interrompre l’utilisation de cette fonctionnalité.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
