---
title: Enrichissement des données d’identité LiveRamp
description: Enrichissez les profils de clients avec des données LiveRamp.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373028"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Enrichir les profils de clients avec les données d’identité de LiveRamp (version préliminaire) 

LiveRamp fournit une résolution d’identité hors ligne déterministe et une consolidation des données client. Vous pouvez mapper des identifiants personnels dans vos données client avec le graphique d’identité AbiliTec et recevoir des identifiants AbiliTec. Vous pouvez ensuite utiliser ces identifiants pour une meilleure unification de vos données clients. 

## <a name="prerequisites"></a>Conditions préalables 

Pour configurer l’enrichissement, les conditions préalables suivantes doivent être remplies : 

- Vous devez disposer d’un abonnement LiveRamp actif. Pour obtenir un abonnement, contactez votre équipe de compte LiveRamp ou [dynamics@liveramp.com](mailto:dynamics@liveramp.com) pour plus d’informations.   

- Un abonnement AbiliTec actif avec un ID client et un secret pour accéder à l’API. Pour plus d’informations, voir [Hub développeur d’API AbiliTec](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Pays/régions pris en charge 

Nous prenons actuellement en charge l’enrichissement des profils clients avec les données LiveRamp aux États-Unis uniquement. 

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement 

1. Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**. 

1. Sélectionnez **Enrichir mes données** sur la vignette **Identité**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Vignette d’identité dans la page de présentation de l’enrichissement.":::

1. Sélectionnez une [connexion](connections.md) dans la liste déroulante. Contactez un administrateur si aucune connexion n’est disponible. Si vous êtes un administrateur, vous pouvez créer une connexion en sélectionnant **Ajouter une connexion**. Sélectionnez **LiveRamp** dans la liste déroulante. 

1. Sélectionnez **Suivant**, puis choisissez le **Jeu de données client** que vous souhaitez enrichir avec les données de LiveRamp. Vous pouvez sélectionner l’entité *Client* pour enrichir tous vos profils clients ou sélectionner une entité *segment* pour enrichir uniquement les profils clients contenus dans ce segment. 

1. Sélectionnez **Suivant** et définissez le type de champs de vos profils unifiés à utiliser pour rechercher les données d’identité correspondantes de LiveRamp. Au moins l’un des champs **Nom et adresse**, **Téléphone** ou **E-mail** est requis. 

   > [!TIP]
   > Plus vous mappez d’identifiants et de champs clés, plus le taux de correspondance est élevé 

1. Mappez les champs à partir de votre entité *Client* unifié qui sera utilisée pour la correspondance avec le graphique d’identification AbiliTec de LiveRamp. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Options de mappage de données pour l’enrichissement LiveRamp.":::

1. Sélectionnez **Suivant** pour terminer le mappage de champs. 

1. Fournissez un **Nom** pour l’enrichissement et pour l’**Entité de sortie**. 

1. Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix. 

## <a name="configure-the-connection-for-liveramp"></a>Configurer la connexion pour LiveRamp 

Vous devez être un administrateur pour [configurer les connexions](connections.md). Sélectionnez **Ajouter une connexion** lors de la configuration de l’enrichissement ou allez dans **Administrateur** > **Connexions** et sélectionnez **Configurer** sur la vignette **LiveRamp**. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Volet de configuration pour paramétrer la connexion au service LiveRamp AbiliTec. ":::

1. Pour **Nom d’affichage**, entrez le nom de la connexion. 

1. Fournissez un ID client LiveRamp valide et un secret. 

1. Vérifiez et donnez votre consentement pour **Confidentialité et conformité des données** en cochant la case **J’accepte**. 

1. Sélectionnez **Vérifier** pour valider la configuration. 

1. Pour terminer la connexion, sélectionnez **Enregistrer**. 

## <a name="enrichment-results"></a>Résultats d’enrichissement 

Pour démarrer le processus d’enrichissement, sélectionnez Exécuter dans la barre de commandes. Vous pouvez également laisser le système exécuter l’enrichissement automatiquement dans le cadre d’une  [actualisation programmée](system.md#schedule-tab). Le temps de traitement dépend de la taille de vos données client. 

Une fois le processus d’enrichissement terminé, vous pouvez consulter les données des profils client de nouvellement enrichis sous  **Mes enrichissements**. De plus, vous trouverez l’heure de la dernière mise à jour et le nombre de profils enrichis. 

Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant  **Afficher des données enrichies**. 

## <a name="next-steps"></a>Étapes suivantes

Exploitez vos données client enrichies. Utilisez les identifiants AbiliTec pour consolider les profils des clients dans une vue basée sur la personne. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données 

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers LiveRamp, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous devez vous assurer que LiveRamp respecte toutes les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, voir [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour interrompre l’utilisation de cette fonctionnalité. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
