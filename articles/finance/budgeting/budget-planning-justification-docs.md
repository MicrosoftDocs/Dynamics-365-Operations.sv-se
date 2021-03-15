---
title: Motiveringsdokument för budgetplan
description: Motiveringsdokument förklarar varför det är nödvändigt med en specifik budget.
author: panolte
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanJustificationTemplate
audience: Application User
ms.reviewer: roschlom
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9ca0c291b5d446325f6be6b6bed612bd26e7c640
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019213"
---
# <a name="budget-planning-justification-documents"></a>Motiveringsdokument för budgetplan

[!include [banner](../includes/banner.md)]

Motiveringsdokument förklarar varför det är nödvändigt med en specifik budget. 

En budgetplansmall skapas av den budgetansvarige i Microsoft Word och tilldelas till aktuell budgetplaneringsprocess. Budgetägaren kan sedan öppna mallen och låta datan fyllas i automatiskt i Word baserat på sin budgetbegäran. De kan sedan lägga till ytterligare text eller data innan de sparar, samt bifoga sitt personliga motiveringsdokument till sin budgetplan.

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a>Ställa in Microsoft Dynamics Office-tillägget för Microsoft Word

1.  Öppna ett nytt Microsoft Word-dokument.
2.  Klicka på **Infoga** i menyfliksområdet och på **Butik**.
3.  Sök efter Microsoft Dynamics Office-tillägget och klicka på **Lägg till**.
4.  Klicka på **Lägg till serverinformation** i fönstret till höger.
5.  Skriv eller klistra in serverns URL och klicka på **OK**.

##### <a name="define-the-justification-template-in-microsoft-word"></a>Definiera justeringsmallen i Microsoft Word

1.  Klicka på **Design** i Microsoft Dynamics Office-tillägget när du loggar in.
2.  Använd knappen **Lägg till fält** för rubrikinformation.
3.  Markera enhetsdatakälla för BudgetPlanJustification och klicka på **Nästa**. **Obs!** Denna enhet krävs för samtliga motiveringsdokument. Andra enheter kan användas, men överföringen tillbaka till Microsoft Dynamics 365 Finance misslyckas om inte denna enhet ingår.
4.  Lägg till etiketterna och värdena BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter och DocumentNumber i Word-dokumentet. **Obs!** Du kan använda dina egna etiketter i stället för standardetiketter vid behov.
5.  Klicka på **Klart** för att slutföra rubrikavsnittet.
6.  Klicka på **Lägg till tabell** för att se information på radnivå om budgetplanbelopp.
7.  Markera återigen enhetsdatakällan för BudgetPlanJustification och klicka på **Nästa**.
8.  Lägg till fält för EffectiveDate, ScenarioName, AccountDisplayValue och AccountingCurrencyExpenseAmount. **Obs!** Om det finns kommentarer att lägga till inom enskilda budgetplansrader, kan dessa läggas till i den här tabellen.
9.  Lägg till eventuella ytterligare instruktioner till slutanvändaren, och utför all nödvändig formatering eller putsning på dokumentet.
10. Spara dokumentet på din lokala dator och stäng filen innan du fortsätter.

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a>Skapa den budgetplaneringsprocess som ska använda motiveringsmallen

1.  Gå till **Budgetering** &gt; **Inställningar** &gt; **Budgetplanering** &gt; **Malla för motiveringsdokument**.
2.  Klicka på **Ny** och bläddra till det nya Microsoft Word-dokumentet.
3.  Ange ett visningsnamn och en beskrivning för mallen. Klicka på **OK**.
4.  Navigera till **Budgetering** &gt; **Inställningar** &gt; **Budget** **planering** &gt; **Budgetplaneringsprocess**.
5.  Välj den process där justeringsmallen ska användas, och klicka på **Redigera**.
6.  I fältet **Mall för motiveringsdokument** markerar du önskad mall och sparar.

##### <a name="edit-and-save-personalized-justification-documents"></a>Redigera och spara personliga motiveringsdokument

1.  Skapa en ny budgetplan eller öppna en befintlig budgetplan.
2.  I listrutan **Motivering** väljer du **Skapa ny motivering**.
3.  När du har fyllt i uppgifterna väljer att överföra anpassade dokumentet via listrutan **Motivering**.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]