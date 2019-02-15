---
title: Konsekvenskontroll av butikstransaktion
description: I det här avsnittet beskrivs funktionen för konsekvenskontroll av butikstransaktioner i Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 01/08/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: db01a12b92574b41f1f4fe7281c23992e0d36027
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "302907"
---
# <a name="retail-transaction-consistency-checker"></a><span data-ttu-id="4856d-103">Konsekvenskontroll av butikstransaktion</span><span class="sxs-lookup"><span data-stu-id="4856d-103">Retail transaction consistency checker</span></span>


[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

<span data-ttu-id="4856d-104">I det här avsnittet beskrivs funktionen för konsekvenskontroll av butikstransaktioner som infördes i Microsoft Dynamics 365 for Finance and Operations version 8.1.3.</span><span class="sxs-lookup"><span data-stu-id="4856d-104">This topic describes the retail transaction consistency checker functionality introduced in Microsoft Dynamics 365 for Finance and Operations version 8.1.3.</span></span> <span data-ttu-id="4856d-105">Konsekvenskontrollen identifierar och isolerar inkonsekventa transaktioner innan de används i bokföringsprocessen för utdrag.</span><span class="sxs-lookup"><span data-stu-id="4856d-105">The consistency checker identifies and isolates inconsistent transactions before they are picked up by the statement posting process.</span></span>

<span data-ttu-id="4856d-106">Det går inte att bokföra utdrag i Retail om det finns inkonsekventa data i butikens transaktionsregister.</span><span class="sxs-lookup"><span data-stu-id="4856d-106">When a statement is posted in Retail, posting can fail due to inconsistent data in the retail transaction tables.</span></span> <span data-ttu-id="4856d-107">Dataproblemet kan bero på oförutsedda problem i kassaprogrammet, eller om transaktioner har importerats felaktigt från kassasystem från tredje part.</span><span class="sxs-lookup"><span data-stu-id="4856d-107">The data issue may be caused by by unforeseen issues in the point of sale (POS) application, or if transactions were incorrectly imported from third-party POS systems.</span></span> <span data-ttu-id="4856d-108">Dessa inkonsekvenser kan till exempel uppenbara sig på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="4856d-108">Examples of how these inconsistencies may appear include:</span></span> 

  - <span data-ttu-id="4856d-109">Transaktionssumman i huvudtabellen stämmer inte överens med transaktionssumman på raderna.</span><span class="sxs-lookup"><span data-stu-id="4856d-109">The transaction total on the header table does not match the transaction total on the lines.</span></span>
  - <span data-ttu-id="4856d-110">Radantalet i huvudtabellen stämmer inte överens med antalet rader i transaktionstabellen.</span><span class="sxs-lookup"><span data-stu-id="4856d-110">The line count on the header table does not match with the number of lines in the transaction table.</span></span>
  - <span data-ttu-id="4856d-111">Momsen i huvudtabellen stämmer inte överens med momsbeloppet på raderna.</span><span class="sxs-lookup"><span data-stu-id="4856d-111">Taxes on the header table do not match the tax amount on the lines.</span></span> 
  
<span data-ttu-id="4856d-112">När inkonsekventa transaktioner fångas upp i bokföringsprocessen för utdrag, skapas inkonsekventa försäljningsfakturor och betalningsjournaler, och bokföringsprocessen för utdrag går inte att utföra.</span><span class="sxs-lookup"><span data-stu-id="4856d-112">When inconsistent transactions are picked up by the statement posting process, inconsistent sales invoices and payment journals are created, and the entire statement posting process fails as a result.</span></span> <span data-ttu-id="4856d-113">När utdragen ska återställas från ett sådant tillstånd krävs komplexa datakorrigeringar av flera transaktionsregister.</span><span class="sxs-lookup"><span data-stu-id="4856d-113">Recovering the statements from such a state involves complex data fixes across multiple transaction tables.</span></span> <span data-ttu-id="4856d-114">Konsekvenskontrollen av butikstransaktioner förhindrar sådana problem.</span><span class="sxs-lookup"><span data-stu-id="4856d-114">The retail transaction consistency checker prevents such issues.</span></span>

<span data-ttu-id="4856d-115">I följande diagram visas bokföringsprocessen där konsekvenskontroll av transaktioner tillämpas.</span><span class="sxs-lookup"><span data-stu-id="4856d-115">The following chart illustrates the posting process with the transaction consistency checker.</span></span>

<span data-ttu-id="4856d-116">![Bokföringsprocess för utdrag med konsekvenskontroll av butikstransaktioner](./media/validchecker.png "Bokföringsprocess för utdrag med konsekvenskontroll av butikstransaktioner")</span><span class="sxs-lookup"><span data-stu-id="4856d-116">![Statement posting process with retail transaction consistency checker](./media/validchecker.png "Statement posting process with retail transsaction consistency checker")</span></span>

<span data-ttu-id="4856d-117">Batchprocessen **Validera butikstransaktioner** kontrollerar att butikens transaktionsregister är konsekventa i följande scenarier.</span><span class="sxs-lookup"><span data-stu-id="4856d-117">The **Validate store transactions** batch process checks the consistency of the retail transaction tables for the following scenarios.</span></span>

- <span data-ttu-id="4856d-118">Kundkonto – Validerar att kundkontot i butikens transaktionsregister finns i huvudkontorets kundmall.</span><span class="sxs-lookup"><span data-stu-id="4856d-118">Customer account - Validates that the customer account in the retail transaction tables exists in the HQ customer master.</span></span>
- <span data-ttu-id="4856d-119">Radräkning – Validerar att antalet rader, som anges i transaktionsregistret huvudtabell, motsvarar antalet rader i försäljningstransaktionsregistren.</span><span class="sxs-lookup"><span data-stu-id="4856d-119">Line count - Validates that the number of lines, as captured on the transaction header table, matches the number of lines in the sales transaction tables.</span></span>

## <a name="set-up-the-consistency-checker"></a><span data-ttu-id="4856d-120">Ställ in konsekvenskontrollen</span><span class="sxs-lookup"><span data-stu-id="4856d-120">Set up the consistency checker</span></span>
<span data-ttu-id="4856d-121">Konfigurera batchprocessen "Validera butikstransaktioner" i **Butik \> Butikens IT \> Kassabokföring** för periodiska körningar.</span><span class="sxs-lookup"><span data-stu-id="4856d-121">Configure the "Validate store transactions" batch process, at **Retail \> Retail IT \> POS posting**, for periodic runs.</span></span> <span data-ttu-id="4856d-122">Batchjobbet kan schemaläggas utifrån butikens organisationshierarki, vilket påminner om hur processerna "Beräkna utdrag i batch" och "Bokför utdrag i batch" konfigureras.</span><span class="sxs-lookup"><span data-stu-id="4856d-122">The batch job can be scheduled based on store organization hierarchy, similar to how the "Calculate statement in batch" and "Post statement in batch" processes are set up.</span></span> <span data-ttu-id="4856d-123">Vi rekommenderar att du konfigurerar den här batchprocessen så att den körs flera gånger under en dag och schemalägga den så att den körs i slutet av varje P-jobbskörning.</span><span class="sxs-lookup"><span data-stu-id="4856d-123">We recommend that you configure this batch process to run multiple times in a day and schedule it so that it runs at the end of every P-job execution.</span></span>

## <a name="results-of-validation-process"></a><span data-ttu-id="4856d-124">Resultat av valideringsprocessen</span><span class="sxs-lookup"><span data-stu-id="4856d-124">Results of validation process</span></span>
<span data-ttu-id="4856d-125">Resultaten av batchprocessens valideringskontroll märks i motsvarande butikstransaktion.</span><span class="sxs-lookup"><span data-stu-id="4856d-125">The results of the validation check by the batch process are tagged on the appropriate retail transaction.</span></span> <span data-ttu-id="4856d-126">Fältet **Valideringsstatus** i butikens transaktionspost anges antingen till **Slutförd** eller **Fel**, och datumet för den senaste valideringskörningen visas i fältet **Senaste valideringstid**.</span><span class="sxs-lookup"><span data-stu-id="4856d-126">The **Validation status** field on the retail transaction record is either set to **Successful** or **Error**, and the date of the last validation run appears on the **Last validation time** field.</span></span>

<span data-ttu-id="4856d-127">Om du vill visa en mer beskrivande feltext som berör ett valideringsfel markerar du aktuell butikstransaktionspost i Retail och klickar på **Valideringsfel**.</span><span class="sxs-lookup"><span data-stu-id="4856d-127">To view more descriptive error text relating to a validation failure, select the relevant retail store transaction record and click the **Validation errors** button.</span></span>

<span data-ttu-id="4856d-128">Transaktionerna som inte klarar valideringskontrollen och de transaktioner som ännu inte validerats används inte i utdragen.</span><span class="sxs-lookup"><span data-stu-id="4856d-128">Transactions that fail the validation check and transactions that have not yet been validated will not be pulled into statements.</span></span> <span data-ttu-id="4856d-129">Under processen "Beräkna utdrag" meddelas användarna om det finns transaktioner som kan ha inkluderats i uttrycket men inte som inte har det.</span><span class="sxs-lookup"><span data-stu-id="4856d-129">During the "Calculate statement" process, users will be notified if there are transactions that could have been included in the statement but weren't.</span></span>

<span data-ttu-id="4856d-130">Om ett valideringsfel inträffar går det bara att korrigera felet genom att kontakta Microsoft Support.</span><span class="sxs-lookup"><span data-stu-id="4856d-130">If a validation error is found, the only way to fix the error is to contact Microsoft Support.</span></span> <span data-ttu-id="4856d-131">I en framtida version kommer en funktion att läggas till som gör att användarna kan korrigera posterna via användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="4856d-131">In a future release, capability will be added so that users can fix the records that failed through the user interface.</span></span> <span data-ttu-id="4856d-132">Funktioner för loggning och granskning kommer också att införas, vilka gör det möjligt att spåra ändringshistoriken.</span><span class="sxs-lookup"><span data-stu-id="4856d-132">Logging and auditing capabilities will also be made available to trace the history of the modifications.</span></span>

> [!NOTE]
> <span data-ttu-id="4856d-133">Ytterligare valideringsregler för andra scenarier kommer i framtida versioner.</span><span class="sxs-lookup"><span data-stu-id="4856d-133">Additional validation rules to support more scenarios will be added in a future release.</span></span>
