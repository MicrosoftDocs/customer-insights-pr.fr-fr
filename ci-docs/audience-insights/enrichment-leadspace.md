---
title: Enrichissement des profils d’entreprise avec l’enrichissement tiers de Leadspace
description: Informations générales sur l’enrichissement tiers de Leadspace.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f89ef6842c21cf6b78154586f818beffbcdcffb9
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230631"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Enrichissement des profils d’entreprise avec Leadspace (aperçu)

Leadspace est une société de science des données qui fournit une plateforme de données client B2B. Cela permet aux environnements avec des profils clients unifiés basés sur les comptes d’enrichir leurs données. Enrichissez les *Profils clients* avec des attributs tels que la taille, l’emplacement ou le secteur de l’entreprise. Enrichissez *Profils de contact* avec des attributs tels que le titre, le personnage ou la vérification par e-mail.

## <a name="prerequisites"></a>Conditions préalables

Pour configurer Leadspace, les conditions préalables suivantes doivent être respectées :

- Vous disposez d’une licence Leadspace active.
- Vous disposez de [profils clients unifiés](customer-profiles.md) sur la base des comptes.
- Une connexion Leadspace a déjà été configurée par un administrateur ou vous disposez d’autorisations [administrateur](permissions.md#administrator) et de la « clé perpétuelle » (appelée **Jeton Leadspace**). Contactez [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) directement pour obtenir des détails sur leur produit.

## <a name="configure-the-enrichment"></a>Configurer l’enrichissement

1. Dans les informations sur l’audience, accédez à **Données** > **Enrichissement**.

1. Sélectionnez **Enrichir mes données** sur la vignette de Leadspace et sélectionnez **Démarrer**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Capture d’écran de la vignette de Leadspace.":::

1. Sélectionnez une [connexion](connections.md) dans la liste déroulante. Contactez un administrateur si aucune connexion n’est disponible. Si vous êtes un administrateur, vous pouvez créer une connexion en sélectionnant **Ajouter une connexion** et en choisissant **Leadspace**. 

1. Sélectionnez **Se connecter à Leadspace** pour confirmer la connexion.

1. Sélectionnez **Suivant** et choisissez le **Jeu de données client** que vous souhaitez enrichir avec les données d’entreprise de Leadspace. Vous pouvez sélectionner l’entité **Client** pour enrichir tous vos profils clients ou sélectionner une entité segment pour enrichir uniquement les profils clients contenus dans ce segment.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Capture d’écran lors du choix du jeu de données client.":::

1. Sélectionnez **Suivant** et définissez les champs de vos profils unifiés qui sont utilisés pour rechercher les données d’entreprise correspondantes de Leadspace. Le champ **Nom de la société** est obligatoire. Pour une plus grande précision de la correspondance, jusqu’à deux autres champs, **Site web de la société** et **Emplacement de la société**, peuvent être ajoutés.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Volet de mappage de champ de Leadspace.":::

1. Sélectionnez **Suivant** pour terminer le mappage de champs.

1. Cochez la case si vous souhaitez enrichir des *Profils de contact*. Les informations sur l’audience mettront automatiquement en correspondance les champs requis.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Enrichissement des enregistrements de contacts Leadspace.":::
 
1. Fournissez un nom pour l’enrichissement et sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.


## <a name="configure-the-connection-for-leadspace"></a>Configurer la connexion pour Leadspace 

Vous devez être un administrateur pour configurer les connexions. Sélectionnez **Ajouter une connexion** lors de la configuration d’un enrichissement *ou* accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** sur la vignette de Leadspace.

1. Cliquez sur **Démarrer**. 

1. Entrez un nom pour la connexion dans la zone **Nom d’affichage**.

1. Fournissez un jeton Leadspace valide.

1. Vérifiez et donnez votre consentement pour **Confidentialité et conformité des données** en sélectionnant **J’accepte**.

1. Sélectionnez **Vérifier** pour valider la configuration.

1. Une fois la vérification terminée, sélectionnez **Enregistrer**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Page de configuration de la connexion de Leadspace.":::

## <a name="enrichment-results"></a>Résultats d’enrichissement

Après avoir actualisé l’enrichissement, vous pouvez consulter les données d’entreprise nouvellement enrichies sous [Mes enrichissements](enrichment-hub.md). Vous pouvez trouver l’heure de la dernière mise à jour et le nombre de profils enrichis.

Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.

Pour plus d’informations, voir [API Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Étapes suivantes


[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Leadspace, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Leadspace respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour ne plus utiliser cette fonctionnalité.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
