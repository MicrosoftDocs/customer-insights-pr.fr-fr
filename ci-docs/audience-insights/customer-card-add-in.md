---
title: Installer et configurer le complément Carte client
description: Installez et configurez le Complément Carte client pour Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597324"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="c78f0-103">Complément Carte client (préversion)</span><span class="sxs-lookup"><span data-stu-id="c78f0-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c78f0-104">Obtenez une vue globale de vos clients directement dans les applications Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c78f0-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="c78f0-105">Affichez les données démographiques, les informations et les chronologies des activités avec le complément Carte client.</span><span class="sxs-lookup"><span data-stu-id="c78f0-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c78f0-106">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="c78f0-106">Prerequisites</span></span>

- <span data-ttu-id="c78f0-107">Application Dynamics 365 (telle que le Centre des ventes ou le Centre Customer Service), version 9.0 et ultérieure avec Unified Interface activé.</span><span class="sxs-lookup"><span data-stu-id="c78f0-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="c78f0-108">Profils clients [ingérés depuis l’application Dynamics 365 à l’aide de Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="c78f0-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="c78f0-109">Les utilisateurs du complément Carte client doivent être [ajoutés en tant qu’utilisateurs](permissions.md) dans les informations sur l’audience.</span><span class="sxs-lookup"><span data-stu-id="c78f0-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="c78f0-110">[Fonctions de recherche et de filtrage configurées](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="c78f0-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="c78f0-111">Contrôle démographique : les champs démographiques (tels que l’âge ou le sexe) sont disponibles dans le profil client unifié.</span><span class="sxs-lookup"><span data-stu-id="c78f0-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="c78f0-112">Contrôle d’enrichissement : nécessite des [enrichissements](enrichment-hub.md) actifs appliqués aux profils clients.</span><span class="sxs-lookup"><span data-stu-id="c78f0-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="c78f0-113">Contrôle d’intelligence : nécessite des données générées à l’aide d’Azure Machine Learning ([Prédictions](predictions.md) ou [Modèles personnalisés](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="c78f0-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="c78f0-114">Contrôle de mesure : nécessite des [mesures configurées](measures.md).</span><span class="sxs-lookup"><span data-stu-id="c78f0-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="c78f0-115">Contrôle de chronologie : nécessite des [activités configurées](activities.md).</span><span class="sxs-lookup"><span data-stu-id="c78f0-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="c78f0-116">Installer le complément Fiche client</span><span class="sxs-lookup"><span data-stu-id="c78f0-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="c78f0-117">Le complément de carte client est une solution pour les applications Customer Engagement dans Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c78f0-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="c78f0-118">Pour installer la solution, accédez à AppSource et recherchez **Carte client Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="c78f0-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="c78f0-119">Sélectionnez le [Complément Carte client sur AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) et sélectionnez **Obtenir maintenant**.</span><span class="sxs-lookup"><span data-stu-id="c78f0-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="c78f0-120">Vous devrez peut-être vous connecter avec vos informations d’identification d’administrateur à l’application Dynamics 365 pour installer la solution.</span><span class="sxs-lookup"><span data-stu-id="c78f0-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="c78f0-121">L’installation de la solution dans votre environnement peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="c78f0-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="c78f0-122">Configurer le complément Carte client</span><span class="sxs-lookup"><span data-stu-id="c78f0-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="c78f0-123">En tant qu’administrateur, accédez à la section **Paramètres** de Dynamics 365 et sélectionnez **Solutions**.</span><span class="sxs-lookup"><span data-stu-id="c78f0-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="c78f0-124">Sélectionnez le lien **Nom complet** pour la solution **Complément Carte client Dynamics 365 Customer Insights (préversion)**.</span><span class="sxs-lookup"><span data-stu-id="c78f0-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c78f0-125">![Sélectionner le nom complet](media/select-display-name.png "Sélectionner le nom complet")</span><span class="sxs-lookup"><span data-stu-id="c78f0-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="c78f0-126">Sélectionnez **Se connecter** et entrez les identifiants du compte d’administrateur que vous utilisez pour configurer Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c78f0-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c78f0-127">Vérifiez que le bloqueur de fenêtres publicitaires de votre navigateur ne bloque pas la fenêtre d’authentification lorsque vous cliquez sur le bouton **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="c78f0-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="c78f0-128">Sélectionnez l’environnement à partir duquel vous souhaitez extraire des données.</span><span class="sxs-lookup"><span data-stu-id="c78f0-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="c78f0-129">Définissez quel champ est mappé aux enregistrements dans l’application Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c78f0-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="c78f0-130">Pour effectuer un mappage avec un contact, sélectionnez le champ dans l’entité Client correspondant à l’ID de votre entité de contact.</span><span class="sxs-lookup"><span data-stu-id="c78f0-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="c78f0-131">Pour effectuer un mappage avec un compte, sélectionnez le champ dans l’entité Client correspondant à l’ID de votre entité de compte.</span><span class="sxs-lookup"><span data-stu-id="c78f0-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c78f0-132">![Champ ID de contact](media/contact-id-field.png "Champ ID de contact")</span><span class="sxs-lookup"><span data-stu-id="c78f0-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="c78f0-133">Sélectionnez **Enregistrer la configuration** pour enregistrer les paramètres.</span><span class="sxs-lookup"><span data-stu-id="c78f0-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="c78f0-134">Ensuite, vous devez affecter des rôles de sécurité dans Dynamics 365 afin que les utilisateurs puissent personnaliser et afficher la carte client.</span><span class="sxs-lookup"><span data-stu-id="c78f0-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="c78f0-135">Dans Dynamics 365, accédez à **Paramètres** > **Sécurité** > **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="c78f0-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="c78f0-136">Sélectionnez les utilisateurs pour modifier les rôles d’utilisateur et sélectionnez **Gérer les rôles**.</span><span class="sxs-lookup"><span data-stu-id="c78f0-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="c78f0-137">Attribuez le rôle **Personnalisateur de carte Customer Insights** aux utilisateurs qui personnaliseront le contenu à afficher sur la carte pour l’ensemble de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="c78f0-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="c78f0-138">Ajouter des contrôles Carte client aux formulaires</span><span class="sxs-lookup"><span data-stu-id="c78f0-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="c78f0-139">Pour ajouter les contrôles Carte client à votre formulaire Contact, accédez à **Paramètres** > **Personnalisations** dans Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c78f0-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="c78f0-140">Sélectionnez **Personnaliser le système**.</span><span class="sxs-lookup"><span data-stu-id="c78f0-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="c78f0-141">Accédez à l’entité **Contact**, développez-la, puis sélectionnez **Formulaires**.</span><span class="sxs-lookup"><span data-stu-id="c78f0-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="c78f0-142">Sélectionnez le formulaire de contact auquel vous souhaitez ajouter les contrôles Carte client.</span><span class="sxs-lookup"><span data-stu-id="c78f0-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c78f0-143">![Sélectionner le formulaire Contact](media/contact-active-forms.png "Sélectionner le formulaire Contact")</span><span class="sxs-lookup"><span data-stu-id="c78f0-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="c78f0-144">Pour ajouter un contrôle, dans l’éditeur de formulaires, faites glisser un champ de l’**Explorateur de champs** vers l’emplacement où vous souhaitez faire apparaître le contrôle.</span><span class="sxs-lookup"><span data-stu-id="c78f0-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="c78f0-145">Sélectionnez le champ sur le formulaire que vous venez d’ajouter, puis sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c78f0-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="c78f0-146">Accédez à l’onglet **Contrôles** et sélectionnez **Ajouter un contrôle**.</span><span class="sxs-lookup"><span data-stu-id="c78f0-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="c78f0-147">Choisissez l’un des contrôles personnalisés disponibles et sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="c78f0-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="c78f0-148">Dans la boîte de dialogue **Propriétés du champ**, désactivez la case à cocher **Afficher l’étiquette sur le formulaire**.</span><span class="sxs-lookup"><span data-stu-id="c78f0-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="c78f0-149">Sélectionnez l’option **Web** pour le contrôle.</span><span class="sxs-lookup"><span data-stu-id="c78f0-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="c78f0-150">Pour le contrôle d’enrichissement, sélectionnez le type d’enrichissement que vous souhaitez afficher en configurant le champ **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="c78f0-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="c78f0-151">Ajoutez un contrôle d’enrichissement distinct pour chaque type d’enrichissement.</span><span class="sxs-lookup"><span data-stu-id="c78f0-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="c78f0-152">Sélectionnez **Enregistrer** et **Publier** pour publier le formulaire de contact mis à jour.</span><span class="sxs-lookup"><span data-stu-id="c78f0-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="c78f0-153">Accédez au formulaire de contact publié.</span><span class="sxs-lookup"><span data-stu-id="c78f0-153">Go to the published contact form.</span></span> <span data-ttu-id="c78f0-154">Le nouveau contrôle ajouté s’affiche.</span><span class="sxs-lookup"><span data-stu-id="c78f0-154">You'll see the newly added control.</span></span> <span data-ttu-id="c78f0-155">Vous pouvez devoir vous connecter la première fois que vous l’utiliserez.</span><span class="sxs-lookup"><span data-stu-id="c78f0-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="c78f0-156">Pour personnaliser ce que vous souhaitez afficher sur le contrôle personnalisé, sélectionnez le bouton Modifier dans le coin supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="c78f0-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="c78f0-157">Mettre à niveau le complément de carte client</span><span class="sxs-lookup"><span data-stu-id="c78f0-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="c78f0-158">Le complément de carte client ne se met pas à niveau automatiquement.</span><span class="sxs-lookup"><span data-stu-id="c78f0-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="c78f0-159">Pour mettre à niveau vers la dernière version, suivez cette procédure dans l’application Dynamics 365 sur laquelle le complément est installé.</span><span class="sxs-lookup"><span data-stu-id="c78f0-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="c78f0-160">Dans l’application Dynamics 365, accédez à **Paramètres** > **Personnalisation** et sélectionnez **Solutions**.</span><span class="sxs-lookup"><span data-stu-id="c78f0-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="c78f0-161">Dans le tableau des compléments, recherchez **CustomerInsightsCustomerCard** et sélectionnez la ligne.</span><span class="sxs-lookup"><span data-stu-id="c78f0-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="c78f0-162">Sélectionnez **Appliquer la mise à niveau de la solution** dans la barre d’action.</span><span class="sxs-lookup"><span data-stu-id="c78f0-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Mettez à niveau la solution dans la zone de personnalisation des applications Dynamics 365":::

1. <span data-ttu-id="c78f0-164">Après le démarrage du processus de mise à niveau, vous verrez un indicateur de chargement jusqu’à la fin de la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="c78f0-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="c78f0-165">S’il n’y a pas de version plus récente, la mise à niveau affichera un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="c78f0-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]