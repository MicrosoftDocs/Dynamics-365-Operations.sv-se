---
title: Lägg till en rekommendationskontroll på transaktionsskärmen på kassaenheter
description: Det här avsnittet beskriver hur du lägger till en rekommendationskontroll på transaktionsskärmen på en kassaenhet med hjälp av layoutdesignern för skärm i Microsoft Dynamics 365 for Retail.
author: bebeale
manager: AnnBe
ms.date: 10/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d646c8ba559ba3e8d2175911e76c57d25eff02ca
ms.sourcegitcommit: 5b53bdafa5cb9a1279576bfece0452a50383b122
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2019
ms.locfileid: "2278139"
---
# <a name="add-a-recommendations-control-to-the-transaction-screen-on-pos-devices"></a>Lägg till en rekommendationskontroll på transaktionsskärmen på kassaenheter

[!include [banner](includes/banner.md)]


Det här avsnittet beskriver hur du lägger till en rekommendationskontroll på transaktionsskärmen på en kassaenhet med hjälp av layoutdesignern för skärm i Microsoft Dynamics 365 Retail. Mer information om produktrekommendationer finns i [produktrekommendationerna i kassadokumentationen.](product.md)


Du kan visa produktrekommendationer på din kassaenhet när du använder Microsoft Dynamics 365 Retail. Om du vill visa produktrekommendationer måste du lägga till en kontroll på transaktionsskärmen med skärmlayoutdesignern. 

## <a name="open-layout-designer"></a>Öppna layoutdesignern

1. Navigera till **Butik** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassa** &gt; **Skärmlayout**.
2. Med snabbfiltret kan du snabbt hitta den skärm som du vill lägga till kontrollen i. Filtrera till exempel fältet **ID för skärmlayout** med hjälp av värdet **F2CP16:9M**.
3. Hitta och markera önskad post i listan. Markera exempelvis **Namn: F2CP16:9M Skärmlayout-ID: F2CP16:9M**.
4. Klicka på **Layoutdesigner**.
5. Följ instruktionerna för att starta layoutdesignern. När du uppmanas ange dina autentiseringsuppgifter, ange då samma autentiseringsuppgifter som användes när layoutdesignern startades från sidan **Skärmlayouter**.
6. När du loggar in visas en sida som liknar den nedanstående. Layouten är olika beroende på de anpassningar som gjorts för din butik.


    [![Layoutdesigner](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)

## <a name="choose-a-display-option"></a>Välj ett visningsalternativ

Det finns två konfigurationsalternativ tillgängliga. Välj det alternativ som passar bäst för din butik, och följ sedan resten av anvisningarna för att avsluta kontrollinställningarna. De två alternativen är:

- Rekommendationer visas alltid.
- Fliken **Rekommendationer** visas i rutnätet till höger på skärmen.

### <a name="make-recommendations-always-visible"></a>Gör så att rekommendationer alltid visas


1. Minska höjden på detaljområdet för transaktionsrader så att denna är samma höjd som hos kundpanelen till vänster.


    [![Höjden på detaljområdet för transaktionsrader har reducerats](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)

2. Från menyn till vänster, dra och släpp rekommendationskontrollen mellan detaljområdet för transaktionsrad och knappsatsen längst ned i mitten längst på transaktionsskärmen. Ändra storlek på kontrollen så att den passar in i utrymmet.

    [![Rekommendationskontroll som läggs till i layouten](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)


3. Klick på **X** för att spara och stänga layoutdesignern.
4. I Dynamics 365 for Retail, gå till **Butik** &gt; **Butik-IT** &gt; **Distributionsschema**.
5. I listan väljer du **1090 Registers**.
6. Klicka på **Kör nu**.


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Lägg till en rekommendationsflik i knappsatsen till höger på skärmen

1. Högerklicka i det tomma utrymmet under den sista fliken på knappsatsen till höger på sidan.

2. Klicka på **anpassa**.

    [![Anpassning - dialogrutan flikkontroll](./media/pic-5.png)](./media/pic-5.png)

3. Klicka på **Ny flik**.
4. Hitta den nya fliken som du just skapade. Du kan behöva rulla nedåt.
5. I listrutan **Innehåll** väljer du **Rekommenderade produkter**.

    [![Välja rekommenderade produkter i fältet Innehåll](./media/pic-6.png)](./media/pic-6.png)

6. I fältet **Etikett** anger du ett namn för rekommendationsfliken. Skriv till exempel ”Rekommenderade produkter”.
7. I fältet **Bild** väljer du den bild du vill visa i fliken.
8. Klicka på **OK**. Den nya fliken visas i knappsatsen.
9. Klick på **X** för att spara och stänga layoutdesignern.
10. I Dynamics 365 for Retail, gå till **Butik** &gt; **Butik-IT** &gt; **Distributionsschema**.
11. I listan väljer du **1090 Registers**.
12. Klicka på **Kör nu**.

## <a name="additional-resources"></a>Ytterligare resurser

[produktrekommendationer i kassa](product.md)

[översikt över produktrekommendationer](../commerce/product-recommendations.md)
