---
title: Lagertransaktion – information
description: Denna artikel innehåller en översikt av sidan Transaktionsdetaljer som visar information om en vald lagertransaktion.
author: rachel-profitt
ms.date: 04/25/2022
ms.topic: article
ms.search.form: InventTrans, InventTransDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-04-25
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 55e29d5804f57cd86fb5ddac5d6c5576b7ea5f61
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859399"
---
# <a name="inventory-transaction-details"></a>Lagertransaktion – information

På sidan **Transaktionsdetaljer** kan du visa information om valda lagertransaktioner.

## <a name="open-the-transaction-details-page"></a>Öppna sidan Transaktionsdetaljer

Följ dessa steg för att öppna sidan **Transaktionsdetaljer**.

1. Gå till **Lagerhantering \> Förfrågningar och rapporter \> Transaktioner**.
1. Välj den transaktion som du vill inspektera.
1. Klicka på **Transaktionsdetaljer** i åtgärdsfönstret.

## <a name="fasttabs-overview"></a>Snabbflikar – översikt

Sidan **Transaktionsdetaljer** är uppdelad på flera snabbflikar. Följande tabell beskriver syftet med varje snabbflik.

| Snabbflik | Beskrivning |
|---|---|
| Allmänt | På den här snabbfliken visas grundläggande information om den valda lagertransaktionen. Utöver de fält som visas på sidan **Lagertransaktioner** innehåller den även ytterligare fält som beskrivs senare i denna artikel. |
| Uppdateringar | På den här snabbfliken visas information som är relaterad till de fysiska, ekonomiska och kvittningsaspekterna för den valda lagertransaktionen. Beroende på aktuell status för transaktionen kan vissa fält vara tomma. Dessa fält ställs dock automatiskt in när transaktionerna bokförs. Utöver de fält som visas på sidan **Lagertransaktioner** innehåller den här snabbfliken även ytterligare fält som beskrivs senare i denna artikel. |
| Bokföring i reskontran | På den här snabbfliken visas den bokföringstyp och det redovisningskonto som används för fysisk uppdatering, ekonomisk uppdatering, fysisk intäkt, fysiska avgifter, ekonomiska intäkter och ekonomiska avgifter som är kopplade till den valda lagertransaktionen. |
| Referenser | På den här snabbfliken visas ytterligare information om källtransaktionen som skapade den valda lagertransaktionen. Den här informationen kan till exempel omfatta information från inköpsordern eller försäljningsordern. |
| Relaterad information | På den här snabbfliken visas ytterligare information om den valda lagertransaktionen. De här fälten kanske inte ställs in om du inte använder vissa funktioner, till exempel anskaffningskategorier eller projekt. |
| Ekonomiska dimensioner – fysiska | På den här snabbfliken visas värdena för den ekonomiska dimensionen som användes när den fysiska uppdateringen bokfördes. Om den fysiska uppdateringen inte har bokförts är fälten tomma. |
| Ekonomiska dimensioner – ekonomiska | På den här snabbfliken visas värdena för den ekonomiska dimensionen som användes när den ekonomiska uppdateringen bokfördes. Om den ekonomiska uppdateringen inte har bokförts är fälten tomma. |
| Lagerdimensioner | På den här snabbfliken visas de lagerdimensionsvärden som har tilldelats den valda lagertransaktionen. Dessa värden inkluderar plats, lagerställe, storlek, färg, konfiguration, placering, batchnummer, serienummer, lagerstatus, ID-nummer och ägare. |

## <a name="fields-on-the-general-fasttab"></a>Fält på snabbfliken Allmänt

I tabellen nedan beskrivs de fält på snabbfliken **Allmänt** som inte visas på sidan **Lagertransaktioner**.

| Fält | Beskrivning |
|---|---|
| Part | Namnet på den relevanta parten för den valda lagertransaktionen. En inköpsordertransaktion visar till exempel namnet på leverantören på inköpsordern och en försäljningsordertransaktion visar kundens namn. Det här fältet är inte tillgängligt för alla typer av lagertransaktioner. |
| Lagerreferens | Om en annan lagertransaktion är relaterad till den valda lagertransaktionen, ska du ange typen för den andra transaktionen. Om till exempel en inköpsorder markeras mot en försäljningsorder får fältet **Lagerreferens** för inköpsordertransaktionen inställningen *Försäljningsorder*. Markering sker automatiskt för direktleveransorder och koncerninterna order. När du använder markering med andra kostnadsredovisningsmetoder än *standardkostnad* och *glidande medelvärde* skapar systemet kvittningar och justeringar för de exakta transaktioner som markeras. På det här sättet kan du uppnå "faktisk" kostnadsredovisning som åsidosätter logiken för först in, först ut (FIFO), sist in först ut (LIFO) eller viktat medelvärde. |
| Lagernummer | Den specifika transaktion som är relaterad till den valda lagertransaktionen. Om till exempel en inköpsorder markeras mot en försäljningsorder får fältet **Lagernummer** för inköpsordertransaktionen försäljningsordernumret som inställning. |
| Projekt-ID | Om den valda lagertransaktionen är relaterad till ett projekt ställs det här fältet in på projektnumret. |
| Parti-ID | Det unika parti-ID som systemet har tilldelat den valda lagertransaktionen. |
| Referensparti | Om en annan lagertransaktion är relaterad till den valda lagertransaktionen, ska du ange parti-ID för den andra transaktionen. Om till exempel en inköpsorder markeras mot en försäljningsorder innehåller fältet **Referensparti** för inköpsordertransaktionen värdet på **Parti-ID** för försäljningsorderradens lagertransaktion. |
| Dimensionsnummer | Ett unikt ID som representerar kombinationen av alla lagerdimensionsvärden som är tilldelade till den valda lagertransaktionen. |
| Värde öppet | Ett värde som anger om den valda lagertransaktionen har kvittats med lagerstängningsprocessen. Om fältet har inställningen *Ja* har transaktionen inte kvittats. |
| Förväntat datum | För inleveranstransaktioner är datumet då lagerinleveransen förväntas ske. Det här fältet kan till exempel visa det förväntade inleveransdatumet på en lagerspärrorder eller ett leveransdatum på en inköpsorderrad. |
| Lagerdatum | Det här fältet ställs in när en registreringstransaktion gjordes på inleveransordern innan en fysisk inleverans bokfördes. |
| Överföring som inte är ekonomisk | Ett värde som anger om den valda lagertransaktionen är en icke-ekonomisk överföring. En icke-ekonomisk överföring sker när en ändring i lagerdimensioner inte spåras ekonomiskt på sidan **Artikelmodellgrupp**. |
| Överför parti-ID | Om den valda lagertransaktionen är en icke-ekonomisk överföring ställs det här fältet in på **parti-ID-värdet** för den andra lagertransaktionen som den valda transaktionen kvittas mot. |

## <a name="fields-on-the-updates-fasttab"></a>Fält på snabbfliken Uppdateringar

I tabellen nedan beskrivs de fält på snabbfliken **Uppdateringar** som inte visas på sidan **Lagertransaktioner**.

| Fält | Beskrivning |
|---|---|
| Fysisk verifikation | Verifikationsnumret från redovisningen där den fysiska bokföringen för den valda lagertransaktionen genererades. |
| Rutt | Den specifika routning som är relaterad till den valda lagertransaktionen. Det här fältet ställs bara in för plocklistetransaktioner för produktion där strukturlistan eller formelraden är relaterad till en specifik artikel. |
| Följesedel | Det följesedelsnummer som har registrerats för en inleveranstransaktion för en inköpsorderprodukt. |
| Fysiskt kostnadsbelopp | Beloppet som bokfördes i redovisningen för den fysiska uppdateringen. För en standardkostnadsprodukt representerar detta belopp standardkostnaden. För andra kostnadsredovisningsmetoder representerar den det viktade medelvärdet för produkten vid bokföring. |
| Fysisk intäkt | Beloppet för uppskjuten intäkt som bokfördes i redovisningen för den fysiska uppdateringen. |
| Last-ID | Om den aktuella transaktionen är relaterad till en beläggning i Transporthantering visar det här fältet det unika numret för beläggningen som inkluderade artikeln. |
| Fysiskt bokförd | Ett värde som anger om den valda lagertransaktionen har bokförts fysiskt. Om den aktuella transaktionen bokförs i redovisningen kommer det också att finnas en fysisk verifikation. |
| Ekonomiskt bokförd | Ett värde som anger om den valda lagertransaktionen har bokförts ekonomiskt. Om den aktuella transaktionen bokförs i redovisningen kommer det också att finnas en ekonomisk verifikation. |
| Fysisk kostnad har bokförts | Ett värde som anger om de fysiska tilläggen som är relaterade till den valda lagertransaktionen har bokförts. |
| Finansiell kostnad har bokförts | Ett värde som anger om de ekonomiska tilläggen som är relaterade till den valda lagertransaktionen har bokförts. |
| Ekonomisk verifikation | Verifikationsnumret i den redovisning där den ekonomiska bokföringen genererades. |
| Faktura | Det fakturanummer som exempelvis genererades för en inköpsorder eller försäljningsorder. |
| Justering | Beloppet som justerades på den valda lagertransaktionen från lagerstängningen och justeringsprocessen. |
| Resultaträkning, bokfört belopp | Det belopp för den markerade lagertransaktionen som bokfördes på vinst- och förlusträkningen. |
| Ej bokförd faktura | Fakturanumret för en relaterad inköpsorder som visas på sidan **Väntande leverantörsfaktura**. |
| Ekonomiskt stängd | Datum då transaktionen var helt kvittad. |
| Täckt FV-kvantitet | Kvantiteten faktisk/nominell vikt som täcks av kvittningen. |
| Kvittad kvantitet | Den kvantitet som har kvittats för den valda lagertransaktionen. |
| Kvittat belopp | Det värden som har kvittats för den valda lagertransaktionen. |
