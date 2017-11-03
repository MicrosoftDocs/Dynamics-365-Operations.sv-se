---
title: "Ställa in och generera betalningskontrollfiler"
description: "Den här artikeln innehåller information om hur du ställer och genererar betalningskontrollfiler."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 28a8c7b739ecd991c6dc4934e379e3a2810f0240
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-and-generate-positive-pay-files"></a><span data-ttu-id="39a40-103">Ställa in och generera betalningskontrollfiler</span><span class="sxs-lookup"><span data-stu-id="39a40-103">Set up and generate positive pay files</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="39a40-104">Den här artikeln innehåller information om hur du ställer och genererar betalningskontrollfiler.</span><span class="sxs-lookup"><span data-stu-id="39a40-104">This article explains how to set up positive pay and generate positive pay files.</span></span> 

<span data-ttu-id="39a40-105">Ställa in betalningskontroll för att generera en elektrisk lista med checkar som ges till banken.</span><span class="sxs-lookup"><span data-stu-id="39a40-105">Set up positive pay to generate an electronic list of checks that is provided to the bank.</span></span> <span data-ttu-id="39a40-106">När checken sedan visas för banken, jämför banken checken med listan med checkar.</span><span class="sxs-lookup"><span data-stu-id="39a40-106">Then, when a check is presented to the bank, the bank compares it with the list of checks.</span></span> <span data-ttu-id="39a40-107">Om checken matchar en check i listan behandlar banken checken.</span><span class="sxs-lookup"><span data-stu-id="39a40-107">If the check matches a check in the list, the bank clears it.</span></span> <span data-ttu-id="39a40-108">Om checken inte matchar en check in listan kvarhåller banken checken för granskning.</span><span class="sxs-lookup"><span data-stu-id="39a40-108">If the check doesn't match a check in the list, the bank holds it for review.</span></span>

## <a name="security-for-positive-pay-files"></a><span data-ttu-id="39a40-109">Säkerhet för betalningskontrollfiler</span><span class="sxs-lookup"><span data-stu-id="39a40-109">Security for positive pay files</span></span>
<span data-ttu-id="39a40-110">Betalningskontrollfiler kan innehålla känslig information om betalningsmottagare och checkbelopp.</span><span class="sxs-lookup"><span data-stu-id="39a40-110">Positive pay files can contain sensitive information about payees and check amounts.</span></span> <span data-ttu-id="39a40-111">Se därför till att du använder lämpliga säkerhetsåtgärder från det att filerna skapas tills det att de tas emot av banken.</span><span class="sxs-lookup"><span data-stu-id="39a40-111">Therefore, make sure that you use appropriate security measures from the time that the files are generated until they are received by the bank.</span></span> <span data-ttu-id="39a40-112">Betalningskontrollfiler hämtas till den plats som anges av din webbläsare.</span><span class="sxs-lookup"><span data-stu-id="39a40-112">Positive pay files are downloaded to the location that is specified by your web browser.</span></span> <span data-ttu-id="39a40-113">Eftersom betalningskontrollfiler kan innehålla känslig information är det viktigt att endast auktoriserade användare har åtkomst för att generera eller visa den här informationen i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span><span class="sxs-lookup"><span data-stu-id="39a40-113">Because positive pay files can contain sensitive information, it's important that only authorized users have access to generate and view this information in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span> <span data-ttu-id="39a40-114">Använd följande tabell som hjälper dig att bestämma behörigheterna som krävs.</span><span class="sxs-lookup"><span data-stu-id="39a40-114">Use the following table to help you determine the privileges that are required.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39a40-115">Uppgift</span><span class="sxs-lookup"><span data-stu-id="39a40-115">Task</span></span></th>
<th><span data-ttu-id="39a40-116">Privilegium</span><span class="sxs-lookup"><span data-stu-id="39a40-116">Privilege</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="39a40-117">Generera betalningskontrollfiler från listsidan <strong>Bankkonton</strong> eller från sidan <strong>Bankkonton</strong>.</span><span class="sxs-lookup"><span data-stu-id="39a40-117">Generate positive pay files from the <strong>Bank accounts</strong> list page or the <strong>Bank accounts</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="39a40-118"><strong>Hantera information om betalningskontroll</strong> (BankPositivePayProcess)</span><span class="sxs-lookup"><span data-stu-id="39a40-118"><strong>Maintain bank positive pay information</strong> (BankPositivePayProcess)</span></span></li>
<li><span data-ttu-id="39a40-119"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span><span class="sxs-lookup"><span data-stu-id="39a40-119"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="39a40-120">Generera betalningskontrollfiler för flera juridiska personer och bankkonton från sidan <strong>Skapa en betalningskontrollfil</strong>.</span><span class="sxs-lookup"><span data-stu-id="39a40-120">Generate positive pay files for multiple legal entities and bank accounts from the <strong>Generate a positive pay file</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="39a40-121"><strong>Hantera information om betalningskontroll</strong> (BankPositivePayProcess)</span><span class="sxs-lookup"><span data-stu-id="39a40-121"><strong>Maintain bank positive pay information</strong> (BankPositivePayProcess)</span></span></li>
<li><span data-ttu-id="39a40-122"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span><span class="sxs-lookup"><span data-stu-id="39a40-122"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="39a40-123">Visa betalningskontrollfiler på sidan <strong>Sammanfattning om betalningskontrollfil</strong>.</span><span class="sxs-lookup"><span data-stu-id="39a40-123">View positive pay files on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="39a40-124"><strong>Visa bankbetalningskontrolluppgifter för flera juridiska personer</strong> (BankPositivePayView)</span><span class="sxs-lookup"><span data-stu-id="39a40-124"><strong>View bank positive pay information for multiple legal entities</strong> (BankPositivePayView)</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="39a40-125">Bekräfta en betalningskontrollfil på sidan <strong>Sammanfattning om betalningskontrollfil</strong>.</span><span class="sxs-lookup"><span data-stu-id="39a40-125">Confirm a bank positive pay file on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="39a40-126"><strong>Bekräfta betalningskontrollfil</strong> (BankPositivePayConfirm)</span><span class="sxs-lookup"><span data-stu-id="39a40-126"><strong>Confirm positive payment file</strong> (BankPositivePayConfirm)</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="39a40-127">Återkalla en betalningskontrollfil på sidan <strong>Sammanfattning om betalningskontrollfil</strong>.</span><span class="sxs-lookup"><span data-stu-id="39a40-127">Recall a bank positive pay file on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="39a40-128"><strong>Återkalla en betalningskontrollfil</strong> (BankPositivePayRecall)</span><span class="sxs-lookup"><span data-stu-id="39a40-128"><strong>Recall positive pay file</strong> (BankPositivePayRecall)</span></span></td>
</tr>
</tbody>
</table>

## <a name="set-up-a-positive-pay-format"></a><span data-ttu-id="39a40-129">Konfigurera ett format för betalningskontrollfil</span><span class="sxs-lookup"><span data-stu-id="39a40-129">Set up a positive pay format</span></span>
<span data-ttu-id="39a40-130">Betalningskontrollfiler skapas genom att använda dataentiteter.</span><span class="sxs-lookup"><span data-stu-id="39a40-130">Positive pay files are created by using data entities.</span></span> <span data-ttu-id="39a40-131">Innan du kan generera en betalningskontrollfil måste du ställa in ett indataformat för transformation som ska användas för att översätta checkinformationen till ett format som kan kommunicera med banken.</span><span class="sxs-lookup"><span data-stu-id="39a40-131">Before you can generate a positive pay file, you must set up a transformation input format that will be used to translate the check information into a format that can communicate with the bank.</span></span> <span data-ttu-id="39a40-132">På sidan **Format för kontrollfil** kan du skapa en filformatidentifierare och en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="39a40-132">On the **Positive pay format** page, you can create a file format identifier and a description.</span></span> <span data-ttu-id="39a40-133">Indataformatet för transformationen måste vara av XML-typ.</span><span class="sxs-lookup"><span data-stu-id="39a40-133">The transformation input format must be of the XML type.</span></span> <span data-ttu-id="39a40-134">Det specifika formatet beror på transformeringsfilen som du använder.</span><span class="sxs-lookup"><span data-stu-id="39a40-134">The specific format depends on the transformation file that you're using.</span></span> <span data-ttu-id="39a40-135">Den tillhandahållna XSLT-exempelfilen (Extensible Stylesheet Language Transformations) använder **XML-Element**-formatet.</span><span class="sxs-lookup"><span data-stu-id="39a40-135">For example, the sample Extensible Stylesheet Language Transformations (XSLT) file that is provided uses the **XML-Element** format.</span></span> <span data-ttu-id="39a40-136">Använd **Överför filen som ska användas för transformation** åtgärden för att ange platsen för transformationsfilen för det format som krävs för banken.</span><span class="sxs-lookup"><span data-stu-id="39a40-136">Use the **Upload file used for transformation** action to specify the location of the transform file for the format that your bank requires.</span></span>

## <a name="example-xslt-file-for-positive-pay-file"></a><span data-ttu-id="39a40-137">Exempel: XSLT-fil för betalningskontrollfil</span><span class="sxs-lookup"><span data-stu-id="39a40-137">Example: XSLT file for positive pay file</span></span>
    <xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl xslthelper" xmlns="urn:iso:std:iso:20022:tech:xsd:pain.001.001.02" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xslthelper="http://schemas.microsoft.com/BizTalk/2003/xslthelper">
      <xsl:output method="xml" omit-xml-declaration="no" version="1.0" encoding="utf-8"/>
      <xsl:template match="/">
        <xsl:value-of select="'
    '" />
        <Document>
          <xsl:value-of select="'
    '" />
          <!--Header Begin-->
          <xsl:value-of select='string("Vendor ID,Vendor Name,Voided,Document Type,Check Date,Check Number,Check Amount,Checkbook ID,Vendor Class ID,Posted Date")'/>
          <xsl:value-of select="'
    '" />
          <!--Header End-->
          <xsl:for-each select="Document/BankPositivePayExportEntity">
            <!--Cheque Detail begin-->
            <xsl:value-of select='RECIPIENTACCOUNTNUM/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='BANKNEGINSTRECIPIENTNAME/text()'/>
            <xsl:value-of select="','" />
            <xsl:choose>
              <xsl:when test='CHEQUESTATUS/text()=normalize-space("Void") or CHEQUESTATUS/text()=normalize-space("Rejected") or CHEQUESTATUS/text()=normalize-space("Cancelled")'>
                <xsl:value-of select='string("Yes")'/>
              </xsl:when>
              <xsl:when test='CHEQUESTATUS/text()=normalize-space("Payment")'>
                <xsl:value-of select='string("No")'/>
              </xsl:when>
              <xsl:otherwise>
                <xsl:value-of select='string(" ")'/>
              </xsl:otherwise>
            </xsl:choose>
            <xsl:value-of select="','" />
            <xsl:value-of select='string("Payment")'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='TRANSDATE/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='CHEQUENUM/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='AMOUNTCUR/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='string("BOA-#1812")'/>
            <xsl:value-of select="','" />
            <xsl:choose>
              <xsl:when test='RECIPIENTTYPE/text()=normalize-space("Vend")'>
                <xsl:value-of select='VENDGROUP/text()'/>
              </xsl:when>
              <xsl:otherwise>
                <xsl:value-of select='CUSTGROUP/text()'/>
              </xsl:otherwise>
            </xsl:choose>
            <xsl:value-of select="','" />
            <xsl:value-of select='TRANSDATE/text()'/>
            <xsl:value-of select="'
    '" />
          </xsl:for-each>
        </Document>
      </xsl:template>
    </xsl:stylesheet>

## <a name="assign-the-positive-pay-format-to-a-bank-account"></a><span data-ttu-id="39a40-138">Tilldela formatet för kontrollfil till ett bankkonto</span><span class="sxs-lookup"><span data-stu-id="39a40-138">Assign the positive pay format to a bank account</span></span>
<span data-ttu-id="39a40-139">För varje bankkonto som du vill skapa information om lönebetalningskontroll för måste du tilldela lönebetalningskontrollformatet som har angetts i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="39a40-139">For each bank account that you want to generate positive pay information for, you must assign the positive pay format that you specified in the previous section.</span></span> <span data-ttu-id="39a40-140">På sidan **Bankkonton**, välj det format för betalningskontrollfil som motsvarar bankkontot.</span><span class="sxs-lookup"><span data-stu-id="39a40-140">On the **Bank accounts** page, select the positive pay format that corresponds to the bank account.</span></span> <span data-ttu-id="39a40-141">I fältet **Betalningskontrollens startdatum**, ange det första datumet då betalningskontrollfiler ska genereras.</span><span class="sxs-lookup"><span data-stu-id="39a40-141">In the **Positive pay start date** field, enter the first date to generate positive pay files.</span></span> <span data-ttu-id="39a40-142">Det är viktigt att du anger ett datum i det här fältet.</span><span class="sxs-lookup"><span data-stu-id="39a40-142">It's important that you enter a date in this field.</span></span> <span data-ttu-id="39a40-143">Annars kommer den första betalningskontrollfil som du skapar inkludera alla checkar som någonsin har skapats för detta bankkonto.</span><span class="sxs-lookup"><span data-stu-id="39a40-143">Otherwise, the first positive pay file that you generate will include all checks that have ever been created for this bank account.</span></span>

## <a name="assign-a-number-sequence-for-positive-pay-files"></a><span data-ttu-id="39a40-144">Tilldela en nummersekvens för betalningskontrollfiler</span><span class="sxs-lookup"><span data-stu-id="39a40-144">Assign a number sequence for positive pay files</span></span>
<span data-ttu-id="39a40-145">Varje betalningskontrollfil måste ha ett unikt nummer.</span><span class="sxs-lookup"><span data-stu-id="39a40-145">Each positive pay file must have a unique number.</span></span> <span data-ttu-id="39a40-146">Använd fliken **Nummersekvenser** på sidan **Parametrar för kassa- och bankhantering** för att skapa en nummersekvens för betalningskontrollfiler.</span><span class="sxs-lookup"><span data-stu-id="39a40-146">Use the **Number sequences** tab on the **Cash and bank management parameters** page to create a number sequence for positive pay files.</span></span>

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a><span data-ttu-id="39a40-147">Generera en betalningskontrollfil för ett enskilt bankkonto</span><span class="sxs-lookup"><span data-stu-id="39a40-147">Generate a positive pay file for a single bank account</span></span>
<span data-ttu-id="39a40-148">Du kan generera en betalningskontroll för en enda juridisk person och ett enskilt bankkonto.</span><span class="sxs-lookup"><span data-stu-id="39a40-148">You can generate a positive pay file for a single legal entity and a single bank account.</span></span> <span data-ttu-id="39a40-149">Information om hur du genererar betalningskontrollfiler för flera juridiska personer och bankkonton samtidigt finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="39a40-149">For information about how to generate positive pay files for multiple legal entities and bank accounts at the same time, see the next section.</span></span> <span data-ttu-id="39a40-150">Om du vill skapa en betalningskontrollfil för ett enskilt bankkonto, öppna dialogrutan **Skapa en betalningskontrollfil** på sidan **Bankkonton**.</span><span class="sxs-lookup"><span data-stu-id="39a40-150">To generate a positive pay file for a single legal entity and a single bank account, open the **Generate a positive pay file** dialog box from the **Bank accounts** page.</span></span> <span data-ttu-id="39a40-151">I fältet **Slutdatum**, ange det datum för senaste kontroll som ska inkluderas i betalningskontrollfilen.</span><span class="sxs-lookup"><span data-stu-id="39a40-151">In the **Cut-off date** field, enter the last check date to include in the positive pay file.</span></span> <span data-ttu-id="39a40-152">Alla checkar som inte har inkluderats i en betalningskontrollfil innan slutet av det här checkdatumet inkluderas i filen.</span><span class="sxs-lookup"><span data-stu-id="39a40-152">All checks that haven’t been included in a positive pay file by the end of this check date are included in the file.</span></span>

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a><span data-ttu-id="39a40-153">Generera en betalningskontrollfil för flera bankkonton</span><span class="sxs-lookup"><span data-stu-id="39a40-153">Generate a positive pay file for multiple bank accounts</span></span>
<span data-ttu-id="39a40-154">Generera en betalningskontrollfil för flera bankkonton med hjälp av den periodiska uppgiften **Skapa en betalningskontrollfil**.</span><span class="sxs-lookup"><span data-stu-id="39a40-154">To generate a positive pay file for multiple bank accounts, use the **Generate a positive pay file** periodic task.</span></span> <span data-ttu-id="39a40-155">Välj format för kontrollfilen och ange om du vill generera betalningskontrollfilen för alla juridiska personer eller för en vald juridisk person.</span><span class="sxs-lookup"><span data-stu-id="39a40-155">Select the positive pay format for the file, and specify whether to generate the file for all legal entities or for a selected legal entity.</span></span> <span data-ttu-id="39a40-156">Du kan även generera betalningskontrollfilen för alla bankkonton som använder det specificerade formatet för kontrollfilen eller för ett valt bankkonto.</span><span class="sxs-lookup"><span data-stu-id="39a40-156">You can also generate the positive pay file for all bank accounts that use the specified positive pay format or for a selected bank account.</span></span> <span data-ttu-id="39a40-157">I fältet **Slutdatum**, ange det datum för senaste kontroll som ska inkluderas i betalningskontrollfilen.</span><span class="sxs-lookup"><span data-stu-id="39a40-157">In the **Cut-off date** field, enter the last check date to include in the positive pay file.</span></span> <span data-ttu-id="39a40-158">Alla checkar som inte har inkluderats i en betalningskontrollfil innan slutet av det här checkdatumet inkluderas i filen.</span><span class="sxs-lookup"><span data-stu-id="39a40-158">All checks that haven’t been included in a positive pay file by the end of this check date are included in the file.</span></span>

## <a name="view-the-results-of-positive-pay-file-generation"></a><span data-ttu-id="39a40-159">Visa resultaten av skapandet av betalningskontrollfilen</span><span class="sxs-lookup"><span data-stu-id="39a40-159">View the results of positive pay file generation</span></span>
<span data-ttu-id="39a40-160">När betalningskontrollfilen har skapats kan du visa resultaten på sidan **Sammanfattning om betalningskontrollfil**.</span><span class="sxs-lookup"><span data-stu-id="39a40-160">After the positive pay file is generated, you can view the results on the **Positive pay file summary** page.</span></span> <span data-ttu-id="39a40-161">Använd detaljsidan **Betalningskontrollfil** för att visa information om de enskilda checkarna.</span><span class="sxs-lookup"><span data-stu-id="39a40-161">To view the details of the individual checks, use the **Positive pay file** details page.</span></span>

## <a name="confirm-a-positive-pay-file"></a><span data-ttu-id="39a40-162">Bekräfta en betalningskontrollfil</span><span class="sxs-lookup"><span data-stu-id="39a40-162">Confirm a positive pay file</span></span>
<span data-ttu-id="39a40-163">När checkarna som anges i en betalningskontrollfil har betalats får du ett bekräftelsenummer från banken.</span><span class="sxs-lookup"><span data-stu-id="39a40-163">After the checks that are listed in a positive pay file have been paid, you receive a confirmation number from your bank.</span></span> <span data-ttu-id="39a40-164">Sedan kan du bekräfta betalningskontrollfilen.</span><span class="sxs-lookup"><span data-stu-id="39a40-164">You can then confirm the positive pay file.</span></span> <span data-ttu-id="39a40-165">På sidan **Sammanfattning om betalningskontrollfil**, välj en betalningskontrollfil som har statusen **Skapat** och välj sedan åtgärden **Ange bekräftelse**.</span><span class="sxs-lookup"><span data-stu-id="39a40-165">On the **Positive pay file summary** page, select a positive pay file that has a status of **Created**, and then select the **Enter confirmation** action.</span></span> <span data-ttu-id="39a40-166">Vid bekräftelsen av en betalningskontrollfil registreras bekräftelsenumret som du fått från banken.</span><span class="sxs-lookup"><span data-stu-id="39a40-166">When you confirm a positive pay file, the confirmation number that you received from the bank is recorded.</span></span>

## <a name="recall-a-positive-pay-file"></a><span data-ttu-id="39a40-167">Återkalla en betalningskontrollfil</span><span class="sxs-lookup"><span data-stu-id="39a40-167">Recall a positive pay file</span></span>
<span data-ttu-id="39a40-168">Om du måste ändra en betalningskontrollfil kan du sedan återkalla den.</span><span class="sxs-lookup"><span data-stu-id="39a40-168">If you must change a positive pay file, you can recall it.</span></span> <span data-ttu-id="39a40-169">På sidan **Sammanfattning om betalningskontrollfil**, välj en betalningskontrollfil som har statusen **Skapat** och välj sedan åtgärden **Återkalla**.</span><span class="sxs-lookup"><span data-stu-id="39a40-169">On the **Positive pay file summary** page, select a positive pay file that has a status of **Created**, and then select the **Recall** action.</span></span> <span data-ttu-id="39a40-170">För varje check i betalningskontrollfilen återställs fältet som anger om denna check har inkluderats i en betalningskontrollfil.</span><span class="sxs-lookup"><span data-stu-id="39a40-170">For each check in the positive pay file, the field that indicates whether that check has been included in a positive pay file is reset.</span></span> <span data-ttu-id="39a40-171">Sedan kan du skapa en ny betalningskontrollfil som innehåller den check som återkallades.</span><span class="sxs-lookup"><span data-stu-id="39a40-171">You can then create a new positive pay file that includes the check that was recalled.</span></span>




