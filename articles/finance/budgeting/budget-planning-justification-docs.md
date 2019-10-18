---
title: Motiveringsdokument för budgetplan
description: Motiveringsdokument förklarar varför det är nödvändigt med en specifik budget.
author: ryansandness
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanJustificationTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 321da6643b421070ddd9f32bddd3e8d72f0adb86
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188566"
---
# <a name="budget-planning-justification-documents"></a><span data-ttu-id="57e2e-103">Motiveringsdokument för budgetplan</span><span class="sxs-lookup"><span data-stu-id="57e2e-103">Budget planning justification documents</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57e2e-104">Motiveringsdokument förklarar varför det är nödvändigt med en specifik budget.</span><span class="sxs-lookup"><span data-stu-id="57e2e-104">Justification documents provide a narrative for those requesting a budget to explain why a specific budget is necessary.</span></span> 

<span data-ttu-id="57e2e-105">En budgetplansmall skapas av den budgetansvarige i Microsoft Word och tilldelas till aktuell budgetplaneringsprocess.</span><span class="sxs-lookup"><span data-stu-id="57e2e-105">A budget plan template is created by the budget manager in Microsoft Word and assigned to the current budget planning process.</span></span> <span data-ttu-id="57e2e-106">Budgetägaren kan sedan öppna mallen och låta datan fyllas i automatiskt i Word baserat på sin budgetbegäran.</span><span class="sxs-lookup"><span data-stu-id="57e2e-106">Budget owners can then open the template and have data automatically populated in Word based on their budget request.</span></span> <span data-ttu-id="57e2e-107">De kan sedan lägga till ytterligare text eller data innan de sparar, samt bifoga sitt personliga motiveringsdokument till sin budgetplan.</span><span class="sxs-lookup"><span data-stu-id="57e2e-107">They can then add additional text or data prior to saving and attaching their personalized justification document to their budget plan.</span></span>

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a><span data-ttu-id="57e2e-108">Ställa in Microsoft Dynamics Office-tillägget för Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="57e2e-108">Set up Microsoft Dynamics Office Add-in for Microsoft Word</span></span>

1.  <span data-ttu-id="57e2e-109">Öppna ett nytt Microsoft Word-dokument.</span><span class="sxs-lookup"><span data-stu-id="57e2e-109">Open a new Microsoft Word document.</span></span>
2.  <span data-ttu-id="57e2e-110">Klicka på **Infoga** i menyfliksområdet och på **Butik**.</span><span class="sxs-lookup"><span data-stu-id="57e2e-110">Click **Insert** on the ribbon, and click **Store**.</span></span>
3.  <span data-ttu-id="57e2e-111">Sök efter Microsoft Dynamics Office-tillägget och klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="57e2e-111">Search for Microsoft Dynamics Office Add-in and click **Add**.</span></span>
4.  <span data-ttu-id="57e2e-112">Klicka på **Lägg till serverinformation** i fönstret till höger.</span><span class="sxs-lookup"><span data-stu-id="57e2e-112">In Word, in the right pane, click **Add server information**.</span></span>
5.  <span data-ttu-id="57e2e-113">Skriv eller klistra in serverns URL och klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="57e2e-113">Type or paste the server URL and click **OK**.</span></span>

##### <a name="define-the-justification-template-in-microsoft-word"></a><span data-ttu-id="57e2e-114">Definiera justeringsmallen i Microsoft Word</span><span class="sxs-lookup"><span data-stu-id="57e2e-114">Define the Justification template in Microsoft Word</span></span>

1.  <span data-ttu-id="57e2e-115">Klicka på **Design** i Microsoft Dynamics Office-tillägget när du loggar in.</span><span class="sxs-lookup"><span data-stu-id="57e2e-115">Click **Design** in the Microsoft Dynamics Office Add-in after you’ve logged in.</span></span>
2.  <span data-ttu-id="57e2e-116">Använd knappen **Lägg till fält** för rubrikinformation.</span><span class="sxs-lookup"><span data-stu-id="57e2e-116">For header information, use the **Add fields** button.</span></span>
3.  <span data-ttu-id="57e2e-117">Markera enhetsdatakälla för BudgetPlanJustification och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="57e2e-117">Select the entity data source of BudgetPlanJustification, and click **Next**.</span></span> <span data-ttu-id="57e2e-118">**Obs!** Denna enhet krävs för samtliga motiveringsdokument.</span><span class="sxs-lookup"><span data-stu-id="57e2e-118">**Note:** This entity is required for any justification document.</span></span> <span data-ttu-id="57e2e-119">Andra enheter kan användas, men överföringen tillbaka till Microsoft Dynamics 365 Finance misslyckas om inte denna enhet ingår.</span><span class="sxs-lookup"><span data-stu-id="57e2e-119">Other entities can be used but the upload back to Microsoft Dynamics 365 Finance will fail if this entity isn’t included.</span></span>
4.  <span data-ttu-id="57e2e-120">Lägg till etiketterna och värdena BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter och DocumentNumber i Word-dokumentet.</span><span class="sxs-lookup"><span data-stu-id="57e2e-120">Add the BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter, and DocumentNumber labels and values in the Word document.</span></span> <span data-ttu-id="57e2e-121">**Obs!** Du kan använda dina egna etiketter i stället för standardetiketter vid behov.</span><span class="sxs-lookup"><span data-stu-id="57e2e-121">**Note:** You can use your own custom labels, rather than the standard labels, if needed.</span></span>
5.  <span data-ttu-id="57e2e-122">Klicka på **Klart** för att slutföra rubrikavsnittet.</span><span class="sxs-lookup"><span data-stu-id="57e2e-122">Click **Done** to complete the header section.</span></span>
6.  <span data-ttu-id="57e2e-123">Klicka på **Lägg till tabell** för att se information på radnivå om budgetplanbelopp.</span><span class="sxs-lookup"><span data-stu-id="57e2e-123">For line level detail of budget plan amounts, click **Add table**.</span></span>
7.  <span data-ttu-id="57e2e-124">Markera återigen enhetsdatakällan för BudgetPlanJustification och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="57e2e-124">Again, select the entity data source of BudgetPlanJustification, and click **Next**.</span></span>
8.  <span data-ttu-id="57e2e-125">Lägg till fält för EffectiveDate, ScenarioName, AccountDisplayValue och AccountingCurrencyExpenseAmount.</span><span class="sxs-lookup"><span data-stu-id="57e2e-125">Add fields for EffectiveDate, ScenarioName, AccountDisplayValue, and AccountingCurrencyExpenseAmount.</span></span> <span data-ttu-id="57e2e-126">**Obs!** Om det finns kommentarer att lägga till inom enskilda budgetplansrader, kan dessa läggas till i den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="57e2e-126">**Note:** If comments are available to add within individual budget plan lines, those can be added to the table here.</span></span>
9.  <span data-ttu-id="57e2e-127">Lägg till eventuella ytterligare instruktioner till slutanvändaren, och utför all nödvändig formatering eller putsning på dokumentet.</span><span class="sxs-lookup"><span data-stu-id="57e2e-127">Add any additional instructions to provide to the end user, and perform any necessary formatting or styling to the document.</span></span>
10. <span data-ttu-id="57e2e-128">Spara dokumentet på din lokala dator och stäng filen innan du fortsätter.</span><span class="sxs-lookup"><span data-stu-id="57e2e-128">Save the document to your local computer and close the file before continuing.</span></span>

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a><span data-ttu-id="57e2e-129">Skapa den budgetplaneringsprocess som ska använda motiveringsmallen</span><span class="sxs-lookup"><span data-stu-id="57e2e-129">Set up the Budget planning process to use the Justification template</span></span>

1.  <span data-ttu-id="57e2e-130">Gå till **Budgetering** &gt; **Inställningar** &gt; **Budgetplanering** &gt; **Malla för motiveringsdokument**.</span><span class="sxs-lookup"><span data-stu-id="57e2e-130">Go to **Budgeting** &gt; **Setup** &gt; **Budget planning** &gt; **Justification document templates**.</span></span>
2.  <span data-ttu-id="57e2e-131">Klicka på **Ny** och bläddra till det nya Microsoft Word-dokumentet.</span><span class="sxs-lookup"><span data-stu-id="57e2e-131">Click **New** and browse to your newly created Microsoft Word document.</span></span>
3.  <span data-ttu-id="57e2e-132">Ange ett visningsnamn och en beskrivning för mallen.</span><span class="sxs-lookup"><span data-stu-id="57e2e-132">Enter a template display name and description.</span></span> <span data-ttu-id="57e2e-133">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="57e2e-133">Click **OK**.</span></span>
4.  <span data-ttu-id="57e2e-134">Navigera till **Budgetering** &gt; **Inställningar** &gt; **Budget** **planering** &gt; **Budgetplaneringsprocess**.</span><span class="sxs-lookup"><span data-stu-id="57e2e-134">Go to **Budgeting** &gt; **Setup** &gt; **Budget** **planning** &gt; **Budget planning process**.</span></span>
5.  <span data-ttu-id="57e2e-135">Välj den process där justeringsmallen ska användas, och klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="57e2e-135">Select the process where the justification template should be used, and click **Edit**.</span></span>
6.  <span data-ttu-id="57e2e-136">I fältet **Mall för motiveringsdokument** markerar du önskad mall och sparar.</span><span class="sxs-lookup"><span data-stu-id="57e2e-136">In the **Justification document template** field, select the appropriate template and save.</span></span>

##### <a name="edit-and-save-personalized-justification-documents"></a><span data-ttu-id="57e2e-137">Redigera och spara personliga motiveringsdokument</span><span class="sxs-lookup"><span data-stu-id="57e2e-137">Edit and save personalized justification documents</span></span>

1.  <span data-ttu-id="57e2e-138">Skapa en ny budgetplan eller öppna en befintlig budgetplan.</span><span class="sxs-lookup"><span data-stu-id="57e2e-138">Create a new budget plan or open an existing budget plan.</span></span>
2.  <span data-ttu-id="57e2e-139">I listrutan **Motivering** väljer du **Skapa ny motivering**.</span><span class="sxs-lookup"><span data-stu-id="57e2e-139">In the **Justification** drop-down menu, select **Create new justification**.</span></span>
3.  <span data-ttu-id="57e2e-140">När du har fyllt i uppgifterna väljer att överföra anpassade dokumentet via listrutan **Motivering**.</span><span class="sxs-lookup"><span data-stu-id="57e2e-140">After filling in the details, select to upload the personalized document from the **Justification** drop-down menu.</span></span>




