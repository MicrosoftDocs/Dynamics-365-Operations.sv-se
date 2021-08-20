---
title: Fakturamatchning för leverantörsreskontra – översikt
description: Fakturamatchning i leverantörsreskontra är den process där information om leverantörsfaktura, inköpsorder och produktinleverans matchas.
author: abruer
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendInvoicePostingHistory
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "27361"
- intro-internal
ms.assetid: 9f3dace7-05d8-4974-8f85-aca2e224876c
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3c9f7c19d81a22feaeccc31a3f3d390b1a721485083c32e215b155e7896a06d7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6737440"
---
# <a name="accounts-payable-invoice-matching-overview"></a>Fakturamatchning för leverantörsreskontra – översikt

[!include [banner](../includes/banner.md)]

Fakturamatchning i leverantörsreskontra är den process där information om leverantörsfaktura, inköpsorder och produktinleverans matchas.

När du matchar dokument kallas skillnader mellan dessa dokument för matchningsavvikelser. Matchningsavvikelser jämförs med toleranserna som ställts in. Om en matchningsavvikelse överskrider toleransprocenten eller toleransmängden visas matchningsavvikelseikoner på sidan Leverantörsfaktura och på sidan Fakturahistorik och matchningsuppgifter. 

Du kan till exempel registrerar en inköpsorder med en radartikel för 1 000 batterier med priset 1,00 styck. Inköpsordern godkänns och skickas till leverantören. Leverantören levererar 1 000 batterier och du registrerar en produktinleverans med 1 000 batterier med priset 1,00 styck. Lagerkostnaden för batterierna uppdateras med det här priset. 

En faktura ankommer för 1 000 batterier med priset 1,10 styck. Din policy för juridiska personer tillåter en femprocentig nettoenhetspristolerans för denna artikelkategori. Ett pris på 1,05 vore acceptabelt, men 1,10 är inte acceptabelt. När du anger fakturainformationen identifieras en prismatchningsavvikelse och du kan spara fakturan tills avvikelsen lösts.

Du kan använda följande typer av fakturamatchning för leverantörsreskontra:

-   Matchning av fakturasummor – Matcha de totala beloppen på fakturan med de totala beloppen på inköpsordern. Den här typen av fakturamatchning inkluderar minst mängd information, så du kan använda det här alternativet för att ställa in kontroller som minimerar personaltiden som behövs för att granska information om fakturamatchning.
-   Tvåvägsmatchning – Matcha prisinformationen på fakturan med prisinformationen på inköpsordern.
-   Trevägsmatchning – Matcha prisinformationen på fakturan med prisinformationen på inköpsordern. Matcha också information om kvantiteten på fakturan med information om kvantiteten för produktinleveranserna som valts för fakturan.
-   Avgiftsmatchning – Matcha avgiftsinformation (belopp) på fakturan med avgiftsinformation (belopp) på inköpsordern.

> [!NOTE]
> Andra formulär för fakturavalidering kan fyllas i genom att använda leverantörsfakturapolicyer. 

Tvåvägsmatchning och trevägsmatchning matchar alltid prisinformation baserat på enhetspriset. Du kan även konfigurera dessa matchningspolicyer för att matcha prisinformation baserat på prissumman.
-   Matchning av nettopris per enhet – Matcha prisinformation för tvåvägsmatchning eller trevägsmatchning genom att jämföra nettopriset per enhet för varje rad på fakturan med motsvarande nettopris per enhet på inköpsordern. Nettopriset per enhet beräknas med följande formel: nettobeloppet på raden dividerat med kvantiteten för raden.
-   Matchning av prissumma – Matcha prisinformation för tvåvägsmatchning eller trevägsmatchning genom att jämföra nettobelopp (prissumma) för varje rad på fakturan med motsvarande nettobelopp på inköpsordern. Nettobeloppet beräknas med följande formel: *(Enhetspris \* Radkvantitet) + Radavgifter – Radrabatter*. När du matchar prissummor efter procent jämför systemet värden i transaktionsvalutan. När du matchar prissummor efter belopp jämför systemet värden med redovisningsvalutan. När du delvis fakturerar en inköpsorderrad, sker valideringen av prissummor-matchning på den senaste fakturan för den raden. 

Vanligtvis utförs fakturamatchningsberäkningar när du redigerar leverantörsfakturor på sidan Leverantörsfaktura. Alternativt kan fakturamatchning utföras vid behov om det behövs. Fakturamatchning vid behov kontrolleras för den juridiska personen av Uppdatera status för fakturahuvud automatiskt som Till på sidan Parametrar för leverantörsreskontra på fliken Fakturavalidering. Fakturamatchningen kan också utföras som en del av fakturagranskningsprocessen. Du kan visa resultaten från fakturamatchningen på sidan Leverantörsfaktura och relaterade fakturamatchningssidor.

## <a name="invoice-totals-matching"></a> Matchning av fakturasummor
Du kan använda matchning av fakturasummor för att se till att totala fakturabelopp inte avviker från förväntade belopp med mer än en godtagbar avvikelse. Sex summor jämförs på sidan Fakturasummamatchningsdetaljer, som du ser i följande tabell. Om den tillåtna toleransen för matchning av fakturasummor är 20 %, betraktas avvikelseprocenten 100 % för det totala rabattbeloppet som en matchningsavvikelse.

| Summafält    | Faktisk fakturasumma | Förväntad fakturasumma | Avvikelseprocent | Matchningsstatus |
|----------------|----------------------|------------------------|---------------------|--------------|
| Saldo        | 495,00               | 495,00                 | 0 %                  | Genomförda       |
| Total rabatt | 0,00                 | 9,90                   | 100 %                | Ej genomförda       |
| Avgifter        | 64,90                | 64,90                  | 0 %                  | Genomförda       |
| Moms      | 139,98               | 137,50                 | 2 %                  | Genomförda       |
| Avrundning      | 0,00                 | 0,00                   | 0 %                  | Genomförda       |
| Fakturabelopp | 699,88               | 687,50                 | 2 %                  | Genomförda       |

Matchning av fakturasummor kontrolleras för den juridiska personen av växlingsknappen Matcha fakturasummor på sidan Parametrar för leverantörsreskontra. Matchningen utförs på de förväntade fakturasummorna och de faktiska fakturasummorna. De förväntade fakturasummorna beräknas baserat på priserna, avgifterna och momsinformationen från inköpsordern och kvantiteterna från fakturan.

## <a name="two-way-price-totals-matching"></a> Tvåvägsmatchning av prissummor
Använd tvåvägsmatchning för att se till att avvikelsen mellan prisinformationen på inköpsordern och fakturan ligger inom godtagbara toleranser. Du kan jämföra prisinformation för nettobeloppet för varje rad på fakturan, och alla väntande och tidigare bokförda fakturarader, med nettobeloppet för den motsvarande inköpsorderraden. Detta kallas matchning av prissummor. 

Matchning av prissummor kan baseras på ett procentvärde, ett belopp eller en procentandel och ett belopp. 

Om en procentsatsen för toleransen för inköpsprissummor har angetts jämförs fem fält, som du ser i tabellen nedan. Eftersom procentsatsen för tolerans för inköpsprissummor är 10 % representerar procentandelen för prissummeavvikelser på 50 % en matchningsavvikelse.

| Matchningsstatus | Fakturanettobelopp | Förväntat nettobelopp | Omatchad inköpsprissumma (avvikelsebelopp) | Omatchad procentandel för inköpsprissumma (avvikelseprocent) | Toleransprocent för inköpsprissumma |
|--------------|--------------------|---------------------|--------------------------------------------------|-----------------------------------------------------------------|----------------------------------------|
| Genomförda       | 105,00             | 100,00              | 5,00                                             | 5 %                                                              | 10 %                                    |
| Ej genomförda       | 150,00             | 100,00              | 50,00                                            | 50 %                                                             | 10 %                                    |

Om en beloppet för toleransen för inköpsprissummor har angetts jämförs fem fält, som du ser i tabellen nedan. Eftersom beloppet för tolerans för inköpsprissummor är 100,00 % representerar beloppet för prissummeavvikelser på 105,00 % en matchningsavvikelse.

| Matchningsstatus | Fakturanettobelopp | Förväntat nettobelopp | Omatchad inköpsprissumma (avvikelsebelopp) | Omatchad inköpsprissumma i redovisningsvaluta (avvikelsebelopp) | Tolerans för inköpsprissumma |
|--------------|--------------------|---------------------|--------------------------------------------------|-------------------------------------------------------------------------|--------------------------------|
| Genomförda       | 150,00             | 100,00              | 50,00                                            | 50,00                                                                   | 100,00                         |
| Ej genomförda       | 205,00             | 100,00              | 105,00                                           | 105,00                                                                  | 100,00                         |

Om matchningen av prissummor ställs in med en procentuell tolerans och ett toleransbelopp, som ibland kallas för ett belopp som inte får överskridas, tas hänsyn till båda toleranser för att utvärdera om en rad har en matchningsavvikelse. Om antingen procentandelen eller beloppet överstiger toleransen, som på raderna 150,00 och 205,00 i följande tabell, har raden en matchningsavvikelse.

| Matchningsstatus | Fakturanettobelopp | Förväntat nettobelopp | Omatchad procentandel för inköpsprissumma (avvikelseprocent) | Toleransprocent för inköpsprissumma | Omatchad inköpsprissumma i redovisningsvaluta (avvikelsebelopp) | Tolerans för inköpsprissumma |
|--------------|--------------------|---------------------|-----------------------------------------------------------------|----------------------------------------|-------------------------------------------------------------------------|--------------------------------|
| Genomförda       | 105,00             | 100,00              | 5 %                                                              | 10 %                                    | 5,00                                                                    | 100,00                         |
| Ej genomförda       | 150,00             | 100,00              | 50 %                                                             | 10 %                                    | 50,00                                                                   | 100,00                         |
| Ej genomförda       | 205,00             | 100,00              | 105 %                                                            | 10 %                                    | 105,00                                                                  | 100,00                         |

Tvåvägsmatchning kontrolleras för den juridiska personen av fältet Radmatchningspolicy på sidan Parametrar för leverantörsreskontra. Beroende på valet i fältet Tillåt åsidosättning av matchningspolicy kan du välja tvåvägsmatchning för en viss leverantör, artikel eller artikel- och leverantörkombination på sidan Matchningspolicy och för en viss inköpsorder på sidan Inköpsorder.

Matchning av prissummor kontrolleras för den juridiska personen av fältet Matcha prissummor på sidan Parametrar för leverantörsreskontra. Procentsatsen för tolerans för inköpspris och toleransbeloppet (belopp som inte får överskridas) anges också på den sidan.

## <a name="two-way-net-unit-price-matching"></a> Tvåvägsmatchning av nettopris per enhet
Använd tvåvägsmatchning för att se till att avvikelsen mellan prisinformationen på inköpsordern och fakturan ligger inom godtagbara toleranser. Du kan jämföra prisinformation för nettopriset per enhet för varje artikel på fakturan. Detta kallas för matchning av nettopris per enhet. 

Nio radbelopp jämförs på sidan Fakturamatchningsdetaljer, som du ser i följande tabell. Om den tillåtna pristoleransen för matchning av nettopris per enhet är 10 %, betraktas avvikelseprocenten 22,61 % för nettopriset per enhet som en matchningsavvikelse.

| Radfält                    | Fakturavärde | Inköpsordervärde | Avvikelseprocent | Matchningsstatus |
|-------------------------------|---------------|----------------------|---------------------|--------------|
| Enhetspris                    | 55,40         | 55,38                | 0 %                  | Genomförda       |
| Prisenhet                    | 1,00          | 1,00                 | 0 %                  | Genomförda       |
| Avgifter på inköp          | 50,00         | 0,00                 | 100 %                | Ej genomförda       |
| Rabatt                      | 0,00          | 0,00                 | 0 %                  | Genomförda       |
| Rabatt i procent              | 0,00          | 0,00                 | 0 %                  | Genomförda       |
| Samköpsrabatt            | 0,00          | 0,00                 | 0 %                  | Genomförda       |
| Samköpsrabatt i procent | 0,00          | 0,00                 | 0 %                  | Genomförda       |
| Nettobelopp                    | 271,60        | 221,52               | 22,61 %              | Ej genomförda       |
| Nettoenhetspris                | 67,9000       | 55,3800              | 22,61 %              | Ej genomförda       |

Tvåvägsmatchning kontrolleras för den juridiska personen av fältet Radmatchningspolicy på sidan Parametrar för leverantörsreskontra. Beroende på valet i fältet Tillåt åsidosättning av matchningspolicy kan du välja tvåvägsmatchning för en viss leverantör, artikel eller artikel- och leverantörkombination på sidan Matchningspolicy och för en viss inköpsorder på sidan Inköpsorder. 

Matchning av nettopris per enhet kontrolleras för den juridiska personen av fältet Aktivera fakturamatchningsvalidering på sidan Parametrar för leverantörsreskontra. Procentvärdet för tolerans för nettopris per enhet kan konfigureras för artiklar, artikelgrupper, leverantörer, leverantörsgrupper, artikel- och leverantörkombinationer eller juridisk person på sidan Pristoleranser.

## <a name="two-way-price-totals-matching-and-net-unit-price-matching"></a> Tvåvägsmatchning av prissummor och matchning av nettopris per enhet
Du kan använda matchning av prissummor och matchning av nettopris per enhet tillsammans. I det här exemplet förutsätts det att följande konfiguration används:

-   Toleransen för nettopris per enhet för artikeln USB-enhet är 10 %.
-   Toleransen för matchning av prissummor för den juridiska personen är 15 % eller 500,00.

Inköpsordern innehåller följande rad.

| Artikelnummer | Kvantitet | Enhetspris | Nettobelopp |
|-------------|----------|------------|------------|
| USB-enhet   | 1 000    | 10,00      | 10 000,00  |

Tre fakturor har angetts, som du ser i följande tabell. Det finns en fakturamatchningsavvikelse för faktura 3 eftersom avvikelsen på 1 880,00 överskrider toleransbeloppet för inköpsprissummor på 500,00. För matchning av prissummor inkluderar fakturanettobeloppet alla tidigare bokförda fakturor förutom fakturan som du arbetar med för närvarande.

| Artikelnummer          | Kvantitet | Enhetspris | Nettobelopp | Prismatchning | Prissummematchning |
|----------------------|----------|------------|------------|-------------|-------------------|
| Faktura 1: USB-enhet | 800      | 10,80      | 8 640,00   | Genomförda      | Genomförda            |
| Faktura 2: USB-enhet | 100      | 10,80      | 1 080,00   | Genomförda      | Genomförda            |
| Faktura 3: USB-enhet | 200      | 10,80      | 2 160,00   | Genomförda      | Ej genomförda            |
| Summa                |          |            | 11 880,00  |             |                   |

## <a name="three-way-matching"></a>Trevägsmatchning

Använd trevägsmatchning för att se till att avvikelsen mellan prisinformationen på inköpsordern och fakturan ligger inom godtagbara toleranser, och för att säkerställa att kvantiteten på fakturan matchar kvantiteten på motsvarande produktinleveranser.

Samma radbelopp jämförs på sidan Fakturamatchningsdetaljer som för tvåvägsmatchning. Dessutom matchas kvantiteten på fakturan med produktinleveranskvantiteter som har tagits emot. Om fakturakvantiteten skiljer sig från den matchande produktinleveranskvantiteten finns det ett kvantitetsmatchningsfel.

| Radfält                    | Fakturavärde | Inköpsordervärde | Avvikelseprocent | Matchningsstatus |
|-------------------------------|---------------|----------------------|---------------------|--------------|
| Enhetspris                    | 55,40         | 55,38                | 0 %                  | Genomförda       |
| Prisenhet                    | 1,00          | 1,00                 | 0 %                  | Genomförda       |
| Avgifter på inköp          | 50,00         | 0,00                 | 100 %                | Ej genomförda       |
| Rabatt                      | 0,00          | 0,00                 | 0 %                  | Genomförda       |
| Rabatt i procent              | 0,00          | 0,00                 | 0 %                  | Genomförda       |
| Samköpsrabatt            | 0,00          | 0,00                 | 0 %                  | Genomförda       |
| Samköpsrabatt i procent | 0,00          | 0,00                 | 0 %                  | Genomförda       |
| Nettobelopp                    | 271,60        | 221,52               | 22,61 %              | Ej genomförda       |
| Nettoenhetspris                | 67,9000       | 55,3800              | 22,61 %              | Ej genomförda       |

| Radfält                     | Fakturavärde | Matchningsstatus |
|--------------------------------|---------------|--------------|
| Fakturakvantitet               | 4,00          |              |
| Totala matchade produktinleveranser | 0,00          | Ej genomförda       |

Trevägsmatchning kontrolleras för den juridiska personen av fältet Radmatchningspolicy på sidan Parametrar för leverantörsreskontra. Beroende på valet i fältet Tillåt åsidosättning av matchningspolicy kan du välja trevägsmatchning för en viss leverantör, artikel eller artikel- och leverantörkombination på sidan Matchningspolicy och för en viss inköpsorder på sidan Inköpsorder.

## <a name="charges-matching"></a> Avgiftsmatchning
Du kan använda avgiftsmatchning för att se till att avgiftsbelopp inte avviker från förväntade belopp med mer än en godtagbar avvikelseprocent. De totala beloppen för varje avgiftskod som gäller för fakturan och inköpsordern jämförs på sidan Jämför avgiftsvärden – Faktura, enligt följande tabell. Om den tillåtna toleransen för debiteringskoden är 25 %, betraktas avvikelseprocenten 99 999 999 999,99 % för licensavgiftskoden som en matchningsavvikelse.

> [!NOTE] 
> En avvikelseprocent på 99 999 999 999,99 % innebär att det förväntade beloppet som baseras på inköpsordern är noll och det riktiga beloppet på fakturan är ett positivt värde. 

| Avgiftsmatchningsstatus | Fakturaavgiftskod | Faktiskt totalt beräknat värde | Förväntat totalt beräknat värde | Avvikelsebelopp | Avvikelseprocent | Toleransprocent |
|----------------------|----------------------|-------------------------------|---------------------------------|-----------------|---------------------|----------------------|
| Ej genomförda               | Licens              | 25                            | 0                               | 25              | 99 999 999 999,99 %  | 25 %                  |
| Genomförda               | Frakt              | 200                           | 200                             | 0               | 0 %                  | 25 %                  |
| Ej genomförda               | Expediera             | 4                             | 2                               | 2               | 100 %                | 25 %                  |

Avgiftsmatchning kontrolleras för den juridiska personen av växlingsknappen Matcha avgifter på sidan Parametrar för leverantörsreskontra. Du kan ställa in avvikelsetoleransprocenter för avgifter på sidan Avgiftstoleranser.

> [!NOTE]
> Avgiftsmatchning utförs bara på avgiftskoder för vilka växlingsknappen Jämför inköpsorder och fakturavärden är vald på sidan Avgiftskoder.

## <a name="related-functionality"></a>Relaterade funktioner
Leverantörsfakturor baseras ofta på produktinleveranser som representerar faktiska leveranser snarare än på inköpsorder. Ibland matchar de fakturerade beloppen inte inköpsorderbeloppen och ibland matchar de levererade kvantiteterna inte de fakturerade kvantiteterna. Du kan göra det enklare att hantera denna information på följande sätt:
-   Skapa en leverantörsfaktura som baseras på produktinleveranser. Produktinleveranser föreslås automatiskt för fakturor, och du kan välja vilka produktinleveranser som ska användas. Du kan också välja specifika produktinleveransradartiklar från flera inköpsorder om du måste.
-   Visa och godkänn kvantitetsskillnader mellan den fakturerade kvantiteten på fakturan och den inlevererade kvantiteten på produktinleveransen. Om det finns en skillnad kan du spara fakturan och senare matcha den med en annan produktinleverans eller ändra den fakturerade kvantiteten så att den matchar den inlevererade kvantiteten.
-   Ange fakturabelopp som inte inkluderades i den ursprungliga inköpsordern så att fakturainformationen matchar den faktura du tagit emot från leverantören. Du kan jämföra avgifterna för inköpsorder med avgifterna för fakturor. Vid behov kan du lägga till avgifter till fakturor och tilldela dem till fakturarader.
-   Visa och godkänn prismatchningsavvikelser mellan fakturans nettoenhetspris och inköpsorderns nettoenhetspris. Du kan ange procentsatser för pristoleranser för juridiska personer, artiklar och leverantörer. Om leverantörens fakturaradpris inte ligger inom den acceptabla pristoleransen, kan du spara fakturan tills den godkänts för bokföring eller tills du får en korrigering från leverantören.

Mer information finns i [Trevägsmatchningspolicyer](three-way-matching-policies.md) och [Konfigurera validering av fakturamatchning för leverantörsreskontra](tasks/set-up-accounts-payable-invoice-matching-validation.md). 






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
