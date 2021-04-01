---
title: Exporter des données Customer Insights vers des hôtes SFTP
description: Découvrez comment configurer la connexion vers un hôte SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598382"
---
# <a name="connector-for-sftp-preview"></a>Connecteur pour SFTP (préversion)

Utilisez vos données client dans des applications tierces en les exportant vers un hôte SFTP (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Conditions préalables

- Disponibilité d’un hôte SFTP et des informations d’identification correspondantes.

## <a name="connect-to-sftp"></a>Se connecter à SFTP

1. Accédez à **Administration** > **Destinations d’exportation**.

1. Sous **SFTP**, sélectionnez **Configurer**.

1. Donnez à votre destination un nom reconnaissable dans le champ **Nom complet**.

1. Fournissez un **Nom d’utilisateur**, **Mot de passe**, **Nom d’hôte** et **dossier Exportation** pour votre compte SFTP.

1. Sélectionnez **Vérifier** pour tester la connexion.

1. Après une vérification réussie, choisissez si vous souhaitez exporter vos données **Gzippé** ou **Décompressées**, et sélectionnez le **délimiteur de champ** pour les fichiers exportés.

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Suivant** pour commencer à configurer l’exportation.

## <a name="configure-the-export"></a>Configurer l’exportation

1. Sélectionnez les entités, par exemple des segments, à exporter.

   > [!NOTE]
   > Chaque entité sélectionnée aura jusqu’à cinq fichiers de sortie lors de l’exportation. 

1. Sélectionnez **Enregistrer**.

## <a name="export-the-data"></a>Exporter les données

Vous pouvez [exporter les données à la demande](export-destinations.md). L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitations connues

- Le temps d’exécution d’une exportation dépend des performances de votre système. Nous recommandons deux cœurs de processeur et 1 Go de mémoire comme configuration minimale de votre serveur. 
- L’exportation d’entités avec jusqu’à 100 millions de profils clients peut prendre 90 minutes si vous utilisez la configuration minimale recommandée de deux cœurs de processeur et 1 Go de mémoire. 

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données via SFTP, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que la destination d’exportation respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.


[!INCLUDE[footer-include](../includes/footer-banner.md)]