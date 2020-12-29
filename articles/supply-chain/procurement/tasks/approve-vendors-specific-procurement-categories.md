---
title: Godkänn leverantörer för specifika anskaffningskategorier
description: I det här avsnittet beskrivs hur du godkänner leverantörer för särskilda anskaffningskategorier i Dynamics 365 Supply Chain Management.
author: mkirknel
manager: tfehr
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e53102d732e9befcaca183adfd2a756c12e0162b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437613"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a><span data-ttu-id="d1c77-103">Godkänn leverantörer för specifika anskaffningskategorier</span><span class="sxs-lookup"><span data-stu-id="d1c77-103">Approve vendors for specific procurement categories</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d1c77-104">I det här avsnittet beskrivs hur du godkänner leverantörer för särskilda anskaffningskategorier i Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d1c77-104">This topic explains how to approve vendors for specific procurement categories in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="d1c77-105">När en inköpsrekvisition har skapats, kan det finnas krav på att välja en godkänd eller prioriterad leverantör beroende på hur inköpspolicyerna ställs in.</span><span class="sxs-lookup"><span data-stu-id="d1c77-105">When a purchase requisition is created, there may be a requirement to select an approved or preferred vendor, depending on how the purchasing policies are set up.</span></span> <span data-ttu-id="d1c77-106">Den här proceduren visar hur du anger att en leverantör är godkänd eller föredras för en viss anskaffningkategori.</span><span class="sxs-lookup"><span data-stu-id="d1c77-106">This procedure shows you how to specify that a vendor is approved or preferred for a specific procurement category.</span></span> <span data-ttu-id="d1c77-107">Den här uppgiften utförs vanligtvis av ett anskaffningsproffs.</span><span class="sxs-lookup"><span data-stu-id="d1c77-107">This task would usually be carried out by a procurement professional.</span></span> <span data-ttu-id="d1c77-108">Du kan köra den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="d1c77-108">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="d1c77-109">I navigeringsfönstret, gå till **Moduler > Anskaffning och källa > Leverantörer > Alla leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="d1c77-109">In the navigation pane, go to **Modules > Procurement and sourcing > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="d1c77-110">Markera leverantören som du vill ange som godkänd eller prioriterad leverantör för en kategori.</span><span class="sxs-lookup"><span data-stu-id="d1c77-110">Select the vendor that you want to set as an approved or preferred vendor for a category.</span></span>
3. <span data-ttu-id="d1c77-111">Välj **Allmänt** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d1c77-111">On the Action Pane, select **General**.</span></span>
4. <span data-ttu-id="d1c77-112">Välj **Kategorier**.</span><span class="sxs-lookup"><span data-stu-id="d1c77-112">Select **Categories**.</span></span>
5. <span data-ttu-id="d1c77-113">Välj **Lägg till kategori**.</span><span class="sxs-lookup"><span data-stu-id="d1c77-113">Select **Add category**.</span></span>
6. <span data-ttu-id="d1c77-114">I fältet **Kategori**, välj **KONTORS- OCH SKRIVBORDSTILLBEHÖR (OFFICE AND DESK ACCESSORIES)**.</span><span class="sxs-lookup"><span data-stu-id="d1c77-114">In the **Category** field, select **OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES)**.</span></span>
7. <span data-ttu-id="d1c77-115">I fältet **Leverantörkategoristatus** väljer du **Prioriterad**.</span><span class="sxs-lookup"><span data-stu-id="d1c77-115">In the **Vendor category status** field, select **Preferred**.</span></span> <span data-ttu-id="d1c77-116">Det är möjligt att ange mer än en prioriterad leverantör för en kategori.</span><span class="sxs-lookup"><span data-stu-id="d1c77-116">It's possible to specify more than one preferred vendor for a category.</span></span>  
8. <span data-ttu-id="d1c77-117">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d1c77-117">Select **Save**.</span></span>
9. <span data-ttu-id="d1c77-118">I navigeringsfönstret, gå till **Moduler > Anskaffning och källa > Anskaffningskategorier**.</span><span class="sxs-lookup"><span data-stu-id="d1c77-118">In the navigation pane, go to **Modules > Procurement and sourcing > Procurement categories**.</span></span>
10. <span data-ttu-id="d1c77-119">Välj **ANSKAFFNINGSKATEGORIER FÖR FÖRETAG\KONTORS- OCH SKRIVBORDSTILLBEHÖR** i trädet.</span><span class="sxs-lookup"><span data-stu-id="d1c77-119">In the tree, select **CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES**.</span></span>
11. <span data-ttu-id="d1c77-120">Expandera avsnittet **Leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="d1c77-120">Expand the **Vendors** section.</span></span> <span data-ttu-id="d1c77-121">Kontrollera om leverantören som du valde visas som en prioriterad leverantör för kategorin Kontor- och skrivbordstillbehör.</span><span class="sxs-lookup"><span data-stu-id="d1c77-121">Check if the vendor that you selected appears as a preferred vendor for the Office and desk accessories category.</span></span> <span data-ttu-id="d1c77-122">Om du kör den här proceduren som en uppgiftsguide måste du eventuellt välja knappen **Lås upp** för att kunna bläddra nedåt i listan över leverantörer.</span><span class="sxs-lookup"><span data-stu-id="d1c77-122">If you're running this procedure as a task guide, you may have to select the **Unlock** button to be able to scroll down to the list of vendors.</span></span>  <span data-ttu-id="d1c77-123">Det går också att lägga till prioriterade och godkända leverantörer på det här sidan.</span><span class="sxs-lookup"><span data-stu-id="d1c77-123">It's also possible to add preferred and approved vendors on this page.</span></span>  
12. <span data-ttu-id="d1c77-124">Expandera **KONTORS- OCH SKRIVBORDSTILLBEHÖR** i trädet och välj **Sax.**</span><span class="sxs-lookup"><span data-stu-id="d1c77-124">In the tree, expand **OFFICE AND DESK ACCESSORIES** and select **Scissors**.</span></span>
13. <span data-ttu-id="d1c77-125">Välj **Nej** i fältet **Ärv leverantörer från överordnad kategori:**.</span><span class="sxs-lookup"><span data-stu-id="d1c77-125">Select **No** in the **Inherit vendors from parent category:** field.</span></span>
14. <span data-ttu-id="d1c77-126">Välj **Ja** i fältet **Ärv leverantörer från överordnad kategori:**.</span><span class="sxs-lookup"><span data-stu-id="d1c77-126">Select **Yes** in the **Inherit vendors from parent category:** field.</span></span>

