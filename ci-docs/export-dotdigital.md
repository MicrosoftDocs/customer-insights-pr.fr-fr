---
title: Exporter des données Customer Insights vers DotDigital
description: Apprenez à configurer la connexion et à exporter vers DotDigital.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f63a0f5f5f93e96681a88fd758381c012a404f43
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645972"
---
# <a name="export-segments-to-dotdigital-preview"></a>Exporter des segments vers DotDigital (version préliminaire)

Exportez des segments de profils clients unifiés vers les carnets d’adresses DotDigital et utilisez-les pour les campagnes, le marketing par e-mail, ainsi que pour créer des segments de client avec DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Conditions préalables à une connexion

-   Vous avez un [compte DotDigital](https://dotdigital.com/) et vous avez créé un [utilisateur API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). Vous devrez utiliser les informations d’identification de l’utilisateur de l’API pour créer une connexion
-   Il existe des carnets d’adresses dans DotDigital et les ID correspondants. L’ID se trouve dans l’URL lorsque vous sélectionnez et ouvrez un carnet d’adresses. Pour plus d’informations, consultez [Carnets d’adresses DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Vous avez des [segments configurés](segments.md) dans Customer Insights.
-   Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Jusqu’à 1 million de profils clients par exportation vers DotDigital.
- L’exportation vers DotDigital est limitée aux segments.
- L’exportation de segments avec un total de 1 million de profils clients peut prendre jusqu’à 3 heures en raison des limitations du côté du fournisseur. 
- Le nombre de profils clients que vous pouvez exporter vers DotDigital dépend de votre contrat et est limité à DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Configurer la connexion à DotDigital

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **DotDigital** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Entrez vos **Nom d’utilisateur et mot de passe DotDigital**. 

1. Entrez votre **[ID de carnet d’adresses DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Connecter** pour initialiser la connexion à DotDigital.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion. 

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section DotDigital. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.


1. Dans la section **Correspondance des données**, dans le champ **E-mail**, sélectionnez le champ qui représente l’adresse e-mail d’un client. Répétez les mêmes étapes pour les autres champs facultatifs tels que **Prénom**, **Nom**, **Nom complet**, **Sexe** et **Code postal**.

1. Sélectionnez les segments que vous souhaitez exporter. Vous pouvez exporter jusqu’à 1 million de profils clients au total vers DotDigital.

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 
 
Dans DotDigital, vous trouverez désormais vos segments dans le [Carnets d’adresses DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers DotDigital, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que DotDigital respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.


[!INCLUDE [footer-include](includes/footer-banner.md)]