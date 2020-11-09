---
title: Skapa ett leverantörskonto
description: I den här proceduren visas hur du skapar ett leverantörskonto och lägger till en adress och kontaktinformation.
author: mkirknel
manager: tfehr
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd8cd2bb7b03c0415a5c5656f0e3ffada961973e
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017217"
---
# <a name="create-a-vendor-account"></a><span data-ttu-id="8422c-103">Skapa ett leverantörskonto</span><span class="sxs-lookup"><span data-stu-id="8422c-103">Create a vendor account</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8422c-104">I den här proceduren visas hur du skapar ett leverantörskonto och lägger till en adress och kontaktinformation.</span><span class="sxs-lookup"><span data-stu-id="8422c-104">This procedure shows how to create a vendor account, and add an address and contact information.</span></span> <span data-ttu-id="8422c-105">I proceduren visas inte hur du fyller i alla fält i inköpssyfte och ekonomiska syften.</span><span class="sxs-lookup"><span data-stu-id="8422c-105">The procedure does not show how to populate all fields for purchasing and financial purposes.</span></span> <span data-ttu-id="8422c-106">Läs fältbeskrivningarna om du vill veta mer om dessa fält.</span><span class="sxs-lookup"><span data-stu-id="8422c-106">To learn more about those fields, please read the field descriptions.</span></span> <span data-ttu-id="8422c-107">Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="8422c-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="8422c-108">Leverantörkonton skapas vanligtvis av ett anskaffningsproffs eller en kundreskontrapersonal.</span><span class="sxs-lookup"><span data-stu-id="8422c-108">Vendor accounts are typically created by a procurement professional or accounts receivable personnel.</span></span>


## <a name="create-a-vendor-account"></a><span data-ttu-id="8422c-109">Skapa ett leverantörskonto</span><span class="sxs-lookup"><span data-stu-id="8422c-109">Create a vendor account</span></span>
1. <span data-ttu-id="8422c-110">Gå till **navigeringsfönstret > Moduler > Anskaffning och källa > Leverantörer > Alla leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="8422c-110">Go to **Navigation pane > Modules > Procurement and sourcing > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="8422c-111">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="8422c-111">Click **New**.</span></span>
3. <span data-ttu-id="8422c-112">I fältet **Leverantörskonto** , skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="8422c-112">In the **Vendor account** field, type a value.</span></span>
    - <span data-ttu-id="8422c-113">Värdet kan fyllas i automatiskt.</span><span class="sxs-lookup"><span data-stu-id="8422c-113">The value may be populated automatically.</span></span> <span data-ttu-id="8422c-114">Om det gör det kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="8422c-114">If so, you can skip this step.</span></span>  
    - <span data-ttu-id="8422c-115">Du kan skapa leverantörskonton för en person eller en organisation.</span><span class="sxs-lookup"><span data-stu-id="8422c-115">You can create vendor accounts for a person or organization.</span></span> <span data-ttu-id="8422c-116">Detta påverkar vilka fält som är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="8422c-116">This will affect which fields are available.</span></span> <span data-ttu-id="8422c-117">I det här exemplet ska du skapa ett leverantörskonto för en organisation.</span><span class="sxs-lookup"><span data-stu-id="8422c-117">In this example, we'll create a vendor account for an organization.</span></span>   
4. <span data-ttu-id="8422c-118">I fältet **Namn** anger eller väljer du ett värde.</span><span class="sxs-lookup"><span data-stu-id="8422c-118">In the **Name** field, enter or select a value.</span></span> <span data-ttu-id="8422c-119">Om leverantören är en redan registrerad part i systemet kan du använda listrutan och välja honom/henne i det här fältet, så ärver det nya leverantörskontot den adress och kontaktinformation som redan är registrerad.</span><span class="sxs-lookup"><span data-stu-id="8422c-119">If your vendor is an already a registered party in your system you can use drop down and select them in this field and the new vendor account will inherit the address and contact information that's already registered.</span></span>
5. <span data-ttu-id="8422c-120">Ange eller välj ett värde i fältet **Grupp**.</span><span class="sxs-lookup"><span data-stu-id="8422c-120">In the **Group** field, enter or select a value.</span></span> <span data-ttu-id="8422c-121">Leverantörsgruppen används för att gruppera leverantörer som har någon av följande parametrar gemensamt: Betalningsvillkor, kvittningsperiod, huvudbokskonton för lagerbokföring inklusive momsgruppen, standardhuvudbokskonton, produktfilterkoder och leveransprognoskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="8422c-121">The vendor group is used to group vendors that have any of the following parameters in common: Terms of payment, settle period, inventory posting ledger accounts – including the sales tax group, default ledger accounts, product filter codes, or supply forecast configuration.</span></span>
6. <span data-ttu-id="8422c-122">Ange ett antal i fältet **Antal medarbetare**.</span><span class="sxs-lookup"><span data-stu-id="8422c-122">In the **Number of employees** field, enter a number.</span></span>
7. <span data-ttu-id="8422c-123">Skriv ett värde i fältet **Organisationsnummer**.</span><span class="sxs-lookup"><span data-stu-id="8422c-123">In the **Organization number** field, type a value.</span></span>

## <a name="add-an-address"></a><span data-ttu-id="8422c-124">Lägg till en adress</span><span class="sxs-lookup"><span data-stu-id="8422c-124">Add an address</span></span>
1. <span data-ttu-id="8422c-125">Expandera avsnittet **Adresser**.</span><span class="sxs-lookup"><span data-stu-id="8422c-125">Expand the **Addresses** section.</span></span>
2. <span data-ttu-id="8422c-126">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="8422c-126">Click **Add**.</span></span>
3. <span data-ttu-id="8422c-127">Ange eller välj ett värde i fältet **Syfte**.</span><span class="sxs-lookup"><span data-stu-id="8422c-127">In the **Purpose** field, enter or select a value.</span></span> <span data-ttu-id="8422c-128">Du kan välja en eller flera syften.</span><span class="sxs-lookup"><span data-stu-id="8422c-128">You can select one or more purposes.</span></span> <span data-ttu-id="8422c-129">Dessa används för att välja korrekt adress för ett visst syfte.</span><span class="sxs-lookup"><span data-stu-id="8422c-129">These are used to select the correct address for a given purpose.</span></span> <span data-ttu-id="8422c-130">Om syftet t.ex. är "Faktura" kommer den adressen att användas när du skickar fakturor.</span><span class="sxs-lookup"><span data-stu-id="8422c-130">For example, if the purpose is "Invoice" that address will be used when you send invoices.</span></span>
4. <span data-ttu-id="8422c-131">Skriv ett värde i fältet **Namn eller beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="8422c-131">In the **Name or description** field, type a value.</span></span>
5. <span data-ttu-id="8422c-132">Ange eller välj ett värde i fältet **Land/region**.</span><span class="sxs-lookup"><span data-stu-id="8422c-132">In the **Country/region** field, enter or select a value.</span></span> <span data-ttu-id="8422c-133">Ange adressinformationen.</span><span class="sxs-lookup"><span data-stu-id="8422c-133">Enter the address details.</span></span> <span data-ttu-id="8422c-134">Landet/regionen som du har valt bestämmer vilka fält som du presenteras tillsammans med, vilket motsvarar adressformatet för landet/regionen.</span><span class="sxs-lookup"><span data-stu-id="8422c-134">The country/region that you selected will determine the fields you are presented with, corresponding to the address format for the country/region.</span></span> 
6. <span data-ttu-id="8422c-135">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="8422c-135">Click **OK**.</span></span>

## <a name="add-contact-information"></a><span data-ttu-id="8422c-136">Lägg till kontaktinformation</span><span class="sxs-lookup"><span data-stu-id="8422c-136">Add contact information</span></span>
1. <span data-ttu-id="8422c-137">Expandera avsnittet **Kontaktinformation.**</span><span class="sxs-lookup"><span data-stu-id="8422c-137">Expand the **Contact information** section.</span></span>
2. <span data-ttu-id="8422c-138">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="8422c-138">Click **Add**.</span></span>
3. <span data-ttu-id="8422c-139">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="8422c-139">In the **Description** field, type a value.</span></span>
4. <span data-ttu-id="8422c-140">Välj ett alternativ i fältet **Typ**.</span><span class="sxs-lookup"><span data-stu-id="8422c-140">In the **Type** field, select an option.</span></span>
5. <span data-ttu-id="8422c-141">Skriv ett värde i fältet **Kontaktens nummer/adress**.</span><span class="sxs-lookup"><span data-stu-id="8422c-141">In the **Contact number/address** field, type a value.</span></span> <span data-ttu-id="8422c-142">Du kan markera den kryssrutan Primär om detta är den primära kontakten.</span><span class="sxs-lookup"><span data-stu-id="8422c-142">You can select the Primary check box if this is the primary contact.</span></span>  
6. <span data-ttu-id="8422c-143">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8422c-143">Click **Save**.</span></span>
7. <span data-ttu-id="8422c-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8422c-144">Close the page.</span></span>
8. <span data-ttu-id="8422c-145">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="8422c-145">Close the page.</span></span>

