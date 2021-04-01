---
title: Exporter des données Customer Insights vers des hôtes SFTP
description: Découvrez comment configurer la connexion vers un hôte SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598382"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="32d5e-103">Connecteur pour SFTP (préversion)</span><span class="sxs-lookup"><span data-stu-id="32d5e-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="32d5e-104">Utilisez vos données client dans des applications tierces en les exportant vers un hôte SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="32d5e-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="32d5e-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="32d5e-105">Prerequisites</span></span>

- <span data-ttu-id="32d5e-106">Disponibilité d’un hôte SFTP et des informations d’identification correspondantes.</span><span class="sxs-lookup"><span data-stu-id="32d5e-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="32d5e-107">Se connecter à SFTP</span><span class="sxs-lookup"><span data-stu-id="32d5e-107">Connect to SFTP</span></span>

1. <span data-ttu-id="32d5e-108">Accédez à **Administration** > **Destinations d’exportation**.</span><span class="sxs-lookup"><span data-stu-id="32d5e-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="32d5e-109">Sous **SFTP**, sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="32d5e-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="32d5e-110">Donnez à votre destination un nom reconnaissable dans le champ **Nom complet**.</span><span class="sxs-lookup"><span data-stu-id="32d5e-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="32d5e-111">Fournissez un **Nom d’utilisateur**, **Mot de passe**, **Nom d’hôte** et **dossier Exportation** pour votre compte SFTP.</span><span class="sxs-lookup"><span data-stu-id="32d5e-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="32d5e-112">Sélectionnez **Vérifier** pour tester la connexion.</span><span class="sxs-lookup"><span data-stu-id="32d5e-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="32d5e-113">Après une vérification réussie, choisissez si vous souhaitez exporter vos données **Gzippé** ou **Décompressées**, et sélectionnez le **délimiteur de champ** pour les fichiers exportés.</span><span class="sxs-lookup"><span data-stu-id="32d5e-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="32d5e-114">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="32d5e-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="32d5e-115">Sélectionnez **Suivant** pour commencer à configurer l’exportation.</span><span class="sxs-lookup"><span data-stu-id="32d5e-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="32d5e-116">Configurer l’exportation</span><span class="sxs-lookup"><span data-stu-id="32d5e-116">Configure the export</span></span>

1. <span data-ttu-id="32d5e-117">Sélectionnez les entités, par exemple des segments, à exporter.</span><span class="sxs-lookup"><span data-stu-id="32d5e-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="32d5e-118">Chaque entité sélectionnée aura jusqu’à cinq fichiers de sortie lors de l’exportation.</span><span class="sxs-lookup"><span data-stu-id="32d5e-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="32d5e-119">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="32d5e-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="32d5e-120">Exporter les données</span><span class="sxs-lookup"><span data-stu-id="32d5e-120">Export the data</span></span>

<span data-ttu-id="32d5e-121">Vous pouvez [exporter les données à la demande](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="32d5e-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="32d5e-122">L’exportation sera également exécutée à chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="32d5e-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="32d5e-123">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="32d5e-123">Known limitations</span></span>

- <span data-ttu-id="32d5e-124">Le temps d’exécution d’une exportation dépend des performances de votre système.</span><span class="sxs-lookup"><span data-stu-id="32d5e-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="32d5e-125">Nous recommandons deux cœurs de processeur et 1 Go de mémoire comme configuration minimale de votre serveur.</span><span class="sxs-lookup"><span data-stu-id="32d5e-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="32d5e-126">L’exportation d’entités avec jusqu’à 100 millions de profils clients peut prendre 90 minutes si vous utilisez la configuration minimale recommandée de deux cœurs de processeur et 1 Go de mémoire.</span><span class="sxs-lookup"><span data-stu-id="32d5e-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="32d5e-127">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="32d5e-127">Data privacy and compliance</span></span>

<span data-ttu-id="32d5e-128">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données via SFTP, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="32d5e-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="32d5e-129">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que la destination d’exportation respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="32d5e-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="32d5e-130">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="32d5e-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="32d5e-131">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="32d5e-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]