---
title: EUR-00015 Skapa moms-ID
description: Denna procedur går igenom registreringsförutsättningarna för moms-ID, till exempel hur du skapar en registreringstyp och tilldelar den till en registreringskategori.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxRegistrationType, TaxRegistrationTypeCreate, TaxRegistrationLegislationTypes
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 127e6caf6a6273df36f580b32fa81219b88b8a29
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183939"
---
# <a name="eur-00015-set-up-vat-id"></a><span data-ttu-id="5ae73-103">EUR-00015 Skapa moms-ID</span><span class="sxs-lookup"><span data-stu-id="5ae73-103">EUR-00015 Set up VAT ID</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5ae73-104">Denna procedur går igenom registreringsförutsättningarna för moms-ID, till exempel hur du skapar en registreringstyp och tilldelar den till en registreringskategori.</span><span class="sxs-lookup"><span data-stu-id="5ae73-104">This procedure walks you through VAT ID registration prerequisites, such as setting up a registration type and assigning it to a registration category.</span></span> <span data-ttu-id="5ae73-105">Du kan hitta ytterligare information om registrerings-ID och bearbetning av registrerings-ID, inklusive erforderliga förutsättningar, i hjälpavsnittet för registrerings-ID.</span><span class="sxs-lookup"><span data-stu-id="5ae73-105">You can find additional information about registration IDs and registration ID processing, including required prerequisites, in the Registration IDs help topic.</span></span> 

<span data-ttu-id="5ae73-106">Informationen här gäller alla europeiska länder/regioner.</span><span class="sxs-lookup"><span data-stu-id="5ae73-106">The information here applies to all European countries/regions.</span></span> <span data-ttu-id="5ae73-107">Uppgiften skapades med hjälp av demonstrationsdataföretaget DEMF, med Tyskland som primär adress för juridisk person.</span><span class="sxs-lookup"><span data-stu-id="5ae73-107">The task was created using the demo data company DEMF with Germany as the legal entity primary address.</span></span> <span data-ttu-id="5ae73-108">Denna uppgift är avsedd för systemadministratörer.</span><span class="sxs-lookup"><span data-stu-id="5ae73-108">This task is intended for system administrators.</span></span> <span data-ttu-id="5ae73-109">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="5ae73-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="5ae73-110">Gå till Organization administration > Global address book > Registration types > Registration types.</span><span class="sxs-lookup"><span data-stu-id="5ae73-110">Go to Organization administration > Global address book > Registration types > Registration types.</span></span>
2. <span data-ttu-id="5ae73-111">Klicka på Nytt om du vill öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="5ae73-111">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="5ae73-112">Ange "VAT ID" i fältet Name.</span><span class="sxs-lookup"><span data-stu-id="5ae73-112">In the Name field, type 'VAT ID'.</span></span>
4. <span data-ttu-id="5ae73-113">Ange momsnumret i fältet Description.</span><span class="sxs-lookup"><span data-stu-id="5ae73-113">In the Description field, VAT number.</span></span>
5. <span data-ttu-id="5ae73-114">Ange eller välj värdet DEU i fältet Country/region</span><span class="sxs-lookup"><span data-stu-id="5ae73-114">In the Country/region field, enter or select a value DEU</span></span>
6. <span data-ttu-id="5ae73-115">Välj Yes i fältet Unique.</span><span class="sxs-lookup"><span data-stu-id="5ae73-115">Select Yes in the Unique field.</span></span>
    * <span data-ttu-id="5ae73-116">Markera den här kryssrutan för att bekräfta att moms-ID är unikt.</span><span class="sxs-lookup"><span data-stu-id="5ae73-116">Select this check box to verify if the VAT ID is unique.</span></span>  
7. <span data-ttu-id="5ae73-117">Välj Yes i fältet Primary for country.</span><span class="sxs-lookup"><span data-stu-id="5ae73-117">Select Yes in the Primary for country field.</span></span>
    * <span data-ttu-id="5ae73-118">Markera den här kryssrutan om moms-ID ska gälla för alla adresser som tillhör det land/den region som angetts.</span><span class="sxs-lookup"><span data-stu-id="5ae73-118">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
8. <span data-ttu-id="5ae73-119">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="5ae73-119">Click Create.</span></span>
9. <span data-ttu-id="5ae73-120">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="5ae73-120">Click Add.</span></span>
10. <span data-ttu-id="5ae73-121">Ange eller välj värdet ITA i fältet country/region</span><span class="sxs-lookup"><span data-stu-id="5ae73-121">In the Country/region field, enter or select a value ITA</span></span>
11. <span data-ttu-id="5ae73-122">I fältet Format anger du "###########".</span><span class="sxs-lookup"><span data-stu-id="5ae73-122">In the Format field, type '###########'.</span></span>
    * <span data-ttu-id="5ae73-123">När du anger ett registrerings-ID av denna typ för det land/den region som har valts, kommer registrerings-ID att kontrolleras mot detta format.</span><span class="sxs-lookup"><span data-stu-id="5ae73-123">When you enter a registration ID of this type for the selected country/region, the registration ID will be verified against this format.</span></span>  
12. <span data-ttu-id="5ae73-124">Markera kryssrutan Unique.</span><span class="sxs-lookup"><span data-stu-id="5ae73-124">Select the Unique check box.</span></span>
    * <span data-ttu-id="5ae73-125">Markera den här kryssrutan för att bekräfta att moms-ID är unikt.</span><span class="sxs-lookup"><span data-stu-id="5ae73-125">Select this check box to verify if the VAT ID is unique.</span></span>  
13. <span data-ttu-id="5ae73-126">Markera kryssrutan Primary for country.</span><span class="sxs-lookup"><span data-stu-id="5ae73-126">Select the Primary for country check box.</span></span>
    * <span data-ttu-id="5ae73-127">Markera den här kryssrutan om moms-ID ska gälla för alla adresser som tillhör det land/den region som angetts.</span><span class="sxs-lookup"><span data-stu-id="5ae73-127">Select this check box if the VAT ID should be effective for all addresses belonging to the specified country/region.</span></span>  
14. <span data-ttu-id="5ae73-128">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5ae73-128">Click Save.</span></span>
15. <span data-ttu-id="5ae73-129">Gå till Organization administration > Global address book > Registration types > Registration categories.</span><span class="sxs-lookup"><span data-stu-id="5ae73-129">Go to Organization administration > Global address book > Registration types > Registration categories.</span></span>
16. <span data-ttu-id="5ae73-130">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5ae73-130">Click New.</span></span>
17. <span data-ttu-id="5ae73-131">Ange eller välj värdet DEU för moms-ID i fältet Country/region</span><span class="sxs-lookup"><span data-stu-id="5ae73-131">In the Country/region field, enter or select a value VAT ID, DEU</span></span>
18. <span data-ttu-id="5ae73-132">Välj "VAT ID" i fältet Registration category.</span><span class="sxs-lookup"><span data-stu-id="5ae73-132">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="5ae73-133">Tilldela den registreringstyp som du skapade tidigare till en fördefinierad registreringskategori.</span><span class="sxs-lookup"><span data-stu-id="5ae73-133">Assign the registration type that you created earlier to a predefined Registration category.</span></span>  
19. <span data-ttu-id="5ae73-134">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="5ae73-134">Click New.</span></span>
20. <span data-ttu-id="5ae73-135">Ange eller välj värdet ITA för moms-ID i fältet Country/region</span><span class="sxs-lookup"><span data-stu-id="5ae73-135">In the Country/region field, enter or select a value VAT ID, ITA</span></span>
21. <span data-ttu-id="5ae73-136">Välj "VAT ID" i fältet Registration category.</span><span class="sxs-lookup"><span data-stu-id="5ae73-136">In the Registration category field, select 'VAT ID'.</span></span>
    * <span data-ttu-id="5ae73-137">Tilldela den registreringstyp som du skapade till en fördefinierad registreringskategori.</span><span class="sxs-lookup"><span data-stu-id="5ae73-137">Assign the registration type that you created to a predefined registration category.</span></span>  
22. <span data-ttu-id="5ae73-138">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="5ae73-138">Click Save.</span></span>

