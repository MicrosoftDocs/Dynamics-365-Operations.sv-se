--- 
title: "Skapa och anskaffa tillgångar från leverantörsreskontra"
description: "Den här uppgifthandboken går igenom skapande och anskaffning av en anläggningstillgång med inköpsprocessen."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: e6c36338cc67855c79ec97d88bb8b633417b85c7
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="create-and-acquire-assets-from-accounts-payable"></a><span data-ttu-id="7fae8-103">Skapa och anskaffa tillgångar från leverantörsreskontra</span><span class="sxs-lookup"><span data-stu-id="7fae8-103">Create and acquire assets from Accounts payable</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7fae8-104">Den här uppgifthandboken går igenom skapande och anskaffning av en anläggningstillgång med inköpsprocessen.</span><span class="sxs-lookup"><span data-stu-id="7fae8-104">This task guide will walk through creation and acquisition of a fixed asset with the purchasing process.</span></span>  <span data-ttu-id="7fae8-105">Här används redovisnings- och leverantörsreskontraansvariga och demonstrationföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="7fae8-105">It uses the Accountant and Accounts payable clerks and the demo company USMF .</span></span>


## <a name="set-fixed-assets-parameters"></a><span data-ttu-id="7fae8-106">Ange parametrar för anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="7fae8-106">Set Fixed assets parameters</span></span>
1. <span data-ttu-id="7fae8-107">Gå till Anläggningstillgångar > Inställning > Parametrar för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="7fae8-107">Go to Fixed assets > Setup > Fixed assets parameters.</span></span>
2. <span data-ttu-id="7fae8-108">Utöka eller komprimera avsnittet Inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="7fae8-108">Expand or collapse the Purchase orders section.</span></span>
3. <span data-ttu-id="7fae8-109">Markera kryssrutan Tillåt förvärv av tillgångar från inköp.</span><span class="sxs-lookup"><span data-stu-id="7fae8-109">Check the Allow asset acquisition from Purchasing checkbox.</span></span>
4. <span data-ttu-id="7fae8-110">Markera kryssrutan Skapa tillgång under bokföring av produktinleverans eller faktura.</span><span class="sxs-lookup"><span data-stu-id="7fae8-110">Check the Create asset during product receipt or invoice posting checkbox.</span></span>

## <a name="create-a-new-vendor-invoice"></a><span data-ttu-id="7fae8-111">Skapa en ny leverantörsfaktura</span><span class="sxs-lookup"><span data-stu-id="7fae8-111">Create a new vendor invoice</span></span>
1. <span data-ttu-id="7fae8-112">Gå till Leverantörsreskontra > Arbetsytor > Leverantörsfakturaregistrering.</span><span class="sxs-lookup"><span data-stu-id="7fae8-112">Go to Accounts payable > Workspaces > Vendor invoice entry.</span></span>
2. <span data-ttu-id="7fae8-113">Klicka på Ny leverantörsfaktura.</span><span class="sxs-lookup"><span data-stu-id="7fae8-113">Click New vendor invoice.</span></span>
3. <span data-ttu-id="7fae8-114">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Fakturakonto.</span><span class="sxs-lookup"><span data-stu-id="7fae8-114">In the Invoice account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="7fae8-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7fae8-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="7fae8-116">Ange ett värde i fältet Antal.</span><span class="sxs-lookup"><span data-stu-id="7fae8-116">In the Number field, type a value.</span></span>
6. <span data-ttu-id="7fae8-117">Ange ett datum i fältet Bokföringsdatum.</span><span class="sxs-lookup"><span data-stu-id="7fae8-117">In the Posting date field, enter a date.</span></span>
7. <span data-ttu-id="7fae8-118">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="7fae8-118">Click Add line.</span></span>
8. <span data-ttu-id="7fae8-119">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="7fae8-119">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="7fae8-120">Antingen icke-lagerförda artiklar eller anskaffningkategorier kan användas för anskaffning av anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="7fae8-120">Either non-stocked items or procurement categories can be used for fixed asset acquisition.</span></span>  
9. <span data-ttu-id="7fae8-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7fae8-121">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="7fae8-122">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="7fae8-122">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="7fae8-123">En fakturarad skapar bara en anläggningstillgång, oberoende av kvantitet.</span><span class="sxs-lookup"><span data-stu-id="7fae8-123">One invoice line will only create one fixed asset, regardless of quantity.</span></span>  <span data-ttu-id="7fae8-124">Fakturakvantitetsfältet överförs till anläggningstillgångskvantiteten.</span><span class="sxs-lookup"><span data-stu-id="7fae8-124">The invoice quantity field value will be transferred to the fixed asset quantity.</span></span>  
11. <span data-ttu-id="7fae8-125">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="7fae8-125">In the Unit price field, enter a number.</span></span>
12. <span data-ttu-id="7fae8-126">Expandera eller dölj avsnittet Raddetaljer.</span><span class="sxs-lookup"><span data-stu-id="7fae8-126">Expand or collapse the Line details section.</span></span>
13. <span data-ttu-id="7fae8-127">Klicka på anläggningstillgångsfliken.</span><span class="sxs-lookup"><span data-stu-id="7fae8-127">Click the Fixed assets tab.</span></span>
14. <span data-ttu-id="7fae8-128">Markera kryssrutan Skapa en ny anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="7fae8-128">Check the Create a new fixed asset checkbox.</span></span>
15. <span data-ttu-id="7fae8-129">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Anläggningstillgångsgrupp.</span><span class="sxs-lookup"><span data-stu-id="7fae8-129">In the Fixed asset group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="7fae8-130">Välj den anläggningstillgångsgrupp som ska användas när du skapar den nya anläggningstillgången i listan.</span><span class="sxs-lookup"><span data-stu-id="7fae8-130">In the list, select the fixed asset group to be used when creating the new fixed asset.</span></span>
17. <span data-ttu-id="7fae8-131">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="7fae8-131">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="7fae8-132">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="7fae8-132">Click Post.</span></span>
    * <span data-ttu-id="7fae8-133">Anläggningstillgången skapas och förvärvas när fakturan bokförs.</span><span class="sxs-lookup"><span data-stu-id="7fae8-133">The fixed asset will be created and acquired when the invoice is posted.</span></span>  


