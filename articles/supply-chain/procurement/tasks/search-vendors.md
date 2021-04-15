---
title: Sök efter leverantörer
description: Läs hur du vill söka efter leverantörer baserat på specifika kriterier.
author: kamaybac
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendSearchCriterion, VendSearchAddCategory, VendSearchAddReviewCriterionGroup, VendSearchResults, VendSearchAddReviewCriterion
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 494f28ad6cf6f973b090a5d0f745eb530256925c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811928"
---
# <a name="search-for-vendors"></a><span data-ttu-id="9e057-103">Sök efter leverantörer</span><span class="sxs-lookup"><span data-stu-id="9e057-103">Search for vendors</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9e057-104">Läs hur du vill söka efter leverantörer baserat på specifika kriterier.</span><span class="sxs-lookup"><span data-stu-id="9e057-104">Learn how to search for vendors based on specific criteria.</span></span> <span data-ttu-id="9e057-105">I det här exemplet visas hur du söker efter leverantörer som har godkänts för en viss anskaffningskategori och har sin primära adress i ett visst land.</span><span class="sxs-lookup"><span data-stu-id="9e057-105">This example shows you how to search for vendors that are approved for a particular procurement category and have their primary address in a specific country.</span></span> <span data-ttu-id="9e057-106">Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="9e057-106">You can run this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="9e057-107">Den här uppgiften utförs vanligtvis av ett anskaffningsproffs.</span><span class="sxs-lookup"><span data-stu-id="9e057-107">This task would usually be carried out by a procurement professional.</span></span>

1. <span data-ttu-id="9e057-108">Gå till Anskaffning och källa > Leverantörer > Leverantörssökning.</span><span class="sxs-lookup"><span data-stu-id="9e057-108">Go to Procurement and sourcing > Vendors > Vendor search.</span></span>
2. <span data-ttu-id="9e057-109">Klicka på plusikonen om du vill öppna sidan Val av anskaffningskategori.</span><span class="sxs-lookup"><span data-stu-id="9e057-109">Click on the Plus icon to open the Procurement category selection page.</span></span>  
3. <span data-ttu-id="9e057-110">Välj "ANSKAFFNINGSKATEGORIER FÖR FÖRETAG\OFFICE-DATORER" i trädet.</span><span class="sxs-lookup"><span data-stu-id="9e057-110">In the tree, select 'CORP PROCUREMENT CATEGORIES\OFFICE MACHINES'.</span></span>
    * <span data-ttu-id="9e057-111">Om du kör den här proceduren som en uppgiftsguide, måste du klicka på fliken Lås upp innan du kan välja korrekt nod.</span><span class="sxs-lookup"><span data-stu-id="9e057-111">If you're running this procedure as a task guide, you may have to click the Unlock button before you can select the correct node.</span></span> <span data-ttu-id="9e057-112">Om du inte använder USMF väljer du en av de kategorier som du har.</span><span class="sxs-lookup"><span data-stu-id="9e057-112">If you're not using USMF, select one of the categories that you have.</span></span>  
4. <span data-ttu-id="9e057-113">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="9e057-113">Click Add.</span></span>
    * <span data-ttu-id="9e057-114">Det går att välja fler än en kategori här.</span><span class="sxs-lookup"><span data-stu-id="9e057-114">It's possible to select more than one category here.</span></span> <span data-ttu-id="9e057-115">Om du gör det kommer alla leverantörer som har godkänts för minst en av kategorierna att hittas vid sökningen.</span><span class="sxs-lookup"><span data-stu-id="9e057-115">If you do so, the search will find all the vendors that are approved for at least one of the categories.</span></span>  
5. <span data-ttu-id="9e057-116">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9e057-116">Click OK.</span></span>
6. <span data-ttu-id="9e057-117">Skriv ett värde i fältet Land/region.</span><span class="sxs-lookup"><span data-stu-id="9e057-117">In the Country/region field, type a value.</span></span>
7. <span data-ttu-id="9e057-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9e057-118">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]