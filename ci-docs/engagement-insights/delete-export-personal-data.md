---
title: Supprimer et exporter des informations personnelles
description: Comment supprimer et exporter des données liées aux événements contenant des données personnelles.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 8edefe25261eaf8939dade3fdddab3d87df4ed5079fa566426319cd7b32e1638
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034084"
---
# <a name="delete-and-export-event-data-containing-personal-information"></a>Supprimer et exporter des données liées aux événements contenant des informations personnelles

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="background"></a>Arrière-plan

Le règlement général sur la protection des données (RGPD) de l'Union européenne est en vigueur depuis le 25 mai 2018. Il donne des droits importants aux individus sur leurs données. Le RGPD repose sur la protection et l'application des droits à la vie privée des personnes. Vous pouvez en savoir plus sur l’engagement de Microsoft en matière de sécurité et de conformité dans le [Microsoft Trust Center](https://www.microsoft.com/trust-center).

## <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Suppression et exportation de données liées aux événements contenant des informations identifiables par l'utilisateur final

Les sections suivantes décrivent comment supprimer et exporter des données liées aux événements susceptibles de contenir des données personnelles.

### <a name="overview"></a>Présentation

La fonction Informations sur l’engagement Dynamics 365 Customer Insights s’engage à aider nos clients à répondre à leurs exigences RGPD. Cela comprend le droit de supprimer et d'exporter des données qui incluent des informations personnelles telles que les identifiants d'utilisateur, les numéros de téléphone et les adresses e-mail. Les administrateurs peuvent implémenter les demandes des utilisateurs pour supprimer ou exporter des données personnelles.

Pour supprimer ou exporter des données :

1. Marquez les propriétés d'événement qui contiennent des données avec des informations personnelles.
2. Supprimez ou exportez les données associées à des valeurs spécifiques (par exemple : un ID utilisateur spécifié).

### <a name="tag-and-update-event-properties"></a>Marquer et mettre à jour les propriétés des événements

Les données personnelles sont marquées au niveau de la propriété d'événement. Commencez par marquer les propriétés à supprimer ou exporter.

Pour marquer une propriété d'événement comme contenant des informations personnelles, procédez comme suit :

1. Ouvrez l'espace de travail contenant l'événement.

1. Allez dans **Données** > **Événements** pour voir la liste des événements dans l'espace de travail sélectionné.
  
1. Sélectionnez l'environnement à marquer.

1. Sélectionnez **Modifier les propriétés** pour ouvrir le volet répertoriant toutes les propriétés de l'événement sélectionné.
     
1. Sélectionnez **...** puis choisissez **Modifier** pour accéder à la boîte de dialogue **Mettre à jour la propriété**.

   ![Modifier l’événement.](media/edit-event.png "Modifier l’événement")

1. Dans la fenêtre **Mettre à jour la propriété**, choisissez **...** dans le coin supérieur droit, puis choisissez la zone **Contient EUII**. Choisissez **Mettre à jour** pour enregistrer vos modifications.

   ![Enregistrez vos modifications.](media/update-property.png "Enregistrer vos modifications")

   > [!NOTE]
   > Chaque fois que le schéma d'événement change ou que vous créez un événement, il est recommandé d'évaluer les propriétés d'événement associées et de les marquer ou de les décocher comme contenant des données personnelles, si nécessaire.

### <a name="delete-or-export-tagged-event-data"></a>Supprimer ou exporter des données d'événement marquées

Si toutes les propriétés d'événement ont été correctement marquées comme décrit à l'étape précédente, un administrateur d'environnement peut émettre une demande de suppression sur les données d'événement marquées.

Pour gérer les demandes de suppression ou d'exportation EUII

1. Allez dans **Administrateur** > **Environnement** > **Paramètres**.

1. Dans la section **Gérer les informations identifiables de l'utilisateur final (EUII)**, sélectionnez **Gérer EUII**.

#### <a name="deletion"></a>Suppression

Pour la suppression, vous pouvez saisir une liste d'ID utilisateur séparés par des virgules dans la section **Supprimer les informations d'identification de l'utilisateur final (EUII)**. Ces ID seront ensuite comparés à toutes les propriétés d'événement marquées de tous les projets de l'environnement actuel via une correspondance de chaîne exacte. 

Si une valeur de propriété correspond à l'un des ID fournis, l'événement associé sera définitivement supprimé. En raison de l'irréversibilité de cette action, vous devez confirmer la suppression après avoir sélectionné **Supprimer**.

#### <a name="export"></a>Export

Le processus d'exportation est identique au processus de suppression lorsqu'il s'agit de définir les valeurs de propriété d'événement dans la section **Exporter les informations d'identification de l'utilisateur final (EUII)**. De plus, vous devrez fournir une **URL de stockage d'objets blob Azure** pour spécifier la destination d'exportation. L'URL de l'objet blob Azure doit inclure une [Signature d'accès partagé (SAS)](/azure/storage/common/storage-sas-overview).

Après avoir sélectionné **Exporter**, tous les événements de l'équipe actuelle contenant des propriétés marquées correspondantes seront exportés au format CSV vers la destination d'exportation.

#### <a name="good-practices"></a>Meilleures pratiques

* Essayez d'éviter d'envoyer des événements contenant des données personnelles.
* Si vous devez envoyer des événements contenant des données EUII, limitez le nombre d'événements et de propriétés d'événement contenant des données EUII. Idéalement, limitez-vous à un de ces événements.
* Assurez-vous que le moins de personnes possible aient accès aux données personnelles envoyées.
* Pour les événements contenant des données personnelles, assurez-vous de définir une propriété pour émettre un identifiant unique qui peut facilement être lié à un utilisateur spécifique (par exemple, un ID utilisateur). Cela facilite la séparation des données et l'exportation ou la suppression des bonnes données.
* Marquez une seule propriété par événement comme contenant des données personnelles. Idéalement, celle qui ne contient qu'un identifiant unique.
* Ne marquez pas les propriétés contenant des valeurs détaillées (par exemple, un corps de requête entier). La fonction Informations sur l’engagement utilise la correspondance exacte des chaînes lors du choix des événements à supprimer ou à exporter.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
