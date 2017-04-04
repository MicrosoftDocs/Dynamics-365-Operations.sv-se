---
title: "Återföra en leverantörsbetalning"
description: "Den här artikeln beskriver skillnaderna mellan att återföra, ta bort, annullera och avvisa en betalning. Den beskriver dessutom de två metoderna för att återföra en leverantörscheck."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankChequeTable, LedgerJournalTransBankChequeReversal, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14361
ms.assetid: 9f0a1883-cbe0-4cc7-b9f3-dd12fb85ebe8
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: 716134b2230683050b234297e475d9331fbc7dab
ms.lasthandoff: 03/31/2017


---

# <a name="reverse-a-vendor-payment"></a>Återföra en leverantörsbetalning

Den här artikeln beskriver skillnaderna mellan att återföra, ta bort, annullera och avvisa en betalning. Den beskriver dessutom de två metoderna för att återföra en leverantörscheck. 

Ibland efter att en leverantörsbetalning har bokförts, måste betalningen återföras. Återföringen skiljer sig från att vill ta bort, annullera eller avvisa en betalning. Du kan bara ta bort en betalning, om dess status är **Skapad**. Denna status anger att betalningen har skapats men ännu inte har skapats. Denna begränsning alltid gäller oavsett betalningsmetoden. Du kan annullera ej bokförda checkar när har skapats men ännu inte har bokförts. Om genereras betalningen görs som en fond för elektronisk överföring kan avvisa du betalning innan den bokförs. Avvisa en betalning genom att ändra den **betalningsstatus** värde. En betalning som annullerade eller avvisade genereras efter den **betalningsstatus** värdet ändras tillbaka till **ingen**. 

När en betalning bokförs används återföringar. Betalningar som görs elektroniskt kan inte ångras när de har bokförts. I stället måste du skapa en ny transaktion för betalning till skulden få tillbaka på leverantörens konto. Det finns två metoder för återföring av bokförda checkar. I en metod bokförs återföringar direkt när du klickar på **Betalningsåterföring** på sidan **Check**. I den metoden skickas återföringen när du klickar på **Betalningsåterföring** på sidan **Check** först till checkåterföringsjournalen i Kassa och bankhantering, där en granskare kan bokföra eller avvisa återföringen. 

Om du vill veta vilken metod som din organisation använder, se sidan **Parametrar för kassa- och bankhantering** . Om alternativet **Använd granskningsprocess för betalningsåterföringar** anges till **Ja**, skickas återföringarna till checkåterföringsjournalen för granskning. I följande tabell finns beskrivningar av hur checkåterföringsmetoderna skiljer sig åt.

| Om din organisation inte granskar checkåterföringar före bokföring                                                                                                                                  | Om din organisation granskar checkåterföringar före bokföring                                                                                                                                                                                                                                                                                                                                                                     |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Checken återförs omedelbart när du klickar på **OK** på sidan **Check**.                                                                                                                      | Checken återförs inte direkt. En checkåterföringsjournal skapas för granskning. Om checkåterföringsjournalen tas bort kan checken återföras igen.                                                                                                                                                                                                                                                                |
| Redovisningposterna för den ursprungliga checken återförs.                                                                                                                                         | Redovisningskontot från den ursprungliga checkens redovisningpost kan inte bokföras. De ekonomiska dimensionerna från den ursprungliga checkens journal används som ekonomiska standarddimensioner i checkåterföringsjournalen. Du kan ändra dessa standardvärden. När checkåterföringjournalen bokförs, anges huvudkontona för leverantörsreskontra automatiskt från de bokföringsprofiler som kan ha ändrats. |
| De redovisningstrukturer som användes när den ursprungliga checken bokfördes används för att återföra checken, även om kontostrukturen har ändrats. Kontokombinationen är inte validerad. | Om en kontostruktur ändras efter att den ursprungliga checken bokfördes kan en ny ekonomisk dimension krävas för återföringen av checken. Denna ekonomiska dimension kan inte anges automatiskt från den ursprungliga betalningens journal. Kontokombinationen valideras när checkåterföringen bokförs.                                                                                                        |
| Fasta dimensioner används inte för återföringen, för att garantera att samma redovisningskonton återförs.                                                                                      | Fasta dimensioner används på checkåterföringsjournalen under bokföringen. Värdet för ekonomisk dimension kanske inte finns i redovisningposten för den ursprungliga checken, beroende på när den fasta dimensionen definierades.                                                                                                                                                                                                     |

## <a name="reverse-posted-checks-without-reviewing-them"></a>Återför bokförda checkar utan att granska dem
Om din organisation vill bokföra checkåterföringar, omedelbart när du klickar på **Betalningsåterföring** på sidan **Checkar**. På sidan **Parametrar för kassa- och bankhantering** anger du alternativet **Använd granskningsprocessen för betalningsåterföringar** till **Nej**. På sidan **Checkar** kan du markera den här kryssrutan om du vill återföra och välj sedan **Betalningsåterföring**. Du kan sedan ange datumet och ett skäl till återföringen.

## <a name="reverse-posted-checks-after-they-are-reviewed-in-the-check-reversal-journal"></a>Återför bokförda checkar efter att de har granskats i checkåterföringsjournalen
Om din organisation vill granska checkåterföringar innan de bokförs, skapar du en checkåterföringjournal för granskning och på sidan **Parametrar för kassa- och bankhantering** anger du alternativet **Använd granskningsprocess för betalningsåterföringar** till **Ja**. På sidan **Checkar** kan du markera den här kryssrutan om du vill återföra och välj sedan **Betalningsåterföring**. Du kan sedan ange datumet och ett skäl till återföringen. Du måste även välja ett journalnamn för att skapa en journal i checkåterföringsjournalen.

### <a name="review-a-reversal"></a>Granska en återföring

Om du är en användare som måste granska återföringar, kan du antingen godkänna och bokföra journalen eller avvisa återföringen genom att ta bort journalen. På sidan **Checkåterföringjournal** kan du välja den återföringsjournal som du vill granska och klicka sedan på **Rader** Du kan granska den återförda checken och sedan välja ett av följande godkännandealternativ:

-   Godkänn och bokför återföringsjournalen genom att klicka på **Bokföra** eller **Bokföra och överföra**.
-   Om du vill avslå en återföring tar du bort checkåterföringsjournalen.

> [!NOTE]
> Om du tar bort journalen kan återföringen bort från systemet, men den ursprungliga checken finns kvar i den **Kontrollera** sida. Checken har då inte längre **Väntar på annullering**.

## <a name="results-of-posting-a-reversal"></a>Resultat av bokföring av en återföring
När du bokför en checkåterföring händer följande:

-   Checkens status uppdateras till **Annullering**.
-   Om alternativet **Stämma av** valdes på återföringsidan under återföringen, stäms checken av (alternativet **Avstämd** markeras) och visas inte på sidan **Kontoavstämning**.
-   Återföringsverifikationen bokförs mot det bankkonto som checken utfärdades från, för att öka bankkontots saldo.
-   Verifikationen bokförs till redovisningen.
-   Ändringsdetaljerna uppdateras i fältgruppen **Historik** på sidan **Check**.

> [!NOTE] 
> När du återför en check som utfärdats för en koncernintern handelstransaktion, kommer motbokningsposterna från de koncerninterna redovisningsinställningarna, inte från den ursprungliga transaktionen. Om checken som återfördes utfärdades för en leverantörsbetalning inträffar även följande:

-   Den ursprungliga betalningen från fakturan som betalningen kvittades mot dras tillbaka (kvittningen återförs).
-   En transaktion bokförs mot leverantörskontot för betalningsåterföringen och den återförda betalningen kvittas mot den ursprungliga betalningen. Fältet **Senaste kvittningsverifikation** på sidan **Leverantörstransaktioner** för den ursprungliga leverantörsutbetalningen uppdateras för att avspegla verifikationsnumret för den återförda transaktionen.

Om checken som återfördes utfärdades för en kundåterbetalning inträffar även följande:

-   En transaktion bokförs mot kundkontot för betalningsåterföringen och kvittningen mellan den ursprungliga betalningen och dokumentet som betalningen ursprungligen kvittades mot återförs (en negativ betalning skapas).
-   En betalningsåterföring tillämpas på den ursprungliga betalningen. Fältet **Senaste kvittningsverifikation** på sidan **Kundtransaktioner** för den ursprungliga kundutbetalningen uppdateras för att avspegla verifikationsnumret för den återförda transaktionen.



