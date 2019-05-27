---
title: Konfigurera kontantbenämningar för kassan (POS)
description: Kontantbenämningar för sedlar och mynt kan definieras i back office för kassörer, affärskontakter och butikschefer iifrån kassan.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreCashDeclarationTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 24775044e5a502a5615392a6a8c4030bdfafb0ab
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558583"
---
# <a name="configure-cash-denominations-for-the-point-of-sale-pos"></a><span data-ttu-id="41e6f-103">Konfigurera kontantbenämningar för kassan (POS)</span><span class="sxs-lookup"><span data-stu-id="41e6f-103">Configure cash denominations for the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="41e6f-104">Kontantbenämningar för sedlar och mynt kan definieras i back office för kassörer, affärskontakter och butikschefer iifrån kassan.</span><span class="sxs-lookup"><span data-stu-id="41e6f-104">Cash denominations for notes and coins can be defined in the back office to be used by cashiers, sales associates, and managers at the store from within the POS.</span></span> <span data-ttu-id="41e6f-105">Dessa benämningar kan användas vid beräkning av kontanter i kassaavstämningar i slutet av dagen eller för att genomföra en försäljning snabbt.</span><span class="sxs-lookup"><span data-stu-id="41e6f-105">These denominations can be used to aid in counting cash for end of day tender declarations or for quickly tendering a sale.</span></span>

## <a name="define-denominations"></a><span data-ttu-id="41e6f-106">Definiera benämningar</span><span class="sxs-lookup"><span data-stu-id="41e6f-106">Define denominations</span></span>

<span data-ttu-id="41e6f-107">Benämningar ställs in per butik på alternativet **Ställ in** \> **kontantavstämning från sidan butiksegenskaper**.</span><span class="sxs-lookup"><span data-stu-id="41e6f-107">The denominations are set up per store on the **Set up** \> **Cash declaration option from the store property** page.</span></span>

![kontantbenämningar](./media/image1-denomination.png)

<span data-ttu-id="41e6f-109">För att definiera en benämning:</span><span class="sxs-lookup"><span data-stu-id="41e6f-109">To define a denomination:</span></span>

1. <span data-ttu-id="41e6f-110">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="41e6f-110">Click **New**.</span></span>
1. <span data-ttu-id="41e6f-111">Ange typen (mynt eller sedel).</span><span class="sxs-lookup"><span data-stu-id="41e6f-111">Specify the type (coin or note).</span></span>
1. <span data-ttu-id="41e6f-112">Ange beloppet (värde).</span><span class="sxs-lookup"><span data-stu-id="41e6f-112">Specify the amount (value).</span></span>

![kontantbenämningar](./media/image2-denomination.png)

## <a name="configure-the-functionality-profile"></a><span data-ttu-id="41e6f-114">Konfigurera funktionsprofilen</span><span class="sxs-lookup"><span data-stu-id="41e6f-114">Configure the functionality profile</span></span>

<span data-ttu-id="41e6f-115">Vid betalning av kontanter i kassan kan användaren använda sedelbenämningar för att snabbt ange det belopp som betalats av kunden.</span><span class="sxs-lookup"><span data-stu-id="41e6f-115">When paying by cash in POS, the user can use the note denominations to quickly enter the amount paid by the customer.</span></span> <span data-ttu-id="41e6f-116">Du kan konfigurera två alternativ för visning av benämningen i kassan i funktionsprofilen.</span><span class="sxs-lookup"><span data-stu-id="41e6f-116">In the functionality profile, you can configure the two options for showing the denomination in POS.</span></span>

- <span data-ttu-id="41e6f-117">**Större eller lika med det förfallna beloppet** - som standard visar kassan endast de sedelbenämningar som är större än beloppet som förfaller till betalning, vilket gör det möjligt för snabb genomföring av transaktionen.</span><span class="sxs-lookup"><span data-stu-id="41e6f-117">**Greater or equal to amount due** – By default, POS will only show the note denominations that are greater than the amount due, which allows for one-touch tendering.</span></span> <span data-ttu-id="41e6f-118">Om till exempel det förfallna beloppet är 7,50 visar kassan följande benämningar: 10, 20, 50 och 100.</span><span class="sxs-lookup"><span data-stu-id="41e6f-118">For example, if the amount due is $7.50, POS would show the following denominations: $10, $20, $50, and $100.</span></span> <span data-ttu-id="41e6f-119">Om du rör något av dessa belopp kommer försäljningaen att genomföras automatiskt för detta belopp.</span><span class="sxs-lookup"><span data-stu-id="41e6f-119">Touching any of these amounts will automatically tender the sale for that amount.</span></span> <span data-ttu-id="41e6f-120">Sedlarna 1 och 5 visas inte eftersom dessa belopp är mindre än beloppet som förfaller.</span><span class="sxs-lookup"><span data-stu-id="41e6f-120">The $1 and $5 notes are not shown since these amounts are less than the amount due.</span></span>
- <span data-ttu-id="41e6f-121">**Alla benämningar** - Markera det här alternativet för att alltid visa alla sedelbenämningar i kassan, oavsett hur mycket förfaller.</span><span class="sxs-lookup"><span data-stu-id="41e6f-121">**All denominations** – Select this option to always show all note denominations in POS, regardless of the amount due.</span></span> <span data-ttu-id="41e6f-122">Detta innebär att användaren kan använda en kombination av sedlar till det förfallna beloppet.</span><span class="sxs-lookup"><span data-stu-id="41e6f-122">This means that the user can use a combination of notes to reach the amount due.</span></span> <span data-ttu-id="41e6f-123">Om till exempel det förfallna beloppet är 25,00 kan användaren välja 20 och 5 för att slutföra försäljningen.</span><span class="sxs-lookup"><span data-stu-id="41e6f-123">For example, if the amount due is $25.00, the user can choose $20 and $5 to complete the sale.</span></span>
