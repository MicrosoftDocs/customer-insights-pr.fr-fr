---
title: Enrichissement avec l’importation personnalisée SFTP
description: Informations générales sur l’enrichissement avec l’importation personnalisée SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269603"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Enrichir les profils clients avec des données personnalisées (version préliminaire)

L’importation personnalisée SFTP (Secure File Transfer Protocol) vous permet d’importer des données qui ne doivent pas passer par le processus d’unification des données. C’est un moyen flexible, sécurisé et facile d’importer vos données. L’importation personnalisée SFTP peut être utilisée en combinaison avec l’[exportation SFTP](export-sftp.md) qui vous permet d’exporter les données de profil client nécessaires à l’enrichissement. Les données peuvent ensuite être traitées, enrichies et l’importation personnalisée SFTP peut être utilisée pour réimporter les données enrichies dans la fonctionnalité d’informations sur l’audience de Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Conditions préalables

Pour configurer l’importation personnalisée SFTP, les conditions préalables suivantes doivent être remplies :

- Vous disposez des informations d’identification utilisateur (nom d’utilisateur et mot de passe) de l’emplacement SFTP à partir duquel les données vont être importées.
- Vous disposez de l’URL et du numéro de port (généralement 22) de l’hôte STFP.
- Vous disposez du nom et de l’emplacement du fichier à importer sur l’hôte SFTP.
- Un fichier *model.json* spécifie le schéma des données à importer. Ce fichier doit se trouver dans le même répertoire que le fichier à importer.
- Vous disposez d’autorisations [Administrateur](permissions.md#administrator).

## <a name="configuration"></a>configuration

1. Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.

1. Sur la **vignette d’importation personnalisée SFTP**, sélectionnez **Enrichir mes données**.

   > [!div class="mx-imgBorder"]
   > ![Vignette d’importation personnalisée SFTP](media/SFTP_Custom_Import_tile.png "Vignette d’importation personnalisée SFTP")

1. Sélectionnez **Démarrer** et fournissez les informations d’identification et l’adresse du serveur SFTP. Par exemple, sftp://mysftpserver.com:22.

1. Entrez le nom du fichier contenant les données et le chemin d’accès au fichier sur le serveur SFTP s’il ne se trouve pas dans le dossier racine.

1. Confirmez toutes les entrées en sélectionnant **Se connecter à l’importation personnalisée**.

   > [!div class="mx-imgBorder"]
   > ![Menu volant de configuration de l’importation personnalisée SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Menu volant de configuration de l’importation personnalisée SFTP")

## <a name="defining-field-mappings"></a>Définition des mappages de champ 

Le répertoire contenant le fichier à importer sur le serveur SFTP doit également contenir un fichier *model.json*. Ce fichier définit le schéma à utiliser pour importer les données. Le schéma doit utiliser [Common Data Model](https://docs.microsoft.com/common-data-model/) pour spécifier le mappage de champ. Un exemple simple de fichier model.json se présente comme suit :

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a>Résultats d’enrichissement

Pour démarrer le processus d’enrichissement, sélectionnez **Exécuter** dans la barre de commandes. Vous pouvez également laisser le système exécuter l’enrichissement automatiquement dans le cadre d’une [actualisation programmée](system.md#schedule-tab). Le temps de traitement dépendra de la taille des données à importer et de la connexion au serveur SFTP.

Une fois le processus d’enrichissement terminé, vous pouvez consulter vos données d’enrichissement personnalisées nouvellement importées sous **Mes enrichissements**. De plus, vous trouverez l’heure de la dernière mise à jour et le nombre de profils enrichis.

Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.

## <a name="next-steps"></a>Étapes suivantes

Exploitez vos données client enrichies. Créez des [segments](segments.md), des [mesures](measures.md) et [exportez les données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.




[!INCLUDE[footer-include](../includes/footer-banner.md)]