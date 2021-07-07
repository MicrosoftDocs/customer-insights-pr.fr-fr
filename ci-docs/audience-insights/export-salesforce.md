---
title: Exporter les données Customer Insights vers Salesforce Marketing Cloud
description: Apprenez à configurer la connexion et à exporter vers Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314606"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="29db6-103">Exporter des segments et d’autres données vers Salesforce Marketing Cloud (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="29db6-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="29db6-104">Utilisez les données de vos clients dans Salesforce Marketing Cloud en les exportant via un emplacement SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="29db6-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="29db6-105">Conditions préalables à une connexion</span><span class="sxs-lookup"><span data-stu-id="29db6-105">Prerequisites for connection</span></span>

- <span data-ttu-id="29db6-106">Disponibilité d’un hôte SFTP et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="29db6-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="29db6-107">Comment configurer des emplacements SFTP pour Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="29db6-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="29db6-108">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="29db6-108">Known limitations</span></span>

- <span data-ttu-id="29db6-109">Le temps d’exécution d’une exportation dépend des performances de votre système.</span><span class="sxs-lookup"><span data-stu-id="29db6-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="29db6-110">Nous recommandons deux cœurs de processeur et 1 Go de mémoire comme configuration minimale de votre serveur.</span><span class="sxs-lookup"><span data-stu-id="29db6-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="29db6-111">L’exportation d’entités avec jusqu’à 100 millions de profils clients peut prendre 90 minutes avec la configuration minimale recommandée.</span><span class="sxs-lookup"><span data-stu-id="29db6-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="29db6-112">Configurer la connexion à Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="29db6-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="29db6-113">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="29db6-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="29db6-114">Sélectionnez **Ajouter une connexion** et choisissez **Salesforce Marketing Cloud** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="29db6-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="29db6-115">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="29db6-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="29db6-116">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="29db6-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="29db6-117">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="29db6-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="29db6-118">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="29db6-118">Choose who can use this connection.</span></span> <span data-ttu-id="29db6-119">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="29db6-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="29db6-120">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="29db6-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="29db6-121">Fournissez un **Nom d’utilisateur**, **Mot de passe**, **Nom d’hôte** et **dossier Exportation** pour votre compte SFTP.</span><span class="sxs-lookup"><span data-stu-id="29db6-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="29db6-122">Sélectionnez **Vérifier** pour tester la connexion.</span><span class="sxs-lookup"><span data-stu-id="29db6-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="29db6-123">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="29db6-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="29db6-124">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="29db6-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="29db6-125">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="29db6-125">Configure an export</span></span>

<span data-ttu-id="29db6-126">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="29db6-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="29db6-127">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="29db6-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="29db6-128">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="29db6-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="29db6-129">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="29db6-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="29db6-130">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section SFTP.</span><span class="sxs-lookup"><span data-stu-id="29db6-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="29db6-131">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="29db6-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="29db6-132">Choisissez si vous souhaitez exporter vos données **compressées** ou **décompressées** et le **délimiteur de champ** pour les fichiers exportés.</span><span class="sxs-lookup"><span data-stu-id="29db6-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="29db6-133">Sélectionnez les entités, par exemple des segments, à exporter.</span><span class="sxs-lookup"><span data-stu-id="29db6-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="29db6-134">Chaque entité sélectionnée sera fractionnée en cinq fichiers de sortie au maximum lors de l’exportation.</span><span class="sxs-lookup"><span data-stu-id="29db6-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="29db6-135">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="29db6-135">Select **Save**.</span></span>

<span data-ttu-id="29db6-136">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="29db6-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="29db6-137">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="29db6-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="29db6-138">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="29db6-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="29db6-139">Importer les données Customer Insights d’un emplacement SFTP vers Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="29db6-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="29db6-140">Créez des [extensions de données dans Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) pour importer le fichier de données Customer Insights à partir de l’emplacement SFTP.</span><span class="sxs-lookup"><span data-stu-id="29db6-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="29db6-141">[Importez les données de l’emplacement SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) dans l’extension de données Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="29db6-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="29db6-142">Configurez l’automatisation pour importer les données dans les extensions de données.</span><span class="sxs-lookup"><span data-stu-id="29db6-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="29db6-143">En savoir plus sur les [automatisations de dépôt de fichier et les automatisations planifiées](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="29db6-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="29db6-144">Définissez une [automatisation de dépôt de fichier](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ou une [automatisation planifiée](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="29db6-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="29db6-145">Voici un exemple d’[automatisation avec SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="29db6-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="29db6-146">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="29db6-146">Data privacy and compliance</span></span>

<span data-ttu-id="29db6-147">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données via SFTP, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="29db6-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="29db6-148">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que la destination d’exportation respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="29db6-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="29db6-149">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="29db6-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="29db6-150">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="29db6-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
