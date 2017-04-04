---
title: "Rörligt genomsnitt"
description: 
author: YuyuScheller
manager: AnnBe
ms.date: 2016-03-17 15 - 16 - 47
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 65531
ms.assetid: dfd10099-8f7f-44b1-917e-df37c2fe8773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: e75016694e63dbc26f8d4c4ae73204966ca28dcf
ms.lasthandoff: 03/29/2017


---

# <a name="moving-average"></a>Rörligt genomsnitt



Följande är förutsättningar när du använder rörligt genomsnitt för kostnad som en kostnadsredovisningsmetod.
1.  På sidan **Artikelmodellgrupper** ställer du in en artikelmodellgrupp som har valts i fältet rörligt genomsnitt i fältet **Lagermodell**.
    | **Obs! **                                                                                                                                |
    |-----------------------------------------------------------------------------------------------------------------------------------------|
    | Som standard när rörligt genomsnitt väljs, väljs också fälten **Bokför fysiskt lager** och **Bokför ekonomiskt lager**. |

2.  På sidna **Bokföring** tilldelar du konton till kontona **Prisdifferens för rörligt genomsnitt** och **Kostnadsomvärdering för rörligt genomsnitt** på sidan **Lager** . Du använder kontot **Prisdifferens för rörligt genomsnitt** när kostnader måste vara proportionella till utgifter. Detta inträffar på grund av en skillnad mellan en kostnad i inköpsinleverans och inköpsfakturan och på grund av en skillnad mellan den ursprungliga lagerkvantitet och kvantiteten för aktuell lagerbehållning. Använd kontot **Kostnadsomvärdering för rörligt genomsnitt** när du vill justera kostnaden för rörligt genomsnitt för en produkt till ett nytt enhetspris.
3.  På sidan **Frisläppta produkter** tilldelar du artikelmodellgruppen för rörligt genomsnitt till produkten.

| **Obs! **                                                                                                                                                     |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Lagerslutprocessen stänger bara redovisningsperioden. Den påverkar inte produkter som har rörligt genomsnitt tilldelat dem som en artikelmodellgrupp. |

## <a name="convert-to-the-moving-average-costing-method"></a>Konvertera till kostnadsredovisningmetoden för rörligt genomsnitt
Produkter kan konverteras till att använda lagervärderingsmetoden för rörligt genomsnitt. Den här typen av konvertering utförs oftast vid årets slut, när den sista månaden under innevarande året har stängts. Den görs genom att använda produktens aktuella kostnadsredovisningsmodell. Du kan ändra din lagerkostnadsredovisningsmetod från en kostnadsredovisningsmetod som baseras på genomsnittlig kostnad eller standardkostnad till en metod som baseras på rörligt genomsnitt. Om du ändrar din kostnadsredovisningmetod från en metod för standardkostnadsredovisning till en metod för rörligt genomsnitt måste du utföra följande uppgifter:
1.  Göra justeringar för att få ned lagerkvantiteter och värden till 0 (noll).
2.  Efter att lagervärdet och kvantiteten är 0 (noll) ändrar du artikelmodellgruppen till rörligt genomsnitt.
3.  Gör justeringar för att få tillbaka kvantitet och värde till lagret.

Du kan inte ändra din metod för lagerkostnadsredovisning från en metod för rörligt genomsnitt till metoden först in, först ut (FIFO), metoden sist in, först ut ((LIFO) eller metoden viktat genomsnitt.
| **Obs! **                                                                      |
|-------------------------------------------------------------------------------|
| Det är en manuell process att konvertera från standardkostnad till rörligt genomsnitt. |

I följande exempel visas effekten av att använda kostnadsredovisningmetoden för rörligt genomsnitt. Det finns fyra konfigurationer:
-   Inköpsorder och proportionell skillnad mellan utgifter och kostnader
-   Produkt med rörligt genomsnitt och lagerjustering
-   Rörligt genomsnitt med produktion
-   Rörligt genomsnitt med en bakåtdaterad etransaktion

## <a name="purchase-order-and-proportionally-expensed-cost-difference"></a>Inköpsorder och proportionell skillnad mellan utgifter och kostnader
Med rörligt genomsnitt bestäms produktens kostnad av inköpinleveransen. När inköpsfakturan bokförs, om det finns en kostnadsskillnad mellan inköpinleveransen och inköpsfakturan, justeras skillnaden proportionellt mot de aktuella produkterna i lager och eventuella resterande belopp är utgifter. I det här exemplet skapas en inköpsorder och inlevereras som en kostnad och inköpsfakturan bokförs med en annan kostnad.
1.  Skapa en inköpsorder för en kvantitet på 2 och ett enhetspris på 10,00.
2.  Skapa en inköpinleverans för produkten.
3.  Skapa en försäljningsorder för en kvantitet på 1 och ett enhetspris på 10,00.
4.  Skapa en inköpsfaktura för en kvantitet på 2 och ett enhetspris på 12,00.

Skillnaden i enhetspris på 2,00 bokförs till kontot för Prisavvikelse för rörligt genomsnitt när inköpsfakturan bokförs. Anledningen är att två produkter köps in till en kostnad på 20,00. En av produkter såldes för ett enhetspris på 10,00. Inköpsfakturan har bokförts på 12,00 med kvantiteten 2 a-priset. Priset per enhet av produkten kan inte bokföras när 14,00.

## <a name="moving-average-product-and-inventory-adjustment"></a>Produkt med rörligt genomsnitt och lagerjustering
Om du behöver justera en produkts rörliga genomsnittskostnad tillåts lagerjusteringar per dagens datum. Du kan inte bakåtdatera en lagerjustering för att korrigera produktens rörliga genomsnittskostnad. Du kan inte ha det kostnadskalkylerade flödet genom efterföljande transaktioner. I det här exemplet justeras den rörliga genomsnittskostnaden för en produkt.
1.  Välj produkten som du vill justera den rörliga genomsnittskostnaden för.
    | **Note**                                                                                    |
    |---------------------------------------------------------------------------------------------|
    | Den ** omvärdering för rörligt genomsnitt ** sida undersöker lagersaldot för en produkt. |

    Den markerade produkten har en bokförd kvantitet på 1, ett bokfört värde på 12,00, en bokförd enhetskostnad på 12,00 och en enhetskostnad på 12,00.
2.  Uppdatera fältet **Enhetskostnad** till 16,00. Systemet beräknar de kvarvarande fälten.
3.  Justeringen bokförs.

| **Obs! **                                                        |
|-----------------------------------------------------------------|
| Du kan bara justera den rörliga genomsnittskostnad per dagens datum. |

På sidan **Kvittningar för verifikationen** kan du se en justering på 4,00 som bokförs på kontot för rörligt genomsnitt.

## <a name="moving-average-with-production"></a>Rörligt genomsnitt med produktion
Rörligt genomsnitt stöder tillverkade artiklar. Om du tänker använda glidande medelvärde i en produktionsmiljö i **Använd uppskattad självkostnad** skjutreglaget i det ** Produktionskontrollparametrar ** sidan ska vara selcted. Det innebär att självkostnaden som beräknas vid uppskattningen används i stället för den verkliga självkostnaden för strukturlisteberäkning.

## <a name="moving-average-with-a-backdated-transaction"></a>Rörligt genomsnitt med en bakåtdaterad etransaktion
Bakåtdaterade transaktioner tilldelas den aktuella rörliga genomsnittskostnaden och produktens fysiska kvantitet uppdateras, men produktens rörliga genomsnittskostnad påverkas inte. I den här rörliga genomsnittskostnaden bokförs en bakåtdaterad transaktion för en rörlig genomsnittskostnad.
1.  Skapa en justering för lager för produkten med rörlig genomsnittskostnad för en kvantitet på 1 och en kostnad på 20,00.
2.  Lagertransaktionhistoriken för produkten skulle likna följande:
    -   En lagertransaktion på 1, en kostnad på 16,00, bokföringsdatumet 15 januari och transaktionsdatumet 15 januari.
    -   En lagertransaktionsjustering på 1, en kostnad på 20,00, bokföringsdatumet 1 januari och transaktionsdatumet 15 januari.

3.  Bokför justeringen.

På sidan **Lagertransaktioner** kan du se att 4,00 är utgifter, eftersom det aktuella rörliga genomsnitten för produkten är 16,00. Du kan bokföra tidigare, men skillnaden i kostnad är kostnadsfört, så den rörliga genomsnittskostnaden påverkas inte.

## <a name="inventory-value-report"></a>Lagervärderapport
I det här exemplet på rörligt genomsnitt skrivs rapporten om lagervärde ut för att stödja den aktuella rörliga genomsnittsberäkningen för en produkt. Rapporten om lagervärde kan skriva ut transaktionerna i kronologisk ordning, tillsammans med kostnaden för att stödja beräkningen av rörliga genomsnittskostnad för en produkt. Rapporten visar den nya kostnaden för rörligt genomsnitt för produkten. I dialogrutan **Rapporter i lagervärde** kan du med ett datumintervall välja **Transaktionstid** eller **Bokföringsdatum** att sortera rapporten efter. Alternativet **Bokföringsdatum** är hur rapporten skrivs ut traditionellt. Alternativet **Transaktionstid** är det faktiska datum då transaktionen rapporteras och den rörliga genomsnittskostnaden för produkten uppdateras. Du kan skriva ut rapporten om lagervärde genom att använda alternativet **Sortering av transaktionstid** om du vill se kostnadsberäkningen för rörligt genomsnitt över tid. I följande tabell visas de transaktioner för produkten som rapporten skrivs ut för när alternativet **Sortering av transaktionstid** används.

| Transaktionstid | Datum         | transaktionstyp           | Kvantitet | Belopp | Genomsnittlig enhetskostnad |
|------------------|--------------|----------------------------|----------|--------|-------------------|
|                  | 1 oktober    | Ingående saldo          | 0        | 0,00   | 0,00              |
| 8 oktober        | 28 september | Bakåtdaterad inleverans          | 1        | 16,00  | 16,00             |
| 3 oktober        | 3 oktober    | Inköpsinleverans           | 2        | 20,00  | 12,00             |
| 5 oktober        | 5 oktober    | Försäljningsorder                | -1       | -10.00 | 13,00             |
| 7 oktober        | 7 oktober    | Inköpsfaktura           |          | 2,00   | 14,00             |
| 8 oktober        | 8 oktober    | Omvärdering av rörligt genomsnitt |          | 4,00   | 16,00             |
|                  | 31 oktober   | Summa                      | 2        | 32,00  | 16,00             |

 

| **Obs! **                                                                                                                                                                  |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Du kan inte stämma av redovisningen med lager genom att använda alternativet **Sortering av transaktionstid**. Rapporten måste skrivas ut genom att använda alternativet **Bokföringsdatum**. |




