---
title: Försäljning och marknadsföring
description: Du kan använda Försäljning och marknadsföring för att hämta, spara och använda olika typer av data i försäljningsflödet. Informationen inkluderar den ursprungliga försäljningsinsatsen, framtida uppföljningsåtgärder och ytterligare försäljning.
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 92303
ms.assetid: 65ca9992-bbfa-4224-bf0e-067a25c7e6a4
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4de2ac36ec13f95c7603d097a0800b317014bbd0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "321074"
---
# <a name="sales-and-marketing"></a>Försäljning och marknadsföring

[!include [banner](../includes/banner.md)]

Du kan använda Försäljning och marknadsföring för att hämta, spara och använda olika typer av data i försäljningsflödet. Informationen inkluderar den ursprungliga försäljningsinsatsen, framtida uppföljningsåtgärder och ytterligare försäljning.

<a name="marketing"></a>Marknadsföring
---------

Du använder marknadskampanjer och aktiviteter för att hitta och bygga relationer med potentiella kunder, så att de första interaktionerna kan utvecklas till försäljningsrelationer. Följande processflöde visar affärsprocessen för marknadsföring. [![Affärsprocess för marknadsföring](./media/marketing01.jpg)](./media/marketing01.jpg)

### <a name="relationships"></a>Relationer

Inom försäljning och marknadsföring kan de första interaktionerna som du har med potentiella kunder uppstå i olika situationer. Du kanske exempelvis hittar en potentiell kund medan du deltar i en mässa eller kanske har ett möjligt lead med en kund efter att din organisationen har kört en massutskickskampanj. Det är mycket viktigt att du förstår flödet för en parts enhet innan denne blir en kund. Följande bild visar flödet för enhetsrelationer när en potentiell kund blir en verklig kund. [![SalesandMarketing01](./media/salesandmarketing01.jpg)](./media/salesandmarketing01.jpg)

### <a name="campaigns"></a>Kampanjer

En kampanj riktar sig till kontakter för prospekt, leads, affärstillfällen och kunder som har valt att delta i kampanjen. I Microsoft Dynamics 365 for Finance and Operations kan du skapa flera olika typer av kampanjer såsom telemarketing, E-postutskick och E-postkampanjer för att maximera din kundpotential. När kampanjen pågår och du får positiva svar kan du inleda försäljningsprocessen med de mottagare som har svarat positivt på kampanjen.

## <a name="sales"></a>Försäljning
Du kan använda försäljningsfunktionen för att skapa offerter, mer- och korsförsäljning till nya och befintliga kunder, försäljningsorder och kundfakturor. Följande processflöde visar affärsprocessen för försäljning. [![Affärsprocess för försäljning](./media/sales01.jpg)](./media/sales01.jpg)

### <a name="sales-quotations"></a>Försäljningsofferter

Du kan skapa försäljningsofferter för att ge kunder ett erbjudande om varor eller tjänster som du kommer att tillhandahålla. En kund kan begära en offert eller du kan skapa en offert som svar på en begäran från en potentiell eller befintlig kund. När kunden godkänner försäljningsofferten kan du konvertera den till en försäljningsorder.

### <a name="up-sellcross-sell"></a>Merförsäljning/korsförsäljning

Merförsäljning och korsförsäljning är tekniker för att sälja produkter när en order har matats in för en kund. Merförsäljning går ut på att föreslå en annan produkt i stället för den aktuella produkten. Korsförsäljning går ut på att föreslå en annan produkt utöver den aktuella produkten. Du kan skapa specifika regler för att visa när en produkt bör föreslås som en korsförsäljnings- eller merförsäljningsprodukt i samband med att du ställer in produktlistor.

### <a name="sales-orders"></a>Försäljningsorder

När du skapar en ny försäljningsorder måste du välja vilken typ av försäljningsorder som ska skapas. Det finns fem alternativ. **Obs!** När du har skapat en försäljningsorder kan du ändra vilken ordertyp som helst förutom typen **Artikelbehov** om försäljningsordern har statusen **Levererad**.

| Typ av försäljningsorder  | Beskrivning                                                                                                                                                                                                                                                                                            |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Journal           | Använd den här typen som ett utkast för en försäljningsorder. Den här typen påverkar inte lagerkvantiteter och skapar inte artikeltransaktioner.                                                                                                                                                                    |
| Abonnemang      | Använd den här typen för återkommande order. När ordern faktureras sätts orderstatusen automatisk till en öppen order. Levererad kvantitet som fakturerats och resterande leveranser uppdateras. Du kan inte använda den här försäljningsordertypen om du använder funktionen Lagerstyrning. |
| Försäljningsorder       | Använd den här typen när en kund har lagt eller bekräftat en order.                                                                                                                                                                                                                                        |
| Returnerad order    | Använd den här typen om en kund returnerar en artikel. Ett artikelnummer för returnering (RMA-nummer) tilldelas automatiskt.                                                                                                                                                                                            |
| Artikelbehov | Den här typen skapas automatiskt när en artikelförsäljning görs via ett projekt.                                                                                                                                                                                                                       |

### <a name="sales-agreements"></a>Försäljningsavtal

Ett försäljningsavtal är ett kontrakt i vilket kunden förbinder sig att köpa en produkt i en viss mängd eller för ett visst ett belopp över tid, i utbyte mot specialpriser och -rabatter. Priserna och rabatterna i försäljningsavtalet åsidosätter eventuella priser och rabatter som anges i andra befintliga handelsavtal. Ett försäljningsavtal gäller för en definierad period. Det begärda transportdatumet som anges för en försäljning på sidan **Försäljningsorder** ska vara inom giltighetsperioden. Som standard är ett försäljningsavtal spärrat. Du kan enbart beställa via ett försäljningsavtal om det är inställt på **Giltigt**.

### <a name="backorders"></a>Restorder

När du registrerar och validerar order måste eventuella restorder och undantag behandlas innan du kan slutföra försäljningen. Restorder är antingen inköpsorder som ännu inte har mottagits från en leverantör eller försäljningsorder som ännu inte har levererats till en kund. Det är viktigt att du följer upp restorder. Om varor från en leverantör är försenade kanske du till exempel måste ändra leveransdatum till en kund och sedan informera kunden om förseningen. Du kan visa restorder efter artikel, kund eller leverantör.

#### <a name="viewing-backorders-by-item"></a>Visa restorder efter artikel

Genom att visa restorder efter artikel kan du följa upp förväntat transaktionsflöde för en viss artikel. Du kan till exempel kontrollera följande information:

-   Antalet försäljningsorder som har lagts för en artikel.
-   Om varuleveranser från leverantörer fortfarande saknas.
-   Om fler artiklar ska vara beställas så att du kan leverera alla försäljningsorder i tid.

Genom att göra den här kontrollen kan svara du på förfrågningar från kunder om tidpunkten för leverans av artikeln. Du kan dessutom prioritera försäljningsrestorder och dela artiklarna som finns i lager mellan order.

#### <a name="viewing-backorders-by-customer"></a>Visa restorder efter kund

I översikten över restorder efter kund ser du statusen för kundens restorder. Kontrollen är användbar när du måste svara kunder som väntar på artiklar som har försenats.

#### <a name="viewing-backorders-by-vendor"></a>Visa restorder efter leverantör

När du visar restorder efter leverantör kan du följa upp uteblivna leveranser eller visa förväntade leveransdatum. Kontrollen gör det också enklare att prioritera restorder när varor inkommer från leverantörer och försäljningsorder måste plockas för leverans.

### <a name="invoices"></a>Fakturor

Du kan skapa tre typer av fakturor under försäljningsprocessen:

-   Kundfaktura
-   Fritextfaktura
-   Proformafaktura

#### <a name="customer-invoice"></a>Kundfaktura

En kundfaktura är en räkning som en organisation ger till en kund i samband med en försäljning. Du kan skapa den här typen av kundfaktura på basis av en försäljningsorder som innehåller en rubrik och en eller flera rader för artiklar eller tjänster. Kundfakturan avslutar cykeln med försäljningsordern, följesedeln och försäljningsfakturan.  

Du kan bokföra och skriva ut en enskild kundfaktura, baserad på en försäljningsorder eller en följesedel och datum. Du kan även bokföra och skriva ut flera kundfakturor samtidigt på basis av följesedlar och datum. När du bokför en enstaka kundfaktura med hjälp av försäljningsordern uppdateras kvantiteten **Fakturarest** för varje artikel med summan av de fakturerade kvantiteterna från den valda försäljningsordern.  

Om båda kvantiteterna **Fakturarest** och **Leveransrest** för alla artiklar på försäljningsordern är lika med 0 (noll) ändras statusen för försäljningsordern till **Fakturerad**. Om kvantiteten i något av fälten inte är lika med 0 (noll) ändras inte försäljningsorderns status och du kan mata in ytterligare fakturor. Om du vill bokföra och skriva ut en eller flera kundfakturor baserat på följesedlar måste du redan ha bokfört minst en följesedel för varje försäljningsorder. Kundfakturan baseras på följesedlarna och återspeglar de angivna kvantiteterna.  

Du kan skapa en kundfaktura som baseras på de artiklar på följesedeln som har levererats hittills, även om alla artiklar för en viss försäljningsorder ännu inte har levererats. Du kanske vill göra detta om exempelvis den juridiska personen utfärdar en faktura per kund och månad för att täcka alla leveranser du skickar den månaden. Varje följesedel representerar en del av eller hela leveransen av artiklarna på försäljningsordern.  

När du bokför fakturan uppdateras kvantiteten **Fakturarest** för varje artikel med summan av de levererade kvantiteterna från de valda följesedlarna. Om båda kvantiteterna **Fakturarest** och **Leveransrest** för alla artiklar på försäljningsordern är lika med 0 (noll) ändras statusen för försäljningsordern till **Fakturerad**. Om kvantiteten inte är lika med 0 (noll) ändras inte försäljningsorderns status och du kan mata in ytterligare fakturor. Lagertransaktioner uppdateras med fakturanumret och statusen på försäljningsorderraden ändras till **Fakturerad**.

#### <a name="free-text-invoice"></a>Fritextfaktura

En fritextfaktura är en faktura som inte är kopplad till en försäljningsorder. Den innehåller orderrader som inkluderar redovisningskonton, fritextbeskrivningar och en försäljningssumma. Du kan inte ange ett artikelnummer på den här typen av faktura och du måste ange korrekt momsinformation. Ett huvudkonto för försäljningen visas på varje fakturarad. Kundsaldot bokförs på samlingskontot från bokföringsprofilen som används för fritextfakturan.

#### <a name="pro-forma-invoice"></a>Proformafaktura

En proformafaktura är en faktura som förbereds som en uppskattning av det faktiska fakturabeloppet innan fakturan bokförs. Du kan skriva ut en proformafaktura för antingen en kundfaktura eller en fritextfaktura.

### <a name="additional-resources"></a>Ytterligare resurser

#### <a name="blogs"></a>Bloggar

Du hittar en översikt över en försäljningsprocess inlägget [hur försäljning fungerar i Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/05/15/how-sales-work-in-dynamics-365-for-finance-and-operations).
