---
title: EUR-00015 Partsökning via moms-ID
description: I den här proceduren visas hur du utför en partsökning part med hjälp av ett registrerings-ID.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirPartyTable, DirPartTaxRegistrationSearch
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 401971b6f146f1df028291ba0f691ccac5f1966d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408603"
---
# <a name="eur-00015-party-search-using-vat-id"></a><span data-ttu-id="02bab-103">EUR-00015 Partsökning via moms-ID</span><span class="sxs-lookup"><span data-stu-id="02bab-103">EUR-00015 Party search using VAT ID</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="02bab-104">I den här proceduren visas hur du utför en partsökning part med hjälp av ett registrerings-ID.</span><span class="sxs-lookup"><span data-stu-id="02bab-104">This procedure shows how to complete a party search using a registration ID.</span></span> <span data-ttu-id="02bab-105">Innan du kan slutföra proceduren måste du skapa moms-ID och ange moms-ID för leverantörer, kunder eller juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="02bab-105">Before you can complete this procedure, you must set up VAT IDs and enter any VAT IDs for vendors, customers, or legal entities.</span></span>

<span data-ttu-id="02bab-106">Den här proceduren gäller för alla europeiska länder/regioner.</span><span class="sxs-lookup"><span data-stu-id="02bab-106">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="02bab-107">Proceduren skapades med hjälp av demonstrationsdataföretaget DEMF, med primär adress i Tyskland.</span><span class="sxs-lookup"><span data-stu-id="02bab-107">The procedure was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="02bab-108">Denna procedur är avsedd för en leverantörsreskontrachef eller en kundreskontrachef.</span><span class="sxs-lookup"><span data-stu-id="02bab-108">This procedure is intended for an accounts payable manager or accounts receivable manager.</span></span> <span data-ttu-id="02bab-109">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="02bab-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="02bab-110">Gå till Organization administration > Global address book > Global address book.</span><span class="sxs-lookup"><span data-stu-id="02bab-110">Go to Organization administration > Global address book > Global address book.</span></span>
2. <span data-ttu-id="02bab-111">Klicka på Registration ID search.</span><span class="sxs-lookup"><span data-stu-id="02bab-111">Click Registration ID search.</span></span>
3. <span data-ttu-id="02bab-112">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="02bab-112">Click Add.</span></span>
4. <span data-ttu-id="02bab-113">Ange eller välj ett värde i fältet Registration type.</span><span class="sxs-lookup"><span data-stu-id="02bab-113">In the Registration type field, enter or select a value.</span></span>
    * <span data-ttu-id="02bab-114">Om du till exempel vill hitta parter med ett registrerings-ID av typen moms-ID, välj VAT ID.</span><span class="sxs-lookup"><span data-stu-id="02bab-114">For example, if you wanted to find parties with a registration ID of type VAT ID, select VAT ID.</span></span>  
5. <span data-ttu-id="02bab-115">Ange eller välj ett värde i fältet Land/region.</span><span class="sxs-lookup"><span data-stu-id="02bab-115">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="02bab-116">Ange exempelvis DEU.</span><span class="sxs-lookup"><span data-stu-id="02bab-116">For example, enter DEU.</span></span>  
6. <span data-ttu-id="02bab-117">Ange ett värde i fältet Registration number.</span><span class="sxs-lookup"><span data-stu-id="02bab-117">In the Registration number field, type a value.</span></span>
7. <span data-ttu-id="02bab-118">Klicka på Find.</span><span class="sxs-lookup"><span data-stu-id="02bab-118">Click Find.</span></span>
    * <span data-ttu-id="02bab-119">Alla parter med detta registrerings-ID visas.</span><span class="sxs-lookup"><span data-stu-id="02bab-119">All parties with that registration ID will be displayed.</span></span>  

