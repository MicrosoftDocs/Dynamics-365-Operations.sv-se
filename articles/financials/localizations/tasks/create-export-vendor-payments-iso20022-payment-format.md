--- 
title: "Skapa och exportera leverantörbetalningar med ett ISO20022-betalningsformat"
description: "Den här proceduren visar hur du kan skapa betalningsrader i leverantörbetalningsjournalen och generera en leverantörbetalningsfil med ett ISO2022-kreditöverföringsexempel."
author: mrolecki
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: dac38165474712cfcd6cdd2712dab89230e07b1b
ms.contentlocale: sv-se
ms.lasthandoff: 09/11/2018

---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a><span data-ttu-id="42a36-103">Skapa och exportera leverantörbetalningar med ett ISO20022-betalningsformat</span><span class="sxs-lookup"><span data-stu-id="42a36-103">Create and export vendor payments using ISO20022 payment format</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="42a36-104">Den här proceduren visar hur du kan skapa betalningsrader i leverantörbetalningsjournalen och generera en leverantörbetalningsfil med ett ISO2022-kreditöverföringsexempel.</span><span class="sxs-lookup"><span data-stu-id="42a36-104">This procedure shows how to create payment lines in the vendor payment journal and generate a vendor payment file using ISO2022 Credit transfer example.</span></span> 

<span data-ttu-id="42a36-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är DEMF.</span><span class="sxs-lookup"><span data-stu-id="42a36-105">The demo data company used to create this procedure is DEMF.</span></span>

<span data-ttu-id="42a36-106">Detta är den femte proceduren av fem som illustrerar leverantörbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="42a36-106">This is the fifth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="42a36-107">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="42a36-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-payment-lines"></a><span data-ttu-id="42a36-108">Skapa betalningsrader</span><span class="sxs-lookup"><span data-stu-id="42a36-108">Create payment lines</span></span>
1. <span data-ttu-id="42a36-109">Gå till Leverantörsreskontra > Betalningar > Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="42a36-109">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="42a36-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="42a36-110">Click New.</span></span>
3. <span data-ttu-id="42a36-111">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="42a36-111">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="42a36-112">Ange eller välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="42a36-112">In the Name field, enter or select a value.</span></span>
5. <span data-ttu-id="42a36-113">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="42a36-113">Click Lines.</span></span>
6. <span data-ttu-id="42a36-114">Klicka på Betalningsförslag.</span><span class="sxs-lookup"><span data-stu-id="42a36-114">Click Payment proposal.</span></span>
7. <span data-ttu-id="42a36-115">Klicka på Skapa betalningsförslag.</span><span class="sxs-lookup"><span data-stu-id="42a36-115">Click Create payment proposal.</span></span>
8. <span data-ttu-id="42a36-116">Expandera avsnittet Poster som ska ingå.</span><span class="sxs-lookup"><span data-stu-id="42a36-116">Expand the Records to include section.</span></span>
9. <span data-ttu-id="42a36-117">Klicka på Filter.</span><span class="sxs-lookup"><span data-stu-id="42a36-117">Click Filter.</span></span>
10. <span data-ttu-id="42a36-118">I listan markerar du raden för leverantörsregister och fältet för leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="42a36-118">In the list, select the row for Vendors table and Vendor account field.</span></span>
11. <span data-ttu-id="42a36-119">Ange eller välj ett värde i fältet Kriterier.</span><span class="sxs-lookup"><span data-stu-id="42a36-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="42a36-120">Du kan använda vissa kriterier för urval av leverantörstransaktioner för betalning ‒ för detta exempel, använd DE-001 som leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="42a36-120">You can apply any criteria for selecting vendor transactions to pay, for this example use DE-001 as a vendor account.</span></span>  
12. <span data-ttu-id="42a36-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="42a36-121">Click OK.</span></span>
13. <span data-ttu-id="42a36-122">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="42a36-122">Click OK.</span></span>
14. <span data-ttu-id="42a36-123">Klicka på Skapa betalningar.</span><span class="sxs-lookup"><span data-stu-id="42a36-123">Click Create payments.</span></span>

## <a name="generate-an-iso20022-payment-file"></a><span data-ttu-id="42a36-124">Skapa en ISO20022-betalningsfil</span><span class="sxs-lookup"><span data-stu-id="42a36-124">Generate an ISO20022 payment file</span></span>


