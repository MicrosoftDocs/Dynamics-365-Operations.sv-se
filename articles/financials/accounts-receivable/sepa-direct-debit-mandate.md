---
title: Ställa in SEPA Autogiromedgivande
description: Ett SEPA-autogiro låter en fordringshavare ta ut medel från en kunds bankkonto, förutsatt att kunden har gett fordringshavaren en undertecknad fullmakt.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 757f3f6e0c5443054d2d6bd21381d9f692e1b9a5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "334828"
---
# <a name="set-up-sepa-direct-debit-mandate"></a><span data-ttu-id="88b85-103">Ställa in SEPA Autogiromedgivande</span><span class="sxs-lookup"><span data-stu-id="88b85-103">Set up SEPA direct debit mandate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88b85-104">Ett SEPA-autogiro låter en fordringshavare ta ut medel från en kunds bankkonto, förutsatt att kunden har gett fordringshavaren en undertecknad fullmakt.</span><span class="sxs-lookup"><span data-stu-id="88b85-104">A Single Euro Payment Area (SEPA) direct debit lets a creditor collect funds from a customer's bank account, provided that the customer has granted a signed mandate to the creditor.</span></span> <span data-ttu-id="88b85-105">Kunden undertecknar en fullmakt som auktoriserar fordringsägaren till att inkassera en betalning och instruerar kundens bank att betala inkasseringen.</span><span class="sxs-lookup"><span data-stu-id="88b85-105">The mandate that the customer signs authorizes the creditor to collect a payment and instructs the customer's bank to pay the collection.</span></span> <span data-ttu-id="88b85-106">Det här avsnittet är organiserat för att visa processen för inställning av SEPA-autogiromedgivande.</span><span class="sxs-lookup"><span data-stu-id="88b85-106">This topic is organized to show the process for setting up SEPA direct debit mandates.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="88b85-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="88b85-107">Prerequisites</span></span>
<span data-ttu-id="88b85-108">Följande tabell visar förutsättningarna som krävs och måste finnas på plats innan du startar</span><span class="sxs-lookup"><span data-stu-id="88b85-108">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="88b85-109">Kategori</span><span class="sxs-lookup"><span data-stu-id="88b85-109">Category</span></span>       | <span data-ttu-id="88b85-110">Förutsättning</span><span class="sxs-lookup"><span data-stu-id="88b85-110">Prerequisite</span></span>                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="88b85-111">Land/region</span><span class="sxs-lookup"><span data-stu-id="88b85-111">Country/region</span></span> | <span data-ttu-id="88b85-112">Den primära adressen för den juridiska personen måste vara i följande länder/regioner: Österrike, Belgien, Tyskland, Spanien, Frankrike, Italien eller Nederländerna.</span><span class="sxs-lookup"><span data-stu-id="88b85-112">The primary address for the legal entity must be in the following countries/regions: Austria, Belgium, Germany, Spain, France, Italy, or the Netherlands.</span></span> |

1. <span data-ttu-id="88b85-113">Ställ in en nummerserie för autogiromedgivande. Varje autogiromedgivande måste ha ett unikt nummer.</span><span class="sxs-lookup"><span data-stu-id="88b85-113">Set up a number sequence for direct debit mandates Each direct debit mandate must have a unique number.</span></span> <span data-ttu-id="88b85-114">Använd sidan **Nummersekvenser** om du vill skapa en nummerserie för autogiromedgivanden.</span><span class="sxs-lookup"><span data-stu-id="88b85-114">Use the **Number sequences** page to create a number sequence for direct debit mandates.</span></span> <span data-ttu-id="88b85-115">Du använder den här identifieraren för att tilldela nummerserien till systemet för autogiromedgivande på sidan **Parametrar för kundreskontra**.</span><span class="sxs-lookup"><span data-stu-id="88b85-115">You will use this identifier to assign the number sequence to the direct debit mandate system on the **Accounts receivable parameters** page.</span></span>

2. <span data-ttu-id="88b85-116">Ställ in parametrar för kundreskontra för autogiromedgivande. Använd sidan **Parametrar för kundreskontra** om du vill ställa in parametrar för autogiromedgivande.</span><span class="sxs-lookup"><span data-stu-id="88b85-116">Set up Accounts receivable parameters for direct debit mandates Use the **Accounts receivable parameters** page to set up parameters for direct debit mandates.</span></span> <span data-ttu-id="88b85-117">Du ställer in dessa parametrar på fliken **Direktdebitering**. Ändra standardparametrarna som du vill.</span><span class="sxs-lookup"><span data-stu-id="88b85-117">To set up the parameters, on the **Direct debit** tab, change the default parameters as you require.</span></span> <span data-ttu-id="88b85-118">Klicka sedan på fliken **Nummerserier** och uppdatera fältet **ID för autogiromedgivande** med den nummerserie som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="88b85-118">Then, on the **Number sequences** tab, update the **Direct debit mandate ID** field with the number sequence that you set up earlier.</span></span>

3. <span data-ttu-id="88b85-119">Om du vill ställa in en betalningsmetod för autogiromedgivanden måste du ställa in en betalningsmetod för autogiromedgivanden.</span><span class="sxs-lookup"><span data-stu-id="88b85-119">Set up a method of payment for direct debit mandates You must set up a method of payment for direct debit mandates.</span></span> <span data-ttu-id="88b85-120">Du använder den här betalningsmetoden om du vill fråga efter fakturor som du vill generera autogirobetalningar för.</span><span class="sxs-lookup"><span data-stu-id="88b85-120">You use this method of payment to query for invoices to generate direct debit payments for.</span></span> <span data-ttu-id="88b85-121">Betalningsmetoden måste ställas in på sidan **Betalningsmetoder**.</span><span class="sxs-lookup"><span data-stu-id="88b85-121">Use the **Methods of payment** page to set up the method of payment.</span></span> <span data-ttu-id="88b85-122">Om du vill ställa in en betalningsmetod för autogiromedgivanden måste du följa följande ytterligare steg för en betalningsmetod:</span><span class="sxs-lookup"><span data-stu-id="88b85-122">To set up a method of payment for direct debit mandates, you must follow these additional steps for a method of payment:</span></span>

-   <span data-ttu-id="88b85-123">Välj **Elektronisk betalning** i fältet **Betalningstyp**.</span><span class="sxs-lookup"><span data-stu-id="88b85-123">In the **Payment type** field, select **Electronic payment**.</span></span>
-   <span data-ttu-id="88b85-124">Valfritt: Om du förväntar dig att var och en av dina kunder har flera fullmakter, väljer du **Faktura** i fältet **Period**.</span><span class="sxs-lookup"><span data-stu-id="88b85-124">Optional: If you expect each of your customers to have multiple mandates, in the **Period** field, select **Invoice**.</span></span> <span data-ttu-id="88b85-125">En separat betalning skapas för varje faktura och varje betalning kommer att använda fullmakten som angetts för fakturan.</span><span class="sxs-lookup"><span data-stu-id="88b85-125">A separate payment will be created for each invoice, and each payment will use the mandate that is specified for the invoice.</span></span>
-   <span data-ttu-id="88b85-126">Välj alternativet **Kräv medgivande** för att skapa betalningar genom att använda autogiromedgivanden.</span><span class="sxs-lookup"><span data-stu-id="88b85-126">Select the **Require mandate** option to create payments by using direct debit mandates.</span></span> <span data-ttu-id="88b85-127">Alternativet **Kräv medgivande** är endast tillgängligt om du väljer **Elektronisk betalning** i fältet **Betalningstyp**.</span><span class="sxs-lookup"><span data-stu-id="88b85-127">The **Require mandate** option is available only if you select **Electronic payment** in the **Payment type** field.</span></span>

<span data-ttu-id="88b85-128">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="88b85-128">Additional resources</span></span>

[<span data-ttu-id="88b85-129">Översikt över autogiro</span><span class="sxs-lookup"><span data-stu-id="88b85-129">Direct debit overview</span></span>](sepa-direct-debit-overview.md) 

[<span data-ttu-id="88b85-130">Skapa ett autogiromedgivande för en kund</span><span class="sxs-lookup"><span data-stu-id="88b85-130">Create a direct debit mandate for a customer</span></span>](tasks/create-direct-debit-mandate-customer.md) 

