---
title: Destinations d'export
description: Exportez des données et gérez les destinations d'exportation.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643860"
---
# <a name="export-destinations-preview"></a>Destinations d'export (aperçu)

La page **Destinations d'exportation** vous indique tous les emplacements que vous avez configurés afin d'y exporter des données. Vous pouvez également ajouter de nouvelles destinations pour l'exportation. De plus, elle affiche les options d'exportation actuellement disponibles. Obtenez un aperçu rapide, une description et découvrez ce que vous pouvez faire avec chaque option d'extensibilité. Exportez des profils, des mesures et des segments unifiés vers des applications prises en charge pertinentes pour votre entreprise.

Aller à **Administrateur** > **Exporter des destinations** pour rechercher les options d'extensibilité suivantes :

- [Complément de carte client Dynamics 365](customer-card-add-in.md)
- [Connecteur Facebook Ads Manager](export-facebook.md)
- [Power Automateconnecteur](export-power-automate.md)
- [Power Appsconnecteur](export-power-apps.md)
- [Power BIconnecteur](export-power-bi.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Stockage Blob Azure](export-azure-blob-storage.md)
- [Connecteur LiveRamp&reg;](export-liveramp.md)
- [Bot pour Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [API Customer Insights](apis.md)

## <a name="add-a-new-export-destination"></a>Ajouter une nouvelle destination d'exportation

Pour ajouter des destinations d'exportation, vous devez avoir des [autorisations administrateur](permissions.md). Si vous exportez vers des services Microsoft, nous supposons que les deux services appartiennent à la même organisation.

1. Accédez à **Administration** > **Destinations d'exportation**.

1. Passez à l'onglet **Mes destinations d'exportation**.

1. Sélectionnez **Ajouter une destination** pour créer une destination d'exportation.

1. Dans le volet **Ajouter une destination**, sélectionnez le **Type** de destination d'exportation dans le menu déroulant.

1. Fournissez les détails requis et sélectionnez **Suivant** pour créer la destination d'exportation.

Vous pouvez également sélectionner **Configurer** sur une vignette sur l'onglet **Découvrir**.

## <a name="view-export-destinations"></a>Afficher les destinations d'exportation

Après avoir créé des destinations d'exportation, vous les trouverez dans un tableau sur l'onglet **Mes destinations d'exportation**. Ce tableau comporte trois colonnes :

- **Nom complet** : le nom que vous avez entré lors de la création de la destination.
- **Type** : Le type de destination d'exportation défini lors de la création de la destination.
- **Créée** : la date à laquelle vous avez créé la destination.

## <a name="edit-an-export-destination"></a>Modifier une destination d'exportation

1. Sélectionnez les points de suspension pour la destination d'exportation que vous souhaitez modifier.

   > [!div class="mx-imgBorder"]
   > ![Ellipses verticales](media/export-destinations-page-ellipsis.png "Ellipses verticales")

1. Sélectionnez **Modifier** dans le menu déroulant.

1. Modifiez les valeurs qui nécessitent une mise à jour et sélectionnez **Enregistrer**.

## <a name="export-data-on-demand"></a>Exporter les données à la demande

Après avoir configuré un connecteur pour une destination d'exportation, les exportations s'exécutent avec chaque [actualisation programmée](system.md#schedule-tab).

Pour exporter des données sans attendre une actualisation planifiée, accédez à l'onglet **Mes destinations d'exportation** sur **Administration** > **Exporter des destinations**.

> [!div class="mx-imgBorder"]
> ![Ellipses verticales](media/export-destinations-page-ellipsis.png "Ellipses verticales")

- Sélectionnez **Exporter** au-dessus de la liste pour exécuter l'exportation vers toutes les destinations d'exportation simultanément.
- Sélectionnez les points de suspension (…) après un élément de liste, puis choisissez **Exporter** pour exécuter l'exportation pour une seule destination d'exportation.

## <a name="remove-an-export-destination"></a>Supprimer une destination d'exportation

Pour supprimer une destination d'exportation, commencez par la page principale **Destinations d'exportation**.

1. Sélectionnez les points de suspension pour la destination d'exportation que vous souhaitez supprimer.

   > [!div class="mx-imgBorder"]
   > ![Ellipses verticales](media/export-destinations-page-ellipsis.png "Ellipses verticales")

2. Sélectionnez **Supprimer** dans la liste déroulante.

3. Confirmez la suppression en sélectionnant **Supprimer** sur l'écran de confirmation.
