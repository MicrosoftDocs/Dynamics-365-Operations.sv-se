---
title: "Lägg till en rekommendationskontroll på transaktionssidan på en kassaenhet"
description: "Det här avsnittet beskriver hur du lägger till en rekommendationskontroll på transaktionsskärmen på en kassaenhet med hjälp av layoutdesignern för skärm i Microsoft Dynamics 365 for Retail."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 47ad5dc8fd698f6f543c6a48e2c7eb01d4e148e6
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a>Lägg till en rekommendationskontroll på transaktionssidan på en kassaenhet

[!include[banner](includes/banner.md)]


Det här avsnittet beskriver hur du lägger till en rekommendationskontroll på transaktionsskärmen på en kassaenhet med hjälp av layoutdesignern för skärm i Microsoft Dynamics 365 for Retail.

Du kan visa produktrekommendationer på din kassaenhet när du använder Microsoft Dynamics 365 for Retail. *Rekommendationer* är artiklar som dina kunder kan vara intresserade av baserat på sina tidigare inköp, artiklar i sina önskelistor samt artiklar som andra kunder köpt online och i fysiska butiker. Om du vill visa produktrekommendationer måste du lägga till en kontroll på transaktionsskärmen med skärmlayoutdesignern.

## <a name="open-layout-designer"></a>Öppna layoutdesignern
1.  Navigera till **Butik** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassa** &gt; **Skärmlayout**.
2.  Med snabbfiltret kan du snabbt hitta den skärm som du vill lägga till kontrollen i. Filtrera till exempel fältet **ID för skärmlayout** med hjälp av värdet "F2CP16:9M".
3.  Hitta och markera önskad post i listan. Markera exempelvis "Namn: F2CP16:9M Skärmlayout-ID: F2CP16:9M".
4.  Klicka på **Layoutdesigner**.
5.  Följ instruktionerna för att starta layoutdesignern. När du uppmanas ange dina autentiseringsuppgifter, ange då samma autentiseringsuppgifter som användes när layoutdesignern startades från sidan **Skärmlayouter**.
6.  När du loggar in visas en sida som liknar den nedanstående. Layouten är olika beroende på de anpassningar som gjorts för din butik.

[![skärmlayout-bild-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png) Välj ett visningsalternativ
-----------------------

Det finns två konfigurationsalternativ tillgängliga. Välj det alternativ som passar bäst för din butik, och följ sedan resten av anvisningarna för att avsluta kontrollinställningarna. De två alternativen är:
-   Rekommendationer visas alltid.
-   Fliken **Rekommendationer** visas i rutnätet till höger på skärmen.

#### <a name="to-make-recommendations-always-visible"></a>För att alltid visa rekommendationer

1.  Minska höjden på detaljområdet för transaktionsrader så att denna är samma höjd som hos kundpanelen till vänster.[](./media/pic-2.png)[![skärmlayout-bild-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)
2.  Från menyn till vänster, dra och släpp rekommendationskontrollen mellan detaljområdet för transaktionsrad och knappsatsen längst ned i mitten längst på transaktionsskärmen. Ändra storlek på kontrollen så att den passar in i utrymmet.[](./media/pic-3.png)[![bildlayout-bild-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)
3.  Klick på **X** för att spara och stänga layoutdesignern.
4.  I Dynamics 365 for Retail, navigera till **Butik** &gt; **Butiks-IT** &gt; **Fördelningsscheman**.
5.  I listan väljer du **1090 Registers**.
6.  Klicka på **Kör nu**.

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>För att lägga till en rekommendationsflik i knappsatsen till höger på skärmen

1.  Högerklicka i det tomma utrymmet under den sista fliken på knappsatsen till höger på sidan.
2.  Klicka på **Anpassa**.[![bild-5](./media/pic-5.png)](./media/pic-5.png)
3.  Klicka på **Ny flik**.
4.  Hitta den nya fliken som du just skapade. Du kan behöva rulla nedåt.
5.  I listrutan **Innehåll** väljer du **Rekommenderade produkter**. [![bild-6](./media/pic-6.png)](./media/pic-6.png)
6.  I fältet **Etikett** anger du ett namn för rekommendationsfliken. Skriv till exempel ”Rekommenderade produkter”.
7.  I fältet **Bild** väljer du den bild du vill visa i fliken.
8.  Klicka på **OK**. Den nya fliken visas i knappsatsen.
9.  Klick på **X** för att spara och stänga layoutdesignern.
10. I Dynamics 365 for Retail, navigera till **Butik** &gt; **Butiks-IT** &gt; **Fördelningsscheman**.
11. I listan väljer du **1090 Registers**.
12. Klicka på **Kör nu**.


<a name="see-also"></a>Se även
--------

[Översikt över anpassade produktrekommendationer](personalized-product-recommendations.md)




