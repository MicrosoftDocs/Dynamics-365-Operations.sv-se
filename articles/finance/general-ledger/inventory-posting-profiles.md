---
title: Artikelbokföringsprofiler
description: Det här ämnet ger en översikt över lagerbokföringsprofiler.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28e3a3051978f921e01a929496e96909e6c32429
ms.sourcegitcommit: 00b39900d3cbdbc9ca1ab3145265007f5dc98a3f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2022
ms.locfileid: "8806381"
---
# <a name="inventory-posting-profiles"></a>Artikelbokföringsprofiler

[!include [banner](../includes/banner.md)]

Lagerbokföringsprofiler styr bokföringen av lagerredovisningens transaktioner i redovisningen. Lagerredovisningens transaktioner kan genereras från många moduler inklusive **Försäljning och marknadsföring**, **Anskaffning och inköp**, **Produktionskontroll**, med mera. Lagerredovisningens transaktioner kan bokföras när en artikel används på en försäljnings- eller inköpsorder. 

Ytterligare transaktioner för lager med underordnade lager kan bokföras:
- Varje gång ett dokument uppdateras.
- När en kundorderföljesedel eller faktura bokförs.
- När en inköpsorder genereras produktinleverans eller faktura.

Mer information finns i Lagerredovisningens transaktioner.

## <a name="inventory-transaction-overview"></a>Översikt över lagertransaktioner

Varje lagerredovisningens transaktion innehåller:
 - Antal 
 - Pris 
 - Webbplats 
 - Lagerställe 
 - Plats 

Lagerredovisningens transaktioner skapar två poster i redovisningen genom den fysiska bokföringen och den ekonomiska bokföringen. Mer information finns i [Fysiska och ekonomiska uppdateringar](/supply-chain/cost-management/physical-financial-updates.md).
Följande exempel är en inköpsorder med tre rader. Anta att hela ordern gäller för en webbplats och ett lagerställe. Varje inköpsorderrad har en enskild relaterad InventTrans-post – en så kallad lagertransaktion – och varje rad får en kvantitet på 10. I bilden nedan visas relationen mellan en inköpsorderrubrik och tre inköpsorderrader, var och en med en InventTrans-post.

![Relationsdiagram för en inköpsorder med tre rader var med en InventTrans-post.](./media/InventTransRelationship.PNG)

En kvantitet på 5 tas emot på den första inköpsorderraden. Den fullständiga kvantiteten för den andra raden och ingen kvantitet som inkom på den tredje raden i inköpsordern. Det finns nu en andra lagertransaktion relaterad till den första inköpsorderraden. Transaktionen för den andra inköpsorderraden kommer att uppdateras till **Inlevererad** och den tredje transaktionen förblir oförändrad. I bilden nedan visas relationen till den ytterligare InventTrans-posten för inköpsorderrad 1.

![Relationsdiagram för en inköpsorder med tre rader. En rad är delvis mottagen och visar två InventTrans-poster.](./media/InventTransRelationshipPartialReceipt.PNG)

I det här exemplet bokförs en verifikation i redovisningen. detta är den fysiska verifikationen. Artikelmodellgruppen är konfigurerad till att bokföra fysiskt lager, och alla artiklar använder samma artikelmodellgrupp. Lagerbokföringsprofilen använder en enda uppsättning huvudkonton. En enda verifikation skapas och InventTrans-posten kopplar både InventTrans 1 och InventTrans 2 till samma verifikation.

Sedan tas en faktura emot för den kvantitet som har inkommit på raderna 1 och 2. En annan verifikation skapas i redovisningen. detta är den ekonomiska verifikationen. Artikelmodellgruppen är konfigurerad för att bokföra finansiell inventering. Den nya andra verifikationen är relaterad till InventTrans 1 och InventTrans 2.

Beroende på kostnadsmodellen kan det finnas en tredje redovisningsbokföring för lagerredovisningstransaktionerna som är relaterade till stängning och kvittning av lagret. Mer information finns i [stängning av lager](/supply-chain/cost-management/inventory-close.md). Du kan visa information om alla lagertransaktioner genom att gå till **Lagerhantering** > **Förfrågningar och rapporter** > **Transaktioner**.

>[!Important]
> Lagertransaktionerna delas upp för varje unik kombination av lagerdimensioner och för varje deluppdatering. Detta visas i föregående exempel för deluppdateringar.

### <a name="split-inventory-based-on-inventory-dimension-example"></a>Dela upp lager baserat på lagerdimensionsexempel

Inköpsorderrad 3 i exemplet är en serialiserad artikel. Tio serienummer registreras för inköpsordern under inleveransen. Lagertransaktionen delas upp i 10 lagertransaktioner. I bilden nedan visas relationen och ytterligare lagertransaktioner, som vart och ett har ett eget serienummer för inköpsorderrad 3.

![Relationsdiagram för en inköpsorder med tre rader. En rad är serialiserad och visar ytterligare InventTrans-poster](./media/InventTransRelationshipSerialNumber.PNG)

I exemplet ovan skapas en ytterligare verifikation om varje serienummer tas emot på en enda produktinleverans. Det fysiska verifikationsfältet länkas till varje serienummer. Samma sak gäller för den ekonomiska uppdateringen när du fakturerar inköpsordern.

## <a name="inventory-transactions"></a>Lagertransaktioner

Du kan visa lagertransaktioner på sidan **Lagertransaktioner** under **Hantering av lager och lagerstyrning** eller **Kostnadshantering**. Du kan också visa lagertransaktioner relaterade till en specifik källdokumentrad – till exempel en inköpsorderrad eller försäljningsorderrad – genom att välja **Lager** och sedan välja **Transaktioner**. 

Sidan **Lagertransaktioner** innehåller följande fält.

| Fält            | Beskrivning                                 |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| Artikelnummer      | Det artikelnummer som är relaterat till transaktionen.                                                                  |
| Fysiskt datum    | Det datum då lagret ankommer till lagerstället, lämnar lagerstället, förbrukas i produktion eller produceras. Till exempel bokföringsdatumet den
Följesedelsbokföringen för en försäljningsorder eller för bokföring av produktinleverans för en inköpsorder.                             |
| Ekonomiskt datum   | Det datum då lagertransaktionen stängs och kostnaden registreras i redovisningen. Till exempel bokföringsdatumet på fakturan 
generera för försäljnings- eller inköpsorder. Uppdateringar av referensdokumentet är inte tillåtna efter att det ekonomiska datumet har fyllts i. |
| Referens        | Anger transaktionens källa och den typ av dokument som visas i fältet **Nummer**. Till exempel försäljningsorder, inköpsorder eller inleverans av överföringsorder.                                                 |
| Nummer           | Anger referens-ID för en transaktion. Om till exempel fältet **Referens** visar försäljningsorder indikerar fältet **nummer** försäljningsordernumret.                                                       |
| Inleverans (status) | För lagertransaktioner som är inleveranser visar det här fältet status för inleveransen. En inköpsorder är till exempel en inleverans, och statusen kan vara **Beställt** eller **Inköpt**.                                                            |
| Utleverans (status)   | För lagertransaktioner som är utleveranser visar det här fältet status för utleveransen. En försäljningsorder är till exempel en utförsäljning, och statusen kan vara **Har beställts** eller **Såld**.                         |
| Antal         | Lagertransaktionens kvantitet. Positiva tal används för inleveranser till lager medan negativa tal används för utleveranser från lagret.                                                                                                                          |
| Enhet             | Måttenheten som kvantiteten uttrycks i.                                                                                   |
| FV-kvantitet      | Kvantitet i faktisk/nominell vikt för transaktionen. Mer information finns i [Om artiklar med faktisk/nominell vikt](/dynamicsax-2012/appuser-itpro/about-catch-weight-items.).       |
| FV-enhet          | Måttenheten faktisk/nominell vikt som kvantitet i faktisk/nominell vikt uttrycks i.                                                         |
| Kostnadsbelopp      | Den sista kostnaden för lagertransaktionen. Det här fältet fylls i när en transaktion uppdateras ekonomiskt. Beroende på kostnadsredovisningsmetodik kan lagerstängning och justeringsprocess uppdatera det här fältet.                            |

## <a name="inventory-status"></a>Lagerstatus

Varje lagertransaktion har en status som visas i antingen fältet **Inleverans** eller **Utleverans**. Fältet som används beror på typen av lagertransaktioner. Inleveranser är transaktioner som ökar lagret. En inköpsorder med en positiv kvantitet eller en försäljningsorderretur med negativ kvantitet. Problem är lagertransaktioner som minskade lagret. En försäljningsorder med en positiv kvantitet eller en inköpsorderretur med negativ kvantitet.

### <a name="receipt-status"></a>Inleveransstatus

Följande tabell beskriver varje status **Inleverans**.

| **Inleveransstatus** | **Beskrivning**       |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Beställt            | Den ursprungliga statusen för alla lagertransaktioner som representerar en inleverans. Det kan till exempel vara inköpsorder med en positiv kvantitet, tillverkningsorder eller försäljningsorderreturer med negativ kvantitet.                                                   |
| Registrerat         | Den här statusen används när en mottagningsprocess med två steg används eller när artikelinleverans används för att visa att produkten har anlänt. Det används när batch- eller serienummer är "fördelade" eller registrerade på ordern. Mer information om artikel införsel finns i [Införselöversikt](/supply-chain/inventory/arrival-overview.md). |
| Mottaget           | Det här statusvärdet används när transaktionen uppdateras fysiskt. För en inköpsorder är det då produktinleverans bokförs. För en försäljningsorderretur är det då följesedeln bokförs.                                                                            |
| Inköpt          | Det här statusvärdet används när transaktionen uppdateras ekonomiskt. För en inköpsorder eller försäljningsorderretur är det då fakturan genereras.                                                                                             |

### <a name="issue-status"></a>Utleveransstatus

Följande tabell beskriver varje status **Utleverans**.

| **Utleveransstatus**  | **Beskrivning**            |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| Har beställts          | Den ursprungliga statusen för alla lagertransaktioner som representerar en utleverans. Det kan till exempel vara försäljningsorder med en positiv kvantitet, tillverkningsorder, strukturlista eller formulärrader eller försäljningsorderreturer med negativ kvantitet.                                             |
| Reserverat beställt  | Lagerstatusen visar att lager reserveras mot en order som har skapats men ännu inte mottagits fysiskt i lagret. När lagret har tagits emot uppdateras status automatiskt till **Reserverat fysiskt**. Mer information om reservationer finns i [Reservera lagerkvantiteter](/supply-chain/inventory/reserve-inventory-quantities.md). |
| Fysiskt reserverat | Den här statusen visar att lagret har tilldelats eller reserverats mot en viss order. När lager är reserverat är det inte fysiskt tillgängligt för andra beställningar.                                 |
| Plockad         | Det visar att lagret har plockats från lagerstället. Lagret finns fortfarande fysiskt på lagerstället, har inte tagits bort, men det är inte tillgängligt för andra order.  |
| Avdraget          | Det här statusvärdet används när transaktionen uppdateras fysiskt. För en försäljningsorder är detta när följesedeln bokförs. För en inköpsorderretur, detta när produktinleveransen bokförs.                                                                      |
| Sålt              | Det här statusvärdet används när transaktionen uppdateras ekonomiskt. För en inköpsorder eller försäljningsorder är det då fakturan genereras.|

Mer information om lagertransaktionerna finns i [Detalj om lagertransaktioner](/supply-chain/inventory/inventory-transactions-details.md).

## <a name="configure-an-inventory-posting-profile"></a>Konfigurera en lagerbokföringsprofilen

Följ dessa steg för att konfigurera en profil för inventering:

1.  Öppna **Lagerhantering** > **Inställningar** > **Bokföring** > **Bokföring**.
2.  Välj fliken för typen av transaktion. Välj till exempel **Inköpsorder**.
3.  Välj alternativknappen för inläggstypen. Välj till exempel **Inköpsomkostnad för utgift**.
4.  Välj **Ny**.
5.  I fältet **Artikelkod** väljer du ett alternativ för **Tabell**, **Grupp**, **Alla** eller **Kategori**. Om du till exempel vill konfigurera en bokföringsprofil för en specifik artikelgrupp väljer du **Grupp**.
     - Om du väljer **Table** i steg 5 väljer du, välj det specifika artikelnumret för postningsprofilen i fältet **Artikelrelation**.
     - Om du väljer **Grupp** i steg 5 väljer du **Artikelgrupp** för bokföringsprofilen i fältet **Artikelrelation**.
     - Om du väljer **Alla** i steg 5 lämnas fältet **Artikelrelation** tomt.
     - Om du väljer **Kategori** i steg 5 lämnas fältet **Artikelrelation** tomt. Använd fältet **Kategorirelation** för att välja kategori för bokföringsprofilen.

6.  I fältet **Kontokod** väljer du ett alternativ för **Tabell**, **Grupp** eller **Alla**. Om du till exempel vill använda bokföringsprofilen för alla leverantörer väljer du **Alla**.
     - Om du väljer **Tabell** i steg 5 väljer du Leverantörsnummer för bokföringsprofilen i fältet **Kontorelation**.
     - Om du väljer **Grupp** i steg 5 väljer du Leverantörsgrupp för bokföringsprofilen i fältet **Kontorelation**.
     - Om du väljer **Alla** i steg 5 kommer fältet **Kontorelation** vara tomt.

7.  Om du vill associera en viss momsgrupp som har den valda bokföringstypen, väljer du en **momsgrupp**. Om det här fältet tomt gäller bokföringstypen för alla befintliga momsgrupper. Bokföring som anges för momsgrupper gäller endast försäljnings- och köptransaktioner.
8.  Ange kontonumret för att bokföra kontotypen i fältet **Huvudkonto**. Om ett kontonummer inte har skapats för att användas som kontotyp kan du skapa ett nytt konto. Du skapar ett nytt konto på sidan **Information om huvudkonton** i Redovisning.

## <a name="additional-resources"></a>Ytterligare resurser

Varje flik på sidan **Lagerbokföringsprofil** relaterar till en redovisning i Dynamics 365 Supply Chain Management. Mer information finns i:
-   [Bokföring av försäljningsorder](sales-order-posting.md)
-   [Bokföring av inköpsorder](purchase-order-posting.md)
-   [Lagerbokföring](inventory-posting.md)
-   [Bokföring av produktionskontroll](production-posting.md)
-   [Bokföring av standardkostnadsavvikelse](standard-cost-variance-posting.md)
