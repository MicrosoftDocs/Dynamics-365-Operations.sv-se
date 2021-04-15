---
title: Felsökning av fel på bankutdragsfilen
description: Det är viktigt att bankutdragsfilen från banken matchar den layout som Microsoft Dynamics 365 Finance stöder. På grund av de strikta standarder som gäller för bankutdrag kommer de flesta integreringar att fungera korrekt. Ibland kan emellertid utdragsfilen inte importeras, eller också har den felaktiga resultat. Vanligtvis orsakas dessa problem av små skillnader i bankutdragsfilen. Denna artikel förklarar hur du korrigerar dessa skillnader och löser problemen.
author: panolte
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f0e01881a6b68526479d27014d49a718069cffc9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815894"
---
# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="471ca-107">Felsökning av fel på bankutdragsfilen</span><span class="sxs-lookup"><span data-stu-id="471ca-107">Bank statement file import troubleshooting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="471ca-108">Det är viktigt att bankutdragsfilen från banken matchar den layout som Microsoft Dynamics 365 Finance stöder.</span><span class="sxs-lookup"><span data-stu-id="471ca-108">It's important that the bank statement file from the bank matches the layout that Microsoft Dynamics 365 Finance supports.</span></span> <span data-ttu-id="471ca-109">På grund av de strikta standarder som gäller för bankutdrag kommer de flesta integreringar att fungera korrekt.</span><span class="sxs-lookup"><span data-stu-id="471ca-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="471ca-110">Ibland kan emellertid utdragsfilen inte importeras, eller också har den felaktiga resultat.</span><span class="sxs-lookup"><span data-stu-id="471ca-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="471ca-111">Vanligtvis orsakas dessa problem av små skillnader i bankutdragsfilen.</span><span class="sxs-lookup"><span data-stu-id="471ca-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="471ca-112">Denna artikel förklarar hur du korrigerar dessa skillnader och löser problemen.</span><span class="sxs-lookup"><span data-stu-id="471ca-112">This article explains how to fix these differences and resolve the issues.</span></span>

<a name="what-is-the-error"></a><span data-ttu-id="471ca-113">Vad består felet av?</span><span class="sxs-lookup"><span data-stu-id="471ca-113">What is the error?</span></span>
------------------

<span data-ttu-id="471ca-114">Gå till jobbhistoriken för datahantering och dess utförandedetaljer för att hitta felet när du försöker importera en bankutdragsfil.</span><span class="sxs-lookup"><span data-stu-id="471ca-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="471ca-115">Felet kan hjälpa dig genom att peka på utdraget, saldot eller utdragsraden.</span><span class="sxs-lookup"><span data-stu-id="471ca-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="471ca-116">Det ger dig emellertid troligtvis inte tillräckligt med information för att hjälpa dig att identifiera det fält eller element som orsakat problemet.</span><span class="sxs-lookup"><span data-stu-id="471ca-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

> [!NOTE]
> <span data-ttu-id="471ca-117">Importerade bankutdrag kan endast överlappa varandra under en viss tidpunkt.</span><span class="sxs-lookup"><span data-stu-id="471ca-117">Imported bank statements can overlap only for single a point in time.</span></span>  <span data-ttu-id="471ca-118">Till exempel, om ett uttalande slutar klockan 24:00 den 1 januari 2021, kan början på nästa uttalande vara 24:00 1 januari 2021 24:00:00 AM.</span><span class="sxs-lookup"><span data-stu-id="471ca-118">For example, if a statement ends at 12:00 AM on January 1, 2021, then beginning date for the next statement can be 12:00 AM on Jarnuary 1, 2021 12:00:00 AM.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="471ca-119">Vilka skillnader finns det?</span><span class="sxs-lookup"><span data-stu-id="471ca-119">What are the differences?</span></span>
<span data-ttu-id="471ca-120">Jämför definitionen av bankfilens layout med Finance importdefinitionen, och notera eventuella skillnader i fält och element.</span><span class="sxs-lookup"><span data-stu-id="471ca-120">Compare the bank file layout definition to the Finance import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="471ca-121">Jämför bankutdragsfilen med relaterad Finance-exempelfil.</span><span class="sxs-lookup"><span data-stu-id="471ca-121">Compare the bank statement file to the related sample Finance file.</span></span> <span data-ttu-id="471ca-122">Skillnader i ISO20022-filerna bör vara lätta att se.</span><span class="sxs-lookup"><span data-stu-id="471ca-122">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="time-zone-differences-on-imported-bank-statements"></a><span data-ttu-id="471ca-123">Tidszonsskillnader i importerade bankutdrag</span><span class="sxs-lookup"><span data-stu-id="471ca-123">Time zone differences on imported bank statements</span></span>
<span data-ttu-id="471ca-124">Datum- och tidsvärden i importfilen kan skilja sig från datum- och tidsvärden som visas i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="471ca-124">The date-time values in the import file can differ from the date-time values that are shown in Finance and Operations.</span></span> <span data-ttu-id="471ca-125">Du kan förhindra den här avvikelsen genom att ange en tidszonsskillnad på sidan **konfigurera datakällor**.</span><span class="sxs-lookup"><span data-stu-id="471ca-125">To prevent this discrepancy, enter a time zone preference on the **Configure data sources** page.</span></span> <span data-ttu-id="471ca-126">För mer information om hur du anger en inställning av tidszonen, se [Ställ in importprocess för avancerad bankavstämning](set-up-advanced-bank-reconciliation-import-process.md).</span><span class="sxs-lookup"><span data-stu-id="471ca-126">For more information about entering a time zone preference, see [Set up the advanced bank reconciliation import process](set-up-advanced-bank-reconciliation-import-process.md).</span></span>

## <a name="transformations"></a><span data-ttu-id="471ca-127">Transformeringar</span><span class="sxs-lookup"><span data-stu-id="471ca-127">Transformations</span></span>
<span data-ttu-id="471ca-128">Normalt måste ändringen utföras i en av de tre transformeringarna.</span><span class="sxs-lookup"><span data-stu-id="471ca-128">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="471ca-129">Varje transformering skrivs för en viss standard.</span><span class="sxs-lookup"><span data-stu-id="471ca-129">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="471ca-130">Resursnamn</span><span class="sxs-lookup"><span data-stu-id="471ca-130">Resource name</span></span>                                         | <span data-ttu-id="471ca-131">Filnamn</span><span class="sxs-lookup"><span data-stu-id="471ca-131">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="471ca-132">BankStmtImport\_BAI2CSV\_till\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="471ca-132">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="471ca-133">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="471ca-133">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="471ca-134">BankStmtImport\_ISO20022XML\_till\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="471ca-134">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="471ca-135">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="471ca-135">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="471ca-136">BankStmtImport\_MT940TXT\_till\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="471ca-136">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="471ca-137">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="471ca-137">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="471ca-138">Felsökningtransformeringar</span><span class="sxs-lookup"><span data-stu-id="471ca-138">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="471ca-139">Justera filerna BAI2 och MT940</span><span class="sxs-lookup"><span data-stu-id="471ca-139">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="471ca-140">Filerna BAI2 och MT940 är textbaserade filer och kräver en justering om du vill aktivera felsökning för Extensible Stylesheet Language-transformeringar (XSLT).</span><span class="sxs-lookup"><span data-stu-id="471ca-140">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="471ca-141">Programmet utför denna justering när en fil importeras.</span><span class="sxs-lookup"><span data-stu-id="471ca-141">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="471ca-142">Skapa en XML-fil och kopiera följande text till den.</span><span class="sxs-lookup"><span data-stu-id="471ca-142">Create an XML file, and copy the following text into it.</span></span>

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  <span data-ttu-id="471ca-143">Kopiera innehållet i bankutdragsfilen och klistra in det i XML-filen så att det ersätter **PASTESTATEMENTFILEHERE**.</span><span class="sxs-lookup"><span data-stu-id="471ca-143">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="471ca-144">Felsöka XSLT</span><span class="sxs-lookup"><span data-stu-id="471ca-144">Debug the XSLT</span></span>

<span data-ttu-id="471ca-145">Mer information finns i <https://msdn.microsoft.com/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="471ca-145">For more information, see <https://msdn.microsoft.com/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="471ca-146">Starta Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="471ca-146">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="471ca-147">Skapa en konsolapplikation.</span><span class="sxs-lookup"><span data-stu-id="471ca-147">Create a console application.</span></span>
3.  <span data-ttu-id="471ca-148">Öppna lämplig XSLT.</span><span class="sxs-lookup"><span data-stu-id="471ca-148">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="471ca-149">Klicka på XLST:n och dess egenskapssida.</span><span class="sxs-lookup"><span data-stu-id="471ca-149">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="471ca-150">Ange inmatningen på platsen för bankutdragsfilen.</span><span class="sxs-lookup"><span data-stu-id="471ca-150">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="471ca-151">Definiera en plats och ett filnamn för utdatan.</span><span class="sxs-lookup"><span data-stu-id="471ca-151">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="471ca-152">Ange erforderliga brytpunkter.</span><span class="sxs-lookup"><span data-stu-id="471ca-152">Set the required break points.</span></span>
8.  <span data-ttu-id="471ca-153">I menyn klickar du på **XML** &gt; **Starta XSLT-felsökning**.</span><span class="sxs-lookup"><span data-stu-id="471ca-153">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="471ca-154">Formatera XSLT-utdata</span><span class="sxs-lookup"><span data-stu-id="471ca-154">Format the XSLT output</span></span>

<span data-ttu-id="471ca-155">När transformeringen körs skapas en utdatafil som du kan visa i Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="471ca-155">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="471ca-156">Använd Ctrl+A, Ctrl+K och Ctrl+D för att snabbformatera utdatafilen.</span><span class="sxs-lookup"><span data-stu-id="471ca-156">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="471ca-157">Justera transformeringen</span><span class="sxs-lookup"><span data-stu-id="471ca-157">Adjust the transformation</span></span>

<span data-ttu-id="471ca-158">Justera transformeringen för att få lämpligt fält eller element i bankutdragsfilen.</span><span class="sxs-lookup"><span data-stu-id="471ca-158">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="471ca-159">Mappa sedan detta fält eller element med lämpligt Finance-element.</span><span class="sxs-lookup"><span data-stu-id="471ca-159">Then map that field or element to the appropriate Finance element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="471ca-160">Debet-/kreditindikator</span><span class="sxs-lookup"><span data-stu-id="471ca-160">Debit/credit indicator</span></span>

<span data-ttu-id="471ca-161">Ibland kan debet importeras som kredit, och kredit kan importeras som debet.</span><span class="sxs-lookup"><span data-stu-id="471ca-161">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="471ca-162">För att lösa detta problem måste du ändra lämplig XSLT.</span><span class="sxs-lookup"><span data-stu-id="471ca-162">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="471ca-163">Om bankutdrag kommer från flera banker, se då till att alla använder samma debet-/kreditmetod, eller skapa separata transformeringar.</span><span class="sxs-lookup"><span data-stu-id="471ca-163">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="471ca-164">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator-mall</span><span class="sxs-lookup"><span data-stu-id="471ca-164">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="471ca-165">ISO20022XML-to-Reconcilation.xslt GetCreditDebit-mall</span><span class="sxs-lookup"><span data-stu-id="471ca-165">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="471ca-166">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator-mall</span><span class="sxs-lookup"><span data-stu-id="471ca-166">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="471ca-167">Exempel på bankutdragsformat och tekniska layouter</span><span class="sxs-lookup"><span data-stu-id="471ca-167">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="471ca-168">Följande tabell anger exempel på tekniska layoutdefinitioner för importfiler för avancerade bankavstämningar, samt tre relaterade bankutdragsexempelfiler.</span><span class="sxs-lookup"><span data-stu-id="471ca-168">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="471ca-169">Du kan hämta till exempelfiler och tekniska layouter här: [Exempel på importfiler](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)</span><span class="sxs-lookup"><span data-stu-id="471ca-169">You can download the example files and technical layouts here: [Import file examples](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)</span></span>  

| <span data-ttu-id="471ca-170">Teknisk layoutdefinition</span><span class="sxs-lookup"><span data-stu-id="471ca-170">Technical layout definition</span></span>                             | <span data-ttu-id="471ca-171">Bankutdragsexempelfil</span><span class="sxs-lookup"><span data-stu-id="471ca-171">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="471ca-172">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="471ca-172">DynamicsAXMT940Layout</span></span>                                   | [<span data-ttu-id="471ca-173">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="471ca-173">MT940StatementExample</span></span>](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| <span data-ttu-id="471ca-174">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="471ca-174">DynamicsAXISO20022Layout</span></span>                                | [<span data-ttu-id="471ca-175">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="471ca-175">ISO20022StatementExample</span></span>](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| <span data-ttu-id="471ca-176">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="471ca-176">DynamicsAXBAI2Layout</span></span>                                    | [<span data-ttu-id="471ca-177">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="471ca-177">BAI2StatementExample</span></span>](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
