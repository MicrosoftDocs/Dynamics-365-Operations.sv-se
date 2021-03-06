---
title: Ändra Leveranssätt i POS
description: I det här avsnittet beskrivs hur du konfigurerar och använder ändringsläget för leverans i POS.
author: hhainesms
ms.date: 03/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: fd69d82536047c06e94ba4a7e860ef54680619a4
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193141"
---
# <a name="change-mode-of-delivery-in-pos"></a>Ändra Leveranssätt i POS

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in och använder funktionen "ändra leveranssätt" i ditt försäljnings- eller kassamiljöläge. 

I Dynamics 365 Commerce versioner 10.0.10 och senare är åtgärden **Byt leveranssätt** (647) tillgänglig för att läggas till i dina layouter för kassaskärm.

Funktionen ändra leveranssätt ger dig möjlighet att ändra leveranssättet för en eller flera försändelse konfigurerade försäljningsrader i kassatransaktionen. I tidigare versions versioner av Commerce var du tvungen att gå igenom hela konfigurationsflöden **Leverera allt** eller **Leverera utvalda** om du vill ändra leveranssättet på en befintlig rad som har konfigurerats för leverans. Den här processen tar lång tid och skulle kunna leda till att den ursprungliga leveransdagen eller leveransdatumen ändras av raden. Den nya funktionen ger en alternativ metod för att effektivt uppdatera leveranssättet på dessa försäljningsrader.

Mer information om hur du lägger till en operation i en knapp på kassaknappens rutnät finns it [Skärmlayouter för POS](pos-screen-layouts.md).

När den här funktionen har konfigurerats i POS när du väljer **Ändra leverans** visas en listsida där du kan välja rader för den transaktion som du vill ändra leveranssättet för. Du kan välja några eller alla av raderna eller avsluta utan att göra några ändringar. De försäljningsrader som tidigare konfigurerades för leverans är de enda raderna i listan som du kan ändra. Om du vill ändra en rad som är avsedd för upphämtning eller utföra leverans, måste du använda operationen **leverera alla** eller **leverera utvalda**. Om du vill ändra en rad som angivits som en försändelse till en upphämtning eller utför måste du använda åtgärderna **upphämta**, **upphämtning vald**, **Utför alla** eller **Utför valda**.

När du har valt de rader som du vill ändra klickar du på **Ändra leveranssätt** för att uppmanas att välja alternativ för leveranssätt. Om du har valt flera rader att ändra, visar POS endast leveranssätt som har konfigurerats som tillåtna för alla valda produkter. Leveranssätten kan konfigureras till att stödja specifika produkter och leveransadresser. Om det finns ett leveranssätt som är acceptabelt för en produkt- och adresskombination, men inte accepteras för någon annan produkt- och adresskombination, är leveranssättet inte tillgängligt. Du kan behöva välja rader en och en och ändra leveranssättet för varje rad separat om du vill välja ett leveranssätt för en produkt som inte stöds av en annan produkt.  

När du har valt det nya leveranssättet visas transaktionssidan. Om du vill granska dina nya val för leveranssätt väljer du **leverans** i transaktionslistan.

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa kundtjänstorder](tasks/create-call-center-orders.md)

[Anpassa transaktionsmeddelanden via e-post efter leveranssätt](customize-email-delivery-mode.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]