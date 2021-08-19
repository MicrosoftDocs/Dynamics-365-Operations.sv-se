---
title: Kreditgrupper för kund
description: Det här avsnittet innehåller information om kundkreditgrupper.
author: mikefalkner
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 360f5114205e33f1288b766f525625bc8fe19a2aacc1db5e35f28a72937e97b9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6724001"
---
# <a name="customer-credit-groups"></a>Kreditgrupper för kund

[!include [banner](../includes/banner.md)]

Du kan definiera grupper av kunder som har en delad kreditgräns. Den individuella kreditgränsen som definieras på kundfakturakontot beaktas också.

Medlemmar i en kundkreditgrupp kan väljas från olika juridiska personer. När du lägger till en kund i listan med kunder i kundkreditgruppen ändras utgångsdatumet för kreditgränsen för varje kund till utgångsdatumet som tilldelas gruppen.

Du kan ställa in kundkreditgrupper på sidan **kundkreditgrupper** (**kredithantering \> kundkreditgrupper \> kundkreditgrupper**).

1. I fälten **Gruppnummer** och **Beskrivning** ande en identifierare och en beskrivning för gruppen.
2. I fälten **kreditgräns** och **valuta** anger du den kreditgräns och valuta som ska användas när systemet kontrollerar kreditgränsen för någon medlem i gruppen.
3. I fältet **kreditgräns till dagens datum** anger du det datum då kreditgränsen förfaller. Kundkreditgrupper måste ha utgångsdatum.

När du har ställt in en kundkreditgrupp kan du lägga till kunder i den genom att ange deras juridiska person och kundens konto-ID. När du lägger till en ny kund i en kundkreditgrupp söker systemet efter samma kundkonto i alla juridiska personer och ber dig lägga till det i kundkreditgruppen.

Använd menyn **Åldersfördelade saldon** om du vill visa information om åldersfördelade saldon för alla fakturakunder i en kundkreditgrupp. Sidan **Åldersfördelat saldo** visas en översikt över de åldersfördelade saldona för kundkontona för fakturor.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]