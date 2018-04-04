---
title: Hantering av redovisningsjournaler
description: "Det här avsnittet innehåller en beskrivning av de funktioner i Microsoft Dynamics 365 for Finance and Operations som kan underlätta processen för allmänna journaler, och som även kan göra det enklare att garantera att rätt data hämtas in samt att interna kontroller inte påverkas."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: eb46613f805999753c2ab73ffb91a6fdae04c68e
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="general-journal-processing"></a><span data-ttu-id="39c8e-103">Hantering av redovisningsjournaler</span><span class="sxs-lookup"><span data-stu-id="39c8e-103">General journal processing</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="39c8e-104">Det här avsnittet innehåller en beskrivning av de funktioner i Microsoft Dynamics 365 for Finance and Operations som kan underlätta processen för allmänna journaler, och som även kan göra det enklare att garantera att rätt data hämtas in samt att interna kontroller inte påverkas.</span><span class="sxs-lookup"><span data-stu-id="39c8e-104">This articles describes capabilities in Microsoft Dynamics 365 for Finance and Operations that can help make general journal processing easier, and that can also help guarantee that correct data is captured and internal control isn't compromised.</span></span>  

<span data-ttu-id="39c8e-105">Journalnamn</span><span class="sxs-lookup"><span data-stu-id="39c8e-105">Journal names</span></span>

<span data-ttu-id="39c8e-106">Ett av de viktigaste områdena att konfigurera är journalnamn.</span><span class="sxs-lookup"><span data-stu-id="39c8e-106">One of the most important areas to set up is journal names.</span></span> <span data-ttu-id="39c8e-107">Det är en god idé att definiera specifika journalnamn för respektive ändamål, till exempel koncerninterna, periodiseringsjustering och felkorrigering.</span><span class="sxs-lookup"><span data-stu-id="39c8e-107">It's a good idea to define specific journal names for each purpose, such as intercompany, accrual adjustment, and error correction.</span></span> <span data-ttu-id="39c8e-108">Du kan skräddarsy varje journalnamn för att göra datainmatningen för varje ändamål lätt och säker.</span><span class="sxs-lookup"><span data-stu-id="39c8e-108">You can tailor each journal name to help make data entry for each purpose easy and secure.</span></span> 

<span data-ttu-id="39c8e-109">På **Journalnamn** sidan kan du ställa in följande element:</span><span class="sxs-lookup"><span data-stu-id="39c8e-109">On the **Journal names** page, you can set up the following elements:</span></span>

-   <span data-ttu-id="39c8e-110">**Arbetsflödesgodkännande** – För att öka den interna kontrollen, definiera journalarbetsflöden som upprättar gränser för granskning och godkännande av åtgärder, på grundval av kriterier såsom totala debetbeloppet.</span><span class="sxs-lookup"><span data-stu-id="39c8e-110">**Workflow approval** – To increase internal control, define journal workflows that establish materiality limits for review and approval steps, based on criteria such as total debit amount.</span></span> <span data-ttu-id="39c8e-111">Du ställer in arbetsflöden för allmänna journaler på sidan **Arbetsflöden för redovisning**.</span><span class="sxs-lookup"><span data-stu-id="39c8e-111">You set up workflows for the general journals on the** General ledger workflows** page.</span></span>
-   <span data-ttu-id="39c8e-112">**Standardvärden** – Välj standardvärdena för kvittning, valuta och finansiella mått.</span><span class="sxs-lookup"><span data-stu-id="39c8e-112">**Default values** – Select default values for offset accounts, currency, and financial dimensions.</span></span>
-   <span data-ttu-id="39c8e-113">**Journalkontroll** – Du kan ställa in begränsningar för företaget och kontotyp och även segmentvärden.</span><span class="sxs-lookup"><span data-stu-id="39c8e-113">**Journal control** – You can set up restrictions on the company and account type, and also the segment values.</span></span> 

<span data-ttu-id="39c8e-114">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="39c8e-114">**Examples**</span></span>

<span data-ttu-id="39c8e-115">Journalnamn kan endast användas för justeringar.</span><span class="sxs-lookup"><span data-stu-id="39c8e-115">A journal name can be used only for adjustments.</span></span> <span data-ttu-id="39c8e-116">I det här fallet kan du ange att endast **huvudbokskonton** är giltiga för alla företag.</span><span class="sxs-lookup"><span data-stu-id="39c8e-116">In this case, you can specify that only the **Ledger** account type is valid across all companies.</span></span> <span data-ttu-id="39c8e-117">[![Kontotyper för journalkontroll](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)</span><span class="sxs-lookup"><span data-stu-id="39c8e-117">[![Journal control account types](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)</span></span>

<span data-ttu-id="39c8e-118">Journalnamn kan användas endast för en viss sektor eller ett datumintervall för huvudbokskonton.</span><span class="sxs-lookup"><span data-stu-id="39c8e-118">A journal name can be used only for a specific segment or for a range for main accounts.</span></span> <span data-ttu-id="39c8e-119">[![Journalkontrollsegment](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)</span><span class="sxs-lookup"><span data-stu-id="39c8e-119">[![Journal control segment](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)</span></span>

<span data-ttu-id="39c8e-120">**Automatisk återföring** alternativet finns tillgängligt i allmänna journaler.</span><span class="sxs-lookup"><span data-stu-id="39c8e-120">The **Automatic reversal** option is available in general journals.</span></span> <span data-ttu-id="39c8e-121">Du kan till exempel ha en periodiserad justering där det aktuella dokumentet har inte bearbetats, som visas i följande illustration.</span><span class="sxs-lookup"><span data-stu-id="39c8e-121">For example, you have an accrual adjustment where the actual document hasn't yet been processed, as shown in the following illustration.</span></span>
<span data-ttu-id="39c8e-122">[![Allmän journalåterföring](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png)</span><span class="sxs-lookup"><span data-stu-id="39c8e-122">[![General journal reversing](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png)</span></span> 

<span data-ttu-id="39c8e-123">Microsoft Excel-tillägget för poster i redovisningsjournal ger en extra nivå av automatisering och gör dataregistreringen lättare.</span><span class="sxs-lookup"><span data-stu-id="39c8e-123">The Microsoft Excel add-in for journal entry provides an additional level of automation and makes data entry easier.</span></span> <span data-ttu-id="39c8e-124">**Öppna rader i Excel** åtgärden är tillgänglig i **Allmän journal** och **Journalverifikat** sidor.</span><span class="sxs-lookup"><span data-stu-id="39c8e-124">The **Open lines in Excel** action is available on the **General journal** and **Journal voucher** pages.</span></span> 

<span data-ttu-id="39c8e-125">På **Periodiska journaler** sidan kan du ställa in återkommande journaler till automatisk journalbearbetning.</span><span class="sxs-lookup"><span data-stu-id="39c8e-125">On the **Periodic journals** page, you can set up recurring journals to automate journal processing.</span></span> 

<span data-ttu-id="39c8e-126">Du kan använda verifikationsmallar när som helst.</span><span class="sxs-lookup"><span data-stu-id="39c8e-126">You can use voucher templates at any time.</span></span> <span data-ttu-id="39c8e-127">På sidan **Allmänna journaler** finns åtgärderna **Spara** och **Välj verifikationsmall** på sidan **Journalverifikation**, under **Funktioner** för verifikationsraderna.</span><span class="sxs-lookup"><span data-stu-id="39c8e-127">On the **General journals** page, the **Save** and **Select voucher template** actions are found on the **Journal voucher** page, under **Functions** for the voucher lines.</span></span>

## <a name="related-setup"></a><span data-ttu-id="39c8e-128">Relaterade inställningar</span><span class="sxs-lookup"><span data-stu-id="39c8e-128">Related setup</span></span>
<span data-ttu-id="39c8e-129">Följande inställningar är inte specifika för allmänna journaler, men kommer att garantera korrekt dataregistrering, enkelt.</span><span class="sxs-lookup"><span data-stu-id="39c8e-129">The following setup isn't specific to general journals, but will help guarantee that data entry is correct data and easy.</span></span>

### <a name="main-account"></a><span data-ttu-id="39c8e-130">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="39c8e-130">Main account</span></span>

<span data-ttu-id="39c8e-131">Huvudkontoinställningen ger flera alternativ för allmän journal bearbetning:</span><span class="sxs-lookup"><span data-stu-id="39c8e-131">The main account setup provides many options for general journal processing:</span></span>

-   <span data-ttu-id="39c8e-132">**D/K-behov** – Använd det här alternativet om en huvud konto är begränsat till debet eller kredit transaktioner.</span><span class="sxs-lookup"><span data-stu-id="39c8e-132">**DC/CR requirement** – Use this option if a main account is limited to debit or credit transactions.</span></span> <span data-ttu-id="39c8e-133">Inställningen verifieras när en journal är validerad eller publiceras.</span><span class="sxs-lookup"><span data-stu-id="39c8e-133">The setup is verified when a journal is validated or posted.</span></span>
-   <span data-ttu-id="39c8e-134">**Standardmotkonto**</span><span class="sxs-lookup"><span data-stu-id="39c8e-134">**Default offset account**</span></span>
-   <span data-ttu-id="39c8e-135">**Uppskjutet** – Stoppa ett huvudkonto för inmatning av data över alla företag eller för ett specifikt företag/juridiska enheter.</span><span class="sxs-lookup"><span data-stu-id="39c8e-135">**Suspended** – Suspend a main account for data entry across all companies or for a specific company/legal entities.</span></span>
-   <span data-ttu-id="39c8e-136">**Tillåt inte manuell inmatning** – Förhindra användare från att manuellt ange ett värde för kontot i journaler.</span><span class="sxs-lookup"><span data-stu-id="39c8e-136">**Do not allow manual entry** – Prevent users from manually entering a value for the account in journals.</span></span>
-   <span data-ttu-id="39c8e-137">**Standard/Validera valuta**</span><span class="sxs-lookup"><span data-stu-id="39c8e-137">**Default/Validate currency**</span></span>
-   <span data-ttu-id="39c8e-138">**Juridisk person åsidosätter** – Denna inställning är specifik för definierade företag/juridiska enhet:</span><span class="sxs-lookup"><span data-stu-id="39c8e-138">**Legal entity override** – This setup is specific to the defined company/legal entity:</span></span>
    -   <span data-ttu-id="39c8e-139">**Standard/Validera moms**</span><span class="sxs-lookup"><span data-stu-id="39c8e-139">**Default/Validate sales tax**</span></span>
    -   <span data-ttu-id="39c8e-140">**Standarddimension** – **Inte fast** eller **Fast värde**.</span><span class="sxs-lookup"><span data-stu-id="39c8e-140">**Default dimension** – **Not fixed** or **Fixed value**.</span></span> <span data-ttu-id="39c8e-141">**Fast värde** kommer att bidra till att garantera att alla konteringar för detta konto använder alltid något dimensionsvärde som är inställt som **fast**.</span><span class="sxs-lookup"><span data-stu-id="39c8e-141">**Fixed value** will help guarantee that all postings for this main account always use any dimension value that is set up as **Fixed**.</span></span>
-   <span data-ttu-id="39c8e-142">**Bokföringsvalidering**</span><span class="sxs-lookup"><span data-stu-id="39c8e-142">**Posting validation**</span></span>
    -   <span data-ttu-id="39c8e-143">**Användarvalidering** – Det här alternativet styr vilka användare som tillåts bokföra på huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="39c8e-143">**User validation** – This option controls which users are allowed to post to a main account.</span></span>
    -   <span data-ttu-id="39c8e-144">**Konteringstypvalidering** – Med det här alternativet styr vilka konteringstyper som tillåts för huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="39c8e-144">**Posting type validation** – This option controls which posting types are allowed for a main account.</span></span>

### <a name="accounting-structures-and-advanced-rules-structures"></a><span data-ttu-id="39c8e-145">Redovisningsstrukturer och avancerade regler strukturer</span><span class="sxs-lookup"><span data-stu-id="39c8e-145">Accounting structures and advanced rules structures</span></span>

<span data-ttu-id="39c8e-146">Redovisningsstrukturer och avancerade regler strukturer är oerhört viktiga för att garantera att de data som krävs för ekonomisk rapportering och uppföljning av prestationer är fångade under allmän journal bearbetning och all dokumentation.</span><span class="sxs-lookup"><span data-stu-id="39c8e-146">Accounting structures and advanced rules structures are extremely important for guaranteeing that the data that is required for financial reporting and performance tracking is captured during general journal processing and any documentation.</span></span> <span data-ttu-id="39c8e-147">Redovisningsstrukturer och avancerade regler strukturer kan du skräddarsy data entry-upplevelse.</span><span class="sxs-lookup"><span data-stu-id="39c8e-147">Accounting structures and advanced rules structures let you tailor the data entry experience.</span></span> <span data-ttu-id="39c8e-148">Du kan registrera data endast för finansiella mått som är relevanta i varje situation, och kan också genomdriva kravet på att obligatorisk och korrekt data alltid finnas fångat.</span><span class="sxs-lookup"><span data-stu-id="39c8e-148">You can allow data entry only for financial dimensions that are relevant in each situation, and can also enforce the requirement that mandatory and correct data always be captured.</span></span>

<span data-ttu-id="39c8e-149">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="39c8e-149">For more information, see the following topics:</span></span>
- <span data-ttu-id="39c8e-150">[Planering: Kontoplan](plan-chart-of-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="39c8e-150">[Planning: Chart of accounts](plan-chart-of-accounts.md).</span></span> 
- [<span data-ttu-id="39c8e-151">Skapa avancerade regler för journaler</span><span class="sxs-lookup"><span data-stu-id="39c8e-151">Create advanced rules for journals</span></span>](tasks/create-advanced-rules-journals.md)
- [<span data-ttu-id="39c8e-152">Skapa en post i en redovisningsjournal med hjälp av en mall</span><span class="sxs-lookup"><span data-stu-id="39c8e-152">Create a journal entry using a template</span></span>](tasks/create-journal-entry-template.md)
- [<span data-ttu-id="39c8e-153">Skapa och validera journaler</span><span class="sxs-lookup"><span data-stu-id="39c8e-153">Create and validate journals</span></span>](tasks/create-validate-journals.md)
- [<span data-ttu-id="39c8e-154">Bokför periodiska journaler</span><span class="sxs-lookup"><span data-stu-id="39c8e-154">Post periodic journals</span></span>](tasks/post-periodic-journals.md)
- [<span data-ttu-id="39c8e-155">Bearbeta journal för redovisningsallokering</span><span class="sxs-lookup"><span data-stu-id="39c8e-155">Process ledger allocation journal</span></span>](tasks/process-ledger-allocation-journal.md)



