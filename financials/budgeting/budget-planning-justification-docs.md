---
title: Budget planering handlingar
description: "Handlingar föreskriva en de begär en budget för att förklara varför det är nödvändigt att en specifik budget."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: c86d01fec3d8d7c210c7e73a034f4e9e384a0dcf
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning-justification-documents"></a>Budget planering handlingar

Handlingar föreskriva en de begär en budget för att förklara varför det är nödvändigt att en specifik budget. 

En budgetplansmall skapas av budgeten projektledaren i Microsoft Word och tilldelas till aktuella budgetplaneringsprocessen. Budget ägare kan sedan öppna mallen och data fylls i automatiskt i Word baserat på deras begäran budget. De kan sedan lägga till ytterligare text eller data innan du sparar och deras personliga justeringsdokumentet avser deras budgetplanen.

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a>Konfigurera Microsoft Dynamics Office-tillägg för Microsoft Word

1.  Öppna ett nytt Microsoft Word-dokument.
2.  Klicka på **infogar** i menyfliksområdet och på **butiken**.
3.  Sök efter Microsoft Dynamics Office-tillägget och klickar på **Lägg till**.
4.  I Word i rutan till höger klickar du på **serverinformation lägger du till**.
5.  Skriv eller klistra in serverns URL och klicka på **OK**.

##### <a name="define-the-justification-template-in-microsoft-word"></a>Definiera justering-mall i Word

1.  Klicka på **Design** i Microsoft Dynamics Office tillägget när du loggar in.
2.  Information i serviceorderhuvudet, Använd den **läggs** knappen.
3.  Markera önskad enhet för BudgetPlanJustification och på **nästa**. **Anmärkning:** entiteten krävs för berättigande dokument. Andra enheter kan användas men tillbaka till Microsoft Dynamics 365 för överföringen misslyckas om inte entiteten ingår.
4.  Lägg till BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter och DocumentNumber etiketter och värden i Word-dokumentet. **Anmärkning:** du kan använda egna etiketter i stället för standardetiketter vid behov.
5.  Klicka på **har gjort** att slutföra rubrikavsnittet.
6.  Raden Rapportnivå detaljer för planen budgetbelopp klickar du på **Lägg till tabell**.
7.  Markera önskad enhet för BudgetPlanJustification igen och klicka på **nästa**.
8.  Lägga till fält för EffectiveDate, ScenarioName, AccountDisplayValue och AccountingCurrencyExpenseAmount. **Anmärkning:** om det finns kommentarer till inom enskilda budgetplansrader kan de läggas till den här tabellen.
9.  Lägg till eventuella ytterligare instruktioner för att förse användaren och utföra nödvändiga formatering eller stil i dokumentet.
10. Spara dokumentet på den lokala datorn och stäng filen innan du fortsätter.

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a>Ställ in budgetplaneringsprocessen använda mallen justering

1.  Gå till Microsoft Dynamics 365 för operationer **budget**&gt;**inställningar**&gt;**budgetplanering**&gt;**justering dokumentmallar**.
2.  Klicka på **New** och bläddra till det nya Microsoft Word-dokumentet.
3.  Ange ett namn för mallen och en beskrivning. Click **OK**.
4.  Gå till **budget**&gt;**inställningar**&gt;**Budget****planering av**&gt;**Budget planeringsprocessen**.
5.  Välj den process där justering mallen ska användas och på **redigera**.
6.  I den **justering dokumentmall** markerar du önskad mall och spara.

##### <a name="edit-and-save-personalized-justification-documents"></a>Redigera och spara personliga handlingar

1.  Skapa en ny budgetplan i Dynamics 365 för operationer, eller öppna en befintlig budgetplan.
2.  I den **justering** listrutan väljer du **Skapa ny justering**.
3.  När du har fyllt i uppgifterna väljer för att överföra anpassade dokumentet från den **justering** listrutan.



