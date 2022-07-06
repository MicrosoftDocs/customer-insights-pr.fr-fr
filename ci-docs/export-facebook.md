---
title: Exporter des segments vers Facebook Ads Manager (version préliminaire) (contient une vidéo)
description: Apprenez à configurer la connexion et à exporter vers Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 782abd7d69166b9c81ac25c4d7e191bdeb03a887
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081169"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Exporter des segments vers Facebook Ads Manager (version préliminaire)

Exportez des segments de profils client unifiés vers Facebook Ads Manager pour créer des campagnes sur Facebook et Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>Conditions préalables à une connexion

- Vous devez disposer d’un compte [**Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) comprenant un [**compte professionnel Facebook**](https://business.facebook.com/).
- Vous devez être un administrateur sur le [**Compte Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Limitations connues

- Jusqu’à 10 millions de profils client par exportation vers Facebook Ads Manager.
- L’exportation vers Facebook Ads Manager est limitée aux segments.
- Créez ou mettez à jour des audiences personnalisées dans Facebook de type *liste de clients* uniquement.
- L’exportation de segments avec un total de 10 million de profils clients peut prendre jusqu’à 90 minutes.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Configurer la connexion à Facebook Ads Manager

Avant que les utilisateurs puissent créer une exportation, un administrateur doit configurer la connexion au service et autoriser les contributeurs à utiliser la connexion.

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Facebook Ads Manager** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. S’authentifier avec Facebook Ads : 

   1. Sélectionnez **Continuer avec Facebook** pour vous connecter à votre compte Facebook Ads.

   1. Activez l’autorisation **ads_management** après l’authentification dans Facebook.

   1. Sélectionnez le **Compte Facebook Ads** que vous souhaitez utiliser.

   1. Sélectionnez une **Audience personnalisée existante** dans la liste déroulante ou créez une **Nouvelle audience personnalisée**. Pour plus d’informations, voir [**Audiences dans Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Vous ne pouvez que créer ou mettre à jour des audiences personnalisées sur Facebook de type *liste de clients* avec cette exportation. Dans certains cas, vous voyez des audiences personnalisées de différents types dans la liste déroulante. Si vous sélectionnez un type autre que *liste de clients*, cela entraînera l’échec de l’exportation. 

1. Passez en revue la **Confidentialité et conformité des données** et sélectionnez **J’accepte**.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**. 

1. Dans **Connexion pour l’exportation**, choisissez une connexion dans la section **Facebook Ads Manager**. Si le nom de la section ne s’affiche pas, aucune connexion de ce type n’est disponible pour vous.

1. Dans le champ **Sélectionner votre champ d’identificateur de la clé**, sélectionnez **E-mail**, **Nom et adresse** ou **Téléphone** à envoyer à Facebook Ads Manager. 

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.

1. Mappez les attributs correspondants de votre entité client unifiée pour l’identifiant de clé sélectionné.
   > [!TIP]
   > Les meilleures chances de correspondance se produisent si vous sélectionnez **E-mail** comme identificateur de la clé. L’ajout d’identificateurs supplémentaires peut améliorer la correspondance.

1. Sélectionnez **Ajouter un attribut** pour mapper d’autres attributs à envoyer vers Facebook Ads Manager. Les attributs de Facebook Ads Manager sont associés aux noms conviviaux suivants : **FN** = **Prénom**, **LN** = **Nom de famille**, **FI** = **Première initiale**, **PHONE** = **Téléphone**, **GEN** = **Sexe**, **DOB** = **Date de naissance**, **ST** = **État**, **CT** = **Ville**, **ZIP** = **Code postal**,**COUNTRY** = **Pays/Région**

1. Sélectionnez les segments que vous souhaitez exporter.

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). 

Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Facebook Ads Manager, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Facebook Ads respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.


[!INCLUDE [footer-include](includes/footer-banner.md)]
