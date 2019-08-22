---
title: Periodisering av projektkostnad på inköpsinleveranser
description: I det här avsnittet beskrivs hur upplupna projektkostnader från inköpsinleveranser kan spåras i Microsoft Dynamics 365 for Finance and Operations.
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
ms.openlocfilehash: 6c1397107c179da56e8dcf4b556140dc06d8f14d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834595"
---
# <a name="project-cost-accrual-on-purchase-receipts"></a>Periodisering av projektkostnad på inköpsinleveranser

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur upplupna projektkostnader från inköpsinleveranser kan spåras i Microsoft Dynamics 365 for Finance and Operations. 

Fakturor för ett projekt kommer ofta senare än varorna och tjänster som levereras, vilket betydligt kan påverka projektets nyckeltal (KPI:er). Det är viktigt att kunna spåra transaktionerna i både ekonomiska rapporter och projektrapporter.

I följande exempelscenarion illustreras detta. 

Contoso Consulting har påbörjat ett nytt molndistributionsprojekt. En inköpsorder skapas för att köpa en dator för projektet. Datorn kommer att kosta $1500 och installationstjänster kostar $150. Leverantören har levererat och installerat datorn, men fakturan har ännu inte nått Contoso Consulting. Projektledaren vill se de upplupna projektkostnaden på $1650 innan fakturan levereras. Kostnaden bör även återspeglas i företagets månadsslutet bokslut. 

Upplupen kostnad måste registreras på både ekonomisk nivå och projektnivå för rapportering. I Finance and Operations kan den ekonomiska uppdateringen av produktinleveransen spåras för artikeln och upphandlingskategorier. 

För artiklar, på sidan **Parametrar för leverantörsreskontra**, anger du alternativet **Bokför produktinleveranser i redovisningen**.
[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png) 

För upphandlingskategorier, på sidan **Kategoripolicyregel**, väljer du **Inköp**-principer och väljer sedan **Periodisera inköpskostnad vid inleverans** för varje anskaffningskategori.
[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png) 

Kontona **Inköpsomkostnad, ej fakturerad** och **Inköp, periodisering** i **Inställningar för bokföring** kommer att användas när verifikationer som är relaterade till produktinleveransen bokförs.
[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png) 

Med samma scenariot ska vi titta på hur bokföring av en produktinleverans påverkar redovisningen och projektinformationen. 

**Steg 1:** Skapa och bekräfta en ny inköpsorder för att projektet för att registrera inköp av en dator för $1500 och installationstjänster för $150.
[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png) 

När inköpsordern har bekräftats skapas transaktioner för utfästa kostnader för projektet. 
[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png) 

> [!NOTE]
> Transaktionerna för de utfästa kostnaderna har fältet **Transaktionsursprung** inställt på **Inköpsorder**. Skapa och bekräfta en inköpsorder skapar inte transaktioner för ett projekt. 

**Steg 2:** Varor och tjänster levereras och en produktinleverans registreras. 

Bokför en produktinleverans skapar och bokför en verifikation i redovisningen. Verifikationen debiterar inköpsutgiften, ofakturerat konto och krediterar kontot för inköpsperiodiseringen. 
[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)

> [!NOTE]
> Bokför en produktinleverans använder bokföringsinställningar för anskaffningskategorier och produkter, inte bokföringsinställningarna för projektkategorier. För att korrekt återspegla den ekonomiska effekten av inköpsperiodiseringar, måste denna inställning justeras. 

Du kan mappa anskaffningskategorier till projektkategorier på sidan **Anskaffningskategori**.
[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)

**Steg 3:** Skapa ett utkast till leverantörsfaktura. 

I Finance and Operations påverkar bokföringen av en produktinleverans inte projektinformationen. Som tillfällig lösning kan du generera du ett utkast till leverantörsfaktura direkt när inleveransen har bokförts. Gå till sidan **Inköpsorder** &gt; **fliken Faktura** &gt; **Generera** &gt; **Faktura**. Då skapas ett väntande fakturadokumentet som uppdaterar projektinformation. 

När ett utkast till leverantörsfaktura skapas genereras pågående projekttransaktioner. 
[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png) 

På sidan **Utfästa kostnader** stängs poster som skapats i steg 1 och nya poster skapas för att återspegla kostnadsåtaganden från den väntande leverantörsfakturan. Fältet **Transaktionsursprung** för den utfästa kostnaden ställs in på **Leverantörsfaktura**.
[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)

Leverantörsfakturan förblir väntande tills den faktiska leverantörsfakturan anländer.



