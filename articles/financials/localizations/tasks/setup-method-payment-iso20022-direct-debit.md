--- 
title: "Ställ in en betalningsmetod för ISO20022-autogiro"
description: "I denna procedur visas hur du ställer in kundbetalningsmetoden ISO20022 med direkt debitering eller någon annan betalningstyp med hjälp av elektronisk rapportering."
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPaymMode
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 953a3cffc356ab44163944318e7e7d542a113112
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="setup-method-of-payment-for-iso20022-direct-debit"></a><span data-ttu-id="d5328-103">Ställ in en betalningsmetod för ISO20022-autogiro</span><span class="sxs-lookup"><span data-stu-id="d5328-103">Setup method of payment for ISO20022 direct debit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d5328-104">I denna procedur visas hur du ställer in kundbetalningsmetoden ISO20022 med direkt debitering eller någon annan betalningstyp med hjälp av elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="d5328-104">This procedure shows how to set up the customer method of payment for ISO20022 direct debit or any other payment type using electronic reporting.</span></span> 



<span data-ttu-id="d5328-105">Innan du slutför denna uppgift måste du skapa exportformatkonfigurationer och betalningskonton.</span><span class="sxs-lookup"><span data-stu-id="d5328-105">Before you complete this task, you must set up export format configurations and payment accounts.</span></span>



<span data-ttu-id="d5328-106">Proceduren har skapats med demodataföretaget DEMF.</span><span class="sxs-lookup"><span data-stu-id="d5328-106">This procedure was created using the demo data company DEMF.</span></span>



<span data-ttu-id="d5328-107">Detta är den tredje av fem procedurer som demonstrerar kundbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="d5328-107">This is the third of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="d5328-108">Gå till Kundreskontra > Betalningsinställning > Betalningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="d5328-108">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="d5328-109">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="d5328-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d5328-110">Filtrera till exempel efter fältet Betalningsmetod med värdet "ELECTRONIC".</span><span class="sxs-lookup"><span data-stu-id="d5328-110">For example, filter on the Method of payment field with a value of 'ELECTRONIC'.</span></span>
3. <span data-ttu-id="d5328-111">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="d5328-111">Click Edit.</span></span>
4. <span data-ttu-id="d5328-112">Ange värdena "'DEMF OPER" i fältet Betalningskonto.</span><span class="sxs-lookup"><span data-stu-id="d5328-112">In the Payment account field, specify the values 'DEMF OPER'.</span></span>
5. <span data-ttu-id="d5328-113">Expandera avsnittet Filformat.</span><span class="sxs-lookup"><span data-stu-id="d5328-113">Expand the File formats section.</span></span>
6. <span data-ttu-id="d5328-114">Välj Ja i fältet Allmän elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="d5328-114">Select Yes in the Generic electronic reporting field.</span></span>
7. <span data-ttu-id="d5328-115">Ange eller välj ett värde i fältet Exportera formatkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="d5328-115">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="d5328-116">Välj "ISO20022 Direct debit (DE)" i listan.</span><span class="sxs-lookup"><span data-stu-id="d5328-116">In the list, select ISO20022 Direct debit (DE).</span></span>  <span data-ttu-id="d5328-117">Om listan är tom innebär det att inga aktiva konfigurationer av exportformat för kundbetalning har importerats.</span><span class="sxs-lookup"><span data-stu-id="d5328-117">If the list is empty, the customer payment export format configuration has not been imported and active.</span></span>  
8. <span data-ttu-id="d5328-118">Välj Ja i fältet kräv medgivande.</span><span class="sxs-lookup"><span data-stu-id="d5328-118">Select Yes in the Require mandate field.</span></span>
    * <span data-ttu-id="d5328-119">Välj parametern Require mandate för layouten för kundbetalningar som kräver inkludering av fullmaktsinformation i betalningsmeddelandet, exempelvis autogiro för SEPA.</span><span class="sxs-lookup"><span data-stu-id="d5328-119">Select the Require mandate parameter for customer payment formats, which require including mandate information in the payment message, like SEPA direct debit.</span></span>  
9. <span data-ttu-id="d5328-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="d5328-120">Click Save.</span></span>


