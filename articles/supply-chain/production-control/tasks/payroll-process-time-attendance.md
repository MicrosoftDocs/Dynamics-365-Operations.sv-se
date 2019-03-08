---
title: Aktivera löneprocessen för tid och närvaro
description: I den här proceduren visas hur du aktiverar lönelistprocessen för tid och närvaro.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgPayTable, JmgPayRate, JmgPayAgreementTable, JmgPayAgreementLine, HcmWorker
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0174f438396d814d153befe4a59a79b6eebb2288
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "311115"
---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a><span data-ttu-id="ffb87-103">Aktivera löneprocessen för tid och närvaro</span><span class="sxs-lookup"><span data-stu-id="ffb87-103">Enable the payroll process for time and attendance</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ffb87-104">I den här proceduren visas hur du aktiverar lönelistprocessen för tid och närvaro.</span><span class="sxs-lookup"><span data-stu-id="ffb87-104">This procedure shows how to enable the payroll process for time and attendance.</span></span> <span data-ttu-id="ffb87-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="ffb87-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-pay-type-with-a-related-pay-rate"></a><span data-ttu-id="ffb87-106">Skapa en lönetyp med en relaterad lönesats</span><span class="sxs-lookup"><span data-stu-id="ffb87-106">Create a pay type with a related pay rate</span></span>
1. <span data-ttu-id="ffb87-107">Tid och närvaro > Inställningar > Lön > Lönetyper</span><span class="sxs-lookup"><span data-stu-id="ffb87-107">Time and attendance > Setup > Payroll > Pay types</span></span>
2. <span data-ttu-id="ffb87-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ffb87-108">Click New.</span></span>
3. <span data-ttu-id="ffb87-109">Skriv ett värde i fältet Lönetyp.</span><span class="sxs-lookup"><span data-stu-id="ffb87-109">In the Pay type field, type a value.</span></span>
4. <span data-ttu-id="ffb87-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="ffb87-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ffb87-111">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ffb87-111">Click Save.</span></span>
6. <span data-ttu-id="ffb87-112">Klick på Tariffer.</span><span class="sxs-lookup"><span data-stu-id="ffb87-112">Click Rates.</span></span>
    * <span data-ttu-id="ffb87-113">Satser för lönetyper ställs in för särskilda tidsintervall och individuella satser kan skapas för enskilda arbetare.</span><span class="sxs-lookup"><span data-stu-id="ffb87-113">Rates for pay types are set up for specific time intervals, and individual rates can be created for workers.</span></span> <span data-ttu-id="ffb87-114">Du behöver inte alltid skapa satser för lönetyper i tid och närvaro.</span><span class="sxs-lookup"><span data-stu-id="ffb87-114">It is not always necessary to create rates for pay types in time and attendance.</span></span> <span data-ttu-id="ffb87-115">Den här informationen kanske redan finns i lönesystemet som används för att generera löner.</span><span class="sxs-lookup"><span data-stu-id="ffb87-115">This information may already exist in the payroll system that is used to generate wages.</span></span>  
7. <span data-ttu-id="ffb87-116">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ffb87-116">Click New.</span></span>
8. <span data-ttu-id="ffb87-117">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="ffb87-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="ffb87-118">Välj ett tal i fältet Tariff.</span><span class="sxs-lookup"><span data-stu-id="ffb87-118">In the Rate field, enter a number.</span></span>
10. <span data-ttu-id="ffb87-119">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ffb87-119">Click Save.</span></span>

## <a name="create-a-pay-agreement"></a><span data-ttu-id="ffb87-120">Skapa ett löneavtal</span><span class="sxs-lookup"><span data-stu-id="ffb87-120">Create a pay agreement</span></span>
1. <span data-ttu-id="ffb87-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ffb87-121">Close the page.</span></span>
2. <span data-ttu-id="ffb87-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ffb87-122">Close the page.</span></span>
3. <span data-ttu-id="ffb87-123">Gå till Löneavtal.</span><span class="sxs-lookup"><span data-stu-id="ffb87-123">Go to Pay agreements.</span></span>
    * <span data-ttu-id="ffb87-124">Tid och närvaro > Inställningar > Löneavtal</span><span class="sxs-lookup"><span data-stu-id="ffb87-124">Time and attendance > Setup > Pay agreements</span></span>  
4. <span data-ttu-id="ffb87-125">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ffb87-125">Click New.</span></span>
5. <span data-ttu-id="ffb87-126">Skriv ett värde i fältet Löneavtal.</span><span class="sxs-lookup"><span data-stu-id="ffb87-126">In the Pay agreement field, type a value.</span></span>
6. <span data-ttu-id="ffb87-127">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="ffb87-127">In the Description field, type a value.</span></span>
7. <span data-ttu-id="ffb87-128">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ffb87-128">Click Save.</span></span>
8. <span data-ttu-id="ffb87-129">Klicka på Avtalsrader.</span><span class="sxs-lookup"><span data-stu-id="ffb87-129">Click Agreement lines.</span></span>
9. <span data-ttu-id="ffb87-130">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ffb87-130">Click New.</span></span>
10. <span data-ttu-id="ffb87-131">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="ffb87-131">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="ffb87-132">Ange eller välj ett värde i fältet Profiltyp.</span><span class="sxs-lookup"><span data-stu-id="ffb87-132">In the Profile type field, enter or select a value.</span></span>
12. <span data-ttu-id="ffb87-133">Ange eller välj ett värde i fältet Lönetyp.</span><span class="sxs-lookup"><span data-stu-id="ffb87-133">In the Pay type field, enter or select a value.</span></span>

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a><span data-ttu-id="ffb87-134">Ställ in löneavtal för tids- och registreringsarbetare</span><span class="sxs-lookup"><span data-stu-id="ffb87-134">Set up pay agreement for time and registration worker</span></span>
1. <span data-ttu-id="ffb87-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ffb87-135">Close the page.</span></span>
2. <span data-ttu-id="ffb87-136">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ffb87-136">Close the page.</span></span>
3. <span data-ttu-id="ffb87-137">Gå till Tidsregistreringsarbetare.</span><span class="sxs-lookup"><span data-stu-id="ffb87-137">Go to Time registration workers.</span></span>
    * <span data-ttu-id="ffb87-138">Tid och närvaro > Inställningar > Tidsregistreringsarbetare</span><span class="sxs-lookup"><span data-stu-id="ffb87-138">Time and attendance > Setup > Time registration workers</span></span>  
4. <span data-ttu-id="ffb87-139">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ffb87-139">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="ffb87-140">Klicka på fliken Anställning.</span><span class="sxs-lookup"><span data-stu-id="ffb87-140">Click the Employment tab.</span></span>
6. <span data-ttu-id="ffb87-141">Expandera tidsregistreringsavsnittet.</span><span class="sxs-lookup"><span data-stu-id="ffb87-141">Expand the Time registration section.</span></span>
7. <span data-ttu-id="ffb87-142">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="ffb87-142">Click Edit.</span></span>
8. <span data-ttu-id="ffb87-143">Ange eller välj ett värde i fältet Löneavtal.</span><span class="sxs-lookup"><span data-stu-id="ffb87-143">In the Pay agreement field, enter or select a value.</span></span>

