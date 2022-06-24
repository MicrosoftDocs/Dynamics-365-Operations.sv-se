---
title: Kreditgrupper för kund
description: Den här artikeln innehåller information om kundkreditgrupper.
author: JodiChristiansen
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 032e92431946f0a41bf2e52c155e422d4ea0b3b7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886528"
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
