---
title: "Ställa in och generera betalningskontrollfiler"
description: "Den här artikeln innehåller information om hur du ställer och genererar betalningskontrollfiler."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 408d08628da983a865e7eabc8ebe1ec05c390372
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="set-up-and-generate-positive-pay-files"></a>Ställa in och generera betalningskontrollfiler

[!include[banner](../includes/banner.md)]


Den här artikeln innehåller information om hur du ställer och genererar betalningskontrollfiler. 

Ställa in betalningskontroll för att generera en elektrisk lista med checkar som ges till banken. När checken sedan visas för banken, jämför banken checken med listan med checkar. Om checken matchar en check i listan behandlar banken checken. Om checken inte matchar en check in listan kvarhåller banken checken för granskning.

## <a name="security-for-positive-pay-files"></a>Säkerhet för betalningskontrollfiler
Betalningskontrollfiler kan innehålla känslig information om betalningsmottagare och checkbelopp. Se därför till att du använder lämpliga säkerhetsåtgärder från det att filerna skapas tills det att de tas emot av banken. Betalningskontrollfiler hämtas till den plats som anges av din webbläsare. Eftersom betalningskontrollfiler kan innehålla känslig information är det viktigt att endast auktoriserade användare har åtkomst för att generera eller visa den här informationen i Microsoft Dynamics 365 for Operations. Använd följande tabell som hjälper dig att bestämma behörigheterna som krävs.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Uppgift</th>
<th>Privilegium</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Generera betalningskontrollfiler från listsidan <strong>Bankkonton</strong> eller från sidan <strong>Bankkonton</strong>.</td>
<td><ul>
<li><strong>Hantera information om betalningskontroll</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="even">
<td>Generera betalningskontrollfiler för flera juridiska personer och bankkonton från sidan <strong>Skapa en betalningskontrollfil</strong>.</td>
<td><ul>
<li><strong>Hantera information om betalningskontroll</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Visa betalningskontrollfiler på sidan <strong>Sammanfattning om betalningskontrollfil</strong>.</td>
<td><strong>Visa bankbetalningskontrolluppgifter för flera juridiska personer</strong> (BankPositivePayView)</td>
</tr>
<tr class="even">
<td>Bekräfta en betalningskontrollfil på sidan <strong>Sammanfattning om betalningskontrollfil</strong>.</td>
<td><strong>Bekräfta betalningskontrollfil</strong> (BankPositivePayConfirm)</td>
</tr>
<tr class="odd">
<td>Återkalla en betalningskontrollfil på sidan <strong>Sammanfattning om betalningskontrollfil</strong>.</td>
<td><strong>Återkalla en betalningskontrollfil</strong> (BankPositivePayRecall)</td>
</tr>
</tbody>
</table>

## <a name="set-up-a-positive-pay-format"></a>Konfigurera ett format för betalningskontrollfil
Betalningskontrollfiler skapas genom att använda dataentiteter. Innan du kan generera en betalningskontrollfil måste du ställa in ett indataformat för transformation som ska användas för att översätta checkinformationen till ett format som kan kommunicera med banken. På sidan **Format för kontrollfil** kan du skapa en filformatidentifierare och en beskrivning. Indataformatet för transformationen måste vara av XML-typ. Det specifika formatet beror på transformeringsfilen som du använder. Den tillhandahållna XSLT-exempelfilen (Extensible Stylesheet Language Transformations) använder **XML-Element**-formatet. Använd **Överför filen som ska användas för transformation** åtgärden för att ange platsen för transformationsfilen för det format som krävs för banken.

## <a name="example-xslt-file-for-positive-pay-file"></a>Exempel: XSLT-fil för betalningskontrollfil
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

## <a name="assign-the-positive-pay-format-to-a-bank-account"></a>Tilldela formatet för kontrollfil till ett bankkonto
För varje bankkonto som du vill skapa information om lönebetalningskontroll för måste du tilldela lönebetalningskontrollformatet som har angetts i föregående avsnitt. På sidan **Bankkonton**, välj det format för betalningskontrollfil som motsvarar bankkontot. I fältet **Betalningskontrollens startdatum**, ange det första datumet då betalningskontrollfiler ska genereras. Det är viktigt att du anger ett datum i det här fältet. Annars kommer den första betalningskontrollfil som du skapar inkludera alla checkar som någonsin har skapats för detta bankkonto.

## <a name="assign-a-number-sequence-for-positive-pay-files"></a>Tilldela en nummersekvens för betalningskontrollfiler
Varje betalningskontrollfil måste ha ett unikt nummer. Använd fliken **Nummersekvenser** på sidan **Parametrar för kassa- och bankhantering** för att skapa en nummersekvens för betalningskontrollfiler.

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a>Generera en betalningskontrollfil för ett enskilt bankkonto
Du kan generera en betalningskontroll för en enda juridisk person och ett enskilt bankkonto. Information om hur du genererar betalningskontrollfiler för flera juridiska personer och bankkonton samtidigt finns i nästa avsnitt. Om du vill skapa en betalningskontrollfil för ett enskilt bankkonto, öppna dialogrutan **Skapa en betalningskontrollfil** på sidan **Bankkonton**. I fältet **Slutdatum**, ange det datum för senaste kontroll som ska inkluderas i betalningskontrollfilen. Alla checkar som inte har inkluderats i en betalningskontrollfil innan slutet av det här checkdatumet inkluderas i filen.

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a>Generera en betalningskontrollfil för flera bankkonton
Generera en betalningskontrollfil för flera bankkonton med hjälp av den periodiska uppgiften **Skapa en betalningskontrollfil**. Välj format för kontrollfilen och ange om du vill generera betalningskontrollfilen för alla juridiska personer eller för en vald juridisk person. Du kan även generera betalningskontrollfilen för alla bankkonton som använder det specificerade formatet för kontrollfilen eller för ett valt bankkonto. I fältet **Slutdatum**, ange det datum för senaste kontroll som ska inkluderas i betalningskontrollfilen. Alla checkar som inte har inkluderats i en betalningskontrollfil innan slutet av det här checkdatumet inkluderas i filen.

## <a name="view-the-results-of-positive-pay-file-generation"></a>Visa resultaten av skapandet av betalningskontrollfilen
När betalningskontrollfilen har skapats kan du visa resultaten på sidan **Sammanfattning om betalningskontrollfil**. Använd detaljsidan **Betalningskontrollfil** för att visa information om de enskilda checkarna.

## <a name="confirm-a-positive-pay-file"></a>Bekräfta en betalningskontrollfil
När checkarna som anges i en betalningskontrollfil har betalats får du ett bekräftelsenummer från banken. Sedan kan du bekräfta betalningskontrollfilen. På sidan **Sammanfattning om betalningskontrollfil**, välj en betalningskontrollfil som har statusen **Skapat** och välj sedan åtgärden **Ange bekräftelse**. Vid bekräftelsen av en betalningskontrollfil registreras bekräftelsenumret som du fått från banken.

## <a name="recall-a-positive-pay-file"></a>Återkalla en betalningskontrollfil
Om du måste ändra en betalningskontrollfil kan du sedan återkalla den. På sidan **Sammanfattning om betalningskontrollfil**, välj en betalningskontrollfil som har statusen **Skapat** och välj sedan åtgärden **Återkalla**. För varje check i betalningskontrollfilen återställs fältet som anger om denna check har inkluderats i en betalningskontrollfil. Sedan kan du skapa en ny betalningskontrollfil som innehåller den check som återkallades.




