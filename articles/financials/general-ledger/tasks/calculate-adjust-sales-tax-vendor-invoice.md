--- 
title: "Beräkna och justera moms på en leverantörsfaktura"
description: "Om det ursprungliga källdokumentet visar andra momsbelopp än dem som beräknas kan du justera dessa belopp, innan du bokför dem."
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 803c038d907b68a3c72a83a3e035c4e08b8a8661
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="b637d-103">Beräkna och justera moms på en leverantörsfaktura</span><span class="sxs-lookup"><span data-stu-id="b637d-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b637d-104">Om det ursprungliga källdokumentet visar andra momsbelopp än dem som beräknas kan du justera dessa belopp, innan du bokför dem.</span><span class="sxs-lookup"><span data-stu-id="b637d-104">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="b637d-105">I den här uppgiften används demonstrationsföretaget DEMF.</span><span class="sxs-lookup"><span data-stu-id="b637d-105">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="b637d-106">Gå till Leverantörsreskontra > Fakturor > Fakturajournal.</span><span class="sxs-lookup"><span data-stu-id="b637d-106">Go to Accounts payable > Invoices > Invoice journal.</span></span>
2. <span data-ttu-id="b637d-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b637d-107">Click New.</span></span>
3. <span data-ttu-id="b637d-108">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="b637d-108">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="b637d-109">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="b637d-109">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="b637d-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="b637d-110">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="b637d-111">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="b637d-111">Click Lines.</span></span>
7. <span data-ttu-id="b637d-112">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="b637d-112">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="b637d-113">Ange önskade värden i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="b637d-113">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="b637d-114">Ange ett värde i fältet Faktura.</span><span class="sxs-lookup"><span data-stu-id="b637d-114">In the Invoice field, type a value.</span></span>
10. <span data-ttu-id="b637d-115">Välj ett tal i fältet Kredit.</span><span class="sxs-lookup"><span data-stu-id="b637d-115">In the Credit field, enter a number.</span></span>
11. <span data-ttu-id="b637d-116">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="b637d-116">In the Offset account field, specify the desired values.</span></span>
12. <span data-ttu-id="b637d-117">Klicka på Moms.</span><span class="sxs-lookup"><span data-stu-id="b637d-117">Click Sales tax.</span></span>
13. <span data-ttu-id="b637d-118">Ange ett tal i fältet Totalt faktiskt momsbelopp.</span><span class="sxs-lookup"><span data-stu-id="b637d-118">In the Total actual sales tax amount field, enter a number.</span></span>
14. <span data-ttu-id="b637d-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="b637d-119">Click OK.</span></span>
15. <span data-ttu-id="b637d-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b637d-120">Click Save.</span></span>
16. <span data-ttu-id="b637d-121">Klicka på Moms.</span><span class="sxs-lookup"><span data-stu-id="b637d-121">Click Sales tax.</span></span>
17. <span data-ttu-id="b637d-122">På justeringsfliken kan momsbeloppen justeras per momskod.</span><span class="sxs-lookup"><span data-stu-id="b637d-122">On the Adjustment tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
18. <span data-ttu-id="b637d-123">Klicka på Återställ utfall till beräknade belopp.</span><span class="sxs-lookup"><span data-stu-id="b637d-123">Click Reset actual from calculated amounts.</span></span>
19. <span data-ttu-id="b637d-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="b637d-124">Click OK.</span></span>
20. <span data-ttu-id="b637d-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b637d-125">Click Save.</span></span>


