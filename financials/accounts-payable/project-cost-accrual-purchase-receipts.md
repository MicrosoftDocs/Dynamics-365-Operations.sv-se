---
title: "Projekt-kostnad påförs för inleveranser av inköp"
description: "Det här avsnittet beskrivs hur upplupna projektkostnader från inleveranser kan spåras i Microsoft Dynamics 365 för inköp."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 27a0a71095dce46c0119b32a92f8c4dce0f42e43
ms.lasthandoff: 03/31/2017


---

# <a name="project-cost-accrual-on-purchase-receipts"></a>Projekt-kostnad påförs för inleveranser av inköp

Det här avsnittet beskrivs hur upplupna projektkostnader från inleveranser kan spåras i Microsoft Dynamics 365 för inköp. 

Fakturor för ett projekt kommer ofta senare än varorna och tjänster som levereras som kan påverka en betydande projekt prestationsindikatorer (KPI). Det är viktigt att kunna spåra transaktionerna i både ekonomiska och projekt rapporter.

Följande exempel illustrerar detta. 

Contoso konsulttjänster har påbörjat ett nytt projekt i molnet distribution. En inköpsorder skapas om du vill köpa en dator för projektet. Datorn kommer att kosta $1500 och installationstjänster kostar $150. Leverantören har levererats och installerat på datorn, men fakturan har ännu inte nått Contoso konsulttjänster. Projektledaren vill se projektet kostnaden påförs av $1650 innan fakturan levereras. Kostnaden bör även återspeglas i företagets månad slutet bokslut. 

Upplupen kostnad måste registreras på nivån finansiella- och projektnivå för rapportering. I Dynamics 365 för operationer, kan den ekonomiska uppdateringen av produktinleveransen spåras för artikeln och upphandling kategorier. 

För artiklar i den **parametrar för leverantörsreskontra** anger den **du bokföra produktinleveranser i redovisningen** alternativ.
[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png) 

För upphandling kategorier på den **Kategoripolicyregeln** anger **inköp** principer och välj sedan **Periodisera inköpskostnad vid inleverans** för varje anskaffningskategori.
[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png) 

Den **Inköpsomkostnad, ej fakturerad** och **inköp, periodisering** konton i **bokföringsinställningar** kommer att användas när verifikationer som är relaterade till produktinleveransen bokförs.
[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png) 

Med det här samma scenariot ska vi titta hur bokföring av en produktinleverans påverkar redovisningen och projektinformation. 

**Steg 1:** skapa och bekräfta en ny inköpsorder för att projektet ska registrera inköp av en dator för installation och $1500 tjänster för $150.
[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png) 

När inköpsordern har bekräftats skapas transaktioner för utfäst kostnad för projektet. 
[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png) 

> [!NOTE]
> Transaktionerna för den utfästa kostnaden får den **Transaktionsursprung** fältet **inköpsordern**. Skapa och bekräfta en inköpsorder kan inte skapa transaktioner för ett projekt. 

**Steg 2:** varor och tjänster som levereras och en produktinleverans registreras. 

Bokför en produktinleverans skapar och bokför du en verifikation i redovisningsmodulen. Verifikationen debitera inköp utgift, ofakturerad kontot och krediteras kontot för ingående periodiseringen. 
[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)

> [!NOTE]
> Bokför en produktinleverans via bokföringsinställningen anskaffningskategorier och produkter inte bokföringsinställningarna för projektkategorier. För att korrekt återspegla ekonomiska effekten av inköp, periodisering, måste denna inställning ska justeras. 

Du kan mappa anskaffningskategorier som ska projektkategorier på de **anskaffningskategori** sida.
[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)

**Steg 3:** skapar en leverantörsfaktura utkast. 

I Dynamics 365 för operationer påverkar bokför en produktinleverans inte projektinformation. Som tillfällig lösning kan generera du en leverantörsfaktura utkast direkt när inleveransen har bokförts. Gå till den **inköpsordern** page &gt;**fakturan på fliken**&gt;**generera**&gt;**fakturan**. Då skapas en pågående fakturadokumentet som uppdaterar projektinformation. 

Skapa en leverantörsfaktura utkast genererar pågående projekttransaktioner. 
[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png) 

I den **utfästa kostnader** sidan poster som skapats i steg 1 stängs och nya poster skapas för att återspegla kostnaderna åtagande från väntande leverantörsfaktura. Den **Transaktionsursprung** för den utfästa kostnaden som sätts till **leverantörsfakturan**.
[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)

Leverantörsfakturan förblir väntande tills den faktiska leverantörsfakturan anländer.


