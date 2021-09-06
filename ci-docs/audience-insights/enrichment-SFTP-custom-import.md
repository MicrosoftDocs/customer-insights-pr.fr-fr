---
title: Enrichissement avec l’importation personnalisée SFTP
description: Informations générales sur l’enrichissement avec l’importation personnalisée SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b67aa7477033222b0bc9512a962a1580edd973b4882ce925620ff5ec14f83fe3
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032709"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Enrichir les profils clients avec des données personnalisées (version préliminaire)

L’importation personnalisée SFTP (Secure File Transfer Protocol) vous permet d’importer des données qui ne doivent pas passer par le processus d’unification des données. C’est un moyen flexible, sécurisé et facile d’importer vos données. L’importation personnalisée SFTP peut être utilisée en combinaison avec l’[exportation SFTP](export-sftp.md) qui vous permet d’exporter les données de profil client nécessaires à l’enrichissement. Les données peuvent ensuite être traitées et enrichies, et l’importation personnalisée SFTP peut être utilisée pour renvoyer les données enrichies vers la fonctionnalité Audience Insights de Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Conditions préalables

Pour configurer l’importation personnalisée SFTP, les conditions préalables suivantes doivent être remplies :

- Vous disposez du nom de fichier et de l’emplacement (chemin d’accès) du fichier à importer dans l’hôte SFTP.
- Il existe un fichier *model.json* qui spécifie le [schéma Common Data Model](/common-data-model/) pour les données à importer. Ce fichier doit se trouver dans le même répertoire que le fichier à importer.
- Une connexion SFTP a déjà été configurée par un administrateur *ou* vous disposez d’autorisations [administrateur](permissions.md#administrator). Vous aurez besoin des informations d’identification de l’utilisateur, de l’URL et du numéro de port de l’emplacement SFTP à partir duquel vous souhaitez importer des données.


## <a name="configure-the-import"></a>Configurer l’importation

1. Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.

1. Sur la **Vignette d’importation personnalisée SFTP**, sélectionnez **Enrichir mes données**, puis sélectionnez **Démarrer**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Vignette d’importation personnalisée SFTP.":::

1. Sélectionnez une [connexion](connections.md) dans la liste déroulante. Contactez un administrateur si aucune connexion n’est disponible. Si vous êtes un administrateur, vous pouvez créer une connexion en sélectionnant **Ajouter une connexion** et en choisissant **Importation personnalisée SFTP** dans la liste déroulante.

1. Sélectionnez **Se connecter à l’importation personnalisée** pour confirmer la connexion sélectionnée.

1.  Sélectionnez **Suivant** et entrez le **Chemin d’accès** et le **Nom de fichier** du fichier de données que vous souhaitez importer.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Capture d’écran lors de la saisie de l’emplacement des données.":::

1. Sélectionnez **Suivant** et fournissez un nom pour l’enrichissement et un nom pour l’entité de sortie. 

1. Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Configurer la connexion pour l’importation personnalisée SFTP 

Vous devez être un administrateur pour configurer les connexions. Sélectionnez **Ajouter une connexion** lors de la configuration d’un enrichissement *ou* accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** sur la vignette d’importation personnalisée.

1. Entrez un nom pour la connexion dans la zone **Nom d’affichage**.

1. Entrez un nom d’utilisateur, un mot de passe et une URL d’hôte valides pour le serveur SFTP dans lequel résident les données à importer.

1. Vérifiez et donnez votre consentement pour **Confidentialité et conformité des données** en cochant la case **J’accepte**.

1. Sélectionnez **Vérifier** pour valider la configuration.

1. Une fois la vérification terminée, la connexion peut être enregistrée en sélectionnant **Enregistrer**.

   > [!div class="mx-imgBorder"]
   > ![Page de configuration de la connexion Experian.](media/enrichment-SFTP-connection.png "Page de configuration de la connexion Experian")


## <a name="defining-field-mappings"></a>Définition des mappages de champ 

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

Exploitez vos données client enrichies. Créez des [segments](segments.md) et des [mesures](measures.md) et [exportez les données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
