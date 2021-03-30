---
title: Upprätta ett betalsätt för kund
description: Det här avsnittet förklarar hur du skapar en metod för betalning av kundbetalningar.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7e60459c417c6018c4088009a323cf7f66616ef4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220213"
---
# <a name="establish-customer-method-of-payment"></a><span data-ttu-id="13e4c-103">Upprätta ett betalsätt för kund</span><span class="sxs-lookup"><span data-stu-id="13e4c-103">Establish customer method of payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="13e4c-104">Det här avsnittet förklarar hur du skapar en metod för betalning av kundbetalningar.</span><span class="sxs-lookup"><span data-stu-id="13e4c-104">This topic explains how to create a method of payment for customer payments.</span></span> <span data-ttu-id="13e4c-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="13e4c-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="13e4c-106">I navigeringsfönstret, gå till **Moduler > Kundreskontra > Betalningsinställning > Betalsätt**.</span><span class="sxs-lookup"><span data-stu-id="13e4c-106">In the navigation pane, go to **Modules > Accounts receivable > Payments setup > Methods of payment**.</span></span>
2. <span data-ttu-id="13e4c-107">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="13e4c-107">Select **New**.</span></span>
3. <span data-ttu-id="13e4c-108">I fältet  **Betalningsmetod** infogas ett ID för betalsättet.</span><span class="sxs-lookup"><span data-stu-id="13e4c-108">In the **Method of payment** field, enter an ID for the method of payment.</span></span> <span data-ttu-id="13e4c-109">Betalningsmetod-ID visas på fakturor och betalningar, vilket gör ett beskrivande nog för att förstå vilken typ av betalning registreras, och för vilket bankkonto.</span><span class="sxs-lookup"><span data-stu-id="13e4c-109">The Method of payment ID is shown on invoices and payments, so make it descriptive enough to understand what type of payment is being recorded, and for what bank account.</span></span>  
4. <span data-ttu-id="13e4c-110">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="13e4c-110">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="13e4c-111">Välj vilken betalningsstatus krävs för att betalningar som ska bokföras.</span><span class="sxs-lookup"><span data-stu-id="13e4c-111">Select what payment status is required in order for payments to be posted.</span></span> <span data-ttu-id="13e4c-112">När du skapar en kundbetalning, den bara kan bokföras, när betalningsstatusen matchar betalningsstatusen, anger du här.</span><span class="sxs-lookup"><span data-stu-id="13e4c-112">When creating a customer payment, it can only be posted when the payment status matches the payment status you define here.</span></span>  
6. <span data-ttu-id="13e4c-113">Välj hur kundbetalningar ska skapas för fakturor.</span><span class="sxs-lookup"><span data-stu-id="13e4c-113">Select how customers payments should be created for invoices.</span></span> <span data-ttu-id="13e4c-114">Den här väljare, används bara när du kör ett betalningsförslag.</span><span class="sxs-lookup"><span data-stu-id="13e4c-114">This option is only used when running a payment proposal.</span></span> <span data-ttu-id="13e4c-115">En betalningsförslag kan användas för kundbetalningar, när du har gjort direkta debetar och drog ut medel från kundernas bankkonton.</span><span class="sxs-lookup"><span data-stu-id="13e4c-115">A payment proposal could be used for customer payments when doing direct debits, and pulling the funds from the customers' bank accounts.</span></span>  
7. <span data-ttu-id="13e4c-116">Välj betalningstyp.</span><span class="sxs-lookup"><span data-stu-id="13e4c-116">Select the type of payment.</span></span> <span data-ttu-id="13e4c-117">Betalningstypen gör det enklare att bestämma om någon validering ska ske eller inte för betalningen.</span><span class="sxs-lookup"><span data-stu-id="13e4c-117">The payment type will help determine whether some validation will occur or not on the payment.</span></span>  
8. <span data-ttu-id="13e4c-118">Välj vilka kontotypbetalningar ska bokföras i.</span><span class="sxs-lookup"><span data-stu-id="13e4c-118">Select what account type payments will post to.</span></span> <span data-ttu-id="13e4c-119">Vanligtvis ska du välja Bank för det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="13e4c-119">Typically, Bank would be selected for this option.</span></span>  
9. <span data-ttu-id="13e4c-120">Välj bankkontot som den här betalningen ska registreras till.</span><span class="sxs-lookup"><span data-stu-id="13e4c-120">Select the bank account into which this payment will be recorded.</span></span>
10. <span data-ttu-id="13e4c-121">Ange vilken typ av banktransaktion som identifierar den typ av betalning som används av banken.</span><span class="sxs-lookup"><span data-stu-id="13e4c-121">Enter the Bank transaction type to identify the type of payment used by your bank.</span></span> <span data-ttu-id="13e4c-122">Banktransaktionstypen används under bankavstämningprocessen och kan göra en avstämning enklare.</span><span class="sxs-lookup"><span data-stu-id="13e4c-122">The bank transaction type is used during the bank reconciliation process, and can make reconciliation easier.</span></span>  
11. <span data-ttu-id="13e4c-123">Välj om den här betalningen tillfälligt bokförs på ett interimskonto.</span><span class="sxs-lookup"><span data-stu-id="13e4c-123">Select whether this payment will temporarily post to a bridging account.</span></span> <span data-ttu-id="13e4c-124">Om du vill försöka flyttaltiden för att en betalning kommer att rensa banken, använder du den överbrygga funktionen.</span><span class="sxs-lookup"><span data-stu-id="13e4c-124">If you want to try the float time for a payment to clear the bank, use the Bridging functionality.</span></span> <span data-ttu-id="13e4c-125">Betalningen tillfälligt bokförs på ett redovisningskonto, tills den rensar banken, då betalningen ska flyttas till bankkontot, som du definierade här.</span><span class="sxs-lookup"><span data-stu-id="13e4c-125">The payment will temporarily post to a Ledger account until it clears the bank, at which time the payment will move to the bank account you defined here.</span></span>  
12. <span data-ttu-id="13e4c-126">Ange som huvudkontot som används för interimsbokningen.</span><span class="sxs-lookup"><span data-stu-id="13e4c-126">Enter the main account used for the bridging posting.</span></span> <span data-ttu-id="13e4c-127">Detta är huvudkontot som betalningen ska bokföras i, om tillfälligt med hjälp av överbrygga.</span><span class="sxs-lookup"><span data-stu-id="13e4c-127">This is the main account to which the payment will temporarily post if using bridging.</span></span>  
13. <span data-ttu-id="13e4c-128">Använd fliken **Filformat** för att definiera inställningen för elektroniska betalningar.</span><span class="sxs-lookup"><span data-stu-id="13e4c-128">Use the **File format** tab to define setting for electronic payments.</span></span>
14. <span data-ttu-id="13e4c-129">Använd fliken **Betalningskontroll** för att definiera fält som är obligatoriska.</span><span class="sxs-lookup"><span data-stu-id="13e4c-129">Use the **Payment control** tab to define fields that are mandatory.</span></span> <span data-ttu-id="13e4c-130">Om du till exempel kräver att alla betalningar med denna betalningsmetod som ska infogas, kan du välja den väljare på den här fliken.</span><span class="sxs-lookup"><span data-stu-id="13e4c-130">For example, if you require all payments with this method of payment to be deposited, you can choose that option on this tab.</span></span>  
15. <span data-ttu-id="13e4c-131">Använd fliken **Betalningsattribut** för att definiera betalningsattribut som du vill använda för den här betalsättet.</span><span class="sxs-lookup"><span data-stu-id="13e4c-131">Use the **Payment attributes** tab to define which payment attributes you want to use for this method of payment.</span></span>
16. <span data-ttu-id="13e4c-132">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="13e4c-132">Select **Save**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]