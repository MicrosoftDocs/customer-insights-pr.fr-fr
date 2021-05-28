---
title: Complément de carte client pour les applications Dynamics 365
description: Affichez les données des informations sur l’audience dans les applications Dynamics 365 avec ce complément.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059585"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="09afc-103">Complément Carte client (préversion)</span><span class="sxs-lookup"><span data-stu-id="09afc-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="09afc-104">Obtenez une vue globale de vos clients directement dans les applications Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="09afc-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="09afc-105">Avec le complément de carte client installé dans une application Dynamics 365 prise en charge, vous pouvez choisir d’afficher des données démographiques, des informations et des calendriers d’activité.</span><span class="sxs-lookup"><span data-stu-id="09afc-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="09afc-106">Le complément récupérera les données de Customer Insights sans affecter les données de l’application Dynamics 365 connectée.</span><span class="sxs-lookup"><span data-stu-id="09afc-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="09afc-107">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="09afc-107">Prerequisites</span></span>

- <span data-ttu-id="09afc-108">Le complément fonctionne uniquement avec les applications pilotées par modèle Dynamics 365, telles que Sales ou Customer Service, versions 9.0 et ultérieures.</span><span class="sxs-lookup"><span data-stu-id="09afc-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="09afc-109">Pour que vos données Dynamics 365 soient mappées aux profils client d’informations sur l’audience, elles doivent être [intégrées à partir de l’application Dynamics 365 à l’aide du connecteur Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="09afc-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="09afc-110">Tous les utilisateurs Dynamics 365 du complément de carte client doivent être [ajoutés en tant qu’utilisateurs](permissions.md) dans les informations sur l’audience pour voir les données.</span><span class="sxs-lookup"><span data-stu-id="09afc-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="09afc-111">[Les fonctions de recherche et de filtrage configurées](search-filter-index.md) dans les informations sur l’audience sont nécessaires pour que la recherche de données fonctionne.</span><span class="sxs-lookup"><span data-stu-id="09afc-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="09afc-112">Chaque contrôle de complément repose sur des données spécifiques dans les informations sur l’audience :</span><span class="sxs-lookup"><span data-stu-id="09afc-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="09afc-113">Contrôle de mesure : nécessite des [mesures configurées](measures.md).</span><span class="sxs-lookup"><span data-stu-id="09afc-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="09afc-114">Contrôle de l’intelligence : nécessite des données générées à l’aide de [prédictions](predictions.md) ou de [modèles personnalisés](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="09afc-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="09afc-115">Contrôle démographique : les champs démographiques (tels que l’âge ou le sexe) sont disponibles dans le profil client unifié.</span><span class="sxs-lookup"><span data-stu-id="09afc-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="09afc-116">Contrôle d’enrichissement : nécessite des [enrichissements](enrichment-hub.md) actifs appliqués aux profils clients.</span><span class="sxs-lookup"><span data-stu-id="09afc-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="09afc-117">Contrôle de chronologie : nécessite des [activités configurées](activities.md).</span><span class="sxs-lookup"><span data-stu-id="09afc-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="09afc-118">Installer le complément Fiche client</span><span class="sxs-lookup"><span data-stu-id="09afc-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="09afc-119">Le complément de carte client est une solution pour les applications Customer Engagement dans Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="09afc-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="09afc-120">Pour installer la solution, accédez à AppSource et recherchez **Carte client Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="09afc-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="09afc-121">Sélectionnez le [Complément Carte client sur AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) et sélectionnez **Obtenir maintenant**.</span><span class="sxs-lookup"><span data-stu-id="09afc-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="09afc-122">Vous devrez peut-être vous connecter avec vos informations d’identification d’administrateur à l’application Dynamics 365 pour installer la solution.</span><span class="sxs-lookup"><span data-stu-id="09afc-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="09afc-123">L’installation de la solution dans votre environnement peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="09afc-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="09afc-124">Configurer le complément Carte client</span><span class="sxs-lookup"><span data-stu-id="09afc-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="09afc-125">En tant qu’administrateur, accédez à la section **Paramètres** de Dynamics 365 et sélectionnez **Solutions**.</span><span class="sxs-lookup"><span data-stu-id="09afc-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="09afc-126">Sélectionnez le lien **Nom complet** pour la solution **Complément Carte client Dynamics 365 Customer Insights (préversion)**.</span><span class="sxs-lookup"><span data-stu-id="09afc-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="09afc-127">![Sélectionner le nom complet](media/select-display-name.png "Sélectionner le nom complet")</span><span class="sxs-lookup"><span data-stu-id="09afc-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="09afc-128">Sélectionnez **Se connecter** et entrez les identifiants du compte d’administrateur que vous utilisez pour configurer Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="09afc-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="09afc-129">Vérifiez que le bloqueur de fenêtres publicitaires de votre navigateur ne bloque pas la fenêtre d’authentification lorsque vous cliquez sur le bouton **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="09afc-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="09afc-130">Sélectionnez l’environnement Customer Insights à partir duquel vous souhaitez extraire des données.</span><span class="sxs-lookup"><span data-stu-id="09afc-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="09afc-131">Définissez le mappage de champ aux enregistrements dans l’application Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="09afc-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="09afc-132">En fonction de vos données dans Customer Insights, vous pouvez choisir de mapper les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="09afc-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="09afc-133">Pour effectuer un mappage avec un contact, sélectionnez le champ dans l’entité Client correspondant à l’ID de votre entité de contact.</span><span class="sxs-lookup"><span data-stu-id="09afc-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="09afc-134">Pour effectuer un mappage avec un compte, sélectionnez le champ dans l’entité Client correspondant à l’ID de votre entité de compte.</span><span class="sxs-lookup"><span data-stu-id="09afc-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="09afc-135">![Champ ID de contact](media/contact-id-field.png "Champ ID de contact")</span><span class="sxs-lookup"><span data-stu-id="09afc-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="09afc-136">Sélectionnez **Enregistrer la configuration** pour enregistrer les paramètres.</span><span class="sxs-lookup"><span data-stu-id="09afc-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="09afc-137">Ensuite, vous devez affecter des rôles de sécurité dans Dynamics 365 afin que les utilisateurs puissent personnaliser et afficher la carte client.</span><span class="sxs-lookup"><span data-stu-id="09afc-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="09afc-138">Dans Dynamics 365, accédez à **Paramètres** > **Sécurité** > **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="09afc-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="09afc-139">Sélectionnez les utilisateurs pour modifier les rôles d’utilisateur et sélectionnez **Gérer les rôles**.</span><span class="sxs-lookup"><span data-stu-id="09afc-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="09afc-140">Attribuez le rôle **Personnalisateur de carte Customer Insights** aux utilisateurs qui personnaliseront le contenu à afficher sur la carte pour l’ensemble de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="09afc-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="09afc-141">Ajouter des contrôles Carte client aux formulaires</span><span class="sxs-lookup"><span data-stu-id="09afc-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="09afc-142">Pour ajouter les contrôles Carte client à votre formulaire Contact, accédez à **Paramètres** > **Personnalisations** dans Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="09afc-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="09afc-143">Sélectionnez **Personnaliser le système**.</span><span class="sxs-lookup"><span data-stu-id="09afc-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="09afc-144">Accédez à l’entité **Contact**, développez-la, puis sélectionnez **Formulaires**.</span><span class="sxs-lookup"><span data-stu-id="09afc-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="09afc-145">Sélectionnez le formulaire de contact auquel vous souhaitez ajouter les contrôles Carte client.</span><span class="sxs-lookup"><span data-stu-id="09afc-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="09afc-146">![Sélectionner le formulaire Contact](media/contact-active-forms.png "Sélectionner le formulaire Contact")</span><span class="sxs-lookup"><span data-stu-id="09afc-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="09afc-147">Pour ajouter un contrôle, dans l’éditeur de formulaires, faites glisser un champ de l’**Explorateur de champs** vers l’emplacement où vous souhaitez faire apparaître le contrôle.</span><span class="sxs-lookup"><span data-stu-id="09afc-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="09afc-148">Sélectionnez le champ sur le formulaire que vous venez d’ajouter, puis sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="09afc-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="09afc-149">Accédez à l’onglet **Contrôles** et sélectionnez **Ajouter un contrôle**.</span><span class="sxs-lookup"><span data-stu-id="09afc-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="09afc-150">Choisissez l’un des contrôles personnalisés disponibles et sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="09afc-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="09afc-151">Dans la boîte de dialogue **Propriétés du champ**, désactivez la case à cocher **Afficher l’étiquette sur le formulaire**.</span><span class="sxs-lookup"><span data-stu-id="09afc-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="09afc-152">Sélectionnez l’option **Web** pour le contrôle.</span><span class="sxs-lookup"><span data-stu-id="09afc-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="09afc-153">Pour le contrôle d’enrichissement, sélectionnez le type d’enrichissement que vous souhaitez afficher en configurant le champ **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="09afc-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="09afc-154">Ajoutez un contrôle d’enrichissement distinct pour chaque type d’enrichissement.</span><span class="sxs-lookup"><span data-stu-id="09afc-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="09afc-155">Sélectionnez **Enregistrer** et **Publier** pour publier le formulaire de contact mis à jour.</span><span class="sxs-lookup"><span data-stu-id="09afc-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="09afc-156">Accédez au formulaire de contact publié.</span><span class="sxs-lookup"><span data-stu-id="09afc-156">Go to the published contact form.</span></span> <span data-ttu-id="09afc-157">Le nouveau contrôle ajouté s’affiche.</span><span class="sxs-lookup"><span data-stu-id="09afc-157">You'll see the newly added control.</span></span> <span data-ttu-id="09afc-158">Vous pouvez devoir vous connecter la première fois que vous l’utiliserez.</span><span class="sxs-lookup"><span data-stu-id="09afc-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="09afc-159">Pour personnaliser ce que vous souhaitez afficher sur le contrôle personnalisé, sélectionnez le bouton Modifier dans le coin supérieur droit.</span><span class="sxs-lookup"><span data-stu-id="09afc-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="09afc-160">Mettre à niveau le complément de carte client</span><span class="sxs-lookup"><span data-stu-id="09afc-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="09afc-161">Le complément de carte client ne se met pas à niveau automatiquement.</span><span class="sxs-lookup"><span data-stu-id="09afc-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="09afc-162">Pour mettre à niveau vers la dernière version, suivez cette procédure dans l’application Dynamics 365 sur laquelle le complément est installé.</span><span class="sxs-lookup"><span data-stu-id="09afc-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="09afc-163">Dans l’application Dynamics 365, accédez à **Paramètres** > **Personnalisation** et sélectionnez **Solutions**.</span><span class="sxs-lookup"><span data-stu-id="09afc-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="09afc-164">Dans le tableau des compléments, recherchez **CustomerInsightsCustomerCard** et sélectionnez la ligne.</span><span class="sxs-lookup"><span data-stu-id="09afc-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="09afc-165">Sélectionnez **Appliquer la mise à niveau de la solution** dans la barre d’action.</span><span class="sxs-lookup"><span data-stu-id="09afc-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Mettez à niveau la solution dans la zone de personnalisation des applications Dynamics 365":::

1. <span data-ttu-id="09afc-167">Après le démarrage du processus de mise à niveau, vous verrez un indicateur de chargement jusqu’à la fin de la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="09afc-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="09afc-168">S’il n’y a pas de version plus récente, la mise à niveau affichera un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="09afc-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
