---
title: Aktivitetsbaserad legotillverkning
description: Det här avsnittet beskriver i detalj hur du använder legotillverkningsaktiviteter i ett produktionsflöde för lean manufacturing.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, PlanActivity, ReqSupplyDemandSchedule, PlanActivityServiceDetails, PlanActivityServiceWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 267034
ms.assetid: 15c76a51-fa6d-42d2-994a-c67df6bae6a9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 48a1943833408767fe77456f66bbe109170a29e2
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985667"
---
# <a name="activity-based-subcontracting"></a>Aktivitetsbaserad legotillverkning

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver i detalj hur du använder legotillverkningsaktiviteter i ett produktionsflöde för lean manufacturing.

Det finns två sätt för legotillverkning i Microsoft Dynamics 365 Supply Chain Management: tillverkningsorder och lean manufacturing. I metoden lean manufacturing modelleras legotillverkningsarbetet som en tjänst som hör till en aktivitet för ett produktionsflöde. En speciell typ av kostnadsgruppstyp som heter **Direktutkontraktering** har införts, och legotillverkningstjänsterna är inte längre en del av en strukturlista (BOM). Kostnadsredovisning av legotillverkning är helt integrerat i kostnadsredovisningen för lean manufacturing.

## <a name="production-flows-that-involve-subcontractors"></a>Produktionsflöden som rör underleverantörer
Den grundläggande principen för ett produktionsflöde ändras inte när aktiviteter är uppdelade på underleverantörer. Materialet flödar fortfarande mellan olika platser, processaktiviteter omvandlar material till produkter och överföringsaktiviteter flyttar material eller produkter från en plats till en annan. Du kan utforma platser och arbetsgrupper som leverantörhanterade genom att tilldela leverantörskontot till ett lager eller en resurs i en resursgrupp.  

Utifrån dessa funktioner kräver lean manufacturing inte några specifika funktioner för att stödja flödet av material och produkter. Alla tänkbara scenarier som berör leverantörer av produktions- eller transporttjänster kan utformas utifrån arkitekturen i produktionsflöde och aktiviteter.  

Till exempel bedriver en underleverantör sin verksamhet från ett storlager hos underleverantören. När materialhanteringsenheter töms hos underleverantören, återgår kanban-korten till monteringscellen tillsammans med nästa leverans. Sedan fylls storlagret hos underleverantören på igen. Överföringar till och från underleverantören kan utformas som explicita överföringsaktiviteter för att stödja en plocknings- och leveransprocess. Om en explicit registrering inte krävs för att stödja fysisk transport, kan överföringsaktiviteter utelämnas.  

Du kan använda en underleverantör att belastningsutjämna den totala kapaciteten för produktionsflödet. Till exempel är ett produktionsflöde utformat med planerade kanban-regler. Planeraren använder planeringstavlan för kanban för att schemalägga och utjämna båda arbetsgrupper vid behov. Planeraren övervakar även schemat för konsoliderad leverans för storlager på sidan **Leveransschema**. Flera underleverantörer kan utformas i ett eller flera produktionsflöden, och det kan finnas flera kanban-regler som kan användas för att tillhandahålla samma produkt på samma plats via olika aktiviteter. Planeraren kan konvertera kanbans till en alternativ kanban-regel för att schemalägga ett kanban som har skapats för inhemsk produktion till en alternativ process. I själva verket påverkar arbetsgruppens legotillverkning inte produktionsflödet. Samma arbetsprincip gäller för två parallella interna arbetsgrupper eller två underleverantörsceller.   

Precis som alla andra aktiviteter i ett produktionsflöde kan legotillverkningsaktiviteter kan förbruka och förse inventerade, icke-inventerade (pågående arbete \[PIA\]), och halvfabrikatsmaterial och -produkter. I samtliga fall är processerna för planering och utförande av legotillverkningsaktiviteter desamma. Dessutom är dessa processer desamma som processerna för internt arbete.

## <a name="purchase-process-for-subcontracted-activities-services"></a>Inköpsprocess för legotillverkningsaktiviteter (tjänster)
Inköpsprocessen för legotillverkningsaktiviteter baseras på det fysiska materialflöde som registreras av kanban-jobbförloppet, till exempel Starta eller Slutför. Det ekonomiska flödet, till exempel kostnader för legotillverkning, är ett sekundärt som följer det fysiska flödet. Samtidigt är inköpsprocessen en oberoende process som tillåter manuell justering av inköpsdokument i alla steg. Här följer inköpsprocessen för legotillverkningsaktiviteter:

1.  Skapa ett inköpsavtal: Inköpsavtalet skapas för tjänsten och är ansluten till produktionsflödesaktiviteten.
2.  Skapa en inköpsorder En frisläppningsorder för inköp kan skapas för tjänsten baserat på planerade kanban-jobb. Jobb för samma tjänst kan grupperas till inköpsorderrader per dag, vecka eller månad. Inköpsorderrader kan skapas när som helst när kanban-jobben har skapats. Inköpsorderrader kan även skapas i efterhand. Detta alternativ väljs vanligen om en underleverantör tillhandahåller tjänster utan vidare meddelanden, baserat på kanban eller kanbankort som underleverantören får. I det här fallet kan avvikelserna mellan inköpsordern och fakturan minimeras.
3.  Skapa kanban-kort, material och en plocklista som ska skickas till underleverantören för bearbetning. Utifrån den detaljerade produktionsflödesmodellen sker förberedelserna på kanban-tavlan för processaktiviteter via plocklistan och förberedelsefunktionen. Alternativt utförs förberedelserna på kanban-tavlan för överföringsjobb med plocklistan samt start eller slutförande. Båda processer kan stödjas av WMS-plockning och en leveransprocess för inventerade material. Du kan skapa en fraktsedel vid behov.
4.  Skapa kanban-materialhanteringsenheter och kanban-kort. Bearbetade som kort returneras från underleverantören. Kort innehåller normalt en följesedel som anger det fysiska material som har levererats. En referens till de angivna tjänsterna behövs inte. Införsel av materialet eller produkten hos kunden registreras på kanban-tavlan, beroende på kanban-kort. (antingen kanban-tavlan för processaktiviteter eller kanban-tavlan för överföringsjobb används, beroende på modellerade aktiviteter.).
5.  Skapa rekommendationer för inleverans. Rekommendationerna för inleverans kan användas för att ersätta ett följesedelsdokument för de mottagna tjänsterna. Rekommendationerna för inleverans kan skapas baserat på slutförda kanban-jobb för legotillverkningsaktiviteten för en vald period. För varje inlevererat jobb skapas rekommendationer för den relaterade inköpsorderraden. Rekommendationerna för inleverans kan skrivas ut och skickas till underleverantören som en mottagningsbekräftelse.
6.  Skapa en faktura.

Processen avslutas när underleverantören faktureras för en period. Fakturamatchning sker mot de rekommendationer för inleverans som skapas. Eftersom rekommendationerna för inleverans representerar den exakta fysiska inleveransen av material, förenklas trevägsmatchningen.

## <a name="configuring-activities-for-subcontracting"></a>Konfigurera aktiviteter för legotillverkning
I följande avsnitt beskrivs hur du konfigurerar aktiviteter för legotillverkning.

### <a name="subcontracted-services"></a>Legotillverkningstjänster

Den betalningsartikel som används i verksamhetsbaserad legotillverkning måste vara en produkt med följande egenskaper:

-   **Produktty:** Tjänst
-   **Lagermodellsgrupp:** Ej i lager

Detta krav framtvingar användning av lagermodellen först in, först ut (FIFO). **Obs!** Kostnadsberäkningen för produkterna kräver att tjänstens standardkostnad definieras. Ett inköpsavtal med leverantören krävs. Annars kan inte tjänsten användas för aktivitetsbaserad legotillverkning.

### <a name="subcontracted-process-activities"></a>Legokontrakterade processaktiviteter

Följ dessa steg om du vill konfigurera en processaktivitet som en legotillverkningsaktivitet.

1.  Konfigurera en arbetsgrupp för legotillverkning. Om du vill konfigurera en arbetsgrupp som en arbetsgrupp för legotillverkning, måste du skapa en resurs av typen **Leverantör** och associera den med arbetsgruppen (resursgrupp). En kostnadskategori för körning av kostnadsgrupptypen **Direktutkontraktering** ska tilldelas till arbetsgruppen. Kostnadskategorier för inställning och kvantitet är inte obligatoriska.
2.  När en processaktivitet skapas och hör till en arbetsgrupp för legotillverkning, måste du konfigurera en tjänst för aktiviteten innan produktionsflödesversionen kan aktiveras. Du slutför detta steg på sidan **Aktivitets**-**information**. För aktiviteter som är kopplade till en arbetsgrupp för legotillverkning, visas snabbfliken **Servicevillkor**. Lägg till en standardtjänst som gäller för alla utleveransartiklar på den här snabbfliken. Om specifika utdataobjekt kräver olika tjänster eller andra tjänsterberäkningsparametrar (exempelvis ett annat tjänsteförhållande), kan du lägga till andra tjänster till aktiviteten.

## <a name="subcontracted-transfer-activities"></a>Legokontrakterade överföringsaktiviteter
En överföringsaktivitet konfigureras som en legotillverkningsaktivitet, beroende på inställningen **Fraktad av** för överföringsaktiviteten. Följande alternativ är tillgängliga:

-   **Speditör** – Aktiviteten läggs ut på entreprenad (legotillverkning) om överföringen från lagerstället hanteras av en leverantör (som definieras av en egenskap för lagerstället). Alla valda inköpsavtal för tjänster måste ha samma leverantörs-ID som lagerstället.
-   **Mottagare** – Aktiviteten läggs ut på entreprenad (legotillverkning) om överföringen till lagerstället hanteras av en leverantör (som definieras av en egenskap för lagerstället). Alla valda inköpsavtal för tjänster måste ha samma leverantörs-ID som lagerstället.
-   **Transportföretag** – Aktiviteten läggs ut på entreprenad (legotillverkning) till alla leverantörer som tillhandahåller tjänsten. Transportföretag måste skapas för lagerstyrning och måste ha ett tilldelat leverantörskonto för att vara giltiga.

Precis som för processaktiviteter måste du konfigurera en standardtjänst för överföringsaktiviteter för legotillverkning på snabbfliken **Servicevillkor** på sidan **Aktivitets**-**information**.

## <a name="service-quantity-calculation"></a>Beräkning av tjänstkvantitet
Hela inköpsprocessen baseras på en artikelreferens för en tjänst. Artikelreferensen mäts i en måttenhet för en tjänst. Tjänster mäts normalt i antalet tjänster (enheter) eller i tid. Du kan använda följande metoder för att beräkna tjänstekvantiteten baserat på registrerat slutförande av kanban-jobb:

-   **Beräkning baserad på antalet jobb** – ett kanban-jobb är lika med *n* tjänsteenheter, oavsett den produktkvantitet som anges. Ett jobb motsvarar en materialhanteringsenhet i lean manufacturing. Den här beräkningsmetoden gäller för alla tjänster som har ett fast pris per materialhanteringsenhet. Denna metod gäller därför vanligtvis för överföringsaktiviteter. Den kan emellertid också gälla processaktiviteter som bearbetar hela materialhanteringsenheter.
-   **Beräkning baserad på produktkvantiteten** – Tjänstekvantiteten är relativ i förhållande till den produktkvantitet som har tidsplanerats/tillhandahålls. När den angivna produktkvantiteten beräknas kan felaktiga kvantiteter antingen inkluderas eller exkluderas. Den här beräkningsmetoden gäller för alla fall där tjänstepriset per enhet för den bearbetade produkten har överenskommits.
-   **Beräkning baserad på aktivitetstiden** – Teoretiska aktivitetstider beräknas baserat på bearbetningstiden för aktiviteten, den totala bearbetade kvantiteten samt genomflödestakten för den bearbetade produkten. Den här beräkningsmetoden gäller för tjänster som betalas per timme och har en avvikelse i tid per bearbetad produkt.

## <a name="cost-accounting-of-subcontracted-services"></a>Kostnadsredovisning för legotillverkningstjänster
När inleveransrekommendationer eller en leverantörsföljesedel på en inköpsorder som har skapats för ett produktionsflöde (d.v.s. den inköpsorder som skapades utifrån kanban-jobb för legotillverkningsaktiviteter) bokförs, redovisas värdet för inleveransen i produktionsflödets PIA-konton. Avvikelser på fakturor redovisas även för produktionsflödet. En kostnadskategori för legotillverkningsarbete har införts. Denna kostnadskategori möjliggör en transparent värdespårning för det underleverantörsarbete som tilldelas PIA och som förbrukas per period.  

Den kostnadskalkylering med automatisk lageravräkning för lean manufacturing som sker mot slutet av en kostnadsredovisningsperiod beräknar faktiska avvikelser för produkter som har framställts i produktionsflödet under kostnadsperioden.

## <a name="modeling-transfers-as-subcontracted-activities"></a>Modellera överföringar som legotillverkningsaktiviteter
Många betraktar transport som ickeproduktivt och menar att det inte tillför något värde. När kostnaden för legotillverkning jämförs med kostnaden för intern produktion måste emellertid kostnaden för ytterligare transportaktiviteter beaktas. Ett produktionsflöde som sträcker sig över flera platser och kräver transporttjänster bör utforma transportkostnader som del av kostnaden för att leverera varorna till kunden. 

Verksamhetsbaserad legotillverkning inom lean manufacturing gör att du kan integrera speditörer och transporteleverantörer som flyttar material och produkter mellan platser för ett produktionsflöde. Du kan tilldela smittbärare eller leverantören av modellvariabler en överföringsaktivitet. Aktiviteter/överföringsjobbet baseras på ett avtal för tjänster och inköp, och du kan skapa inköpsorder och rekommendationer för inleverans, baserat på de faktiska överföringsjobben. Denna funktion är densamma som funktionerna för processaktiviteter för legotillverkning.  

Supply Chain Management stöder numera strukturlisteberäkning som innehåller transporttjänster, skapandet av relaterade inköpsorder, integrerad inleveransregistrering samt integrering av transporttjänstkostnader i kostnaderna för produktionsflödet.



