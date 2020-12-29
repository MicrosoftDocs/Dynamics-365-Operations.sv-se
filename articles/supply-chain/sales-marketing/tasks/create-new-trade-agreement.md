---
title: Skapa ett nytt handelsavtal
description: I den här proceduren visas hur du skapar ett handelsavtal där du registrerar ett nytt produktförsäljningspris som du har avtalat med en viss kund.
author: omulvad
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TradeNonStockedConversion, TradeNonStockedConversionChangeWizard, TradeNonStockedConversionCheckWorksheet, TradeNonStockedConversionWizard, TradeNonStockedRegister
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 43426e77c30e46f4dd1cc117c38cf6ba5437655b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437473"
---
# <a name="create-a-new-trade-agreement"></a>Skapa ett nytt handelsavtal

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du skapar ett handelsavtal där du registrerar ett nytt produktförsäljningspris som du har avtalat med en viss kund. Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Om du använder dina egna data måste du se till att det finns ett namn på handelsavtalsjournalen där standardrelationen har angetts till "Pris (försäljning)" innan du startar den här guiden.


## <a name="create-and-post-a-new-trade-agreement-journal"></a>Skapa och bokför en ny handelsavtalsjournal.
1. Gå till **Navigeringsrutan > Moduler > Försäljning och marknadsföring > Priser och rabatter > Handelsavtalsjournaler**.
2. Klicka på **Ny**.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Namn**.
4. Hitta och markera önskad post i listan.
5. Klicka på **Rader** i **åtgärdsfönstret**.
6. I fältet **Kontokod**, välj Tabell.
    
    I det här exemplet uppdaterar du priset för en viss kund, vilket innebär att du måste välja Tabell. Om du har uppdaterat produktens listpris, du vill markera alla, så att det nya priset är giltigt för alla kunder. Om du differentiera priser mellan olika kundsegment, då skulle du välja grupp. Du måste ha ställt in Kundprisgrupper för att välja Grupp.  

7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Kontomarkering**.
8. Hitta och markera önskad post i listan.
9. Fältet **Artikelkod**, väljTabell.
    
    När du registrerar ett handelsavtal av typen "Pris (försäljning), måste du först markera "Tabell" i fältet **artikelkod**. Detta beror på att ett pris är ett absolut värde och kan inte vara samma för alla produkter eller en grupp av produkter.
    
10. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelrelation**.
11. I listan väljer du vilken produkt som du vill inkludera i avtalet. Gör en notering för vilken produkt du har valt.  
12. I fältet **Från**, ange en minsta kvantitet.
    - Om kunden har en minsta kvantitet innan de kan kvalificera sig för det nya priset, alltså du nöd till preciserar kvantiteten här.  
    - Ange ett värde i fältet **Till** för att ange den maximala kvantitet som avtalet är priset inte vara giltig. Om du erbjuder priser och rabatter baserade på flera kvantitetssteg, ange sedan varje kvantitet fäste som ett par minimala och maximala kvantiteten i **från** och **till** respektive fält.
13. I **Belopp i valutafältet**, ange ett pris.
14. Under avsnittet **Detaljer**, i fältet **Fråndatum**, anger du ett datum från vilket detta avtal skall vara giltigt.
15. Klicka på **Spara**.
16. Klicka på **Validera.**
17. Klickar på **Validera markerade rader**.
18. Klicka på **OK**.
19. Klicka på **Bokför**.
20. Klicka på **OK**.

## <a name="view-trade-agreements-for-a-product"></a>Visa handelsavtal för en produkt.
1. Gå till **Navigeringsfönster > Moduler > Produktinformationshantering > Produkter > Frisläppta produkter**.
2. Hitta och markera den produkt vars pris du precis har uppdaterat.
3. Klicka på **Sälj** i **åtgärdsfönstret**.
4. Klicka på **Visa handelsavtal**.
    
    Granska informationen i prishandelsavtalet som du precis har skapat.    

5. Stäng sidan.

## <a name="additional-resources"></a>Ytterligare resurser
### <a name="community-blogs"></a>Bloggar
- [Försäljningspriser i Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)
