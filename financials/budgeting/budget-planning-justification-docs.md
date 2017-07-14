---
title: "Motiveringsdokument för budgetplan"
description: "Motiveringsdokument förklarar varför det är nödvändigt med en specifik budget."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 1d23c0e1725a39d25d2be8971f541b2c31bbe859
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Motiveringsdokument för budgetplan
<a id="budget-planning-justification-documents" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Motiveringsdokument förklarar varför det är nödvändigt med en specifik budget. 

En budgetplansmall skapas av den budgetansvarige i Microsoft Word och tilldelas till aktuell budgetplaneringsprocess. Budgetägaren kan sedan öppna mallen och låta datan fyllas i automatiskt i Word baserat på sin budgetbegäran. De kan sedan lägga till ytterligare text eller data innan de sparar, samt bifoga sitt personliga motiveringsdokument till sin budgetplan.

##### Konfigurera Microsoft Dynamics Office-tillägg för Microsoft Word
<a id="set-up-microsoft-dynamics-office-add-in-for-microsoft-word" class="xliff"></a>

1.  Öppna ett nytt Microsoft Word-dokument.
2.  Klicka på **Infoga** i menyfliksområdet och på **Butik**.
3.  Sök efter Microsoft Dynamics Office-tillägget och klicka på **Lägg till**.
4.  Klicka på **Lägg till serverinformation** i fönstret till höger.
5.  Skriv eller klistra in serverns URL och klicka på **OK**.

##### Definiera motiveringsmallen i Microsoft Word
<a id="define-the-justification-template-in-microsoft-word" class="xliff"></a>

1.  Klicka på **Design** i Microsoft Dynamics Office-tillägget när du loggar in.
2.  Använd knappen **Lägg till fält** för rubrikinformation.
3.  Markera enhetsdatakälla för BudgetPlanJustification och klicka på **Nästa**. **Obs!** Denna enhet krävs för samtliga motiveringsdokument. Andra enheter kan användas, men överföringen tillbaka till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition misslyckas om inte denna enhet ingår.
4.  Lägg till etiketterna och värdena BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter och DocumentNumber i Word-dokumentet. **Obs!** Du kan använda dina egna etiketter i stället för standardetiketter vid behov.
5.  Klicka på **Klart** för att slutföra rubrikavsnittet.
6.  Klicka på **Lägg till tabell** för att se information på radnivå om budgetplanbelopp.
7.  Markera återigen enhetsdatakällan för BudgetPlanJustification och klicka på **Nästa**.
8.  Lägg till fält för EffectiveDate, ScenarioName, AccountDisplayValue och AccountingCurrencyExpenseAmount. **Obs!** Om det finns kommentarer att lägga till inom enskilda budgetplansrader, kan dessa läggas till i den här tabellen.
9.  Lägg till eventuella ytterligare instruktioner till slutanvändaren, och utför all nödvändig formatering eller putsning på dokumentet.
10. Spara dokumentet på din lokala dator och stäng filen innan du fortsätter.

##### Skapa den budgetplaneringsprocess som ska använda motiveringsmallen
<a id="set-up-the-budget-planning-process-to-use-the-justification-template" class="xliff"></a>

1.  Navigera till **Budgetering** &gt; **Inställningar** &gt; **Budgetplanering** &gt; **Malla för motiveringsdokument** i Finance and Operations.
2.  Klicka på **Ny** och bläddra till det nya Microsoft Word-dokumentet.
3.  Ange ett visningsnamn och en beskrivning för mallen. Klicka på **OK**.
4.  Navigera till **Budgetering** &gt; **Inställningar** &gt; **Budget****planering** &gt; **Budgetplaneringsprocess**.
5.  Välj den process där justeringsmallen ska användas, och klicka på **Redigera**.
6.  I fältet **Mall för motiveringsdokument** markerar du önskad mall och sparar.

##### Redigera och spara personliga motiveringsdokument
<a id="edit-and-save-personalized-justification-documents" class="xliff"></a>

1.  Skapa en ny budgetplan i Finance and Operations, eller öppna en befintlig budgetplan.
2.  I listrutan **Motivering** väljer du **Skapa ny motivering**.
3.  När du har fyllt i uppgifterna väljer att överföra anpassade dokumentet via listrutan **Motivering**.





