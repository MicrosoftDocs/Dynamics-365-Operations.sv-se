---
title: Viktfälten på beläggningsrader matchar inte viktfälten i beläggningen
description: Viktfälten på beläggningsrader matchar inte viktfälten i beläggningen
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSShipmentDetails_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 639b82a9d46b74f179d6904d2c3b8e7dfb813b58
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924361"
---
# <a name="the-weight-fields-on-load-lines-dont-match-the-weight-fields-on-the-load"></a><span data-ttu-id="2f8cc-103">Viktfälten på beläggningsrader matchar inte viktfälten i beläggningen</span><span class="sxs-lookup"><span data-stu-id="2f8cc-103">The weight fields on load lines don't match the weight fields on the load</span></span>

<span data-ttu-id="2f8cc-104">Felkoder: WHSLoadWeightOnLinesDoNotMatchLoadWarning</span><span class="sxs-lookup"><span data-stu-id="2f8cc-104">Error codes: WHSLoadWeightOnLinesDoNotMatchLoadWarning</span></span>

## <a name="symptoms"></a><span data-ttu-id="2f8cc-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="2f8cc-105">Symptoms</span></span>

<span data-ttu-id="2f8cc-106">Systemet visar följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="2f8cc-106">The system shows the following error message:</span></span>

> <span data-ttu-id="2f8cc-107">Viktfälten på beläggningsrader matchar inte viktfälten i beläggningen %1.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-107">The weight fields on load lines do not match the weight fields on load %1.</span></span> <span data-ttu-id="2f8cc-108">Kör överensstämmelsekontrollen för lagerställets belastningsvikt om du vill räkna om viktfälten.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-108">Run the Warehouse load weight consistency check to recalculate the weight fields.</span></span>

## <a name="cause"></a><span data-ttu-id="2f8cc-109">Orsak</span><span class="sxs-lookup"><span data-stu-id="2f8cc-109">Cause</span></span>

<span data-ttu-id="2f8cc-110">Fälten **Nettovikt** och **Tara-vikt** ställs in på *0* (noll) på beläggningsraden.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-110">The **Net weight** and **Tara weight** fields are set to *0* (zero) on the load line.</span></span> <span data-ttu-id="2f8cc-111">Viktfälten ställs dock inte in på *0* för produktens viktmått.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-111">However, the weight fields aren't set to *0* for the weight measurements on the product.</span></span> <span data-ttu-id="2f8cc-112">När viktfält inte ställs in på beläggningsraden kan eventuella korrigeringar av kvantiteten på beläggningsraden leda till fel viktberäkning av beläggningen.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-112">When weight fields aren't set on the load line, any corrections of the quantity on the load line might cause incorrect weight calculation on the load.</span></span> <span data-ttu-id="2f8cc-113">Det här problemet kan inträffa om vikterna på produkten har ändrats sedan beläggningsraden skapades.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-113">This issue might occur if the weights on the product have been changed since the load line was created.</span></span>

## <a name="resolution"></a><span data-ttu-id="2f8cc-114">Upplösning</span><span class="sxs-lookup"><span data-stu-id="2f8cc-114">Resolution</span></span>

<span data-ttu-id="2f8cc-115">När en beläggningsrad skapas anges som standard viktfälten från produkten på den.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-115">By default, when a load line is created, the weight fields from the product are entered on it.</span></span> <span data-ttu-id="2f8cc-116">Om vikten är noll kan du beräkna om den med hjälp av funktionen för *överensstämmelsekontroll av lagerställets belastningsvikt*.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-116">If the weight is zero, you can recalculate it by using the *Warehouse load weight consistency check* functionality.</span></span>

1. <span data-ttu-id="2f8cc-117">Gå till **Systemadministration \> Periodiska uppgifter \> Databas \> Överensstämmelsekontroll**.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-117">Go to **System administration \> Periodic tasks \> Database \> Consistency check**.</span></span>
1. <span data-ttu-id="2f8cc-118">I dialogrutan **Överensstämmelsekontroll** anger du fältet **Modul** som *Lagerhantering*.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-118">In the **Consistency check** dialog box, set the **Module** field to *Warehouse management*.</span></span>
1. <span data-ttu-id="2f8cc-119">Ange fältet **Kontroll/åtgärd** som *Korrigera fel*.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-119">Set the **Check/Fix** field to *Fix error*.</span></span>
1. <span data-ttu-id="2f8cc-120">I listan väljer du kryssrutan för **Överensstämmelse för lagerställets belastningsvikt** och ser till att endast raden för denna kryssruta är markerad.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-120">In the checkbox list, select the **Warehouse load weight consistency check** checkbox, and make sure that only the row for this checkbox is highlighted.</span></span>
1. <span data-ttu-id="2f8cc-121">Högst upp i kryssrutelistan väljer du ellipsknappen (**...**) och väljer sedan **Dialog** i menyn.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-121">At the top of the checkbox list, select the ellipsis button (**...**), and then select **Dialog** on the menu.</span></span>
1. <span data-ttu-id="2f8cc-122">I dialogrutan **Överensstämmelsekontroll av överensstämmelse för lagerställes belastningsvikt** anger du följande fält i syfte att ange de kriterier som överensstämmelsekontrollen ska köras för:</span><span class="sxs-lookup"><span data-stu-id="2f8cc-122">In the **Warehouse load weight consistency check** dialog box, set the following fields to specify the criteria that the consistency check should run for:</span></span>

    - <span data-ttu-id="2f8cc-123">**Beläggnings-ID:** Ange ett beläggnings-ID.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-123">**Load ID:** Specify a load ID.</span></span> <span data-ttu-id="2f8cc-124">Låt detta fält vara tomt om du vill kontrollera alla inläsnings-ID:er.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-124">Leave this blank to check all load IDs.</span></span>
    - <span data-ttu-id="2f8cc-125">**Artikelnummer:** Ange ett artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-125">**Item number:** Specify an item number.</span></span> <span data-ttu-id="2f8cc-126">Låt detta fält vara tomt om du vill kontrollera alla artiklar.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-126">Leave this blank to check all items.</span></span>
    - <span data-ttu-id="2f8cc-127">**Räkna alltid om vikt på beläggningar:** Ange detta alternativ som *Ja*.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-127">**Always recalculate weight on loads:** Set this option to *Yes*.</span></span>
    - <span data-ttu-id="2f8cc-128">**Tillåt överskrivning av vikt på beläggningsrader:** Ange det här alternativet som *Ja*.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-128">**Allow overwrite of weight on load lines:** Set this option to *Yes*.</span></span>

1. <span data-ttu-id="2f8cc-129">Välj **OK** om du vill stänga dialogrutan **Överensstämmelsekontrollen för lagerställets belastningsvikt**.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-129">Select **OK** to close the **Warehouse load weight consistency check** dialog box.</span></span>
1. <span data-ttu-id="2f8cc-130">Välj ellipsknappen och sedan **Kör** i menyn.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-130">Select the ellipsis button, and then select **Execute** on the menu.</span></span>

<span data-ttu-id="2f8cc-131">Vikten räknas om baserat på de kriterier som du har angett.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-131">The weight is recalculated based on the criteria that you specified.</span></span> <span data-ttu-id="2f8cc-132">Markera länken **Meddelandeinformation** om du vill visa resultatet av överensstämmelsekontrollen.</span><span class="sxs-lookup"><span data-stu-id="2f8cc-132">Select the **Message details** link to view the result of the consistency check.</span></span>
