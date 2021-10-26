---
title: Créer un lien entre les informations sur l’audience et les informations sur l’engagement
description: Créez un lien actif entre les informations sur l’audience et les informations sur l’engagement pour activer le partage bidirectionnel des données.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: db38778c0da862e119f9b374e07c82ead0d3a4f2
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645579"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Créer un lien entre les informations sur l’audience et les informations sur l’engagement

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

L’intégration entre les informations sur l’engagement et les informations sur l’audience lie les environnements des deux fonctionnalités et active le partage bidirectionnel des données entre eux.

Utilisez les profils unifiés et les segments des informations sur l’audience pour obtenir plus d’options d’analyse dans les informations sur l’engagement. Exportez les événements à forte valeur commerciale à partir des informations sur l’engagement. Utilisez ces événements pour ajouter des données aux profils unifiés dans les informations sur l’audience.

## <a name="prerequisites"></a>Conditions préalables

- Les profils d’informations sur l’audience doivent être stockés sur un compte Azure Data Lake Storage personnel ou dans un lac de données [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)&ndash;géré. 
- Votre environnement d’informations sur l’audience doit être associé à un environnement Dataverse. Et si cet environnement utilise également Dataverse pour le stockage des données, assurez-vous de cocher l’option **Activer le partage de données** dans les informations sur l’audience. Pour plus d’informations, consultez [Créer et configurer un environnement dans des insights d’audience](../audience-insights/create-environment.md).
- Vous avez besoin des autorisations d’administrateur pour les environnements d’informations sur l’engagement et des informations sur l’audience.
- Les environnements liés doivent être situés dans la même région géographique.

> [!NOTE]
> - Si votre abonnement aux informations sur l’audience est un essai, qui utilise un lac de données des informations sur l’audience géré en interne, contactez [pirequest@microsoft.com](mailto:pirequest@microsoft.com) pour obtenir de l’aide. 
> - Si votre environnement d’informations sur l’audience utilise votre compte personnel Azure Data Lake Storage pour stocker les données, vous devez ajouter un principal de service Azure des informations sur l’engagement à votre compte de stockage. Pour plus de détails, accédez à [Se connecter à un compte Azure Data Lake Storage avec un principal de service Azure pour les informations sur l’audience](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Créer un lien d’environnement

Créez un lien d’environnement en mettant à jour les paramètres **Administrateur** > **Environnement** dans les informations sur l’engagement.

**Pour créer un lien actif entre les informations sur l’audience et les informations sur l’engagement**

1. Dans la page **Administrateur de l’environnement**, sélectionnez l’onglet **Lier les environnements**.

    :::image type="content" source="media/integrate1.png" alt-text="Configurez un environnement.":::

1. Sélectionnez **Configurer les environnements** dans le coin supérieur gauche ou en bas de l’écran.

     :::image type="content" source="media/integrate2.png" alt-text="Sélectionnez un environnement d’informations sur l’audience.":::

1. Sélectionnez un environnement d’informations sur l’audience, puis sélectionnez ***Suivant** pour terminer. Vous pouvez maintenant sélectionner des fonctionnalités facultatives pour les environnements liés.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Activer les attributs et les segments des profils unifiés des informations sur l’audience

Après avoir lié les environnements, vous pouvez sélectionner les fonctionnalités facultatives des environnements liés. Ces fonctionnalités activent les attributs et les segments des profils unifiés à partir des informations sur l’audience pour l’analyse interactive des données client.

> [!IMPORTANT]
> Pour que les segments des informations sur l’audience apparaissent dans les informations sur l’engagement, vous devez d’abord [exécuter les processus de fusion et en aval](../audience-insights/merge-entities.md). Les processus en aval sont importants car ils génèrent un tableau unique qui prépare les segments des informations sur l’audience à partager avec les informations sur l’engagement. (Si une actualisation du système est planifiée, elle inclut automatiquement les processus en aval.)

**Pour analyser les données web dans les informations sur l’engagement**

1. Dans la page **Administrateur de l’environnement**, activez l’option **Partager les données des informations sur l’audience avec les informations sur l’engagement**, puis sélectionnez **Suivant**.

    :::image type="content" source="media/integrate4.png" alt-text="Sélectionnez les fonctionnalités.":::

1. Sélectionnez les attributs des profils unifiés qui deviendront des dimensions dans les informations sur l’engagement. (Tous les attributs ne sont pas des dimensions utiles. Par exemple, il est peu probable que vous ayez besoin des attributs **Prénom** ou **Nom** pour l’analyse des événements de votre site web.)

    :::image type="content" source="media/integrate5.png" alt-text="Organisez les dimensions.":::

   >[!NOTE]
   > Tous les attributs des profils des informations sur l’audience qui représentent des identifiants (comme **ID** et **ID secondaire**) sont retirés des attributs disponibles et deviennent des dimensions dans les informations sur l’engagement.

1. Une fois la sélection des attributs terminée, cliquez sur **Suivant**.
1. Ajoutez les utilisateurs qui peuvent afficher les dimensions et les segments des profils des informations sur l’audience dans les informations sur l’engagement.

    :::image type="content" source="media/integrate6.png" alt-text="Gérez l’accès aux données client.":::

   > [!IMPORTANT]
   > Si vous n’ajoutez pas explicitement des utilisateurs lors de cette étape, les données sont masquées aux utilisateurs dans les informations sur l’engagement.
   > Pour que les segments des informations sur l’audience apparaissent dans les informations sur l’engagement, vous devez d’abord [exécuter les processus de fusion et en aval](../audience-insights/merge-entities.md). Les processus en aval sont importants car ils génèrent un tableau unique qui prépare les segments des informations sur l’audience à partager avec les informations sur l’engagement. (Si une actualisation du système est planifiée, elle inclut automatiquement les processus en aval.)

1. Vérifiez votre sélection, puis cliquez sur **Terminer**.

    :::image type="content" source="media/integrate7.png" alt-text="Vérifiez les paramètres des données client.":::

## <a name="export-refined-events-to-audience-insights"></a>Exporter les événements affinés dans les informations sur l’audience

Après avoir créé un lien entre les environnements, vous pouvez exporter des événements affinés des informations sur l’engagement vers les informations sur l’audience et les ingérer en tant que nouvelle source de données. 

Pour plus d’informations, accédez à [Intégrer les données web des informations sur l’engagement avec les informations sur l’audience](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
