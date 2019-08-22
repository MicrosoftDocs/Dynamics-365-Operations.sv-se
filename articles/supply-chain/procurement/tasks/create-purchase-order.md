---
title: Skapa en inköpsorder
description: Den här proceduren visar hur du skapar en inköpsorder manuellt.
author: FrankDahl
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventDimParmFixed, InventItemIdLookupPurchase, InventProductDimensionLookup, PurchTotals
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3ad846ba14b05f8e7d34aff2e3a256cc9b3b56c1
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838128"
---
# <a name="create-a-purchase-order"></a>Skapa en inköpsorder

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar hur du skapar en inköpsorder manuellt. Den är vanligare att inköpsorder skapas automatiskt som resultat av huvudplaneringen, en direktleverans och andra processer. Inköpsorder används vanligtvis av inköpsagenter. De exempel som visas här, kan användas i demonstrationsföretaget USMF som använder de värden som föreslås i anteckningarna för olika steg.


## <a name="create-the-purchase-order-header"></a>Skapa inköpsorderrubriken
1. Gå till Anskaffning och källa > Inköpsorder > Alla inköpsorder.
2. Klicka på Ny.
3. Välj ett leverantörskonto US-101.
    * När du väljer en leverantör kommer detaljer från leverantörsposten som adress, fakturakonto, leveransvillkor och leveranssätt att kopieras som standardvärden till orderrubriken. Du kan ändra dessa värden när som helst.  
4. Expandera avsnittet Allmänt.
    * Fältet Site tillsammans med fältet Lagerställe anger var de upphandlade varorna eller tjänsterna måste levereras till. Standardleveransadressen är siten. Båda fält kan fylla i med värden som har ställts in för den valda leverantören, eller så kan du ange dem manuellt.  
    * Fältet Leveransdatum används för att ange när de upphandlade varorna och tjänsterna måste levereras. Du kan ange ett enskilt leveransdatum för ordern, eller så kan de enskilda orderraderna ges unika leveransdatum. Om leveransdatum som anges här inte uppfylls för specifika produkter eller tjänster eftersom de har längre produktionstider, skapas dessa rader med ett senare leveransdatum för att tillgodose detta.  
5. Dölj avsnittet Allmänt.
6. Visa avsnittet Administration.
    * Fältet Beställd av kan användas för att ange vem som tillämpar ordern. Detta kan vara lämpligt att dela med leverantören om den behöver kontakta den personen. Fältet kan tilldelas ett värde automatiskt om det aktuella användarkontot associeras med ett namn på sidan Användare.  
7. Dölj avsnittet Administration.
8. Klicka på OK.
    * Orderrubriken har nu skapats. När du arbetar med inköpsorderrader, visas bara en sammanfattning av rubrikinformationen. Om du behöver visa resten av informationen, klickar du på Rubrik.  

## <a name="add-a-purchase-order-line"></a>Lägg till en inköpsorderrad
1. Klicka på Inköpsorderrad.
2. Klicka på Dimensioner.
    * Produkter kan vara i varianter som särskiljs av dimensioner, till exempel färg, storlek eller utförande. Produkter kan också ställas in att använda lagringsdimensioner, till exempel site och lagerställe. Det finns också frivilliga spårningsdimensioner, såsom parti och serienummer. Om du vill förbättra effektiviteten hos orderregistreringen kan du lägga till dimensionsfälten som du använder ofta direkt till orderrutnätet.  
3. Markera kryssrutan Färg.
    * Valfritt: Om du väljer fältet Spara inställningar kommer de dimensioner som du har valt även att visas på orderradrutnätet nästa gång du öppnar inköpsordersidan.  
4. Klicka på OK.
5. Välj T0004 i fältet Artikelnummer.
    * Orderrader skapas för produkter och tjänster genom att ange ett artikelnummer, eller som utgifter genom att ange en anskaffningkategori.  
    * Fältet Anskaffningkategori används för att lägga till rader där upphandlade artiklar är utgifter direkt, snarare än att det går till lagret. Det innebär att du om du behöver utgifter för ett inköp kan du göra detta genom att skapa en inköpsorderrad som anger en anskaffningkategori snarare än skapa en rad med ett artikelnummer. Artiklar kan också associeras med en anskaffningkategori, och i så fall, visas anskaffningkategorin som informativ.  
6. Ange eller välj ett värde i fältet Färg.
    * Fälten Site och Lagerställe fylls normalt i med värden från orderrubriken, men det går att åsidosätta fält, om alla rader måste levereras till andra platser.  
7. Ange ett tal i fältet Kvantitet.
    * Välj vilken kvantitet du vill köpa. Fältet Kvantitet fylls i automatiskt med den minsta orderkvantitet för produkten om detta har ställts in, eller med värdet på 1.  
    * Fältet Måttenhet anger måttenheten för den beställda kvantiteten. Vanligtvis anges enheten automatiskt från inköpsenheten i produktmalldatan, men du kan ändra detta.  
    * Fältet Enhetspris innehåller vanligtvis ett värde i antingen ett inköpsavtal eller ett handelsavtal. Det är möjligt att ändra enhetspriset på enskilda orderrader, till exempel om ett unikt pris förhandlas med leverantören.  
    * Rabattfältet representerar ett rabattbelopp per enhet. Denna rabatt minskar därmed enhetspriset efter rabatten. Denna rabatt levereras ofta automatiskt från inköpsavtal eller handelsavtal, men den går att åsidosätta på enskilda rader om unika rabatter har förhandlats fram med leverantören.  
    * En rabattprocentsats kan anges som minskar nettobeloppet för raden. Denna rabatt levereras ofta automatiskt från inköpsavtal eller handelsavtal, men den går att åsidosätta på enskilda rader om unika rabattprocentsatser har förhandlats fram med leverantören.  
    * Värdet i fältet Nettobelopp beräknas från andra fält på raden inklusive kvantitet, enhetspris, rabatt och rabattprocent. Det är möjligt att ändra Nettobelopp, men sedan kommer fälten Enhetspris, Rabatt och Rabattprocent att vara tomma och när du bokför mot raden kommer det bokförda beloppet att vara proportionell mot nettobeloppet. Vanligtvis används fältet Nettobeloppet endast för att visa nettobeloppet för raden.  
8. Expandera avsnittet Radinformation.
9. Klicka på fliken Leverans.
    * Ett unikt leveransdatum kan tilldelas varje orderrad. Datumet ärvs från fältet på inköpsorderrubriken, men du kan ändra detta.  
10. Komprimera avsnittet Raddetalj.

## <a name="review-order-totals"></a>Granska ordersummor
1. Klicka på Summor.
    * Om du inte ser Totala åtgärder, klicka på fliken Inköpsorder på åtgärdsfältet.  
    * Denna dialogruta visar summan för helhetsordern.  
    * Fältet Val låter dig ändra grunden för hur summorna beräknas. Du kanske till exempel kan välja Produktinleveranskvantitet att visa summor som är relaterade till beloppet för produkter, som har inlevererats, eller beställd kvantitet om du vill visa beloppet av produkten, som har beställts.  
2. Klicka på OK.

