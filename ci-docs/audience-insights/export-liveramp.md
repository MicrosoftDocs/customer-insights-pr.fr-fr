---
title: Connecteur LiveRamp
description: Découvrez comment exporter des données vers LiveRamp.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597554"
---
# <a name="liverampreg-connector-preview"></a>Connecteur&reg; LiveRamp (aperçu)

Activez vos données dans LiveRamp pour vous connecter à plus de 500 plateformes à travers les écosystèmes numériques, sociaux et télévisuels. Exploitez vos données dans LiveRamp pour cibler, supprimer et personnaliser des campagnes publicitaires.

## <a name="prerequisites"></a>Conditions préalables

- Vous avez besoin d’un abonnement LiveRamp pour utiliser ce connecteur.
- Pour obtenir un abonnement, [contactez LiveRamp](https://liveramp.com/contact/) directement. [En savoir plus sur LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Se connecter à LiveRamp

1. Dans les informations sur l’audience, accédez à **Administration** > **Destinations d’exportation**.

1. Dans la vignette **LiveRamp**, sélectionnez **Configurer**.

1. Donnez à votre destination un nom reconnaissable dans le champ **Nom complet**.

1. Fournissez un **Nom d’utilisateur** et un **Mot de passe** pour votre compte LiveRamp Secure FTP (SFTP).
Ces informations d’identification peuvent être différentes de vos informations d’identification à LiveRamp Onboarding.

1. Sélectionnez **Vérifier** pour tester la connexion à LiveRamp.

1. Une fois la vérification réussie, donnez votre consentement pour **Confidentialité et conformité des données** en cochant la case **J’accepte**.

1. Sélectionnez **Suivant** pour configurer le connecteur LiveRamp.

## <a name="configure-the-connector"></a>Configurer le connecteur

1. Dans le champ **Choisir votre identifiant de clé**, sélectionnez **E-mail**, **Nom et adresse** ou **Téléphone** à envoyer à LiveRamp pour la résolution des problèmes d’identité.

1. Mappez les attributs correspondants de votre entité client unifiée pour l’identifiant de clé sélectionné.

1. Sélectionnez **Ajouter un attribut** pour mapper des attributs supplémentaires à envoyer à LiveRamp.

   > [!TIP]
   > L’envoi d’attributs d’identifiant de clé supplémentaires à LiveRamp est susceptible de vous permettre d’obtenir un taux de correspondance plus élevé.

1. Sélectionnez les segments que vous souhaitez exporter vers LiveRamp.

1. Sélectionnez **Enregistrer**.

> [!div class="mx-imgBorder"]
> ![Connecteur LiveRamp avec mappage d’attributs](media/export-liveramp-segments.png "Connecteur LiveRamp avec mappage d’attributs")

## <a name="export-the-data"></a>Exporter les données

L’exportation doit démarrer rapidement si toutes les conditions préalables requises pour l’exportation sont satisfaites. L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).
Une fois l’exportation terminée, vous pouvez vous connecter à LiveRamp Onboarding pour activer et distribuer vos données.

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Liveramp, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Liveramp respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.

[!INCLUDE[footer-include](../includes/footer-banner.md)]