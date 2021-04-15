---
title: Hantera validering av internationellt bankkontonummer (IBAN)
description: Det här avsnittet förklarar hur du hanterar validering av internationellt bankkontonummer (IBAN).
author: mikefalkner
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: e44b855165752baeb42d3c9952c35982ef24b0f5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815870"
---
# <a name="manage-international-bank-account-number-iban-account-validation"></a><span data-ttu-id="de12e-103">Hantera validering av internationellt bankkontonummer (IBAN)</span><span class="sxs-lookup"><span data-stu-id="de12e-103">Manage International Bank Account Number (IBAN) account validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="de12e-104">Validering av internationellt bankkontonummer (IBAN) ökar mängden validering som görs när du lägger till ett IBAN till ett bankkonto.</span><span class="sxs-lookup"><span data-stu-id="de12e-104">International Bank Account Number (IBAN) validation increases the amount of validation that is done when you add an IBAN to a bank account.</span></span>

<span data-ttu-id="de12e-105">Information om strukturen i IBAN-numret lagras i Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="de12e-105">Information about the structure of the IBAN is stored in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="de12e-106">Informationen läses in automatiskt när du först använder IBAN på bankkonton.</span><span class="sxs-lookup"><span data-stu-id="de12e-106">That information is automatically loaded when you first use the IBAN on bank accounts.</span></span> <span data-ttu-id="de12e-107">Den innehåller längden på IBAN, bankkontonumrets startposition och organisationsnumret och längden på kontonumret och organisationsnummer.</span><span class="sxs-lookup"><span data-stu-id="de12e-107">It contains the length of the IBAN, the starting positions of the bank account number and the routing number, and the length of the bank account number and routing number.</span></span>

## <a name="set-up-iban-structures"></a><span data-ttu-id="de12e-108">Ställ in IBAN-strukturer</span><span class="sxs-lookup"><span data-stu-id="de12e-108">Set up IBAN structures</span></span>

1. <span data-ttu-id="de12e-109">Gå till **Kassa- och bankhantering \> Inställningar \> IBAN-strukturer**.</span><span class="sxs-lookup"><span data-stu-id="de12e-109">Go to **Cash and bank management \> Setup \> IBAN structures**.</span></span>
2. <span data-ttu-id="de12e-110">Observera att IBAN strukturerna för varje land eller region har ställts in automatiskt.</span><span class="sxs-lookup"><span data-stu-id="de12e-110">Notice that the IBAN structures for each country or region have been set up automatically.</span></span>
3. <span data-ttu-id="de12e-111">Om du vill anpassa strukturerna för ett visst land eller region kan du redigera dem.</span><span class="sxs-lookup"><span data-stu-id="de12e-111">If you want to customize the structures for a specific country or region, you can edit them.</span></span>
4. <span data-ttu-id="de12e-112">Strukturdefinitionerna kommer att ingå i varje ny utgåva.</span><span class="sxs-lookup"><span data-stu-id="de12e-112">The structure definitions will be a part of each new release.</span></span> <span data-ttu-id="de12e-113">Du kan använda menyn **Återställ strukturer** för att hämta de senaste definitionerna efter varje uppdatering.</span><span class="sxs-lookup"><span data-stu-id="de12e-113">You can use the **Reset structures** menu to load the latest definitions after each update.</span></span>

## <a name="validate-the-iban-structure-in-a-bank-account"></a><span data-ttu-id="de12e-114">Validera IBAN-strukturen på ett bankkonto</span><span class="sxs-lookup"><span data-stu-id="de12e-114">Validate the IBAN structure in a bank account</span></span>

1. <span data-ttu-id="de12e-115">Gå till **Kassa- och bankhantering \> Bankkonton \> Bankkonton**.</span><span class="sxs-lookup"><span data-stu-id="de12e-115">Go to **Cash and bank management \> Bank accounts \> Bank accounts**.</span></span>
2. <span data-ttu-id="de12e-116">Skapa ett bankkonto.</span><span class="sxs-lookup"><span data-stu-id="de12e-116">Create a bank account.</span></span>
3. <span data-ttu-id="de12e-117">På snabbfliken **Ytterligare information**, ange ett IBAN.</span><span class="sxs-lookup"><span data-stu-id="de12e-117">On the **Additional information** FastTab, enter an IBAN.</span></span>

    <span data-ttu-id="de12e-118">Om längden på IBAN inte motsvaras av längden som definieras för varje land eller region, visas ett varningsmeddelande.</span><span class="sxs-lookup"><span data-stu-id="de12e-118">If the length of the IBAN doesn't match the length that is defined for each country or region, you will receive a warning message.</span></span> <span data-ttu-id="de12e-119">Du kan inte fortsätta om längden på IBAN inte motsvaras av längden som specificeras i IBAN-strukturen.</span><span class="sxs-lookup"><span data-stu-id="de12e-119">You can't continue if the length of the IBAN doesn't match the length specified in the IBAN structure.</span></span>

    <span data-ttu-id="de12e-120">Valideringen kontrollerar även att bankkontonumret stämmer överens med delen i IBAN-numret som representerar numret på bankkontot.</span><span class="sxs-lookup"><span data-stu-id="de12e-120">The validation also verifies that the bank account number matches the part of the IBAN that represents the bank account number.</span></span> <span data-ttu-id="de12e-121">Om bankkontonumret inte överensstämmer visas ett varningsmeddelande.</span><span class="sxs-lookup"><span data-stu-id="de12e-121">If the bank account number doesn't match, you will receive a warning message.</span></span> <span data-ttu-id="de12e-122">Detta meddelande är bara en varning.</span><span class="sxs-lookup"><span data-stu-id="de12e-122">This message is only a warning.</span></span> <span data-ttu-id="de12e-123">Du kan fortsätta trots att bankkontonumret inte stämmer överens.</span><span class="sxs-lookup"><span data-stu-id="de12e-123">You can continue even if the bank account number doesn't match.</span></span>

    <span data-ttu-id="de12e-124">Valideringen kontrollerar även att bankorganisationsnumret stämmer överens med delen i IBAN-numret som representerar bankorganisationsnumret.</span><span class="sxs-lookup"><span data-stu-id="de12e-124">The validation also verifies that the bank routing number matches the part of the IBAN that represents the bank routing number.</span></span> <span data-ttu-id="de12e-125">Organisationsnumret inkluderar ett banknummer och ofta ett ytterligare bankkontor.</span><span class="sxs-lookup"><span data-stu-id="de12e-125">The routing number includes a bank number and often an additional bank branch.</span></span> <span data-ttu-id="de12e-126">Om bankorganisationsnumret inte överensstämmer visas ett varningsmeddelande.</span><span class="sxs-lookup"><span data-stu-id="de12e-126">If the bank routing number doesn't match, you will receive a warning message.</span></span> <span data-ttu-id="de12e-127">Detta meddelande är bara en varning.</span><span class="sxs-lookup"><span data-stu-id="de12e-127">This message is only a warning.</span></span> <span data-ttu-id="de12e-128">Du kan fortsätta trots att bankorganisationsnumret inte stämmer överens.</span><span class="sxs-lookup"><span data-stu-id="de12e-128">You can continue even if the bank routing number doesn't match.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]