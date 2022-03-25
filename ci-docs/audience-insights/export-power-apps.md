---
title: Connecteur Power Apps
description: Connectez-vous à Power Apps et Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 18cc32a169e79794d2d3203d462620ab41efaafe
ms.sourcegitcommit: d168a738a08adb8b4b2e410bdaa3716d7b63cc9b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455949"
---
# <a name="microsoft-power-apps-connector-preview"></a>Connecteur Microsoft Power Apps (préversion)

Importez des profils client unifiés dans vos applications personnalisées avec Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Connectez-vous à Power Apps et à Dynamics 365 Customer Insights

Customer Insights est l’une des nombreuses [sources disponibles pour les données dans Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Consultez la documentation de Power Apps pour savoir comment [ajouter une connexion de données à une application](/powerapps/maker/canvas-apps/add-data-connection). Nous vous recommandons de consulter également l’article [Comment Power Apps utilise la délégation pour gérer de grands ensembles de données dans les applications canevas](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entités disponibles

Après avoir ajouté Customer Insights en tant que connexion de données, vous pouvez choisir les entités suivantes dans Power Apps :

- **Client** : pour utiliser les données du [profil client unifié](customer-profiles.md).
- **UnifiedActivity** : pour afficher la [chronologie des activités](activities.md) dans l’application.
- **ContactProfile** : pour afficher les contacts d’un client. Cette entité n’est disponible qu’avec les environnements d’informations sur l’audience pour les comptes professionnels.

## <a name="limitations"></a>Limitations

### <a name="retrievable-entities"></a>Entités récupérables

Vous ne pouvez récupérer que les entités **Client**, **UnifiedActivity**, **Segments** et **ContactProfile** grâce au connecteur Power Apps. ContactProfile n’est disponible qu’avec l’instance d’informations sur l’audience pour les comptes professionnels. D’autres entités sont affichées, car le connecteur sous-jacent les prend en charge par le biais des déclencheurs dans Power Automate.

Vous pouvez passer au maximum 100 appels par minute. Vous pouvez appeler le point de terminaison d’API plusieurs fois en utilisant le paramètre $skip. [En savoir plus sur le paramètre $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Délégation

La délégation fonctionne pour l’entité **Client** et l’entité **UnifiedActivity**. 

- Délégation pour l’entité **Client** : pour utiliser la délégation pour cette entité, les champs doivent être indexés dans [Index Rechercher et filtrer](search-filter-index.md).  
- Délégation pour **UnifiedActivity** : La délégation pour cette entité ne fonctionne que pour les champs **ActivityId** et **N° de client**.  
- Délégation pour **ContactProfile** : La délégation pour cette entité ne fonctionne que pour les champs **ContactId** et **CustomerId**. ContactProfile n’est disponible que dans les environnements d’informations sur l’audience pour les comptes professionnels.

Pour plus d’informations sur la délégation, accédez aux [opérations et fonctions délégables de Power Apps](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Exemple de contrôle de galerie

Vous pouvez ajouter des profils clients à un [contrôle de galerie](/powerapps/maker/canvas-apps/add-gallery).

1. Ajoutez un contrôle de **galerie** à une application que vous créez.

    > [!div class="mx-imgBorder"]
    > ![Ajoutez un élément de galerie.](media/connector-powerapps9.png "Ajoutez un élément de galerie.")

2. Sélectionnez **Client** comme source de données pour les éléments.

    > [!div class="mx-imgBorder"]
    > ![Sélectionnez une source de données.](media/choose-datasource-powerapps.png "Sélectionnez une source de données.")

3. Vous pouvez modifier le volet de données sur la droite pour sélectionner le champ de l’entité Client à afficher dans la galerie.

4. Si vous souhaitez afficher n’importe quel champ du client sélectionné dans la galerie, renseignez la propriété **Text** d’une étiquette en utilisant **{Name_of_the_gallery}.Selected.{property_name}**  
    - Exemple : _Gallery1.Selected.address1_city_

5. Pour afficher la chronologie unifiée pour un client, ajoutez un élément de galerie et ajoutez la propriété **Items** en utilisant **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Exemple : _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE[footer-include](../includes/footer-banner.md)]
