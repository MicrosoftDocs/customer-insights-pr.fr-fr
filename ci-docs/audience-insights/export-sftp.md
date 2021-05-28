---
title: Exporter des données Customer Insights vers des hôtes SFTP
description: Apprenez à configurer la connexion et à exporter vers un emplacement SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3663a48955f0b1db8a96e25403e5f8947bc6a220
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976890"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="165ac-103">Exporter des listes de segments et d’autres données vers SFTP (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="165ac-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="165ac-104">Utilisez vos données client dans des applications tierces en les exportant vers un emplacement SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="165ac-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="165ac-105">Conditions préalables à une connexion</span><span class="sxs-lookup"><span data-stu-id="165ac-105">Prerequisites for connection</span></span>

- <span data-ttu-id="165ac-106">Disponibilité d’un hôte SFTP et des informations d’identification correspondantes.</span><span class="sxs-lookup"><span data-stu-id="165ac-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="165ac-107">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="165ac-107">Known limitations</span></span>

- <span data-ttu-id="165ac-108">Le temps d’exécution d’une exportation dépend des performances de votre système.</span><span class="sxs-lookup"><span data-stu-id="165ac-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="165ac-109">Nous recommandons deux cœurs de processeur et 1 Go de mémoire comme configuration minimale de votre serveur.</span><span class="sxs-lookup"><span data-stu-id="165ac-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="165ac-110">L’exportation d’entités avec jusqu’à 100 millions de profils clients peut prendre 90 minutes si vous utilisez la configuration minimale recommandée de deux cœurs de processeur et 1 Go de mémoire.</span><span class="sxs-lookup"><span data-stu-id="165ac-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="165ac-111">Configurer la connexion à SFTP</span><span class="sxs-lookup"><span data-stu-id="165ac-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="165ac-112">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="165ac-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="165ac-113">Sélectionnez **Ajouter une connexion** et choisissez **SFTP** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="165ac-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="165ac-114">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="165ac-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="165ac-115">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="165ac-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="165ac-116">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="165ac-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="165ac-117">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="165ac-117">Choose who can use this connection.</span></span> <span data-ttu-id="165ac-118">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="165ac-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="165ac-119">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="165ac-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="165ac-120">Fournissez un **Nom d’utilisateur**, **Mot de passe**, **Nom d’hôte** et **dossier Exportation** pour votre compte SFTP.</span><span class="sxs-lookup"><span data-stu-id="165ac-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="165ac-121">Sélectionnez **Vérifier** pour tester la connexion.</span><span class="sxs-lookup"><span data-stu-id="165ac-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="165ac-122">Choisissez si vous souhaitez exporter vos données **compressées** ou **décompressées** et le **délimiteur de champ** pour les fichiers exportés.</span><span class="sxs-lookup"><span data-stu-id="165ac-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="165ac-123">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="165ac-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="165ac-124">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="165ac-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="165ac-125">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="165ac-125">Configure an export</span></span>

<span data-ttu-id="165ac-126">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="165ac-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="165ac-127">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="165ac-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="165ac-128">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="165ac-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="165ac-129">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="165ac-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="165ac-130">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section SFTP.</span><span class="sxs-lookup"><span data-stu-id="165ac-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="165ac-131">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="165ac-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="165ac-132">Sélectionnez les entités, par exemple des segments, à exporter.</span><span class="sxs-lookup"><span data-stu-id="165ac-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="165ac-133">Chaque entité sélectionnée sera fractionnée en cinq fichiers de sortie au maximum lors de l’exportation.</span><span class="sxs-lookup"><span data-stu-id="165ac-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="165ac-134">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="165ac-134">Select **Save**.</span></span>

<span data-ttu-id="165ac-135">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="165ac-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="165ac-136">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="165ac-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="165ac-137">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="165ac-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="165ac-138">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="165ac-138">Data privacy and compliance</span></span>

<span data-ttu-id="165ac-139">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données via SFTP, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="165ac-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="165ac-140">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que la destination d’exportation respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="165ac-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="165ac-141">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="165ac-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="165ac-142">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="165ac-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
