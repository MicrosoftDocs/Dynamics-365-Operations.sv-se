---
title: Ögonblicksbild av åldersfördelningen för kunder
description: Den här artikeln innehåller information om ögonblicksbilder av kunders åldersfördelning. En ögonblicksbild av åldersfördelning beräknar åldersfördelningssaldon för en grupp av kunder vid en viss tidpunkt.
author: JodiChristiansen
ms.date: 10/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2021-05-05
ms.dyn365.ops.version: 10.0.17
ms.search.form: ''
ms.openlocfilehash: e4ccc8ac9b5374ca0713167a17b8704727c687fd
ms.sourcegitcommit: 9740f9b41a7dcf1821c6baccb2e05b9865ac2966
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/15/2022
ms.locfileid: "9775252"
---
# <a name="customer-aging-snapshots"></a>Ögonblicksbild av åldersfördelningen för kunder

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller information om ögonblicksbilder av kunders åldersfördelning. En ögonblicksbild av åldersfördelning beräknar åldersfördelningssaldon för en grupp av kunder vid en viss tidpunkt. Du kan skapa ögonblicksbild av åldersfördelningposter för antingen alla kunder eller för kunderna i en kundpool.

Information från ögonblicksbilder av åldersfördelning visas på listsidan **Åldersfördelade saldon** och på sidan **Inkasso**. Du måste skapa en ögonblicksbild av åldersfördelning innan du kan använda listsidan **Åldersfördelade saldon**. Listsidan visar bara kunder som en ögonblicksbild av åldersfördelning har skapats för.

I arbetsytan **Kundkredit och inkasso** visas också kunders åldersfördelning. Mer information finns i innehållet [i Kredit- och inkassohantering Power BI](credit-collections-power-bi.md).

> [!NOTE]
> Du minskar den tid som krävs för att skapa en ögonblicksbild av åldersfördelningen genom att aktivera följande funktioner i arbetsytan **Funktionshantering**. 
> - **Prestandaförbättring av åldersfördelning för kunder** 
> - **Prestandaförbättringar i åldersfördelning för kunder med kundpooler**  
>När båda funktionerna är aktiverade kan **kundpooler** användas när ögonblicksbild av åldersfördelning skapas. 

När du skapar en ögonblicksbild av kunders åldersfördelning kan du ange information om detta i följande fält:

- **Definition av åldersfördelningsperiod** – Välj definitionen av åldersfördelningsperiod för ögonblicksbilden av åldersfördelning. Du kan ha en ögonblicksbild av åldersfördelning för varje definition av åldersfördelningsperiod. Ögonblicksbilden av åldersfördelningen och definitionen av av åldersfördelningsperioden måste skapas separat.
- **Pool-ID** – Det här fältet är valfritt. Du kan använda en pool för att definiera den uppsättning med kunder som ska behandlas i ögonblicksbilden av åldersfördelningen. Om du väljer en kundpool i det här fältet skapas en ögonblicksbild av åldersfördelning bara för kundkonton som ingår i kundpoolen. Den valda kundpoolen måste vara av typen **Ögonblicksbild av åldersfördelning**. Om du låter fältet vara tomt skapas en ögonblicksbild av åldersfördelningen för alla kundkonton.


- **Kriterier** – Ögonblicksbilden av åldersfördelning åldras baserat på det datum som du väljer:

    - **Transaktionsdatum** – Varje transaktion åldras baserat på dess transaktionsdatum.
    - **Förfallodatum** – Varje transaktion åldras baserat på dess förfallodatum.
    - **Dokumentdatum** – Varje transaktion åldras baserat på dess dokumentdatum.

- **Åldersfördelning** – Välj vilket datum som ska användas i fältet **Aktuellt datum** för ögonblicksbilden av åldersfördelning. Åldersfördelningsperioder beräknas sedan utifrån detta datum. 

    - **Dagens datum** – använd systemdatumet. Välj det här alternativet om bearbetning har ställts in för att köra i en återkommande batch. Därefter används systemdatumet för körningen varje gång batchen körs.
    - **Valt datum** – använd ett datum som du anger. Om du väljer det här alternativet måste du ange ett åldersfördelningsdatum.

   Den aktuella åldersfördelningsperioden är till exempel 30 dagar. Om du väljer **Dagens datum** i det här fältet, startar den aktuella åldersfördelningsperioden dagens datum och inbegriper sedan de föregående 29 dagarna. Om du väljer **Valt datum** och anger ett datum, startar den aktuella åldersfördelningsperioden det angivna datumet och inbegriper sedan de föregående 29 dagarna.

- **Uppdatera inkassostatus** – Ställ in det här alternativet på **Ja** för att uppdatera inkassostatus för transaktiner på sidan **Inkasso** från **Löfte om betalning** till **Löfte om betalning brutet** om åldersfördelningsdatumet har passerat datumet i fältet **Löfte om betalning**. Ställ in det här alternativet på **Nej** för att låta inkassostatus vara oförändrad på sidan **Inkasso**.
- **Inkludera kunder med nollsaldo** – Ställ in det alternativet på **Ja** för att inkludera alla kunder, oavsett saldo. Om du inkluderar alla kunder rekommenderar vi att du aktiverar både funktionen **Förbättrad prestanda för kunders ålderfördelning** och **Prestandaförbättringar i åldersfördelning för kunder med kundpooler**. Ställ in det här alternativet på **Nej** för att endast inkludera kunder som har ett saldo. Den här inställningen gör prestanda snabbare eftersom kunder som inte har något saldo hoppas över.
- **Hoppa över kreditgränsberäkningar under åldersfördelning** – Om det här alternativet är inställt på **Ja** åldringsprocessen kommer inte att räkna om beloppet **Delsumma för följesedel**, **Delsumma för öppen order** och **Disponibel kredit** för varje kund. Dessa saldon visas på sidan **Åldersfördelade saldon** i faktaruta under **Kreditgräns**. Du kan få snabbare prestanda under åldersfördelningsprocessen om du ställer in alternativet **Ja**. Ställ in det till **Nej** om du vill omberäkna saldona när åldersprocessen körs. 
- **Företagsintervall** – Under fliken **Företagsintervall** väljer du de juridiska personer (företag) som ska inkluderas i ögonblicksbilden av åldersfördelning. Det är bara juridiska personer som har ställts in för centraliserade betalningar som kan väljas. Transaktioner från de valda juridiska personerna tas sedan med i åldersfördelningsperioderna för kunder som har samma part-ID i alla dessa juridiska personer. Valutabelopp konverteras till valutan för den juridiska person du är inloggad på när du skapar ögonblicksbilden av åldersfördelning.

Vi rekommenderar att du planerar den här processen så att den körs i en batch.

> [!NOTE]
> För att bidra till förbättrad batchprestanda när ögonblicksbilder av åldersfördelning skapas anger du ett nummer i fältet **Maximalt antal batchuppgifter** under snabbfliken **Inkassostandard** under fliken **Inkasso** på sidan **kundreskontraparametrar**. I fältet **Åldersfördelat kundsaldo** rekommenderar vi att du börjar med standardvärdet på **12** och **20** och sedan justerar värdet för att optimera bearbetningen för din situation. Vi rekommenderar inte att du anger det här värdet som är större än **30** eftersom det kommer att påverka prestandan. 

