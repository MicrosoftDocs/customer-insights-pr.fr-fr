---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755541"
---
Après avoir ingéré les données, commencez le processus d’unification des données pour créer un profil client unifié. Pour plus d’informations, consultez [Unification des données](../data-unification.md).

### <a name="select-source-fields"></a>Sélectionner les champs source

1. Une fois les données ingérées, mappez les contacts des données d’eCommerce et du programme de fidélité aux types de données courants. Accédez à **Données** > **Unifier**.

1. Sélectionnez les entités qui représentent le profil client : **eCommerceContacts** et **loyCustomers**.

   ![Unifiez les sources de données d’eCommerce et du programme de fidélité.](../media/unify-ecommerce-loyalty.png)

1. Sélectionnez **ContactId** comme clé primaire pour **eCommerceContacts** et **LoyaltyID** comme clé primaire pour **loyCustomers**.

1. Cliquez sur **Suivant**. Ignorez les enregistrements en double et sélectionnez **Suivant**.

### <a name="match-conditions"></a>Conditions de correspondance

1. Choisissez **eCommerceContacts : eCommerce** comme entité principale et incluez tous les enregistrements.

1. Choisissez **loyCustomers : LoyaltyScheme** et incluez tous les enregistrements.

1. Ajoutez une règle :
   - Sélectionnez **FullName** pour eCommerceContacts et loyCustomers.
   - Sélectionnez **Type (Téléphone, Nom, Adresse, ...)** pour **Normaliser**.
   - Définissez le **Niveau de précision** sur **Base** et la **Valeur** sur **Élevé**.
   - Entrez **FullName, Email** pour le nom.

1. Ajoutez une deuxième condition pour l’adresse e-mail :
   - Sélectionnez **Email** pour eCommerceContacts et loyCustomers.
   - Laissez le champ Normaliser vide.
   - Définissez le **Niveau de précision** sur **Base** et la **Valeur** sur **Élevé**.

   ![Unifiez la règle de mise en correspondance pour le nom et l’adresse e-mail.](../media/unify-match-rule.png)

1. Cliquez sur **Terminé**.

1. Cliquez sur **Suivant**.

### <a name="unify-fields"></a>Unifier les champs

1. Remplacez le nom du **ContactId** pour l’entité **loyCustomers** par **ContactIdLOYALTY** pour le différencier des autres identifiants ingérés.

1. Sélectionnez **Suivant** pour vérifier, puis sélectionnez **Créer des profils clients**.
