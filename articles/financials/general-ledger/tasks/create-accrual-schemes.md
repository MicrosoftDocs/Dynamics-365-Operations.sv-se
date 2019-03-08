---
title: Skapa periodiseringsscheman
description: Den här uppgiften leder dig genom stegen för att skapa ett periodiseringsschema.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ce96ccfb0dc3e4a723af967147dae93772c5b44f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "355298"
---
# <a name="create-accrual-schemes"></a><span data-ttu-id="fc481-103">Skapa periodiseringsscheman</span><span class="sxs-lookup"><span data-stu-id="fc481-103">Create accrual schemes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fc481-104">Den här uppgiften leder dig genom stegen för att skapa ett periodiseringsschema.</span><span class="sxs-lookup"><span data-stu-id="fc481-104">This task guide steps through creating an accrual scheme.</span></span> <span data-ttu-id="fc481-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="fc481-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="fc481-106">Gå till Redovisning > Journalkonfigurering > Periodiseringsscheman.</span><span class="sxs-lookup"><span data-stu-id="fc481-106">Go to General ledger > Journal setup > Accrual schemes.</span></span>
2. <span data-ttu-id="fc481-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fc481-107">Click New.</span></span>
3. <span data-ttu-id="fc481-108">Skriv ett värde i fältet Identifiering av periodisering.</span><span class="sxs-lookup"><span data-stu-id="fc481-108">In the Accrual identification field, type a value.</span></span>
4. <span data-ttu-id="fc481-109">Skriv ett värde i fältet Beskrivning av periodiseringsschema.</span><span class="sxs-lookup"><span data-stu-id="fc481-109">In the Description of accrual scheme field, type a value.</span></span>
5. <span data-ttu-id="fc481-110">Ange önskade värden i fältet Debet.</span><span class="sxs-lookup"><span data-stu-id="fc481-110">In the Debit field, specify the desired values.</span></span>
    * <span data-ttu-id="fc481-111">Det definierade huvudkontot ersätter debethuvudkontot på journalverifikationsraden och det används också för återföringen av uppskjutandet baserat på periodiseringstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="fc481-111">The main account defined will replace the debit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
6. <span data-ttu-id="fc481-112">Ange önskade värden i fältet Kredit.</span><span class="sxs-lookup"><span data-stu-id="fc481-112">In the Credit field, specify the desired values.</span></span>
    * <span data-ttu-id="fc481-113">Det definierade huvudkontot ersätter kredithuvudkontot på journalverifikationsraden och det används också för återföringen av uppskjutandet baserat på periodiseringstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="fc481-113">The main account defined will replace the credit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
7. <span data-ttu-id="fc481-114">I fältet Verifikation väljer du hur du vill att verifikationen ska fastställas när transaktionerna bokförs.</span><span class="sxs-lookup"><span data-stu-id="fc481-114">In the Voucher field, select how you want the voucher determined when the transactions are posted.</span></span>
8. <span data-ttu-id="fc481-115">I fältet Beskrivning skriver du ett värde som beskriver vilka transaktioner som ska bokföras.</span><span class="sxs-lookup"><span data-stu-id="fc481-115">In the Description field, type a value to describe the transactions that will be posted.</span></span>
9. <span data-ttu-id="fc481-116">Välj hur ofta transaktionerna ska ske i fältet Periodfrekvens.</span><span class="sxs-lookup"><span data-stu-id="fc481-116">In the Period frequency field, select how often the transactions should occur.</span></span>
10. <span data-ttu-id="fc481-117">Ange ett värde i fältet Antal förekomster per period.</span><span class="sxs-lookup"><span data-stu-id="fc481-117">In the Number of occurrences by period field, enter a number.</span></span>
11. <span data-ttu-id="fc481-118">I fältet Bokför transaktioner väljer du när transaktionerna ska bokföras, till exempel varje månad.</span><span class="sxs-lookup"><span data-stu-id="fc481-118">In the Post transactions field, select when the transactions should be posted, such as Monthly.</span></span>

