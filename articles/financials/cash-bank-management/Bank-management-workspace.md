---
title: "Arbetsyta för bankhantering"
description: "Det här ämnet innehåller information om Arbetsyta för bankhantering. Den här arbetsytan visar information som är relaterat till företagets bankkonton och omfattar en sammanfattningsvy och en sida för analys. Sammanfattningen innehåller sammanfattningsrutor, bankkontoinformation, saldodiagram och relaterad information. Sidan analys använder funktionerna i Microsoft Power BI för att visa visuella som är relaterade till bankkontosaldon."
author: saraschi2
manager: AnnBe
ms.date: 05/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 91a6c2e5aeee4a10ffbd574f99218d49f9a19bbc
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="bank-management-workspace"></a><span data-ttu-id="42016-106">Arbetsyta för bankhantering</span><span class="sxs-lookup"><span data-stu-id="42016-106">Bank management workspace</span></span>

<span data-ttu-id="42016-107">Arbetsytan **Bankhantering** visar information som hör till företagets bankkonton.</span><span class="sxs-lookup"><span data-stu-id="42016-107">The **Bank management** workspace shows information that is related to company bank accounts.</span></span> <span data-ttu-id="42016-108">Den här arbetsytan innehåller en **sammanfattningsvy** och en **analyssida**.</span><span class="sxs-lookup"><span data-stu-id="42016-108">This workspace includes a **Summary** view and an **Analytics** page.</span></span> <span data-ttu-id="42016-109">**Sammanfattningsvyn** innehåller sammanfattningsrutor, bankkontoinformation, saldodiagram och relaterad information.</span><span class="sxs-lookup"><span data-stu-id="42016-109">The **Summary** view shows summary tiles, bank account information, a balance chart, and related information.</span></span> <span data-ttu-id="42016-110">Sidan **analys** använder funktionerna i Microsoft Power BI för att visa visuella som är relaterade till bankkontosaldon.</span><span class="sxs-lookup"><span data-stu-id="42016-110">The **Analytics** page uses the capabilities of Microsoft Power BI to show visuals that are related to bank account balances.</span></span>

## <a name="summary-view"></a><span data-ttu-id="42016-111">Sammanfattningsvy</span><span class="sxs-lookup"><span data-stu-id="42016-111">Summary view</span></span>

### <a name="summary"></a><span data-ttu-id="42016-112">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="42016-112">Summary</span></span>

<span data-ttu-id="42016-113">Rutorna i avsnittet **sammanfattning** ger en översikt över dina bankkonton och ger snabb åtkomst till de sidor som du behöver använda oftast.</span><span class="sxs-lookup"><span data-stu-id="42016-113">The tiles in the **Summary** section give an overview of your bank accounts and provide quick access to the pages that you most often have to use.</span></span> <span data-ttu-id="42016-114">Information för bankavstämning gäller funktionen avancerad bankavstämning.</span><span class="sxs-lookup"><span data-stu-id="42016-114">The bank reconciliation information is specific to the Advanced bank reconciliation functionality.</span></span> <span data-ttu-id="42016-115">Informationen finns endast för de bankkonton som har alternativet inställt på **avancerad bankavstämning** till **Ja** på sidan **bankkonto**.</span><span class="sxs-lookup"><span data-stu-id="42016-115">Information is included only for those bank accounts that have the **Advanced bank reconciliation** option set to **Yes** on the **Bank account** page.</span></span> <span data-ttu-id="42016-116">Från avsnittet **sammanfattning** kan du importera elektroniska bankfilerna för bankkonton över alla juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="42016-116">From the **Summary** section, you can import electronic bank files for bank accounts across all legal entities.</span></span>

### <a name="bank-accounts"></a><span data-ttu-id="42016-117">Bankkonton</span><span class="sxs-lookup"><span data-stu-id="42016-117">Bank accounts</span></span>

<span data-ttu-id="42016-118">Varje bankkonto hos den juridiska personen representeras av ett kort i avsnittet **bankkonton**.</span><span class="sxs-lookup"><span data-stu-id="42016-118">Each bank account in the legal entity is represented by a card in the **Bank accounts** section.</span></span> <span data-ttu-id="42016-119">Aktuellt saldo visas och du kan rulla ned till de transaktioner som utgör det sammanfattande balansbeloppet.</span><span class="sxs-lookup"><span data-stu-id="42016-119">The current balance is shown, and you can drill down to the transactions that make up that summary balance amount.</span></span> <span data-ttu-id="42016-120">Beloppet **interimstransaktioner** låter dig också rulla ner till de transaktioner som utgör detta sammanfattande balansbelopp.</span><span class="sxs-lookup"><span data-stu-id="42016-120">The **Bridged transactions** amount also lets you drill down to the transactions that make up that summary amount.</span></span> <span data-ttu-id="42016-121">Interimstransaktioner är alla pågående transaktioner som har bokförts med hjälp av överbryggande funktioner, men som ännu inte har tagits emot.</span><span class="sxs-lookup"><span data-stu-id="42016-121">Bridged transactions are any pending transactions that have been posted by using bridging functionality, but that haven't yet been cleared.</span></span> <span data-ttu-id="42016-122">Beloppet **Väntar på saldo** är aktuellt saldo minus överbryggade eller pågående transaktioner.</span><span class="sxs-lookup"><span data-stu-id="42016-122">The **Pending balance** amount is the current balance minus the bridged, or pending, transactions.</span></span>

<span data-ttu-id="42016-123">Kortet visar även när bankkontot senast stämdes av.</span><span class="sxs-lookup"><span data-stu-id="42016-123">The card also shows when the bank account was last reconciled.</span></span> <span data-ttu-id="42016-124">Den här informationen visas endast om avancerad bankavstämning aktiveras för bankkontot.</span><span class="sxs-lookup"><span data-stu-id="42016-124">This information is shown only if Advanced bank reconciliation is enabled for the bank account.</span></span>

### <a name="balance"></a><span data-ttu-id="42016-125">Balans</span><span class="sxs-lookup"><span data-stu-id="42016-125">Balance</span></span>

<span data-ttu-id="42016-126">Diagrammet **Saldo** visar antingen historisk saldoinformation för det bankkonto som valts i avsnittet **bankkonton** eller en sammanfattning av information om alla bankkonton hos den juridiska personen historiska saldo.</span><span class="sxs-lookup"><span data-stu-id="42016-126">The **Balance** chart shows either historic balance information for the bank account that is selected in the **Bank accounts** section or a summary of historic balance information for all bank accounts in the legal entity.</span></span> <span data-ttu-id="42016-127">Denna information är tillgänglig för olika perioder: den aktuella veckan, innevarande månad, innevarande år, senaste fem åren och samtliga perioder (den fullständiga historiken över bankkontot).</span><span class="sxs-lookup"><span data-stu-id="42016-127">This information is available for various periods: the current week, the current month, the current year, the last five years, and all periods (the full history of the bank account).</span></span> 

<span data-ttu-id="42016-128">Om du förhandsgranskar diagrammet **Saldo** för ett enda bankkonto, visas historiska saldon i bankkontots valuta.</span><span class="sxs-lookup"><span data-stu-id="42016-128">If you're viewing the **Balance** chart for a single bank account, the historic balances are shown in the bank account currency.</span></span> <span data-ttu-id="42016-129">Om du visar diagrammet för alla bankkonton i den juridiska personen, visas historiska saldon i redovisningsvaluta.</span><span class="sxs-lookup"><span data-stu-id="42016-129">If you're viewing the chart for all bank accounts in the legal entity, the historic balances are shown in the accounting currency.</span></span>

<span data-ttu-id="42016-130">Information om när data senast uppdaterades visas högst upp i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="42016-130">Information about when the data was last updated appears at the top of the chart.</span></span> <span data-ttu-id="42016-131">Du kan uppdatera data enligt behov.</span><span class="sxs-lookup"><span data-stu-id="42016-131">You can update the data as you require.</span></span>

### <a name="related-information"></a><span data-ttu-id="42016-132">Relaterad information</span><span class="sxs-lookup"><span data-stu-id="42016-132">Related information</span></span>

<span data-ttu-id="42016-133">Från avsnittet **relaterad information** kan du öppna sidan **redovisningsjournal** för att slutföra banköverföringar.</span><span class="sxs-lookup"><span data-stu-id="42016-133">From the **Related information** section, you can open the **General journal** page to complete bank transfers.</span></span> <span data-ttu-id="42016-134">Du kan snabbt öppna sidorna **banktransaktioner** och **interimstransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="42016-134">You can also quickly open the **Bank transactions** and **Bridged transactions** pages.</span></span>

## <a name="analytics-view"></a><span data-ttu-id="42016-135">Analysvy</span><span class="sxs-lookup"><span data-stu-id="42016-135">Analytics view</span></span>

<span data-ttu-id="42016-136">Sidan **analys** ger viktiga mått om bankkonton i det aktuella företaget.</span><span class="sxs-lookup"><span data-stu-id="42016-136">The **Analytics** page provides important metrics about the bank accounts in the current company.</span></span> <span data-ttu-id="42016-137">Följande visualiseringar är tillgängliga på sidan.</span><span class="sxs-lookup"><span data-stu-id="42016-137">The following visualizations are available on the page:</span></span>

-   <span data-ttu-id="42016-138">Totalt banksaldo i systemvaluta</span><span class="sxs-lookup"><span data-stu-id="42016-138">Total bank balance in system currency</span></span>
-   <span data-ttu-id="42016-139">Saldo per juridisk person</span><span class="sxs-lookup"><span data-stu-id="42016-139">Balance by legal entity</span></span>
-   <span data-ttu-id="42016-140">Aktuellt utfall kontra prognostiserat saldot i bankkontots valuta</span><span class="sxs-lookup"><span data-stu-id="42016-140">Today’s actual vs forecasted balance in bank account currency</span></span>
-   <span data-ttu-id="42016-141">Saldo per bankkonto</span><span class="sxs-lookup"><span data-stu-id="42016-141">Balance by bank account</span></span>
-   <span data-ttu-id="42016-142">Saldo per valuta</span><span class="sxs-lookup"><span data-stu-id="42016-142">Balance by currency</span></span>

<span data-ttu-id="42016-143">Du kan visa bankanalys i alla företag från arbetsytan **kontantöversikt – alla företag**.</span><span class="sxs-lookup"><span data-stu-id="42016-143">You can view bank analytics across all companies from the **Cash overview – all companies** workspace.</span></span>
