---
title: Aktivera löneprocessen för tid och närvaro
description: I den här proceduren visas hur du aktiverar lönelistprocessen för tid och närvaro.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgPayTable, JmgPayRate, JmgPayAgreementTable, JmgPayAgreementLine, HcmWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72b925feb8f784c257656dd93b48c9c0cc66da5e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214924"
---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a><span data-ttu-id="0ede7-103">Aktivera löneprocessen för tid och närvaro</span><span class="sxs-lookup"><span data-stu-id="0ede7-103">Enable the payroll process for time and attendance</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0ede7-104">I den här proceduren visas hur du aktiverar lönelistprocessen för tid och närvaro.</span><span class="sxs-lookup"><span data-stu-id="0ede7-104">This procedure shows how to enable the payroll process for time and attendance.</span></span> <span data-ttu-id="0ede7-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="0ede7-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-pay-type-with-a-related-pay-rate"></a><span data-ttu-id="0ede7-106">Skapa en lönetyp med en relaterad lönesats</span><span class="sxs-lookup"><span data-stu-id="0ede7-106">Create a pay type with a related pay rate</span></span>
1. <span data-ttu-id="0ede7-107">Tid och närvaro > Inställningar > Lön > Lönetyper</span><span class="sxs-lookup"><span data-stu-id="0ede7-107">Time and attendance > Setup > Payroll > Pay types</span></span>
2. <span data-ttu-id="0ede7-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0ede7-108">Click New.</span></span>
3. <span data-ttu-id="0ede7-109">Skriv ett värde i fältet Lönetyp.</span><span class="sxs-lookup"><span data-stu-id="0ede7-109">In the Pay type field, type a value.</span></span>
4. <span data-ttu-id="0ede7-110">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="0ede7-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="0ede7-111">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="0ede7-111">Click Save.</span></span>
6. <span data-ttu-id="0ede7-112">Klick på Tariffer.</span><span class="sxs-lookup"><span data-stu-id="0ede7-112">Click Rates.</span></span>
    * <span data-ttu-id="0ede7-113">Satser för lönetyper ställs in för särskilda tidsintervall och individuella satser kan skapas för enskilda arbetare.</span><span class="sxs-lookup"><span data-stu-id="0ede7-113">Rates for pay types are set up for specific time intervals, and individual rates can be created for workers.</span></span> <span data-ttu-id="0ede7-114">Du behöver inte alltid skapa satser för lönetyper i tid och närvaro.</span><span class="sxs-lookup"><span data-stu-id="0ede7-114">It is not always necessary to create rates for pay types in time and attendance.</span></span> <span data-ttu-id="0ede7-115">Den här informationen kanske redan finns i lönesystemet som används för att generera löner.</span><span class="sxs-lookup"><span data-stu-id="0ede7-115">This information may already exist in the payroll system that is used to generate wages.</span></span>  
7. <span data-ttu-id="0ede7-116">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0ede7-116">Click New.</span></span>
8. <span data-ttu-id="0ede7-117">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="0ede7-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="0ede7-118">Välj ett tal i fältet Tariff.</span><span class="sxs-lookup"><span data-stu-id="0ede7-118">In the Rate field, enter a number.</span></span>
10. <span data-ttu-id="0ede7-119">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="0ede7-119">Click Save.</span></span>

## <a name="create-a-pay-agreement"></a><span data-ttu-id="0ede7-120">Skapa ett löneavtal</span><span class="sxs-lookup"><span data-stu-id="0ede7-120">Create a pay agreement</span></span>
1. <span data-ttu-id="0ede7-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0ede7-121">Close the page.</span></span>
2. <span data-ttu-id="0ede7-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0ede7-122">Close the page.</span></span>
3. <span data-ttu-id="0ede7-123">Gå till Löneavtal.</span><span class="sxs-lookup"><span data-stu-id="0ede7-123">Go to Pay agreements.</span></span>
    * <span data-ttu-id="0ede7-124">Tid och närvaro > Inställningar > Löneavtal</span><span class="sxs-lookup"><span data-stu-id="0ede7-124">Time and attendance > Setup > Pay agreements</span></span>  
4. <span data-ttu-id="0ede7-125">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0ede7-125">Click New.</span></span>
5. <span data-ttu-id="0ede7-126">Skriv ett värde i fältet Löneavtal.</span><span class="sxs-lookup"><span data-stu-id="0ede7-126">In the Pay agreement field, type a value.</span></span>
6. <span data-ttu-id="0ede7-127">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="0ede7-127">In the Description field, type a value.</span></span>
7. <span data-ttu-id="0ede7-128">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="0ede7-128">Click Save.</span></span>
8. <span data-ttu-id="0ede7-129">Klicka på Avtalsrader.</span><span class="sxs-lookup"><span data-stu-id="0ede7-129">Click Agreement lines.</span></span>
9. <span data-ttu-id="0ede7-130">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0ede7-130">Click New.</span></span>
10. <span data-ttu-id="0ede7-131">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="0ede7-131">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="0ede7-132">Ange eller välj ett värde i fältet Profiltyp.</span><span class="sxs-lookup"><span data-stu-id="0ede7-132">In the Profile type field, enter or select a value.</span></span>
12. <span data-ttu-id="0ede7-133">Ange eller välj ett värde i fältet Lönetyp.</span><span class="sxs-lookup"><span data-stu-id="0ede7-133">In the Pay type field, enter or select a value.</span></span>

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a><span data-ttu-id="0ede7-134">Ställ in löneavtal för tids- och registreringsarbetare</span><span class="sxs-lookup"><span data-stu-id="0ede7-134">Set up pay agreement for time and registration worker</span></span>
1. <span data-ttu-id="0ede7-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0ede7-135">Close the page.</span></span>
2. <span data-ttu-id="0ede7-136">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0ede7-136">Close the page.</span></span>
3. <span data-ttu-id="0ede7-137">Gå till Tidsregistreringsarbetare.</span><span class="sxs-lookup"><span data-stu-id="0ede7-137">Go to Time registration workers.</span></span>
    * <span data-ttu-id="0ede7-138">Tid och närvaro > Inställningar > Tidsregistreringsarbetare</span><span class="sxs-lookup"><span data-stu-id="0ede7-138">Time and attendance > Setup > Time registration workers</span></span>  
4. <span data-ttu-id="0ede7-139">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="0ede7-139">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="0ede7-140">Klicka på fliken Anställning.</span><span class="sxs-lookup"><span data-stu-id="0ede7-140">Click the Employment tab.</span></span>
6. <span data-ttu-id="0ede7-141">Expandera tidsregistreringsavsnittet.</span><span class="sxs-lookup"><span data-stu-id="0ede7-141">Expand the Time registration section.</span></span>
7. <span data-ttu-id="0ede7-142">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="0ede7-142">Click Edit.</span></span>
8. <span data-ttu-id="0ede7-143">Ange eller välj ett värde i fältet Löneavtal.</span><span class="sxs-lookup"><span data-stu-id="0ede7-143">In the Pay agreement field, enter or select a value.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]