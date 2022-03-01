---
title: Exporter les données Customer Insights vers Klaviyo
description: Apprenez à configurer la connexion et à exporter vers Klaviyo.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7c1297fd5381c00c07d6501186c51fe4798773d1
ms.sourcegitcommit: 205f931ec671a0ab1850f2c1c94df3307ffb62c9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7385785"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Exporter les listes de segments vers Klaviyo (version préliminaire)

Exportez les segments des profils client unifiés vers Klaviyo et utilisez-les pour des activités de marketing.

## <a name="prerequisites"></a>Conditions préalables

-   Vous disposez d’un [compte Klaviyo](https://www.klaviyo.com/) et des informations d’identification administrateur correspondantes.
-   Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.
-   Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="known-limitations"></a>Limitations connues

- Vous pouvez exporter jusqu’à 100 000 profils par exportation vers Klaviyo.
- L’exportation vers Klaviyo est limitée aux segments.
- L’exportation d’un maximum de 1 million de profils vers Klaviyo peut prendre jusqu’à 20 minutes. 
- Le nombre de profils exportables vers Klaviyo dépend de votre contrat avec Klaviyo et se limite à ce qui est spécifié dans ce contrat.

## <a name="set-up-connection-to-klaviyo"></a>Configurer la connexion à Klaviyo

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Klaviyo** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Indiquez votre [clé API Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) pour poursuivre la connexion. 

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Connecter** pour initialiser la connexion à Klaviyo.

1. Sélectionnez **Authentification avec Klaviyo** et indiquez vos informations d’identification d’administrateur pour Klaviyo.

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Klaviyo. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.

1. Entrez votre [**ID de liste Klaviyo**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client. C’est obligatoire pour exporter les segments vers Klaviyo.

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Si vous activez Dynamics 365 Customer Insights pour la transmission de données vers Klaviyo, vous autorisez le transfert des données en dehors de la limite de conformité pour Dynamics 365 Customer Insights, y compris les données potentiellement sensibles telles que les données personnelles. Microsoft transfère ces données selon vos instructions, mais vous êtes tenu de vous assurer que Klaviyo respecte vos éventuelles obligations de confidentialité ou de sécurité. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.
