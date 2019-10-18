---
title: Skapa periodiseringsscheman
description: Det här avsnittet innehåller information om hur du skapar periodiseringsschema.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e8f8cf8546187ae1c65d4966887e1c5842dff431
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175640"
---
# <a name="create-accrual-schemes"></a><span data-ttu-id="f00c9-103">Skapa periodiseringsscheman</span><span class="sxs-lookup"><span data-stu-id="f00c9-103">Create accrual schemes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f00c9-104">Det här avsnittet innehåller information om hur du skapar periodiseringsschema.</span><span class="sxs-lookup"><span data-stu-id="f00c9-104">This topic explains how to create an accrual scheme.</span></span> <span data-ttu-id="f00c9-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="f00c9-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="f00c9-106">Gå till **Navigeringsfönstret > Moduler > Redovisning > Journalkonfiguration > Periodiseringsscheman**.</span><span class="sxs-lookup"><span data-stu-id="f00c9-106">Go to **Navigation pane > Modules > General ledger > Journal setup > Accrual schemes**.</span></span>
2. <span data-ttu-id="f00c9-107">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="f00c9-107">Select **New**.</span></span>
3. <span data-ttu-id="f00c9-108">Skriv ett värde i fältet **Identifiering av periodisering**.</span><span class="sxs-lookup"><span data-stu-id="f00c9-108">In the **Accrual identification** field, type a value.</span></span>
4. <span data-ttu-id="f00c9-109">Skriv ett värde i fältet **Beskrivning av periodiseringsschema**.</span><span class="sxs-lookup"><span data-stu-id="f00c9-109">In the **Description of accrual scheme** field, type a value.</span></span>
5. <span data-ttu-id="f00c9-110">Ange önskade värden i fältet **Debet**.</span><span class="sxs-lookup"><span data-stu-id="f00c9-110">In the **Debit** field, specify the desired values.</span></span> <span data-ttu-id="f00c9-111">Det definierade huvudkontot ersätter debethuvudkontot på journalverifikationsraden och det används också för återföringen av uppskjutandet baserat på periodiseringstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="f00c9-111">The main account defined will replace the debit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
6. <span data-ttu-id="f00c9-112">Ange önskade värden i fältet **Kredit**.</span><span class="sxs-lookup"><span data-stu-id="f00c9-112">In the **Credit** field, specify the desired values.</span></span> <span data-ttu-id="f00c9-113">Det definierade huvudkontot ersätter kredithuvudkontot på journalverifikationsraden och det används också för återföringen av uppskjutandet baserat på periodiseringstransaktionerna.</span><span class="sxs-lookup"><span data-stu-id="f00c9-113">The main account defined will replace the credit main account on the journal voucher line and it will also be used for the reversal of the deferral based on the ledger accrual transactions.</span></span>  
7. <span data-ttu-id="f00c9-114">I fältet **Verifikation** väljer du hur du vill att verifikationen ska fastställas när transaktionerna bokförs.</span><span class="sxs-lookup"><span data-stu-id="f00c9-114">In the **Voucher** field, select how you want the voucher determined when the transactions are posted.</span></span>
8. <span data-ttu-id="f00c9-115">I fältet **Beskrivning** skriver du ett värde som beskriver vilka transaktioner som ska bokföras.</span><span class="sxs-lookup"><span data-stu-id="f00c9-115">In the **Description** field, type a value to describe the transactions that will be posted.</span></span>
9. <span data-ttu-id="f00c9-116">Välj hur ofta transaktionerna ska ske i fältet **Periodfrekvens**.</span><span class="sxs-lookup"><span data-stu-id="f00c9-116">In the **Period frequency** field, select how often the transactions should occur.</span></span>
10. <span data-ttu-id="f00c9-117">Ange ett värde i fältet **Antal förekomster per period**.</span><span class="sxs-lookup"><span data-stu-id="f00c9-117">In the **Number of occurrences by period** field, enter a number.</span></span>
11. <span data-ttu-id="f00c9-118">I fältet **Bokför transaktioner** väljer du när transaktionerna ska bokföras, till exempel **Varje månad**.</span><span class="sxs-lookup"><span data-stu-id="f00c9-118">In the **Post transactions** field, select when the transactions should be posted, such as **Monthly**.</span></span>

