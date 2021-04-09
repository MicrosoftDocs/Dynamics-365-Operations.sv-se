---
title: Frågor och svar om ekonomisk rapportering
description: Det här avsnittet finns en lista med frågor om ekonomisk rapportering som andra användare har haft.
author: jiwo
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a0718db77399901acc8c88278c5b373b77b3cb16
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811320"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="0cff4-103">Frågor och svar om ekonomisk rapportering</span><span class="sxs-lookup"><span data-stu-id="0cff4-103">Financial reporting FAQ</span></span> 

<span data-ttu-id="0cff4-104">Det här avsnittet finns en lista med frågor om ekonomisk rapportering som andra användare har haft.</span><span class="sxs-lookup"><span data-stu-id="0cff4-104">This topic lists questions related to financial reporting that other users have had.</span></span> 


## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a><span data-ttu-id="0cff4-105">Hur begränsar jag åtkomsten till en rapport med hjälp av trädsäkerhet?</span><span class="sxs-lookup"><span data-stu-id="0cff4-105">How do I restrict access to a report using Tree security?</span></span>

<span data-ttu-id="0cff4-106">Scenario: Demoföretaget USMF har en balansräkningsrapport som alla användare av Ekonomisk rapportering inte ska kunna visa i D365.</span><span class="sxs-lookup"><span data-stu-id="0cff4-106">Scenario: The USMF demo company has a Balance sheet report that it doesn’t want all Financial reporting users to be able to view in D365.</span></span> <span data-ttu-id="0cff4-107">Lösning: Du kan använda trädsäkerhet för att begränsa åtkomsten till en enskild rapport så att bara vissa användare kan komma åt rapporten.</span><span class="sxs-lookup"><span data-stu-id="0cff4-107">Solution: You can utilize Tree security to restrict access to a single report so that only certain users can access the report.</span></span> 

1.  <span data-ttu-id="0cff4-108">Logga in på Rapportdesignern i ekonomisk rapportering</span><span class="sxs-lookup"><span data-stu-id="0cff4-108">Log into Financial Reporter Report Designer</span></span>

2.  <span data-ttu-id="0cff4-109">Skapa en ny träddefinition (Arkiv | Nytt | Träddefinition) a.</span><span class="sxs-lookup"><span data-stu-id="0cff4-109">Create a new Tree Definition (File | New | Tree Definition) a.</span></span>    <span data-ttu-id="0cff4-110">Dubbelklicka på **Sammanfattning** i kolumnen **Enhetssäkerhet**.</span><span class="sxs-lookup"><span data-stu-id="0cff4-110">Double-click the **Summary** line in the **Unit Security** column.</span></span>
  <span data-ttu-id="0cff4-111">i.</span><span class="sxs-lookup"><span data-stu-id="0cff4-111">i.</span></span>    <span data-ttu-id="0cff4-112">Klicka på Användare och grupper.</span><span class="sxs-lookup"><span data-stu-id="0cff4-112">Click Users and Groups.</span></span>  
          <span data-ttu-id="0cff4-113">1. Välj de användare eller grupper som ska ha tillgång till rapporten.</span><span class="sxs-lookup"><span data-stu-id="0cff4-113">1.    Select the User(s) or Group that would like to access this report.</span></span> 
          
<span data-ttu-id="0cff4-114">[![användarskärm](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)</span><span class="sxs-lookup"><span data-stu-id="0cff4-114">[![user screen](./media/FR-FAQ_users.png)](./media/FR-FAQ_users.png)</span></span>

<span data-ttu-id="0cff4-115">[![säkerhetsskärm](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)</span><span class="sxs-lookup"><span data-stu-id="0cff4-115">[![security screen](./media/FR-FAQ_security.jpg)](./media/FR-FAQ_security.jpg)</span></span>

  <span data-ttu-id="0cff4-116">b.</span><span class="sxs-lookup"><span data-stu-id="0cff4-116">b.</span></span>    <span data-ttu-id="0cff4-117">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0cff4-117">Click **Save**.</span></span>
  
<span data-ttu-id="0cff4-118">[![knappen Spara](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)</span><span class="sxs-lookup"><span data-stu-id="0cff4-118">[![save button](./media/FR-FAQ_save.png)](./media/FR-FAQ_save.png)</span></span>

3.  <span data-ttu-id="0cff4-119">Lägg till den nya träddefinitionen i rapportdefinitionen</span><span class="sxs-lookup"><span data-stu-id="0cff4-119">In your Report Definition add your new Tree Definition</span></span>

<span data-ttu-id="0cff4-120">[![formulär för träddefinition](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)</span><span class="sxs-lookup"><span data-stu-id="0cff4-120">[![tree definition form](./media/FR-FAQ_tree-definition.jpg)](./media/FR-FAQ_tree-definition.jpg)</span></span>

<span data-ttu-id="0cff4-121">A.</span><span class="sxs-lookup"><span data-stu-id="0cff4-121">A.</span></span>  <span data-ttu-id="0cff4-122">När du är i träddefinitionen klickar du på Inställningar och under "Val av rapportenhet" i "Ta med alla enheter"</span><span class="sxs-lookup"><span data-stu-id="0cff4-122">While in the Tree Definition click on Setting and under “Reporting unit selection” check “Include all units”</span></span>

<span data-ttu-id="0cff4-123">[![formuläret Val av rapportenhet](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)</span><span class="sxs-lookup"><span data-stu-id="0cff4-123">[![reporting unit selection form](./media/FR-FAQ_reporting-unit-selection.jpg)](./media/FR-FAQ_reporting-unit-selection.jpg)</span></span>

<span data-ttu-id="0cff4-124">**Före:** [![skärmdump för före](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)</span><span class="sxs-lookup"><span data-stu-id="0cff4-124">**Before:** [![before screenshot](./media/FR-FAQ_before.png)](./media/FR-FAQ_before.png)</span></span>

<span data-ttu-id="0cff4-125">**Efter:** [![skärmdump för efter](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)</span><span class="sxs-lookup"><span data-stu-id="0cff4-125">**After:** [![after screenshot](./media/FR-FAQ_after.png)](./media/FR-FAQ_after.png)</span></span>

<span data-ttu-id="0cff4-126">Obs! Orsaken till meddelandet ovan är att min användare inte har tillgång till rapporten efter att ha tillämpat enhetssäkerhet.</span><span class="sxs-lookup"><span data-stu-id="0cff4-126">Note: Reason for the above message is my user does not have access to that report after applying Unit Security</span></span>



## <a name="how-do-i-determine-which-accounts-do-not-matching-my-balances-in-d365"></a><span data-ttu-id="0cff4-127">Hur kan jag ta reda på vilka konton som inte matchar mina saldon i D365?</span><span class="sxs-lookup"><span data-stu-id="0cff4-127">How do I determine which account(s) do not matching my balances in D365?</span></span>

<span data-ttu-id="0cff4-128">När du har en rapport som inte matchar vad du förväntade dig i D365, kan du följa några steg som beskrivs här för att identifiera dessa konton och avvikelserna.</span><span class="sxs-lookup"><span data-stu-id="0cff4-128">When you have a report that doesn't match what you would expect in D365, here are some steps you could take to identify those accounts and the variances.</span></span> 

### <a name="in-financial-reporter-report-designer"></a><span data-ttu-id="0cff4-129">I Rapportdesignern i ekonomisk rapportering</span><span class="sxs-lookup"><span data-stu-id="0cff4-129">In Financial Reporter Report Designer</span></span>

1.  <span data-ttu-id="0cff4-130">Skapa en ny raddefinition a.</span><span class="sxs-lookup"><span data-stu-id="0cff4-130">Create a new Row Definition a.</span></span>    <span data-ttu-id="0cff4-131">Klicka på Redigera | Infoga rader från Dimensioner i.</span><span class="sxs-lookup"><span data-stu-id="0cff4-131">Click Edit | Insert Rows from Dimensions i.</span></span>  <span data-ttu-id="0cff4-132">Välj MainAccount [![Välj huvudskärmen_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)</span><span class="sxs-lookup"><span data-stu-id="0cff4-132">Select MainAccount [![Select Main screen_](./media/FR-FAQ_selectmain_.png)](./media/FR-FAQ_selectmain_.png)</span></span>
    
    <span data-ttu-id="0cff4-133">ii.</span><span class="sxs-lookup"><span data-stu-id="0cff4-133">ii.</span></span> <span data-ttu-id="0cff4-134">Klicka på OK b.</span><span class="sxs-lookup"><span data-stu-id="0cff4-134">Click Ok b.</span></span>    <span data-ttu-id="0cff4-135">Spara raddefinitionen</span><span class="sxs-lookup"><span data-stu-id="0cff4-135">Save the Row Definition</span></span>

2.  <span data-ttu-id="0cff4-136">Skapa en ny kolumndefinition     [![Skapa en ny kolumndefinition](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)</span><span class="sxs-lookup"><span data-stu-id="0cff4-136">Create a new Column Definition     [![Create a new column definition](./media/FR-FAQ_column.png)](./media/FR-FAQ_column.png)</span></span>

3.  <span data-ttu-id="0cff4-137">Skapa en ny rapportdefinition a.</span><span class="sxs-lookup"><span data-stu-id="0cff4-137">Create a new Report Definition a.</span></span>    <span data-ttu-id="0cff4-138">Klicka på Inställningar och avmarkera [![formuläret Inställningar](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)</span><span class="sxs-lookup"><span data-stu-id="0cff4-138">Click Settings and uncheck [![Settings form](./media/FR-FAQ_settings.png)](./media/FR-FAQ_settings.png)</span></span>
   
4.  <span data-ttu-id="0cff4-139">Skapa rapporten.</span><span class="sxs-lookup"><span data-stu-id="0cff4-139">Generate the Report.</span></span> 

5.  <span data-ttu-id="0cff4-140">Exportera rapporten till Excel.</span><span class="sxs-lookup"><span data-stu-id="0cff4-140">Export the Report to Excel.</span></span>

### <a name="in-d365"></a><span data-ttu-id="0cff4-141">I D365:</span><span class="sxs-lookup"><span data-stu-id="0cff4-141">In D365:</span></span> 
1.  <span data-ttu-id="0cff4-142">Klicka på Redovisning | Förfrågningar och rapporter | Råbalans a.</span><span class="sxs-lookup"><span data-stu-id="0cff4-142">Click General Ledger | Inquiries and Reports | Trial Balance a.</span></span>    <span data-ttu-id="0cff4-143">Parametrar i.</span><span class="sxs-lookup"><span data-stu-id="0cff4-143">Parameters i.</span></span>  <span data-ttu-id="0cff4-144">Från datum: Räkenskapsårets början ii.</span><span class="sxs-lookup"><span data-stu-id="0cff4-144">From Date: Start of Fiscal Year ii.</span></span> <span data-ttu-id="0cff4-145">Till datum: Datumet du genererade rapporten för iii.</span><span class="sxs-lookup"><span data-stu-id="0cff4-145">To Date: Date you generated the report for iii.</span></span>    <span data-ttu-id="0cff4-146">Ekonomisk dimensionsuppsättning "Huvudkontouppsättning" [![Huvudkontoformulär](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)</span><span class="sxs-lookup"><span data-stu-id="0cff4-146">Financial Dimension Set “Main Account set” [![Main Account Form](./media/FR-FAQ_mainacct.png)](./media/FR-FAQ_mainacct.png)</span></span>
      
  <span data-ttu-id="0cff4-147">b.</span><span class="sxs-lookup"><span data-stu-id="0cff4-147">b.</span></span>    <span data-ttu-id="0cff4-148">Klicka på Beräkna</span><span class="sxs-lookup"><span data-stu-id="0cff4-148">Click Calculate</span></span>

2.  <span data-ttu-id="0cff4-149">Exportera rapporten till Excel</span><span class="sxs-lookup"><span data-stu-id="0cff4-149">Export the report to Excel</span></span>

<span data-ttu-id="0cff4-150">Du bör nu kunna kopiera data från Excel-rapporten i ekonomisk rapportering och till D365-råbalansrapporten och jämföra kolumnerna "Utgående balans".</span><span class="sxs-lookup"><span data-stu-id="0cff4-150">You should now be able to copy the data from the FR Excel Report and to the D365 Trial Balance report and compare the “Closing Balance” columns.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]