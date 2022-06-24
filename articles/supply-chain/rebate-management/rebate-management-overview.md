---
title: Rabatthanteringsmodul – översikt
description: Denna artikel innehåller en översikt över modulen Rabatthantering för Microsoft Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: cfba391536559ed3a967d0aafe2e352486777dda
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873649"
---
# <a name="rebate-management-module-overview"></a>Modul för rabatthantering – översikt

[!include [banner](../includes/banner.md)]

Du kan använda modulen **Rabatthantering** om du vill skapa avtal, avtal eller avtal mellan ditt företag och dess kunder eller leverantörer, så att du kan beräkna rabatter, avdrag och royalties. Rabatthantering spårar och underhåller rabatt- och avdragstransaktioner på en central plats där användarna effektivt kan skapa, granska och bearbeta dem.

Rabatthantering stöder generering, underhåll och bearbetning av *rabatter*. En rabatt är en retur av en del av inköpspriset av en säljare eller en köpare. Rabatter baseras normalt på inköp av en viss kvantitet eller ett visst värde av varor under en viss period. Till skillnad från rabatter görs rabatter efter att inköpsbeloppet är helt fakturerat.

Rabatthantering stöder även *avdrag*. Ett avdrag är kompensation, en ersättning eller en avgift som betalas antingen för en licens eller för att använda immateriell egendom såsom märke, upphovsrätt eller patent eller för rättigheten att använda en naturlig resurs i syfte att t.ex. för resursbelöning, rotering eller brytning. Avdrag beräknas vanligtvis som en procentandel av intäkten eller vinsten från realiserad användning. Ju mer immateriell egendom eller naturlig resurs används, desto större är det avdrag som realiseras.

Dessutom har Rabatthantering stöd för kunders *royalties*. Royalties är betalningar som en part gör till licensinnehavaren eller franchisetagare för rätt att använda en tillgång.

Med rabatthantering kan du definiera bokföringsprofiler för provisionsbokföring, rabatter och avskrivningar. Dessutom kan bokföringar definieras för en viss kund eller leverantör. På det här sättet kan transaktioner som inte gäller för alla kund- eller leverantörsscenarier spåras via bokföringar.

Rabattransaktioner genereras automatiskt baserat på den beräkningsmetod som väljs och tidsplanerats i batchjobb. Du kan dessutom skapa arbetsflöden för hantering, granskning och godkännande av avtal.

## <a name="basis-calculation"></a>Basberäkning

Kundrabatter, kunders royalties och leverantörsrabatter kan ha olika underlag beroende på verksamhetens krav:

- Kundrabatter kan baseras på försäljningsorder, leveransfakturor eller fakturor.
- Kund royalties kan baseras på försäljningsorder, leveransfakturor eller betalda fakturor.
- Leverantörsrabatter kan baseras på inköpsorder eller försäljningsorder. De kan beräknas baserat på produkter som köps från rabattleverantören och säljs till kunder via försäljningsfakturor.

## <a name="flexible-calculations"></a>Flexibla beräkningar

Beräkningsperioder för rabatt är tillgängliga för både kund- och leverantörserbjudanden. En beräkningsperiod definierar längden på affären, beräkningsfrekvensen och beräkningsperioden. Rabatterna kan periodiseras baserat på försäljningsorderkvantiteter eller belopp för kvalificerade produkter under rabattperioden.

För varje avtalsberäkning kan någon av följande perioder ställas in:

- Faktura
- Dag
- Vecka
- Månad
- Kvartal
- År
- Anpassad period
- Alla eventuella multipler av de tidigare listade perioderna

Beräkningen kan göras för enskilda kunder och produkter, grupper av kunder och produkter, eller för alla kunder och produkter. Rabatter med flera detaljrader kan ha olika kvalificeringsdatumintervall. Etablerings- och anspråksperioderna kan skilja sig åt. Ersättning kan till exempel behandlas varje dag, medan anspråk behandlas en gång per månad.

Rabatter kan konfigureras baserat på många olika parametrar. De kan till exempel konfigureras som en procentsats, en sats eller ett fast belopp. Det finns fyra huvudberäkningsmetoder:

- Stegvis
- Ackumulerat
- Rullande
- Totalt värde

Rabattberäkningsresultat kan också reduceras med andra rabatter, beroende på om rabatten har ställts in för beräkning baserat på nettobeloppet.

På leverantörssidan kan rabatter som baseras på försäljningsorder beräkna priset baserat på en fifo-regel (först in, först ut), det senaste inköpspriset, det genomsnittliga inköpspriset eller försäljningspriset.

## <a name="rebate-target-transactions"></a>Rabattmåltransaktioner

Utleveransen som rabattavtalet eller avtalet genererar kan vara ekonomi eller artiklar.

Ekonomiska utdata fastställs av betalningstypen som tilldelas avtalet från bokföringsprofilen. Dessa utdata kan omfatta kundavdragsjournaler, fritextfakturor och leverantörsfakturor. I granskningssyfte omfattar transaktioner för ekonomisk rabattmål en referens till det ursprungliga rabattavtalet.

Artikelutleverans skapar en gratis artikelförsäljningsorder för kundrabatter och en inköpsorder för leverantörsrabatter. Transaktioner för artikelrabattmål innehåller alternativ för att avgöra vilken rabattreferens som ska anges på den kostnadsfria artikelförsäljningsordern eller inköpsordern.

## <a name="accurate-rebate-calculations"></a>Korrekta rabattberäkningar

Kombinationen av associerade erbjudanden, frekvensen för beräkningarna, beräkningsunderlaget och den valda beräkningsmetoden avgör om rabattberäkningarna är korrekta och precisa. Rabattbeloppet kan användas för att periodisera och begärde värden.

Bestämmelserna kan hanteras dagligen, varje vecka, varje månad eller enligt en anpassad period. Funktionen kan emellertid allokera eller betala rabatten, eller ta emot betalning av den, vid en definierad frekvens som är lika lång eller längre än reserveringsfrekvensen. För bortskrivning används samma frekvens som rabatten. Användarna kan enkelt justera ett plan- eller betalningsbelopp när som helst under utbetalningen.

Användarna behöver inte längre hantera affärer eller villkor i två steg. Provisions- och avskrivningar bokförs direkt i redovisningen. Dessutom kan kreditnotor skapas automatiskt. Därför finns det fullständig integrering med leverantörsreskontra och kundreskontra. Under bearbetningen överväger beräkningarna kvittningsrabatter, betalda fakturor, handelsrabatter och befintliga kreditfakturor för att se till att beloppen och värdena beräknas korrekt.

När rabatter beräknas skapar processen transaktioner som kan granskas innan bokföringen sker. En separat process bokför rabatthanteringstransaktioner. En journal, kreditfaktura eller debettransaktion kan sedan skapas vid bokföring till föreslagna transaktioner. Rapportutdrag och transaktionslistor kan erhållas för att säkerställa efterföljande, effektivitet och genomskinlighet.

## <a name="guaranteed-royalty-payments"></a>Så här ser det ut att vara royaltybetalningar

I Rabatthantering gör automatisk generering av betalningar det möjligt att hantera royalties snabbt och enkelt, även om det gäller minimum.

## <a name="maximizing-spend-versus-rebates"></a>Maximera utgift jämfört med rabatter

Leverantörer och produkter kan grupperas efter region, och olika erbjudanden kan ges, beroende på landet eller regionen för transaktionen. När användarna väljer produkter kan de definiera artiklarna som ingår och antalet artiklar som ska användas i rabattkvittning.
