--- 
title: "Ställ in företagets bankkonton för ISO20022-kreditöverföringar"
description: "I den här proceduren visas hur du ställer in företagsspecifik bankkontoinformation som krävs för att generera betalningsfilen."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 66fd18c415a11a6b9bb027a323b416cb12f2a3a4
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a><span data-ttu-id="c565e-103">Ställ in företagets bankkonton för ISO20022-kreditöverföringar</span><span class="sxs-lookup"><span data-stu-id="c565e-103">Set up company bank accounts for ISO20022 credit transfers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c565e-104">I den här proceduren visas hur du ställer in företagsspecifik bankkontoinformation som krävs för att generera betalningsfilen.</span><span class="sxs-lookup"><span data-stu-id="c565e-104">This procedure shows how to set up company-specific bank account information that is required for payment file generation.</span></span> <span data-ttu-id="c565e-105">Du ställer in information som krävs för att skapa format för ISO 20022-kreditöverföring, men beroende på formatet kan annan information krävas, till exempel företags-ID eller sorteringskod.</span><span class="sxs-lookup"><span data-stu-id="c565e-105">You set up information required to generate ISO 20022 credit transfer format but depending on the format there might be other information required, such as the Company ID or the Sort code.</span></span> 

<span data-ttu-id="c565e-106">Det demonstrationsdataföretag som används för att skapa den här proceduren är DEMF.</span><span class="sxs-lookup"><span data-stu-id="c565e-106">The demo data company used to create this procedure is DEMF.</span></span>

<span data-ttu-id="c565e-107">Detta är den andra proceduren av fem som illustrerar leverantörbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="c565e-107">This is the second procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="c565e-108">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="c565e-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-iban-and-swift-code"></a><span data-ttu-id="c565e-109">Ställ in IBAN- och SWIFT-koden</span><span class="sxs-lookup"><span data-stu-id="c565e-109">Set up IBAN and SWIFT code</span></span>
1. <span data-ttu-id="c565e-110">Gå till Kassa- och bankhantering > Bankkonton.</span><span class="sxs-lookup"><span data-stu-id="c565e-110">Go to Cash and bank management > Bank accounts.</span></span>
2. <span data-ttu-id="c565e-111">Använd snabbfiltret för att filtrera efter fältet Bankkonto med värdet "DEMF OPER".</span><span class="sxs-lookup"><span data-stu-id="c565e-111">Use the Quick Filter to filter on the Bank account field with a value of 'DEMF OPER'.</span></span>
3. <span data-ttu-id="c565e-112">Klicka på DEMF OPER för att öppna bankkontoinformationen.</span><span class="sxs-lookup"><span data-stu-id="c565e-112">Click DEMF OPER to open bank account details.</span></span>
4. <span data-ttu-id="c565e-113">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="c565e-113">Click Edit.</span></span>
5. <span data-ttu-id="c565e-114">Expandera avsnittet Additional identification section.</span><span class="sxs-lookup"><span data-stu-id="c565e-114">Expand the Additional identification section.</span></span>
6. <span data-ttu-id="c565e-115">Skriv "DE89370400440532013000" i fältet IBAN.</span><span class="sxs-lookup"><span data-stu-id="c565e-115">In the IBAN field, type 'DE89370400440532013000'.</span></span>
7. <span data-ttu-id="c565e-116">Skriv "DEUTDEFF" i fältet SWIFT-kod.</span><span class="sxs-lookup"><span data-stu-id="c565e-116">In the SWIFT code field, type 'DEUTDEFF'.</span></span>
    * <span data-ttu-id="c565e-117">Observera att SWIFT\BIC inte krävs för många betalningsformat, men det rekommenderas att registrera det för ett bankkonto.</span><span class="sxs-lookup"><span data-stu-id="c565e-117">Note that SWIFT\BIC is not required for many payment formats, however it is recommended to have it registered for a bank account.</span></span>  
8. <span data-ttu-id="c565e-118">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c565e-118">Click Save.</span></span>

## <a name="set-up-bank-account-for-the-legal-entity"></a><span data-ttu-id="c565e-119">Ställ in bankkonto för den juridiska personen</span><span class="sxs-lookup"><span data-stu-id="c565e-119">Set up bank account for the legal entity</span></span>
1. <span data-ttu-id="c565e-120">Gå till Organisationsadministration > Organisationer > Juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="c565e-120">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="c565e-121">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="c565e-121">Click Edit.</span></span>
3. <span data-ttu-id="c565e-122">Expandera avsnittet Bankkontoinformation.</span><span class="sxs-lookup"><span data-stu-id="c565e-122">Expand the Bank account information section.</span></span>
4. <span data-ttu-id="c565e-123">Ange eller välj ett värde i fältet Bankkonto.</span><span class="sxs-lookup"><span data-stu-id="c565e-123">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="c565e-124">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="c565e-124">Click Save.</span></span>


