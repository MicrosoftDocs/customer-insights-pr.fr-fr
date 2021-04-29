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
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896278"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="f0ad6-103">Enrichir les profils clients avec des données personnalisées (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="f0ad6-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="f0ad6-104">L’importation personnalisée SFTP (Secure File Transfer Protocol) vous permet d’importer des données qui ne doivent pas passer par le processus d’unification des données.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="f0ad6-105">C’est un moyen flexible, sécurisé et facile d’importer vos données.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="f0ad6-106">L’importation personnalisée SFTP peut être utilisée en combinaison avec l’[exportation SFTP](export-sftp.md) qui vous permet d’exporter les données de profil client nécessaires à l’enrichissement.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="f0ad6-107">Les données peuvent ensuite être traitées, enrichies et l’importation personnalisée SFTP peut être utilisée pour réimporter les données enrichies dans la fonctionnalité d’informations sur l’audience de Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f0ad6-108">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="f0ad6-108">Prerequisites</span></span>

<span data-ttu-id="f0ad6-109">Pour configurer l’importation personnalisée SFTP, les conditions préalables suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="f0ad6-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f0ad6-110">Vous disposez du nom de fichier et de l’emplacement (chemin d’accès) du fichier à importer dans l’hôte SFTP.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="f0ad6-111">Il existe un fichier *model.json* qui spécifie le [schéma Common Data Model](/common-data-model/) pour les données à importer.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="f0ad6-112">Ce fichier doit se trouver dans le même répertoire que le fichier à importer.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="f0ad6-113">Une connexion SFTP a déjà été configurée par un administrateur *ou* vous disposez d’autorisations [administrateur](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="f0ad6-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="f0ad6-114">Vous aurez besoin des informations d’identification de l’utilisateur, de l’URL et du numéro de port de l’emplacement SFTP à partir duquel vous souhaitez importer des données.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="f0ad6-115">Configurer l’importation</span><span class="sxs-lookup"><span data-stu-id="f0ad6-115">Configure the import</span></span>

1. <span data-ttu-id="f0ad6-116">Accédez à **Données** > **Enrichissement** et sélectionnez l’onglet **Découvrir**.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="f0ad6-117">Sur la **Vignette d’importation personnalisée SFTP**, sélectionnez **Enrichir mes données**, puis sélectionnez **Démarrer**.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Vignette d’importation personnalisée SFTP.":::

1. <span data-ttu-id="f0ad6-119">Sélectionnez une [connexion](connections.md) dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="f0ad6-120">Contactez un administrateur si aucune connexion n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="f0ad6-121">Si vous êtes un administrateur, vous pouvez créer une connexion en sélectionnant **Ajouter une connexion** et en choisissant **Importation personnalisée SFTP** dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="f0ad6-122">Sélectionnez **Se connecter à l’importation personnalisée** pour confirmer la connexion sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="f0ad6-123">Sélectionnez **Suivant** et entrez le **Nom de fichier** et le **Chemin d’accès** du fichier de données que vous souhaitez importer.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Capture d’écran lors de la saisie de l’emplacement des données.":::

1. <span data-ttu-id="f0ad6-125">Sélectionnez **Suivant** et fournissez un nom pour l’enrichissement et un nom pour l’entité de sortie.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="f0ad6-126">Sélectionnez **Enregistrer l’enrichissement** après avoir vérifié vos choix.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="f0ad6-127">Configurer la connexion pour l’importation personnalisée SFTP</span><span class="sxs-lookup"><span data-stu-id="f0ad6-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="f0ad6-128">Vous devez être un administrateur pour configurer les connexions.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="f0ad6-129">Sélectionnez **Ajouter une connexion** lors de la configuration d’un enrichissement *ou* accédez à **Administrateur** > **Connexions** et sélectionnez **Configurer** sur la vignette d’importation personnalisée.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="f0ad6-130">Entrez un nom pour la connexion dans la zone **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="f0ad6-131">Entrez un nom d’utilisateur, un mot de passe et une URL d’hôte valides pour le serveur STFP sur lequel résident les données à importer.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="f0ad6-132">Vérifiez et donnez votre consentement pour **Confidentialité et conformité des données** en cochant la case **J’accepte**.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="f0ad6-133">Sélectionnez **Vérifier** pour valider la configuration.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="f0ad6-134">Une fois la vérification terminée, la connexion peut être enregistrée en cliquant sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="f0ad6-135">![Page de configuration de la connexion d’Experian](media/enrichment-SFTP-connection.png "Page de configuration de la connexion d’Experian")</span><span class="sxs-lookup"><span data-stu-id="f0ad6-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="f0ad6-136">Définition des mappages de champ</span><span class="sxs-lookup"><span data-stu-id="f0ad6-136">Defining field mappings</span></span> 

<span data-ttu-id="f0ad6-137">Le répertoire contenant le fichier à importer sur le serveur SFTP doit également contenir un fichier *model.json*.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="f0ad6-138">Ce fichier définit le schéma à utiliser pour importer les données.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="f0ad6-139">Le schéma doit utiliser [Common Data Model](/common-data-model/) pour spécifier le mappage de champ.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="f0ad6-140">Un exemple simple de fichier model.json se présente comme suit :</span><span class="sxs-lookup"><span data-stu-id="f0ad6-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="f0ad6-141">Résultats d’enrichissement</span><span class="sxs-lookup"><span data-stu-id="f0ad6-141">Enrichment results</span></span>

<span data-ttu-id="f0ad6-142">Pour démarrer le processus d’enrichissement, sélectionnez **Exécuter** dans la barre de commandes.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f0ad6-143">Vous pouvez également laisser le système exécuter l’enrichissement automatiquement dans le cadre d’une [actualisation programmée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f0ad6-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f0ad6-144">Le temps de traitement dépendra de la taille des données à importer et de la connexion au serveur SFTP.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="f0ad6-145">Une fois le processus d’enrichissement terminé, vous pouvez consulter vos données d’enrichissement personnalisées nouvellement importées sous **Mes enrichissements**.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="f0ad6-146">De plus, vous trouverez l’heure de la dernière mise à jour et le nombre de profils enrichis.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f0ad6-147">Vous pouvez accéder à une vue détaillée de chaque profil enrichi en sélectionnant **Afficher des données enrichies**.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f0ad6-148">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="f0ad6-148">Next steps</span></span>

<span data-ttu-id="f0ad6-149">Exploitez vos données client enrichies.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f0ad6-150">Créez des [segments](segments.md), des [mesures](measures.md) et [exportez les données](export-destinations.md) pour offrir des expériences personnalisées à vos clients.</span><span class="sxs-lookup"><span data-stu-id="f0ad6-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
