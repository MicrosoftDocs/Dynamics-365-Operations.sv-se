---
title: Felsöka produktkonfiguratorn
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med produktkonfiguratorn.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: dacc7205eaf2084f6fbd3be9d8ac0572f9e1bcde
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516879"
---
# <a name="troubleshoot-the-product-configurator"></a><span data-ttu-id="219a5-103">Felsöka produktkonfiguratorn</span><span class="sxs-lookup"><span data-stu-id="219a5-103">Troubleshoot the product configurator</span></span>

<span data-ttu-id="219a5-104">I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med produktkonfiguratorn.</span><span class="sxs-lookup"><span data-stu-id="219a5-104">This topic describes how to fix issues that you might encounter while you work with the product configurator.</span></span>

## <a name="item-text-is-overwritten-when-i-configure-a-product-on-a-sales-order-line"></a><span data-ttu-id="219a5-105">Artikeltext skrivs över när jag konfigurerar en produkt på en försäljningsorderrad.</span><span class="sxs-lookup"><span data-stu-id="219a5-105">Item text is overwritten when I configure a product on a sales order line.</span></span>

### <a name="issue-description"></a><span data-ttu-id="219a5-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="219a5-106">Issue description</span></span>

<span data-ttu-id="219a5-107">Det här problemet uppstår när du skapar en försäljningsorderrad för en konfigurerbar artikel och sedan ändrar artikelns text.</span><span class="sxs-lookup"><span data-stu-id="219a5-107">This issue occurs when you create a sales order line for a configurable item and then modify the item text.</span></span> <span data-ttu-id="219a5-108">När du konfigurerar artikeln och sedan väljer **OK** skrivs texten över med standardtexten.</span><span class="sxs-lookup"><span data-stu-id="219a5-108">When you configure the item and then select **OK**, the text is overwritten with the standard text.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="219a5-109">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="219a5-109">Issue resolution</span></span>

<span data-ttu-id="219a5-110">Detta är ett förväntat beteende.</span><span class="sxs-lookup"><span data-stu-id="219a5-110">This behavior is expected.</span></span> <span data-ttu-id="219a5-111">Textfältet innehåller variantnamnet, som endast fylls i när du har konfigurerat raden.</span><span class="sxs-lookup"><span data-stu-id="219a5-111">The text field includes the variant name, which is filled in only after you configure the line.</span></span> <span data-ttu-id="219a5-112">Därför måste du ändra texten när du har konfigurerat raden, inte före.</span><span class="sxs-lookup"><span data-stu-id="219a5-112">Therefore, you must change the text after you've configured the line, not before.</span></span>

## <a name="integer-attributes-are-incorrectly-rounded-when-product-configuration-models-are-calculated"></a><span data-ttu-id="219a5-113">Heltalsattribut avrundas felaktigt när produkt konfigurationsmodeller beräknas.</span><span class="sxs-lookup"><span data-stu-id="219a5-113">Integer attributes are incorrectly rounded when product configuration models are calculated.</span></span>

### <a name="issue-description"></a><span data-ttu-id="219a5-114">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="219a5-114">Issue description</span></span>

<span data-ttu-id="219a5-115">Det här problemet kan uppstå när du utför följande serie åtgärder:</span><span class="sxs-lookup"><span data-stu-id="219a5-115">This issue can occur when you perform the following series of actions:</span></span>

1. <span data-ttu-id="219a5-116">Ställ in följande attribut i en modell för produktionskonfiguration:</span><span class="sxs-lookup"><span data-stu-id="219a5-116">Set up the following attributes on a production configuration model:</span></span>

    - <span data-ttu-id="219a5-117">Indata (heltal)</span><span class="sxs-lookup"><span data-stu-id="219a5-117">Input (integer)</span></span>
    - <span data-ttu-id="219a5-118">Procent (decimal)</span><span class="sxs-lookup"><span data-stu-id="219a5-118">Percent (decimal)</span></span>
    - <span data-ttu-id="219a5-119">Resultat (heltal)</span><span class="sxs-lookup"><span data-stu-id="219a5-119">Result (integer)</span></span>

2. <span data-ttu-id="219a5-120">Skapa en beräkning som har följande uttryck:</span><span class="sxs-lookup"><span data-stu-id="219a5-120">Create a calculation that has the following expression:</span></span>

    <span data-ttu-id="219a5-121">*Resultat* = *indata* × *procent* ÷ 100</span><span class="sxs-lookup"><span data-stu-id="219a5-121">*Result* = *Input* × *Percent* ÷ 100</span></span>

<span data-ttu-id="219a5-122">I det här fallet har heltalsresultatet inte alltid avrundats korrekt.</span><span class="sxs-lookup"><span data-stu-id="219a5-122">In this case, the integer result isn't always correctly rounded.</span></span> <span data-ttu-id="219a5-123">Indata är till exempel 1 000 och procentsatsen är 2,40.</span><span class="sxs-lookup"><span data-stu-id="219a5-123">For example, the input is 1,000, and the percentage is 2.40.</span></span> <span data-ttu-id="219a5-124">Därför förväntar du att heltalsresultatet ska vara 24 eftersom 2,40 procent av 1 000 är 24 (eller 24,00 i decimalform).</span><span class="sxs-lookup"><span data-stu-id="219a5-124">Therefore, you expect the integer result to be 24, because 2.40 percent of 1,000 is 24 (or 24.00 in decimal form).</span></span> <span data-ttu-id="219a5-125">I stället visas resultatet 23.</span><span class="sxs-lookup"><span data-stu-id="219a5-125">Instead, the result is shown as 23.</span></span> <span data-ttu-id="219a5-126">När procentsatsen är 2,39 avrundas dock beräkningen till 24 i stället för 23.</span><span class="sxs-lookup"><span data-stu-id="219a5-126">However, when the percentage is 2.39, the calculation is rounded to 24 instead of 23.</span></span> <span data-ttu-id="219a5-127">När procentsatsen är 2,50 avrundas beräkningen till 25, som förväntat.</span><span class="sxs-lookup"><span data-stu-id="219a5-127">When the percentage is 2.50, the calculation is rounded to 25, as expected.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="219a5-128">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="219a5-128">Issue resolution</span></span>

<span data-ttu-id="219a5-129">Det här problemet beror på det sätt som Microsoft Solver Foundation internt representerar tal genom att använda bråktal.</span><span class="sxs-lookup"><span data-stu-id="219a5-129">This issue occurs because of the way that Microsoft Solver Foundation internally represents numbers by using fractions.</span></span> <span data-ttu-id="219a5-130">I föregående exempel representeras resultatet av beräkningen där procentsatsen är 2,40 som 27021597764222975 ÷ 1125899906842624 = 23.99999999999999911182158029987476766109466552734375.</span><span class="sxs-lookup"><span data-stu-id="219a5-130">For the preceding example, the result of the calculation where the percentage is 2.40 is represented as 27021597764222975 ÷ 1125899906842624 = 23.99999999999999911182158029987476766109466552734375.</span></span> <span data-ttu-id="219a5-131">När .NET skickar det här värdet som ett heltal returneras 23.</span><span class="sxs-lookup"><span data-stu-id="219a5-131">When .NET casts this value as an integer, it will return 23.</span></span>

<span data-ttu-id="219a5-132">Det här beteendet ändras inte eftersom andra scenarier är beroende av den.</span><span class="sxs-lookup"><span data-stu-id="219a5-132">This behavior won't be changed, because other scenarios depend on it.</span></span> <span data-ttu-id="219a5-133">I föregående exempel kan du åtgärda problemet genom att införa ytterligare ett decimalattribut och en beräkning.</span><span class="sxs-lookup"><span data-stu-id="219a5-133">For the preceding example, you can fix the issue by introducing an additional decimal attribute and a calculation.</span></span>

<span data-ttu-id="219a5-134">Du kan till exempel ställa in följande attribut i en modell för produktionskonfiguration:</span><span class="sxs-lookup"><span data-stu-id="219a5-134">For example, you can set up the following attributes on a production configuration model:</span></span>

- <span data-ttu-id="219a5-135">Indata (heltal)</span><span class="sxs-lookup"><span data-stu-id="219a5-135">Input (integer)</span></span>
- <span data-ttu-id="219a5-136">Procent (decimal)</span><span class="sxs-lookup"><span data-stu-id="219a5-136">Percent (decimal)</span></span>
- <span data-ttu-id="219a5-137">ResultDecimal (decimal)</span><span class="sxs-lookup"><span data-stu-id="219a5-137">ResultDecimal (decimal)</span></span>
- <span data-ttu-id="219a5-138">ResultInteger (heltal)</span><span class="sxs-lookup"><span data-stu-id="219a5-138">ResultInteger (integer)</span></span>

<span data-ttu-id="219a5-139">Du kan sedan lägga till följande beräkningar:</span><span class="sxs-lookup"><span data-stu-id="219a5-139">You can then add the following calculations:</span></span>

- <span data-ttu-id="219a5-140">*ResultDecimal* = *Indata* × *Procent* ÷ 100</span><span class="sxs-lookup"><span data-stu-id="219a5-140">*ResultDecimal* = *Input* × *Percent* ÷ 100</span></span>
- <span data-ttu-id="219a5-141">*ResultInteger* = *ResultDecimal*</span><span class="sxs-lookup"><span data-stu-id="219a5-141">*ResultInteger* = *ResultDecimal*</span></span>
