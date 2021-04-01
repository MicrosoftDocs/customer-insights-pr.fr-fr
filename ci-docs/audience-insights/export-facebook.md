---
title: Exporter des données Customer Insights vers Facebook Ads Manager
description: Découvrez comment configurer la connexion au Gestionnaire d’annonces Facebook.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596679"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Connecteur pour le gestionnaire d’annonces Facebook (préversion)

Exportez des segments de profils client unifiés vers le gestionnaire d’annonces Facebook pour créer des campagnes sur Facebook et Instagram.

## <a name="prerequisites"></a>Conditions préalables

- Vous devez avoir un [compte **Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) comprenant un [compte professionnel **Facebook**](https://business.facebook.com/).
- Vous devez être un administrateur du [compte **Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Se connecter au gestionnaire d’annonces Facebook

1. Accédez à **Administration** > **Destinations d’exportation**.

1. Sous le **gestionnaire d’annonces Facebook**, sélectionnez **Configurer**.

1. Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.

1. Sélectionner **Continue avec Facebook** pour vous connecter à votre compte publicitaire Facebook.

1. Activez l’autorisation **ads_management** après l’authentification dans Facebook.

1. Sélectionnez le **Compte d’annonces Facebook** que vous souhaitez utiliser.

1. Sélectionnez une **Audience personnalisée existante** dans la liste déroulante ou créez une **Nouvelle audience personnalisée**. Pour plus d’informations, voir [**Audiences dans le gestionnaire d’annonces Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Suivant** pour configurer l’exportation.

## <a name="configure-the-connector"></a>Configurer le connecteur

1. Dans le champ **Sélectionner votre champ d’identificateur de la clé**, sélectionnez **E-mail**, **Nom et adresse** ou **Téléphone** à envoyer au gestionnaire d’annonces Facebook.

1. Mappez les attributs correspondants de votre entité client unifiée pour l’identifiant de clé sélectionné.
   > [CONSEIL] Les meilleures chances pour une correspondance se produisent si vous sélectionnez **E-mail** comme identificateur de la clé. L’ajout d’identificateurs supplémentaires peut améliorer la correspondance.

1. Sélectionnez **Ajouter un attribut** pour mapper des attributs supplémentaires à envoyer au gestionnaire d’annonces Facebook. Les attributs du gestionnaire d’annonces Facebook correspondent aux noms conviviaux des utilisateurs suivants : **FN** = **Prénom**, **LN** = **Nom de famille**, **FI** = **Première initiale**, **PHONE** = **Téléphone**, **GEN** = **Sexe**, **DOB** = **Date de naissance**, **ST** = **État**, **CT** = **Ville**, **ZIP** = **Code postal**, **COUNTRY** = **Pays/Région**

1. Sélectionnez les segments que vous souhaitez exporter.

1. Sélectionnez **Enregistrer**.

## <a name="export-the-data"></a>Exporter les données

Vous pouvez [exporter les données à la demande](export-destinations.md). L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitations connues

- Jusqu’à 10 millions de profils clients par exportation vers le Gestionnaire publicités Facebook 
- L’exportation vers le Gestionnaire de publicités Facebook est limitée aux segments
- L’exportation de segments avec un total de 10 million de profils peut prendre jusqu’à 90 minutes pour se terminer

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Facebook Ads Manager, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Facebook Ads respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.


[!INCLUDE[footer-include](../includes/footer-banner.md)]