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
ms.openlocfilehash: 023354b0e2973f63411bf81cbeb0344333c49112
ms.sourcegitcommit: d63e7e0593084a61362a6cad3937b1fd956c384f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5923035"
---
# <a name="financial-reporting-faq"></a><span data-ttu-id="cb9ba-103">Frågor och svar om ekonomisk rapportering</span><span class="sxs-lookup"><span data-stu-id="cb9ba-103">Financial reporting FAQ</span></span> 

<span data-ttu-id="cb9ba-104">Det här avsnittet innehåller svar på vanliga frågor om ekonomisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-104">This topic provides answers to frequently asked questions about financial reporting.</span></span> 

## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a><span data-ttu-id="cb9ba-105">Hur begränsar jag åtkomsten till en rapport med hjälp av trädsäkerhet?</span><span class="sxs-lookup"><span data-stu-id="cb9ba-105">How do I restrict access to a report using tree security?</span></span>

<span data-ttu-id="cb9ba-106">Följande exempel visar hur du begränsar åtkomsten till en rapport med hjälp av trädsäkerhet.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-106">The following example shows how to restrict access to a report using tree security.</span></span>

<span data-ttu-id="cb9ba-107">Demonstrationsföretaget USMF har en balansräkningsrapport som inte alla användare av ekonomisk rapportering ska ha åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-107">The USMF demo company has a Balance sheet report that not all Financial reporting users should have access to.</span></span> <span data-ttu-id="cb9ba-108">Du kan använda trädsäkerhet för att begränsa åtkomsten till en enskild rapport så att bara vissa användare kan komma åt rapporten.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-108">To restrict access, you can use tree security to restrict access to a single report so that only certain users can access the report.</span></span> <span data-ttu-id="cb9ba-109">Gör på följande sätt om du vill begränsa åtkomsten:</span><span class="sxs-lookup"><span data-stu-id="cb9ba-109">Follow these steps to restrict access:</span></span> 

1. <span data-ttu-id="cb9ba-110">Logga in i Financial Reporter Report Designer.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-110">Sign in to Financial Reporter Report Designer.</span></span>
2. <span data-ttu-id="cb9ba-111">Skapa en ny träddefinition.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-111">Create a new tree definition.</span></span> <span data-ttu-id="cb9ba-112">Gå till **Arkiv > Ny > Träddefinition**.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-112">Go to **File > New > Tree Definition**.</span></span>
3. <span data-ttu-id="cb9ba-113">Dubbelklicka på **Sammanfattning** i kolumnen **Enhetssäkerhet**.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-113">Double-click the **Summary** line in the **Unit Security** column.</span></span>
4. <span data-ttu-id="cb9ba-114">Välj **Användare och grupper**.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-114">Select **Users and Groups**.</span></span>  
5. <span data-ttu-id="cb9ba-115">Välj de användare eller grupper som behöver ha åtkomst till rapporten.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-115">Select the users or groups that need access to this report.</span></span> 
6. <span data-ttu-id="cb9ba-116">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-116">Select **Save**.</span></span>
7. <span data-ttu-id="cb9ba-117">Lägg till den nya träddefinitionen i rapportdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-117">In the report definition, add your new tree definition.</span></span>
8. <span data-ttu-id="cb9ba-118">Välj Inställning i **träddefinitionen**.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-118">In the tree definition, select **Setting**.</span></span> <span data-ttu-id="cb9ba-119">Välj **Ta med alla enheter** under **Val av rapportenhet**.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-119">Under **Reporting unit selection**, select **Include all units**.</span></span>

## <a name="how-do-i-identify-which-accounts-do-not-match-my-balances"></a><span data-ttu-id="cb9ba-120">Hur identifierar jag vilka konton som inte matchar mina saldon?</span><span class="sxs-lookup"><span data-stu-id="cb9ba-120">How do I identify which accounts do not match my balances?</span></span>

<span data-ttu-id="cb9ba-121">Om du har en rapport som inte har matchande saldon kan du vidta följande åtgärder för att identifiera dessa konton och avvikelser.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-121">If you have a report that doesn't have matching balances, here are some steps you can take to identify each of the accounts and variances.</span></span> 

<span data-ttu-id="cb9ba-122">**Financial Reporter Report Designer**</span><span class="sxs-lookup"><span data-stu-id="cb9ba-122">**Financial Reporter Report Designer**</span></span>
1. <span data-ttu-id="cb9ba-123">Skapa en ny raddefinition i Financial Reporter Report Designer</span><span class="sxs-lookup"><span data-stu-id="cb9ba-123">In Financial Reporter Report Designer, create a new row definition.</span></span> 
2. <span data-ttu-id="cb9ba-124">Välj **Redigera > Infoga rader från dimensioner**.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-124">Select **Edit > Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="cb9ba-125">Välj **Huvudkonto**.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-125">Select **MainAccount**.</span></span>  
4. <span data-ttu-id="cb9ba-126">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-126">Select **OK**.</span></span>
5. <span data-ttu-id="cb9ba-127">Spara raddefinitionen.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-127">Save the row definition.</span></span>
6. <span data-ttu-id="cb9ba-128">Skapa en ny kolumndefinition</span><span class="sxs-lookup"><span data-stu-id="cb9ba-128">Create a new column definition</span></span>
7. <span data-ttu-id="cb9ba-129">Skapa en ny rapportdefinition.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-129">Create a new report definition.</span></span>
8. <span data-ttu-id="cb9ba-130">Välj **Inställningar** och avmarkera det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-130">Select **Settings** and unmark this option.</span></span>  
9. <span data-ttu-id="cb9ba-131">Skapa rapporten.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-131">Generate the report.</span></span> 
10. <span data-ttu-id="cb9ba-132">Exportera rapporten till Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-132">Export the report to Microsoft Excel.</span></span>

<span data-ttu-id="cb9ba-133">**Dynamics 365 Finance**</span><span class="sxs-lookup"><span data-stu-id="cb9ba-133">**Dynamics 365 Finance**</span></span> 
1. <span data-ttu-id="cb9ba-134">I Dynamics 365 Finance, gå till **Redovisning > Förfrågningar och rapporter > Råbalans**.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-134">In Dynamics 365 Finance, go to **General Ledger > Inquiries and Reports > Trial Balance**.</span></span>
2. <span data-ttu-id="cb9ba-135">Ställ in följande parametrar:</span><span class="sxs-lookup"><span data-stu-id="cb9ba-135">Set the following parameters:</span></span>
   - <span data-ttu-id="cb9ba-136">**Från datum** – Ange räkenskapsårets början.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-136">**From Date** - Enter the start of the fiscal year.</span></span>
   - <span data-ttu-id="cb9ba-137">**Till datum** – Ange det datum som du genererar rapporten för.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-137">**To Date** - Enter the date you are generating the report for.</span></span>
   - <span data-ttu-id="cb9ba-138">**Ekonomisk dimension** – Ange detta fält till **huvudkontouppsättning**.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-138">**Financial Dimension** - Set this field to **Main Account set**.</span></span>
 3. <span data-ttu-id="cb9ba-139">Välj **Beräkna**.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-139">Select **Calculate**.</span></span>
 4. <span data-ttu-id="cb9ba-140">Exportera rapporten till Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-140">Export the report to Microsoft Excel.</span></span>

<span data-ttu-id="cb9ba-141">Du bör nu kunna kopiera data från Excel-rapporten i ekonomisk rapportering till råbalansrapporten så att du kan jämföra kolumnerna **Utgående balans**.</span><span class="sxs-lookup"><span data-stu-id="cb9ba-141">You should now be able to copy the data from the Financial Reporter Excel report to the Trial Balance report, so you can compare the **Closing Balance** columns.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]