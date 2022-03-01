---
title: Exporter les données Customer Insights vers Salesforce Marketing Cloud
description: Apprenez à configurer la connexion et à exporter vers Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8ce243918c2388e931a98df3bbe576ddf692f707
ms.sourcegitcommit: 4823684a1399fd66ffecfce21735f2bc90a1733c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/23/2021
ms.locfileid: "6660264"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Exporter des segments et d’autres données vers Salesforce Marketing Cloud (version préliminaire)

Utilisez les données de vos clients dans Salesforce Marketing Cloud en les exportant via un emplacement SFTP (Secure File Transfer Protocol).

## <a name="prerequisites-for-connection"></a>Conditions préalables à une connexion

- Disponibilité d’un hôte SFTP et des informations d’identification administrateur correspondantes. [Comment configurer des emplacements SFTP pour Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Configurer la connexion à Salesforce Marketing Cloud

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Salesforce Marketing Cloud** pour configurer la connexion.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Si vous n’effectuez aucune action, la valeur par défaut sera Administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Fournissez un **Nom d’utilisateur**, **Mot de passe**, **Nom d’hôte** et **dossier Exportation** pour votre compte SFTP.

1. Sélectionnez **Vérifier** pour tester la connexion.

1. Sélectionnez **J’accepte** de confirmer la **Confidentialité et conformité des données**.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

Vous pouvez configurer cette exportation si vous avez accès à une connexion de ce type. Pour plus d’informations, voir [Autorisations nécessaires pour configurer une exportation](export-destinations.md#set-up-a-new-export).

1. Accédez à **Données** > **Exportations**.

1. Pour créer une nouvelle exportation, sélectionnez **Ajouter une destination**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section SFTP. Si ce nom de section ne s’affiche pas, cela signifie qu’aucune connexion de ce type n’est disponible.

1. Choisissez si vous souhaitez exporter vos données **compressées** ou **décompressées** et le **délimiteur de champ** pour les fichiers exportés.

1. Sélectionnez les entités, par exemple des segments, à exporter.

   > [!NOTE]
   > Chaque entité sélectionnée sera fractionnée en cinq fichiers de sortie au maximum lors de l’exportation. 

1. Sélectionnez **Enregistrer**.

L’enregistrement d’une exportation n’exécute pas l’exportation immédiatement.

L’exportation s’exécute avec chaque [actualisation planifiée](system.md#schedule-tab). Vous pouvez également [exporter des données à la demande](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importer les données Customer Insights d’un emplacement SFTP vers Salesforce Marketing Cloud

1. Créez des [extensions de données dans Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) pour importer le fichier de données Customer Insights à partir de l’emplacement SFTP.

2. [Importez les données de l’emplacement SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) dans l’extension de données Salesforce Marketing Cloud. 

3. Configurez l’automatisation pour importer les données dans les extensions de données. En savoir plus sur les [automatisations de dépôt de fichier et les automatisations planifiées](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Définissez une [automatisation de dépôt de fichier](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ou une [automatisation planifiée](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Voici un exemple d’[automatisation avec SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Confidentialité et conformité des données

Lorsque vous activez Dynamics 365 Customer Insights pour transmettre des données via SFTP, vous autorisez le transfert de données en dehors de la limite de conformité de Dynamics 365 Customer Insights, notamment des données potentiellement sensibles, telles que des données personnelles. Microsoft transférera ces données selon vos instructions, mais vous êtes tenu de vous assurer que la destination d’exportation respecte les obligations de confidentialité ou de sécurité qui vous incombent. Pour plus d’informations, consultez [Déclaration de confidentialité Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Votre administrateur Dynamics 365 Customer Insights peut supprimer cette destination d’exportation à tout moment pour interrompre l’utilisation de cette fonctionnalité.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
