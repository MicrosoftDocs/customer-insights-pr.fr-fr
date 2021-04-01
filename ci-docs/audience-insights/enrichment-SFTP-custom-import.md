---
title: Enrichissement avec l’importation personnalisée SFTP
description: Informations générales sur l’enrichissement avec l’importation personnalisée SFTP.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595852"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="dcfd2-103">Enrichir les profils clients avec des données personnalisées (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="dcfd2-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="dcfd2-104">L’importation personnalisée SFTP (Secure File Transfer Protocol) vous permet d’importer des données qui ne doivent pas passer par le processus d’unification des données.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="dcfd2-105">C’est un moyen flexible, sécurisé et facile d’importer vos données.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="dcfd2-106">L’importation personnalisée SFTP peut être utilisée en combinaison avec l’[exportation SFTP](export-sftp.md) qui vous permet d’exporter les données de profil client nécessaires à l’enrichissement.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="dcfd2-107">Les données peuvent ensuite être traitées, enrichies et l’importation personnalisée SFTP peut être utilisée pour réimporter les données enrichies dans la fonctionnalité d’informations sur l’audience de Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dcfd2-108">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="dcfd2-108">Prerequisites</span></span>

<span data-ttu-id="dcfd2-109">Pour configurer l’importation personnalisée SFTP, les conditions préalables suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="dcfd2-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="dcfd2-110">Vous disposez des informations d’identification utilisateur (nom d’utilisateur et mot de passe) de l’emplacement SFTP à partir duquel les données vont être importées.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="dcfd2-111">Vous disposez de l’URL et du numéro de port (généralement 22) de l’hôte STFP.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="dcfd2-112">Vous disposez du nom et de l’emplacement du fichier à importer sur l’hôte SFTP.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="dcfd2-113">Un fichier *model.json* spécifie le schéma des données à importer.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="dcfd2-114">Ce fichier doit se trouver dans le même répertoire que le fichier à importer.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="dcfd2-115">Vous disposez d’autorisations [Administrateur](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="dcfd2-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="dcfd2-116">configuration</span><span class="sxs-lookup"><span data-stu-id="dcfd2-116">Configuration</span></span>

1. <span data-ttu-id="dcfd2-117">Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="dcfd2-118">Sur la **vignette d’importation personnalisée SFTP**, sélectionnez **Enrichir mes données**.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dcfd2-119">![Vignette d’importation personnalisée SFTP](media/SFTP_Custom_Import_tile.png "Vignette d’importation personnalisée SFTP")</span><span class="sxs-lookup"><span data-stu-id="dcfd2-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="dcfd2-120">Sélectionnez **Démarrer** et fournissez les informations d’identification et l’adresse du serveur SFTP.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="dcfd2-121">Par exemple, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="dcfd2-122">Entrez le nom du fichier contenant les données et le chemin d’accès au fichier sur le serveur SFTP s’il ne se trouve pas dans le dossier racine.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="dcfd2-123">Confirmez toutes les entrées en sélectionnant **Se connecter à l’importation personnalisée**.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dcfd2-124">![Menu volant de configuration de l’importation personnalisée SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Menu volant de configuration de l’importation personnalisée SFTP")</span><span class="sxs-lookup"><span data-stu-id="dcfd2-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="dcfd2-125">Définition des mappages de champ</span><span class="sxs-lookup"><span data-stu-id="dcfd2-125">Defining field mappings</span></span> 

<span data-ttu-id="dcfd2-126">Le répertoire contenant le fichier à importer sur le serveur SFTP doit également contenir un fichier *model.json*.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="dcfd2-127">Ce fichier définit le schéma à utiliser pour importer les données.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="dcfd2-128">Le schéma doit utiliser [Common Data Model](/common-data-model/) pour spécifier le mappage de champ.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-128">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="dcfd2-129">Un exemple simple de fichier model.json se présente comme suit :</span><span class="sxs-lookup"><span data-stu-id="dcfd2-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="dcfd2-130">Résultats d’enrichissement</span><span class="sxs-lookup"><span data-stu-id="dcfd2-130">Enrichment results</span></span>

<span data-ttu-id="dcfd2-131">Pour démarrer le processus d’enrichissement, sélectionnez **Exécuter** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="dcfd2-132">Vous pouvez également laisser le système exécuter l’enrichissement automatiquement dans le cadre d’une [actualisation programmée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dcfd2-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dcfd2-133">Le temps de traitement dépendra de la taille des données à importer et de la connexion au serveur SFTP.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="dcfd2-134">Une fois le processus d’enrichissement terminé, vous pouvez consulter vos données d’enrichissement personnalisées nouvellement importées sous **Mes enrichissements**.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="dcfd2-135">De plus, vous trouverez l’heure de la dernière mise à jour et le nombre de profils enrichis.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="dcfd2-136">Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dcfd2-137">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="dcfd2-137">Next steps</span></span>

<span data-ttu-id="dcfd2-138">Exploitez vos données client enrichies.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="dcfd2-139">Créez des [segments](segments.md), des [mesures](measures.md) et [exportez les données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.</span><span class="sxs-lookup"><span data-stu-id="dcfd2-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]