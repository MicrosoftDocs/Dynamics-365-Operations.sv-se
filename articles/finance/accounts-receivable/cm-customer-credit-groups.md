---
title: Kreditgrupper för kund
description: Det här avsnittet innehåller information om kundkreditgrupper.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: f7121b78f3318bae9f82b2f0f951bc7bfe6c4358
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015401"
---
# <a name="customer-credit-groups"></a>Kreditgrupper för kund

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Du kan definiera grupper av kunder som har samma kreditgräns. Den individuella kreditgränsen som definieras på kundfakturakontot beaktas också.

Medlemmar i en kundkreditgrupp kan väljas från olika juridiska personer. När du lägger till en kund i listan med kunder i kundkreditgruppen ändras utgångsdatumet för kreditgränsen för varje kund till utgångsdatumet som tilldelas gruppen.

Du kan ställa in kundkreditgrupper på sidan **kundkreditgrupper** (**kredithantering \> kundkreditgrupper \> kundkreditgrupper**).

1. I fälten **Gruppnummer** och **Beskrivning** ande en identifierare och en beskrivning för gruppen.
2. I fälten **kreditgräns** och **valuta** anger du den kreditgräns och valuta som ska användas när systemet kontrollerar kreditgränsen för någon medlem i gruppen.
3. I fältet **kreditgräns till dagens datum** anger du det datum då kreditgränsen förfaller. Kundkreditgrupper måste ha utgångsdatum.

När du har ställt in en kundkreditgrupp kan du lägga till kunder i den genom att ange deras juridiska person och kundens konto-ID. När du lägger till en ny kund i en kundkreditgrupp söker systemet efter samma kundkonto i alla juridiska personer och ber dig lägga till det i kundkreditgruppen.

Använd menyn **Åldersfördelade saldon** om du vill visa information om åldersfördelade saldon för alla fakturakunder i en kundkreditgrupp. Sidan **Åldersfördelat saldo** visas en översikt över de åldersfördelade saldona för kundkontona för fakturor.
