---
title: Exporter des segments vers LiveRamp (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196713"
---
# <a name="export-segments-to-liverampreg-preview"></a>Exporter des segments vers LiveRamp&reg; (version préliminaire)

Activez vos données dans LiveRamp pour vous connecter à plus de 500 plateformes dans les écosystèmes numériques, sociaux et télévisés. Exploitez vos données dans LiveRamp pour cibler, supprimer et personnaliser des campagnes publicitaires.

## <a name="prerequisites"></a>Conditions préalables

- Un abonnement LiveRamp pour utiliser ce connecteur. Pour obtenir un abonnement, [contactez LiveRamp](https://liveramp.com/contact/) directement. [En savoir plus sur LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Limitations connues

- L’exportation LiveRamp utilise une exportation SFTP. Les destinations SFTP derrière des pare-feu ne sont actuellement pas prises en charge.
- Si vous utilisez une clé SSH pour l’authentification, assurez-vous que vous [créez votre clé privée](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) au format PEM ou SSH.COM. Si vous utilisez Putty, convertissez votre clé privée en l’exportant en Open SSH. Les formats de clé privée suivants sont pris en charge :
  - RSA au format OpenSSL PEM et ssh.com
  - DSA au format OpenSSL PEM et ssh.com
  - ECDSA 256/384/521 au format OpenSSL PEM
  - ED25519 et RSA au format de clé OpenSSH
- Le temps d’exécution d’une exportation dépend des performances de votre système. Nous recommandons deux cœurs de processeur et 1 Go de mémoire comme configuration minimale de votre serveur.
- L’exportation d’entités avec jusqu’à 100 millions de profils clients peut prendre 90 minutes si vous utilisez la configuration minimale recommandée de deux cœurs de processeur et 1 Go de mémoire.
- Le nombre de profils (ou de données) que vous pouvez exporter vers LiveRamp dépend de votre abonnement à LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Configurer la connexion à LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion**, puis choisissez **LiveRamp**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Choisissez si vous souhaitez vous authentifier via SSH ou nom d’utilisateur/mot de passe pour votre connexion et fournissez les détails nécessaires.

1. Sélectionnez **Vérifier** pour tester la connexion à LiveRamp.

1. Après une vérification réussie, passez en revue la [Confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section LiveRamp. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Dans le champ **Connecter les données**, sélectionnez **E-mail**, **Nom et adresse** ou **Téléphone** à envoyer à LiveRamp pour la résolution des problèmes d’identité.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="Connecteur LiveRamp avec mappage d’attributs.":::

1. Mappez les attributs correspondants de votre entité *Client* pour l’identifiant de clé sélectionné.

1. Sélectionnez **Ajouter un attribut** pour mapper d’autres attributs à envoyer vers LiveRamp.

   > [!TIP]
   > L’envoi d’attributs d’identifiant de clé supplémentaires à LiveRamp est susceptible de vous permettre d’obtenir un taux de correspondance plus élevé.

1. Sélectionnez les segments que vous souhaitez exporter.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
