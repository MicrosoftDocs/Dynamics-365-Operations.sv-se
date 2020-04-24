---
title: Bearbeta rabatter för betalning
description: I den här proceduren visas hur du konverterar godkända och bearbetade kundrabatter till kreditfakturor.
author: omulvad
manager: tfehr
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e2e9af7167e4a4209b708d00493b8866f6d5f7e0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209937"
---
# <a name="process-rebates-for-payment"></a><span data-ttu-id="9be50-103">Bearbeta rabatter för betalning</span><span class="sxs-lookup"><span data-stu-id="9be50-103">Process rebates for payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9be50-104">I den här proceduren visas hur du konverterar godkända och bearbetade kundrabatter till kreditfakturor.</span><span class="sxs-lookup"><span data-stu-id="9be50-104">This procedure demonstrates how to convert approved and processed customer rebates to credit notes.</span></span> <span data-ttu-id="9be50-105">Du kan använda den här guiden i demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="9be50-105">You can use this guide in the USMF demo company.</span></span> <span data-ttu-id="9be50-106">Förhandsvillkoret för den här guiden är att ha ett eller flera rabattanspråk som har statusen Markera.</span><span class="sxs-lookup"><span data-stu-id="9be50-106">The precondition for this guide is to have one or more rebate claims which have a status of Mark.</span></span> <span data-ttu-id="9be50-107">Om du använder USMF ska du köra guiden "Generera och bearbeta kundrabatter" innan du startar den här guiden.</span><span class="sxs-lookup"><span data-stu-id="9be50-107">If you're using USMF you should run the "Generate and process customer rebates" guide before you start this guide.</span></span>


## <a name="convert-rebate-claims-to-credit-note"></a><span data-ttu-id="9be50-108">Konvertera rabattanspråk till kreditfaktura</span><span class="sxs-lookup"><span data-stu-id="9be50-108">Convert rebate claims to credit note</span></span>
1. <span data-ttu-id="9be50-109">Gå till Alla kunder.</span><span class="sxs-lookup"><span data-stu-id="9be50-109">Go to All customers.</span></span>
2. <span data-ttu-id="9be50-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9be50-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="9be50-111">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9be50-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="9be50-112">Klicka på Inkasso i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9be50-112">On the Action Pane, click Collect.</span></span>
5. <span data-ttu-id="9be50-113">Klicka på Kvitta transaktioner.</span><span class="sxs-lookup"><span data-stu-id="9be50-113">Click Settle transactions.</span></span>
6. <span data-ttu-id="9be50-114">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="9be50-114">Click Functions.</span></span>
7. <span data-ttu-id="9be50-115">Klicka på Rabattprogram.</span><span class="sxs-lookup"><span data-stu-id="9be50-115">Click Rebate program.</span></span>
    * <span data-ttu-id="9be50-116">På sidan Rabatt visas de rabattanspråk som du har bearbetat i workbenchen för kundrabatten och som har statusen "Markera".</span><span class="sxs-lookup"><span data-stu-id="9be50-116">The Rebate page lists the rebate claims that you have processed in the customer rebate workbench and that are in status Mark.</span></span>    
8. <span data-ttu-id="9be50-117">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="9be50-117">Click Edit.</span></span>
    * <span data-ttu-id="9be50-118">Markera fältet Markera för de anspråk som du vill inkludera i kreditfakturan.</span><span class="sxs-lookup"><span data-stu-id="9be50-118">Set checkmarks in the Mark field for the claims that you want to include into credit note.</span></span>   
9. <span data-ttu-id="9be50-119">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="9be50-119">Click Functions.</span></span>
10. <span data-ttu-id="9be50-120">Klicka på Skapa kreditfaktura.</span><span class="sxs-lookup"><span data-stu-id="9be50-120">Click Create credit note.</span></span>
    * <span data-ttu-id="9be50-121">Ett meddelande visas för att informera dig om att en journal har bokförts (detta är den journal för kundreskontraförbrukning som har angetts på sidan Parametrar för kundreskontra).</span><span class="sxs-lookup"><span data-stu-id="9be50-121">A message appears to inform you that a journal has been posted (This is the Accounts receivable consumption journal, as specified in the Accounts receivable parameters page).</span></span> <span data-ttu-id="9be50-122">Detta gör att real skuld (kredit) belopp som skall flyttas till kunden.</span><span class="sxs-lookup"><span data-stu-id="9be50-122">This causes the real liability (credit) amount to be moved to the customer balance.</span></span> <span data-ttu-id="9be50-123">Det innebär att kundens konto har krediterats och att periodiseringskontot för rabatt har debiterats.</span><span class="sxs-lookup"><span data-stu-id="9be50-123">This means that the customer's account has been credited, and the Rebate accrual account has been debited.</span></span>  
11. <span data-ttu-id="9be50-124">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9be50-124">Close the page.</span></span>
12. <span data-ttu-id="9be50-125">Klicka på Avbryt.</span><span class="sxs-lookup"><span data-stu-id="9be50-125">Click Cancel.</span></span>
    * <span data-ttu-id="9be50-126">Detta uppdaterar sidan, så att du kan se uppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="9be50-126">This refreshes the page so that you can see the updates.</span></span>  
13. <span data-ttu-id="9be50-127">Klicka på Inkasso i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9be50-127">On the Action Pane, click Collect.</span></span>
14. <span data-ttu-id="9be50-128">Klicka på Kvitta transaktioner.</span><span class="sxs-lookup"><span data-stu-id="9be50-128">Click Settle transactions.</span></span>
    * <span data-ttu-id="9be50-129">Observera att en transaktion för negativt belopp som motsvarar det totala rabattbeloppet utan fakturareferens har lagts till kundbalansen.</span><span class="sxs-lookup"><span data-stu-id="9be50-129">Note that a transaction for negative amount, representing the total rebate amount, without invoice reference has been added to the customer balance.</span></span>   
15. <span data-ttu-id="9be50-130">Klicka på Avbryt.</span><span class="sxs-lookup"><span data-stu-id="9be50-130">Click Cancel.</span></span>

