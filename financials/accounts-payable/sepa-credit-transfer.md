---
title: "Översikt över SEPA-kreditöverföring"
description: "Artikeln innehåller allmän information om ISO 20022 betalningar, som inkluderar enstaka Euro betalningar område (SEPA) betalningar och andra elektroniska betalningar för leverantörer. En SEPA-betalning är en särskild typ av betalningar i euro från ett företag eller enskilda till ett annat företag eller enskilda. Avsnittet lär dig också att skapa och skicka en betalningsfil för överföring av kredit."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, VendPaymMode
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11124
ms.assetid: 36b0f870-16d4-4bbb-8da5-e747e69b970d
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 848df5e3898f37284d7746c59bff8b38d35ac883
ms.lasthandoff: 03/31/2017


---

# <a name="sepa-credit-transfer-overview"></a>Översikt över SEPA-kreditöverföring

Artikeln innehåller allmän information om ISO 20022 betalningar, som inkluderar enstaka Euro betalningar område (SEPA) betalningar och andra elektroniska betalningar för leverantörer. En SEPA-betalning är en särskild typ av betalningar i euro från ett företag eller enskilda till ett annat företag eller enskilda. Avsnittet lär dig också att skapa och skicka en betalningsfil för överföring av kredit.

## <a name="what-is-a-credit-transfer-message"></a>Vad är en kredit överföringen?
Kredit överföringen meddelandet är en förfrågan som en initierande part (företaget) skickar du flyttar medel från eget bruk till en fordringshavare. Det finns många lands-/ regionspecifika och bank-specifika implementeringar av betalning meddelanden. Några av tecknen används inom ett land/region och blir vissa standarder. En väl etablerad global standard är ISO 20022 och dess inledande meddelandet, t ex betalning. Följande bild visar relationer och artikeldisponering för valda kredit överför meddelanden. 
![Kreditera överföringen har](./media/credit-transfer.jpg) kredit överför meddelanden\[/beskrivning\] 

## <a name="what-are-iso-20022-and-sepa-payments"></a>Vad är ISO 20022 och SEPA-betalningar?
SEPA (Single Euro Payments Area) skapas av den europeiska kommissionen och anger att alla elektroniska betalningar ska betraktas som inhemska oavsett i vilket land/region personen, företaget eller organisationen och banken finns. Det är ingen skillnad mellan betalningar och gränsöverskridande transaktioner. SEPA innehåller 28 medlemsstater i Europeiska unionen (EU) och även Island, Liechtenstein, Norge, Schweiz, Monaco och San Marino. SEPA hjälper till att skapa en gemensam marknad för betalningstransaktioner inom Europeiska ekonomiska samarbetsområdet (EES). Slutligen förväntas SEPA minska antalet betalningsformat, som banker, företag och individer måste arbeta med. Europeiska kommissionen etablerade den juridiska grunden för SEPA-betalningar med betalningstjänstdirektivet (PSD). Det europeiska betalningsrådet (EPC) stöder SEPA genom följande aktiviteter:

-   Den anger standarden för elektroniska SEPA-betalningar genom att använda finansbranschens gemensamma XML-format enligt ISO 20022.
-   Den fastställer regler och riktlinjer om hur du hanterar eurobetalningar.

EPC som består av ett antal europeiska banker, utvecklar de kommersiella och tekniska ramverken för SEPA-betalningsinstrument. Tre typer av SEPA-betalningar används:

-   Kreditöverföringar
-   Direktdebiteringar
-   Kort

## <a name="what-is-a-sepa-credit-transfer"></a>Vad är en SEPA-kreditöverföring?
En SEPA-överföring är en betalning från ett företag eller en person till ett annat företag eller annan person. Betalningar måste vara i euro och måste inkludera det internationella bankkontonumret (IBAN) och bankidentifierarkoden (BIC) för båda parterna. (BIC kallas Society for Worldwide Interbank Financial Telecommunication \[SWIFT\] kod.) Transaktionskostnader får delas mellan de båda parterna. Krediteringsöverföringar som uppstår mellan parterna ska använda XML-filer som överensstämmer med ISO 20022-standarderna för betalning och XML-formatet, som anges av EPC.

## <a name="how-is-a-credit-transfer-implemented"></a>Hur implementeras en betalning
Kredit överföringen betalningsformat för europeiska länder implementeras med elektronisk rapportering (ER) och metoderna för funktionen betalning i Dynamics 365 för operationer. Några kredit överföringsformat som används i andra regioner fortfarande använda äldre betalning ramverket. Det finns tolv ISO 20022 kredit överföringen filformat som finns bland många andra format. Följande exportformat motsvarar SEPA ISO 20022 XML-standarden. Används för att generera icke eurokomponenter betalningsöverföringar för länder/regioner där de används och betalningar i euro enligt version 8.2 av SEPA kredit överför schemat föreskrifter som faller som släpps på EPC. Innan du kan implementera betalningar måste du kontakta din bank och hämta programvara som krävs för att överföra filer för elektronisk bankverksamhet. Programmet använder du vill överföra de XML-filer som innehåller betalningsorder till banken.

## <a name="what-credit-transfer-formats-are-currently-supported-in-dynamics-365-for-operations"></a>Vilken kredit överföringsformat stöds i Dynamics 365 för operationer?
Du bör alltid gå till delade resursbiblioteket Microsoft Dynamics Lifecycle Services (LCS) och visa en lista över tillgängliga filer som har en tillgångstyp av **konfigurationen GER**. Nästa avsnitt, "Vad måste jag skapa?", som innehåller en länk till ett hjälpavsnitt som beskriver hur du skapar en databas LCS Granska tillgängliga konfigurationer och importera valda konfigurationer.

## <a name="what-do-i-have-to-set-up"></a>Vad måste jag ställa in?
-   Innan du kan skapa betalning filer ska minst en aktiv konfiguration av överföring importeras till ER-konfigurationer. Instruktioner finns i [hämta elektronisk rapportering konfigurationer från Lifecycle Services](https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).
-   När du konfigurerar konton Leverantörsreskontra betalningsmetoder markerar du den **allmän elektronisk rapportering** kryssrutan och välj lämplig kredit överföringsformat (till exempel **ISO 20022 överföring (AT)**) som en formatkonfigurationen för export.
-   Du måste även ställa in juridisk enhet och bankkonto information i Dynamics 365 för operationer.
-   Bankkontonummer IBANs och ibland SWIFT-kod (BICs) eller andra ID krävs för att skapa giltiga betalning betalningar. Därför måste du ställa in dem för leverantörens bankkonto och bankkontot för organisationen som begär överföringen.
-   Ytterligare information kan krävas, t.ex moms (VAT) nummer för parter som anges i meddelandet kredit överföringen. Denna information måste ställas in för den juridiska personen och leverantörer när det krävs.
-   Vissa konton Leverantörsreskontra betalningsmetoder, oftast 20022 ISO-baserade betalningsmetoder, kanske kräver ytterligare inställningar för **betalning format koduppsättningar**, t ex **Service typen** = **SLEV**. Dessa koder kan användas som ytterligare märkning för betalningstransaktioner under betalningarna ska kunna behandlas. Standardvärden för koder, som **kategori syfte**, **tillägget innehavaren**, **instrument för lokala** och **Service nivå** kan ställas in på två olika platser. Den första decimalen är **konton utgående betalning journalrubriken** och andra **Accounts payable metoder för betalningar**. När den payment journal rader skapas betalningen kodvärden bedrev journalrubriken betalning är överförs till en journalrad, om inte är aktiverad används värdena från betalningsmetoder.

## <a name="what-parameters-are-available-for-generating-credit-transfer-payments"></a>Vilka parametrar som är tillgängliga för att generera betalningar kredit överföringen?
En lista över specifika parametrar beror på överföringsformat kredit. Följande tabell visar de parametrar som är tillgängliga när du skapar en ISO 20022 kredit överföringen betalningsfil för Tyskland i en leverantörsbetalningsjournal. Med hjälp av verktygen som finns tillgängliga i den **körs i bakgrunden** och du kör Betalningsgenerering i batchläge.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Fält</th>
<th>beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Samlad debitering</td>
<td>Markera den här kryssrutan om du vill inkludera buntbokningsmärket i XML-filen.</td>
</tr>
<tr class="even">
<td>Bearbetningsdatum</td>
<td>Ange datumet när banken ska bearbeta betalningarna.</td>
</tr>
<tr class="odd">
<td>Format</td>
<td>Välj formatet för information om remissan beroende på kraven för ditt land/din region eller bank:
<ul>
<li><strong>Strd</strong> – Markera alternativet om du vill använda formatet för strukturerade när en betalningsrad kvittas mot en faktura. Det här alternativet är inte tillgängligt för lands-/ regionspecifika exportformat för Frankrike, Tyskland och Nederländerna.</li>
<li><strong>Ustrd</strong> – Markera det här alternativet för att använda det ostrukturerade formatet när betalningen kvittas mot flera fakturor. Fakturanumren för de kvittade fakturorna sammanfogas och används som remitteringsinformation. I enlighet med ISO 20022 riktlinjer ostrukturerad Remitteringsinformation begränsas till 140 tecken.</li>
</ul></td>
</tr>
<tr class="even">
<td>Antal fakturor</td>
<td>Ange antalet fakturor som den <strong>betalningsavi</strong> rapporten ut från.</td>
</tr>
<tr class="odd">
<td>Löpnummer</td>
<td>Ange ett sekvensnummer för att identifiera filen. Sekvensnumret visas på de <strong>notering om deltagande</strong> rapporten.</td>
</tr>
<tr class="even">
<td>Skriv ut notering om deltagande</td>
<td>Markera den här kryssrutan om du vill skriva ut rapporten <strong>Notering om deltagande</strong>.</td>
</tr>
<tr class="odd">
<td>Skriv ut kontrollrapport</td>
<td>Markera kryssrutan om du vill skriva ut en rapport med betalningsinformationen.</td>
</tr>
<tr class="even">
<td>Skriv ut följebrev</td>
<td>Markera den här kryssrutan om du vill skriva ut rapporten <strong>Betalningsavi</strong>.</td>
</tr>
</tbody>
</table>

## <a name="what-are-ibans-and-bics"></a>Vad är IBAN och BIC?
Bankkonto IBAN (International Number) och kod BIC (Bank Identifier) används för att identifiera alla konton i många länder/regioner över hela världen. Dessa inkluderar 34 SEPA länder/regioner. Ange BIC i den **SWIFT-kod** fältet och IBAN i den **IBAN** fält. Fälten för både borgenärens konto och kundens bankkonto finns på den **ytterligare identifiering** snabbfliken i den **bankkonto** fliken i den **bankkonton** sida. Användning av BIC för SEPA-betalningar gäller inte längre.

## <a name="how-do-i-transmit-a-payment-file-to-the-bank"></a>Hur överför jag en betalningsfil till banken?
När du genererar betalningar betalningsfilen skapas och du uppmanas att spara den på en viss plats i din webbläsare. Nästa steg är att skicka XML-filen till banken. Den här processen varierar från bank till bank. Följ instruktionerna från banken om att skicka in filerna till banken för bearbetning.


