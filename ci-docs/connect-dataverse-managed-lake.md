---
title: Se connecter aux données dans un lac de données géré Microsoft Dataverse
description: Importer des données depuis un lac de données géré Microsoft Dataverse.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609792"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Se connecter aux données dans un lac de données géré Microsoft Dataverse

Les utilisateurs Microsoft Dataverse peuvent se connecter rapidement aux entités analytiques dans un lac géré Microsoft Dataverse. Une seule source de données d’un environnement peut utiliser simultanément le même lac géré Dataverse.

> [!NOTE]
> Vous devez être un administrateur dans l’organisation Dataverse pour continuer et afficher la liste des entités disponibles dans le lac géré.

## <a name="prerequisites"></a>Conditions préalables

- Les données stockées dans des services en ligne, tels que Azure Data Lake Storage, peut être stocké dans un emplacement différent de celui où les données sont traitées ou stockées dans Dynamics 365 Customer Insights. En important ou en vous connectant aux données stockées dans des services en ligne, vous acceptez que les données puissent être transférées dans Dynamics 365 Customer Insights et qu’elles y soient stockées. [En savoir plus sur le Centre de gestion de la confidentialité Microsoft](https://www.microsoft.com/trust-center).

- Seules les entités Dataverse avec le [suivi des modifications](/power-platform/admin/enable-change-tracking-control-data-synchronization) activé sont visibles. Ces entités peuvent être exportées vers le lac de données géré par Dataverse et utilisées dans Customer Insights. Les tables Dataverse prédéfinies ont le suivi des modifications activé par défaut. Vous devez activer le suivi des modifications pour les tables personnalisées. Pour vérifier si une table Dataverse est activée pour le suivi des modifications, accédez à [Power Apps](https://make.powerapps.com) > **Données** > **Tables**. Recherchez la table qui vous intéresse et sélectionnez-la. Accédez à **Paramètres** > **Options avancées** et vérifiez le paramètre **Suivi des modifications**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Se connecter à un lac géré Dataverse

1. Accédez à **Données** > **Sources de données**.

1. Sélectionnez **Ajouter une source de données**.

1. Sélectionnez **Microsoft Dataverse**.

1. Entrez le **nom** de la source de données et une **description** facultative.

1. Fournissez l’**adresse du serveur** pour l’organisation Dataverse et sélectionnez **Connexion**.

1. Sélectionnez dans la liste disponible les tables que vous souhaitez ingérer en tant qu’entités dans Customer Insights.

   > [!NOTE]
   > Si vous remarquez que certaines tables sont déjà sélectionnées, c’est probablement parce qu’elles sont utilisées par d’autres applications Dynamics 365 (telles que Dynamics 365 Sales Insights ou Customer Service Insights). Vous ne pouvez pas modifier la sélection. Ces tables seront disponibles comme entités une fois la source de données créée.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Boîte de dialogue affichant une liste d’entités dans l’environnement Dataverse.":::

1. Enregistrez votre sélection pour commencer à synchroniser les tables sélectionnées à partir de Dataverse. Vous trouverez la connexion récemment ajoutée sur la page **Sources de données**. Elle est mise dans la file d’attente pour actualisation et présente le nombre d’entités comme 0 jusqu’à la synchronisation de l’ensemble des tables.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Le chargement des données peut prendre du temps. Après une actualisation réussie, les données ingérées peuvent être consultées à partir de la page [**Entités**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Modifier une source de données du lac géré Dataverse

Vous ne modifiez la sélection d’entités qu’après avoir créé la source de données. Par exemple, si des entités supplémentaires ont été ajoutées à Dataverse et que vous souhaitez également les importer.
Pour se connecter à un autre lac de données Dataverse, [créez une source de données](#connect-to-a-dataverse-managed-lake).

1. Accédez à **Données** > **Sources de données**.

1. En regard de la source de données que vous souhaitez mettre à jour, sélectionnez **Modifier**.

1. Sélectionnez des entités supplémentaires dans la liste des entités.

1. Cliquez sur **Enregistrer** pour appliquer vos modifications et revenir à la page **Sources de données**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Raisons courantes aux erreurs d’ingestion ou aux données endommagées

Les vérifications suivantes s’exécutent sur les données ingérées pour exposer les enregistrements endommagés :

- La valeur d’un champ ne correspond pas au type de données de sa colonne.
- Les champs contiennent des caractères qui font que les colonnes ne correspondent pas au schéma attendu. Par exemple : guillemets mal formatés, guillemets sans échappement ou caractères de nouvelle ligne.
- S’il existe des colonnes datetime/date/datetimeoffset, leur format doit être spécifié dans le modèle s’il ne respecte pas le format ISO standard.

### <a name="schema-or-data-type-mismatch"></a>Le schéma ou le type de données ne correspondent pas

Si les données ne sont pas conformes au schéma, les enregistrements sont classés comme endommagés. Corrigez les données source ou le schéma et réingérez les données.

### <a name="datetime-fields-in-the-wrong-format"></a>Champs de date/heure au format incorrect

Les champs de date/heure de l’entité ne sont pas aux formats ISO ou en-US. Le format de date/heure par défaut dans Customer Insights est le format en-US. Tous les champs de date/heure d’une entité doivent être au même format. Customer Insights prend en charge d’autres formats à condition que des annotations ou des traits soient effectués au niveau de la source ou de l’entité dans le modèle ou le fichier manifest.json. Par exemple : 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  Dans un fichier manifest.json, le format de date/heure peut être spécifié au niveau de l’entité ou au niveau de l’attribut. Au niveau de l’entité, utilisez « exhibitsTraits » dans l’entité du fichier *.manifest.cdm.json pour définir le format de date/heure. Au niveau de l’attribut, utilisez « appliedTraits » dans l’attribut du fichier entityname.cdm.json.

**Manifest.json au niveau de l’entité**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json au niveau de l’attribut**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
