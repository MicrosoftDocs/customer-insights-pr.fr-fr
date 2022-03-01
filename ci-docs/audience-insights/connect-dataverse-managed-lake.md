---
title: Se connecter aux tables dans Microsoft Dataverse
description: Importer des données depuis un lac de données géré Microsoft Dataverse.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: f92d64723e6a4d2fcebdbb3758519d4bfd4aeaf4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692571"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Se connecter aux données dans un lac de données géré Microsoft Dataverse

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Cet article fournit des informations sur la façon dont les utilisateurs Dataverse peuvent se connecter rapidement à leurs entités analytiques dans un lac géré Dataverse. Vous devez être administrateur de l’organisation Dataverse pour continuer et voir la liste des entités disponibles dans le lac géré.

## <a name="important-considerations"></a>Remarques importantes

Les données stockées dans des services en ligne, tels que Azure Data Lake Storage, peut être stocké dans un emplacement différent de celui où les données sont traitées ou stockées dans Dynamics 365 Customer Insights. En important ou en vous connectant aux données stockées dans les services en ligne, vous acceptez que les données puissent être transférées et stockées avec Dynamics 365 Customer Insights. [En savoir plus sur le Centre de gestion de la confidentialité Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Se connecter à un lac géré Dataverse

1. Dans les informations sur l’audience, accédez à **Données** > **Sources de données**.

2. Sélectionnez **Ajouter une source de données**.

3. Sélectionnez **Se connecter au lac géré Microsoft Dataverse** et sélectionnez **Suivant**.

4. Saisissez un **Nom** pour la source de données, puis sélectionnez **Suivant**. Instructions relatives au nom : 
   - Commencez par une lettre.
   - Utilisez uniquement des lettres et des chiffres. Les espaces et caractères spéciaux ne sont pas autorisés.
   - Utilisez entre 3 et 64 caractères.

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