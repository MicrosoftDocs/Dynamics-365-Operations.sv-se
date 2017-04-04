---
title: Verksamhetsbaserade legotillverkning
description: "Det här avsnittet beskrivs i detalj, använda legotillverkningsaktiviteter i ett produktionsflöde för lean manufacturing."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 267034
ms.assetid: 15c76a51-fa6d-42d2-994a-c67df6bae6a9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8e57c53ca894aa44b71e15c1f66bd7c722ea8a81
ms.lasthandoff: 03/31/2017


---

# <a name="activity-based-subcontracting"></a>Verksamhetsbaserade legotillverkning

Det här avsnittet beskrivs i detalj, använda legotillverkningsaktiviteter i ett produktionsflöde för lean manufacturing.

Det finns två sätt för legotillverkning i Microsoft Dynamics 365 för operationer: tillverkningsorder och lean manufacturing. I metoden lean manufacturing modelleras det legotillverkning arbetet som en tjänst som hör till en aktivitet för ett produktionsflöde. En speciell typ av kostnadsgruppstyp som heter **direktutkontraktering** har införts, och de legotillverkning tjänsterna inte längre en del av en strukturlista (BOM). Kostnadsredovisning av legotillverkning är helt integrerat i kostnadsredovisning för lean manufacturing lösningen.

## <a name="production-flows-that-involve-subcontractors"></a>Produktionsflöden som rör underleverantörer
Den grundläggande principen av ett produktionsflöde ändras inte när aktiviteter är uppdelat på underleverantörer. Materialet fortfarande flödar mellan platser, konvertera processaktiviteter material till produkter och överföringsaktiviteter flytta material eller produkter från en plats till en annan. Du kan utforma platser och arbetsgrupper som leverantören hanteras genom att tilldela leverantörskontot till ett lager eller en resurs i en resursgrupp  

Utifrån dessa funktioner kräver lean manufacturing inte några specifika funktioner för att stödja flödet av material och produkter. Alla tänkbara scenarier som innehåller leverantörer som tillhandahåller av produktions- eller tjänster kan utformas utifrån arkitekturen i produktionsflödet och aktiviteter.  

Till exempel fungerar en underleverantör från ett storlager med underleverantören. När materialhanteringsenheter vid underleverantören är tomma återgår kanban-kort till cellen sammansättningen tillsammans med nästa leverans. Sedan fylls storlager vid underleverantören. Överföringar till och från underleverantören kan utformas som explicit överföringen verksamhet för att stödja en plockning och processen för försändelsereservation. Om en explicit registrering inte krävs för att stödja fysisk transport, kan överföringsaktiviteter uteslutas.  

Du kan använda en underleverantör att belastningsutjämna totala kapacitet för produktionsflödet. Till exempel är ett produktionsflöde utformat med planerade kanban-regler. Planeraren använder planering styrelse att schemalägga och Belastningsnivå kanban både arbetsgrupper efterfrågan. Planeraren övervakar även schemat för storlager konsoliderade leverans på de **schema leverans** sida. Flera underleverantörer kan utformas i en eller flera produktionsflöden och det kan finnas flera kanban-regler som kan användas för att tillhandahålla samma produkt på samma plats via olika aktiviteter. Planeraren kan konvertera kanbans till en alternativ kanban-regel som ska schemaläggas om ett kanban som har skapats för inhemsk produktion till en alternativ process. I själva verket påverkar den legotillverkning slags arbetsgruppen inte produktionsflödet. Arbeta samma sak gäller för två parallella interna arbetsgrupper eller underleverantörer två celler.   

Precis som all annan verksamhet i ett produktionsflöde legotillverkningsaktiviteter kan förbruka och ange inventerade, inventerade (pågående arbete \[PIA\]), och halvfabrikat material och produkter. Alltid är processer för planering och köra legotillverkningsaktiviteter desamma. Dessutom kan bearbeta dessa lika processer för intern resurs.

## <a name="purchase-process-for-subcontracted-activities-services"></a>Inköpsprocessen för legotillverkningsaktiviteter (tjänster)
Inköpsprocessen för legotillverkningsaktiviteter baseras på den fysiska materialflödet registreras av jobbet för kanban-förlopp, till exempel, starta eller Slutför. Ekonomiska flödet, till exempel kostnader för den legotillverkning är Sekundärflöde efter fysiska flödet. Samtidigt är en oberoende process som tillåter manuell justering av inköpsdokument hela vägen inköpsprocessen. Här följer inköpsprocessen för legotillverkningsaktiviteter:

1.  Skapa ett inköpsavtal. Inköpsavtalet för tjänsten och ansluten till aktiviteten för produktionsflödet.
2.  Skapa en inköpsorder En frisläppningsorder för inköp kan skapas för tjänsten baserat på planerad kanban-jobb. Jobb för samma tjänst kan grupperas till inköpsorderrader per dag, vecka eller månad. Inköpsorderrader kan skapas när som helst när kanban-jobben har skapats. Inköpsorderrader kan även skapas i efterhand. Detta alternativ väljs vanligen om en underleverantör tillhandahåller tjänster utan vidare meddelanden baserat på kanban- eller kanban där underleverantören. I det här fallet kan avvikelserna mellan inköpsordern och fakturan minimeras.
3.  Skapa kanban-kort, material och en plocklista som ska skickas till underleverantören iordningställande för bearbetning. Utifrån detaljerad modellträdstrukturen för produktionsflödet görs framställning på kanban-tavla för processaktiviteter via plocklistan och Förbered funktion. Alternativt kan utförs förbereda på kanban-tavla för överföringsjobb med i plocklistan och start- eller. Båda processerna kan stödjas av WMS plockning och processen för försändelsereservation för inventerade material. Du kan skapa en fraktsedel vid behov.
4.  Skapa kanban materialhanteringsenheter och kanban-kort. Bearbetade som kort returneras för underleverantören. Kort innehåller normalt en följesedel som anger det fysiska material som har levererats. En referens till de angivna tjänsterna behövs inte efter uppgraderingen. Införsel av materialet eller produkten hos kunden registreras på kanban-tavla, beroende på kanban-kort. (Eller kanban-tavla för processaktiviteter kanban-tavlan för överföringsjobb används beroende på modellerade aktiviteter.).
5.  Skapa en inleverans rådgivande. Rådgivande inleverans kan användas för att ersätta en följesedel följesedeln dokument för mottagna tjänsterna. Rekommendationerna för inleverans kan skapas baserat på slutförd kanban-jobb för den legotillverkning aktiviteten för en vald period. För varje jobb inleverans skapas rekommendationerna för den relaterade inköpsorderraden. Rådgivande inleveransen kan skrivas ut och skickas till underleverantören som bekräfta mottagandet.
6.  Generera en faktura.

Processen avslutas när underleverantören faktureras för en period. Faktura-matchning sker mot rekommendationerna inleveransen som skapas. Eftersom inleveransen rekommendationerna representerar exakt fysisk inleverans av material, förenklas den trevägsmatchning.

## <a name="configuring-activities-for-subcontracting"></a>Konfigurera aktiviteter för legotillverkning
I följande avsnitt beskrivs hur du konfigurerar aktiviteter för den legotillverkning.

### <a name="subcontracted-services"></a>Legotillverkningstjänster

Artikeln som används i verksamhetsbaserade legotillverkning betalning måste vara en produkt som har följande egenskaper:

-   **Produkttyp:** Service
-   **Lagermodellgruppen:** inte finns i lager

Detta framtvingar användning av först in, först ut (FIFO) lagermodell. **Anmärkning:** kostnadsberäkningen produkternas kräver att definieras standardkostnaden för tjänsten. Det krävs ett inköpsavtal med leverantören. Annars kommer kan inte tjänsten användas för verksamhetsbaserade legotillverkning.

### <a name="subcontracted-process-activities"></a>Legotillverkning processaktiviteter

Följ dessa steg om du vill konfigurera en processaktivitet som en legotillverkning verksamhet.

1.  Konfigurera en cell med underleverantörsarbete. Om du vill konfigurera en arbetsgrupp som den legotillverkning, måste du skapa en resurs av den **leverantör** ange och associera den med en arbetsgrupp (resursgrupp). En kostnadskategori för körning av den **direktutkontraktering** kostnadsgruppstyp ska tilldelas till arbetsgruppen. Kostnadskategorier för inställning och kvantitet är inte obligatoriska.
2.  När en processaktivitet skapas och hör till en arbetsgrupp legotillverkning produktionsflödesversionen kan aktiveras om du konfigurerar en tjänst för aktiviteten. Du har slutfört denna åtgärd på de **aktiviteten****information** sida. För aktiviteter som är kopplade till den legotillverkning arbetsgrupp i **Service villkor** på snabbfliken visas. Lägg till en standardtjänst som gäller för alla Utleveransartiklar på den här snabbfliken. Om utdata objekt kräver olika tjänster eller annan beräkning Serviceparametrar (exempelvis en annan Tjänstförhållande) kan du lägga till andra tjänster till aktiviteten.

## <a name="subcontracted-transfer-activities"></a>Legotillverkning överföringsaktiviteter
En överföringsaktivitet konfigureras som en legotillverkning aktivitet, beroende på de **Fraktad av** Ange aktivitetens överföringen. Följande alternativ är tillgängliga:

-   **Speditörens** – aktiviteten gäller legotillverkning om överföring från lagerstället hanteras av en leverantör (som definieras av en egenskap för lagerstället). Alla valda inköpsavtal för tjänster måste ha samma leverantör-ID som lagerstället.
-   **Mottagaren** – aktiviteten gäller legotillverkning om överföring till lagerstället hanteras av en leverantör (som definieras av en egenskap för lagerstället). Alla valda inköpsavtal för tjänster måste ha samma leverantör-ID som lagerstället.
-   **Transportföretagets** – aktiviteten legotillverkning till alla leverantörer som tillhandahåller tjänsten. Transportföretag måste skapas för lagerstyrning för att vara giltig och måste ha en tilldelad leverantörskonto.

För processaktiviteter, måste du konfigurera en standardtjänst för legotillverkning överföringsaktiviteter på de **Service villkor** snabbfliken i den **aktiviteten****information** sida.

## <a name="service-quantity-calculation"></a>Beräkning av tjänstkvantitet
Hela inköpsprocessen baseras på en artikelreferens för en tjänst. Referensen till det här objektet mäts i en enhet för en tjänst. Tjänster mäts normalt i antalet tjänster (enheter) eller i tid. Du kan använda följande metoder för att beräkna tjänstekvantiteten baserat på registrerad slutförandet av kanban-jobb:

-   **Beräkning baserat på antalet jobb** – ett kanban-jobb är lika med *n* tjänsteenheter, oavsett den produktkvantitet som anges. Ett jobb motsvarar en materialhanteringsenhet i lean manufacturing. Den här beräkningsmetoden gäller för alla tjänster som har ett fast pris per hanteringsenhet. Denna metod gäller därför vanligtvis för att överföra aktiviteter. Men kan det också gälla processaktiviteter som bearbetar hela materialhanteringsenheter.
-   **Beräkning baserat på produktkvantiteten** – tjänstekvantiteten är i förhållande till den produktkvantitet som har tidsplanerats/tillhandahålls. När den angivna produktkvantiteten beräknas kan felaktiga kvantiteter vara antingen inkluderas eller exkluderas. Den här beräkningsmetoden gäller för alla fall där tjänsten priset per enhet för den bearbetade produkten har överenskommits.
-   **Beräkning baserat på aktivitetstiden** – teoretiska aktivitetstider beräknas baserat på bearbetningstiden för aktiviteten, behandlas totalen kvantitet och Genomflödestakten för den bearbetade produkten. Den här beräkningsmetoden gäller för tjänster som betalas per timme och har en avvikelse i tid per produkt.

## <a name="cost-accounting-of-subcontracted-services"></a>Kostnadsredovisning för legotillverkningstjänster
När inleveransen rådgivande eller en följesedel för en inköpsorder har skapats för ett produktionsflöde (d.v.s. den inköpsorder som skapades utifrån kanban-jobb för legotillverkningsaktiviteter) leverantör bokförs, redovisas värdet på inleveransen i PIA-konton för produktionsflödet. Avvikelser av fakturor redovisas även för produktionsflödet. En kostnadskategori för den legotillverkning har införts. Denna kostnadskategori kan genomskinliga spåra värdet för underleverantörsarbete som konsumeras per period och fördelas till Pågående arbete.  

Bakåtavräkning för lean manufacturing i slutet av en kostnadsredovisning period beräknar faktiska avvikelser för produkter som har framställts under kostnadsredovisningen av produktionsflödet.

## <a name="modeling-transfers-as-subcontracted-activities"></a>Modellering överföringar som legotillverkningsaktiviteter
Personer du ofta transport icke produktivt och Tänk läggs inget värde. Jämfört med kostnaden för den legotillverkning är interna produktionskostnaden, beaktas kostnaden för ytterligare transporter. Ett produktionsflöde som sträcker sig över flera platser och kräver transporttjänster bör utforma transportkostnader som del av kostnaden för att leverera varor till kunden. 

Verksamhetsbaserade legotillverkning i lean manufacturing kan du integrera transportföretag och transportera leverantörer som flyttar material och produkter mellan platser för ett produktionsflöde. Du kan tilldela smittbärare eller leverantören av modellvariabler en överföringsaktivitet. Aktiviteter/överföringsjobbet utifrån ett avtal för tjänster och inköp och du kan skapa inköpsorder och rekommendationerna för inleverans, baserat på de faktiska överföringsjobb. Denna funktion är densamma som funktionerna för den legotillverkning processaktiviteter.  

Därför servicekostnader nu stöder strukturlisteberäkning som innehåller transporttjänster skapandet av relaterade inköpsorder, integrerad inleverans registrering och integrationen transportmedel för Dynamics 365 i flödet produktionskostnad.


