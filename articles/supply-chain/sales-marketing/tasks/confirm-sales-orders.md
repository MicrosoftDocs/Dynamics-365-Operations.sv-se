---
title: Bekräfta försäljningsorder
description: I den här proceduren visas hur du bekräftar försäljningsorder.
author: omulvad
manager: AnnBe
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, CustConfirmJournal, SysQueryForm, SysQueryFieldLookUp, SysLookup, SalesParmIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6383576302789d268d64edcbbe05305b03e956d0
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148724"
---
# <a name="confirm-sales-orders"></a>Bekräfta försäljningsorder

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du bekräftar försäljningsorder. Du får reda på hur du bekräftar en enstaka order och hur du bekräftar flera order på en gång. Dessa uppgifter utförs vanligtvis via en försäljningsorderbehandlare. Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Kontrollera att det finns flera öppna försäljningsorder för samma kund innan du börjar. Om du använder USMF kan du använda kunden US-027.


## <a name="confirm-a-single-sales-order"></a>Bekräfta en enskild försäljningsorder
1. Gå till **Navigeringsfönster > Moduler > Försäljning och marknadsföring > Försäljningsorder > Alla försäljningsorder**.
2. Hitta och markera den order du vill bekräfta i listan.
3. Klicka på länken för försäljningsordernumret för att öppna den valda ordern.
4. Klicka på **Sälj** i **åtgärdsfönstret**.
5. Klicka på **Bekräfta försäljningsorder**.
6. Expandera avsnittet **Parametrar**. Kontrollera att alternativet **Bokför** har värdet Ja.  
7. Ställ in alternativet **Skriv ut bekräftelse** på Ja. Fältet **Checkkreditgräns** anger vilken metod som ska användas för att beräkna en kunds återstående kredit. Som standard kopieras den från sidan Parametrar för kundreskontra. Om du vill hoppa över kreditgränskontrollen när du bekräftar en specifik försäljningsorder anger du **checkkreditgränsen** till Ingen. Du bör dock vara medveten om att även om det här fältet är inställt på Ingen, så kommer kreditgränskontrollen fortfarande att utföras om alternativet **Obligatorisk kreditgräns** har valts i kundhuvuddata. 
8. Klicka på **OK**.
9. Klicka på **Ja**.
10. Stäng sidan.
11. I **åtgärdsrutan** klickar du på **Alternativ**.
12. Klicka på **ändra uppfattning**.
13. Klicka på **Huvudvy**. När en order har bekräftats anges **dokumentstatusen** till Bekräftelse. 
14. Klicka på **Sälj** i **åtgärdsfönstret**.
15. Klicka på **Försäljningsorderbekräftelse**.
16. Stäng sidan.

## <a name="confirm-multiple-sales-orders-at-once"></a>Bekräfta flera försäljningsorder samtidigt
1. Gå till **Försäljning och marknadsföring > Försäljningsorder > Orderbekräftelse > Bekräfta försäljningsorder**.
2. Klicka på **Välj**.
3. Välj den post som refererar till fältet **Kundkonto** i listan på fliken **Intervall**.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Kriterier**.
5. Hitta och välj kundkontot som har flera order som du vill massbekräfta. Om du använder USMF kan du välja kontot US-027.  
6. Klicka på **OK**.
    - På fliken **Översikt** visas en lista över order som matchar frågekriterierna. Dessa inkluderas i bekräftelsen.  
    - I fältet **Samlingsuppdatering** för anges avsnitt **parameter** som ska användas för att summera flera order till ett bekräftelsedokument. Som standard kopieras alternativet från inställningen **Standardvärden för samlingsuppdatering** på sidan **Parametrar för kundreskontra**.  
7. Välj "Order" i **Samlingsuppdatering** för fält. Minimiparametrarna som krävs för att skapa samlingsuppdateringar är **Fakturakonto** och **Valuta**. Det innebär att samlingsuppdateringar som har olika fakturakonton och olika valutor inte är tillåtna. Ytterligare parametrar kan ställas in på sidan **Samlingsuppdateringsparametrar** som är tillgänglig från sidan **Parametrar för kundreskontra**. 
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Försäljningsorder**.
9. Markera det ordernummer som du vill ska vara samlingsorder i listan.
10. Klicka på **Ordna**.
11. Klicka på **OK**.
12. Klicka på **OK**.

