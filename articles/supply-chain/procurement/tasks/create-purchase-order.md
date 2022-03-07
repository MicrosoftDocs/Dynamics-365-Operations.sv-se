---
title: Skapa en inköpsorder
description: Det här avsnittet visar hur du skapar en inköpsorder manuellt.
author: RichardLuan
manager: tfehr
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventDimParmFixed, InventItemIdLookupPurchase, InventProductDimensionLookup, PurchTotals
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2152a2f6677fc0a321f15798c063f01ffd5969d4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5212016"
---
# <a name="create-a-purchase-order"></a>Skapa en inköpsorder

[!include [banner](../../includes/banner.md)]

Det här avsnittet visar hur du skapar en inköpsorder manuellt. Den är vanligare att inköpsorder skapas automatiskt som resultat av huvudplaneringen, en direktleverans och andra processer. Inköpsorder används vanligtvis av inköpsagenter. De exempel som visas här, kan användas i demonstrationsföretaget USMF som använder de värden som föreslås i anteckningarna för olika steg.


## <a name="create-the-purchase-order-header"></a>Skapa inköpsorderrubriken
1. Gå till **Navigeringsfönster > Moduler > Anskaffning och källa > Inköpsorder > Alla inköpsorder**.
2. Välj **Ny**.
3. Välj ett leverantörskonto **US-101**. När du väljer en leverantör kommer detaljer från leverantörsposten som adress, fakturakonto, leveransvillkor och leveranssätt att kopieras som standardvärden till orderrubriken. Du kan ändra dessa värden när som helst.  
4. Expandera den **allmänna** delen.

    - Fältet **Plats** tillsammans med fältet **Lagerställe** anger var de upphandlade varorna eller tjänsterna måste levereras till. Standardleveransadressen är siten. Båda fält kan fylla i med värden som har ställts in för den valda leverantören, eller så kan du ange dem manuellt.  
    - Fältet **Leveransdatum** används för att ange när de upphandlade varorna och tjänsterna måste levereras. Du kan ange ett enskilt leveransdatum för ordern, eller så kan de enskilda orderraderna ges unika leveransdatum. Om leveransdatum som anges här inte uppfylls för specifika produkter eller tjänster eftersom de har längre produktionstider, skapas dessa rader med ett senare leveransdatum för att tillgodose detta.  

5. Expandera avsnittet **Administration**. Fältet **Beställd av** kan användas för att ange vem som tillämpar ordern. Detta kan vara lämpligt att dela med leverantören om den behöver kontakta den personen. Fältet kan tilldelas ett värde automatiskt om det aktuella användarkontot associeras med ett namn på sidan **Användare**.  
6. Välj **OK**. Orderrubriken har nu skapats. När du arbetar med inköpsorderrader, visas bara en sammanfattning av rubrikinformationen. Om du behöver visa resten av informationen, klickar du på **Sidhuvud**.  

## <a name="add-a-purchase-order-line"></a>Lägg till en inköpsorderrad
1. Välj **inköpsorderrad**.
2. Välj **dimensioner** Produkter kan vara i varianter som särskiljs av dimensioner, till exempel färg, storlek eller utförande. Produkter kan också ställas in att använda lagringsdimensioner, till exempel site och lagerställe. Det finns också frivilliga spårningsdimensioner, såsom parti och serienummer. Om du vill förbättra effektiviteten hos orderregistreringen kan du lägga till dimensionsfälten som du använder ofta direkt till orderrutnätet.  
3. Markera kryssrutan **Färg**. Valfritt: Om du väljer fältet **Spara inställningar** kommer de dimensioner som du har valt även att visas på orderradrutnätet nästa gång du öppnar inköpsordersidan.  
4. Välj **OK**.
5. I fältet **Artikelnummer**, välj **T0004**.

    - Orderrader skapas för produkter och tjänster genom att ange ett artikelnummer, eller som utgifter genom att ange en anskaffningkategori. 
    - Kategorifältet **Anskaffning** används för att lägga till rader där upphandlade artiklar kostnadsförs direkt, snarare än att de går till lagret. Det innebär att du om du behöver utgifter för ett inköp kan du göra detta genom att skapa en inköpsorderrad som anger en anskaffningkategori snarare än skapa en rad med ett artikelnummer. Artiklar kan också associeras med en anskaffningkategori, och i så fall, visas anskaffningkategorin som informativ.  

6. Ange eller välj ett värde i fältet **Färg**. Fälten **Plats** och **Lagerställe** fylls normalt i med värden från orderrubriken, men det går att åsidosätta fälten, om vissa rader måste levereras till andra platser.  
7. Ange ett nummer i fältet **Kvantitet**.

    - Välj vilken kvantitet du vill köpa. Fältet **Kvantitet** fylls i automatiskt med den minsta orderkvantitet för produkten om detta har ställts in, eller med värdet på 1.  
    - Fältet **Enhet** anger måttenheten för den beställda kvantiteten. Vanligtvis anges enheten automatiskt från inköpsenheten i produktmalldatan, men du kan ändra detta.  
    - Fältet **Enhetspris** innehåller vanligtvis ett värde i antingen ett inköpsavtal eller ett handelsavtal. Det är möjligt att ändra enhetspriset på enskilda orderrader, till exempel om ett unikt pris förhandlas med leverantören.  
    - Fältet **Rabatt** representerar ett rabattbelopp per enhet. Denna rabatt minskar därmed enhetspriset efter rabatten. Denna rabatt levereras ofta automatiskt från inköpsavtal eller handelsavtal, men den går att åsidosätta på enskilda rader om unika rabatter har förhandlats fram med leverantören.  
    - En rabattprocentsats kan anges som minskar nettobeloppet för raden. Denna rabatt levereras ofta automatiskt från inköpsavtal eller handelsavtal, men den går att åsidosätta på enskilda rader om unika rabattprocentsatser har förhandlats fram med leverantören.  
    - Värdet i fältet **Nettobelopp** beräknas från andra fält på raden inklusive kvantitet, enhetspris, rabatt och rabattprocent. Det är möjligt att ändra Nettobelopp, men sedan kommer fälten **Enhetspris**, **Rabatt** och **Rabattprocent** att vara tomma och när du bokför mot raden kommer det bokförda beloppet att vara proportionell mot nettobeloppet. Vanligtvis används fältet **Nettobelopp** endast för att visa nettobeloppet för raden.  

8. Visa avsnittet **Raddetaljer**.
9. Välj fliken **Leverans**. Ett unikt leveransdatum kan tilldelas varje orderrad. Datumet ärvs från fältet på inköpsorderrubriken, men du kan ändra detta.  

## <a name="review-order-totals"></a>Granska ordersummor
1. Välj **Summor**.

    - Om du inte ser åtgärden **Summor** väljer du fliken **Inköpsorder** i åtgärdsfönstret.  
    - Denna dialogruta visar summan för helhetsordern.  
    - Fältet **Val** låter dig ändra grunden för hur summorna beräknas. Du kanske till exempel kan välja **Produktinleveranskvantitet** för att visa summor som är relaterade till beloppet för produkter, som har inlevererats, eller **Beställd kvantitet** om du vill visa beloppet av produkten, som har beställts.  

2. Välj **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]