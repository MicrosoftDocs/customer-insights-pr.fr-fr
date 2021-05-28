---
title: Exporter des données Customer Insights vers DotDigital
description: Apprenez à configurer la connexion et à exporter vers DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976843"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="f07db-103">Exporter des listes de segments vers DotDigital (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="f07db-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="f07db-104">Exportez des segments de profils clients unifiés vers les carnets d’adresses DotDigital et utilisez-les pour les campagnes, le marketing par e-mail, ainsi que pour créer des segments de client avec DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f07db-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f07db-105">Conditions préalables à une connexion</span><span class="sxs-lookup"><span data-stu-id="f07db-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f07db-106">Vous disposez d’un [compte DotDigital](https://dotdigital.com/) et des informations d’identification administrateur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="f07db-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f07db-107">Il existe des carnets d’adresses dans DotDigital et les ID correspondants.</span><span class="sxs-lookup"><span data-stu-id="f07db-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="f07db-108">L’ID se trouve dans l’URL lorsque vous sélectionnez et ouvrez un carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="f07db-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="f07db-109">Pour plus d’informations, consultez [Carnets d’adresses DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="f07db-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="f07db-110">Vous avez [configuré des segments](segments.md) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="f07db-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f07db-111">Les profils clients unifiés dans les segments exportés contiennent un champ représentant une adresse e-mail.</span><span class="sxs-lookup"><span data-stu-id="f07db-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f07db-112">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="f07db-112">Known limitations</span></span>

- <span data-ttu-id="f07db-113">Jusqu’à 1 million de profils par exportation vers DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f07db-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="f07db-114">L’exportation vers DotDigital est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="f07db-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="f07db-115">L’exportation de segments avec un total de 1 million de profils peut prendre jusqu’à 3 heures en raison des limitations du côté du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="f07db-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="f07db-116">Le nombre de profils que vous pouvez exporter vers DotDigital dépend et est limité par votre contrat avec DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f07db-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="f07db-117">Configurer la connexion à DotDigital</span><span class="sxs-lookup"><span data-stu-id="f07db-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="f07db-118">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="f07db-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f07db-119">Sélectionnez **Ajouter une connexion** et choisissez **DotDigital** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="f07db-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="f07db-120">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="f07db-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f07db-121">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="f07db-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f07db-122">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="f07db-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f07db-123">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="f07db-123">Choose who can use this connection.</span></span> <span data-ttu-id="f07db-124">Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="f07db-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f07db-125">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f07db-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f07db-126">Entrez vos **Nom d’utilisateur et mot de passe DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="f07db-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="f07db-127">Entrez votre **[ID de carnet d’adresses DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="f07db-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="f07db-128">Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.</span><span class="sxs-lookup"><span data-stu-id="f07db-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f07db-129">Sélectionnez **Connecter** pour initialiser la connexion à DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f07db-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="f07db-130">Sélectionnez **Vous ajouter en tant qu’utilisateur à exporter** et fournissez vos informations d’identification Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f07db-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f07db-131">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="f07db-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="f07db-132">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="f07db-132">Configure an export</span></span>

<span data-ttu-id="f07db-133">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="f07db-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f07db-134">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f07db-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f07db-135">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="f07db-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f07db-136">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="f07db-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f07db-137">Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f07db-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="f07db-138">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="f07db-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="f07db-139">Dans la section **Mise en correspondance des données**, dans le champ **E-mail**, sélectionnez le champ de votre profil client unifié qui représente l’adresse e-mail d’un client.</span><span class="sxs-lookup"><span data-stu-id="f07db-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f07db-140">Répétez les mêmes étapes pour les autres champs facultatifs tels que **Prénom**, **Nom**, **Nom complet**, **Sexe** et **Code postal**.</span><span class="sxs-lookup"><span data-stu-id="f07db-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="f07db-141">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="f07db-141">Select the segments you want to export.</span></span> <span data-ttu-id="f07db-142">Vous pouvez exporter jusqu’à 1 million de profils clients au total vers DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f07db-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="f07db-143">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f07db-143">Select **Save**.</span></span>

<span data-ttu-id="f07db-144">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="f07db-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f07db-145">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f07db-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f07db-146">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f07db-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="f07db-147">Dans DotDigital, vous trouverez désormais vos segments dans le [Carnets d’adresses DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="f07db-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f07db-148">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="f07db-148">Data privacy and compliance</span></span>

<span data-ttu-id="f07db-149">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers DotDigital, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="f07db-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f07db-150">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que DotDigital respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="f07db-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f07db-151">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f07db-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f07db-152">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="f07db-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
