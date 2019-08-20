---
title: Godkänn leverantörer för specifika anskaffningskategorier
description: När en inköpsrekvisition har skapats, kan det finnas krav på att välja en godkänd eller prioriterad leverantör beroende på hur inköpspolicyerna ställs in.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eec50e2e8f08fabb64f89c17159b97ba770026f8
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1836352"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a><span data-ttu-id="aa40f-103">Godkänn leverantörer för specifika anskaffningskategorier</span><span class="sxs-lookup"><span data-stu-id="aa40f-103">Approve vendors for specific procurement categories</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="aa40f-104">När en inköpsrekvisition har skapats, kan det finnas krav på att välja en godkänd eller prioriterad leverantör beroende på hur inköpspolicyerna ställs in.</span><span class="sxs-lookup"><span data-stu-id="aa40f-104">When a purchase requisition is created, there may be a requirement to select an approved or preferred vendor, depending on how the purchasing policies are set up.</span></span> <span data-ttu-id="aa40f-105">Den här proceduren visar hur du anger att en leverantör är godkänd eller föredras för en viss anskaffningkategori.</span><span class="sxs-lookup"><span data-stu-id="aa40f-105">This procedure shows you how to specify that a vendor is approved or preferred for a specific procurement category.</span></span> <span data-ttu-id="aa40f-106">Den här uppgiften utförs vanligtvis av ett anskaffningsproffs.</span><span class="sxs-lookup"><span data-stu-id="aa40f-106">This task would usually be carried out by a procurement professional.</span></span> <span data-ttu-id="aa40f-107">Du kan köra den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="aa40f-107">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="aa40f-108">Gå till Anskaffning och källa > Leverantörer > Alla leverantörer.</span><span class="sxs-lookup"><span data-stu-id="aa40f-108">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="aa40f-109">Markera leverantören som du vill ange som godkänd eller prioriterad leverantör för en kategori.</span><span class="sxs-lookup"><span data-stu-id="aa40f-109">Select the vendor that you want to set as an approved or preferred vendor for a category.</span></span>
3. <span data-ttu-id="aa40f-110">Klicka på Allmänt i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="aa40f-110">On the Action Pane, click General.</span></span>
4. <span data-ttu-id="aa40f-111">Klicka på kategorier.</span><span class="sxs-lookup"><span data-stu-id="aa40f-111">Click Categories.</span></span>
5. <span data-ttu-id="aa40f-112">Klicka på Lägg till kategori.</span><span class="sxs-lookup"><span data-stu-id="aa40f-112">Click Add category.</span></span>
6. <span data-ttu-id="aa40f-113">I fältet Kategori väljer du KONTORS- OCH SKRIVBORDSTILLBEHÖR (KONTORS- OCH SKRIVBORDDTILLBEHÖR).</span><span class="sxs-lookup"><span data-stu-id="aa40f-113">In the Category field, select OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES).</span></span>
7. <span data-ttu-id="aa40f-114">I fältet Leverantörkategoristatus väljer du "Föredragen".</span><span class="sxs-lookup"><span data-stu-id="aa40f-114">In the Vendor category status field, select 'Preferred'.</span></span>
    * <span data-ttu-id="aa40f-115">Det är möjligt att ange mer än en prioriterad leverantör för en kategori.</span><span class="sxs-lookup"><span data-stu-id="aa40f-115">It’s possible to specify more than one preferred vendor for a category.</span></span>  
8. <span data-ttu-id="aa40f-116">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="aa40f-116">Click Save.</span></span>
9. <span data-ttu-id="aa40f-117">Gå till Anskaffning och källa > Anskaffningskategorier.</span><span class="sxs-lookup"><span data-stu-id="aa40f-117">Go to Procurement and sourcing > Procurement categories.</span></span>
10. <span data-ttu-id="aa40f-118">Välj "ANSKAFFNINGSKATEGORIER FÖR FÖRETAG\KONTORS- OCH SKRIVBORDSTILLBEHÖR" i trädet.</span><span class="sxs-lookup"><span data-stu-id="aa40f-118">In the tree, select 'CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES'.</span></span>
11. <span data-ttu-id="aa40f-119">Visa avsnittet Leverantörer.</span><span class="sxs-lookup"><span data-stu-id="aa40f-119">Expand the Vendors section.</span></span>
    * <span data-ttu-id="aa40f-120">Kontrollera om leverantören som du valde, visas som en prioriterad leverantör för kategorin Kontor- och skrivbordtillbehör.</span><span class="sxs-lookup"><span data-stu-id="aa40f-120">Check if the vendor that you selected  appears as a preferred vendor for the Office and desk accessories category.</span></span> <span data-ttu-id="aa40f-121">Om du kör den här proceduren som en uppgiftsguide måste du eventuellt klicka på fliken Lås upp för att kunna bläddra nedåt i listan över leverantörer.</span><span class="sxs-lookup"><span data-stu-id="aa40f-121">If you’re running this procedure as a task guide, you may have to click the Unlock button to be able to scroll down to the list of vendors.</span></span>  <span data-ttu-id="aa40f-122">Det går också att lägga till prioriterade och godkända leverantörer på det här sidan.</span><span class="sxs-lookup"><span data-stu-id="aa40f-122">It’s also possible to add preferred and approved vendors on this page.</span></span>  
12. <span data-ttu-id="aa40f-123">Expandera "KONTORS- OCH SKRIVBORDSTILLBEHÖR" i trädet.</span><span class="sxs-lookup"><span data-stu-id="aa40f-123">In the tree, expand 'OFFICE AND DESK ACCESSORIES'.</span></span>
13. <span data-ttu-id="aa40f-124">Välj "Saxar" i trädet. </span><span class="sxs-lookup"><span data-stu-id="aa40f-124">In the tree, select 'Scissors'.</span></span>
14. <span data-ttu-id="aa40f-125">Välj Nej i fältet Ärv leverantörer från överordnad kategori.</span><span class="sxs-lookup"><span data-stu-id="aa40f-125">Select No in the Inherit vendors from parent category: field.</span></span>
15. <span data-ttu-id="aa40f-126">Välj Ja i fältet Ärv leverantörer från överordnad kategori.</span><span class="sxs-lookup"><span data-stu-id="aa40f-126">Select Yes in the Inherit vendors from parent category: field.</span></span>

