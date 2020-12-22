---
title: Exporter des données Customer Insights vers des hôtes SFTP
description: Découvrez comment configurer la connexion vers un hôte SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643500"
---
# <a name="connector-for-sftp-preview"></a>Connecteur pour SFTP (préversion)

Utilisez vos données client dans des applications tierces en les exportant vers un hôte SFTP (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Conditions préalables

- Disponibilité d'un hôte SFTP et informations d'identification correspondantes.

## <a name="connect-to-sftp"></a>Se connecter à SFTP

1. Accédez à **Administration** > **Destinations d'exportation**.

1. Sous **SFTP**, sélectionnez **Configurer**.

1. Donnez à votre destination un nom reconnaissable dans le champ **Nom complet**.

1. Fournissez un **Nom d'utilisateur**, **Mot de passe** et **Nom d'hôte** pour votre compte SFTP. Exemple : si le dossier racine de votre serveur SFTP est /root/folder et vous souhaitez que les données soient exportées vers /root/folder/ci_export_destination_folder, l'hôte doit être sftp://<server_address>/ci_export_destination_folder.

1. Sélectionnez **Vérifier** pour tester la connexion.

1. Une fois la vérification réussie, choisissez si vous souhaitez exporter vos données **Comprimées** ou **Non comprimées** et sélectionnez le **délimiteur de champ** pour les fichiers exportés.

1. Sélectionnez **J'accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Suivant** pour commencer à configurer l'exportation.

## <a name="configure-the-connection"></a>Configurer la connexion

1. Sélectionnez les **attributs client** que vous souhaitez exporter. Vous pouvez exporter un ou plusieurs attributs.

1. Cliquez sur **Suivant**.

1. Sélectionnez les segments que vous souhaitez exporter.

1. Sélectionnez **Enregistrer**.

## <a name="export-the-data"></a>Exporter les données

Vous pouvez [exporter les données à la demande](export-destinations.md). L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données via SFTP, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que la destination d'exportation respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d'informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d'exportation à tout moment pour interrompre l'utilisation de cette fonctionnalité.
