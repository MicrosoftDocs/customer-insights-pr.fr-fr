---
title: Exporter des segments vers Facebook Ads Manager (version préliminaire) (contient une vidéo)
description: Apprenez à configurer la connexion et à exporter vers Facebook Ads Manager.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01be1a075db0da05dc5536aea8a33093f9a2ea13
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195011"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Exporter des segments vers Facebook Ads Manager (version préliminaire)

Exportez des segments de profils client unifiés vers Facebook Ads Manager pour créer des campagnes sur Facebook et Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Conditions préalables

- Un [compte Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) qui inclut un [compte professionnel Facebook](https://business.facebook.com/).
- Privilèges d’administrateur sur le [compte Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Limitations connues

- Jusqu’à 10 million de profils clients par exportation vers Facebook Ads Manager, ce qui peut prendre jusqu’à 90 minutes.
- Segments uniquement.
- Type de *liste de clients* Facebook dans [audiences personnalisées](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) seulement.
  > [!NOTE]
  > Dans certains cas, vous pouvez voir des audiences personnalisées de différents types dans la liste déroulante. Si vous sélectionnez un type autre que *liste de clients*, l’exportation échouera.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Configurer la connexion à Facebook Ads Manager

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion**, puis choisissez **Facebook Ads Manager**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. S’authentifier avec Facebook Ads :

   1. Sélectionnez **Continuer avec Facebook** pour vous connecter à votre compte Facebook Ads.

   1. Activez l’autorisation **ads_management** après l’authentification dans Facebook.

   1. Sélectionnez le **Compte Facebook Ads** que vous souhaitez utiliser.

   1. Sélectionnez une **Audience personnalisée existante** dans la liste déroulante ou créez une **Nouvelle audience personnalisée**.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section Facebook Ads Manager. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Dans le champ **Connecter les données**, sélectionnez **E-mail**, **Nom et adresse** ou **Téléphone** à envoyer à Facebook Ads Manager.

1. Mappez les attributs correspondants de votre entité client unifiée pour l’identifiant de clé sélectionné.
   > [!TIP]
   > Les meilleures chances de correspondance se produisent si vous sélectionnez **E-mail** comme identificateur de la clé. L’ajout d’identificateurs supplémentaires peut améliorer la correspondance.

1. Sélectionnez **Ajouter un attribut** pour mapper d’autres attributs à envoyer vers Facebook Ads Manager. Les attributs de Facebook Ads Manager sont associés aux noms conviviaux suivants : **FN** = **Prénom**, **LN** = **Nom de famille**, **FI** = **Première initiale**, **PHONE** = **Téléphone**, **GEN** = **Sexe**, **DOB** = **Date de naissance**, **ST** = **État**, **CT** = **Ville**, **ZIP** = **Code postal**,**COUNTRY** = **Pays/Région**

1. Sélectionnez les segments que vous souhaitez exporter.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
