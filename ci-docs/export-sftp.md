---
title: Exporter des données vers les hôtes SFTP (version préliminaire) (contient une vidéo)
description: Apprenez à configurer la connexion et à exporter vers un emplacement SFTP.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207226"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Exporter des données vers des hôtes SFTP (version préliminaire)

Utilisez vos données client dans des applications tierces en les exportant vers un emplacement SFTP (Secure File Transfer Protocol).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Conditions préalables

- Disponibilité d’un hôte SFTP et des informations d’identification correspondantes.

## <a name="known-limitations"></a>Limitations connues

- Les destinations SFTP derrière des pare-feu ne sont actuellement pas prises en charge.
- Le temps d’exécution d’une exportation dépend des performances de votre système. Nous recommandons deux cœurs de processeur et 1 Go de mémoire comme configuration minimale de votre serveur.
- Jusqu’à 100 millions de profils clients, ce qui peut prendre 90 minutes si vous utilisez la configuration minimale recommandée de deux cœurs de processeur et 1 Go de mémoire.
- Si vous utilisez une clé SSH pour l’authentification, assurez-vous que vous [créez votre clé privée](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) au format PEM ou SSH.COM. Si vous utilisez Putty, convertissez votre clé privée en l’exportant en Open SSH. Les formats de clé privée suivants sont pris en charge :
  - RSA au format OpenSSL PEM et ssh.com
  - DSA au format OpenSSL PEM et ssh.com
  - ECDSA 256/384/521 au format OpenSSL PEM
  - ED25519 et RSA au format de clé OpenSSH

## <a name="set-up-connection-to-sftp"></a>Configurer la connexion à SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **SFTP**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Choisissez si vous souhaitez vous authentifier via SSH ou nom d’utilisateur/mot de passe pour votre connexion et fournissez les détails nécessaires. Si vous utilisez une clé SSH pour l’authentification, assurez-vous que vous [créez votre clé privée](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) au format PEM ou SSH.COM. Si vous utilisez Putty, convertissez votre clé privée en l’exportant en Open SSH. Les formats de clé privée suivants sont pris en charge :
   - RSA au format OpenSSL PEM et ssh.com
   - DSA au format OpenSSL PEM et ssh.com
   - ECDSA 256/384/521 au format OpenSSL PEM
   - ED25519 et RSA au format de clé OpenSSH

1. Sélectionnez **Vérifier** pour tester la connexion.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section SFTP. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Choisissez si vous souhaitez exporter vos données **compressées** ou **décompressées** et le **délimiteur de champ** pour les fichiers exportés.

1. Sélectionnez les entités, par exemple des segments, à exporter.

   > [!NOTE]
   > Chaque entité sélectionnée sera fractionnée en un maximum de cinq fichiers de sortie au maximum lors de l’exportation.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> L'exportation d'entités contenant une grande quantité de données peut générer plusieurs fichiers CSV dans le même dossier pour chaque exportation. Le fractionnement des exportations se produit pour des raisons de performances afin de minimiser le temps nécessaire à l'exécution d'une exportation.

[!INCLUDE [footer-include](includes/footer-banner.md)]
