---
title: Transporthantering diverse avgifter
description: Det här ämnet förklarar hur transportgenererade avgifter måste associeras med en debiteringskod.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 2b703d770c7f9ea684716368cf1e7dbe5fec8710
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2020
ms.locfileid: "4438138"
---
# <a name="transportation-management-miscellaneous-charges"></a>Transporthantering diverse avgifter

[!include [banner](../includes/banner.md)]

Som med alla andra avgifter måste transportgenererade avgifter associeras med en debiteringskod. Annars kommer de inte att läggas till i ordern som en tilläggsavgift. **Avgiftskoden** avgör hur tillägget redovisas i relation till ordern och order raden där den läggs till.

Gå till **Transporthantering > inställningar > klassificering > tillägg** för att definiera de kvalificerings kriterier som avgör när en viss **Avgiftskod** tillämpas på en debitering.

Du bör ha minst en inställning för varje relevant inställning för **Modulen avgifter** (*kund* och *leverantör*) där **Typen övriga avgifter** anges till *ingen*. Om detta saknas kommer tillägget *inte* att läggas till i ordern.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]