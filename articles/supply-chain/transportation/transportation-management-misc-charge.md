---
title: Transporthantering diverse avgifter
description: Det här ämnet förklarar hur transportgenererade avgifter måste associeras med en debiteringskod.
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 53c25f204e98a911e9697f5bb950706555749a55
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828332"
---
# <a name="transportation-management-miscellaneous-charges"></a>Transporthantering diverse avgifter

[!include [banner](../includes/banner.md)]

Som med alla andra avgifter måste transportgenererade avgifter associeras med en debiteringskod. Annars kommer de inte att läggas till i ordern som en tilläggsavgift. **Avgiftskoden** avgör hur tillägget redovisas i relation till ordern och order raden där den läggs till.

Gå till **Transporthantering > inställningar > klassificering > tillägg** för att definiera de kvalificerings kriterier som avgör när en viss **Avgiftskod** tillämpas på en debitering.

Du bör ha minst en inställning för varje relevant inställning för **Modulen avgifter** (*kund* och *leverantör*) där **Typen övriga avgifter** anges till *ingen*. Om detta saknas kommer tillägget *inte* att läggas till i ordern.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]