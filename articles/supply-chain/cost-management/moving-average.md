---
title: Rörligt genomsnitt
description: Glidande medelvärde är en beständig kostnadsredovisning som baseras på principen om medelvärde där kostnaderna för lagerutleveranser inte ändras när inköpskostnaden gör det. Skillnaden kapitaliseras och baseras på en proportionell beräkning. Beloppet som kvarstår kostnadsförs.
author: AndersGirke
manager: tfehr
ms.date: 08/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 65531
ms.assetid: dfd10099-8f7f-44b1-917e-df37c2fe8773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb0472a0d2ac9b552cd16e4d6bf516a876ea4a0e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437509"
---
# <a name="moving-average"></a>Rörligt genomsnitt

[!include [banner](../includes/banner.md)]

Glidande medelvärde är en beständig kostnadsredovisning som baseras på principen om medelvärde där kostnaderna för lagerutleveranser inte ändras när inköpskostnaden gör det. Skillnaden kapitaliseras och baseras på en proportionell beräkning. Beloppet som kvarstår kostnadsförs.

När du använder rörligt genomsnitt stöds inte lagerkvittningar och lagermarkering. Lagerstängning påverkar inte produkter som har rörligt genomsnitt som lagermodellgruppen och genererar inte alla kvittningar mellan transaktionerna.

Följande är förutsättningar när du använder rörligt genomsnitt för kostnad som en kostnadsredovisningsmetod.

1. På sidan **Artikelmodellgrupper** ställer du in en artikelmodellgrupp som har valts i fältet **rörligt genomsnitt** i fältet **Lagermodell**.

    > [!NOTE]
    > Som standard när **rörligt genomsnitt** väljs, väljs också fälten **Bokför fysiskt lager** och **Bokför ekonomiskt lager**.

1. På sidan **Bokföring** tilldela konton på **Prisavvikelse för rörligt genomsnitt**. Du använder kontot **Prisdifferens för rörligt genomsnitt** när kostnader måste vara proportionella till utgifter. Detta inträffar i följande två situationer:
    - Detta inträffar på grund av en skillnad mellan en kostnad i inköpsinleverans och inköpsfakturan och på grund av en skillnad mellan den ursprungliga lagerkvantitet och kvantiteten för aktuell lagerbehållning.
    - Transaktionerna gör lagret från negativt till noll och det finns en skillnad mellan transaktionskostnaden och den aktuella kostnaden för rörligt genomsnitt.

1. På sidan **Bokföring** tilldelar du konton till kontona **Kostnadsomvärdering för rörligt genomsnitt** på fliken **Lager**. Du använder kontot **Kostnadsomvärdering för rörligt genomsnitt** när du vill justera kostnaden för rörligt genomsnitt för en produkt till ett nytt enhetspris.

1. På sidan **Frisläppta produkter** tilldelar du artikelmodellgruppen för rörligt genomsnitt till produkten.

    > [!NOTE]
    > Lagerslutprocessen stänger bara redovisningsperioden. Den påverkar inte produkter som har rörligt genomsnitt tilldelat dem som en artikelmodellgrupp.

## <a name="convert-to-the-moving-average-costing-method"></a>Konvertera till kostnadsredovisningmetoden för rörligt genomsnitt

Produkter kan konverteras till att använda lagervärderingsmetoden för rörligt genomsnitt. Den här typen av konvertering utförs oftast vid årets slut, när den sista månaden under innevarande året har stängts. Den görs genom att använda produktens aktuella kostnadsredovisningsmodell. Du kan ändra din lagerkostnadsredovisningsmetod från en kostnadsredovisningsmetod som baseras på genomsnittlig kostnad eller standardkostnad till en metod som baseras på rörligt genomsnitt.

Om du ändrar din kostnadsredovisningmetod från en metod för standardkostnadsredovisning till en metod för rörligt genomsnitt måste du utföra följande uppgifter:

1. Göra justeringar för att få ned lagerkvantiteter och värden till 0 (noll).
1. Efter att lagervärdet och kvantiteten är 0 (noll) ändrar du artikelmodellgruppen till rörligt genomsnitt.
1. Gör justeringar för att få tillbaka kvantitet och värde till lagret.

Du kan inte ändra din metod för lagerkostnadsredovisning från en metod för rörligt genomsnitt till metoden först in, först ut (FIFO), metoden sist in, först ut (LIFO) eller metoden viktat genomsnitt.

> [!NOTE]
> Det är en manuell process att konvertera från standardkostnad till rörligt genomsnitt.

I följande exempel visas effekten av att använda kostnadsredovisningmetoden för rörligt genomsnitt. Det finns fyra konfigurationer:

- Inköpsorder och proportionell skillnad mellan utgifter och kostnader
- Produkt med rörligt genomsnitt och lagerjustering
- Rörligt genomsnitt med produktion
- Rörligt genomsnitt med en bakåtdaterad etransaktion

## <a name="purchase-order-and-proportionally-expensed-cost-difference"></a>Inköpsorder och proportionell skillnad mellan utgifter och kostnader

Med rörligt genomsnitt bestäms produktens kostnad av inköpinleveransen. När inköpsfakturan bokförs, om det finns en kostnadsskillnad mellan inköpinleveransen och inköpsfakturan, justeras skillnaden proportionellt mot de aktuella produkterna i lager och eventuella resterande belopp är utgifter.

I det här exemplet skapas en inköpsorder och inlevereras som en kostnad och inköpsfakturan bokförs med en annan kostnad.

1. Skapa en inköpsorder för en kvantitet på 2 och ett enhetspris på 10,00.
1. Skapa en inköpinleverans för produkten.
1. Skapa en försäljningsorder för en kvantitet på 1 och ett enhetspris på 10,00.
1. Skapa en inköpsfaktura för en kvantitet på 2 och ett enhetspris på 12,00.

Skillnaden i enhetspris på 2,00 bokförs till kontot för Prisavvikelse för rörligt genomsnitt när inköpsfakturan bokförs. Anledningen är att två produkter köps in till en kostnad på 20,00. En av produkter såldes för ett enhetspris på 10,00. Inköpsfakturan bokfördes med enhetspriset på 12,00 med kvantiteten 2. Enhetspriset för produkten kan inte bokföras som 14,00.

## <a name="moving-average-product-and-inventory-adjustment"></a>Produkt med rörligt genomsnitt och lagerjustering

Om du behöver justera en produkts rörliga genomsnittskostnad tillåts lagerjusteringar per dagens datum. Du kan inte bakåtdatera en lagerjustering för att korrigera produktens rörliga genomsnittskostnad. Du kan inte ha det kostnadskalkylerade flödet genom efterföljande transaktioner.

I det här exemplet justeras den rörliga genomsnittskostnaden för en produkt.

1. Välj produkten som du vill justera den rörliga genomsnittskostnaden för. 

 > [!NOTE]
 > Sidan **Omvärdering för rörligt genomsnitt** undersöker tillgängligt lager för en produkt. Den markerade produkten har en bokförd kvantitet på 1, ett bokfört värde på 12,00, en bokförd enhetskostnad på 12,00 och en enhetskostnad på 12,00.
    
1. Uppdatera fältet **Enhetskostnad** till 16,00. Systemet beräknar de kvarvarande fälten.
1. Justeringen bokförs.

> [!NOTE]
> Du kan bara justera den rörliga genomsnittskostnad per dagens datum.

På sidan **Kvittningar för verifikationen** kan du se en justering på 4,00 som bokförs på kontot för rörligt genomsnitt.

## <a name="moving-average-with-production"></a>Rörligt genomsnitt med produktion

Rörligt genomsnitt stöder tillverkade artiklar. Om du tänker använda rörligt genomsnitt i en produktionsmiljö, ska skjutreglaget **Använd uppskattad självkostnad** på sidan **Produktionkontrollparametrar** väljas. Det innebär att självkostnaden som beräknas vid uppskattningen används i stället för den verkliga självkostnaden för strukturlisteberäkning.

## <a name="moving-average-with-a-backdated-transaction"></a>Rörligt genomsnitt med en bakåtdaterad etransaktion

Bakåtdaterade transaktioner tilldelas den aktuella rörliga genomsnittskostnaden och produktens fysiska kvantitet uppdateras, men produktens rörliga genomsnittskostnad påverkas inte. I den här rörliga genomsnittskostnaden bokförs en bakåtdaterad transaktion för en rörlig genomsnittskostnad.

1. Skapa en justering för lager för produkten med rörlig genomsnittskostnad för en kvantitet på 1 och en kostnad på 20,00.
1. Lagertransaktionhistoriken för produkten skulle likna följande:
    - En lagertransaktion på 1, en kostnad på 16,00, bokföringsdatumet 15 januari och transaktionsdatumet 15 januari.
    - En lagertransaktionsjustering på 1, en kostnad på 20,00, bokföringsdatumet 1 januari och transaktionsdatumet 15 januari.
1. Bokför justeringen.

På sidan **Lagertransaktioner** kan du se att 4,00 är utgifter, eftersom det aktuella rörliga genomsnitten för produkten är 16,00. Du kan bokföra tidigare, men skillnaden i kostnad är kostnadsfört, så den rörliga genomsnittskostnaden påverkas inte.

## <a name="negative-inventory-balances"></a>Negativa lagersaldon

Transaktioner hanteras på olika sätt beroende på om den nya lagerbehållningen efter transaktionen är negativ, noll eller positiv.

### <a name="new-balance-is-negative-or-zero"></a>Nytt saldo är negativt eller noll

Om den nya lagerbehållningen är negativ eller noll, kostnadsredovisas transaktionen till de aktuella genomsnittskostnaderna. Om det finns en skillnad mellan inköpspriset och de aktuella genomsnittskostnaderna bokförs det i **Prisavvikelse för rörligt genomsnitt**.

### <a name="new-balance-is-positive"></a>Nytt saldo är positivt

Om den nya lagerbehållningen är positiv efter transaktionen delas transaktionen upp i två delar och kostnaden på olika sätt summeras i följande tabell.

| Del | beskrivning |
|---|---|
| Kvantitet från negativ till noll | I lagret används den aktuella kostnaden för rörligt genomsnitt för artikeln i stället för transaktionskostnaden för den del av inleveranskvantiteten som ökar saldot i lagerbehållningen från negativ till noll. Skillnaden mellan transaktionskostnaden och den aktuella kostnaden för rörligt genomsnitt bokförs till **Prisavvikelse för rörligt genomsnitt**. |
| Kvantitet från noll till positiv | I lagret används transaktionskostnaden för den del av inleveranskvantiteten som ökar saldot i lagerbehållningen från noll till positiv.                                                  |

## <a name="inventory-value-report"></a>Lagervärderapport

I det här exemplet på rörligt genomsnitt skrivs rapporten om lagervärde ut för att stödja den aktuella rörliga genomsnittsberäkningen för en produkt. Rapporten om lagervärde kan skriva ut transaktionerna i kronologisk ordning, tillsammans med kostnaden för att stödja beräkningen av rörliga genomsnittskostnad för en produkt. Rapporten visar den nya kostnaden för rörligt genomsnitt för produkten. I dialogrutan **Rapporter i lagervärde** kan du med ett datumintervall välja **Transaktionstid** eller **Bokföringsdatum** att sortera rapporten efter. Alternativet **Bokföringsdatum** är hur rapporten skrivs ut traditionellt. Alternativet **Transaktionstid** är det faktiska datum då transaktionen rapporteras och den rörliga genomsnittskostnaden för produkten uppdateras. Du kan skriva ut rapporten om lagervärde genom att använda alternativet **Sortering av transaktionstid** om du vill se kostnadsberäkningen för rörligt genomsnitt över tid. I följande tabell visas de transaktioner för produkten som rapporten skrivs ut för när alternativet **Sortering av transaktionstid** används.

| Transaktionstid | Datum         | transaktionstyp           | Kvantitet | Belopp | Genomsnittlig enhetskostnad |
|------------------|--------------|----------------------------|----------|--------|-------------------|
|                  | 1 oktober    | Ingående saldo          | 0        | 0,00   | 0,00              |
| 8 oktober        | 28 september | Bakåtdaterad inleverans          | 1        | 16,00  | 16,00             |
| 3 oktober        | 3 oktober    | Inköpsinleverans           | 2        | 20,00  | 12,00             |
| 5 oktober        | 5 oktober    | Försäljningsorder                | -1       | -10.00 | 13,00             |
| 7 oktober        | 7 oktober    | Inköpsfaktura           |          | 2,00   | 14,00             |
| 8 oktober        | 8 oktober    | Omvärdering av rörligt genomsnitt |          | 4.00   | 16.00             |
|                  | 31 oktober   | Totalt                      | 2        | 32.00  | 16.00             |

> [!NOTE]
> Du kan inte stämma av redovisningen med lager genom att använda alternativet **Sortering av transaktionstid**. Rapporten måste skrivas ut genom att använda alternativet **Bokföringsdatum**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]