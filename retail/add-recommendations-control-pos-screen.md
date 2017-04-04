---
title: "Lägga till en kontroll med rekommendationer på sidan transaktionen på en POS-enhet"
description: "Det här avsnittet beskrivs hur du lägger till en kontroll med rekommendationer skärmen på en försäljning (PO) enheten med Layoutdesigner för skärm i Microsoft Dynamics 365 för transaktionen."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 2377b1639a3c95fe6bba4754c4069cc12043e3d3
ms.lasthandoff: 03/31/2017


---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a>Lägga till en kontroll med rekommendationer på sidan transaktionen på en POS-enhet

Det här avsnittet beskrivs hur du lägger till en kontroll med rekommendationer skärmen på en försäljning (PO) enheten med Layoutdesigner för skärm i Microsoft Dynamics 365 för transaktionen.

Du kan visa produktrekommendationer på POS enheten när du använder Microsoft Dynamics 365 för operationer. *Rekommendationer för* som kunderna kan vara intresserade av baserat på deras tidigare inköp och objekt i sina önskelista artiklar som andra kunder köpt online och bankkontor och andra objekt. Om du vill visa produktrekommendationer måste du lägga till en kontroll på transaktionen skärmen med Layoutdesigner för skärm.

## <a name="open-layout-designer"></a>Öppna Layoutdesignern för formulär
1.  Gå till **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**POS**&gt;**skärm layouter**.
2.  Med filtret snabbt hitta skärmen som du vill lägga till kontrollen. Till exempel filtrera efter den **skärm layout-ID** med hjälp av värdet 'F2CP16:9M'.
3.  Hitta och markera önskad post i listan. Markera exempelvis "namn: F2CP16:9M skärmlayout-ID: F2CP16:9M'.
4.  Klicka på **Layoutdesigner för**.
5.  Följ instruktionerna för att starta Layoutdesignern för formulär. Autentiseringsuppgifter Skriv samma autentiseringsuppgifter som användes när layoutdesignern startades från **skärm layouter** sida.
6.  När du loggar in visas en sida som liknar den nedan. Layouten är olika beroende på anpassningar som har gjorts för din butik.

[![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) väljer du ett visningsalternativ
-----------------------

Det finns två alternativ för konfigurationer. Välj det alternativ som passar bäst för din butik och följ resten av anvisningarna tills kontrollen. Det finns två alternativ:
-   Rekommendationer visas alltid.
-   A **rekommendationer** flik i rutnätet till höger på skärmen.

#### <a name="to-make-recommendations-always-visible"></a>Att utfärda rekommendationer alltid ska visas

1.  Minska höjden på detaljområdet transaktionen rader så att den är samma höjd som kunden panelen till vänster. [](./media/pic-2.png)[![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)
2.  Dra och släpp rekommendationer kontrollen mellan detaljområdet transaktionen rad och knappsatsen i mitten längst ned skärmbilden transaktionen på menyn till vänster. Ändra storlek på kontrollen så att den passar på det resterande utrymmet. [](./media/pic-3.png)[![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)
3.  Klicka på den **X** att spara och stänga Layoutdesignern för formulär.
4.  I Dynamics 365 för operationer, gå till **butik och handel**&gt;**Retail IT**&gt;**fördelning scheman**.
5.  I listan väljer du **1090 registrerar**.
6.  Klicka på **kör nu**.

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Lägga till en flik rekommendationer till knappsatsen på höger sida av skärmen

1.  Högerklicka i det tomma utrymmet nedanför sista på knappsats finns till höger på sidan.
2.  Klicka på **anpassa**. [![pic-5](./media/pic-5.png)](./media/pic-5.png)
3.  Klicka på **ny flik**.
4.  Hitta den nya fliken som du just skapade. Du kan behöva rulla nedåt.
5.  I den **innehåll** listrutan, väljer **produkter bör**. [![PIC-6](./media/pic-6.png)](./media/pic-6.png)
6.  I den **etiketten** skriver du ett namn för fliken rekommendationer. Skriv till exempel "Rekommenderas produkter".
7.  I den **bild**, markera bilden ska visas på fliken.
8.  Click **OK**. Den nya fliken visas i knappsatsen.
9.  Klicka på den **X** att spara och stänga Layoutdesignern för formulär.
10. I Dynamics 365 för operationer, gå till **butik och handel**&gt;**Retail IT**&gt;**fördelning scheman**.
11. I listan väljer du **1090 registrerar**.
12. Klicka på **kör nu**.


<a name="see-also"></a>Se även
--------

[Personliga rekommendationer Produktöversikt](personalized-product-recommendations.md)


