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
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 776c73b1a29666e393bed7c40059a578fe86cb0d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576194"
---
# <a name="transportation-management-miscellaneous-charges"></a>Transporthantering diverse avgifter

[!include [banner](../includes/banner.md)]

Som med alla andra avgifter måste transportgenererade avgifter associeras med en debiteringskod. Annars kommer de inte att läggas till i ordern som en tilläggsavgift. **Avgiftskoden** avgör hur tillägget redovisas i relation till ordern och order raden där den läggs till.

Gå till **Transporthantering > inställningar > klassificering > tillägg** för att definiera de kvalificerings kriterier som avgör när en viss **Avgiftskod** tillämpas på en debitering.

Du bör ha minst en inställning för varje relevant inställning för **Modulen avgifter** (*kund* och *leverantör*) där **Typen övriga avgifter** anges till *ingen*. Om detta saknas kommer tillägget *inte* att läggas till i ordern.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]