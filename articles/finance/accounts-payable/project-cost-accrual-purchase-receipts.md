---
title: Periodisering av projektkostnad på inköpsinleveranser
description: I det här avsnittet beskrivs hur upplupna projektkostnader från inköpsinleveranser kan spåras i Microsoft Dynamics 365 Finance.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostControlCommittedCost
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0a930b4921a29d5ce561ce0e958733f0c3261b81
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447964"
---
# <a name="project-cost-accrual-on-purchase-receipts"></a>Periodisering av projektkostnad på inköpsinleveranser

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur upplupna projektkostnader från inköpsinleveranser kan spåras i Microsoft Dynamics 365 Finance. 

Fakturor för ett projekt kommer ofta senare än varorna och tjänster som levereras, vilket betydligt kan påverka projektets nyckeltal (KPI:er). Det är viktigt att kunna spåra transaktionerna i både ekonomiska rapporter och projektrapporter.

I följande exempelscenarion illustreras detta. 

Contoso Consulting har påbörjat ett nytt molndistributionsprojekt. En inköpsorder skapas för att köpa en dator för projektet. Datorn kommer att kosta $1500 och installationstjänster kostar $150. Leverantören har levererat och installerat datorn, men fakturan har ännu inte nått Contoso Consulting. Projektledaren vill se de upplupna projektkostnaden på $1650 innan fakturan levereras. Kostnaden bör även återspeglas i företagets månadsslutet bokslut. 

Upplupen kostnad måste registreras på både ekonomisk nivå och projektnivå för rapportering. Den ekonomiska uppdateringen av produktinleveransen spåras för artikeln och upphandlingskategorier. 

För artiklar, på sidan **Parametrar för leverantörsreskontra**, anger du alternativet **Bokför produktinleveranser i redovisningen**.
[![Sida för parametrar för leverantörsreskontra](./media/accruals1-1024x409.png)](./media/accruals1.png) 

För upphandlingskategorier, på sidan **Kategoripolicyregel**, väljer du **Inköp**-principer och väljer sedan **Periodisera inköpskostnad vid inleverans** för varje anskaffningskategori.
[![Sida för kategoripolicyregel](./media/accruals2-1024x569.png)](./media/accruals2.png) 

Kontona **Inköpsomkostnad, ej fakturerad** och **Inköp, periodisering** i **Inställningar för bokföring** kommer att användas när verifikationer som är relaterade till produktinleveransen bokförs.

Med samma scenariot ska vi titta på hur bokföring av en produktinleverans påverkar redovisningen och projektinformationen. 

**Steg 1:** Skapa och bekräfta en ny inköpsorder för att projektet för att registrera inköp av en dator för $1500 och installationstjänster för $150.
[![Skapa ny inköpsorder](./media/accruals4-1024x497.png)](./media/accruals4.png) 

När inköpsordern har bekräftats skapas transaktioner för utfästa kostnader för projektet. 
[![Skapade transaktioner](./media/accruals5-1024x219.png)](./media/accruals5.png) 

> [!NOTE]
> Transaktionerna för de utfästa kostnaderna har fältet **Transaktionsursprung** inställt på **Inköpsorder**. Skapa och bekräfta en inköpsorder skapar inte transaktioner för ett projekt. 

**Steg 2:** Varor och tjänster levereras och en produktinleverans registreras. 

Bokför en produktinleverans skapar och bokför en verifikation i redovisningen. Verifikationen debiterar inköpsutgiften, ofakturerat konto och krediterar kontot för inköpsperiodiseringen. 
[![Verifikationstransaktioner](./media/accruals6-1024x214.png)](./media/accruals6.png)

> [!NOTE]
> Bokför en produktinleverans använder bokföringsinställningar för anskaffningskategorier och produkter, inte bokföringsinställningarna för projektkategorier. För att korrekt återspegla den ekonomiska effekten av inköpsperiodiseringar, måste denna inställning justeras. 

Du kan mappa anskaffningskategorier till projektkategorier på sidan **Anskaffningskategori**.
[![Sidan anskaffningskategori](./media/accruals7-1024x390.png)](./media/accruals7.png)

**Steg 3:** Skapa ett utkast till leverantörsfaktura. 

Bokföringen av en produktinleverans påverkar inte projektinformationen. Som tillfällig lösning kan du generera du ett utkast till leverantörsfaktura direkt när inleveransen har bokförts. Gå till sidan **Inköpsorder** &gt; **fliken Faktura** &gt; **Generera** &gt; **Faktura**. Då skapas ett väntande fakturadokumentet som uppdaterar projektinformation. 

När ett utkast till leverantörsfaktura skapas genereras pågående projekttransaktioner. 
[![Pågående projekttransaktioner](./media/accruals8-1024x225.png)](./media/accruals8.png) 

På sidan **Utfästa kostnader** stängs poster som skapats i steg 1 och nya poster skapas för att återspegla kostnadsåtaganden från den väntande leverantörsfakturan. Fältet **Transaktionsursprung** för den utfästa kostnaden ställs in på **Leverantörsfaktura**.
[![Sidan Utfästa kostnader](./media/accruals9-1024x200.png)](./media/accruals9.png)

Leverantörsfakturan förblir väntande tills den faktiska leverantörsfakturan anländer.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]