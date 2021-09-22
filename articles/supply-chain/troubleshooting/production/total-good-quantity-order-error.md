---
title: Fel på totalt godkänt antal vid försök att avsluta en order
description: När du försöker avsluta en produktionsorder och rapportera som färdig kan du få felet för totalt godkänt antal. På den här sidan beskrivs varför och hur du åtgärdar problemet.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5f0c2c2ca64ada9d72c0ebd04e7de561aaa52039
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477622"
---
# <a name="total-good-quantity-error-when-trying-to-end-a-production-order"></a>Fel på totalt godkänt antal vid försök att avsluta en produktionsorder

## <a name="symptoms"></a>Symtom

När du försöker att bokföra en rapport som färdig journal på en tillverkningsorder visas följande felmeddelande:

> Totalt godkänt antal rapporterat som färdigt för produktionen blir %1. Återrapportering för den senaste operationen är 0,00 sammanlagt.

## <a name="cause"></a>Orsak

Det här problemet uppstår om kvantiteterna som har bokförts i de senaste operationerna var felaktiga. Om till exempel produktionen startas men den kvantitet som ska startas inte fördelas, bokförs flödeskortjournalen utan några rader. Du bekräftar situationen genom att öppna tillverkningsordern och sedan välja fliken **Vy** och **flödeskort** i åtgärdsfönstret.

## <a name="resolution"></a>Lösning

Du kan lösa det här problemet genom att bokföra ytterligare journaler för de operationer som journalerna inte kunde bokföras för. Starta om produktionsordern och välj att bokföra ytterligare journaler. Den här åtgärden startar inte tillverkningsordern, utan då bokförs journalerna. Flödeskortet ska sedan visa de kvantiteter som bokfördes och du bör kunna avsluta tillverkningsorder.
