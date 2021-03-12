---
title: EUR-00015 Registrering av moms-ID för leverantör
description: I den här proceduren visas hur du lägger till momsregistrerings-ID och momsbefrielsenummer i ett leverantörskonto.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddress, RegNumTaxIdLookup
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eb8e5ea8a7a8360155c9eb30eaa85004483950e2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4984769"
---
# <a name="eur-00015-registration-of-vendor-vat-id"></a><span data-ttu-id="8b41a-103">EUR-00015 Registrering av moms-ID för leverantör</span><span class="sxs-lookup"><span data-stu-id="8b41a-103">EUR-00015 Registration of vendor VAT ID</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8b41a-104">I den här proceduren visas hur du lägger till momsregistrerings-ID och momsbefrielsenummer i ett leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="8b41a-104">This procedure shows how to add VAT registration IDs and a tax except number to a vendor account.</span></span> <span data-ttu-id="8b41a-105">Den här processen påminner om den för juridiska personer och kunder.</span><span class="sxs-lookup"><span data-stu-id="8b41a-105">This process is similar for legal entities and customers.</span></span> 

<span data-ttu-id="8b41a-106">Innan du kan slutföra denna procedur måste du skapa moms-ID:n.</span><span class="sxs-lookup"><span data-stu-id="8b41a-106">Before you can complete this procedure you must set up VAT IDs.</span></span> <span data-ttu-id="8b41a-107">Den här proceduren gäller för alla europeiska länder/regioner.</span><span class="sxs-lookup"><span data-stu-id="8b41a-107">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="8b41a-108">Proceduren skapades med hjälp av demonstrationsdataföretaget DEMF, med primär adress i Tyskland.</span><span class="sxs-lookup"><span data-stu-id="8b41a-108">The procedure was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="8b41a-109">Denna procedur är avsedd för en datahanteringsadministratör, leverantörsreskontrachef eller en kundreskontrachef.</span><span class="sxs-lookup"><span data-stu-id="8b41a-109">This procedure is intended for a data management administrator, accounts payable manager, or accounts receivable manager.</span></span> <span data-ttu-id="8b41a-110">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="8b41a-110">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="8b41a-111">Gå till leverantörsreskontra > Leverantörer > Alla leverantörer.</span><span class="sxs-lookup"><span data-stu-id="8b41a-111">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="8b41a-112">Hitta och välj leverantören vendor DE-01001 i listan</span><span class="sxs-lookup"><span data-stu-id="8b41a-112">In the list find and select vendor DE-01001</span></span>
3. <span data-ttu-id="8b41a-113">Klicka på Registration IDs.</span><span class="sxs-lookup"><span data-stu-id="8b41a-113">Click Registration IDs.</span></span>
4. <span data-ttu-id="8b41a-114">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="8b41a-114">Click Add.</span></span>
5. <span data-ttu-id="8b41a-115">Välj moms-ID.</span><span class="sxs-lookup"><span data-stu-id="8b41a-115">Select VAT ID.</span></span>
6. <span data-ttu-id="8b41a-116">Ange ett värde i fältet Registration number.</span><span class="sxs-lookup"><span data-stu-id="8b41a-116">In the Registration number field, type a value.</span></span>
    * <span data-ttu-id="8b41a-117">Ange ett moms-ID i Tyskland för den valda leverantören.</span><span class="sxs-lookup"><span data-stu-id="8b41a-117">Specify a VAT ID in Germany for the selected vendor.</span></span> <span data-ttu-id="8b41a-118">ID måste matcha det angivna formatet för registreringstypen.</span><span class="sxs-lookup"><span data-stu-id="8b41a-118">The ID must match the specified format of the registration type.</span></span>  
7. <span data-ttu-id="8b41a-119">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="8b41a-119">Click the General tab.</span></span>
8. <span data-ttu-id="8b41a-120">Ange ett datum i fältet Giltighet.</span><span class="sxs-lookup"><span data-stu-id="8b41a-120">In the Effective field, enter a date.</span></span>
9. <span data-ttu-id="8b41a-121">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8b41a-121">Click Save.</span></span>
10. <span data-ttu-id="8b41a-122">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8b41a-122">Click New.</span></span>
11. <span data-ttu-id="8b41a-123">Skriv ett värde i fältet Namn eller beskrivning.</span><span class="sxs-lookup"><span data-stu-id="8b41a-123">In the Name or description field, type a value.</span></span>
    * <span data-ttu-id="8b41a-124">Ange exempelvis ITA.</span><span class="sxs-lookup"><span data-stu-id="8b41a-124">For example, enter ITA.</span></span>  
12. <span data-ttu-id="8b41a-125">Ange eller välj ett värde i fältet Land/region.</span><span class="sxs-lookup"><span data-stu-id="8b41a-125">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="8b41a-126">Välj till exempel ITA.</span><span class="sxs-lookup"><span data-stu-id="8b41a-126">For example, select ITA.</span></span>  
13. <span data-ttu-id="8b41a-127">Välj Yes i fältet Primary for country.</span><span class="sxs-lookup"><span data-stu-id="8b41a-127">Select Yes in the Primary for country field.</span></span>
14. <span data-ttu-id="8b41a-128">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8b41a-128">Click Save.</span></span>
15. <span data-ttu-id="8b41a-129">Klicka på fliken Översikt.</span><span class="sxs-lookup"><span data-stu-id="8b41a-129">Click the Overview tab.</span></span>
16. <span data-ttu-id="8b41a-130">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="8b41a-130">Click Add.</span></span>
17. <span data-ttu-id="8b41a-131">Ange eller välj ett värde i fältet Registration type.</span><span class="sxs-lookup"><span data-stu-id="8b41a-131">In the Registration type field, enter or select a value.</span></span>
    * <span data-ttu-id="8b41a-132">Välj till exempel moms-ID (VAT ID).</span><span class="sxs-lookup"><span data-stu-id="8b41a-132">For example, select VAT ID.</span></span>  
18. <span data-ttu-id="8b41a-133">Ange ett värde i fältet Registration number.</span><span class="sxs-lookup"><span data-stu-id="8b41a-133">In the Registration number field, type a value.</span></span>
    * <span data-ttu-id="8b41a-134">Ange exempelvis ett moms-ID i Italien.</span><span class="sxs-lookup"><span data-stu-id="8b41a-134">For example, specify a VAT ID in Italy.</span></span>  <span data-ttu-id="8b41a-135">ID måste ha samma format som registreringstypen.</span><span class="sxs-lookup"><span data-stu-id="8b41a-135">The ID must have the same format as the registration type.</span></span>  
19. <span data-ttu-id="8b41a-136">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8b41a-136">Click Save.</span></span>
20. <span data-ttu-id="8b41a-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8b41a-137">Close the page.</span></span>
21. <span data-ttu-id="8b41a-138">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="8b41a-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="8b41a-139">Välj till exempel DE-01001.</span><span class="sxs-lookup"><span data-stu-id="8b41a-139">For example, select DE-01001.</span></span>  
22. <span data-ttu-id="8b41a-140">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="8b41a-140">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="8b41a-141">Expandera faktura- och leveransavsnittet.</span><span class="sxs-lookup"><span data-stu-id="8b41a-141">Expand the Invoice and delivery section.</span></span>
24. <span data-ttu-id="8b41a-142">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="8b41a-142">Click Edit.</span></span>
25. <span data-ttu-id="8b41a-143">Ange eller välj ett värde i fältet Momsregistreringsnummer.</span><span class="sxs-lookup"><span data-stu-id="8b41a-143">In the Tax exempt number field, enter or select a value.</span></span>
26. <span data-ttu-id="8b41a-144">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8b41a-144">Click Save.</span></span>

