---
title: Hantera validering av internationellt bankkontonummer (IBAN)
description: "Det här avsnittet förklarar hur du hanterar validering av internationellt bankkontonummer (IBAN)."
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: e091aab70a98e0f4b96c41c1ee48926947539105
ms.contentlocale: sv-se
ms.lasthandoff: 08/31/2018

---

# <a name="manage-international-bank-account-number-iban-account-validation"></a><span data-ttu-id="75665-103">Hantera validering av internationellt bankkontonummer (IBAN)</span><span class="sxs-lookup"><span data-stu-id="75665-103">Manage International Bank Account Number (IBAN) account validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="75665-104">Validering av internationellt bankkontonummer (IBAN) ökar mängden validering som görs när du lägger till ett IBAN till ett bankkonto.</span><span class="sxs-lookup"><span data-stu-id="75665-104">International Bank Account Number (IBAN) account validation increases the amount of validation that is done when you add an IBAN to a bank account.</span></span>

<span data-ttu-id="75665-105">Strukturen i IBAN lagras i Microsoft Dynamics 365 for Finance and Operation och laddas automatiskt när du först använder IBAN på bankkonton.</span><span class="sxs-lookup"><span data-stu-id="75665-105">The structure of the IBAN is stored in Microsoft Dynamics 365 for Finance and Operation, and is automatically loaded when you first use the IBAN on bank accounts.</span></span> <span data-ttu-id="75665-106">Bankkontonumret ingår i strukturen som definieras för ett IBAN-nummer.</span><span class="sxs-lookup"><span data-stu-id="75665-106">The bank account number is part of the structure defined for an IBAN number.</span></span> <span data-ttu-id="75665-107">Utifrån denna struktur, om placering och längden på kontonummer i IBAN inte matchar den position som definieras i strukturen för varje land eller region kommer du att få varningsmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="75665-107">Based on that structure, if the position and length of the account number in the IBAN don't match the position that is defined in the structure for each country or region, you will receive warning messages.</span></span>

## <a name="set-up-iban-structures"></a><span data-ttu-id="75665-108">Ställ in IBAN-strukturer</span><span class="sxs-lookup"><span data-stu-id="75665-108">Set up IBAN structures</span></span>

1. <span data-ttu-id="75665-109">Gå till **Kassa- och bankhantering \> Inställningar \> IBAN-strukturer**.</span><span class="sxs-lookup"><span data-stu-id="75665-109">Go to **Cash and bank management \> Setup \> IBAN structures**.</span></span>
2. <span data-ttu-id="75665-110">Observera att IBAN strukturerna för varje land eller region har ställts in automatiskt.</span><span class="sxs-lookup"><span data-stu-id="75665-110">Notice that the IBAN structures for each country or region have been set up automatically.</span></span>
3. <span data-ttu-id="75665-111">Om du måste anpassa strukturerna för ett visst land eller region kan du redigera dem.</span><span class="sxs-lookup"><span data-stu-id="75665-111">If you must customize the structures for a specific country or region, you can edit them.</span></span>
4. <span data-ttu-id="75665-112">Strukturdefinitionerna kommer att ingå i varje ny utgåva.</span><span class="sxs-lookup"><span data-stu-id="75665-112">The structure definitions will be a part of each new release.</span></span> <span data-ttu-id="75665-113">Du kan använda menyn **Återställ strukturer** för att hämta de senaste definitionerna efter varje uppdatering.</span><span class="sxs-lookup"><span data-stu-id="75665-113">You can use the **Reset structures** menu to load the latest definitions after each update.</span></span>

## <a name="validate-the-iban-structure-in-a-bank-account"></a><span data-ttu-id="75665-114">Validera IBAN-strukturen på ett bankkonto</span><span class="sxs-lookup"><span data-stu-id="75665-114">Validate the IBAN structure in a bank account</span></span>

1. <span data-ttu-id="75665-115">Gå till **Kassa- och bankhantering \> Bankkonton \> Bankkonton**.</span><span class="sxs-lookup"><span data-stu-id="75665-115">Go to **Cash and bank management \> Bank accounts \> Bank accounts**.</span></span>
2. <span data-ttu-id="75665-116">Skapa ett bankkonto.</span><span class="sxs-lookup"><span data-stu-id="75665-116">Create a bank account.</span></span>
3. <span data-ttu-id="75665-117">På snabbfliken **Ytterligare information**, ange ett IBAN.</span><span class="sxs-lookup"><span data-stu-id="75665-117">On the **Additional information** FastTab, enter an IBAN.</span></span>

    <span data-ttu-id="75665-118">Om placeringen och längden på kontonummer i IBAN inte matchar den position som definieras i strukturen för varje land eller region kommer du att få ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="75665-118">If the position and length of the account number in the IBAN don't match the position that is defined in the structure for each country or region, you receive a message.</span></span> <span data-ttu-id="75665-119">Du kan inte fortsätta om längden på IBAN inte motsvaras av längden i IBAN-strukturen.</span><span class="sxs-lookup"><span data-stu-id="75665-119">You can't continue if the length of the IBAN doesn't match the length in the IBAN structure.</span></span>

    <span data-ttu-id="75665-120">Valideringen kontrollerar även att bankkontonumret stämmer överens med delen i IBAN-numret som representerar numret på bankkontot.</span><span class="sxs-lookup"><span data-stu-id="75665-120">The validation also verifies that the bank account number matches the part of the IBAN that represents the bank account number.</span></span> <span data-ttu-id="75665-121">Om bankkontonumret  inte överensstämmer visas ett varningsmeddelande.</span><span class="sxs-lookup"><span data-stu-id="75665-121">If the bank account number doesn't match, you receive a warning message.</span></span> <span data-ttu-id="75665-122">Detta meddelande är bara en varning.</span><span class="sxs-lookup"><span data-stu-id="75665-122">This message is only a warning.</span></span> <span data-ttu-id="75665-123">Du kan fortsätta trots att bankkontonumret inte stämmer överens.</span><span class="sxs-lookup"><span data-stu-id="75665-123">You can continue even if the bank account number doesn't match.</span></span>

