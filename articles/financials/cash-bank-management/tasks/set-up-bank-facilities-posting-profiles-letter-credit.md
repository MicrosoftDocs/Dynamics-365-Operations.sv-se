--- 
title: "Ställ in bankkreditlimiter och bokföringsprofiler för en remburs"
description: "Den här proceduren går genom skapandet av bankkreditlimiter och den bokföringsprofil som krävs för att bearbeta remburser."
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 43422627f8529768ab9377c04568da531d6565c6
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a><span data-ttu-id="23a0a-103">Ställ in bankkreditlimiter och bokföringsprofiler för en remburs</span><span class="sxs-lookup"><span data-stu-id="23a0a-103">Set up bank facilities and posting profiles for letter of credit</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="23a0a-104">Den här proceduren går genom skapandet av bankkreditlimiter och den bokföringsprofil som krävs för att bearbeta remburser.</span><span class="sxs-lookup"><span data-stu-id="23a0a-104">This procedure walks through creating a Bank facility and posting profile required to process Letters of credit.</span></span> 

<span data-ttu-id="23a0a-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="23a0a-105">This tasks uses the demo company 'USMF'.</span></span>






## <a name="general-ledger-parameter"></a><span data-ttu-id="23a0a-106">Redovisningsparameter</span><span class="sxs-lookup"><span data-stu-id="23a0a-106">General ledger parameter</span></span>
1. <span data-ttu-id="23a0a-107">Gå till Kassa- och bankhantering > Inställningar > Parametrar för kassa- och bankhantering.</span><span class="sxs-lookup"><span data-stu-id="23a0a-107">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="23a0a-108">Expandera bankdokumentavsnittet.</span><span class="sxs-lookup"><span data-stu-id="23a0a-108">Expand the Bank document section.</span></span>
3. <span data-ttu-id="23a0a-109">Välj alternativet Aktivera importremburs.</span><span class="sxs-lookup"><span data-stu-id="23a0a-109">Select the Enable import letter of credit option.</span></span>
4. <span data-ttu-id="23a0a-110">Välj alternativet Aktivera exportremburs.</span><span class="sxs-lookup"><span data-stu-id="23a0a-110">Select the Enable export letter of credit option.</span></span>
5. <span data-ttu-id="23a0a-111">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="23a0a-111">Click Save.</span></span>
6. <span data-ttu-id="23a0a-112">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="23a0a-112">Close the page.</span></span>

## <a name="create-bank-facility"></a><span data-ttu-id="23a0a-113">Skapa bankkreditlimit</span><span class="sxs-lookup"><span data-stu-id="23a0a-113">Create Bank facility</span></span>
1. <span data-ttu-id="23a0a-114">Gå till Kassa- och bankhantering > Inställningar > Bankkreditlimiter.</span><span class="sxs-lookup"><span data-stu-id="23a0a-114">Go to Cash and bank management > Setup > Bank facilities.</span></span>
2. <span data-ttu-id="23a0a-115">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="23a0a-115">Click New.</span></span>
3. <span data-ttu-id="23a0a-116">I fältet Kreditlimitgrupp, ange bankkreditlimitgruppens namn.</span><span class="sxs-lookup"><span data-stu-id="23a0a-116">In the Facility group field, enter the bank facility group name.</span></span>
4. <span data-ttu-id="23a0a-117">I fältet Beskrivning, ange beskrivningen av bankkreditlimitgruppen.</span><span class="sxs-lookup"><span data-stu-id="23a0a-117">In the Description field, enter the bank facility group description.</span></span>
5. <span data-ttu-id="23a0a-118">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="23a0a-118">Click Save.</span></span>
6. <span data-ttu-id="23a0a-119">Klicka på fliken Kreditlimittyper.</span><span class="sxs-lookup"><span data-stu-id="23a0a-119">Click the Facility types tab.</span></span>
7. <span data-ttu-id="23a0a-120">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="23a0a-120">Click New.</span></span>
8. <span data-ttu-id="23a0a-121">I fältet Kreditlimittyp, ange en unik kod.</span><span class="sxs-lookup"><span data-stu-id="23a0a-121">In the Facility type field, enter a unique code.</span></span>
9. <span data-ttu-id="23a0a-122">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="23a0a-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="23a0a-123">I fältet Kreditlimittyp, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="23a0a-123">In the Facility group field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="23a0a-124">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="23a0a-124">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="23a0a-125">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="23a0a-125">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="23a0a-126">I fältet Kreditlimitens natur, välj natur för kreditlimiten.</span><span class="sxs-lookup"><span data-stu-id="23a0a-126">In the Facility nature field, select the nature of the bank facility.</span></span>
14. <span data-ttu-id="23a0a-127">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="23a0a-127">Click Save.</span></span>
15. <span data-ttu-id="23a0a-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="23a0a-128">Close the page.</span></span>

## <a name="bank-posting-profile"></a><span data-ttu-id="23a0a-129">Bokföringsprofil för bank</span><span class="sxs-lookup"><span data-stu-id="23a0a-129">Bank posting profile</span></span>
1. <span data-ttu-id="23a0a-130">Gå till Kassa- och bankhantering > Inställningar > Bokföringsprofil för bankdokument.</span><span class="sxs-lookup"><span data-stu-id="23a0a-130">Go to Cash and bank management > Setup > Bank documents posting profile.</span></span>
2. <span data-ttu-id="23a0a-131">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="23a0a-131">Click New.</span></span>
3. <span data-ttu-id="23a0a-132">I fältet Konto-/gruppnummer, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="23a0a-132">In the Account/Group number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="23a0a-133">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="23a0a-133">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="23a0a-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="23a0a-134">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="23a0a-135">Välj huvudkontot för kvittning.</span><span class="sxs-lookup"><span data-stu-id="23a0a-135">Select the main account for settlement.</span></span>
    * <span data-ttu-id="23a0a-136">Detta konto används när du beräknar kassaflödesprognosen.</span><span class="sxs-lookup"><span data-stu-id="23a0a-136">This account is used when calculating cash flow forecast.</span></span>  
7. <span data-ttu-id="23a0a-137">I fältet Avgiftskonto, välj kontot för utgiftstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="23a0a-137">In the Charges account field, select the account for expense transactions.</span></span>
8. <span data-ttu-id="23a0a-138">I fältet Marginalkonto, välj kontot för marginaltransaktioner.</span><span class="sxs-lookup"><span data-stu-id="23a0a-138">In the Margin account field, select the account for margin transactions.</span></span>
    * <span data-ttu-id="23a0a-139">Det här kontot debiteras när ingångsmarginalen bokförs och krediteras när betalningen bokförs.</span><span class="sxs-lookup"><span data-stu-id="23a0a-139">This account is debited when the opening margin is posted and credited when the payment is posted.</span></span>  
9. <span data-ttu-id="23a0a-140">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="23a0a-140">Click Save.</span></span>


