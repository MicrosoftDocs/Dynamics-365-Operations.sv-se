---
title: Skapa en upprepad inköpsorder
description: I denna artikel visas hur du skapar en upprepad inköpsorder (IO) genom att kopiera rader från ett tidigare inköpsorderdokument till en ny IO eller till en befintlig IO.
author: GalynaFedorova
ms.date: 09/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, PurchCopying
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 335461d60fa0bc92e9711806c6e42643a3f75d02
ms.sourcegitcommit: 073604c07116e0a87f78ab2c76cb89ae83ebba3c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9608122"
---
# <a name="create-a-repeat-purchase-order"></a>Skapa en upprepad inköpsorder

[!include [banner](../../includes/banner.md)]

I denna artikel visas hur du skapar en upprepad inköpsorder (IO) genom att kopiera rader från ett tidigare inköpsorderdokument till en ny IO eller till en befintlig IO. Det finns två sätt att skapa upprepade order. Du kan använda tillgängliga åtgärder på dokumentnivån från åtgärdsfönstret, eller använda raddetaljåtgärderna. Dokumentnivååtgärderna är avsedda för att skapa en ny inköpsorder genom att lägga till rader och rubrikinformation från en annan order, medan raddetaljåtgärden är avsedd för att lägga till rader i en befintlig order. De exempel som visas i den här handboken kan användas i demoföretaget USMF. Denna uppgift utförs vanligtvis av en inköpsagent.

## <a name="create-a-new-repeat-purchase-order"></a>Skapa en upprepad inköpsreturorder.

1. I navigeringsfönstret går du till **Moduler \> Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**. Först ska försöka med alternativet att kopiera information till en ny order.  
1. Välj **Ny**.
1. I fältet **Leverantörskonto** ange `US-101`.
1. Välj **OK**.
1. I åtgärdsfönstret, öppna fliken **Inköpsorder** innan du i gruppen **Kopiera** väljer **Från alla**. Dialogrutan **Kopiera från andra dokument** öppnas. Härifrån kan du kopiera från befintliga order till din order. Det finns olika alternativ för hur raderna kopieras och olika slags dokument som du kan kopiera från. Vi kommer att titta på alternativen för hur rader kopieras först.
1. Visa snabbfliken **Parametrar**.

    - Fältet **Kvantitetsfaktor** är användbart om du behöver använda en kvantitet som skiljer sig från den som finns på ordern som du kopierar från. Om du till exempel vill beställa två gånger kvantiteten som är på raderna som du kopierar från, ska du skriva "2" i det här fältet. Sedan kommer systemet att lägga till rader där den ursprungliga kvantiteten har dubblerats.  
    - Fältet **Byt förtecken** ändrar också den beställda kvantiteten genom att ändra förtecknet för kvantiteten för orderrader som har lagts till. Detta kan vara användbart om du behöver återföra en transaktion genom att skapa orderrader som upphäver transaktionen. Det här alternativet väljs automatiskt när sidan öppnas från åtgärden **Skapa kreditfaktura**.  
    - Alternativet **Kopiera avgifter** låter dig kopiera avgifter på den nya ordern från det dokument som du kopierar orderraderna från.  
    - Alternativet **Omräkna priser** använder de aktuella priserna och rabatterna snarare än att kopiera dessa från dokument som du kopierar annan information från.  
    - Alternativet **Kopiera exakt** kopierar värdena i flera fält i orderns rubrik och rader. Om det här alternativet inte har markerats kommer förvalda värden att användas för många av fälten som relaterar till leverantören och produkterna, precis som när du skapar en ny order manuellt. Om du till exempel anger **Kopiera exakt** som *Ja* och kopierar en order som åsidosätter leverantörens förvalda fakturakonto, kommer samma fakturakonto att kopieras till din nya order. Om du anger **Kopiera exakt** som *Nej* kommer förvalt fakturakonto för leverantören att istället användas på din nya order. Värden för följande fält kopieras när **Kopiera exakt** är inställt på *Ja*:
        - Språk
        - Betalningsvillkor
        - Betalningsmetod
        - Betalningsspecifikation
        - Nummerseriegrupp
        - Kassarabatt
        - Rabattprocent
        - Valuta
        - Leveransvillkor
        - Leveranssätt
        - Dimension
        - Momsgrupp
        - Åsidosätt moms
        - Moms ingår i priserna
        - Transport
        - Lastningsplats
        - Statistikprocedur
        - Mall-ID
        - Leveransnamn
        - Postadress
        - Referens
        - ID för referenstabell
    - Alternativet **Radera inköpsrader** tar bort alla inköpsorderrader som redan finns på inköpsordern som du kopierar till, innan du tillämpar nya raderna. Använd det här alternativet försiktigt eftersom det tar bort alla befintliga rader utan ytterligare varning.  
    - Om du använder alternativet **Kopiera orderrubrik**, behöver du inte manuellt skapa huvudinformationen på den nya ordern. Detta alternativ leder till att förvalda värden används för de fält som är kopplade till leverantören. Om dokumentet som du kopierar från har icke-standardvärden som du vill kopiera, använder du alternativet **Kopiera exakt**.
    - Det finns olika dokumentkällor som du kan kopiera från och var och en har ett separat avsnitt på den här sidan. Till exempel låter avsnittet **Inköpsorder** dig att kopiera från befintliga inköpsorder.  

1. Markera de rader som du vill kopiera till Urklipp i avsnittet **Inköpsorder**. Det går att välja ytterligare inköpsorderrader från andra inköpsorder och även att kopiera dem till din order. Det går också att lägga till rader från andra typer av inköpsdokument. De nästa få steg granskar de olika alternativen.  
1. Expandera avsnittet **Bekräftelse**. Här kan du välja inköpsorderbekräftelser som du vill kopiera från. Inköpsorderbekräftelserna identifieras av associerat inköpsjournal-ID eller inköpsorder-ID.  
1. Expandera avsnittet **Produktinleveranser**. Här kan du välja produktinleveransjournaler som du vill kopiera från. Produktinleveransjournalerna identifieras av produktinleveransverifikationen eller inköpsorder-ID.
1. Expandera avsnittet **Fakturor**. Här kan du välja leverantörsfakturor att kopiera från. Fakturorna identifieras av fakturaverifikationen eller inköpsorder-ID.
1. Expandera avsnittet **Valda rader eller rubriker som ska kopieras**. Den här vyn visar en sammanfattning av alla dokument och rader somhar valt för att kopieras till din order.
1. Välj **OK**. De rader som du valde har kopierats till din nya inköpsorder.

## <a name="copy-lines-to-an-existing-purchase-order"></a>Kopiera rader till en befintlig inköpsorder  

Istället för att kopiera en hel order är det mer vanligt att kopiera en ny inköpsorder och komplett information om inköpsorderhuvudet och sedan kopiera enskilda rader från befintliga order.  

1. Välj raden **Inköpsorder**.
1. Välj **Från alla**. Sidan som öppnas är identisk med det som visades tidigare, men olika alternativ markeras när den öppnas från orderradvyn. Vi tar en titt på parametrarna.
1. Expandera avsnittet **Parametrar**.

    - Alternativet **Radera inköpsrader** är inte markerat. Det innebär att du kan kopiera nya rader i din order utan att ta bort befintliga rader.
    - Alternativet **Kopiera orderrubrik** markeras inte heller eftersom vi bara lägger till ytterligare rader till ordern.
    - I det här exemplet kopierar vi rader från en befintlig inköpsorder.

1. Välj raden för den önskade inköpsordern. Observera att även den enskilda orderraden som finns på denna inköpsorder markeras.  
1. Välj **OK**. Den ytterligare orderraden har lagts till din inköpsorder.  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]