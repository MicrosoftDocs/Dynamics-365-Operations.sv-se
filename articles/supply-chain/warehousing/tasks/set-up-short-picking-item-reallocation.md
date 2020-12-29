---
title: Skapa omallokering av artiklar för kort plockning
description: I det här ämnet visas hur du auktoriserar lagerarbetare att snabbt söka efter alternativa platser om det inte finns tillräckligt med lagerutrymme på den plats som de har hänvisats till.
author: ShylaThompson
manager: tfehr
ms.date: 06/29/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker, WHSLocationWithWorkException
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e8f5c23f82e96145f411ec993f766a90137b5b8
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4438023"
---
# <a name="set-up-short-picking-item-reallocation"></a><span data-ttu-id="01f30-103">Skapa omallokering av artiklar för kort plockning</span><span class="sxs-lookup"><span data-stu-id="01f30-103">Set up short picking item reallocation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="01f30-104">I den här proceduren visas hur du auktoriserar lagerarbetare att snabbt söka efter alternativa platser om det inte finns tillräckligt med lagerutrymme på den plats som de har hänvisats till.</span><span class="sxs-lookup"><span data-stu-id="01f30-104">This procedure shows how to enable warehouse workers to quickly find alternative locations if there isn’t sufficient inventory at the location they’ve been directed to.</span></span> 

<span data-ttu-id="01f30-105">Omallokeringsprocessen styrs av ett **arbetsundantag** och används av lagerställets **arbetare**.</span><span class="sxs-lookup"><span data-stu-id="01f30-105">The reallocation process is controlled by a **Work exception** and used by the warehouse **worker.**</span></span>

<span data-ttu-id="01f30-106">Det går att använda automatiska, manuella eller båda omallokeringsprocesser:</span><span class="sxs-lookup"><span data-stu-id="01f30-106">It is possible to use Automatic, Manual, or both reallocation processes:</span></span>

- <span data-ttu-id="01f30-107">Automatiska omallokeringar – Platsdirektiv används för att fastställa om varorna finns tillgängliga på en annan plats.</span><span class="sxs-lookup"><span data-stu-id="01f30-107">Automatic reallocation - Location directives are used to determine if the goods are available at another location.</span></span> <span data-ttu-id="01f30-108">Om möjligt kommer arbetet att uppdateras och lageranvändaren kommer att dirigeras till den alternativa platsen.</span><span class="sxs-lookup"><span data-stu-id="01f30-108">If possible, the work will be updated and the warehouse user will be directed to the alternative location.</span></span>
- <span data-ttu-id="01f30-109">Manuell omallokering – Gör att lageranvändaren kan välja mellan en eller flera platser med icke reserverade kvantiteter av varor.</span><span class="sxs-lookup"><span data-stu-id="01f30-109">Manual reallocation - Allows the warehouse user to select from one or more locations with unreserved quantities of goods.</span></span> 
- <span data-ttu-id="01f30-110">Automatisk och manuell – Om systemet inte kan utföra automatisk omallokering och platser är tillgängliga med icke reserverade kvantiteter, uppmanas användaren att välja en plats.</span><span class="sxs-lookup"><span data-stu-id="01f30-110">Automatic and manual - If the system is unable to perform an automatic reallocation, and locations are available with unreserved quantities, the user will be prompted to select a location.</span></span>

## <a name="set-up-work-exceptions"></a><span data-ttu-id="01f30-111">Konfigurera arbetsavvikelser</span><span class="sxs-lookup"><span data-stu-id="01f30-111">Set up work exceptions</span></span>
<span data-ttu-id="01f30-112">Det går att definiera flera arbetsundantag med olika artikelomallokeringspolicyer om du vill göra det möjligt för lagerarbetare att välja en baserat på behoven hos den försändelse som de bearbetar.</span><span class="sxs-lookup"><span data-stu-id="01f30-112">It's possible to define several work exceptions with different item reallocation policies to enable the warehouse worker to choose one based on the needs of the shipment that they are processing.</span></span>

<span data-ttu-id="01f30-113">Demonstrationsdataföretaget USMF har använts för att skapa denna procedur.</span><span class="sxs-lookup"><span data-stu-id="01f30-113">The USMF demo data company was used to create this procedure.</span></span>

1. <span data-ttu-id="01f30-114">I **navigeringsfönstret**, gå till **Lagerstyrning > Inställningar > Arbete > Arbetsundantag**.</span><span class="sxs-lookup"><span data-stu-id="01f30-114">In the **Navigation pane**, go to **Warehouse management > Setup > Work > Work exceptions**.</span></span>
2. <span data-ttu-id="01f30-115">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="01f30-115">Click **New**</span></span> 
3. <span data-ttu-id="01f30-116">Ange ett värde i fältet **Kod för arbetsundantag.**</span><span class="sxs-lookup"><span data-stu-id="01f30-116">In the **Work exception code** field, type a value.</span></span> <span data-ttu-id="01f30-117">Detta är rubriken på detta undantag.</span><span class="sxs-lookup"><span data-stu-id="01f30-117">This will be the title of this exception .</span></span> <span data-ttu-id="01f30-118">Till exempel "Kortplockning manuellt".</span><span class="sxs-lookup"><span data-stu-id="01f30-118">For example, Short picking manual.</span></span>
4. <span data-ttu-id="01f30-119">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="01f30-119">In the **Description** field, type a value.</span></span> <span data-ttu-id="01f30-120">En kort beskrivning av hur detta undantags används.</span><span class="sxs-lookup"><span data-stu-id="01f30-120">This will be a short description of the usage of this exception.</span></span> <span data-ttu-id="01f30-121">T.ex. är den här artikeln för kortplockning inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="01f30-121">For example, Short picking - item not available.</span></span>
5. <span data-ttu-id="01f30-122">I typfältet **Undantag** välj **Kort plockning**.</span><span class="sxs-lookup"><span data-stu-id="01f30-122">In the **Exception** type field, select **Short pick**.</span></span>
6. <span data-ttu-id="01f30-123">Välj kryssrutan **Justera lager**.</span><span class="sxs-lookup"><span data-stu-id="01f30-123">Select the **Adjust inventory** check box.</span></span> <span data-ttu-id="01f30-124">Om detta väljs kommer lagret justeras automatiskt till 0 på en kort plockad plats.</span><span class="sxs-lookup"><span data-stu-id="01f30-124">If selected, inventory will automatically be adjusted to 0 at the short picked location.</span></span>
7. <span data-ttu-id="01f30-125">Ange eller välj ett värde i fältet **Kod för standardjusteringstyp**.</span><span class="sxs-lookup"><span data-stu-id="01f30-125">In the **Default adjustment type code** field, enter or select a value.</span></span> <span data-ttu-id="01f30-126">I USMF kan du till exempel välja **Ta bort Res Adj Out**. Varje justerings typ kod innehåller fyra kännetecken: namn, beskrivning, lagerjournalnamn och **Ta bort reservationer**.</span><span class="sxs-lookup"><span data-stu-id="01f30-126">For example, in USMF you can select **Remove Res Adj Out**. Each Adjustment type code contains four characteristics: name, description, inventory journal name, and **Remove reservations**.</span></span> <span data-ttu-id="01f30-127">Om **ta bort reservationer** är aktiverad tas reservationer för den kortplockade orderraden bort.</span><span class="sxs-lookup"><span data-stu-id="01f30-127">If **Remove reservations** is enabled, the short-picked order line's reservations will be removed.</span></span>  
8. <span data-ttu-id="01f30-128">I fältet **Omallokering av artikel** väljer du ett värde, t.ex. Manuell.</span><span class="sxs-lookup"><span data-stu-id="01f30-128">In the **Item reallocation** field, select a value, such as Manual.</span></span> <span data-ttu-id="01f30-129">Om du väljer manuellt, eller automatiskt och manuellt, måste lagerställearbetaren auktoriseras för att använda manuell omallokering.</span><span class="sxs-lookup"><span data-stu-id="01f30-129">If you select Manual, or Automatic and Manual, the warehouse worker needs to be enabled to use manual reallocation.</span></span>

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a><span data-ttu-id="01f30-130">Ställ in en arbetare som ska använda manuell artikelomallokering</span><span class="sxs-lookup"><span data-stu-id="01f30-130">Set up a worker to use manual item reallocation</span></span>

<span data-ttu-id="01f30-131">Demonstrationsdataföretaget USMF har använts för att skapa denna procedur.</span><span class="sxs-lookup"><span data-stu-id="01f30-131">The USMF demo data company was used to create this procedure.</span></span>

1. <span data-ttu-id="01f30-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="01f30-132">Close the page.</span></span>
2. <span data-ttu-id="01f30-133">I **navigeringsfönstret**, gå till **Lagerstyrning > Inställningar > Arbetare**.</span><span class="sxs-lookup"><span data-stu-id="01f30-133">In the **Navigation pane**, go to **Warehouse management > Setup > Worker**.</span></span>
3. <span data-ttu-id="01f30-134">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="01f30-134">Click **Edit**.</span></span>
4. <span data-ttu-id="01f30-135">I listan väljer du arbetare.</span><span class="sxs-lookup"><span data-stu-id="01f30-135">In the list, select worker.</span></span> <span data-ttu-id="01f30-136">Till exempel Julia Funderburk.</span><span class="sxs-lookup"><span data-stu-id="01f30-136">For example, Julia Funderburk.</span></span>
5. <span data-ttu-id="01f30-137">Expandera snabbfliken **Användare**.</span><span class="sxs-lookup"><span data-stu-id="01f30-137">Expand the **Users** FastTab.</span></span>
6. <span data-ttu-id="01f30-138">I listan väljer du **Användar-ID**.</span><span class="sxs-lookup"><span data-stu-id="01f30-138">In the list, select a **User ID**.</span></span> <span data-ttu-id="01f30-139">Exempelvis 24.</span><span class="sxs-lookup"><span data-stu-id="01f30-139">For example, 24.</span></span>
7. <span data-ttu-id="01f30-140">Expandera snabbfliken **Arbete**.</span><span class="sxs-lookup"><span data-stu-id="01f30-140">Expand the **Work** FastTab.</span></span>
8. <span data-ttu-id="01f30-141">Välj **Ja** i fältet **Tillåt manuell omallokering av artikel**.</span><span class="sxs-lookup"><span data-stu-id="01f30-141">Select **Yes** in the **Allow manual item reallocation** field.</span></span>
