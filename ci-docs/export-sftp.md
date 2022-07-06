---
title: Exporter des données vers les hôtes SFTP (version préliminaire) (contient une vidéo)
description: Apprenez à configurer la connexion et à exporter vers un emplacement SFTP.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67789a87cf0ff1b0d9933f2c0adde37762c83476
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081123"
---
# <a name="export-data-to-sftp-preview"></a>Exporter des données vers SFTP (version préliminaire)

Utilisez vos données client dans des applications tierces en les exportant vers un emplacement SFTP (Secure File Transfer Protocol).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Conditions préalables à une connexion

- Disponibilité d’un hôte SFTP et des informations d’identification correspondantes.

## <a name="known-limitations"></a>Limitations connues

- Les destinations SFTP derrière des pare-feu ne sont actuellement pas prises en charge. 
- Le temps d’exécution d’une exportation dépend des performances de votre système. Nous recommandons deux cœurs de processeur et 1 Go de mémoire comme configuration minimale de votre serveur.
- L’exportation d’entités avec jusqu’à 100 millions de profils clients peut prendre 90 minutes si vous utilisez la configuration minimale recommandée de deux cœurs de processeur et 1 Go de mémoire.

## <a name="set-up-connection-to-sftp"></a>Configurer la connexion à SFTP

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **SFTP** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Fournissez un **Nom d’utilisateur**, **Mot de passe**, **Nom d’hôte** et **dossier Exportation** pour votre compte SFTP.

1. Sélectionnez **Vérifier** pour tester la connexion.

1. Choisissez si vous souhaitez exporter vos données **compressées** ou **décompressées** et le **délimiteur de champ** pour les fichiers exportés.

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section SFTP. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.

1. Sélectionnez les entités, par exemple des segments, à exporter.

   > [!NOTE]
   > Chaque entité sélectionnée sera fractionnée en cinq fichiers de sortie au maximum lors de l’exportation.

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).
Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).

> [!TIP]
> L'exportation d'entités contenant une grande quantité de données peut générer plusieurs fichiers CSV dans le même dossier pour chaque exportation. Le fractionnement des exportations se produit pour des raisons de performances afin de minimiser le temps nécessaire à l'exécution d'une exportation.

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données via SFTP, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que la destination d’exportation respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.

[!INCLUDE [footer-include](includes/footer-banner.md)]
