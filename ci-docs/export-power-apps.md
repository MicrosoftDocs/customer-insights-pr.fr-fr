---
title: Connecteur Power Apps (préversion)
description: Connectez-vous à Power Apps et Power Automate.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 8807e82e65ea20d1a7f7dc07552229f377927eed
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196897"
---
# <a name="power-apps-connector-preview"></a>Connecteur Power Apps (préversion)

Importez des profils client unifiés dans vos applications personnalisées avec Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Connectez-vous à Power Apps et à Dynamics 365 Customer Insights

Customer Insights est l’une des nombreuses [sources disponibles pour les données dans Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Consultez la documentation de Power Apps pour savoir comment [ajouter une connexion de données à une application](/powerapps/maker/canvas-apps/add-data-connection). Nous vous recommandons de consulter également l’article [Comment Power Apps utilise la délégation pour gérer de grands ensembles de données dans les applications canevas](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entités disponibles

Après avoir ajouté Customer Insights en tant que connexion de données, Choisissez les entités suivantes dans Power Apps :

- **Client** : pour utiliser les données du [profil client unifié](customer-profiles.md).
- **UnifiedActivity** : pour afficher la [chronologie des activités](activities.md) dans l’application.
- **ContactProfile** : pour afficher les contacts d’un client. Cette entité n’est disponible que dans les environnements Customer Insights pour les comptes professionnels.

## <a name="limitations"></a>Limitations

### <a name="retrievable-entities"></a>Entités récupérables

Vous ne pouvez récupérer que les entités **Client**, **UnifiedActivity**, **Segments** et **ContactProfile** grâce au connecteur Power Apps. ContactProfile n’est disponible que dans les environnements Customer Insights pour les comptes professionnels. D’autres entités sont affichées, car le connecteur sous-jacent les prend en charge par le biais des déclencheurs dans Power Automate.

Vous pouvez passer au maximum 100 appels par minute. Vous pouvez appeler le point de terminaison d’API plusieurs fois en utilisant le paramètre $skip. [En savoir plus sur le paramètre $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Délégation

La délégation fonctionne pour l’entité **Client** et l’entité **UnifiedActivity**.

- Délégation pour l’entité **Client** : pour utiliser la délégation pour cette entité, les champs doivent être indexés dans [Index Rechercher et filtrer](search-filter-index.md).  
- Délégation pour **UnifiedActivity** : La délégation pour cette entité ne fonctionne que pour les champs **ActivityId** et **N° de client**.  
- Délégation pour **ContactProfile** : La délégation pour cette entité ne fonctionne que pour les champs **ContactId** et **CustomerId**. ContactProfile n’est disponible que dans les environnements Customer Insights pour les comptes professionnels.

Pour plus d’informations sur la délégation, accédez aux [opérations et fonctions délégables de Power Apps](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="example-gallery-control"></a>Exemple de contrôle de galerie

Si nécessaire, vous pouvez ajouter des profils clients à un [contrôle de galerie](/powerapps/maker/canvas-apps/add-gallery).

1. Ajoutez un contrôle de **galerie** à une application que vous créez.
  
   :::image type="content" source="media/connector-powerapps9.png" alt-text="Ajoutez un élément de galerie.":::

1. Sélectionnez **Client** comme source de données pour les éléments.

   :::image type="content" source="media/choose-datasource-powerapps.png" alt-text="Sélectionnez une source de données.":::

1. Modifiez le volet de données sur la droite pour sélectionner le champ de l’entité Client à afficher dans la galerie.

1. Si vous souhaitez afficher n’importe quel champ du client sélectionné dans la galerie, renseignez la propriété **Text** d’une étiquette en utilisant **{Name_of_the_gallery}.Selected.{property_name}**  
    - Exemple : _Gallery1.Selected.address1_city_

1. Pour afficher la chronologie unifiée pour un client, ajoutez un élément de galerie et ajoutez la propriété **Items** en utilisant **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Exemple : _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_

[!INCLUDE [footer-include](includes/footer-banner.md)]
