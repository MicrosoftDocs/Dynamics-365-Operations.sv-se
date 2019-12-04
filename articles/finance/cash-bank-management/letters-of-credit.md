---
title: Remburser
description: Remburser är bankdokument som vanligtvis används för inköp och försäljning av varor över internationella gränser.
author: ShylaThompson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankLCImport
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 18271
ms.assetid: aa594beb-bdb2-4117-91c2-d097d9401b0f
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 184a6bf9ad43280de135a326688dedd4a5f03a6f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772615"
---
# <a name="letters-of-credit"></a><span data-ttu-id="f69e9-103">Remburser</span><span class="sxs-lookup"><span data-stu-id="f69e9-103">Letters of credit</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f69e9-104">Remburser är bankdokument som vanligtvis används för inköp och försäljning av varor över internationella gränser.</span><span class="sxs-lookup"><span data-stu-id="f69e9-104">Letters of credit are bank documents that are commonly used for the purchase and sale of goods across international borders.</span></span> 

<span data-ttu-id="f69e9-105">Remburser används i internationella transaktioner för att se till att betalningarna utförs.</span><span class="sxs-lookup"><span data-stu-id="f69e9-105">Letters of credit are used for international transactions to ensure that payments will be made.</span></span> <span data-ttu-id="f69e9-106">En remburs är ett avtal som har utfärdats av en bank, i vilket banken går med på att säkerställa betalningen på uppdrag av köparen om villkoren i avtalet mellan köparen och säljaren uppfylls.</span><span class="sxs-lookup"><span data-stu-id="f69e9-106">A letter of credit is an agreement that is issued by a bank, in which the bank agrees to ensure payment on behalf of the buyer, if the terms of the agreement between the buyer and seller are met.</span></span> <span data-ttu-id="f69e9-107">En remburs kallas letter of credit eller documentary credit (DC) på engelska.</span><span class="sxs-lookup"><span data-stu-id="f69e9-107">Note that a letter of credit is also referred to as a documentary credit (DC).</span></span> 

<span data-ttu-id="f69e9-108">För en importremburs är den juridiska personen köparen eller sökande av rembursen.</span><span class="sxs-lookup"><span data-stu-id="f69e9-108">For an import letter of credit, the legal entity is the buyer or the applicant for the letter of credit.</span></span> <span data-ttu-id="f69e9-109">För en exportremburs är den juridiska personen säljaren eller mottagaren av rembursen.</span><span class="sxs-lookup"><span data-stu-id="f69e9-109">For an export letter of credit, the legal entity is the seller or the beneficiary of the letter of credit.</span></span> <span data-ttu-id="f69e9-110">Följande parter är inblandade vid en remburs:</span><span class="sxs-lookup"><span data-stu-id="f69e9-110">The following parties are involved with a letter of credit:</span></span> 

 - <span data-ttu-id="f69e9-111">En sökande (köparen) som ska betala för varorna.</span><span class="sxs-lookup"><span data-stu-id="f69e9-111">The applicant (buyer) who intends to pay for the goods</span></span> 
 - <span data-ttu-id="f69e9-112">Mottagaren (säljaren) som ska få betalningen.</span><span class="sxs-lookup"><span data-stu-id="f69e9-112">The beneficiary (seller) who will receive the payment</span></span>
 - <span data-ttu-id="f69e9-113">Banken som utfärdar rembursen.</span><span class="sxs-lookup"><span data-stu-id="f69e9-113">The issuing bank that issues the letter of credit</span></span>
 - <span data-ttu-id="f69e9-114">Banken som utför transaktionen på uppdrag av den sökande.</span><span class="sxs-lookup"><span data-stu-id="f69e9-114">The advising bank that carries out the transaction on behalf of the applicant</span></span>

<span data-ttu-id="f69e9-115">Rembursen innehåller en beskrivning av varorna, eventuella obligatoriska dokument, leveransdatumet och ett utgångsdatum för betalningen, dvs. betalningen görs inte efter detta datum.</span><span class="sxs-lookup"><span data-stu-id="f69e9-115">The letter of credit includes a description of the goods, any required documents, the date of shipment, and the expiration date after which payment will not be made.</span></span> <span data-ttu-id="f69e9-116">Den utfärdande banken får en avgift för rembursen.</span><span class="sxs-lookup"><span data-stu-id="f69e9-116">The issuing bank collects a margin for the letter of credit.</span></span> 

<span data-ttu-id="f69e9-117">En remburs kan vara återkallelig eller oåterkallelig.</span><span class="sxs-lookup"><span data-stu-id="f69e9-117">A letter of credit can be revocable or irrevocable.</span></span> <span data-ttu-id="f69e9-118">En remburs kan vara transferabel, ej transferabel eller revolverande.</span><span class="sxs-lookup"><span data-stu-id="f69e9-118">The nature of a letter of credit can be transferable, non transferable, or revolving.</span></span> <span data-ttu-id="f69e9-119">Vanligtvis är en remburs ett oåterkalleligt avtal om att betalning ska göras till en viss mottagare vid uppvisande av fullständiga och korrekta leveransdokument.</span><span class="sxs-lookup"><span data-stu-id="f69e9-119">Typically, a letter of credit is an irrevocable and confirmed agreement that payment will be made to a specific beneficiary upon submission of complete and accurate shipping documentation.</span></span>

<span data-ttu-id="f69e9-120">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="f69e9-120">For more information, see the following topics:</span></span>

[<span data-ttu-id="f69e9-121">Importera remburs</span><span class="sxs-lookup"><span data-stu-id="f69e9-121">Import letter of credit</span></span>](tasks/import-letter-credit.md)

[<span data-ttu-id="f69e9-122">Exportremburs</span><span class="sxs-lookup"><span data-stu-id="f69e9-122">Export letter of credit</span></span>](tasks/export-letter-credit.md)

[<span data-ttu-id="f69e9-123">Skapa ett kreditlimitavtal för en remburs</span><span class="sxs-lookup"><span data-stu-id="f69e9-123">Create a bank facility agreement for a letter of credit</span></span>](tasks/create-bank-facility-agreement-letter-credit.md)


