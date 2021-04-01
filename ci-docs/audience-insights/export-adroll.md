---
title: Exporter des données Customer Insights vers AdRoll
description: Découvrez comment configurer la connexion à AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697071"
---
# <a name="connector-for-adroll-preview"></a>Connecteur pour AdRoll (version préliminaire)

Exportez des segments de profils clients unifiés vers AdRoll et utilisez-les pour la publicité. 

## <a name="prerequisites"></a>Conditions préalables

-   Vous disposez d’un [compte AdRoll](https://www.adroll.com/) et des informations d’identification administrateur correspondantes.
-   Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.
-   Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="connect-to-adroll"></a>Se connecter à AdRoll

1. Accédez à **Administration** > **Destinations d’exportation**.

1. Sous **AdRoll**, sélectionnez **Configurer**.

1. Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Volet de configuration pour la connexion à AdRoll.":::

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Connecter** pour initialiser la connexion à AdRoll.

1. Sélectionnez **S’authentifier avec AdRoll** et fournissez vos informations d’administrateur pour AdRoll. 

1. Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.

1. Entrez votre **ID d’annonceur AdRoll** [possibilité de publicité AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Sélectionnez **Suivant** pour configurer l’exportation.

## <a name="configure-the-connector"></a>Configurer le connecteur

1. Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client. Il est nécessaire d’exporter des segments vers AdRoll.

1. Sélectionnez les segments que vous souhaitez exporter. Sélectionnez un segment avec au moins 100 membres. Vous ne pouvez pas exporter des segments plus petits. De plus, la taille maximale d’un segment à exporter est de 250 000 membres par exportation. 

1. Sélectionnez **Enregistrer**.

## <a name="export-the-data"></a>Exporter les données

Vous pouvez [exporter les données à la demande](export-destinations.md). L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitations connues

- Vous pouvez exporter jusqu’à 250 000 profils par exportation vers AdRoll.
- Vous ne pouvez pas exporter de segments contenant moins de 100 profils vers AdRoll. 
- L’exportation vers AdRoll est limitée aux segments.
- L’exportation de jusqu’à 250 000 profils vers AdRoll peut prendre jusqu’à 10 minutes. 
- Le nombre de profils que vous pouvez exporter vers AdRoll dépend et est limité par votre contrat avec AdRoll.

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers AdRoll, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que AdRoll respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.
