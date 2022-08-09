---
title: Exporter des données vers Salesforce Marketing Cloud (version préliminaire)
description: Apprenez à configurer la connexion et à exporter vers Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197035"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Exporter des données vers Salesforce Marketing Cloud (version préliminaire)

Utilisez les données de vos clients dans Salesforce Marketing Cloud en les exportant via un emplacement SFTP (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Conditions préalables

- Un [hôte SFTP pour Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) et les informations d’identification d’administrateur correspondantes.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Configurer la connexion à Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Accédez à **Administrateur** > **Connexions**.

1. Sélectionnez **Ajouter une connexion** et choisissez **Salesforce Marketing Cloud**.

1. Donnez à votre connexion un nom reconnaissable dans le champ **Nom d’affichage**. Le nom et le type de connexion décrivent cette connexion. Nous vous recommandons de choisir un nom qui explique l’objectif et la cible de la connexion.

1. Choisissez qui peut utiliser cette connexion. Par défaut, il s’agit uniquement des administrateurs. Pour plus d’informations, voir [Autoriser les contributeurs à utiliser une connexion pour les exportations](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Fournissez un **Nom d’utilisateur**, **Mot de passe**, **Nom d’hôte** et **dossier Exportation** pour votre compte SFTP.

1. Sélectionnez **Vérifier** pour tester la connexion.

1. Passez en revue la [confidentialité et conformité des données](connections.md#data-privacy-and-compliance) et sélectionnez **J’accepte**.

1. Sélectionnez **Enregistrer** pour terminer la connexion.

## <a name="configure-an-export"></a>Configurer une exportation

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Accédez à **Données** > **Exportations**.

1. Sélectionnez **Ajouter une exportation**.

1. Dans le champ **Connexion pour l’exportation**, choisissez une connexion dans la section SFTP. Contactez un administrateur si aucune connexion n’est disponible.

1. Entrez un nom pour l’exportation.

1. Choisissez si vous souhaitez exporter vos données **compressées** ou **décompressées** et le **délimiteur de champ** pour les fichiers exportés.

1. Sélectionnez les entités, par exemple des segments, à exporter.

   > [!NOTE]
   > Chaque entité sélectionnée sera fractionnée en un maximum de cinq fichiers de sortie au maximum lors de l’exportation.

1. Cliquez sur **Enregistrer**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importer les données Customer Insights d’un emplacement SFTP vers Salesforce Marketing Cloud

1. Créez des [extensions de données dans Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) pour importer le fichier de données Customer Insights à partir de l’emplacement SFTP.

2. [Importez les données de l’emplacement SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) dans l’extension de données Salesforce Marketing Cloud.

3. Configurez l’automatisation pour importer les données dans les extensions de données. En savoir plus sur les [automatisations de dépôt de fichier et les automatisations planifiées](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Définissez une [automatisation de dépôt de fichier](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ou une [automatisation planifiée](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Voici un exemple d’[automatisation avec SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
