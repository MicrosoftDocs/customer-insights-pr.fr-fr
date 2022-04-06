---
title: Se connecter aux tables dans Microsoft Dataverse
description: Importer des données depuis un lac de données géré Microsoft Dataverse.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 81412ea8259e690eb839676d82ab31847854a97e
ms.sourcegitcommit: a8e99cf8b23ccc00d76c1dee22afd808a160a5c8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2022
ms.locfileid: "8464063"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Se connecter aux données dans un lac de données géré Microsoft Dataverse

Cet article fournit des informations sur la façon dont les utilisateurs Dataverse peuvent se connecter rapidement aux entités analytiques dans un lac géré par Microsoft Dataverse. 

> [!NOTE]
> Vous devez être un administrateur dans l’organisation Dataverse pour continuer et afficher la liste des entités disponibles dans le lac géré.

## <a name="important-considerations"></a>Remarques importantes

1. Les données stockées dans des services en ligne, tels que Azure Data Lake Storage, peut être stocké dans un emplacement différent de celui où les données sont traitées ou stockées dans Dynamics 365 Customer Insights. En important ou en vous connectant aux données stockées dans des services en ligne, vous acceptez que les données puissent être transférées dans Dynamics 365 Customer Insights et qu’elles y soient stockées. [En savoir plus sur le Centre de gestion de la confidentialité Microsoft](https://www.microsoft.com/trust-center).
2. Seules les entités Dataverse avec le [suivi des modifications](/power-platform/admin/enable-change-tracking-control-data-synchronization) activé sont visibles. Ces entités peuvent être exportées vers le lac de données géré par Dataverse et utilisées dans Customer Insights. Les tables Dataverse prédéfinies ont le suivi des modifications activé par défaut. Vous devez activer le suivi des modifications pour les tables personnalisées. Pour vérifier si une table Dataverse est activée pour le suivi des modifications, accédez à [Power Apps](https://make.powerapps.com) > **Données** > **Tables**. Recherchez la table qui vous intéresse et sélectionnez-la. Accédez à **Paramètres** > **Options avancées** et vérifiez le paramètre **Suivi des modifications**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Se connecter à un lac géré Dataverse

1. Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.

2. Sélectionnez **Ajouter une source de données**.

3. Sélectionnez **Microsoft Dataverse** et sélectionnez **Suivant**.

4. Saisissez un **Nom** pour la source de données, puis sélectionnez **Suivant**. 

5. Fournissez l’**adresse du serveur** pour l’organisation Dataverse et sélectionnez **Connexion**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Écran dans l’étape d’ingestion des données où un utilisateur peut saisir l’URL d’environnement Dataverse.":::

6. Sélectionnez les tables que vous souhaitez ingérer en tant qu’entités pour les informations sur l’audience dans la liste disponible.    

   > [!NOTE]
   > Si vous remarquez que certaines tables sont déjà sélectionnées, c’est probablement parce qu’elles sont utilisées par d’autres applications Dynamics 365 (telles que Dynamics 365 Sales Insights ou Customer Service Insights). Vous ne pouvez pas modifier la sélection. Ces tables seront disponibles comme entités une fois la source de données créée.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Boîte de dialogue affichant une liste d’entités dans l’environnement Dataverse.":::

7. Enregistrez votre sélection pour commencer à synchroniser les tables sélectionnées à partir de Dataverse. Vous trouverez la connexion récemment ajoutée sur la page **Sources de données**. Elle est mise dans la file d’attente pour actualisation et présente le nombre d’entités comme 0 jusqu’à la synchronisation de l’ensemble des tables.

Une seule source de données d’un environnement peut utiliser simultanément le même lac géré Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Modifier une source de données du lac géré Dataverse

Vous ne modifiez la sélection d’entités qu’après avoir créé la source de données. Par exemple, si des entités supplémentaires ont été ajoutées à Dataverse et que vous souhaitez également les importer.    
Pour se connecter à un autre lac de données Dataverse, [créez une source de données](#connect-to-a-dataverse-managed-lake).

1. Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.

2. En regard de la source de données que vous souhaitez mettre à jour, sélectionnez les points de suspension.

3. Sélectionnez l’option **Modifier** dans la liste.

4. Sélectionnez des entités supplémentaires dans la liste des entités disponibles et sélectionnez **Enregistrer**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
