---
title: Connecteur LiveRamp
description: Apprenez à configurer la connexion et à exporter vers LiveRamp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4c0f58083e8486d2042d8efcc8b3690020efb1c3
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226349"
---
# <a name="export-segments-to-liverampreg-preview"></a>Exporter des segments vers LiveRamp&reg; (version préliminaire)

Activez vos données dans LiveRamp pour vous connecter à plus de 500 plateformes dans les écosystèmes numériques, sociaux et télévisés. Exploitez vos données dans LiveRamp pour cibler, supprimer et personnaliser des campagnes publicitaires.

## <a name="prerequisites-for-a-connection"></a>Conditions préalables à une connexion

- Vous avez besoin d’un abonnement LiveRamp pour utiliser ce connecteur.
- Pour obtenir un abonnement, [contactez LiveRamp](https://liveramp.com/contact/) directement. [En savoir plus sur LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Configurer la connexion à LiveRamp

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **LiveRamp** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Fournissez un **Nom d’utilisateur** et un **Mot de passe** pour votre compte LiveRamp Secure FTP (SFTP).
Ces informations d’identification peuvent être différentes de vos informations d’identification à LiveRamp Onboarding.

1. Sélectionnez **Vérifier** pour tester la connexion à LiveRamp.

1. Une fois la vérification réussie, donnez votre consentement pour **Confidentialité et conformité des données** en cochant la case **J’accepte**.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section LiveRamp. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.

1. Dans le champ **Choisir votre identifiant de clé**, sélectionnez **E-mail**, **Nom et adresse** ou **Téléphone** à envoyer à LiveRamp pour la résolution des problèmes d’identité.
   > [!div class="mx-imgBorder"]
   > ![Connecteur LiveRamp avec mappage d’attributs.](media/export-liveramp-segments.png "Connecteur LiveRamp avec mappage d’attributs")

1. Mappez les attributs correspondants de votre entité *Client* pour l’identifiant de clé sélectionné.

1. Sélectionnez **Ajouter un attribut** pour mapper d’autres attributs à envoyer vers LiveRamp.

   > [!TIP]
   > L’envoi d’attributs d’identifiant de clé supplémentaires à LiveRamp est susceptible de vous permettre d’obtenir un taux de correspondance plus élevé.

1. Sélectionnez les segments que vous souhaitez exporter vers LiveRamp.

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Liveramp, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Liveramp respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
