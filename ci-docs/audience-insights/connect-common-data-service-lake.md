---
title: Se connecter aux entités dans le lac géré Common Data Service
description: Importer des données depuis un lac de données géré Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643395"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Se connecter aux données dans un lac de données géré Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Cet article fournit des informations sur la façon dont les clients Dynamics 365 existants peuvent se connecter rapidement à leurs entités analytiques dans le lac géré Common Data Service. Vous devez être administrateur de l'organisation Common Data Service pour continuer et voir la liste des entités disponibles dans le lac géré.

## <a name="important-considerations"></a>Remarques importantes

Les données stockées dans des services en ligne, tels que Azure Data Lake Storage, peut être stocké dans un emplacement différent de celui où les données sont traitées ou stockées dans Dynamics 365 Customer Insights. En important ou en vous connectant aux données stockées dans les services en ligne, vous acceptez que les données puissent être transférées et stockées avec Dynamics 365 Customer Insights. [En savoir plus sur le Centre de gestion de la confidentialité Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Se connecter à un lac géré Common Data Service

1. Dans Audience Insights, accédez à **Données** > **Sources de données**.

2. Sélectionnez **Ajouter une source de données**.

3. Sélectionnez **Se connecter à Common Data Service** et sélectionnez **Suivant**.

4. Saisissez un **Nom** pour la source de données, puis sélectionnez **Suivant**.

5. Renseignez le champ **Adresse du serveur** pour votre organisation Common Data Service et sélectionnez **Se connecter**.

   > [!div class="mx-imgBorder"]
   > ![Boîte de dialogue pour saisir l'adresse de serveur Common Data Service](media/enter-CDS-org-details.png)

6. Sélectionnez les entités que vous souhaitez ingérer dans la liste disponible.    

   > [!NOTE]
   > Si certaines entités sont déjà sélectionnées, elles peuvent être utilisées par d'autres applications Dynamics 365 (telles que Dynamics 365 Sales Insights ou Customer Service Insights). Vous ne pouvez pas modifier la sélection. Ces entités seront disponibles une fois la source de données créée.

   > [!div class="mx-imgBorder"]
   > ![Boîte de dialogue affichant une liste d'entités dans l'organisation Common Data Service](media/select-analytical-entities.png)

7. Enregistrez votre sélection pour commencer à synchroniser les entités sélectionnées avec le lac géré Common Data Service. Vous trouverez la connexion récemment ajoutée sur la page **Sources de données**. Elles sera mise en file d'attente pour actualisation et affichera les entités comme 0 jusqu'à ce que toutes les entités soient synchronisées.

Une seule source de données d'un environnement peut utiliser simultanément le même lac géré Common Data Service.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Modifier une source de données du lac géré Common Data Service

Vous ne modifiez la sélection d'entités qu'après avoir créé la source de données. Par exemple, si des entités supplémentaires ont été ajoutées à Common Data Service et que vous souhaitez également les importer.    
Pour vous connecter à un autre Common Data Service, [créer une source de données](#connect-to-a-common-data-service-managed-lake).

1. Dans Audience Insights, accédez à **Données** > **Sources de données**.

2. En regard de la source de données que vous souhaitez mettre à jour, sélectionnez les points de suspension.

3. Sélectionnez l'option **Modifier** dans la liste.

4. Sélectionnez des entités supplémentaires dans la liste des entités disponibles et sélectionnez **Enregistrer**.
