---
title: Actualisation incrémentielle des sources de données basées sur Power Query
description: Actualisez les données nouvelles et mises à jour pour les sources de données volumineuses basées sur Power Query.
ms.date: 09/28/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 1af2e4c42dc5890556c90bb3e5ef1aeb0621fda0
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554156"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Actualisation incrémentielle pour les sources de données basées sur Power Query

L’actualisation incrémentielle des sources de données offre les avantages suivants :

- **Actualisations plus rapides** - Seules les données modifiées ont été actualisées. Par exemple, vous pouvez actualiser uniquement les cinq derniers jours d’un historique jeu de données.
- **Fiabilité accrue** - Avec des actualisations plus petites, vous n’avez pas besoin de maintenir les connexions aux systèmes sources volatils aussi longtemps, ce qui réduit le risque de problèmes de connexion.
- **Réduction de la consommation de ressources** - Actualiser uniquement un sous-ensemble de vos données totales permet une utilisation plus efficace des ressources informatiques et diminue l’empreinte environnementale.

## <a name="configure-incremental-refresh"></a>Configurer l’actualisation incrémentielle

Les informations sur l’audience permettent une actualisation incrémentielle des sources de données importées via Power Query qui prennent en charge l’ingestion incrémentielle. Par exemple, des bases de données SQL Azure avec des champs de date et d’heure, qui indiquent quand les enregistrements de données ont été mis à jour pour la dernière fois.

1. [Créer une source de données basée sur Power Query](connect-power-query.md).

1. Offrez un nom pour la source de données.

1. Sélectionnez une source de données qui prend en charge l’actualisation incrémentielle, telle qu’une base de données Azure SQL.

1. Sélectionnez les entités ou les tables à ingérer.

1. Terminez les étapes de transformation et sélectionnez **Suivant**.

1. Dans la boîte de dialogue **Configurer une actualisation incrémentielle**, sélectionnez **Configurer** pour ouvrir **Paramètres d’actualisation incrémentielle**. Si vous sélectionnez **Ignorer**, la source de données actualisera l’intégralité du jeu de données.
   > [!TIP]
   > Vous pouvez également appliquer une actualisation incrémentielle ultérieurement en modifiant une source de données existante.

1. Sur **Paramètres d’actualisation incrémentielle**, vous allez configurer l’actualisation incrémentielle pour toutes les entités que vous avez sélectionnées lors de la création de la source de données.

   > [!div class="mx-imgBorder"]
   > ![Configurez des entités dans une source de données pour une actualisation incrémentielle.](media/incremental-refresh-settings.png "Configurer des entités dans une source de données pour une actualisation incrémentielle")

1. Sélectionnez une entité et fournissez les détails suivants :

   - **Définir la clé primaire** : Sélectionnez une clé primaire pour l’entité ou la table.
   - **Définir le champ « dernière mise à jour »**  : Ce champ n’affichera que les attributs de type date ou heure. Sélectionnez un attribut qui indique la dernière mise à jour des enregistrements. Il sera utilisé pour identifier les enregistrements faisant partie de la fenêtre temporelle de l’actualisation incrémentielle.
   - **Rechercher des mises à jour toutes les** : Spécifiez la durée du délai d’exécution de l’actualisation incrémentielle.

1. Sélectionnez **Enregistrer** pour terminer la création de la source de données. L’actualisation initiale des données sera une actualisation complète. Ensuite, l’actualisation incrémentielle des données se produit comme configuré à l’étape précédente.


[!INCLUDE[footer-include](../includes/footer-banner.md)]