---
title: "Allokeringsregler för redovisning"
description: "Den här artikeln innehåller information om allokeringsregler för redovisning. Den beskriver de olika komponenterna för dessa allokeringsregler och allokeringsmetoderna som kan användas för dem."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerAllocation, LedgerAllocationBasisRule, LedgerAllocationRequest, LedgerAllocationRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15402
ms.assetid: 8147e148-7c11-45ef-95c6-f9889a875b54
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e5eb9d79fee7ec2e288db24aee9535d6414fdeed
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="ledger-allocation-rules"></a><span data-ttu-id="de0a6-104">Allokeringsregler för redovisning</span><span class="sxs-lookup"><span data-stu-id="de0a6-104">Ledger allocation rules</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="de0a6-105">Den här artikeln innehåller information om allokeringsregler för redovisning.</span><span class="sxs-lookup"><span data-stu-id="de0a6-105">This article provides information about ledger allocation rules.</span></span> <span data-ttu-id="de0a6-106">Den beskriver de olika komponenterna för dessa allokeringsregler och allokeringsmetoderna som kan användas för dem.</span><span class="sxs-lookup"><span data-stu-id="de0a6-106">It describes the various components of these allocation rules and the allocation methods that can be used for them.</span></span>

<span data-ttu-id="de0a6-107">Redovisningallokeringsregler används för att beräkna och automatiskt generera allokeringsjournaler och kontoposter för allokering av redovisningssaldon eller fasta belopp.</span><span class="sxs-lookup"><span data-stu-id="de0a6-107">Ledger allocation rules are used to automatically calculate and generate allocation journals and account entries for the allocation of ledger balances or fixed amounts.</span></span> <span data-ttu-id="de0a6-108">Allokeringmetoder kan vara variabla eller fasta.</span><span class="sxs-lookup"><span data-stu-id="de0a6-108">Allocation methods can be variable or fixed.</span></span> <span data-ttu-id="de0a6-109">Följande allokeringsmetoder kan användas för redovisningallokeringsregler:</span><span class="sxs-lookup"><span data-stu-id="de0a6-109">The following allocation methods can be used for ledger allocation rules:</span></span>

-   <span data-ttu-id="de0a6-110">**Bas** – Den här variabelmetoden används när allokeringen beror på det verkliga redovisningssaldot, baserat på filterkriterier.</span><span class="sxs-lookup"><span data-stu-id="de0a6-110">**Basis** – This variable method is used when the allocation depends on the actual ledger balance, based on filter criteria.</span></span> <span data-ttu-id="de0a6-111">Du kan till exempel allokera utgifter baserat på varje avdelnings försäljning i proportion till den totala försäljningen.</span><span class="sxs-lookup"><span data-stu-id="de0a6-111">For example, advertising expenses can be allocated based on each department's sales in proportion to the total departmental sales.</span></span>
-   <span data-ttu-id="de0a6-112">**Fast procentsats** och **Fast vikt** – För dessa metoder anges allokeringsprocent eller vikt direkt för regeln.</span><span class="sxs-lookup"><span data-stu-id="de0a6-112">**Fixed percentage** and **Fixed weight** – For these methods, the allocation percentage or weight is defined directly for the rule.</span></span> <span data-ttu-id="de0a6-113">Till exempel kan annonseringsutgifter allokeras så att avdelning A får 70 procent av annonseringsutgifterna och avdelning B får 30 procent.</span><span class="sxs-lookup"><span data-stu-id="de0a6-113">For example, advertising expenses can be allocated so that Department A receives 70 percent of the advertising expense and Department B receives 30 percent.</span></span>
-   <span data-ttu-id="de0a6-114">**Lika** – Den här metoden fördelar beloppet jämnt på varje definierad destination.</span><span class="sxs-lookup"><span data-stu-id="de0a6-114">**Equally** – This method distributes the amount equally to each defined destination.</span></span> <span data-ttu-id="de0a6-115">Om till exempel destination har definierats för avdelning A och avdelning B, kan annonseringsutgifter allokeras så att både avdelning A och avdelning B får 50 procent av annonseringsutgifterna.</span><span class="sxs-lookup"><span data-stu-id="de0a6-115">For example, if destinations are defined for Department A and Department B, advertising expenses can be allocated so that both Department A and Department B receive 50 percent of the advertising expense.</span></span>

<span data-ttu-id="de0a6-116">Om Bas används som allokeringsmetod för en allokeringsregel är lika med , måste du också definiera en separat basallokeringsregler för redovisning.</span><span class="sxs-lookup"><span data-stu-id="de0a6-116">If Basis is used as the allocation method for an allocation rule, you must also define separate ledger allocation basis rules.</span></span> <span data-ttu-id="de0a6-117">Processen ”Bearbeta allokeringsbegäran" gör det möjligt för användare att bearbeta redovisningallokeringsregeln och förhandsgranska de resulterande allokeringsjournalposterna innan de bokförs eller ta bort de beräknade allokeringarna.</span><span class="sxs-lookup"><span data-stu-id="de0a6-117">The "Process allocation request" process lets users process the ledger allocation rule and preview the resulting allocation journal entries before they either post or delete the calculated allocations.</span></span>

## <a name="components-of-ledger-allocation-rules"></a><span data-ttu-id="de0a6-118">Komponenter för allokeringsregler för redovisning</span><span class="sxs-lookup"><span data-stu-id="de0a6-118">Components of ledger allocation rules</span></span>
<span data-ttu-id="de0a6-119">En allokeringsregel har fyra huvudsakliga komponenter – allmän, källa, destination och motbokning.</span><span class="sxs-lookup"><span data-stu-id="de0a6-119">Each allocation rule has four components: general, source, destination, and offset.</span></span> <span data-ttu-id="de0a6-120">En ytterligare komponent, allokeringsbasregler för redovisning, krävs om Bas används som allokeringsmetod.</span><span class="sxs-lookup"><span data-stu-id="de0a6-120">An additional component, ledger allocation bases rules, is required if Basis is used as the allocation method.</span></span> <span data-ttu-id="de0a6-121">Varje komponent omfattar viktig information som krävs för att bearbeta processallokeringarna.</span><span class="sxs-lookup"><span data-stu-id="de0a6-121">Each component provides a critical piece of the information that is required in order to process allocations.</span></span>

-   <span data-ttu-id="de0a6-122">**Allmän** – Den allmänna komponenten är där användaren anger alternativ, bland annat allokeringsmetod, inställningar för koncernintern regel och om regeln är aktiv eller inte.</span><span class="sxs-lookup"><span data-stu-id="de0a6-122">**General** – This component is where the user specifies options such as the allocation method, intercompany rule settings, and whether the rule is active.</span></span>
-   <span data-ttu-id="de0a6-123">**Källa** – Denna komponent är där användaren anger källadatan för allokeringen.</span><span class="sxs-lookup"><span data-stu-id="de0a6-123">**Source** – This component is where the user specifies the source data for the allocation.</span></span> <span data-ttu-id="de0a6-124">Allokeringen kan baseras på redovisningssaldo (**Datakälla** = **Redovisning**) eller fasta belopp (**Datakälla** = **Fast värde**).</span><span class="sxs-lookup"><span data-stu-id="de0a6-124">Allocation can be based on ledger balances (**Data source** = **Ledger**) or fixed amounts (**Data source** = **Fixed value**).</span></span> <span data-ttu-id="de0a6-125">När **Datakälla** ställs in på **Redovisning** måste källafiltervillkoret definieras för redovisningallokeringsregeln (exempelvis för annonseringsutgifterna).</span><span class="sxs-lookup"><span data-stu-id="de0a6-125">When **Data source** is set to **Ledger**, source filter criteria must be defined for the ledger allocation rule (for example, for the advertising expenses).</span></span>
-   <span data-ttu-id="de0a6-126">**Destination** – Denna komponent anger hur resultatet från allokeringsberäkningen ska fördelas och bokföras.</span><span class="sxs-lookup"><span data-stu-id="de0a6-126">**Destination** – This component defines how the result of the allocation calculation should be distributed and accounted for.</span></span> <span data-ttu-id="de0a6-127">Till exempel kan det finnas en destinationsrad för varje avdelning.</span><span class="sxs-lookup"><span data-stu-id="de0a6-127">For example, there can be one destination line for each department.</span></span>
-   <span data-ttu-id="de0a6-128">**Motboka** Denna komponent definierar hur huvudkonton och dimensioner ska bestämmas för motbokningsposter som överensstämmer med posterna.</span><span class="sxs-lookup"><span data-stu-id="de0a6-128">**Offset** – This component defines how main accounts and dimensions should be determined for the offset entries that balance the destination entries.</span></span> <span data-ttu-id="de0a6-129">användardefinierade alternativ används vanligtvis i stället för de konton och dimensioner som baseras på källan.</span><span class="sxs-lookup"><span data-stu-id="de0a6-129">User-defined options are typically used instead of accounts and dimensions that are based on the source.</span></span> <span data-ttu-id="de0a6-130">När **Datakälla** är inställd på **Fast värde**, kan inte **Källa** användas som ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="de0a6-130">When **Data source** is set to **Fixed value**, **Source** can't be used as an option.</span></span>
-   <span data-ttu-id="de0a6-131">**Basallokeringsregler för redovisning** – Dessa regler använder sin egen källafiltervillkor som avgör vilka redovisningssaldon som ska användas för allokering (exempelvis intäkt per avdelning.)</span><span class="sxs-lookup"><span data-stu-id="de0a6-131">**Ledger allocation basis rules** – These rules use their own source filter criteria to determine which ledger balances should be used for allocation (for example, the revenue per department).</span></span> <span data-ttu-id="de0a6-132">Varje allokeringsbasregel kan användas för många allokeringsregler.</span><span class="sxs-lookup"><span data-stu-id="de0a6-132">Each allocation basis rule can be used with multiple allocation rules.</span></span>





