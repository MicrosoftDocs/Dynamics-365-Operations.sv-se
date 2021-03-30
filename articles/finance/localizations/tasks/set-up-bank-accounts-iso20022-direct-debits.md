---
title: Ställ in kunder och kundbankkonton för ISO20022-autogiron
description: Den här uppgiften går igenom hur du ställer in ett kundbankkonto och ett autogiromedgivande för kund som krävs för att generera kundbetalningsfilen som ISO20022-autogiro.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, CustDirectDebitMandate, BankAccountTableLookUp,  LogisticsAddressCityLookup
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4d097caf3ad097e3107708c426ef668c70298c4f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209861"
---
# <a name="set-up-customers-and-customer-bank-accounts-for-iso20022-direct-debits"></a><span data-ttu-id="94919-103">Ställ in kunder och kundbankkonton för ISO20022-autogiron</span><span class="sxs-lookup"><span data-stu-id="94919-103">Set up customers and customer bank accounts for ISO20022 direct debits</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="94919-104">Den här uppgiften går igenom hur du ställer in ett kundbankkonto och ett autogiromedgivande för kund som krävs för att generera kundbetalningsfilen som ISO20022-autogiro.</span><span class="sxs-lookup"><span data-stu-id="94919-104">This task walks you through setting up a customer bank account and a customer direct debit mandate which are required to generate the customer payment file like ISO20022 direct debit.</span></span> <span data-ttu-id="94919-105">Beroende på de format för kundbetalningar som har ställts in, kan ytterligare information som inte ingår i den här proceduren kanske komma att krävas för en kund eller ett kundbankkonto.</span><span class="sxs-lookup"><span data-stu-id="94919-105">Depending on the customer payment formats tha are set up, additional information, not covered in this procedure, might be required for a customer or a customer bank account.</span></span> 

<span data-ttu-id="94919-106">Den här uppgiften skapades med hjälp av demonstrationsdataföretaget DEMF med en primär adress för juridisk person i Tyskland.</span><span class="sxs-lookup"><span data-stu-id="94919-106">This task was created using the demo data company DEMF with a legal entity primary address in Germany.</span></span>



<span data-ttu-id="94919-107">Detta är den fjärde av fem procedurer som demonstrerar kundbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="94919-107">This is the fourth of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>


## <a name="set-up-a-customer-bank-account"></a><span data-ttu-id="94919-108">Ställ in ett kundbankkonto</span><span class="sxs-lookup"><span data-stu-id="94919-108">Set up a customer bank account</span></span>
1. <span data-ttu-id="94919-109">Gå till Leverantörsreskontra > Kunder > Alla kunder.</span><span class="sxs-lookup"><span data-stu-id="94919-109">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="94919-110">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="94919-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="94919-111">Filtrera till exempel efter fältet Konto med värdet "DE-010".</span><span class="sxs-lookup"><span data-stu-id="94919-111">For example, filter on the Account field with a value of 'DE-010 '.</span></span>
3. <span data-ttu-id="94919-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="94919-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="94919-113">Klicka på Kund i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="94919-113">On the Action Pane, click Customer.</span></span>
5. <span data-ttu-id="94919-114">Klicka på bankkonton.</span><span class="sxs-lookup"><span data-stu-id="94919-114">Click Bank accounts.</span></span>
6. <span data-ttu-id="94919-115">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="94919-115">Click New.</span></span>
7. <span data-ttu-id="94919-116">I fältet Bankkonto, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="94919-116">In the Bank account field, type a value.</span></span>
8. <span data-ttu-id="94919-117">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="94919-117">In the Name field, type a value.</span></span>
    * <span data-ttu-id="94919-118">Ange till exempel "EUR bank".</span><span class="sxs-lookup"><span data-stu-id="94919-118">For example, enter 'EUR bank'.</span></span>  
9. <span data-ttu-id="94919-119">Ange eller välj ett värde i fältet Bankgrupper.</span><span class="sxs-lookup"><span data-stu-id="94919-119">In the Bank groups field, enter or select a value.</span></span>
10. <span data-ttu-id="94919-120">Ange ett värde i fältet IBAN.</span><span class="sxs-lookup"><span data-stu-id="94919-120">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="94919-121">Ange till exempel "DE36200400000628808808".</span><span class="sxs-lookup"><span data-stu-id="94919-121">For example, enter 'DE36200400000628808808'.</span></span>  
11. <span data-ttu-id="94919-122">Skriv ett värde i fältet SWIFT-kod.</span><span class="sxs-lookup"><span data-stu-id="94919-122">In the SWIFT code field, type a value.</span></span>
    * <span data-ttu-id="94919-123">Ange till exempel "COBADEFFXXX".</span><span class="sxs-lookup"><span data-stu-id="94919-123">For example: Enter 'COBADEFFXXX'.</span></span>  <span data-ttu-id="94919-124">Observera att SWIFT\BIC inte krävs för många betalningsformat, men det rekommenderas att registrera det för ett bankkonto.</span><span class="sxs-lookup"><span data-stu-id="94919-124">Please note that SWIFT \ BIC is not mandatory for many payment formats however it is recommended to have it registered for a bank account.</span></span>  
12. <span data-ttu-id="94919-125">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="94919-125">Click Save.</span></span>
13. <span data-ttu-id="94919-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="94919-126">Close the page.</span></span>
14. <span data-ttu-id="94919-127">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="94919-127">Click Edit.</span></span>
15. <span data-ttu-id="94919-128">Expandera avsnittet Standardvärden för betalningar.</span><span class="sxs-lookup"><span data-stu-id="94919-128">Expand the Payment defaults section.</span></span>
16. <span data-ttu-id="94919-129">Ange eller välj ett värde i fältet Bankkonto.</span><span class="sxs-lookup"><span data-stu-id="94919-129">In the Bank account field, enter or select a value.</span></span>

## <a name="add-a-direct-debit-mandate"></a><span data-ttu-id="94919-130">Lägg till ett autogiromedgivande</span><span class="sxs-lookup"><span data-stu-id="94919-130">Add a direct debit mandate</span></span>
1. <span data-ttu-id="94919-131">Expandera avsnittet Autogiromedgivanden.</span><span class="sxs-lookup"><span data-stu-id="94919-131">Expand the Direct debit mandates section.</span></span>
2. <span data-ttu-id="94919-132">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="94919-132">Click Add.</span></span>
3. <span data-ttu-id="94919-133">Ange eller välj ett värde i fältet Creditor bank account.</span><span class="sxs-lookup"><span data-stu-id="94919-133">In the Creditor bank account field, enter or select a value.</span></span>
    * <span data-ttu-id="94919-134">Välj till exempel "DEMF OPER".</span><span class="sxs-lookup"><span data-stu-id="94919-134">For example, select DEMF OPER.</span></span>  
4. <span data-ttu-id="94919-135">I fältet Datum för undertecknande, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="94919-135">In the Signature date field, enter a date.</span></span>
5. <span data-ttu-id="94919-136">Klicka på Ja om du vill bekräfta datumuppdateringen.</span><span class="sxs-lookup"><span data-stu-id="94919-136">Click Yes to confirm the date update.</span></span>
6. <span data-ttu-id="94919-137">Ange eller välj ett värde i fältet Plats för undertecknande.</span><span class="sxs-lookup"><span data-stu-id="94919-137">In the Signature location field, enter or select a value.</span></span>
7. <span data-ttu-id="94919-138">Ange ett antal i fältet Förväntat antal betalningar.</span><span class="sxs-lookup"><span data-stu-id="94919-138">In the Expected number of payments field, enter a number.</span></span>
8. <span data-ttu-id="94919-139">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="94919-139">Click OK.</span></span>
9. <span data-ttu-id="94919-140">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="94919-140">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]