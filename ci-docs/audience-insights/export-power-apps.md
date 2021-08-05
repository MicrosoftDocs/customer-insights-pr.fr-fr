---
title: Connecteur Power Apps
description: Connectez-vous à Power Apps et Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 2ab5a9059991611a2959a19cc688d232ec782e1e
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554110"
---
# <a name="microsoft-power-apps-connector-preview"></a>Connecteur Microsoft Power Apps (préversion)

Importez des profils client unifiés dans vos applications personnalisées avec Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Connectez-vous à Power Apps et à Dynamics 365 Customer Insights

Customer Insights est l’une des nombreuses [sources disponibles pour les données dans Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Consultez la documentation de Power Apps pour savoir comment [ajouter une connexion de données à une application](/powerapps/maker/canvas-apps/add-data-connection). Nous vous recommandons de consulter également l’article [Comment Power Apps utilise la délégation pour gérer de grands ensembles de données dans les applications canevas](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entités disponibles

Après avoir ajouté Customer Insights en tant que connexion de données, vous pouvez choisir les entités suivantes dans Power Apps :

- Client : pour utiliser les données du [profil client unifié](customer-profiles.md).
- UnifiedActivity : pour afficher la [chronologie des activités](activities.md) sur l’application.

## <a name="limitations"></a>Limitations

### <a name="retrievable-entities"></a>Entités récupérables

Vous ne pouvez récupérer que les entités **Client**, **UnifiedActivity**, et **Segments** à l’aide du connecteur Power Apps. D’autres entités sont affichées, car le connecteur sous-jacent les prend en charge par le biais des déclencheurs dans Power Automate.  

### <a name="delegation"></a>Délégation

La délégation fonctionne pour l’entité Client et l’entité UnifiedActivity. 

- Délégation pour l’entité **Client** : pour utiliser la délégation pour cette entité, les champs doivent être indexés dans [Index Rechercher et filtrer](search-filter-index.md).  

- Délégation pour **UnifiedActivity** : La délégation pour cette entité ne fonctionne que pour les champs **ActivityId** et **N° de client**.  

- Pour plus d’informations sur la délégation, voir [Fonctions et opérations délégables Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Exemple de contrôle de galerie

Par exemple, vous ajoutez des profils clients à un [contrôle de galerie](/powerapps/maker/canvas-apps/add-gallery).

1. Ajoutez un contrôle **Galerie** à une application que vous créez.

> [!div class="mx-imgBorder"]
> ![Ajoutez un élément de galerie.](media/connector-powerapps9.png "Ajouter un élément de galerie")

1. Sélectionnez **Client** comme source de données pour les éléments.

    > [!div class="mx-imgBorder"]
    > ![Sélectionnez une source de données.](media/choose-datasource-powerapps.png "Sélectionner une source de données")

1. Vous pouvez modifier le volet de données sur la droite pour sélectionner le champ de l’entité Client à afficher dans la galerie.

1. Si vous souhaitez afficher n’importe quel champ du client sélectionné dans la galerie, renseignez la propriété de texte d’une étiquette : **{Name_of_the_gallery}.Selected.{property_name}**

    Exemple : Gallery1.Selected.addresse1_ville

1. Pour afficher la chronologie unifiée pour un client, ajouter un élément de galerie et ajouter la propriété Éléments : **Filter(’UnifiedActivity’, CustomerId = {Customer_Id})**

    Exemple : Filter(’UnifiedActivity’, CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]