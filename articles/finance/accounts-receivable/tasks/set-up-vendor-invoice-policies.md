---
title: Ställ in leverantörsfakturapolicyer
description: Det här avsnittet innehåller information om hur du ställer in leverantörsfakturapolicyer.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 58518f5291b70c63506c20717034daff0268901b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4448026"
---
# <a name="set-up-vendor-invoice-policies"></a><span data-ttu-id="576bb-103">Ställ in leverantörsfakturapolicyer</span><span class="sxs-lookup"><span data-stu-id="576bb-103">Set up vendor invoice policies</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="576bb-104">Det här avsnittet innehåller information om hur du ställer in leverantörsfakturapolicyer.</span><span class="sxs-lookup"><span data-stu-id="576bb-104">This topic explains how to set up vendor invoice policies.</span></span> <span data-ttu-id="576bb-105">Leverantörsfakturapolicyer körs när du bokför en leverantörsfaktur genom att använda leverantörsfakturasidan, och när du öppnar sidan för brott mot leverantörsfakturapolicyn.</span><span class="sxs-lookup"><span data-stu-id="576bb-105">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="576bb-106">Du kan även konfigurera leverantörsfakturaarbetsflödet om du vill köra leverantörsfakturapolicyer varje gång som du skickar in en faktura till arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="576bb-106">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

- <span data-ttu-id="576bb-107">Leverantörsfakturapolicyer gäller inte för fakturor som har skapats i ankomstregistreringen eller fakturajournalen.</span><span class="sxs-lookup"><span data-stu-id="576bb-107">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span>  
- <span data-ttu-id="576bb-108">Fakturamatchningsvalidering använder inte leverantörsfakturapolicyer, utan ställs in på sidan med leverantörsreskontraparametrar.</span><span class="sxs-lookup"><span data-stu-id="576bb-108">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>  
- <span data-ttu-id="576bb-109">I den här registreringen används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="576bb-109">This recording uses the USMF demo company.</span></span> <span data-ttu-id="576bb-110">Leverantörsreskontrachefsrollen eller redovisningschefsrollen ska utföra stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="576bb-110">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="576bb-111">Innan du börjar kontrollerar du att konfigurationsnyckeln för fakturamatchning har valts.</span><span class="sxs-lookup"><span data-stu-id="576bb-111">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="576bb-112">Förbered för att skapa leverantörsfakturapolicyer</span><span class="sxs-lookup"><span data-stu-id="576bb-112">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="576bb-113">Gå till **Navigeringsfönster > Moduler > Leverantörsreskontra > Inställningar > Parametrar för leverantörsreskontra**.</span><span class="sxs-lookup"><span data-stu-id="576bb-113">Go to **Navigation pane > Modules > Accounts payable > Setup > Accounts payable parameters**.</span></span>
2. <span data-ttu-id="576bb-114">Välj fliken **Fakturavalidering**</span><span class="sxs-lookup"><span data-stu-id="576bb-114">Select the **Invoice validation** tab.</span></span>
3. <span data-ttu-id="576bb-115">Markera eller avmarkera kryssrutan **Uppdatera status för fakturahuvud automatiskt**.</span><span class="sxs-lookup"><span data-stu-id="576bb-115">Select or clear the **Automatically update invoice header** status check box.</span></span>
4. <span data-ttu-id="576bb-116">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="576bb-116">Select **OK**.</span></span>
5. <span data-ttu-id="576bb-117">Välj ett alternativ i fältet **Bokför faktura med avvikelser**.</span><span class="sxs-lookup"><span data-stu-id="576bb-117">In the **Post invoice with discrepancies** field, select an option.</span></span>
6. <span data-ttu-id="576bb-118">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="576bb-118">Close the page.</span></span>
7. <span data-ttu-id="576bb-119">Gå till **Navigeringsfönster > Moduler > Leverantörsreskontra > Policyinställningar > Leverantörsfakturapolicyer**.</span><span class="sxs-lookup"><span data-stu-id="576bb-119">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
8. <span data-ttu-id="576bb-120">Välj **parametrar**.</span><span class="sxs-lookup"><span data-stu-id="576bb-120">Select **Parameters**.</span></span>
9. <span data-ttu-id="576bb-121">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="576bb-121">Select **Add**.</span></span>
10. <span data-ttu-id="576bb-122">Stäng sidan om du vill gå tillbaka till startsidan.</span><span class="sxs-lookup"><span data-stu-id="576bb-122">Close the page to return to the home page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="576bb-123">Skapa policyregeltyper för leverantörsfakturor</span><span class="sxs-lookup"><span data-stu-id="576bb-123">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="576bb-124">Gå till **Navigeringsfönster > Moduler > Leverantörsreskontra > Policyinställningar > Policyregeltyper för leverantörsfaktura**.</span><span class="sxs-lookup"><span data-stu-id="576bb-124">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policy rule types**.</span></span>
2. <span data-ttu-id="576bb-125">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="576bb-125">Select **New**.</span></span>
3. <span data-ttu-id="576bb-126">Ange värden i fälten **Regelnamn** och **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="576bb-126">In the **Rule name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="576bb-127">I fältet **frågenamn** väljer du den nedrullningsbara knappen för att öppna sökningen och väljer sedan önskad post.</span><span class="sxs-lookup"><span data-stu-id="576bb-127">In the **Query name** field, select the drop-down button to open the lookup, then select the desired record.</span></span>
5. <span data-ttu-id="576bb-128">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="576bb-128">Select **Save**.</span></span>
6. <span data-ttu-id="576bb-129">Stäng sidan om du vill gå tillbaka till startsidan.</span><span class="sxs-lookup"><span data-stu-id="576bb-129">Close the page to return to the home page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="576bb-130">Definiera en leverantörsfakturapolicy</span><span class="sxs-lookup"><span data-stu-id="576bb-130">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="576bb-131">Gå till **Navigeringsfönster > Moduler > Leverantörsreskontra > Policyinställningar > Leverantörsfakturapolicyer**.</span><span class="sxs-lookup"><span data-stu-id="576bb-131">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
2. <span data-ttu-id="576bb-132">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="576bb-132">Select **New**.</span></span>
3. <span data-ttu-id="576bb-133">Ange värden i fälten **Namn** och **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="576bb-133">In the **Name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="576bb-134">Expandera eller komprimera avsnittet **Policyorganisationer**.</span><span class="sxs-lookup"><span data-stu-id="576bb-134">Expand or collapse the **Policy organizations** section.</span></span>
5. <span data-ttu-id="576bb-135">I trädet, välj **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="576bb-135">In the tree, select **Contoso Entertainment System USA**.</span></span>
6. <span data-ttu-id="576bb-136">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="576bb-136">Select **Add**.</span></span>
7. <span data-ttu-id="576bb-137">Expandera eller komprimera avsnittet **Policyregler**.</span><span class="sxs-lookup"><span data-stu-id="576bb-137">Expand or collapse the **Policy rules** section.</span></span>
8. <span data-ttu-id="576bb-138">Välj **Skapa policyregel**.</span><span class="sxs-lookup"><span data-stu-id="576bb-138">Select **Create policy rule**.</span></span>
9. <span data-ttu-id="576bb-139">Skriv ett värde i fältet **Beskrivning av policyregel**.</span><span class="sxs-lookup"><span data-stu-id="576bb-139">In the **Policy rule description** field, type a value.</span></span>
10. <span data-ttu-id="576bb-140">Välj **filter**.</span><span class="sxs-lookup"><span data-stu-id="576bb-140">Select **Filter**.</span></span>
11. <span data-ttu-id="576bb-141">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="576bb-141">Select **Add**.</span></span> <span data-ttu-id="576bb-142">Välj önskad post.</span><span class="sxs-lookup"><span data-stu-id="576bb-142">Select the desired record.</span></span>
12. <span data-ttu-id="576bb-143">I fälten **Tabell**, **Härlett register** och **Fält** väljer du eller anger alternativ från listrutemenyer.</span><span class="sxs-lookup"><span data-stu-id="576bb-143">In the **Table**, **Derived table**, and **Field** fields, select or enter options from the drop-down menus.</span></span>
13. <span data-ttu-id="576bb-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="576bb-144">Close the page.</span></span>
14. <span data-ttu-id="576bb-145">I fältet **Kriterier** skriver du ett värde.</span><span class="sxs-lookup"><span data-stu-id="576bb-145">In the **Criteria** field, type a value.</span></span>
15. <span data-ttu-id="576bb-146">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="576bb-146">Select **OK**.</span></span>
16. <span data-ttu-id="576bb-147">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="576bb-147">Select **OK**.</span></span>
17. <span data-ttu-id="576bb-148">Stäng sidorna om du vill gå tillbaka till startsidan.</span><span class="sxs-lookup"><span data-stu-id="576bb-148">Close the pages to return to the home page.</span></span>

