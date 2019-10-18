---
title: Felsökning av fel på bankutdragsfilen
description: Det är viktigt att bankutdragsfilen från banken matchar den layout som Microsoft Dynamics 365 Finance stöder. På grund av de strikta standarder som gäller för bankutdrag kommer de flesta integreringar att fungera korrekt. Ibland kan emellertid utdragsfilen inte importeras, eller också har den felaktiga resultat. Vanligtvis orsakas dessa problem av små skillnader i bankutdragsfilen. Denna artikel förklarar hur du korrigerar dessa skillnader och löser problemen.
author: ShylaThompson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 612ded1f68cc8e1b26b8046501bae1707175e23a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188336"
---
# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="b511e-107">Felsökning av fel på bankutdragsfilen</span><span class="sxs-lookup"><span data-stu-id="b511e-107">Bank statement file import troubleshooting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b511e-108">Det är viktigt att bankutdragsfilen från banken matchar den layout som Microsoft Dynamics 365 Finance stöder.</span><span class="sxs-lookup"><span data-stu-id="b511e-108">It's important that the bank statement file from the bank match the layout that Microsoft Dynamics 365 Finance supports.</span></span> <span data-ttu-id="b511e-109">På grund av de strikta standarder som gäller för bankutdrag kommer de flesta integreringar att fungera korrekt.</span><span class="sxs-lookup"><span data-stu-id="b511e-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="b511e-110">Ibland kan emellertid utdragsfilen inte importeras, eller också har den felaktiga resultat.</span><span class="sxs-lookup"><span data-stu-id="b511e-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="b511e-111">Vanligtvis orsakas dessa problem av små skillnader i bankutdragsfilen.</span><span class="sxs-lookup"><span data-stu-id="b511e-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="b511e-112">Denna artikel förklarar hur du korrigerar dessa skillnader och löser problemen.</span><span class="sxs-lookup"><span data-stu-id="b511e-112">This article explains how to fix these differences and resolve the issues.</span></span>

<a name="what-is-the-error"></a><span data-ttu-id="b511e-113">Vad består felet av?</span><span class="sxs-lookup"><span data-stu-id="b511e-113">What is the error?</span></span>
------------------

<span data-ttu-id="b511e-114">Gå till jobbhistoriken för datahantering och dess utförandedetaljer för att hitta felet när du försöker importera en bankutdragsfil.</span><span class="sxs-lookup"><span data-stu-id="b511e-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="b511e-115">Felet kan hjälpa dig genom att peka på utdraget, saldot eller utdragsraden.</span><span class="sxs-lookup"><span data-stu-id="b511e-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="b511e-116">Det ger dig emellertid troligtvis inte tillräckligt med information för att hjälpa dig att identifiera det fält eller element som orsakat problemet.</span><span class="sxs-lookup"><span data-stu-id="b511e-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="b511e-117">Vilka skillnader finns det?</span><span class="sxs-lookup"><span data-stu-id="b511e-117">What are the differences?</span></span>
<span data-ttu-id="b511e-118">Jämför definitionen av bankfilens layout med Finance importdefinitionen, och notera eventuella skillnader i fält och element.</span><span class="sxs-lookup"><span data-stu-id="b511e-118">Compare the bank file layout definition to the Finance import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="b511e-119">Jämför bankutdragsfilen med relaterad Finance-exempelfil.</span><span class="sxs-lookup"><span data-stu-id="b511e-119">Compare the bank statement file to the related sample Finance file.</span></span> <span data-ttu-id="b511e-120">Skillnader i ISO20022-filerna bör vara lätta att se.</span><span class="sxs-lookup"><span data-stu-id="b511e-120">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="time-zone-differences-on-imported-bank-statements"></a><span data-ttu-id="b511e-121">Tidszonsskillnader i importerade bankutdrag</span><span class="sxs-lookup"><span data-stu-id="b511e-121">Time zone differences on imported bank statements</span></span>
<span data-ttu-id="b511e-122">Datum- och tidsvärden i importfilen kan skilja sig från datum- och tidsvärden som visas i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b511e-122">The date-time values in the import file can differ from the date-time values that are shown in Finance and Operations.</span></span> <span data-ttu-id="b511e-123">Du kan förhindra den här avvikelsen genom att ange en tidszonsskillnad på sidan **konfigurera datakällor**.</span><span class="sxs-lookup"><span data-stu-id="b511e-123">To prevent this discrepancy, enter a time zone preference on the **Configure data sources** page.</span></span> <span data-ttu-id="b511e-124">Se [Ställ in importprocess för avancerad bankavstämning](set-up-advanced-bank-reconciliation-import-process.md) för mer information om hur du anger en inställning av tidszon.</span><span class="sxs-lookup"><span data-stu-id="b511e-124">See [Set up the advanced bank reconciliation import process](set-up-advanced-bank-reconciliation-import-process.md) for more information about entering a time zone preference.</span></span>

## <a name="transformations"></a><span data-ttu-id="b511e-125">Transformeringar</span><span class="sxs-lookup"><span data-stu-id="b511e-125">Transformations</span></span>
<span data-ttu-id="b511e-126">Normalt måste ändringen utföras i en av de tre transformeringarna.</span><span class="sxs-lookup"><span data-stu-id="b511e-126">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="b511e-127">Varje transformering skrivs för en viss standard.</span><span class="sxs-lookup"><span data-stu-id="b511e-127">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="b511e-128">Resursnamn</span><span class="sxs-lookup"><span data-stu-id="b511e-128">Resource name</span></span>                                         | <span data-ttu-id="b511e-129">Filnamn</span><span class="sxs-lookup"><span data-stu-id="b511e-129">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="b511e-130">BankStmtImport\_BAI2CSV\_till\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="b511e-130">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="b511e-131">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="b511e-131">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="b511e-132">BankStmtImport\_ISO20022XML\_till\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="b511e-132">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="b511e-133">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="b511e-133">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="b511e-134">BankStmtImport\_MT940TXT\_till\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="b511e-134">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="b511e-135">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="b511e-135">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="b511e-136">Felsökningtransformeringar</span><span class="sxs-lookup"><span data-stu-id="b511e-136">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="b511e-137">Justera filerna BAI2 och MT940</span><span class="sxs-lookup"><span data-stu-id="b511e-137">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="b511e-138">Filerna BAI2 och MT940 är textbaserade filer och kräver en justering om du vill aktivera felsökning för Extensible Stylesheet Language-transformeringar (XSLT).</span><span class="sxs-lookup"><span data-stu-id="b511e-138">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="b511e-139">Programmet utför denna justering när en fil importeras.</span><span class="sxs-lookup"><span data-stu-id="b511e-139">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="b511e-140">Skapa en XML-fil och kopiera följande text till den.</span><span class="sxs-lookup"><span data-stu-id="b511e-140">Create an XML file, and copy the following text into it.</span></span>

        <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>

2.  <span data-ttu-id="b511e-141">Kopiera innehållet i bankutdragsfilen och klistra in det i XML-filen så att det ersätter **PASTESTATEMENTFILEHERE**.</span><span class="sxs-lookup"><span data-stu-id="b511e-141">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="b511e-142">Felsöka XSLT</span><span class="sxs-lookup"><span data-stu-id="b511e-142">Debug the XSLT</span></span>

<span data-ttu-id="b511e-143">Mer information finns i <https://msdn.microsoft.com/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="b511e-143">For more information, see <https://msdn.microsoft.com/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="b511e-144">Starta Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b511e-144">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="b511e-145">Skapa en konsolapplikation.</span><span class="sxs-lookup"><span data-stu-id="b511e-145">Create a console application.</span></span>
3.  <span data-ttu-id="b511e-146">Öppna lämplig XSLT.</span><span class="sxs-lookup"><span data-stu-id="b511e-146">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="b511e-147">Klicka på XLST:n och dess egenskapssida.</span><span class="sxs-lookup"><span data-stu-id="b511e-147">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="b511e-148">Ange inmatningen på platsen för bankutdragsfilen.</span><span class="sxs-lookup"><span data-stu-id="b511e-148">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="b511e-149">Definiera en plats och ett filnamn för utdatan.</span><span class="sxs-lookup"><span data-stu-id="b511e-149">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="b511e-150">Ange erforderliga brytpunkter.</span><span class="sxs-lookup"><span data-stu-id="b511e-150">Set the required break points.</span></span>
8.  <span data-ttu-id="b511e-151">I menyn klickar du på **XML** &gt; **Starta XSLT-felsökning**.</span><span class="sxs-lookup"><span data-stu-id="b511e-151">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="b511e-152">Formatera XSLT-utdata</span><span class="sxs-lookup"><span data-stu-id="b511e-152">Format the XSLT output</span></span>

<span data-ttu-id="b511e-153">När transformeringen körs skapas en utdatafil som du kan visa i Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b511e-153">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="b511e-154">Använd Ctrl+A, Ctrl+K och Ctrl+D för att snabbformatera utdatafilen.</span><span class="sxs-lookup"><span data-stu-id="b511e-154">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="b511e-155">Justera transformeringen</span><span class="sxs-lookup"><span data-stu-id="b511e-155">Adjust the transformation</span></span>

<span data-ttu-id="b511e-156">Justera transformeringen för att få lämpligt fält eller element i bankutdragsfilen.</span><span class="sxs-lookup"><span data-stu-id="b511e-156">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="b511e-157">Mappa sedan detta fält eller element med lämpligt Finance-element.</span><span class="sxs-lookup"><span data-stu-id="b511e-157">Then map that field or element to the appropriate Finance element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="b511e-158">Debet-/kreditindikator</span><span class="sxs-lookup"><span data-stu-id="b511e-158">Debit/credit indicator</span></span>

<span data-ttu-id="b511e-159">Ibland kan debet importeras som kredit, och kredit kan importeras som debet.</span><span class="sxs-lookup"><span data-stu-id="b511e-159">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="b511e-160">För att lösa detta problem måste du ändra lämplig XSLT.</span><span class="sxs-lookup"><span data-stu-id="b511e-160">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="b511e-161">Om bankutdrag kommer från flera banker, se då till att alla använder samma debet-/kreditmetod, eller skapa separata transformeringar.</span><span class="sxs-lookup"><span data-stu-id="b511e-161">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="b511e-162">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator-mall</span><span class="sxs-lookup"><span data-stu-id="b511e-162">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="b511e-163">ISO20022XML-to-Reconcilation.xslt GetCreditDebit-mall</span><span class="sxs-lookup"><span data-stu-id="b511e-163">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="b511e-164">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator-mall</span><span class="sxs-lookup"><span data-stu-id="b511e-164">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="b511e-165">Exempel på bankutdragsformat och tekniska layouter</span><span class="sxs-lookup"><span data-stu-id="b511e-165">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="b511e-166">Följande tabell anger exempel på tekniska layoutdefinitioner för importfiler för avancerade bankavstämningar, samt tre relaterade bankutdragsexempelfiler.</span><span class="sxs-lookup"><span data-stu-id="b511e-166">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="b511e-167">Du kan hämta till exempelfiler och tekniska layouter här: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span><span class="sxs-lookup"><span data-stu-id="b511e-167">You can download the example files and technical layouts here: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span></span>  


| <span data-ttu-id="b511e-168">Teknisk layoutdefinition</span><span class="sxs-lookup"><span data-stu-id="b511e-168">Technical layout definition</span></span>                             | <span data-ttu-id="b511e-169">Bankutdragsexempelfil</span><span class="sxs-lookup"><span data-stu-id="b511e-169">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="b511e-170">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="b511e-170">DynamicsAXMT940Layout</span></span>                                   | <span data-ttu-id="b511e-171">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="b511e-171">MT940StatementExample</span></span>                |
| <span data-ttu-id="b511e-172">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="b511e-172">DynamicsAXISO20022Layout</span></span>                                | <span data-ttu-id="b511e-173">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="b511e-173">ISO20022StatementExample</span></span>             |
| <span data-ttu-id="b511e-174">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="b511e-174">DynamicsAXBAI2Layout</span></span>                                    | <span data-ttu-id="b511e-175">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="b511e-175">BAI2StatementExample</span></span>                 |





