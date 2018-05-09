---
title: Remburs och importinkasso
description: "Det här avsnittet innehåller allmän information om remburser och importsamlingar. Båda typerna av bankdokument används ofta för inköp och försäljning av varor över internationella gränser."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankLCImport
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 18321
ms.assetid: 5c97ab81-632b-4043-a940-674bcb496c80
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: effaffe8b5fbfc79713501973ece49db0517e30d
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="letters-of-credit-and-import-collections"></a><span data-ttu-id="0a10b-104">Remburs och importinkasso</span><span class="sxs-lookup"><span data-stu-id="0a10b-104">Letters of credit and import collections</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0a10b-105">Det här avsnittet innehåller allmän information om remburser och importsamlingar.</span><span class="sxs-lookup"><span data-stu-id="0a10b-105">This article provides general information about letters of credit and import collections.</span></span> <span data-ttu-id="0a10b-106">Båda typerna av bankdokument används ofta för inköp och försäljning av varor över internationella gränser.</span><span class="sxs-lookup"><span data-stu-id="0a10b-106">Both types of bank document are often used for the purchase and sale of goods across international borders.</span></span>

<a name="letters-of-credit"></a><span data-ttu-id="0a10b-107">Remburser</span><span class="sxs-lookup"><span data-stu-id="0a10b-107">Letters of credit</span></span>
-----------------

<span data-ttu-id="0a10b-108">Remburser används i internationella transaktioner och hjälper till att säkerställa att betalningarna utförs.</span><span class="sxs-lookup"><span data-stu-id="0a10b-108">Letters of credit are used for international transactions and help guarantee that payments will be made.</span></span> <span data-ttu-id="0a10b-109">En remburs är ett avtal som utfärdas av en bank, i vilken banken går med på att garantera betalning på uppdrag av en köpare, förutsatt att villkoren i avtalet mellan köpare och säljare uppfylls.</span><span class="sxs-lookup"><span data-stu-id="0a10b-109">A letter of credit is an agreement that is issued by a bank, in which the bank agrees to guarantee payment on behalf of a buyer, provided that the terms of the agreement between the buyer and seller are met.</span></span> <span data-ttu-id="0a10b-110">En remburs kallas "letter of credit" eller "documentary credit" (DC) på engelska.</span><span class="sxs-lookup"><span data-stu-id="0a10b-110">A letter of credit is also referred to as a documentary credit (DC).</span></span>

<span data-ttu-id="0a10b-111">För en importremburs är den juridiska personen köparen eller sökande av rembursen.</span><span class="sxs-lookup"><span data-stu-id="0a10b-111">For an import letter of credit, the legal entity is the buyer or the applicant for the letter of credit.</span></span> <span data-ttu-id="0a10b-112">För en exportremburs är den juridiska personen säljaren eller mottagaren av rembursen.</span><span class="sxs-lookup"><span data-stu-id="0a10b-112">For an export letter of credit, the legal entity is the seller or the beneficiary of the letter of credit.</span></span> <span data-ttu-id="0a10b-113">Följande parter är inblandade i en remburs:</span><span class="sxs-lookup"><span data-stu-id="0a10b-113">The following parties are involved in a letter of credit:</span></span>

-   <span data-ttu-id="0a10b-114">En sökande (köparen) som ska betala för varorna.</span><span class="sxs-lookup"><span data-stu-id="0a10b-114">The applicant (buyer) who intends to pay for the goods</span></span>
-   <span data-ttu-id="0a10b-115">Mottagaren (säljaren) som ska få betalningen.</span><span class="sxs-lookup"><span data-stu-id="0a10b-115">The beneficiary (seller) who will receive the payment</span></span>
-   <span data-ttu-id="0a10b-116">Banken som utfärdar rembursen.</span><span class="sxs-lookup"><span data-stu-id="0a10b-116">The issuing bank that issues the letter of credit</span></span>
-   <span data-ttu-id="0a10b-117">Banken som utför transaktionen på uppdrag av den sökande.</span><span class="sxs-lookup"><span data-stu-id="0a10b-117">The advising bank that carries out the transaction on behalf of the applicant</span></span>

<span data-ttu-id="0a10b-118">Rembursen innehåller en beskrivning av varorna, eventuella obligatoriska dokument, leveransdatumet och ett utgångsdatum för betalningen, dvs. betalningen görs inte efter detta datum.</span><span class="sxs-lookup"><span data-stu-id="0a10b-118">The letter of credit includes a description of the goods, any required documents, the date of shipment, and the expiration date after which payment won't be made.</span></span> <span data-ttu-id="0a10b-119">Den utfärdande banken får en avgift för rembursen.</span><span class="sxs-lookup"><span data-stu-id="0a10b-119">The issuing bank collects a margin for the letter of credit.</span></span> 

<span data-ttu-id="0a10b-120">En remburs kan vara **återkallelig** eller **oåterkallelig**.</span><span class="sxs-lookup"><span data-stu-id="0a10b-120">A letter of credit can be **revocable** or **irrevocable**.</span></span> <span data-ttu-id="0a10b-121">En remburs kan vara **transferabel**, **ej transferabel** eller **revolverande**.</span><span class="sxs-lookup"><span data-stu-id="0a10b-121">The nature of a letter of credit can be **transferable**, **non-transferable**, or **revolving**.</span></span> <span data-ttu-id="0a10b-122">Vanligtvis är en remburs ett oåterkalleligt avtal om att betalning ska göras till en viss mottagare vid uppvisande av fullständiga och korrekta leveransdokument.</span><span class="sxs-lookup"><span data-stu-id="0a10b-122">Typically, a letter of credit is an irrevocable and confirmed agreement that payment will be made to a specific beneficiary upon submission of complete and accurate shipping documentation.</span></span>

## <a name="import-collections"></a><span data-ttu-id="0a10b-123">Importinkasso</span><span class="sxs-lookup"><span data-stu-id="0a10b-123">Import collections</span></span>
<span data-ttu-id="0a10b-124">En importinkasso är ett avtal mellan banken och exportörn (säljaren), där banken förbinder sig att leverera leveransdokumentationen till den internationella importören (köparen).</span><span class="sxs-lookup"><span data-stu-id="0a10b-124">An import collection is an agreement between the bank and the exporter (seller), in which the bank agrees to deliver the shipping documentation to the international importer (buyer).</span></span> <span data-ttu-id="0a10b-125">Banken förväntas att skicka leveransdokumentationen när betalningen för de levererade varorna tas emot, eller när en växel tas emot för betalningen.</span><span class="sxs-lookup"><span data-stu-id="0a10b-125">The bank is expected to deliver the shipping documentation upon receipt of payment for the shipped goods in cash, or upon receipt of a signed draft toward the payment.</span></span> 

<span data-ttu-id="0a10b-126">En importinkasso garanterar att säljaren får betalt när köparen får leveransdokumentationen för de importerade varorna.</span><span class="sxs-lookup"><span data-stu-id="0a10b-126">An import collection helps guarantee that the seller is paid when the buyer collects the shipping documents to take delivery of the imported goods.</span></span>




