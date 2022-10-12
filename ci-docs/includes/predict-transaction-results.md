---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611100"
---
- **Performances du modèle de formation** : les notes A, B et C indiquent les performances de la prédiction et peuvent vous aider à prendre la décision d’utiliser les résultats stockés dans l’entité de sortie.

  Les notes sont calculées selon les règles suivantes :
  - **A** lorsque le modèle a prédit avec précision au moins 50 % des prédictions totales et que le pourcentage de prédictions précises pour les clients perdus est supérieur d’au moins 10 % au taux de référence.
  - **B** lorsque le modèle a prédit avec précision au moins 50 % des prédictions totales et que le pourcentage de prédictions précises pour les clients perdus est jusqu’à 10 % supérieur au taux de référence.
  - **C** lorsque le modèle a prédit avec précision moins de 50 % des prédictions totales ou que le pourcentage de prédictions précises pour les clients perdus est inférieur au taux de référence.
  - **Référence** prend l’entrée de l’intervalle de temps de prédiction pour le modèle (par exemple, un an) et crée différentes fractions de temps en le divisant par 2 jusqu’à ce qu’il atteigne un mois ou moins. Il utilise ces fractions pour créer une règle métier pour les clients qui n’ont pas effectué d’achats sur cette période. Ces clients sont considérés comme perdus. La règle métier basée sur le temps ayant la plus grande capacité à prédire qui présente un risque d’attrition est choisie comme modèle de référence.

- **Probabilité d’attrition (nombre de clients)**  : Groupes de clients en fonction du risque d’attrition prévu. Vous pouvez éventuellement [créer des segments de clients](../prediction-based-segment.md) avec un risque de désabonnement élevé. Ces segments aident à comprendre où doit se situer votre limite pour l’appartenance à un segment.

- **Facteurs les plus influents** : De nombreux facteurs sont pris en compte lors de la création de votre prédiction. Chacun des facteurs a son importance calculée pour les prédictions regroupées créées par un modèle. Utilisez ces facteurs pour valider les résultats de votre prédiction. Ou bien, utilisez ces informations ultérieurement pour [créer des segments](../prediction-based-segment.md) qui pourraient contribuer à influer sur le risque de désabonnement des clients.