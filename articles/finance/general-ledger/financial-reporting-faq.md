---
title: Frågor och svar om ekonomisk rapportering
description: Det här avsnittet innehåller svar på några vanliga frågor om ekonomisk rapportering.
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
ms.openlocfilehash: e1b67f86446403933005008a9a1e2cc6739dc516
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266643"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="7c2b1-103">Frågor och svar om ekonomisk rapportering</span><span class="sxs-lookup"><span data-stu-id="7c2b1-103">Financial reporting FAQ</span></span>

<span data-ttu-id="7c2b1-104">Det här avsnittet innehåller svar på vanliga frågor om ekonomisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-104">This topic provides answers to frequently asked questions about Financial reporting.</span></span>

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a><span data-ttu-id="7c2b1-105">Hur begränsar jag åtkomsten till en rapport med hjälp av trädsäkerhet?</span><span class="sxs-lookup"><span data-stu-id="7c2b1-105">How do I restrict access to a report by using tree security?</span></span>

<span data-ttu-id="7c2b1-106">Följande exempel visar hur du begränsar åtkomsten till en rapport med hjälp av trädsäkerhet.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-106">The following example shows how to restrict access to a report by using tree security.</span></span>

<span data-ttu-id="7c2b1-107">Demonstrationsföretaget USMF har en **balansräkningsrapport** som inte alla användare av ekonomisk rapportering ska ha åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-107">The USMF demo company has a **Balance sheet** report that not all Financial reporting users should have access to.</span></span> <span data-ttu-id="7c2b1-108">Du kan använda trädsäkerhet för att begränsa åtkomsten till en enskild rapport så att bara specifika användare kan komma åt den.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-108">You can use tree security to restrict access to a single report so that only specific users can access it.</span></span>

1. <span data-ttu-id="7c2b1-109">Logga in i Financial Reporter Report Designer.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-109">Sign in to Financial Reporter Report Designer.</span></span>
2. <span data-ttu-id="7c2b1-110">Välj **Arkiv \> Ny \> Träddefinition** för att skapa en ny träddefinition.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-110">Select **File \> New \> Tree Definition** to create a new tree definition.</span></span>
3. <span data-ttu-id="7c2b1-111">Dubbelklicka på **Sammanfattning** i kolumnen **Enhetssäkerhet**.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-111">Double-tap (or double-click) the **Summary** line in the **Unit Security** column.</span></span>
4. <span data-ttu-id="7c2b1-112">Välj **Användare och grupper**.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-112">Select **Users and Groups**.</span></span>
5. <span data-ttu-id="7c2b1-113">Välj de användare eller grupper som behöver ha åtkomst till rapporten.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-113">Select the users or groups that require access to the report.</span></span>
6. <span data-ttu-id="7c2b1-114">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-114">Select **Save**.</span></span>
7. <span data-ttu-id="7c2b1-115">Lägg till den nya träddefinitionen i rapportdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-115">In the report definition, add your new tree definition.</span></span>
8. <span data-ttu-id="7c2b1-116">Välj Inställning i **träddefinitionen**.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-116">In the tree definition, select **Setting**.</span></span> <span data-ttu-id="7c2b1-117">Välj sedan **Ta med alla enheter** under **Val av rapportenhet**.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-117">Then, under **Reporting unit selection**, select **Include all units**.</span></span>

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a><span data-ttu-id="7c2b1-118">Hur identifierar jag vilka konton som inte matchar mina saldon?</span><span class="sxs-lookup"><span data-stu-id="7c2b1-118">How do I identify which accounts don't match my balances?</span></span>

<span data-ttu-id="7c2b1-119">Om du har en rapport som inte har matchande saldon kan du använda dig av följande procedurer för att identifiera dessa konton och avvikelser.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-119">If you have a report that doesn't have matching balances, use the following procedures to identify each account and variance.</span></span>

### <a name="in-financial-reporter-report-designer"></a><span data-ttu-id="7c2b1-120">I Financial Reporter Report Designer</span><span class="sxs-lookup"><span data-stu-id="7c2b1-120">In Financial Reporter Report Designer</span></span>

1. <span data-ttu-id="7c2b1-121">Skapa en ny raddefinition.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-121">Create a new row definition.</span></span>
2. <span data-ttu-id="7c2b1-122">Välj **Redigera \> Infoga rader från dimensioner**.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-122">Select **Edit \> Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="7c2b1-123">Välj **MainAccount**.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-123">Select **MainAccount**.</span></span>
4. <span data-ttu-id="7c2b1-124">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-124">Select **OK**.</span></span>
5. <span data-ttu-id="7c2b1-125">Spara raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-125">Save the row definition.</span></span>
6. <span data-ttu-id="7c2b1-126">Skapa en ny kolumndefinition.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-126">Create a new column definition.</span></span>
7. <span data-ttu-id="7c2b1-127">Skapa en ny rapportdefinition.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-127">Create a new report definition.</span></span>
8. <span data-ttu-id="7c2b1-128">Välj **Inställningar** och avmarkera det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-128">Select **Settings** and unmark this option.</span></span>
9. <span data-ttu-id="7c2b1-129">Skapa rapporten.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-129">Generate the report.</span></span> 
10. <span data-ttu-id="7c2b1-130">Exportera rapporten till Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-130">Export the report to Microsoft Excel.</span></span>

### <a name="in-dynamics-365-finance"></a><span data-ttu-id="7c2b1-131">I Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="7c2b1-131">In Dynamics 365 Finance</span></span>

1. <span data-ttu-id="7c2b1-132">Gå till **Redovisning \> > Förfrågningar och rapporter \> Råbalans**.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-132">Go to **General ledger \> Inquiries and reports \> Trial balance**.</span></span>
2. <span data-ttu-id="7c2b1-133">Ange följande fält.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-133">Set the following fields:</span></span>

    - <span data-ttu-id="7c2b1-134">**Från datum** – Ange räkenskapsårets startdatum och räkenskapsår.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-134">**From Date** – Enter the start date of the fiscal year.</span></span>
    - <span data-ttu-id="7c2b1-135">**Till datum** – Ange det datum som du genererar rapporten för.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-135">**To Date** – Enter the date that you're generating the report for.</span></span>
    - <span data-ttu-id="7c2b1-136">**Ekonomisk dimension** – Ange detta fält till **huvudkontouppsättning**.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-136">**Financial Dimension** – Set this field to **Main Account set**.</span></span>

3. <span data-ttu-id="7c2b1-137">Välj **Beräkna**.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-137">Select **Calculate**.</span></span>
4. <span data-ttu-id="7c2b1-138">Exportera rapporten till Excel.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-138">Export the report to Excel.</span></span>

<span data-ttu-id="7c2b1-139">Du bör nu kunna kopiera data från Excel-rapporten Financial Reporter till rapporten **Råbalans** så att du kan jämföra kolumnerna **Utgående balans**.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-139">You should now be able to copy the data from the Financial Reporter Excel report to the **Trial Balance** report, so that you can compare the **Closing Balance** columns.</span></span>

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a><span data-ttu-id="7c2b1-140">När jag designar en rapport i Report Designer eller genererar en ekonomisk rapport får jag ett meddelande om att åtgärden inte kunde slutföras på grund av ett problem i dataleverantörens ramverk.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-140">When I design a report in Report Designer, or when I generate a financial report, I received the following message: "The operation could not be completed due to a problem in the data provider framework."</span></span> <span data-ttu-id="7c2b1-141">Vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="7c2b1-141">How should I respond?</span></span>

<span data-ttu-id="7c2b1-142">Meddelandet anger att ett problem inträffade när systemet skulle hämta ekonomiska metadata från den ekonomiska rapporteringen medan du använde Financial Reporting.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-142">The message indicates that an issue occurred when the system tried to retrieve financial metadata from the data mart while you were using Financial reporting.</span></span> <span data-ttu-id="7c2b1-143">Det finns två sätt att hantera det här problemet:</span><span class="sxs-lookup"><span data-stu-id="7c2b1-143">There are two ways to respond to this issue:</span></span>

- <span data-ttu-id="7c2b1-144">Granska integrationsstatusen för data genom att gå till **Verktyg \> Integrationsstatus** i Report Designer.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-144">Review the integration status of the data by going to **Tools \> Integration status** in Report Designer.</span></span> <span data-ttu-id="7c2b1-145">Om integrationen inte är klar väntar du tills den är klar.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-145">If the integration is incomplete, wait for it to be completed.</span></span> <span data-ttu-id="7c2b1-146">Försök sedan igen med det du gjorde när du fick meddelandet.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-146">Then retry what you were doing when you received the message.</span></span>
- <span data-ttu-id="7c2b1-147">Kontakta supporten om du vill identifiera och arbeta dig igenom problemet.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-147">Contact Support to identify and work through the issue.</span></span> <span data-ttu-id="7c2b1-148">Det kan finnas inkonsekventa data i systemet.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-148">There might be inconsistent data in the system.</span></span> <span data-ttu-id="7c2b1-149">Supporttekniker kan hjälpa dig att identifiera problemet på servern och hitta de specifika data som kan kräva en uppdatering.</span><span class="sxs-lookup"><span data-stu-id="7c2b1-149">Support engineers can help you identify that issue on the server and find the specific data that might require an update.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
