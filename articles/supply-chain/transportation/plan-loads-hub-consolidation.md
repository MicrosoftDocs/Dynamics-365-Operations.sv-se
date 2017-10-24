---
title: "Planera laster med hjälp av navkonsolidering"
description: "Den här artikeln beskriver funktionen för att konsolidera försändelser i ett nav när du levererar varor från olika lagerställen till samma kund eller när du tar emot varor från flera leverantörer på samma lagerställe."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 92273
ms.assetid: d27b0926-a534-4caf-a2a3-acbc7c440bca
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3145febe40108e50b263514de1ca541dd914b7c5
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="plan-loads-using-hub-consolidation"></a>Planera laster med hjälp av navkonsolidering

[!include[banner](../includes/banner.md)]


Den här artikeln beskriver funktionen för att konsolidera försändelser i ett nav när du levererar varor från olika lagerställen till samma kund eller när du tar emot varor från flera leverantörer på samma lagerställe.

Det kan vara användbart att konsolidera försändelser i ett nav när du levererar varor från olika lager till samma kund eller när varorna levereras från flera leverantörer till samma lagerställe.

## <a name="building-loads"></a>Bygga laster
Innan du kan använda navkonsolidering måste du aktivera alternativet **Transportplanering**på sidan **Parametrar för transporthantering**. Du måste också skapa nav där konsolideringen ska utföras. Följande diagram visar ett exempel på navkonsolidering. I det här fallet ska försäljningsorder från olika lagerställen till samma kund. Grundläggande laster skapas utifrån försäljningsorder på vanligt sätt med hjälp av sidan **Workbench för lastplanering**. Om du vill konsolidera två laster i ett nav innan de levereras till kunden, gå till sidan **Workbench för lastplanering**, till fältet **Transport** och välj **Navkonsolidering**. Om du väljer rätt nav för varje last kommer lasterna att ha navet som avlämningsmål. Du kommer även att ha två "rader för transportförfrågan" i avsnittet **Tillgång och efterfrågan** på sidan **Workbench för lastplanering**. Du kan sedan lägga till dessa två rader till en ny last. Den nya lasten kommer att ha båda försäljningsorderraderna och kommer även att ha navet som hämtningsadress och kunden A som avlämningsmål. De tre lasterna är sedan klara för klassificering och kan skickas som andra laster. Du kan välja vilket transportföretag systemet ska föreslå för varje last. [![Hubbkonsolidering](./media/hubconsol.jpg)](./media/hubconsol.jpg) Du kan även använda samma metod för att konsolidera laster för flera överföringsorder. I detta fall är kunden A i föregående diagram ett lagerställe. Alternativt kan du konsolidera laster för flera inköpsorder, där lasterna levereras från olika leverantörer till samma lagerställe. Du kan ha fler än ett konsolideringsnav och konsolidera i flera nav för fler laster som kommer från olika lagerställen. När du skapar dina grundlaster och använder navkonsolideringsalternativet kan du skapa nya laster med hjälp av konsoliderade rader för transportförfrågan. Klassificera och skicka sedan dina laster.




