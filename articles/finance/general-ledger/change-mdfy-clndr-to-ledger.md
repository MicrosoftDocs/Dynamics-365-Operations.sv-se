---
title: Ändra eller tilldela om en redovisningskalender
description: Det här avsnittet förklarar hur du ändrar kalendern som för närvarande är tilldelad en redovisning och hur du tilldelar en ny kalender till redovisningen.
author: kweekley
ms.date: 05/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-07
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 052b8944c0a015187d1d7c4ba3db878c52faeeea
ms.sourcegitcommit: 905a8c7a0c1bc06ada2acfba913dfe5f7b44ea16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/14/2021
ms.locfileid: "6039960"
---
# <a name="change-or-reassign-a-ledger-calendar"></a><span data-ttu-id="0353a-103">Ändra eller tilldela om en redovisningskalender</span><span class="sxs-lookup"><span data-stu-id="0353a-103">Change or reassign a ledger calendar</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0353a-104">Det här avsnittet förklarar hur du ändrar kalendern som för närvarande är tilldelad en redovisning och hur du tilldelar en ny kalender till redovisningen.</span><span class="sxs-lookup"><span data-stu-id="0353a-104">This topic explains how to change the calendar that is currently assigned to a ledger, and how to assign a new calendar to the ledger.</span></span>

## <a name="issue"></a><span data-ttu-id="0353a-105">Problem</span><span class="sxs-lookup"><span data-stu-id="0353a-105">Issue</span></span>

<span data-ttu-id="0353a-106">Ibland måste företag antingen ändra den befintliga kalendern som har tilldelats en redovisning eller tilldela en ny kalender.</span><span class="sxs-lookup"><span data-stu-id="0353a-106">Sometime, companies must either change the existing calendar that is assigned to a ledger or assign a new calendar.</span></span>

## <a name="resolution"></a><span data-ttu-id="0353a-107">Lösning</span><span class="sxs-lookup"><span data-stu-id="0353a-107">Resolution</span></span>

<span data-ttu-id="0353a-108">Det finns två scenarier för att ändra eller tilldela om en redovisningskalender.</span><span class="sxs-lookup"><span data-stu-id="0353a-108">There are two scenarios for changing or reassigning a ledger calendar.</span></span> <span data-ttu-id="0353a-109">Det första scenariot ändrar en befintlig kalender som redan är tilldelad redovisningen.</span><span class="sxs-lookup"><span data-stu-id="0353a-109">The first scenario involves changing an existing calendar that is already assigned to the ledger.</span></span> <span data-ttu-id="0353a-110">Det andra scenariot skapar en ny kalender och tilldelar den till redovisningen.</span><span class="sxs-lookup"><span data-stu-id="0353a-110">The second scenario involves creating a new calendar and assigning it to the ledger.</span></span> <span data-ttu-id="0353a-111">Båda ändringarna kan utföras när som helst, även efter att transaktioner har bokförts i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="0353a-111">Both changes can be done at any time, even after transactions have been posted to the ledger.</span></span>

### <a name="change-an-existing-fiscal-calendar"></a><span data-ttu-id="0353a-112">Ändra en befintlig räkenskapskalender</span><span class="sxs-lookup"><span data-stu-id="0353a-112">Change an existing fiscal calendar</span></span>

<span data-ttu-id="0353a-113">Ändra en befintlig kalender som är tilldelad redovisningen genom att gå till **Redovisning \> Redovisningsinställningar \> Redovisning** och välj länken till räkenskapskalendern för att öppna sidan **Redovisningskalendrar**.</span><span class="sxs-lookup"><span data-stu-id="0353a-113">To change an existing calendar that is assigned to your ledger, go to **General ledger \> Ledger setup \> Ledger**, and select the link for the fiscal calendar to open the **Ledger calendars** page.</span></span>

<span data-ttu-id="0353a-114">Det finns gränser för ändringarna som går att utföra i en kalender.</span><span class="sxs-lookup"><span data-stu-id="0353a-114">There are limits to the changes that can be made to a calendar.</span></span> <span data-ttu-id="0353a-115">Det går till exempel att ändra start- och slutdatum för *perioder* under ett år, men det går inte att ändra start- och slutdatum för ett *år* i kalendern.</span><span class="sxs-lookup"><span data-stu-id="0353a-115">For example, you can change the start and end dates of the *periods* in a year, but you can't change the start and end dates of a *year* in the calendar.</span></span>

<span data-ttu-id="0353a-116">Välj en lämplig kalender och ett lämpligt år om du vill ändra perioder under ett år.</span><span class="sxs-lookup"><span data-stu-id="0353a-116">To change the periods in a year, select the appropriate calendar and year.</span></span> <span data-ttu-id="0353a-117">Använd först knappen **Ta bort period** för att ta bort vissa eller alla befintliga driftsperioder.</span><span class="sxs-lookup"><span data-stu-id="0353a-117">First, use the use the **Delete period** button to delete some or all of the existing operating periods.</span></span> <span data-ttu-id="0353a-118">Det går att ta bort alla driftsperioder utom den första.</span><span class="sxs-lookup"><span data-stu-id="0353a-118">All operating periods except the first can be deleted.</span></span> <span data-ttu-id="0353a-119">Använd sedan knappen **Dela period** för att dela upp återstående period eller perioder i nya perioder genom att ange ett lämpligt startdatum för nästa period.</span><span class="sxs-lookup"><span data-stu-id="0353a-119">Then use the **Divide period** button to divide the remaining period or periods into new periods by entering an appropriate start date for the next period.</span></span>

<span data-ttu-id="0353a-120">När du ändrar perioderna i en kalender måste du köra processen **Beräkna om redovisningsperioder** i varje juridisk person (företag) som kalendern är tilldelad till.</span><span class="sxs-lookup"><span data-stu-id="0353a-120">After you change the periods in a calendar, you must run the **Recalculate ledger periods** process in every legal entity (company) that the calendar is assigned to.</span></span> <span data-ttu-id="0353a-121">Även om inget varningsmeddelande påminner dig om att slutföra det här steget krävs omberäkningsprocessen för att uppdatera perioden som tilldelas varje bokförd transaktion i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="0353a-121">Although no warning message reminds you to complete this step, the recalculation process is required to update the period that is assigned to each posted transaction in General ledger.</span></span> <span data-ttu-id="0353a-122">Kör omberäkningen genom att välja **Beräkna om redovisningsperioder** på sidan **Redovisningsinställningar** i varje företag.</span><span class="sxs-lookup"><span data-stu-id="0353a-122">To run the recalculation process, select **Recalculate ledger periods** on the **Ledger setup** page in each company.</span></span>

<span data-ttu-id="0353a-123">Om omberäkningen inte körs är det möjligt att transaktionssaldon i en råbalans eller i bokslut felaktigt inkluderas i perioder.</span><span class="sxs-lookup"><span data-stu-id="0353a-123">If the recalculation process isn't run, transaction balances on a trial balance or on financial statements might be incorrectly included in periods.</span></span> <span data-ttu-id="0353a-124">I det här fallet kan du korrigera saldon när som helst genom att köra omberäkningen.</span><span class="sxs-lookup"><span data-stu-id="0353a-124">In this case, you can correct the balances at any time by running the recalculation process.</span></span>

### <a name="assign-a-new-fiscal-calendar"></a><span data-ttu-id="0353a-125">Tilldela en ny räkenskapskalender</span><span class="sxs-lookup"><span data-stu-id="0353a-125">Assign a new fiscal calendar</span></span>

<span data-ttu-id="0353a-126">Tilldela en ny räkenskapskalender genom att öppna **Redovisning \> Redovisningsinställningar \> Redovisning** och välja **Redigera** för att ställa sidan **Redovisning** i redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="0353a-126">To assign a new fiscal calendar, go to **General ledger \> Ledger setup \> Ledger**, and select **Edit** to put the **Ledger** page into edit mode.</span></span> <span data-ttu-id="0353a-127">Välj sedan en ny räkenskapskalender i fältet **Räkenskapskalender**.</span><span class="sxs-lookup"><span data-stu-id="0353a-127">Then, in the **Fiscal calendar** field, select a new fiscal calendar.</span></span>

<span data-ttu-id="0353a-128">När du har ändrat räkenskapskalendern för en redovisning måste du köra **Beräkna om redovisningsperioder**.</span><span class="sxs-lookup"><span data-stu-id="0353a-128">After you change the fiscal calendar for a ledger, you must run the **Recalculate ledger periods**.</span></span> <span data-ttu-id="0353a-129">När du tilldelar en ny räkenskapskalender till en redovisning påminner ett meddelande dig om att slutföra det här steget.</span><span class="sxs-lookup"><span data-stu-id="0353a-129">When you assign a new fiscal calendar to a ledger, a message reminds you to complete this step.</span></span> <span data-ttu-id="0353a-130">Meddelande kan får omberäkningsprocessen att framstå som valfri, trots att den inte är det.</span><span class="sxs-lookup"><span data-stu-id="0353a-130">Although the message might seem to indicate that the recalculation process is optional, it isn't.</span></span> <span data-ttu-id="0353a-131">Den krävs för att uppdatera perioden som tilldelas varje bokförd transaktion i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="0353a-131">It's required to update the period that is assigned to each posted transaction in General ledger.</span></span> <span data-ttu-id="0353a-132">Kör omberäkningen genom att välja **Beräkna om redovisningsperioder** på sidan **Redovisningsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="0353a-132">To run the recalculation process, select **Recalculate ledger periods** on the **Ledger setup** page.</span></span>

<span data-ttu-id="0353a-133">Om omberäkningen inte körs är det möjligt att transaktionssaldon i en råbalans eller i bokslut felaktigt inkluderas i perioder.</span><span class="sxs-lookup"><span data-stu-id="0353a-133">If the recalculation process isn't run, transaction balances on a trial balance or on financial statements might be incorrectly included in periods.</span></span> <span data-ttu-id="0353a-134">I det här fallet kan du korrigera saldon när som helst genom att köra omberäkningen.</span><span class="sxs-lookup"><span data-stu-id="0353a-134">In this case, you can correct the balances at any time by running the recalculation process.</span></span>
