---
title: Ingående balanser saknas i årsbokslut
description: Det här ämnet förklarar varför ingående balanser kan saknas vid årsbokslut och hur du återskapar dem om de saknas.
author: kweekley
ms.date: 05/12/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4478f2b46f984c97ff01588098d64953dedf476e7f3f76aeecb29a0ff0074b9d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735472"
---
# <a name="year-end-close-missing-opening-balances"></a>Ingående balanser saknas i årsbokslut

[!include [banner](../includes/banner.md)]

Det här ämnet förklarar varför ingående balanser kan saknas vid årsbokslut och hur du återskapar dem om de saknas.

### <a name="symptom"></a>Symptom

Varför finns det inga ingående balanser efter körning av redovisningens årsbokslut? 

### <a name="resolution"></a>Lösning

Saker att kontrollera vid ett årsbokslut i redovisningen och när du har genererat en råbalans som inte visar ingående balanser för nästa räkenskapsår.

Om fältet **Ångra föregående slut** är inställt på **Ja** återförs föregående årsbokslut för samma räkenskapsår. När du kör en process för att återföra årsboksluten tas alla utgående och ingående balansposter bort, som om årsbokslutet aldrig hade körts. Verifikationerna tas också bort. Årsbokslutet körs inte automatiskt igen. Du måste starta processen på nytt och nu uppdatera alternativet **Ångra föregående slut** till **Nej**.

Det här scenariot beskrivs i ämnet vanliga frågor och svar om årsbokslut. Mer information finns i [Vanliga frågor och svar om aktiviteter för årsavslut](faq-year-end-activities.md).

### <a name="symptom"></a>Symptom

Jag körde årsbokslut med alternativet **Ångra föregående stängning** inställt på **Nej** och jag har fortfarande inga ingående balanser för räkenskapsåret.

### <a name="resolution"></a>Lösning

Kontrollera för batchjobbets status. Årsbokslut innehåller ett antal separata uppgifter, men det viktigaste steget är batchaktiviteten med aktivitetsbeskrivningen **Steg 5.0.0**. Bokföring av IB-transaktioner och eventuellt UB-transaktioner i redovisningen sker under det här steget. 

[![Lista med batchhistorik.](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)

Om det här steget har slutförts, men du ser inga ingående balanser på sidan **Förfrågan om råbalans** (**Redovisning > Förfrågningar och rapporter > Råbalans**) måste du granska resultatet av årsbokslutets batchjobb för att kontrollera om steget Återskapa saldon har slutförts.

[![Resultat av årsbokslutets batchjobb.](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)

Om det här steget av någon anledning inte slutfördes, bokfördes troligen IB-transaktionerna (och valfria UB). Du kan kontrollera att redovisningstransaktionerna bokfördes på sidan **Förfrågan om verifikationstransaktioner** genom att ange verifikationsnumret och datumet som angavs i dialogrutan Årsbokslut för året som du stängde (**Redovisning > Förfrågningar och rapporter > Verifikationstransaktioner**).

[![Förfrågan om verifikationstransaktioner.](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)

Om det finns ingående verifikationer (och eventuellt utgående verifikationer) behöver du inte köra årsbokslutet igen. Se i stället nästa avsnitt för information om att gå vidare.

### <a name="symptom"></a>Symptom

Måste jag köra om hela årsbokslutsprocessen om steget Återskapa saldon i årsbokslutet inte slutfördes?

### <a name="resolution"></a>Lösning

Steget Återskapa saldon uppdaterar redovisningssaldona som används när förfrågan Råbalans genereras.  Det är det sista steget i årsbokslutsprocessen.  Om det här steget är det enda som inte slutfördes har redovisningstransaktionerna bokförts.  Du behöver inte köra årsbokslutet på nytt. Det går att köra processen som återskapar saldona manuellt på sidan **Ekonomiska dimensionsuppsättningar** (**Redovisning > Kontoplan > Dimensioner > Ekonomiska dimensionsuppsättningar**).

[![Knappen Återskapa saldon på sidan Ekonomiska dimensionsuppsättningar.](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)

Om det här steget tar lång tid att bearbeta rekommenderar vi att du granskar metodtipsen för ekonomiska dimensionsuppsättningar enligt beskrivningen i [Metodtips för uppdatering av ekonomiska dimensionsuppsättningar](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets). 

