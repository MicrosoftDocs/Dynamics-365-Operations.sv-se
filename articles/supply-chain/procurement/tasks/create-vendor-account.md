---
title: Skapa ett leverantörskonto
description: I den här proceduren visas hur du skapar ett leverantörskonto och lägger till en adress och kontaktinformation.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 98a7c6d209400b754064f2176d1ebca291093304
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838056"
---
# <a name="create-a-vendor-account"></a><span data-ttu-id="7a0df-103">Skapa ett leverantörskonto</span><span class="sxs-lookup"><span data-stu-id="7a0df-103">Create a vendor account</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7a0df-104">I den här proceduren visas hur du skapar ett leverantörskonto och lägger till en adress och kontaktinformation.</span><span class="sxs-lookup"><span data-stu-id="7a0df-104">This procedure shows how to create a vendor account, and add an address and contact information.</span></span> <span data-ttu-id="7a0df-105">I proceduren visas inte hur du fyller i alla fält i inköpssyfte och ekonomiska syften.</span><span class="sxs-lookup"><span data-stu-id="7a0df-105">The procedure does not show how to populate all fields for purchasing and financial purposes.</span></span> <span data-ttu-id="7a0df-106">Läs fältbeskrivningarna om du vill veta mer om dessa fält.</span><span class="sxs-lookup"><span data-stu-id="7a0df-106">To learn more about those fields, please read the field descriptions.</span></span> <span data-ttu-id="7a0df-107">Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="7a0df-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="7a0df-108">Leverantörkonton skapas vanligtvis av ett anskaffningsproffs eller en kundreskontrapersonal.</span><span class="sxs-lookup"><span data-stu-id="7a0df-108">Vendor accounts are typically created by a procurement professional or accounts receivable personnel.</span></span>


## <a name="create-a-vendor-account"></a><span data-ttu-id="7a0df-109">Skapa ett leverantörskonto</span><span class="sxs-lookup"><span data-stu-id="7a0df-109">Create a vendor account</span></span>
1. <span data-ttu-id="7a0df-110">Gå till Anskaffning och källa > Leverantörer > Alla leverantörer.</span><span class="sxs-lookup"><span data-stu-id="7a0df-110">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="7a0df-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="7a0df-111">Click New.</span></span>
3. <span data-ttu-id="7a0df-112">Ange ett värde i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="7a0df-112">In the Vendor account field, type a value.</span></span>
    * <span data-ttu-id="7a0df-113">Värdet kan fyllas i automatiskt.</span><span class="sxs-lookup"><span data-stu-id="7a0df-113">The value may be populated automatically.</span></span> <span data-ttu-id="7a0df-114">Om det gör det kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="7a0df-114">If so, you can skip this step.</span></span>  
    * <span data-ttu-id="7a0df-115">Du kan skapa leverantörskonton för en person eller en organisation.</span><span class="sxs-lookup"><span data-stu-id="7a0df-115">You can create vendor accounts for a person or organization.</span></span> <span data-ttu-id="7a0df-116">Detta påverkar vilka fält som är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="7a0df-116">This will affect which fields are available.</span></span> <span data-ttu-id="7a0df-117">I det här exemplet ska du skapa ett leverantörskonto för en organisation.</span><span class="sxs-lookup"><span data-stu-id="7a0df-117">In this example, we’ll create a vendor account for an organization.</span></span>   
4. <span data-ttu-id="7a0df-118">Ange eller välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="7a0df-118">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="7a0df-119">Om leverantören är en redan registrerad part i systemet kan du använda listrutan och välja honom/henne i det här fältet, så ärver det nya leverantörskontot den adress och kontaktinformation som redan är registrerad.</span><span class="sxs-lookup"><span data-stu-id="7a0df-119">If your vendor is an already a registered party in your system you can use drop down and select them in this field and the new vendor account will inherit the address and contact information that’s already registered.</span></span>  
5. <span data-ttu-id="7a0df-120">Ange eller välj ett värde i fältet Grupp.</span><span class="sxs-lookup"><span data-stu-id="7a0df-120">In the Group field, enter or select a value.</span></span>
    * <span data-ttu-id="7a0df-121">Leverantörsgruppen används för att gruppera leverantörer som har någon av följande parametrar gemensamt: Betalningsvillkor, kvittningsperiod, huvudbokskonton för lagerbokföring inklusive momsgruppen, standardhuvudbokskonton, produktfilterkoder och leveransprognoskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="7a0df-121">The vendor group is used to group vendors that have any of the following parameters in common: Terms of payment , settle period,  inventory posting ledger accounts – including the sales tax group, default ledger accounts, product filter codes, or supply forecast configuration.</span></span>  
6. <span data-ttu-id="7a0df-122">Ange ett antal i fältet Antal medarbetare.</span><span class="sxs-lookup"><span data-stu-id="7a0df-122">In the Number of employees field, enter a number.</span></span>
7. <span data-ttu-id="7a0df-123">Skriv ett värde i fältet Organisationsnummer.</span><span class="sxs-lookup"><span data-stu-id="7a0df-123">In the Organization number field, type a value.</span></span>

## <a name="add-an-address"></a><span data-ttu-id="7a0df-124">Lägg till en adress</span><span class="sxs-lookup"><span data-stu-id="7a0df-124">Add an address</span></span>
1. <span data-ttu-id="7a0df-125">Expandera avsnittet Adresser.</span><span class="sxs-lookup"><span data-stu-id="7a0df-125">Expand the Addresses section.</span></span>
2. <span data-ttu-id="7a0df-126">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a0df-126">Click Add.</span></span>
3. <span data-ttu-id="7a0df-127">Ange eller välj ett värde i fältet Syfte.</span><span class="sxs-lookup"><span data-stu-id="7a0df-127">In the Purpose field, enter or select a value.</span></span>
    * <span data-ttu-id="7a0df-128">Du kan välja en eller flera syften.</span><span class="sxs-lookup"><span data-stu-id="7a0df-128">You can select one or more purposes.</span></span> <span data-ttu-id="7a0df-129">Dessa används för att välja korrekt adress för ett visst syfte.</span><span class="sxs-lookup"><span data-stu-id="7a0df-129">These are used to select the correct address for a given purpose.</span></span> <span data-ttu-id="7a0df-130">Om syftet te.x. är "Faktura" kommer den adressen att användas när du skickar fakturor.</span><span class="sxs-lookup"><span data-stu-id="7a0df-130">For example, if the purpose is “Invoice” that address will be used when you send invoices.</span></span>  
4. <span data-ttu-id="7a0df-131">Skriv ett värde i fältet Namn eller beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a0df-131">In the Name or description field, type a value.</span></span>
5. <span data-ttu-id="7a0df-132">Ange eller välj ett värde i fältet Land/region.</span><span class="sxs-lookup"><span data-stu-id="7a0df-132">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="7a0df-133">Ange adressinformationen.</span><span class="sxs-lookup"><span data-stu-id="7a0df-133">Enter the address details.</span></span> <span data-ttu-id="7a0df-134">Landet/regionen som du har valt bestämmer vilka fält som du presenteras tillsammans med, vilket motsvarar adressformatet för landet/regionen.</span><span class="sxs-lookup"><span data-stu-id="7a0df-134">The country/region that you selected will determine the fields you are presented with, corresponding to the address format for the country/region.</span></span>   
6. <span data-ttu-id="7a0df-135">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="7a0df-135">Click OK.</span></span>

## <a name="add-contact-information"></a><span data-ttu-id="7a0df-136">Lägg till kontaktinformation</span><span class="sxs-lookup"><span data-stu-id="7a0df-136">Add contact information</span></span>
1. <span data-ttu-id="7a0df-137">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="7a0df-137">Click Add.</span></span>
2. <span data-ttu-id="7a0df-138">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="7a0df-138">In the Description field, type a value.</span></span>
3. <span data-ttu-id="7a0df-139">Välj ett alternativ i fältet Typ.</span><span class="sxs-lookup"><span data-stu-id="7a0df-139">In the Type field, select an option.</span></span>
4. <span data-ttu-id="7a0df-140">Skriv ett värde i fältet Kontaktens nummer/adress.</span><span class="sxs-lookup"><span data-stu-id="7a0df-140">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="7a0df-141">Du kan markera den kryssrutan Primär om detta är den primära kontakten.</span><span class="sxs-lookup"><span data-stu-id="7a0df-141">You can select the Primary check box if this is the primary contact.</span></span>  
5. <span data-ttu-id="7a0df-142">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="7a0df-142">Click Save.</span></span>
6. <span data-ttu-id="7a0df-143">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7a0df-143">Close the page.</span></span>
7. <span data-ttu-id="7a0df-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="7a0df-144">Close the page.</span></span>

