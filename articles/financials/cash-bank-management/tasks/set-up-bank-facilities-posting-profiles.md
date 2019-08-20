---
title: Ställ in bankkreditlimiter och bokföringsprofiler för garanti
description: Denna uppgift skapar en bankkreditlimit och en bokföringsprofil som behövs för att bearbeta en garanti.
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
ms.openlocfilehash: 427159048ffbb17749e813d67a900622900a7f21
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841931"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a><span data-ttu-id="ba797-103">Ställ in bankkreditlimiter och bokföringsprofiler för garanti</span><span class="sxs-lookup"><span data-stu-id="ba797-103">Set up bank facilities and posting profiles for letters of guarantee</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ba797-104">Denna uppgift skapar en bankkreditlimit och en bokföringsprofil som behövs för att bearbeta en garanti.</span><span class="sxs-lookup"><span data-stu-id="ba797-104">This task creates a Bank facility and posting profile that is needed to process a letter of guarantee.</span></span>



<span data-ttu-id="ba797-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="ba797-105">This task uses the USMF demo company.</span></span> 




## <a name="general-ledger-parameter"></a><span data-ttu-id="ba797-106">Redovisningsparameter</span><span class="sxs-lookup"><span data-stu-id="ba797-106">General ledger parameter</span></span>
1. <span data-ttu-id="ba797-107">Gå till Kassa- och bankhantering > Inställningar > Parametrar för kassa- och bankhantering.</span><span class="sxs-lookup"><span data-stu-id="ba797-107">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="ba797-108">Expandera bankdokumentavsnittet.</span><span class="sxs-lookup"><span data-stu-id="ba797-108">Expand the Bank document section.</span></span>
3. <span data-ttu-id="ba797-109">Välj alternativet Aktivera garanti.</span><span class="sxs-lookup"><span data-stu-id="ba797-109">Select the Enable letter of guarantee option.</span></span>
4. <span data-ttu-id="ba797-110">I fältet Transaktionsjournal, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="ba797-110">In the Transaction journal field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="ba797-111">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="ba797-111">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="ba797-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ba797-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="ba797-113">Klicka på fliken Nummersekvenser.</span><span class="sxs-lookup"><span data-stu-id="ba797-113">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="ba797-114">Definiera nummerseriekoden för referenserna Garantinummer och Transaktionsnummer för garanti</span><span class="sxs-lookup"><span data-stu-id="ba797-114">Define number sequence code for Letter of guarantee number and Letter of guarantee transaction references</span></span>  
8. <span data-ttu-id="ba797-115">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ba797-115">Click Save.</span></span>
9. <span data-ttu-id="ba797-116">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ba797-116">Close the page.</span></span>

## <a name="create-bank-facility"></a><span data-ttu-id="ba797-117">Skapa bankkreditlimit</span><span class="sxs-lookup"><span data-stu-id="ba797-117">Create Bank facility</span></span>
1. <span data-ttu-id="ba797-118">Gå till Kassa- och bankhantering > Inställningar > Bankkreditlimiter.</span><span class="sxs-lookup"><span data-stu-id="ba797-118">Go to Cash and bank management > Setup > Bank facilities.</span></span>
2. <span data-ttu-id="ba797-119">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ba797-119">Click New.</span></span>
3. <span data-ttu-id="ba797-120">I fältet Kreditlimitgrupp, ange bankkreditlimitgruppens namn för garantitransaktionen.</span><span class="sxs-lookup"><span data-stu-id="ba797-120">In the Facility group field, enter the bank facility group name for the letter of guarantee transaction.</span></span>
4. <span data-ttu-id="ba797-121">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="ba797-121">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ba797-122">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ba797-122">Click Save.</span></span>
6. <span data-ttu-id="ba797-123">Klicka på fliken Kreditlimittyper.</span><span class="sxs-lookup"><span data-stu-id="ba797-123">Click the Facility types tab.</span></span>
7. <span data-ttu-id="ba797-124">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ba797-124">Click New.</span></span>
8. <span data-ttu-id="ba797-125">I fältet Kreditlimittyp, ange namnet på bankkreditlimittypen som är relaterad till bankkreditlimitavtalet.</span><span class="sxs-lookup"><span data-stu-id="ba797-125">In the Facility type field, enter the name of the bank facility type that is related to the bank facility agreement.</span></span>
9. <span data-ttu-id="ba797-126">Skriv ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="ba797-126">In the Description field, type a value.</span></span>
10. <span data-ttu-id="ba797-127">I fältet Kreditlimittyp, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="ba797-127">In the Facility group field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="ba797-128">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="ba797-128">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="ba797-129">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ba797-129">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="ba797-130">I fältet Kreditlimitens natur, välj ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="ba797-130">In the Facility nature field, select an option.</span></span>
14. <span data-ttu-id="ba797-131">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ba797-131">Click Save.</span></span>
15. <span data-ttu-id="ba797-132">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ba797-132">Close the page.</span></span>

## <a name="bank-posting-profile"></a><span data-ttu-id="ba797-133">Bokföringsprofil för bank</span><span class="sxs-lookup"><span data-stu-id="ba797-133">Bank posting profile</span></span>
1. <span data-ttu-id="ba797-134">Gå till Kassa- och bankhantering > Inställningar > Bokföringsprofil för bankdokument.</span><span class="sxs-lookup"><span data-stu-id="ba797-134">Go to Cash and bank management > Setup > Bank documents posting profile.</span></span>
2. <span data-ttu-id="ba797-135">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ba797-135">Click New.</span></span>
3. <span data-ttu-id="ba797-136">I fältet Konto-/gruppnummer, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="ba797-136">In the Account/Group number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="ba797-137">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="ba797-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="ba797-138">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ba797-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="ba797-139">I fältet Kvittningskonto, välj huvudkontot för kvittning.</span><span class="sxs-lookup"><span data-stu-id="ba797-139">In the Settle account field, select the main account for settlement.</span></span>
7. <span data-ttu-id="ba797-140">I fältet Avgiftskonto, välj kontot för utgiftstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="ba797-140">In the Charges account field, select the account for expense transactions.</span></span>
8. <span data-ttu-id="ba797-141">I fältet Marginalkonto, välj kontot för marginaltransaktionen.</span><span class="sxs-lookup"><span data-stu-id="ba797-141">In the Margin account field, select the account for the margin transaction.</span></span>
9. <span data-ttu-id="ba797-142">I fältet Likvideringskonto, välj likvideringkontot för garantitransaktionen.</span><span class="sxs-lookup"><span data-stu-id="ba797-142">In the Liquidation account field, select the liquidation account for the letter of guarantee transaction.</span></span> 
10. <span data-ttu-id="ba797-143">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ba797-143">Click Save.</span></span>
11. <span data-ttu-id="ba797-144">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ba797-144">Close the page.</span></span>

