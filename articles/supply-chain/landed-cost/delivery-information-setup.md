---
title: Inställningar för leveransinformation
description: I det här avsnittet beskrivs hur du ställer in leveransinformation för modulen hemtagningskostnad.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMPortTable, ITMLeadTimeTable, ITMLegTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: c9e36bef0b4cf87fa3fbad5d191731b48221a41e9d92241733e1bc3edb2ca838
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747021"
---
# <a name="delivery-information-setup"></a>Inställningar för leveransinformation

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in leveransinformation för modulen **hemtagningskostnad**.

## <a name="shipping-ports"></a>Leveranshamnar

Leveransportar identifierar varifrån varorna levereras och till. För varje denna definieras en "till"-port och en "från"-port, baserat på den tid som valts för färdens fartyg. Leveransportar används för att bygga sträckor på en resa och även färdens aktiviteter. De definieras normalt med hjälp av namnet på staden och landet eller regionen där den fysiska leveransporten finns.

För att arbeta med leveransportar, gå till **Hemtagningskostnad \> Inställning av leveransinformation \> Leveransportar**. Där kan du visa, lägga till och ta bort poster för dina leveransportar. Följande register beskriver de fält som är tillgängliga för varje post.

| Fält | beskrivning |
|---|---|
| Leveranshamn | Ange ett unikt ID-namn/nummer för leveransport. |
| beskrivning | Ange en beskrivning av leveransport. |

## <a name="tracking-control-center"></a><a name="tracking-control-center"></a>Center för spårningskontroll

Du använder spårningskontrollcentret när du vill ställa in ledtider, statusuppdateringar och flöde för information som är kopplad till en transportbehållare när leveransbehållarena flyttas från en del till nästa. När du skapar en spårningskontrollpost är den associerad med en specifik sträcka för en resa på en färd. När en färd uppdateras, uppdateras den associerade posten och fylls i enligt definitionen. Du kan uppdatera spårningsinformation för enskilda användare från sidan **Alla färder**.

Du öppnar spårningskontrollcentret genom att gå till **Hemtagningskostnad \> Informationsinställningarna för leverans \> Spårningskontrollcenter**.

I spårningskontrollcentret visas en av de tre sidvyerna, beroende på vilket värde som har valts i fältet **Skapa typ** i listfönstret: *Tom*, *Ledtid* eller *Statusuppdatering*. Varje skapartyp uppdaterar en annan uppsättning information som är associerad med förloppet för en fil från ursprungsplatsen till slutdestinationen.

### <a name="common-rule-settings"></a>Vanliga regelinställningar

Följande tabell visar de fält som är tillgängliga för alla tre typerna i spårningskontrollcentret.

| Fält | beskrivning |
|---|---|
| Källregister, källfält | Dessa fält identifierar ett källregister och ett källfält i databasen. Regeln läser in värdet i fältet och använder det på det sätt som har definierats av andra inställningar för regeln. |
| Målregister, målfält | Dessa fält identifierar en destinationsregister och ett källfält i databasen. Regeln läser in värdet i fältet och använder det (eller skriver över) på det sätt som har definierats av andra inställningar för regeln. |
| Aktivitet | Det här fältet identifierar den typ av aktivitet som ska användas för en leveransbehållare som matchas av en regel. |
| Matchningskriterier | Det här fältet avgör hur systemet identifierar en matchning för en regel. I varje instans granskas data i käll- och destinationsregistren för att avgöra om och när ett fält ska uppdateras i målregistret.<p>Källregistret är till exempel *Färder* och målregistret är *Inköpsrubrik* eller *Inköpsrader*. Tabellen *Färder* har ett värde för **Från port** på *Hongkong* och *Inköpsrubrik* har **Från port** värdet *Shanghai*. En regel skapas sedan som har *Hongkong* som "från"-port. I det här fallet fungerar värdena i fältet **Matchningskriterier** på följande sätt:</p><ul><li>**Båda** – Målfältet uppdateras inte eftersom en av de två portarna inte matchar.</li><li>**Källa** – Målfältet uppdateras eftersom källregistrets "från"-port är *Hongkong*.</li><li>**Mål** – Målfältet uppdateras inte eftersom destinationsregistrets "från"-port är *Shanghai* (inte *Hongkong*).</li></ul> |
| Kopiera åtgärd | Tillgängliga värden är *Kopiera* och *Standard*. Välj *Kopiera* om du vill kopiera värdet i källfältet till destinationsfältet. Välj *Standard* om du vill ange ett statiskt värde för destinationsfältet. |
| Standardvärde | När fältet **Kopiera åtgärd** är inställt som *Standard* definierar fältet **Standard** standardvärdet för destinationsfältet. Om åtgärden till exempel är relaterad till en portuppdatering och fältet **Kopiera åtgärd** är inställt som *Standard*, identifierar **Standard** en port. |
| Etapp | Det här fältet identifierar den del av såret som den angivna åtgärden ska vidtas för, t.ex. inläsning eller tull. |
| Tjänstleverantör | Om en viss serviceleverantör används för aktuell statusuppdatering/del av tjänsten, identifierar detta fält tjänstleverantören. Tjänstleverantörer definieras i leverantörskontot. |

### <a name="lead-time-rules"></a>Regler för ledtid

Ledtiden är den uppskattade tid det tar att slutföra en definierad sträcka för en resa för en färd. Ledtiden för varje sträcka på en resa används för att beräkna det uppskattade leveransdatumet för färden. Det datumet anges sedan i fältet **Bekräftat leveransdatum** på varje inköpsrad i färden.

Med hjälp av ledtidsregler kan du hantera uppdateringar av datum. Aktiviteter genereras automatiskt när en resemall används för en sådan.

Lägg till en ledtidsregel i spårningskontrollcentret genom att följa dessa steg.

1. Gör något av följande:

    - Gå till **Hemtagningskostnad \> Inställning av resa med flera sträckor \> Sträckor**. Välj det ben du vill ställa in ledtider för och välj sedan i åtgärdsfönstret **Spårningskontrollcenter**. Spårningskontrollcentret förinlästs med information om valt del.
    - Gå till **Hemtagningskostnad \> Inställning av leveransinformation \> Spårningskontrollcenter**. Du måste sedan välja en sträcka manuellt i steg 4 i den här proceduren.

1. I listfönstret, ange fältet **Skapa typ** till *Ledtid*.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Om du har startat från spårningskontrollcentret i steg 1 ska du ställa in fältet **Sträcka** till delen som du vill skapa en ledtidsregel för. Om du har startat från sidan **Sträckor** är fältet **Sträcka** förinställt på den sträcka du valde innan du öppnade spårningskontrollcentret.

    Baserat på värdet i fältet **Sträcka** anges flera fält automatiskt, som visas här:

    - **Källregister:** *Behållaraktiviteter*
    - **Källfält:** *Startdatum*
    - **Målregister:** *Behållaraktiviteter*
    - **Målfält:** *Uppskattat slutdatum*

1. I fältet **aktivitet**, välj den aktivitet som den aktuella regeln ska gälla för.
1. I fältet **Ledtid** ange ledtiden (i dagar) som ska tillämpas när den aktuella regeln utlöses.

### <a name="status-update-rules"></a>Regler för uppdatera status

Poster där fältet **Skapa typ** är inställt på *Statusuppdatering* kommer att uppdatera statusen på inköpsordern eller statusen på resan, leveransbehållaren eller folionivån. Statusen kan anges separat. Använd dessa för att informera användaren eller avdelningen om färdens stadium (t.ex. mottagna dokument eller varor på väg).

När fältet **Skapa typ** är inställt på *Statusuppdatering*, innehåller spårningskontrollcentret en snabbflik för **Rader** där du kan definiera ett kostnadsområde och den uppdaterade statusen för artikeln. Det kan till exempel vara en rad där fältet **Kostnadsområde** har ställts in som *Behållare* och fältet **Färdstatus** anges till *Varor på väg*. I det här fallet, när en order slutför den angivna sträckan kommer fältet **Färdstatus** för leveransbehållaren att uppdateras till *Varor på väg*.

Statusuppdateringar ger status för en färd genom färdraderna och inköpsorderrader som är associerade med den färden. När en färd går genom sin resa från port, segling och tull till destinationslagret, ger fältet **Färdstatus** för färdposten en snabbvy över vilket stadium artiklarna befinner sig i.

Lägg till en regel för statusuppdatering i spårningskontrollcentret genom att följa dessa steg.

1. Gör något av följande:

    - Gå till **Hemtagningskostnad \> Inställning av resa med flera sträckor \> Sträckor**. Välj den sträcka du vill ställa in statusuppdatering för och välj sedan i åtgärdsfönstret **Spårningskontrollcenter**. Spårningskontrollcentret förinlästs med information om valt del.
    - Gå till **Hemtagningskostnad \> Inställning av leveransinformation \> Spårningskontrollcenter**. Du måste sedan välja en sträcka manuellt i steg 4 i den här proceduren.

1. I listfönstret, ange fältet **Skapa typ** till *statusuppdatering*.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Om du har startat från spårningskontrollcentret i steg 1 ska du ställa in fältet **Sträcka** till delen som du vill skapa en statusuppdatering för. Om du har startat från sidan **Sträckor** är fältet **Sträcka** förinställt på den sträcka du valde innan du öppnade spårningskontrollcentret.

    Baserat på värdet i fältet **Sträcka** anges flera fält automatiskt, som visas här:

    - **Källregister:** *Behållaraktiviteter*
    - **Källfält:** *Faktiskt slutdatum*
    - **Målregister:** Detta fält är tomt.
    - **Målfält:** Detta fält är tomt.

1. I fältet **aktivitet**, välj den aktivitet som din regel ska gälla för.
1. På snabbfliken **Rader** anger du statusuppdateringar för respektive kostnadsområde.

### <a name="blank-type-rules"></a>Tomma typregler

Du använder poster som har värdet **Skapa typ** på *Tom* om du vill åsidosätta eller ange ett fältvärde, baserat på data i ett annat fält. Ett fält från hemtagningskostnad skriver över data i andra områden av Microsoft Dynamics 365 Supply Chain Management, baserat på regler som ställs in i spårningskontrollcentret.

1. Gå till **Hemtagningskostnad \> Inställning av leveransinformation \> Spårningskontrollcenter**.
1. I listfönstret, ange fältet **Skapa typ** till *Tom*.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Definiera käll- och destinationsvärden, matchningskriterier, kopieringsåtgärd och andra relevanta parametrar enligt regelns krav.

### <a name="required-tracking-control-setup"></a>Nödvändiga inställningar för spårningskontroll

För varje mallen måste två poster ställas in i spårningskontrollcentret. Båda dessa poster har värdet **Skapa typ** av *Tom* och används i alla implementeringar av hemtagningskostnad. De hjälper till att säkerställa att inköpsdatum och varor på väg de förväntade datumen uppdateras för färder och på relaterade inköpsorderrader på förväntat sätt.

Den första posten som krävs för att uppdatera inköpsraderna. Den måste ha följande inställningar:

- **Källregister:** *Behållaraktiviteter*
- **Källfält:** *Uppskattat slutdatum*
- **Måltabell:** *Inköpsrader*
- **Målfält:** *Bekräftat eller leveransdatum*

Den andra posten krävs för att uppdatera transaktioner för varor på väg. Den måste ha följande inställningar:

- **Källregister:** *Behållaraktiviteter*
- **Källfält:** *Uppskattat slutdatum*
- **Måltabell:** *Order för varor på väg*
- **Målfält:** *Förväntat datum*
