---
title: Actualisation incrémentielle pour les sources de données Power Query et Azure Data Lake
description: Actualisez les données nouvelles et mises à jour pour les grandes sources de données en fonction des sources de données Power Query ou Azure Data Lake.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207134"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Actualisation incrémentielle pour les sources de données Power Query et Azure Data Lake

L’actualisation incrémentielle des sources de données dans Power Query ou Azure Data Lake fournit les avantages suivants :

- **Actualisations plus rapides** - Seules les données modifiées ont été actualisées. Par exemple, vous pouvez actualiser uniquement les cinq derniers jours d’un historique jeu de données.
- **Fiabilité accrue** - Avec des actualisations plus petites, vous n’avez pas besoin de maintenir les connexions aux systèmes sources volatils aussi longtemps, ce qui réduit le risque de problèmes de connexion.
- **Réduction de la consommation de ressources** - Actualiser uniquement un sous-ensemble de vos données totales permet une utilisation plus efficace des ressources informatiques et diminue l’empreinte environnementale.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Configurer l'actualisation incrémentielle de sources de données basées sur Power Query

Customer Insights permet l’actualisation incrémentielle des sources de données importées via Power Query qui prennent en charge l’ingestion incrémentielle. Par exemple, des bases de données SQL Azure avec des champs de date et d’heure, qui indiquent quand les enregistrements de données ont été mis à jour pour la dernière fois.

1. [Créer une source de données basée sur Power Query](connect-power-query.md).

1. Sélectionnez une source de données qui prend en charge l’actualisation incrémentielle, telle qu’une [base de données Azure SQL](/power-query/connectors/azuresqldatabase).

1. Sélectionnez les entités ou les tables à ingérer.

1. Terminez les étapes de transformation et sélectionnez **Suivant**.

1. Dans la boîte de dialogue **Configurer une actualisation incrémentielle**, sélectionnez **Configurer** pour ouvrir **Paramètres d’actualisation incrémentielle**. Si vous sélectionnez **Ignorer**, la source de données actualisera l’intégralité du jeu de données.
   > [!TIP]
   > Vous pouvez également appliquer une actualisation incrémentielle ultérieurement en modifiant une source de données existante.

1. Sur **Paramètres d’actualisation incrémentielle**, vous allez configurer l’actualisation incrémentielle pour toutes les entités que vous avez sélectionnées lors de la création de la source de données.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Configurer les paramètres d’actualisation incrémentielle.":::

1. Sélectionnez une entité et fournissez les détails suivants :

   - **Définir la clé primaire** : Sélectionnez une clé primaire pour l’entité ou la table.
   - **Définir le champ « dernière mise à jour »**  : Ce champ n’affichera que les attributs de type date ou heure. Sélectionnez un attribut qui indique la dernière mise à jour des enregistrements. Il sera utilisé pour identifier les enregistrements faisant partie de la fenêtre temporelle de l’actualisation incrémentielle.
   - **Rechercher des mises à jour toutes les** : Spécifiez la durée du délai d’exécution de l’actualisation incrémentielle.

1. Sélectionnez **Enregistrer** pour terminer la création de la source de données. L’actualisation initiale des données sera une actualisation complète. Ensuite, l’actualisation incrémentielle des données se produit comme configuré à l’étape précédente.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Configurer l'actualisation incrémentielle pour les sources de données Azure Data Lake

Customer Insights permet une actualisation incrémentielle des sources de données connectées à Azure Data Lake Storage. Pour utiliser l'ingestion et l'actualisation incrémentielles pour une entité, configurez cette entité lors de l'ajout de la source de données Azure Data Lake ou ultérieurement lors de la modification de la source de données. Le dossier de données d'entité doit contenir les dossiers suivants :

- **FullData** : Dossier avec les fichiers de données contenant les enregistrements initiaux
- **IncrementalData** : Dossier avec des dossiers de hiérarchie date/heure au format **aaaa/mm/jj/hh** contenant les mises à jour incrémentielles. **hh** représente l'heure UTC des mises à jour et contient les dossiers **Upserts** et **Deletes**. **Upserts** contient des fichiers de données avec des mises à jour d'enregistrements existants ou de nouveaux enregistrements. **Deletes** contient des fichiers de données avec des enregistrements à supprimer.

1. Lors de l'ajout ou de la modification d'une source de données, accédez au volet **Attributs** de l'entité.

1. Examinez les attributs. Assurez-vous qu'un attribut de date de création ou de dernière mise à jour est configuré avec *dateTime* pour le **format de date** et *Calendar.Date* pour le **type de sémantique**. Modifiez l'attribut si nécessaire, puis sélectionnez **Terminé**.

1. Dans le volet **Sélectionner les entités**, modifiez l'entité. La case **Ingestion incrémentielle** est cochée.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Configurez des entités dans une source de données pour une actualisation incrémentielle.":::

   1. Accédez au dossier racine qui contient les fichiers .csv ou .parquet pour les données complètes, les mises à jour de données incrémentielles et les suppressions de données incrémentielles.
   1. Entrez l'extension pour les données complètes et les deux fichiers incrémentiels (\.csv or \.parquet).
   1. Pour les fichiers .csv, sélectionnez le délimiteur de colonne et si vous voulez la première ligne du fichier comme en-tête de colonne.
   1. Cliquez sur **Enregistrer**.

1. Pour **Dernière mise à jour**, sélectionnez l'attribut d'horodatage de date.

1. Si la **Clé primaire** n'est pas sélectionnée, sélectionnez-la. La clé primaire est un attribut unique à l’entité. Pour qu’un attribut soit une clé primaire valide, il ne doit inclure aucune valeur en double, aucune valeur manquante, ni aucune valeur nulle. Les attributs de type de données chaîne, entier et GUID sont pris en charge en tant que clés primaires.

1. Sélectionnez **Fermer**, puis enregistrez et fermez le volet.

1. Continuez en ajoutant ou en modifiant la source de données.

[!INCLUDE [footer-include](includes/footer-banner.md)]
