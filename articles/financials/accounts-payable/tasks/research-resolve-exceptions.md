--- 
title: "Undersöka eller lösa undantag"
description: "Leverantörsfakturapolicyer körs när du bokför en leverantörsfaktur genom att använda leverantörsfakturasidan, och när du öppnar sidan för brott mot leverantörsfakturapolicyn."
author: abruer
manager: AnnBe
ms.date: 02/16/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 6c191d0d5ad5c05ce3a9280bcca7c6916f0d963b
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="research-or-resolve-exceptions"></a><span data-ttu-id="45d5c-103">Undersöka eller lösa undantag</span><span class="sxs-lookup"><span data-stu-id="45d5c-103">Research or resolve exceptions</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="45d5c-104">Leverantörsfakturapolicyer körs när du bokför en leverantörsfaktur genom att använda leverantörsfakturasidan, och när du öppnar sidan för brott mot leverantörsfakturapolicyn.</span><span class="sxs-lookup"><span data-stu-id="45d5c-104">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="45d5c-105">Du kan även konfigurera leverantörsfakturaarbetsflödet om du vill köra leverantörsfakturapolicyer varje gång som du skickar in en faktura till arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="45d5c-105">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

<span data-ttu-id="45d5c-106">Leverantörsfakturapolicyer gäller inte för fakturor som har skapats i ankomstregistreringen eller fakturajournalen.</span><span class="sxs-lookup"><span data-stu-id="45d5c-106">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span> 

<span data-ttu-id="45d5c-107">Fakturamatchningsvalidering använder inte leverantörsfakturapolicyer, utan ställs in på sidan med leverantörsreskontraparametrar.</span><span class="sxs-lookup"><span data-stu-id="45d5c-107">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>

<span data-ttu-id="45d5c-108">I den här registreringen används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="45d5c-108">This recording uses the USMF demo company.</span></span> <span data-ttu-id="45d5c-109">Leverantörsreskontrachefsrollen eller redovisningschefsrollen ska utföra stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="45d5c-109">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="45d5c-110">Innan du börjar kontrollerar du att konfigurationsnyckeln för fakturamatchning har valts.</span><span class="sxs-lookup"><span data-stu-id="45d5c-110">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="45d5c-111">Förbered för att skapa leverantörsfakturapolicyer</span><span class="sxs-lookup"><span data-stu-id="45d5c-111">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="45d5c-112">Gå till Leverantörsreskontra > Inställningar > Parametrar för leverantörsreskontra.</span><span class="sxs-lookup"><span data-stu-id="45d5c-112">Go to Accounts payable > Setup > Accounts payable parameters.</span></span>
2. <span data-ttu-id="45d5c-113">Klicka på fliken Fakturavalidering.</span><span class="sxs-lookup"><span data-stu-id="45d5c-113">Click the Invoice validation tab.</span></span>
3. <span data-ttu-id="45d5c-114">Markera eller avmarkera kryssrutan Uppdatera status för fakturahuvud automatiskt.</span><span class="sxs-lookup"><span data-stu-id="45d5c-114">Select or clear the Automatically update invoice header status check box.</span></span>
4. <span data-ttu-id="45d5c-115">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="45d5c-115">Click OK.</span></span>
5. <span data-ttu-id="45d5c-116">Välj ett alternativ i fältet Bokför faktura med avvikelser.</span><span class="sxs-lookup"><span data-stu-id="45d5c-116">In the Post invoice with discrepancies field, select an option.</span></span>
6. <span data-ttu-id="45d5c-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="45d5c-117">Close the page.</span></span>
7. <span data-ttu-id="45d5c-118">Gå till Leverantörsreskontra > Policyinställningar > Leverantörsfakturapolicyer.</span><span class="sxs-lookup"><span data-stu-id="45d5c-118">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
8. <span data-ttu-id="45d5c-119">Klicka på Parametrar.</span><span class="sxs-lookup"><span data-stu-id="45d5c-119">Click Parameters.</span></span>
9. <span data-ttu-id="45d5c-120">Klicka på btnAdd.</span><span class="sxs-lookup"><span data-stu-id="45d5c-120">Click btnAdd.</span></span>
10. <span data-ttu-id="45d5c-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="45d5c-121">Close the page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="45d5c-122">Skapa policyregeltyper för leverantörsfakturor</span><span class="sxs-lookup"><span data-stu-id="45d5c-122">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="45d5c-123">Gå till Leverantörsreskontra > Policyinställningar > Policyregeltyper för leverantörsfaktura.</span><span class="sxs-lookup"><span data-stu-id="45d5c-123">Go to Accounts payable > Policy setup > Vendor invoice policy rule types.</span></span>
2. <span data-ttu-id="45d5c-124">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="45d5c-124">Click New.</span></span>
3. <span data-ttu-id="45d5c-125">I fältet Regelnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="45d5c-125">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="45d5c-126">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="45d5c-126">In the Description field, type a value.</span></span>
5. <span data-ttu-id="45d5c-127">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Frågenamn.</span><span class="sxs-lookup"><span data-stu-id="45d5c-127">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="45d5c-128">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="45d5c-128">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="45d5c-129">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="45d5c-129">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="45d5c-130">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="45d5c-130">Click Save.</span></span>
9. <span data-ttu-id="45d5c-131">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="45d5c-131">Close the page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="45d5c-132">Definiera en leverantörsfakturapolicy</span><span class="sxs-lookup"><span data-stu-id="45d5c-132">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="45d5c-133">Gå till Leverantörsreskontra > Policyinställningar > Leverantörsfakturapolicyer.</span><span class="sxs-lookup"><span data-stu-id="45d5c-133">Go to Accounts payable > Policy setup > Vendor invoice policies.</span></span>
2. <span data-ttu-id="45d5c-134">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="45d5c-134">Click New.</span></span>
3. <span data-ttu-id="45d5c-135">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="45d5c-135">In the Name field, type a value.</span></span>
4. <span data-ttu-id="45d5c-136">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="45d5c-136">In the Description field, type a value.</span></span>
5. <span data-ttu-id="45d5c-137">Expandera eller komprimera avsnittet Policyorganisationer.</span><span class="sxs-lookup"><span data-stu-id="45d5c-137">Expand or collapse the Policy organizations section.</span></span>
6. <span data-ttu-id="45d5c-138">Välj det ”Contoso Entertainment System USA" i trädet..</span><span class="sxs-lookup"><span data-stu-id="45d5c-138">In the tree, select 'Contoso Entertainment System USA'.</span></span>
7. <span data-ttu-id="45d5c-139">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="45d5c-139">Click Add.</span></span>
8. <span data-ttu-id="45d5c-140">Expandera eller komprimera avsnittet Policyregler.</span><span class="sxs-lookup"><span data-stu-id="45d5c-140">Expand or collapse the Policy rules section.</span></span>
9. <span data-ttu-id="45d5c-141">Klicka på Skapa policyregel.</span><span class="sxs-lookup"><span data-stu-id="45d5c-141">Click Create policy rule.</span></span>
10. <span data-ttu-id="45d5c-142">I fältet Policyregel, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="45d5c-142">In the Policy rule description field, type a value.</span></span>
11. <span data-ttu-id="45d5c-143">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="45d5c-143">Click Filter.</span></span>
12. <span data-ttu-id="45d5c-144">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="45d5c-144">Click Add.</span></span>
13. <span data-ttu-id="45d5c-145">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="45d5c-145">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="45d5c-146">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Register.</span><span class="sxs-lookup"><span data-stu-id="45d5c-146">In the Table field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="45d5c-147">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="45d5c-147">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="45d5c-148">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Härlett register.</span><span class="sxs-lookup"><span data-stu-id="45d5c-148">In the Derived table field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="45d5c-149">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="45d5c-149">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="45d5c-150">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Fält.</span><span class="sxs-lookup"><span data-stu-id="45d5c-150">In the Field field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="45d5c-151">Ange ett värde i fältet Fält.</span><span class="sxs-lookup"><span data-stu-id="45d5c-151">In the Field field, type a value.</span></span>
20. <span data-ttu-id="45d5c-152">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="45d5c-152">Close the page.</span></span>
21. <span data-ttu-id="45d5c-153">Ange ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="45d5c-153">In the Criteria field, type a value.</span></span>
22. <span data-ttu-id="45d5c-154">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="45d5c-154">Click OK.</span></span>
23. <span data-ttu-id="45d5c-155">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="45d5c-155">Click OK.</span></span>
24. <span data-ttu-id="45d5c-156">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="45d5c-156">Close the page.</span></span>
25. <span data-ttu-id="45d5c-157">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="45d5c-157">Close the page.</span></span>

