---
title: Felsöka befattningsbudgetering
description: Den här artikeln innehåller svar på frågor som du kan ha när du konfigurerar befattningsbudgetering. Det handlar om vanliga frågor och svar om hur du skapar budgetkostnadselement, kompensationsgrupper och kompensationsrutnät.
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmBudgetPurposeType, HcmPositionForecast
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 88253
ms.assetid: c44df01b-8700-4022-b4c6-c4b1cb84d31d
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: afddc9815ee3864236f93c8400bcf116d5b6cc89
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188520"
---
# <a name="position-budgeting-troubleshooting"></a><span data-ttu-id="00b0f-104">Felsöka befattningsbudgetering</span><span class="sxs-lookup"><span data-stu-id="00b0f-104">Position budgeting troubleshooting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="00b0f-105">Den här artikeln innehåller svar på frågor som du kan ha när du konfigurerar befattningsbudgetering.</span><span class="sxs-lookup"><span data-stu-id="00b0f-105">This article provides answers to questions that you might have when you configure position budgeting.</span></span> <span data-ttu-id="00b0f-106">Det handlar om vanliga frågor och svar om hur du skapar budgetkostnadselement, kompensationsgrupper och kompensationsrutnät.</span><span class="sxs-lookup"><span data-stu-id="00b0f-106">It addresses frequently asked questions about how to create budget cost elements, compensation groups, and compensation grids.</span></span> 

<a name="why-cant-i-find-the-forecast-position-page-in-human-resources"></a><span data-ttu-id="00b0f-107">Varför inte kan hitta jag sidan Prognosposition i Personal?</span><span class="sxs-lookup"><span data-stu-id="00b0f-107">Why can’t I find the forecast position page in Human resources?</span></span>
---------------------------------------------------------------

<span data-ttu-id="00b0f-108">Prognospositioner har flyttats till Budgetering.</span><span class="sxs-lookup"><span data-stu-id="00b0f-108">Forecast positions have been moved to Budgeting.</span></span>

## <a name="why-cant-i-delete-a-budget-cost-element"></a><span data-ttu-id="00b0f-109">Varför kan jag inte ta bort ett budgetkostnadselement?</span><span class="sxs-lookup"><span data-stu-id="00b0f-109">Why can’t I delete a budget cost element?</span></span>
<span data-ttu-id="00b0f-110">Du kan inte ta bort ett budgetkostnadselement som är tilldelat till en prognosbefattning.</span><span class="sxs-lookup"><span data-stu-id="00b0f-110">You can’t delete a budget cost element that is assigned to a forecast position.</span></span> <span data-ttu-id="00b0f-111">Innan du kan ta bort budgetkostnadselementet måste du ta bort det från alla prognospositioner.</span><span class="sxs-lookup"><span data-stu-id="00b0f-111">Before you can delete a budget cost element, you must remove it from all forecast positions.</span></span> <span data-ttu-id="00b0f-112">**Tips:** För att hitta alla positioner som ett budgetkostnadselement är tilldelat till, välj kostnadselementet på sidan **Budgetkostnadselement** och klicka sedan på **Uppdatera positioner**.</span><span class="sxs-lookup"><span data-stu-id="00b0f-112">**Tip:** To find all the positions that a budget cost element is assigned to, select the cost element on the **Budget cost elements** page, and then click **Update positions**.</span></span> <span data-ttu-id="00b0f-113">De befattningar som använder kostnadselementet anges i det övre rutnätet.</span><span class="sxs-lookup"><span data-stu-id="00b0f-113">The positions that use the cost element are listed in the upper grid.</span></span>

## <a name="how-can-i-remove-a-cost-element-from-multiple-forecast-positions-without-opening-each-one"></a><span data-ttu-id="00b0f-114">Hur kan jag ta bort ett kostnadselement från flera prognospositioner utan att öppna vart och ett?</span><span class="sxs-lookup"><span data-stu-id="00b0f-114">How can I remove a cost element from multiple forecast positions without opening each one?</span></span>
<span data-ttu-id="00b0f-115">Du kan inte ta bort ett kostnadselement.</span><span class="sxs-lookup"><span data-stu-id="00b0f-115">You can’t remove a cost element.</span></span> <span data-ttu-id="00b0f-116">Men om du ändrar start- och slutdatumen så att det hamnar utanför budgetplaneringscykeln kommer kostnadselementet inte längre att tilldelas till prognospositioner i budgetplaneringscykeln.</span><span class="sxs-lookup"><span data-stu-id="00b0f-116">However, if you change the start and end dates so that they are outside the budget planning cycle dates, the cost element will no longer be assigned to the forecast positions in that budget planning cycle.</span></span> <span data-ttu-id="00b0f-117">Du gör den här ändringen genom att öppna budgetkostnadselementet, och sedan på snabbfliken **Kostnadsberäkning** klicka på **Ändra datum** och ändra giltighetsdatumet eller utgångsdatumet.</span><span class="sxs-lookup"><span data-stu-id="00b0f-117">To make this change, open the budget cost element, and then, on the **Cost calculation** FastTab, click **Change dates**, and change the effective date or expiration date.</span></span> <span data-ttu-id="00b0f-118">Klicka sedan på **OK** om du automatiskt vill uppdatera alla prognospositioner kostnadselementet har tilldelats till.</span><span class="sxs-lookup"><span data-stu-id="00b0f-118">Then click **OK** to automatically update all forecast positions that the cost element is assigned to.</span></span> <span data-ttu-id="00b0f-119">**Tips:** Om du använder den här metoden, ska du vara medveten om att den tar bort budgetkostnadselementet från **alla** prognospositioner i vilka start- och slutdatumen inte längre är inom lämpligt intervall.</span><span class="sxs-lookup"><span data-stu-id="00b0f-119">**Tip:** If you use this method, be aware that it removes the budget cost element from **all** forecast positions where the start and end dates are no longer within the appropriate range.</span></span> <span data-ttu-id="00b0f-120">Om denna effekt inte är vad du tänker dig, måste du öppna varje prognosposition som du vill ta bort budgetkostnadselementet från och manuellt göra ändringen.</span><span class="sxs-lookup"><span data-stu-id="00b0f-120">If this effect isn't what you intend, you must open each forecast position that you want to remove the budget cost element from and manually make the change.</span></span>

## <a name="why-cant-i-enter-an-annual-amount-on-the-cost-calculation-fasttab-for-the-budget-cost-element"></a><span data-ttu-id="00b0f-121">Varför kan jag inte ange ett årligt belopp på snabbfliken Kostnadsberäkning för budgetkostnadselementet?</span><span class="sxs-lookup"><span data-stu-id="00b0f-121">Why can’t I enter an annual amount on the Cost calculation FastTab for the budget cost element?</span></span>
<span data-ttu-id="00b0f-122">Du kan inte ange ett årligt belopp om det finns kostnader för budgetkostnadselementen på snabbfliken **Beräkningsbas** eftersom systemet kräver en procentsats för att kunna beräkna värdet.</span><span class="sxs-lookup"><span data-stu-id="00b0f-122">You can’t enter an annual amount if there are budget cost elements on the **Calculation basis** FastTab, because the system requires a percentage in order to calculate the value.</span></span> <span data-ttu-id="00b0f-123">För att ändra värdet, ta bort alla budgetkostnadselement från snabbfliken **Beräkningsbas**.</span><span class="sxs-lookup"><span data-stu-id="00b0f-123">To change the value, remove all budget cost elements from the **Calculation basis** FastTab.</span></span>

## <a name="why-cant-i-change-the-budget-cost-type-from-earning-to-another-budget-cost-type"></a><span data-ttu-id="00b0f-124">Varför kan jag inte ändra budgetkostnadstypen från inkomst till en annan budgetkostnadstyp?</span><span class="sxs-lookup"><span data-stu-id="00b0f-124">Why can’t I change the budget cost type from earning to another budget cost type?</span></span>
<span data-ttu-id="00b0f-125">Vissa budgeterade kostnadselement använder intäktskostnadselementet som beräkningsbas.</span><span class="sxs-lookup"><span data-stu-id="00b0f-125">Some budget cost elements use the earning cost element as a calculation basis.</span></span> <span data-ttu-id="00b0f-126">För att ändra fältet **Budgetkostnadstyp**, ta bort intäktskostnadselementet från snabbfliken **Beräkningsbas** för alla budgetkostnadselement.</span><span class="sxs-lookup"><span data-stu-id="00b0f-126">To change the **Budget cost type** field, remove the earning cost element from the **Calculation basis** FastTab of all budget cost elements.</span></span>

## <a name="why-cant-i-change-the-date-on-budget-cost-element-lines-for-a-budget-cost-element"></a><span data-ttu-id="00b0f-127">Varför kan jag inte ändra datumet på budgetkostnadselementrader för ett budgetkostnadselement?</span><span class="sxs-lookup"><span data-stu-id="00b0f-127">Why can’t I change the date on budget cost element lines for a budget cost element?</span></span>
<span data-ttu-id="00b0f-128">Du kan inte ändra datumet på budgetkostnadselementraden när ett budgetkostnadselement används av en prognosbefattning.</span><span class="sxs-lookup"><span data-stu-id="00b0f-128">You can’t change the date on the budget cost element line when a budget cost element is used by a forecast position.</span></span> <span data-ttu-id="00b0f-129">Denna begränsning garanterar att prognospositionerna alltid är inom riktlinjerna för budgetkostnadselementet.</span><span class="sxs-lookup"><span data-stu-id="00b0f-129">This limitation helps guarantee that the forecast positions are always within the guidelines of the budget cost element.</span></span> <span data-ttu-id="00b0f-130">Om du vill ändra datumet, på **Kostnadsberäkning** snabbfliken klicka **Ändra datum** och ange de nya datumen.</span><span class="sxs-lookup"><span data-stu-id="00b0f-130">To change the date, on the **Cost calculation** FastTab, click **Change dates**, and enter the new dates.</span></span> <span data-ttu-id="00b0f-131">Klicka sedan på **OK** för att uppdatera positionerna kostnadselementet har tilldelats till.</span><span class="sxs-lookup"><span data-stu-id="00b0f-131">Then click **OK** to update the positions that the cost element is assigned to.</span></span>

## <a name="why-cant-i-change-the-costs-for-a-budget-cost-element-on-the-compensation-group-page"></a><span data-ttu-id="00b0f-132">Varför kan jag inte ändra kostnaderna för ett budgetkostnadselement på sidan Kompensationsgrupp?</span><span class="sxs-lookup"><span data-stu-id="00b0f-132">Why can’t I change the costs for a budget cost element on the Compensation group page?</span></span>
<span data-ttu-id="00b0f-133">Du kan skapa och ändra kostnader för budgetkostnadselement bara på sidan **Budgetkostnadselement**.</span><span class="sxs-lookup"><span data-stu-id="00b0f-133">You can create and change budget cost elements only on the **Budget cost elements** page.</span></span>

## <a name="why-do-i-receive-an-error-message-when-i-change-the-dates-for-a-cost-element-on-a-forecast-position"></a><span data-ttu-id="00b0f-134">Varför får jag ett felmeddelande när jag ändrar datumen för ett kostnadselement i en prognosposition?</span><span class="sxs-lookup"><span data-stu-id="00b0f-134">Why do I receive an error message when I change the dates for a cost element on a forecast position?</span></span>
<span data-ttu-id="00b0f-135">Datumen på prognospositionens kostnadselementrad måste vara inom följande intervall:</span><span class="sxs-lookup"><span data-stu-id="00b0f-135">The dates on the forecast position cost element line must be within the following ranges:</span></span>

-   <span data-ttu-id="00b0f-136">Aktiverings- och avyttringsdatum för befattningen.</span><span class="sxs-lookup"><span data-stu-id="00b0f-136">The activation and retirement dates of the position.</span></span>
-   <span data-ttu-id="00b0f-137">Aktiverings- och utgångsdatum för budgetkostnadselementet.</span><span class="sxs-lookup"><span data-stu-id="00b0f-137">The activation and expiration dates of the budget cost element.</span></span>
-   <span data-ttu-id="00b0f-138">Start- och slutdatumen för den budgetcykel som associeras med budgetplaneringsprocessen för prognosbefattningen.</span><span class="sxs-lookup"><span data-stu-id="00b0f-138">The start and end dates of the budget cycle that is associated with the budget planning process of the forecast position.</span></span>




