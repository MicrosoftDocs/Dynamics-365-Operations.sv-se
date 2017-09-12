--- 
title: "Registrera och bokför en efterdaterad check för en leverantör"
description: "Du kan registrera informationen om en efterdaterad check innan du utfärdar checken till en leverantör genom att använda bokföringsordern."
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 8689421d3281f93af9298f777f92c5c3b2c1c86c
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="register-and-post-a-postdated-check-for-a-vendor"></a><span data-ttu-id="3ca49-103">Registrera och bokför en efterdaterad check för en leverantör</span><span class="sxs-lookup"><span data-stu-id="3ca49-103">Register and post a postdated check for a vendor</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3ca49-104">Du kan registrera informationen om en efterdaterad check innan du utfärdar checken till en leverantör genom att använda bokföringsordern.</span><span class="sxs-lookup"><span data-stu-id="3ca49-104">You can register the details of a postdated check before you issue the check to a vendor by using the journal voucher.</span></span> <span data-ttu-id="3ca49-105">Du kan även bokföra den efterdaterade checken och generera ekonomiska transaktioner.</span><span class="sxs-lookup"><span data-stu-id="3ca49-105">You can also post the postdated check and generate financial transactions.</span></span> <span data-ttu-id="3ca49-106">Slutför följande uppgift innan du registrerar och bokför en efterdaterad check från en leverantör:</span><span class="sxs-lookup"><span data-stu-id="3ca49-106">Before you register and post a postdated check from a vendor, complete the following task:</span></span> 

<span data-ttu-id="3ca49-107">ställ in efterdaterade checkar på sidan Kassa- och bankhantering.</span><span class="sxs-lookup"><span data-stu-id="3ca49-107">Set up postdated checks in the Cash and bank management page.</span></span> 



<span data-ttu-id="3ca49-108">Rollen för den här uppgiftsguiden är Kassaförvaltare.</span><span class="sxs-lookup"><span data-stu-id="3ca49-108">The role of this task guides is Treasurer.</span></span> <span data-ttu-id="3ca49-109">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="3ca49-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="3ca49-110">Gå till Leverantörsreskontra > Betalningar > Betalningsjournal</span><span class="sxs-lookup"><span data-stu-id="3ca49-110">Go to Acounts payable > Payments > Payment journal</span></span>
2. <span data-ttu-id="3ca49-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="3ca49-111">Click New.</span></span>
3. <span data-ttu-id="3ca49-112">Skriv ”VendPay” i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="3ca49-112">In the Name field, type 'VendPay'.</span></span>
4. <span data-ttu-id="3ca49-113">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="3ca49-113">Click Lines.</span></span>
5. <span data-ttu-id="3ca49-114">Ange önskade värden i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="3ca49-114">In the Account field, specify the desired values.</span></span>
6. <span data-ttu-id="3ca49-115">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="3ca49-115">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="3ca49-116">Ange ett tal i fältet Debet.</span><span class="sxs-lookup"><span data-stu-id="3ca49-116">In the Debit field, enter a number.</span></span>
8. <span data-ttu-id="3ca49-117">I fältet Betalningsmetod, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="3ca49-117">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="3ca49-118">Välj betalningsmetoden för den efterdaterade checken.</span><span class="sxs-lookup"><span data-stu-id="3ca49-118">Select the method of payment for the postdated check</span></span>  
9. <span data-ttu-id="3ca49-119">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="3ca49-119">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="3ca49-120">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="3ca49-120">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="3ca49-121">Klicka på fliken Efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="3ca49-121">Click the Postdated checks tab.</span></span>
12. <span data-ttu-id="3ca49-122">I fältet Checknummer, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="3ca49-122">In the Check number field, type a value.</span></span>
    * <span data-ttu-id="3ca49-123">Ange eller ändra numret på den efterdaterade checken.</span><span class="sxs-lookup"><span data-stu-id="3ca49-123">Enter or modify the number of the postdated check.</span></span>  
13. <span data-ttu-id="3ca49-124">I fältet Namn på utfärdande bank, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="3ca49-124">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="3ca49-125">ange bankdetaljerna för den utfärdande banken.</span><span class="sxs-lookup"><span data-stu-id="3ca49-125">enter the bank details for the issuing bank.</span></span>  
14. <span data-ttu-id="3ca49-126">Klicka på fliken Lista.</span><span class="sxs-lookup"><span data-stu-id="3ca49-126">Click the List tab.</span></span>
15. <span data-ttu-id="3ca49-127">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="3ca49-127">Click Post.</span></span>
16. <span data-ttu-id="3ca49-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="3ca49-128">Close the page.</span></span>
17. <span data-ttu-id="3ca49-129">Klicka på fliken Efterdaterade checkar.</span><span class="sxs-lookup"><span data-stu-id="3ca49-129">Click the Postdated checks tab.</span></span>


