---
title: Exporter des données Customer Insights vers Facebook Ads Manager
description: Apprenez à configurer la connexion et à exporter vers Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906807"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="e7716-103">Exporter une liste de segments vers Facebook Ads Manager (version préliminaire)</span><span class="sxs-lookup"><span data-stu-id="e7716-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="e7716-104">Exportez des segments de profils client unifiés vers Facebook Ads Manager pour créer des campagnes sur Facebook et Instagram.</span><span class="sxs-lookup"><span data-stu-id="e7716-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e7716-105">Conditions préalables à une connexion</span><span class="sxs-lookup"><span data-stu-id="e7716-105">Prerequisites for connection</span></span>

- <span data-ttu-id="e7716-106">Vous devez disposer d’un [Compte **Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) comprenant un [Compte professionnel **Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="e7716-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="e7716-107">Vous devez être un administrateur du [compte **Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="e7716-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e7716-108">Limitations connues</span><span class="sxs-lookup"><span data-stu-id="e7716-108">Known limitations</span></span>

- <span data-ttu-id="e7716-109">Jusqu’à 10 millions de profils clients par exportation vers Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="e7716-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="e7716-110">L’exportation vers Facebook Ads Manager est limitée aux segments.</span><span class="sxs-lookup"><span data-stu-id="e7716-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="e7716-111">Créez ou mettez à jour des audiences personnalisées dans Facebook de type *liste de clients* uniquement.</span><span class="sxs-lookup"><span data-stu-id="e7716-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="e7716-112">L’exportation de segments avec un total de 10 millions de profils peut prendre jusqu’à 90 minutes.</span><span class="sxs-lookup"><span data-stu-id="e7716-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="e7716-113">Configurer la connexion à Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="e7716-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="e7716-114">Avant que les utilisateurs puissent créer une exportation, un administrateur doit configurer la connexion au service et autoriser les contributeurs à utiliser la connexion.</span><span class="sxs-lookup"><span data-stu-id="e7716-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="e7716-115">Accédez à **Administrateur** > **Connexions**.</span><span class="sxs-lookup"><span data-stu-id="e7716-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e7716-116">Sélectionnez **Ajouter une connexion** et choisissez **Facebook Ads Manager** pour configurer la connexion.</span><span class="sxs-lookup"><span data-stu-id="e7716-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="e7716-117">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="e7716-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e7716-118">Le nom et le type de connexion décrivent cette connexion.</span><span class="sxs-lookup"><span data-stu-id="e7716-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e7716-119">Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.</span><span class="sxs-lookup"><span data-stu-id="e7716-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e7716-120">Choisissez qui peut utiliser cette connexion.</span><span class="sxs-lookup"><span data-stu-id="e7716-120">Choose who can use this connection.</span></span> <span data-ttu-id="e7716-121">Si vous n’effectuez aucune action, la valeur par défaut sera **Administrateurs**.</span><span class="sxs-lookup"><span data-stu-id="e7716-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="e7716-122">Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e7716-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e7716-123">S’authentifier avec Facebook Ads :</span><span class="sxs-lookup"><span data-stu-id="e7716-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="e7716-124">Sélectionner **Continue avec Facebook** pour vous connecter à votre compte Facebook Ads.</span><span class="sxs-lookup"><span data-stu-id="e7716-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="e7716-125">Activez l’autorisation **ads_management** après l’authentification dans Facebook.</span><span class="sxs-lookup"><span data-stu-id="e7716-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="e7716-126">Sélectionnez le **Compte Facebook Ads** que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="e7716-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="e7716-127">Sélectionnez une **Audience personnalisée existante** dans la liste déroulante ou créez une **Nouvelle audience personnalisée**.</span><span class="sxs-lookup"><span data-stu-id="e7716-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="e7716-128">Pour plus d’informations, voir [**Audiences dans Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="e7716-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="e7716-129">Vous ne pouvez que créer ou mettre à jour des audiences personnalisées sur Facebook de type *liste de clients* avec cette exportation.</span><span class="sxs-lookup"><span data-stu-id="e7716-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="e7716-130">Dans certains cas, des audiences personnalisées de différents types s’affichent dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="e7716-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="e7716-131">Si vous sélectionnez un type autre que *liste de clients*, cela entraînera l’échec de l’exportation.</span><span class="sxs-lookup"><span data-stu-id="e7716-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="e7716-132">Passez en revue la **Confidentialité et conformité des données** et sélectionnez **J’accepte**.</span><span class="sxs-lookup"><span data-stu-id="e7716-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="e7716-133">Sélectionnez **Enregistrer** pour terminer la connexion.</span><span class="sxs-lookup"><span data-stu-id="e7716-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e7716-134">Configurer une exportation</span><span class="sxs-lookup"><span data-stu-id="e7716-134">Configure an export</span></span>

<span data-ttu-id="e7716-135">Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type.</span><span class="sxs-lookup"><span data-stu-id="e7716-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e7716-136">Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e7716-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e7716-137">Accédez à **Données** > **Exportations**.</span><span class="sxs-lookup"><span data-stu-id="e7716-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e7716-138">Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.</span><span class="sxs-lookup"><span data-stu-id="e7716-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="e7716-139">Dans **Connexion pour l’exportation**, choisissez une connexion dans la section **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="e7716-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="e7716-140">Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="e7716-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e7716-141">Dans le champ **Sélectionner votre champ d’identificateur de la clé**, sélectionnez **E-mail**, **Nom et adresse** ou **Téléphone** à envoyer à Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="e7716-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="e7716-142">Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**.</span><span class="sxs-lookup"><span data-stu-id="e7716-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e7716-143">Mappez les attributs correspondants de votre entité client unifiée pour l’identifiant de clé sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e7716-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="e7716-144">[CONSEIL] Les meilleures chances pour une correspondance se produisent si vous sélectionnez **E-mail** comme identificateur de la clé.</span><span class="sxs-lookup"><span data-stu-id="e7716-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="e7716-145">L’ajout d’identificateurs supplémentaires peut améliorer la correspondance.</span><span class="sxs-lookup"><span data-stu-id="e7716-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="e7716-146">Sélectionnez **Ajouter un attribut** pour mapper d’autres attributs à envoyer vers Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="e7716-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="e7716-147">Les attributs de Facebook Ads Manager correspondent aux noms conviviaux suivants : **FN** = **Prénom**, **LN** = **Nom de famille**, **FI** = **Première initiale**, **PHONE** = **Téléphone**, **GEN** = **Sexe**, **DOB** = **Date de naissance**, **ST** = **État**, **CT** = **Ville**, **ZIP** = **Code postal**, **COUNTRY** = **Pays/Région**</span><span class="sxs-lookup"><span data-stu-id="e7716-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="e7716-148">Sélectionnez les segments que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="e7716-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="e7716-149">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e7716-149">Select **Save**.</span></span>

<span data-ttu-id="e7716-150">L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.</span><span class="sxs-lookup"><span data-stu-id="e7716-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e7716-151">L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e7716-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e7716-152">Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e7716-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e7716-153">Confidentialité et conformité des données</span><span class="sxs-lookup"><span data-stu-id="e7716-153">Data privacy and compliance</span></span>

<span data-ttu-id="e7716-154">Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données vers Facebook Ads Manager, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles.</span><span class="sxs-lookup"><span data-stu-id="e7716-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e7716-155">Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que Facebook Ads respecte les obligations de confidentialité ou de sécurité qui vous incombent.</span><span class="sxs-lookup"><span data-stu-id="e7716-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="e7716-156">Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e7716-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e7716-157">Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="e7716-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
