---
title: Hantering av allmänna journaler
description: Det här avsnittet innehåller en beskrivning av de funktioner i Microsoft Dynamics 365 Finance som kan underlätta processen för allmänna journaler och som även kan göra det enklare att garantera att rätt data hämtas in samt att interna kontroller inte påverkas.
author: ShylaThompson
manager: AnnBe
ms.date: 08/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f9f19f0714fc160792a29261e21fe4ec8d62c4b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249249"
---
# <a name="general-journal-processing"></a><span data-ttu-id="a559f-103">Hantering av allmänna journaler</span><span class="sxs-lookup"><span data-stu-id="a559f-103">General journal processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a559f-104">Det här avsnittet innehåller en beskrivning av de funktioner som kan underlätta processen för allmänna journaler och som även kan göra det enklare att garantera att rätt data hämtas in samt att interna kontroller inte påverkas.</span><span class="sxs-lookup"><span data-stu-id="a559f-104">This topic describes capabilities that can help make general journal processing easier, and that can also help ensure that correct data is captured and internal control isn't compromised.</span></span>  

## <a name="journal-names"></a><span data-ttu-id="a559f-105">Journalnamn</span><span class="sxs-lookup"><span data-stu-id="a559f-105">Journal names</span></span>

<span data-ttu-id="a559f-106">Ett av de viktigaste områdena att konfigurera är journalnamn.</span><span class="sxs-lookup"><span data-stu-id="a559f-106">One of the most important areas to set up is journal names.</span></span> <span data-ttu-id="a559f-107">Det är en god idé att definiera specifika journalnamn för respektive ändamål, till exempel koncerninterna, periodiseringsjustering och felkorrigering.</span><span class="sxs-lookup"><span data-stu-id="a559f-107">It's a good idea to define specific journal names for each purpose, such as intercompany, accrual adjustment, and error correction.</span></span> <span data-ttu-id="a559f-108">Du kan skräddarsy varje journalnamn för att göra datainmatningen för varje ändamål lätt och säker.</span><span class="sxs-lookup"><span data-stu-id="a559f-108">You can tailor each journal name to help make data entry for each purpose easy and secure.</span></span> 

<span data-ttu-id="a559f-109">På **Journalnamn** sidan kan du ställa in följande element:</span><span class="sxs-lookup"><span data-stu-id="a559f-109">On the **Journal names** page, you can set up the following elements:</span></span>

-   <span data-ttu-id="a559f-110">**Arbetsflödesgodkännande** – För att öka den interna kontrollen, definiera journalarbetsflöden som upprättar gränser för granskning och godkännande av åtgärder, på grundval av kriterier såsom totala debetbeloppet.</span><span class="sxs-lookup"><span data-stu-id="a559f-110">**Workflow approval** – To increase internal control, define journal workflows that establish materiality limits for review and approval steps, based on criteria such as total debit amount.</span></span> <span data-ttu-id="a559f-111">Du ställer in arbetsflöden för allmänna journaler på **Redovisningsarbetsflöden** sidan.</span><span class="sxs-lookup"><span data-stu-id="a559f-111">You set up workflows for the general journals on the **General ledger workflows** page.</span></span>
-   <span data-ttu-id="a559f-112">**Standardvärden** – Välj standardvärdena för kvittning, valuta och finansiella mått.</span><span class="sxs-lookup"><span data-stu-id="a559f-112">**Default values** – Select default values for offset accounts, currency, and financial dimensions.</span></span>
-   <span data-ttu-id="a559f-113">**Journalkontroll** – Du kan ställa in begränsningar för företaget och kontotyp och även segmentvärden.</span><span class="sxs-lookup"><span data-stu-id="a559f-113">**Journal control** – You can set up restrictions on the company and account type, and also the segment values.</span></span> 

<span data-ttu-id="a559f-114">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="a559f-114">**Examples**</span></span>

<span data-ttu-id="a559f-115">Journalnamn kan endast användas för justeringar.</span><span class="sxs-lookup"><span data-stu-id="a559f-115">A journal name can be used only for adjustments.</span></span> <span data-ttu-id="a559f-116">I det här fallet kan du ange att endast **huvudbokskonton** är giltiga för alla företag.</span><span class="sxs-lookup"><span data-stu-id="a559f-116">In this case, you can specify that only the **Ledger** account type is valid across all companies.</span></span> 

<span data-ttu-id="a559f-117">[![Kontotyper för journalkontroll](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)</span><span class="sxs-lookup"><span data-stu-id="a559f-117">[![Journal control account types](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)</span></span>

<span data-ttu-id="a559f-118">Journalnamn kan användas endast för en viss sektor eller ett datumintervall för huvudbokskonton.</span><span class="sxs-lookup"><span data-stu-id="a559f-118">A journal name can be used only for a specific segment or for a range for main accounts.</span></span> 

<span data-ttu-id="a559f-119">[![Journalkontrollsegment](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)</span><span class="sxs-lookup"><span data-stu-id="a559f-119">[![Journal control segment](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)</span></span>

<span data-ttu-id="a559f-120">**Automatisk återföring** alternativet finns tillgängligt i allmänna journaler.</span><span class="sxs-lookup"><span data-stu-id="a559f-120">The **Automatic reversal** option is available in general journals.</span></span> <span data-ttu-id="a559f-121">Du kan till exempel ha en periodiserad justering där det aktuella dokumentet har inte bearbetats, som visas i följande illustration.</span><span class="sxs-lookup"><span data-stu-id="a559f-121">For example, you have an accrual adjustment where the actual document hasn't yet been processed, as shown in the following illustration.</span></span>
<span data-ttu-id="a559f-122">[![Allmän journalåterföring](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png)</span><span class="sxs-lookup"><span data-stu-id="a559f-122">[![General journal reversing](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png)</span></span> 

<span data-ttu-id="a559f-123">Microsoft Excel-tillägget för poster i redovisningsjournal ger en extra nivå av automatisering och gör dataregistreringen lättare.</span><span class="sxs-lookup"><span data-stu-id="a559f-123">The Microsoft Excel add-in for journal entry provides an additional level of automation and makes data entry easier.</span></span> <span data-ttu-id="a559f-124">**Öppna rader i Excel** åtgärden är tillgänglig i **Allmän journal** och **Journalverifikat** sidor.</span><span class="sxs-lookup"><span data-stu-id="a559f-124">The **Open lines in Excel** action is available on the **General journal** and **Journal voucher** pages.</span></span> 

<span data-ttu-id="a559f-125">På **Periodiska journaler** sidan kan du ställa in återkommande journaler till automatisk journalbearbetning.</span><span class="sxs-lookup"><span data-stu-id="a559f-125">On the **Periodic journals** page, you can set up recurring journals to automate journal processing.</span></span> 

<span data-ttu-id="a559f-126">Du kan använda verifikationsmallar när som helst.</span><span class="sxs-lookup"><span data-stu-id="a559f-126">You can use voucher templates at any time.</span></span> <span data-ttu-id="a559f-127">På sidan **Allmänna journaler** finns åtgärderna **Spara** och **Välj verifikationsmall** på sidan **Journalverifikation**, under **Funktioner** för verifikationsraderna.</span><span class="sxs-lookup"><span data-stu-id="a559f-127">On the **General journals** page, the **Save** and **Select voucher template** actions are found on the **Journal voucher** page, under **Functions** for the voucher lines.</span></span>

## <a name="related-setup"></a><span data-ttu-id="a559f-128">Relaterade inställningar</span><span class="sxs-lookup"><span data-stu-id="a559f-128">Related setup</span></span>
<span data-ttu-id="a559f-129">Följande inställningar är inte specifika för allmänna journaler, men kommer att garantera korrekt dataregistrering, enkelt.</span><span class="sxs-lookup"><span data-stu-id="a559f-129">The following setup isn't specific to general journals, but will help ensure that data entry is correct data and easy.</span></span>

### <a name="main-account"></a><span data-ttu-id="a559f-130">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="a559f-130">Main account</span></span>

<span data-ttu-id="a559f-131">Huvudkontoinställningen ger flera alternativ för allmän journal bearbetning:</span><span class="sxs-lookup"><span data-stu-id="a559f-131">The main account setup provides many options for general journal processing:</span></span>

-   <span data-ttu-id="a559f-132">**D/K-behov** – Använd det här alternativet om en huvud konto är begränsat till debet eller kredit transaktioner.</span><span class="sxs-lookup"><span data-stu-id="a559f-132">**DC/CR requirement** – Use this option if a main account is limited to debit or credit transactions.</span></span> <span data-ttu-id="a559f-133">Inställningen verifieras när en journal är validerad eller publiceras.</span><span class="sxs-lookup"><span data-stu-id="a559f-133">The setup is verified when a journal is validated or posted.</span></span>

-   <span data-ttu-id="a559f-134">**Standardmotkonto**</span><span class="sxs-lookup"><span data-stu-id="a559f-134">**Default offset account**</span></span>
-   <span data-ttu-id="a559f-135">**Uppskjutet** – Stoppa ett huvudkonto för inmatning av data över alla företag eller för ett specifikt företag/ juridisk person.</span><span class="sxs-lookup"><span data-stu-id="a559f-135">**Suspended** – Suspend a main account for data entry across all companies or for a specific company/legal entity.</span></span>
-   <span data-ttu-id="a559f-136">**Tillåt inte manuell inmatning** – Förhindra användare från att manuellt ange ett värde för kontot i journaler.</span><span class="sxs-lookup"><span data-stu-id="a559f-136">**Do not allow manual entry** – Prevent users from manually entering a value for the account in journals.</span></span>
-   <span data-ttu-id="a559f-137">**Standard/Validera valuta**</span><span class="sxs-lookup"><span data-stu-id="a559f-137">**Default/Validate currency**</span></span>
-   <span data-ttu-id="a559f-138">**Juridisk person åsidosätter** – Denna inställning är specifik för definierade företag/juridiska enhet:</span><span class="sxs-lookup"><span data-stu-id="a559f-138">**Legal entity override** – This setup is specific to the defined company/legal entity:</span></span>
    -   <span data-ttu-id="a559f-139">**Standard/Validera moms**</span><span class="sxs-lookup"><span data-stu-id="a559f-139">**Default/Validate sales tax**</span></span>
    -   <span data-ttu-id="a559f-140">**Standarddimension** – **Inte fast** eller **Fast värde**.</span><span class="sxs-lookup"><span data-stu-id="a559f-140">**Default dimension** – **Not fixed** or **Fixed value**.</span></span> <span data-ttu-id="a559f-141">**Fast värde** kommer att bidra till att garantera att alla konteringar för detta konto använder alltid något dimensionsvärde som är inställt som **fast**.</span><span class="sxs-lookup"><span data-stu-id="a559f-141">**Fixed value** will help ensure that all postings for this main account always use any dimension value that is set up as **Fixed**.</span></span>
-   <span data-ttu-id="a559f-142">**Bokföringsvalidering**</span><span class="sxs-lookup"><span data-stu-id="a559f-142">**Posting validation**</span></span>
    -   <span data-ttu-id="a559f-143">**Användarvalidering** – Det här alternativet styr vilka användare som tillåts bokföra på huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="a559f-143">**User validation** – This option controls which users are allowed to post to a main account.</span></span>
    -   <span data-ttu-id="a559f-144">**Konteringstypvalidering** – Med det här alternativet styr vilka konteringstyper som tillåts för huvudkonto.</span><span class="sxs-lookup"><span data-stu-id="a559f-144">**Posting type validation** – This option controls which posting types are allowed for a main account.</span></span>

### <a name="accounting-structures-and-advanced-rules-structures"></a><span data-ttu-id="a559f-145">Redovisningsstrukturer och avancerade regler strukturer</span><span class="sxs-lookup"><span data-stu-id="a559f-145">Accounting structures and advanced rules structures</span></span>

<span data-ttu-id="a559f-146">Redovisningsstrukturer och avancerade regler strukturer är oerhört viktiga för att garantera att de data som krävs för ekonomisk rapportering och uppföljning av prestationer är fångade under allmän journal bearbetning och all dokumentation.</span><span class="sxs-lookup"><span data-stu-id="a559f-146">Accounting structures and advanced rules structures are extremely important for ensuring that the data that is required for financial reporting and performance tracking is captured during general journal processing and any documentation.</span></span> <span data-ttu-id="a559f-147">Redovisningsstrukturer och avancerade regler strukturer kan du skräddarsy data entry-upplevelse.</span><span class="sxs-lookup"><span data-stu-id="a559f-147">Accounting structures and advanced rules structures let you tailor the data entry experience.</span></span> <span data-ttu-id="a559f-148">Du kan registrera data endast för finansiella mått som är relevanta i varje situation, och kan också genomdriva kravet på att obligatorisk och korrekt data alltid finnas fångat.</span><span class="sxs-lookup"><span data-stu-id="a559f-148">You can allow data entry only for financial dimensions that are relevant in each situation, and can also enforce the requirement that required and accurate data always be captured.</span></span>

<span data-ttu-id="a559f-149">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="a559f-149">For more information, see the following topics:</span></span>
- [<span data-ttu-id="a559f-150">Planera kontoplanen</span><span class="sxs-lookup"><span data-stu-id="a559f-150">Plan your chart of accounts</span></span>](plan-chart-of-accounts.md) 
- [<span data-ttu-id="a559f-151">Skapa avancerade regler för journaler</span><span class="sxs-lookup"><span data-stu-id="a559f-151">Create advanced rules for journals</span></span>](tasks/create-advanced-rules-journals.md)
- [<span data-ttu-id="a559f-152">Skapa en journalpost med en mall</span><span class="sxs-lookup"><span data-stu-id="a559f-152">Create a journal entry using template</span></span>](tasks/create-journal-entry-template.md)
- [<span data-ttu-id="a559f-153">Skapa och validera journaler</span><span class="sxs-lookup"><span data-stu-id="a559f-153">Create and validate journals</span></span>](tasks/create-validate-journals.md)
- [<span data-ttu-id="a559f-154">Bokför periodiska journaler</span><span class="sxs-lookup"><span data-stu-id="a559f-154">Post periodic journals</span></span>](tasks/post-periodic-journals.md)
- [<span data-ttu-id="a559f-155">Bearbeta journal för redovisningsallokering</span><span class="sxs-lookup"><span data-stu-id="a559f-155">Process ledger allocation journal</span></span>](tasks/process-ledger-allocation-journal.md)

## <a name="simulate-posting"></a><span data-ttu-id="a559f-156">Simulera bokföring</span><span class="sxs-lookup"><span data-stu-id="a559f-156">Simulate posting</span></span>
<span data-ttu-id="a559f-157">Du hittar **Simulera bokföring** på menyn **Validera** för de flesta journaler.</span><span class="sxs-lookup"><span data-stu-id="a559f-157">You can find **Simulate posting** on the **Validate** menu for most journals.</span></span> <span data-ttu-id="a559f-158">När du validerar en journal med hjälp av funktionen **Validera** testar systemet journalen för specifika felförhållanden.</span><span class="sxs-lookup"><span data-stu-id="a559f-158">When you validate a journal using the **Validate** function, the system tests the journal for specific error conditions.</span></span> <span data-ttu-id="a559f-159">Om du använder funktionen **Simulera bokföring**, kör systemet alla samma processer som körs utan att själva bokföringen av journalen vid bokföring.</span><span class="sxs-lookup"><span data-stu-id="a559f-159">If you use the **Simulate posting** function, the system runs all of the same processes that are run during posting without actually posting the journal.</span></span> <span data-ttu-id="a559f-160">Du kan sedan granska bokföringsmeddelanden som visas, korrigera eventuella fel som kan du söka efter och öppna menyn **bokför** om du vill bokföra journalen.</span><span class="sxs-lookup"><span data-stu-id="a559f-160">You can then review the posting messages that are displayed, fix any errors that you find, and then open the **Post** menu to post the journal.</span></span> 

<span data-ttu-id="a559f-161">**Simulera bokföring** är inte tillgänglig för batchbearbetning.</span><span class="sxs-lookup"><span data-stu-id="a559f-161">**Simulate posting** is not available for batch processing.</span></span> <span data-ttu-id="a559f-162">Det finns emellertid kod tillgänglig för att simulera bokföring i batch kod och utvecklare kan använda kod för att lägga till funktionen.</span><span class="sxs-lookup"><span data-stu-id="a559f-162">However, there is code available to simulate posting in batch and developers can extend the code to add that functionality.</span></span>  

## <a name="journal-unlock"></a><span data-ttu-id="a559f-163">Lås upp journal</span><span class="sxs-lookup"><span data-stu-id="a559f-163">Journal unlock</span></span>
<span data-ttu-id="a559f-164">En knapp är tillgänglig på sidan Journal för att låsa upp en journal med status "låst av systemet" inställd på Ja.</span><span class="sxs-lookup"><span data-stu-id="a559f-164">A button is available on the journal page to unlock a journal that has a status of "locked by system" set to Yes.</span></span> <span data-ttu-id="a559f-165">Den här upplåsningen kan utföras av en systemadministratör som har analyserat alla exekverande batchjobb och bekräftat att den här journalen inte längre aktivt bearbetas av ett batchjobb.</span><span class="sxs-lookup"><span data-stu-id="a559f-165">This unlock can be performed by an administrator of the system who has analyzed any executing batch jobs and confirmed this journal is no longer actively being processed by a batch job.</span></span> <span data-ttu-id="a559f-166">Den här knappen aktiveras med funktionen **knappen lås upp journal** på sidan **funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="a559f-166">This button is enabled by the feature named **Journal Unlock button** on the **Feature management** page.</span></span> 

## <a name="workflow-recall"></a><span data-ttu-id="a559f-167">Arbetsflödet har återkallats</span><span class="sxs-lookup"><span data-stu-id="a559f-167">Workflow recall</span></span> 
<span data-ttu-id="a559f-168">Möjligheten att återkalla en journal i ett arbetsflöde med statusen "oåterkallelig" aktiveras genom att använda knappen **arbetsflöde** i en journal och på sidan **arbetsflödeshistorik**.</span><span class="sxs-lookup"><span data-stu-id="a559f-168">The ability to recall a journal in a workflow that has a status of "unrecoverable" is enabled by using the **Workflow** button on a journal, and on the **Workflow history** page.</span></span> <span data-ttu-id="a559f-169">Detta aktiveras med funktionen som kallas **återställning av arbetsflödesstatusen för journaler** på sidan **funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="a559f-169">This is enabled by the feature named **Resetting the workflow status for journals** on the **Feature management** page.</span></span>

## <a name="delete-journal-lines"></a><span data-ttu-id="a559f-170">Radera journalrader</span><span class="sxs-lookup"><span data-stu-id="a559f-170">Delete Journal Lines</span></span>
<span data-ttu-id="a559f-171">Möjligheten att snabbt ta bort alla journalrader är aktiverad i en journal under **funktioner** > **ta bort journalrader**.</span><span class="sxs-lookup"><span data-stu-id="a559f-171">The ability to delete all journal lines quickly is enabled in a journal under **Functions** > **Delete Journal Lines**.</span></span> <span data-ttu-id="a559f-172">Om du vill aktivera den här funktionen väljer du **funktionshantering**, välj **ta bort optimeringar för journalprestanda**.</span><span class="sxs-lookup"><span data-stu-id="a559f-172">To enable this feature, on the **Feature management**, select **Delete journal performance optimizations**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]