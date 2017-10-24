---
title: "Fakturamatchning och koncerninterna inköpsorder"
description: "Den juridiska personen för inköp som ingår i en koncernintern handelstransaktion kan ställas in för att använda fakturamatchning i leverantörsreskontra. I det här fallet måste bokföringskraven för både koncernintern handel och fakturamatchning i leverantörsreskontra uppfyllas innan koncerninterna leverantörsfakturor kan bokföras."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchLineMatchingPolicy
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3101
ms.assetid: 9c7c2e44-45f8-4325-b6de-a09fe790f9cf
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: affdffd5e73958788ed2a5a4959eea71024140ab
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="invoice-matching-and-intercompany-purchase-orders"></a>Fakturamatchning och koncerninterna inköpsorder

[!include[banner](../includes/banner.md)]


Den juridiska personen för inköp som ingår i en koncernintern handelstransaktion kan ställas in för att använda fakturamatchning i leverantörsreskontra. I det här fallet måste bokföringskraven för både koncernintern handel och fakturamatchning i leverantörsreskontra uppfyllas innan koncerninterna leverantörsfakturor kan bokföras.

I exemplen i det här avsnittet används följande inställningar för koncernintern handel:
-   Fabrikam Purchase är den juridiska personen som köper.
-   Fabrikam Sales är det juridiska personen som säljer.
-   Kund 4020 finns i Fabrikam Sales.
-   Leverantör 3024 finns i Fabrikam Purchase.
-   Koncernintern information anges i Fabrikam Purchase för leverantör 3024. Fabrikam Sales anges som kundföretag, och kund 4020 anges som det kundkonto som motsvarar den juridiska personen för Fabrikam Purchase.
-   Koncernintern information anges i Fabrikam Purchase för kund 4020. Fabrikam Purchase anges som leverantörsföretag, och leverantör 3024 anges som det leverantörskonto som motsvarar den juridiska personen för Fabrikam Sales.

I dessa exempel används följande inställningar för fakturamatchning i leverantörsreskontra för Fabrikam Purchase:
-   Alternativet Aktivera fakturamatchningsvalidering är valt på sidan Parametrar för leverantörsreskontra.
-   Fältet Bokför faktura med avvikelser är inställt på Kräv godkännande på sidan Parametrar för leverantörsreskontra.
-   Pristoleransprocentsatsen för den juridiska personen är 2 procent.

## <a name="example-price-matching-and-intercompany-trade"></a> Exempel: Prismatchning och koncernintern handel
Nettobeloppen för den koncerninterna leverantörsfakturan och den koncerninterna kundfakturan måste vara samma. Detta krav åsidosätter eventuella fakturamatchningsgodkännanden och pristoleransprocent. Exempelvis följer du dessa steg.
1.  Skapa försäljningsorder SO888 för kund 4020 i Fabrikam Purchase. Den koncerninterna inköpsordern ICPO222 skapas automatiskt i Fabrikam Purchase för leverantör 3024, och försäljningsorder ICSO888 skapas automatiskt i Fabrikam Sales.
2.  Registrera att artiklar har inlevererats och bokför en följesedel i Fabrikam Sales. Statusvärdet för KIFO888 ändras till Levererat. Statusvärdet för KIIO222 ändras till Inlevererat.
3.  Utför en fakturauppdatering för KIFO888 i Fabrikam Sales. Enhetspriset är 0,45 och 100 artiklar uppdateras.
4.  Skapa en faktura för KIIO222 i Fabrikam Purchase. Du råkade ändra nettopriset från 45,00 till 54,00. En ikon visas som anger att priset överskrider den tillåtna pristoleransen på 2 procent.
5.  På sidan Fakturamatchningsdetaljer väljer du alternativet för att godkänna bokföring med matchningsavvikelser. På sidan Leverantörsfaktura klickar du på OK. Om leverantörsfakturan inte är en koncernintern leverantörsfaktura lyckas bokföringen. Men eftersom du arbetar med en koncernintern leverantörsfaktura misslyckas bokföringen. För koncernintern handel måste fakturasumman för den koncerninterna försäljningsordern vara samma som fakturasumman för motsvarande koncerninterna inköpsorder. För att lösa detta måste du korrigera nettopriset på fakturan genom att ändra tillbaka nettopriset till standardbeloppet 45,00.

## <a name="example-quantity-matching-with-intercompany-trade"></a> Exempel: Kvantitetsmatchning med koncernintern handel
Kvantiteten på den koncerninterna inköpsordern och den koncerninterna försäljningsordern måste vara samma. Detta krav åsidosätter eventuella godkännanden av fakturamatchning. I detta exempel används följande ytterligare inställningar för koncernintern handel:
-   I Fabrikam Purchase har åtgärdspolicyn för inköpsorder för leverantör 3024 ställts in att automatiskt bokföra både den ursprungliga kundfakturan och den koncerninterna leverantörsfakturan.

I det här exemplet används följande ytterligare inställningar för fakturamatchning i leverantörsreskontra för Fabrikam Purchase:
-   På sidan Artikelmodellgrupper för modellgruppen som används av artikel B-R14 är alternativet Inleveransbehov valt.
-   Lagerbehållningen för artikel B-R14 är 0 (noll).

Exempelvis följer du dessa steg.
1.  Skapa försäljningsorder FO999 för kund 4020 i Fabrikam Purchase. Ordern innehåller en radartikel: 100 batterier (artikel B-R14) till enhetspriset 1,00 per styck. Den koncerninterna inköpsordern KIIO333 skapas automatiskt för leverantör 3024 i Fabrikam Purchase och försäljningsorder KIFO999 skapas automatiskt i Fabrikam Sales.
2.  Utför en fakturauppdatering för KIFO999 i Fabrikam Sales. Bokföringen misslyckad eftersom artikeln inte finns i lager och ännu inte har inlevererats. Därför kan den ekonomiska informationen inte uppdateras.
3.  Registrera att artiklar har inlevererats och bokför en följesedel för KIFO999 i Fabrikam Sales. En produktinleverans för KIIO333 bokförs automatiskt i Fabrikam Purchase. Den mottagna kvantiteten för artikel B-R14 ändras till 100 i Fabrikam Purchase.
4.  Utför en fakturauppdatering för KIFO999 i Fabrikam Sales. Bokföringen lyckas i båda juridiska personer. Den inköpta kvantiteten för artikel B-R14 ändras till 100 i Fabrikam Purchase. 






