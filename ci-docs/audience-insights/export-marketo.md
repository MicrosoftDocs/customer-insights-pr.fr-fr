---
title: Exporter des données Customer Insights vers Marketo
description: Découvrez comment configurer la connexion à Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570400"
---
# <a name="connector-for-marketo-preview"></a>Connecteur pour Marketo (version préliminaire)

Exportez des segments de profils clients unifiés pour générer des campagnes, fournir des activités de marketing par e-mail et utiliser certains groupes de clients avec Marketo.

## <a name="prerequisites"></a>Conditions préalables

-   Vous disposez d'un [compte Marketo](https://login.marketo.com/) et des informations d'identification administrateur correspondantes.
-   Il existe des listes dans Marketo et les ID correspondants. Pour plus d'informations, consultez [Listes Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Vous avez [configuré des segments](segments.md).
-   Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.

## <a name="connect-to-marketo"></a>Se connecter à Marketo

1. Accédez à **Administration** > **Destinations d'exportation**.

1. Sous **Marketo**, sélectionnez **Configurer**.

1. Donnez à votre destination d’exportation un nom reconnaissable dans le champ **Nom complet**.

1. Entrez vos **[ID de client Marketo, secret client et nom d'hôte du point de terminaison REST](https://developers.marketo.com/rest-api/authentication/)**.

1. Entrez votre **[ID de liste Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Sélectionnez **J'accepte** pour confirmer la **Confidentialité et conformité des données** et sélectionnez **Connecter** pour initialiser la connexion à Marketo.

1. Sélectionnez **Vous ajouter en tant qu'utilisateur à exporter** et fournissez vos informations d'identification Customer Insights.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Capture d'écran d'exportation pour la connexion à Marketo":::

1. Sélectionnez **Suivant** pour configurer l'exportation.

## <a name="configure-the-connector"></a>Configurer le connecteur

1. Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l'adresse e-mail d'un client. 

1. Vous pouvez éventuellement exporter les champs **Prénom**, **Nom**, **Ville**, **Département** et **Pays/Région** comme champs supplémentaires pour créer des e-mails plus personnalisés. Sélectionnez **Ajouter un attribut** pour mapper ces champs.

1. Sélectionnez les segments que vous souhaitez exporter. Vous pouvez exporter jusqu'à 1 million de profils clients au total vers Marketo.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Sélectionner les champs et les segments à exporter vers Marketo":::

1. Sélectionnez **Enregistrer**.

## <a name="export-the-data"></a>Exporter les données

Vous pouvez [exporter les données à la demande](export-destinations.md). L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab). Dans Marketo, vous trouverez désormais vos segments sous [Listes Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Limitations connues

- Jusqu'à 1 million de profils par exportation vers Marketo.
- L'exportation vers Marketo est limitée aux segments.
- L'exportation de segments avec un total de 1 million de profils peut prendre jusqu'à 3 heures. 
- Le nombre de profils que vous pouvez exporter vers Marketo dépend et est limité par votre contrat avec Marketo.

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Marketo, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Marketo respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d'informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d'exportation à tout moment pour interrompre l'utilisation de cette fonctionnalité.
