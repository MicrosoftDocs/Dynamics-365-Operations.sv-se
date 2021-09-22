---
title: Momsinformation uppdateras inte om försäljningsorderns plats ändras
description: Om platsen, lagerstället eller leveransadressen ändras i ett försäljningsorderhuvud uppdateras inte ärendets momsinformation på raderna. Du måste göra detta manuellt.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 77a73a787ff8a174c575f3b4f75694ded45d5712
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477636"
---
# <a name="tax-information-isnt-updated-if-location-on-a-sales-order-header-is-changed"></a>Momsinformation uppdateras inte om plats i ett försäljningsorderhuvud ändras

## <a name="symptoms"></a>Symtom

Om platsen, lagerstället eller leveransadressen ändras i ett försäljningsorderhuvud uppdateras inte ärendets momsinformation på raderna.

## <a name="resolution"></a>Lösning

Detta beteende är av design. Problemet beror på att leveransadressen, platsen och lagerstället inte ändras automatiskt på radnivå. Du måste uppdatera dem manuellt.
