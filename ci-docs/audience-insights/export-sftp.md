---
title: Exporter des données Customer Insights vers des hôtes SFTP
description: Découvrez comment configurer la connexion vers un hôte SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643500"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="1b8a4-103">Connecteur pour SFTP (préversion)</span><span class="sxs-lookup"><span data-stu-id="1b8a4-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="1b8a4-104">Utilisez vos données client dans des applications tierces en les exportant vers un hôte SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="1b8a4-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1b8a4-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="1b8a4-105">Prerequisites</span></span>

- <span data-ttu-id="1b8a4-106">Disponibilité d'un hôte SFTP et informations d'identification correspondantes.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="1b8a4-107">Se connecter à SFTP</span><span class="sxs-lookup"><span data-stu-id="1b8a4-107">Connect to SFTP</span></span>

1. <span data-ttu-id="1b8a4-108">Accédez à **Administration** > **Destinations d'exportation**.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1b8a4-109">Sous **SFTP**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="1b8a4-110">Donnez à votre destination un nom reconnaissable dans le champ **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="1b8a4-111">Fournissez un **Nom d'utilisateur**, **Mot de passe** et **Nom d'hôte** pour votre compte SFTP.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="1b8a4-112">Exemple : si le dossier racine de votre serveur SFTP est /root/folder et vous souhaitez que les données soient exportées vers /root/folder/ci_export_destination_folder, l'hôte doit être sftp://<server_address>/ci_export_destination_folder.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="1b8a4-113">Sélectionnez **Vérifier** pour tester la connexion.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="1b8a4-114">Une fois la vérification réussie, choisissez si vous souhaitez exporter vos données **Comprimées** ou **Non comprimées** et sélectionnez le **délimiteur de champ** pour les fichiers exportés.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="1b8a4-115">Sélectionnez **J'accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1b8a4-116">Sélectionnez **Suivant** pour commencer à configurer l'exportation.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="1b8a4-117">Configurer la connexion</span><span class="sxs-lookup"><span data-stu-id="1b8a4-117">Configure the connection</span></span>

1. <span data-ttu-id="1b8a4-118">Sélectionnez les **attributs client** que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="1b8a4-119">Vous pouvez exporter un ou plusieurs attributs.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="1b8a4-120">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-120">Select **Next**.</span></span>

1. <span data-ttu-id="1b8a4-121">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="1b8a4-122">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1b8a4-123">Exporter les données</span><span class="sxs-lookup"><span data-stu-id="1b8a4-123">Export the data</span></span>

<span data-ttu-id="1b8a4-124">Vous pouvez [exporter les données à la demande](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="1b8a4-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="1b8a4-125">L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1b8a4-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1b8a4-126">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="1b8a4-126">Data privacy and compliance</span></span>

<span data-ttu-id="1b8a4-127">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données via SFTP, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1b8a4-128">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que la destination d'exportation respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1b8a4-129">Pour plus d'informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1b8a4-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1b8a4-130">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d'exportation à tout moment pour interrompre l'utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="1b8a4-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
