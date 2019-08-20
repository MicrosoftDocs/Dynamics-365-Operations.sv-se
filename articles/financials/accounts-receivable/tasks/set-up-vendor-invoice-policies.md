---
title: Ställ in leverantörsfakturapolicyer
description: Det här avsnittet förklarar hur du ställer in policyer för leverantörsfaktura i Dynamics 365 for Finance and Operations.
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
ms.openlocfilehash: 328aafd16496fdbb963c9aa40a5c13005be7a382
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842819"
---
# <a name="set-up-vendor-invoice-policies"></a><span data-ttu-id="e87b4-103">Ställ in leverantörsfakturapolicyer</span><span class="sxs-lookup"><span data-stu-id="e87b4-103">Set up vendor invoice policies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e87b4-104">Det här avsnittet förklarar hur du ställer in policyer för leverantörsfaktura i Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e87b4-104">This topic explains how to set up vendor invoice policies in Dynamics 365 for Finance and Operatoins.</span></span> <span data-ttu-id="e87b4-105">Leverantörsfakturapolicyer körs när du bokför en leverantörsfaktur genom att använda leverantörsfakturasidan, och när du öppnar sidan för brott mot leverantörsfakturapolicyn.</span><span class="sxs-lookup"><span data-stu-id="e87b4-105">Vendor invoice policies are run when you post a vendor invoice by using the Vendor invoice page and when you open the vendor invoice Policy violations page.</span></span> <span data-ttu-id="e87b4-106">Du kan även konfigurera leverantörsfakturaarbetsflödet om du vill köra leverantörsfakturapolicyer varje gång som du skickar in en faktura till arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="e87b4-106">You can also configure the vendor invoice workflow to run vendor invoice policies every time that you submit an invoice to workflow.</span></span> 

- <span data-ttu-id="e87b4-107">Leverantörsfakturapolicyer gäller inte för fakturor som har skapats i ankomstregistreringen eller fakturajournalen.</span><span class="sxs-lookup"><span data-stu-id="e87b4-107">Vendor invoice policies do not apply to invoices that were created in the invoice register or invoice journal.</span></span>  
- <span data-ttu-id="e87b4-108">Fakturamatchningsvalidering använder inte leverantörsfakturapolicyer, utan ställs in på sidan med leverantörsreskontraparametrar.</span><span class="sxs-lookup"><span data-stu-id="e87b4-108">Invoice matching validation does not use vendor invoice policies, but is instead set up in the Accounts payable parameters page.</span></span>  
- <span data-ttu-id="e87b4-109">I den här registreringen används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="e87b4-109">This recording uses the USMF demo company.</span></span> <span data-ttu-id="e87b4-110">Leverantörsreskontrachefsrollen eller redovisningschefsrollen ska utföra stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="e87b4-110">The accounts payable manager or accounting manager role would perform these steps.</span></span> <span data-ttu-id="e87b4-111">Innan du börjar kontrollerar du att konfigurationsnyckeln för fakturamatchning har valts.</span><span class="sxs-lookup"><span data-stu-id="e87b4-111">Before you begin, make sure that the Invoice matching configuration key is selected.</span></span>


## <a name="prepare-to-create-vendor-invoice-policies"></a><span data-ttu-id="e87b4-112">Förbered för att skapa leverantörsfakturapolicyer</span><span class="sxs-lookup"><span data-stu-id="e87b4-112">Prepare to create vendor invoice policies</span></span>
1. <span data-ttu-id="e87b4-113">Gå till **Navigeringsfönster > Moduler > Leverantörsreskontra > Inställningar > Parametrar för leverantörsreskontra**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-113">Go to **Navigation pane > Modules > Accounts payable > Setup > Accounts payable parameters**.</span></span>
2. <span data-ttu-id="e87b4-114">Välj fliken **Fakturavalidering**</span><span class="sxs-lookup"><span data-stu-id="e87b4-114">Select the **Invoice validation** tab.</span></span>
3. <span data-ttu-id="e87b4-115">Markera eller avmarkera kryssrutan **Uppdatera status för fakturahuvud automatiskt**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-115">Select or clear the **Automatically update invoice header** status check box.</span></span>
4. <span data-ttu-id="e87b4-116">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-116">Select **OK**.</span></span>
5. <span data-ttu-id="e87b4-117">Välj ett alternativ i fältet **Bokför faktura med avvikelser**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-117">In the **Post invoice with discrepancies** field, select an option.</span></span>
6. <span data-ttu-id="e87b4-118">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e87b4-118">Close the page.</span></span>
7. <span data-ttu-id="e87b4-119">Gå till **Navigeringsfönster > Moduler > Leverantörsreskontra > Policyinställningar > Leverantörsfakturapolicyer**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-119">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
8. <span data-ttu-id="e87b4-120">Välj **parametrar**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-120">Select **Parameters**.</span></span>
9. <span data-ttu-id="e87b4-121">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-121">Select **Add**.</span></span>
10. <span data-ttu-id="e87b4-122">Stäng sidan om du vill gå tillbaka till startsidan.</span><span class="sxs-lookup"><span data-stu-id="e87b4-122">Close the page to return to the home page.</span></span>

## <a name="create-policy-rule-types-for-vendor-invoices"></a><span data-ttu-id="e87b4-123">Skapa policyregeltyper för leverantörsfakturor</span><span class="sxs-lookup"><span data-stu-id="e87b4-123">Create policy rule types for vendor invoices</span></span>
1. <span data-ttu-id="e87b4-124">Gå till **Navigeringsfönster > Moduler > Leverantörsreskontra > Policyinställningar > Policyregeltyper för leverantörsfaktura**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-124">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policy rule types**.</span></span>
2. <span data-ttu-id="e87b4-125">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-125">Select **New**.</span></span>
3. <span data-ttu-id="e87b4-126">Ange värden i fälten **Regelnamn** och **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-126">In the **Rule name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="e87b4-127">I fältet **frågenamn** väljer du den nedrullningsbara knappen för att öppna sökningen och väljer sedan önskad post.</span><span class="sxs-lookup"><span data-stu-id="e87b4-127">In the **Query name** field, select the drop-down button to open the lookup, then selec the desired record.</span></span>
5. <span data-ttu-id="e87b4-128">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-128">Select **Save**.</span></span>
6. <span data-ttu-id="e87b4-129">Stäng sidan om du vill gå tillbaka till startsidan.</span><span class="sxs-lookup"><span data-stu-id="e87b4-129">Close the page to return to the home page.</span></span>

## <a name="define-a-vendor-invoice-policy"></a><span data-ttu-id="e87b4-130">Definiera en leverantörsfakturapolicy</span><span class="sxs-lookup"><span data-stu-id="e87b4-130">Define a vendor invoice policy</span></span>
1. <span data-ttu-id="e87b4-131">Gå till **Navigeringsfönster > Moduler > Leverantörsreskontra > Policyinställningar > Leverantörsfakturapolicyer**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-131">Go to **Navigation pane > Modules > Accounts payable > Policy setup > Vendor invoice policies**.</span></span>
2. <span data-ttu-id="e87b4-132">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-132">Select **New**.</span></span>
3. <span data-ttu-id="e87b4-133">Ange värden i fälten **Namn** och **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-133">In the **Name** and **Description** fields, type values.</span></span>
4. <span data-ttu-id="e87b4-134">Expandera eller komprimera avsnittet **Policyorganisationer**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-134">Expand or collapse the **Policy organizations** section.</span></span>
5. <span data-ttu-id="e87b4-135">I trädet, välj **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-135">In the tree, select **Contoso Entertainment System USA**.</span></span>
6. <span data-ttu-id="e87b4-136">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-136">Select **Add**.</span></span>
7. <span data-ttu-id="e87b4-137">Expandera eller komprimera avsnittet **Policyregler**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-137">Expand or collapse the **Policy rules** section.</span></span>
8. <span data-ttu-id="e87b4-138">Välj **Skapa policyregel**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-138">Select **Create policy rule**.</span></span>
9. <span data-ttu-id="e87b4-139">Skriv ett värde i fältet **Beskrivning av policyregel**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-139">In the **Policy rule description** field, type a value.</span></span>
10. <span data-ttu-id="e87b4-140">Välj **filter**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-140">Select **Filter**.</span></span>
11. <span data-ttu-id="e87b4-141">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-141">Select **Add**.</span></span> <span data-ttu-id="e87b4-142">Välj önskad post.</span><span class="sxs-lookup"><span data-stu-id="e87b4-142">Select the desired record.</span></span>
12. <span data-ttu-id="e87b4-143">I fälten **Tabell**, **Härlett register** och **Fält** väljer du eller anger alternativ från listrutemenyer.</span><span class="sxs-lookup"><span data-stu-id="e87b4-143">In the **Table**, **Derived table**, and **Field** fields, select or enter options from the drop-down menus.</span></span>
13. <span data-ttu-id="e87b4-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e87b4-144">Close the page.</span></span>
14. <span data-ttu-id="e87b4-145">I fältet **Kriterier** skriver du ett värde.</span><span class="sxs-lookup"><span data-stu-id="e87b4-145">In the **Criteria** field, type a value.</span></span>
15. <span data-ttu-id="e87b4-146">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-146">Select **OK**.</span></span>
16. <span data-ttu-id="e87b4-147">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="e87b4-147">Select **OK**.</span></span>
17. <span data-ttu-id="e87b4-148">Stäng sidorna om du vill gå tillbaka till startsidan.</span><span class="sxs-lookup"><span data-stu-id="e87b4-148">Close the pages to return to the home page.</span></span>

