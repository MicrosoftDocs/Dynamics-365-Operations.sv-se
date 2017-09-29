---
title: "Felsökning av fel på bankutdragsfilen"
description: "Det är viktigt att bankutdragsfilen från banken matchar den layout som Microsoft Dynamics 365 for Finance and Operations, Enterprise edition stöder. På grund av de strikta standarder som gäller för bankutdrag kommer de flesta integreringar att fungera korrekt. Ibland kan emellertid utdragsfilen inte importeras, eller också har den felaktiga resultat. Vanligtvis orsakas dessa problem av små skillnader i bankutdragsfilen. Denna artikel förklarar hur du korrigerar dessa skillnader och löser problemen."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 51cd32217b2f753f606e3060b4872a8274f16549
ms.contentlocale: sv-se
ms.lasthandoff: 07/18/2017

---

# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="e7a6f-107">Felsökning av fel på bankutdragsfilen</span><span class="sxs-lookup"><span data-stu-id="e7a6f-107">Bank statement file import troubleshooting</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="e7a6f-108">Det är viktigt att bankutdragsfilen från banken matchar den layout som Microsoft Dynamics 365 for Finance and Operations, Enterprise edition stöder.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-108">It's important that the bank statement file from the bank match the layout that Microsoft Dynamics 365 for Finance and Operations, Enterprise edition supports.</span></span> <span data-ttu-id="e7a6f-109">På grund av de strikta standarder som gäller för bankutdrag kommer de flesta integreringar att fungera korrekt.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="e7a6f-110">Ibland kan emellertid utdragsfilen inte importeras, eller också har den felaktiga resultat.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="e7a6f-111">Vanligtvis orsakas dessa problem av små skillnader i bankutdragsfilen.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="e7a6f-112">Denna artikel förklarar hur du korrigerar dessa skillnader och löser problemen.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-112">This article explains how to fix these differences and resolve the issues.</span></span>

<a name="what-is-the-error"></a><span data-ttu-id="e7a6f-113">Vad består felet av?</span><span class="sxs-lookup"><span data-stu-id="e7a6f-113">What is the error?</span></span>
------------------

<span data-ttu-id="e7a6f-114">Gå till jobbhistoriken för datahantering och dess utförandedetaljer för att hitta felet när du försöker importera en bankutdragsfil.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="e7a6f-115">Felet kan hjälpa dig genom att peka på utdraget, saldot eller utdragsraden.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="e7a6f-116">Det ger dig emellertid troligtvis inte tillräckligt med information för att hjälpa dig att identifiera det fält eller element som orsakat problemet.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="e7a6f-117">Vilka skillnader finns det?</span><span class="sxs-lookup"><span data-stu-id="e7a6f-117">What are the differences?</span></span>
<span data-ttu-id="e7a6f-118">Jämför definitionen av bankfilens layout med Finance and Operations-importdefinitionen, och notera eventuella skillnader i fält och element.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-118">Compare the bank file layout definition to the Finance and Operations import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="e7a6f-119">Jämför bankutdragsfilen med relaterad Finance and Operations-exempelfil.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-119">Compare the bank statement file to the related sample Finance and Operations file.</span></span> <span data-ttu-id="e7a6f-120">Skillnader i ISO20022-filerna bör vara lätta att se.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-120">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="transformations"></a><span data-ttu-id="e7a6f-121">Transformeringar</span><span class="sxs-lookup"><span data-stu-id="e7a6f-121">Transformations</span></span>
<span data-ttu-id="e7a6f-122">Normalt måste ändringen utföras i en av de tre transformeringarna.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-122">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="e7a6f-123">Varje transformering skrivs för en viss standard.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-123">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="e7a6f-124">Resursnamn</span><span class="sxs-lookup"><span data-stu-id="e7a6f-124">Resource name</span></span>                                         | <span data-ttu-id="e7a6f-125">Filnamn</span><span class="sxs-lookup"><span data-stu-id="e7a6f-125">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="e7a6f-126">BankStmtImport\_BAI2CSV\_till\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="e7a6f-126">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="e7a6f-127">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="e7a6f-127">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="e7a6f-128">BankStmtImport\_ISO20022XML\_till\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="e7a6f-128">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="e7a6f-129">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="e7a6f-129">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="e7a6f-130">BankStmtImport\_MT940TXT\_till\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="e7a6f-130">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="e7a6f-131">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="e7a6f-131">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="e7a6f-132">Felsökningtransformeringar</span><span class="sxs-lookup"><span data-stu-id="e7a6f-132">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="e7a6f-133">Justera filerna BAI2 och MT940</span><span class="sxs-lookup"><span data-stu-id="e7a6f-133">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="e7a6f-134">Filerna BAI2 och MT940 är textbaserade filer och kräver en justering om du vill aktivera felsökning för Extensible Stylesheet Language-transformeringar (XSLT).</span><span class="sxs-lookup"><span data-stu-id="e7a6f-134">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="e7a6f-135">Programmet utför denna justering när en fil importeras.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-135">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="e7a6f-136">Skapa en XML-fil och kopiera följande text till den.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-136">Create an XML file, and copy the following text into it.</span></span>

        <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>

2.  <span data-ttu-id="e7a6f-137">Kopiera innehållet i bankutdragsfilen och klistra in det i XML-filen så att det ersätter **PASTESTATEMENTFILEHERE**.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-137">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="e7a6f-138">Felsöka XSLT</span><span class="sxs-lookup"><span data-stu-id="e7a6f-138">Debug the XSLT</span></span>

<span data-ttu-id="e7a6f-139">Mer information finns på <https://msdn.microsoft.com/en-us/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-139">For more information, see <https://msdn.microsoft.com/en-us/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="e7a6f-140">Starta Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-140">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="e7a6f-141">Skapa en konsolapplikation.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-141">Create a console application.</span></span>
3.  <span data-ttu-id="e7a6f-142">Öppna lämplig XSLT.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-142">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="e7a6f-143">Klicka på XLST:n och dess egenskapssida.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-143">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="e7a6f-144">Ange inmatningen på platsen för bankutdragsfilen.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-144">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="e7a6f-145">Definiera en plats och ett filnamn för utdatan.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-145">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="e7a6f-146">Ange erforderliga brytpunkter.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-146">Set the required break points.</span></span>
8.  <span data-ttu-id="e7a6f-147">I menyn klickar du på **XML** &gt; **Starta XSLT-felsökning**.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-147">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="e7a6f-148">Formatera XSLT-utdata</span><span class="sxs-lookup"><span data-stu-id="e7a6f-148">Format the XSLT output</span></span>

<span data-ttu-id="e7a6f-149">När transformeringen körs skapas en utdatafil som du kan visa i Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-149">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="e7a6f-150">Använd Ctrl+A, Ctrl+K och Ctrl+D för att snabbformatera utdatafilen.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-150">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="e7a6f-151">Justera transformeringen</span><span class="sxs-lookup"><span data-stu-id="e7a6f-151">Adjust the transformation</span></span>

<span data-ttu-id="e7a6f-152">Justera transformeringen för att få lämpligt fält eller element i bankutdragsfilen.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-152">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="e7a6f-153">Mappa sedan detta fält eller element med lämpligt Finance and Operations-element.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-153">Then map that field or element to the appropriate Finance and Operations element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="e7a6f-154">Debet-/kreditindikator</span><span class="sxs-lookup"><span data-stu-id="e7a6f-154">Debit/credit indicator</span></span>

<span data-ttu-id="e7a6f-155">Ibland kan debet importeras som kredit, och kredit kan importeras som debet.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-155">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="e7a6f-156">För att lösa detta problem måste du ändra lämplig XSLT.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-156">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="e7a6f-157">Om bankutdrag kommer från flera banker, se då till att alla använder samma debet-/kreditmetod, eller skapa separata transformeringar.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-157">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="e7a6f-158">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator-mall</span><span class="sxs-lookup"><span data-stu-id="e7a6f-158">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="e7a6f-159">ISO20022XML-to-Reconcilation.xslt GetCreditDebit-mall</span><span class="sxs-lookup"><span data-stu-id="e7a6f-159">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="e7a6f-160">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator-mall</span><span class="sxs-lookup"><span data-stu-id="e7a6f-160">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="e7a6f-161">Exempel på bankutdragsformat och tekniska layouter</span><span class="sxs-lookup"><span data-stu-id="e7a6f-161">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="e7a6f-162">Följande tabell anger exempel på tekniska layoutdefinitioner för importfiler för avancerade bankavstämningar, samt tre relaterade bankutdragsexempelfiler.</span><span class="sxs-lookup"><span data-stu-id="e7a6f-162">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="e7a6f-163">Du kan hämta exempelfiler och tekniska layouter här: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span><span class="sxs-lookup"><span data-stu-id="e7a6f-163">You can download the example files and technical layouts here: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span></span>  


| <span data-ttu-id="e7a6f-164">Teknisk layoutdefinition</span><span class="sxs-lookup"><span data-stu-id="e7a6f-164">Technical layout definition</span></span>                             | <span data-ttu-id="e7a6f-165">Bankutdragsexempelfil</span><span class="sxs-lookup"><span data-stu-id="e7a6f-165">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="e7a6f-166">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="e7a6f-166">DynamicsAXMT940Layout</span></span>                                   | <span data-ttu-id="e7a6f-167">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="e7a6f-167">MT940StatementExample</span></span>                |
| <span data-ttu-id="e7a6f-168">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="e7a6f-168">DynamicsAXISO20022Layout</span></span>                                | <span data-ttu-id="e7a6f-169">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="e7a6f-169">ISO20022StatementExample</span></span>             |
| <span data-ttu-id="e7a6f-170">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="e7a6f-170">DynamicsAXBAI2Layout</span></span>                                    | <span data-ttu-id="e7a6f-171">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="e7a6f-171">BAI2StatementExample</span></span>                 |






