---
title: Enrichir les profils clients avec l’importation personnalisée SFTP (version préliminaire)
description: Informations générales sur l’enrichissement avec l’importation personnalisée SFTP.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 88fc366ab9478c3b67034af794e237ff4573da7c
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081030"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Enrichir les profils clients avec l’importation personnalisée SFTP (version préliminaire)

L’importation personnalisée SFTP (Secure File Transfer Protocol) vous permet d’importer des données qui ne doivent pas passer par le processus d’unification des données. C’est un moyen flexible, sécurisé et facile d’importer vos données. L’importation personnalisée SFTP peut être utilisée en combinaison avec l’[exportation SFTP](export-sftp.md) qui vous permet d’exporter les données de profil client nécessaires à l’enrichissement. Les données peuvent ensuite être traitées et enrichies et l’importation personnalisée SFTP peut être utilisée pour réimporter les données enrichies dans Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Conditions préalables

- Le nom de fichier et l'emplacement (chemin) du fichier à importer sur l'hôte SFTP sont connus.

- Un fichier *model.json* qui spécifie le schéma Common Data Model pour les données à importer est disponible. Ce fichier doit se trouver dans le même répertoire que le fichier à importer.

- Une [connexion](connections.md) SFTP est [configurée](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Exemple de schéma de fichier

Le répertoire contenant le fichier à importer sur le serveur SFTP doit également contenir un fichier *model.json*. Ce fichier définit le schéma à utiliser pour importer les données. Le schéma doit utiliser [Common Data Model](/common-data-model/) pour spécifier le mappage de champ. Un exemple simple de fichier model.json se présente comme suit :

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Configurer la connexion pour l’importation personnalisée SFTP

Vous devez être un [Administrateur](permissions.md#admin) dans Customer Insights et disposez des informations d'identification de l'utilisateur, de l'URL et du numéro de port de l'emplacement SFTP à partir duquel vous souhaitez importer des données.

1. Sélectionnez **Ajouter une connexion** lors de la configuration d’un enrichissement ou accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** sur la vignette d’importation personnalisée.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Page de configuration Connexion pour l'importation personnalisée.":::

1. Saisissez un nom pour l’ensemble de connexions.

1. Entrez un nom d’utilisateur, un mot de passe et une URL d’hôte valides pour le serveur SFTP dans lequel résident les données à importer.

1. Vérifiez et donnez votre consentement pour [Confidentialité et conformité des données](#data-privacy-and-compliance) en sélectionnant **J’accepte**.

1. Sélectionnez **Vérifier** pour valider la configuration, puis sélectionnez **Enregistrer**.

### <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données à l'aide de l'importation personnalisée, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous devez vous assurer que les données respectent toutes les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cet enrichissement à tout moment pour ne plus utiliser cette fonctionnalité.

## <a name="configure-the-import"></a>Configurer l’importation

1. Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.

1. Sélectionnez **Enrichir mes données** sur la vignette **Importation personnalisée SFTP**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Vignette d’importation personnalisée SFTP.":::

1. Passez la synthèse en revue et sélectionnez **Suivant**.

1. Sélectionnez la connexion. Contactez un Administrateur si aucun n'est disponible.

1. Sélectionnez le **Jeu de données client**, puis choisissez le profil ou segment que vous souhaitez enrichir. L’entité *Client* enrichit tous vos profils clients tandis qu'un segment enrichit uniquement les profils clients contenus dans ce segment.

1. Cliquez sur **Suivant**.

1. Entrez le **Chemin** et le **Nom de fichier** du fichier de données que vous souhaitez importer.

1. Cliquez sur **Suivant**.

1. Fournissez un **Nom** pour l’enrichissement et pour le **Nom de l'entité de sortie**.

1. Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.

1. Sélectionnez **Exécuter** pour démarrer le processus d'enrichissement ou fermer pour revenir à la page **Enrichissements**.

## <a name="view-enrichment-results"></a>Afficher les résultats de l’enrichissement

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Étapes suivantes

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
