---
title: Transporthantering diverse avgifter
description: Denna artikel förklarar hur transportgenererade avgifter måste associeras med en debiteringskod.
author: Weijiesa
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 8cc4c595d8b61cb9b6c81af4bf7f03faa1a12960
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849225"
---
# <a name="transportation-management-miscellaneous-charges"></a>Transporthantering diverse avgifter

[!include [banner](../includes/banner.md)]

Som med alla andra avgifter måste transportgenererade avgifter associeras med en debiteringskod. Annars kommer de inte att läggas till i ordern som en tilläggsavgift. **Avgiftskoden** avgör hur tillägget redovisas i relation till ordern och order raden där den läggs till.

Gå till **Transporthantering > inställningar > klassificering > tillägg** för att definiera de kvalificerings kriterier som avgör när en viss **Avgiftskod** tillämpas på en debitering.

Du bör ha minst en inställning för varje relevant inställning för **Modulen avgifter** (*kund* och *leverantör*) där **Typen övriga avgifter** anges till *ingen*. Om detta saknas kommer tillägget *inte* att läggas till i ordern.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]