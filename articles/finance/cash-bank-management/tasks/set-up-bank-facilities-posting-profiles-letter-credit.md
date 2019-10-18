---
title: Ställ in bankkreditlimiter och bokföringsprofiler för en remburs
description: Den här proceduren går genom skapandet av bankkreditlimiter och den bokföringsprofil som krävs för att bearbeta remburser.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d3d35bd265ad31da083d2437fae886569766085
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188083"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a><span data-ttu-id="b5440-103">Ställ in bankkreditlimiter och bokföringsprofiler för en remburs</span><span class="sxs-lookup"><span data-stu-id="b5440-103">Set up bank facilities and posting profiles for letter of credit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b5440-104">Den här proceduren går genom skapandet av bankkreditlimiter och den bokföringsprofil som krävs för att bearbeta remburser.</span><span class="sxs-lookup"><span data-stu-id="b5440-104">This procedure walks through creating a Bank facility and posting profile required to process Letters of credit.</span></span> 

<span data-ttu-id="b5440-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="b5440-105">This tasks uses the demo company 'USMF'.</span></span>






## <a name="general-ledger-parameter"></a><span data-ttu-id="b5440-106">Redovisningsparameter</span><span class="sxs-lookup"><span data-stu-id="b5440-106">General ledger parameter</span></span>
1. <span data-ttu-id="b5440-107">Gå till Kassa- och bankhantering > Inställningar > Parametrar för kassa- och bankhantering.</span><span class="sxs-lookup"><span data-stu-id="b5440-107">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="b5440-108">Expandera bankdokumentavsnittet.</span><span class="sxs-lookup"><span data-stu-id="b5440-108">Expand the Bank document section.</span></span>
3. <span data-ttu-id="b5440-109">Välj alternativet Aktivera importremburs.</span><span class="sxs-lookup"><span data-stu-id="b5440-109">Select the Enable import letter of credit option.</span></span>
4. <span data-ttu-id="b5440-110">Välj alternativet Aktivera exportremburs.</span><span class="sxs-lookup"><span data-stu-id="b5440-110">Select the Enable export letter of credit option.</span></span>
5. <span data-ttu-id="b5440-111">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b5440-111">Click Save.</span></span>
6. <span data-ttu-id="b5440-112">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b5440-112">Close the page.</span></span>

## <a name="create-bank-facility"></a><span data-ttu-id="b5440-113">Skapa bankkreditlimit</span><span class="sxs-lookup"><span data-stu-id="b5440-113">Create Bank facility</span></span>
1. <span data-ttu-id="b5440-114">Gå till Kassa- och bankhantering > Inställningar > Bankkreditlimiter.</span><span class="sxs-lookup"><span data-stu-id="b5440-114">Go to Cash and bank management > Setup > Bank facilities.</span></span>
2. <span data-ttu-id="b5440-115">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b5440-115">Click New.</span></span>
3. <span data-ttu-id="b5440-116">I fältet Kreditlimitgrupp, ange bankkreditlimitgruppens namn.</span><span class="sxs-lookup"><span data-stu-id="b5440-116">In the Facility group field, enter the bank facility group name.</span></span>
4. <span data-ttu-id="b5440-117">I fältet Beskrivning, ange beskrivningen av bankkreditlimitgruppen.</span><span class="sxs-lookup"><span data-stu-id="b5440-117">In the Description field, enter the bank facility group description.</span></span>
5. <span data-ttu-id="b5440-118">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b5440-118">Click Save.</span></span>
6. <span data-ttu-id="b5440-119">Klicka på fliken Kreditlimittyper.</span><span class="sxs-lookup"><span data-stu-id="b5440-119">Click the Facility types tab.</span></span>
7. <span data-ttu-id="b5440-120">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b5440-120">Click New.</span></span>
8. <span data-ttu-id="b5440-121">I fältet Kreditlimittyp, ange en unik kod.</span><span class="sxs-lookup"><span data-stu-id="b5440-121">In the Facility type field, enter a unique code.</span></span>
9. <span data-ttu-id="b5440-122">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="b5440-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="b5440-123">I fältet Kreditlimittyp, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="b5440-123">In the Facility group field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="b5440-124">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="b5440-124">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="b5440-125">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="b5440-125">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="b5440-126">I fältet Kreditlimitens natur, välj natur för kreditlimiten.</span><span class="sxs-lookup"><span data-stu-id="b5440-126">In the Facility nature field, select the nature of the bank facility.</span></span>
14. <span data-ttu-id="b5440-127">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b5440-127">Click Save.</span></span>
15. <span data-ttu-id="b5440-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="b5440-128">Close the page.</span></span>

## <a name="bank-posting-profile"></a><span data-ttu-id="b5440-129">Bokföringsprofil för bank</span><span class="sxs-lookup"><span data-stu-id="b5440-129">Bank posting profile</span></span>
1. <span data-ttu-id="b5440-130">Gå till Kassa- och bankhantering > Inställningar > Bokföringsprofil för bankdokument.</span><span class="sxs-lookup"><span data-stu-id="b5440-130">Go to Cash and bank management > Setup > Bank documents posting profile.</span></span>
2. <span data-ttu-id="b5440-131">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="b5440-131">Click New.</span></span>
3. <span data-ttu-id="b5440-132">I fältet Konto-/gruppnummer, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="b5440-132">In the Account/Group number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="b5440-133">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="b5440-133">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="b5440-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="b5440-134">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="b5440-135">Välj huvudkontot för kvittning.</span><span class="sxs-lookup"><span data-stu-id="b5440-135">Select the main account for settlement.</span></span>
    * <span data-ttu-id="b5440-136">Detta konto används när du beräknar kassaflödesprognosen.</span><span class="sxs-lookup"><span data-stu-id="b5440-136">This account is used when calculating cash flow forecast.</span></span>  
7. <span data-ttu-id="b5440-137">I fältet Avgiftskonto, välj kontot för utgiftstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="b5440-137">In the Charges account field, select the account for expense transactions.</span></span>
8. <span data-ttu-id="b5440-138">I fältet Marginalkonto, välj kontot för marginaltransaktioner.</span><span class="sxs-lookup"><span data-stu-id="b5440-138">In the Margin account field, select the account for margin transactions.</span></span>
    * <span data-ttu-id="b5440-139">Det här kontot debiteras när ingångsmarginalen bokförs och krediteras när betalningen bokförs.</span><span class="sxs-lookup"><span data-stu-id="b5440-139">This account is debited when the opening margin is posted and credited when the payment is posted.</span></span>  
9. <span data-ttu-id="b5440-140">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="b5440-140">Click Save.</span></span>

