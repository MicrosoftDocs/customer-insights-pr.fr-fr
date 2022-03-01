---
title: Démarrer avec la fonction Informations sur l’engagement
description: Un aperçu des ressources d'aide pour démarrer rapidement.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 4552c0b743510ab7c33e8ff1159474f4e83d474d
ms.sourcegitcommit: b78c9680b213204e6b0ed47f0147205083f6a98f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2021
ms.locfileid: "6539295"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Démarrer avec la fonction Informations sur l’engagement Dynamics 365 Customer Insights (version préliminaire publique)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

La fonction Informations sur l’engagement vous permet de collecter et de mesurer le comportement des clients sur votre site Web. Elle s'intègre à la fonction Informations sur l’audience afin de pouvoir voir de riches analyses comportementales en temps réel aux côtés des rapports de profil client. Les liens de cet article vous aident à configurer rapidement votre environnement.

## <a name="step-1-review-prerequisites"></a>Étape 1 : Examiner les conditions requises préalables

Tout d'abord, vous devez avoir un compte d'utilisateur Microsoft Azure Active Directory actif. Ensuite, vous devez lire les articles suivants avant de configurer un espace de travail Informations sur l’engagement.

- Prenez connaissance des [conditions d’utilisation du service](terms-of-service.md) de Microsoft et acceptez-les.  
- Lisez l'article [Gérer les cookies et le consentement des utilisateurs](user-consent-storage.md). Après avoir lu cet article, demandez-vous si vous devez mettre à jour votre notification de consentement de l'utilisateur. Si vous n'aviez auparavant aucun cookie « non essentiel », vous devrez probablement mettre à jour la politique de votre site.
- Consultez le [glossaire](glossary.md) pour découvrir rapidement les termes et les concepts clés.

## <a name="step-2-explore-engagement-insights"></a>Étape 2 : Explorer Informations sur l’engagement

La première fois que vous visitez Informations sur l’engagement, vous pouvez configurer les paramètres, examiner les politiques et explorer le produit.

1. Connectez-vous au portail de la [fonction Informations sur l’engagement](https://pi.dynamics.com) en utilisant votre compte d'utilisateur Microsoft Azure Active Directory. (Il peut s'agir de votre compte scolaire ou professionnel.)

1. Sélectionnez votre région et utilisez la case à cocher pour indiquer si vous acceptez de recevoir des mises à jour et des offres par e-mail.

1. Consultez les **conditions d’utilisation d'Informations sur l'engagement (version préliminaire)** et la **Déclaration de confidentialité.**, puis sélectionnez **Explorer la démonstration** pour les accepter.

1. Explorez le produit à l'aide d'un ensemble d'exemples de données.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Étape 3 : Configurer un espace de travail et ajouter du code à votre site Web

L'espace de travail vous permet de visualiser l'activité des utilisateurs en temps réel, de stocker et de gérer des rapports. Ajoutez du code à votre site Web pour commencer à collecter des *événements*, les données d'activité provenant des utilisateurs.

1. [Créer un espace de travail](create-workspace.md) et ajouter des membres.

1. [Ajoutez du code à votre site Web](instrument-website.md) ou votre [application mobile](developer-resources.md#capture-events-from-mobile-apps) pour voir l’activité utilisateur qui arrive dans votre espace de travail.

1. Affichez un [rapport en temps réel](view-reports.md) indiquant les utilisateurs actifs par navigateur, appareil, système d'exploitation, emplacement et langue. Vous pouvez également créer des [rapports personnalisés](custom-reports.md) pour créer vos propres visualisations.
    
## <a name="step-4-export-data-to-other-channels"></a>Étape 4 : Exporter les données vers d'autres canaux

Vous pouvez créer des *événements affinés* (une vue virtuelle) de vos données d'analyse Web. Vous pouvez ensuite filtrer et exporter les données vers Azure Data Lake Storage. Vous pouvez ingérer les données exportées sous forme de source de données dans [Informations sur l’audience](/audience-insights/integrate-engagement-insights.md).

1. [Créez des événements affinés](refined-events.md) pour l'exportation.

1. [Exportez les données](export-events.md) dans Data Lake Storage.

1. Découvrez comment [supprimer et exporter des données liées aux événements contenant des informations personnelles](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Étape 5 : Rester connecté

Nous apprécions votre participation active et prévoyons de prendre en compte tous les commentaires pertinents lors du développement des futures versions. Partagez vos commentaires et signalez les problèmes par l'un de ces canaux :
- [Communauté](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Fournir des commentaires](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Demande de support](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]