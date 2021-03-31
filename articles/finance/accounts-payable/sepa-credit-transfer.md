---
title: Översikt över SEPA-kreditöverföring
description: Artikeln innehåller allmän information om ISO 20022 kreditöverföringar, som inkluderar SEPA-kreditöverföringar ( Single Euro Payments Area) och andra elektroniska betalningar för leverantörer. En SEPA-kreditöverföring är specifik typ av betalning i euro från ett företag eller en person till ett annat företag eller annan person. Ämnet beskriver även hur du ställer in och överför en fil för betalning med kreditöverföring.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, VendPaymMode
audience: Application User
ms.reviewer: roschlom
ms.custom: 11124
ms.assetid: 36b0f870-16d4-4bbb-8da5-e747e69b970d
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 277f11bc6aa74ac9bb9f476b07be7bbf29025342
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227410"
---
# <a name="sepa-credit-transfer-overview"></a>Översikt över SEPA-kreditöverföring

[!include [banner](../includes/banner.md)]

Artikeln innehåller allmän information om ISO 20022 kreditöverföringar, som inkluderar SEPA-kreditöverföringar ( Single Euro Payments Area) och andra elektroniska betalningar för leverantörer. En SEPA-kreditöverföring är specifik typ av betalning i euro från ett företag eller en person till ett annat företag eller annan person. Ämnet beskriver även hur du ställer in och överför en fil för betalning med kreditöverföring.

## <a name="what-is-a-credit-transfer-message"></a>Vad är ett kreditöverföringsmeddelande?
Kreditöverföringsmeddelandet är en begäran som en initierande part (ditt företag) skickar för att flytta medel från eget konto till en fordringshavare. Det finns många lands-/regionspecifika och bankspecifika implementeringar av betalningsmeddelanden. Några av dem används inom ett land/en region och vissa blir standarder. En väl etablerad global standard är ISO 20022 och dess initieringsmeddelandet som t.ex. kreditöverföring. Följande bild visar relationerna och täckning för valda kreditöverföringsmeddelanden. 
![Kreditöverföring](./media/credit-transfer.jpg) Kreditöverföringsmeddelanden 

## <a name="what-are-iso-20022-and-sepa-payments"></a>Vad är ISO 20022 och SEPA-betalningar?
SEPA (Single Euro Payments Area) skapas av den europeiska kommissionen och anger att alla elektroniska betalningar ska betraktas som inhemska oavsett i vilket land/region personen, företaget eller organisationen och banken finns. Det finns inte någon skillnad mellan nationella och gränsöverskridande betalningar. SEPA inkluderar de 28 medlemsstaterna i Europeiska unionen plus Island, Liechtenstein, Norge, Schweiz, Monaco och San Marino. SEPA hjälper till att skapa en gemensam marknad för betalningstransaktioner inom Europeiska ekonomiska samarbetsområdet (EES). Slutligen förväntas SEPA minska antalet betalningsformat, som banker, företag och individer måste arbeta med. Europeiska kommissionen etablerade den juridiska grunden för SEPA-betalningar med betalningstjänstdirektivet (PSD). Det europeiska betalningsrådet (EPC) stöder SEPA genom följande aktiviteter:

-   Den anger standarden för elektroniska SEPA-betalningar genom att använda finansbranschens gemensamma XML-format enligt ISO 20022.
-   Den fastställer regler och riktlinjer om hur du hanterar eurobetalningar.

EPC som består av ett antal europeiska banker, utvecklar de kommersiella och tekniska ramverken för SEPA-betalningsinstrument. Tre typer av SEPA-betalningar används:

-   Kreditöverföringar
-   Direktdebiteringar
-   Kort

## <a name="what-is-a-sepa-credit-transfer"></a>Vad är en SEPA-kreditöverföring?
En SEPA-överföring är en betalning från ett företag eller en person till ett annat företag eller annan person. Betalningar måste vara i euro och måste inkludera det internationella bankkontonumret (IBAN) och bankidentifierarkoden (BIC) för båda parterna. (BIC kallas även Society for Worldwide Interbank Financial Telecommunication \[SWIFT\]-kod.) Transaktionskostnader måste delas mellan de båda parterna. Krediteringsöverföringar som uppstår mellan parterna ska använda XML-filer som överensstämmer med ISO 20022-standarderna för betalning och XML-formatet, som anges av EPC.

## <a name="how-is-a-credit-transfer-implemented"></a>Hur utförs en kreditöverföring?
Betalningsformatet för kreditöverföring för europeiska länder implementeras genom att använda funktionerna för elektronisk rapportering och betalningsmetod i Microsoft Dynamics 365 Finance. Några får kreditöverföringsformat som används i andra regioner använder fortfarande äldre betalningsramverk. Bland många andra format finns det tolv ISO 20022 kreditöverföringsfilformat tillgängliga. Följande exportformat motsvarar SEPA ISO 20022 XML-standarden. De används för att generera betalningsöverföringar som inte är i euro för länder/regioner där de används och betalningar i euro enligt version 8.2 av SEPA Credit Transfer Scheme Rulebook som EPC släpper. Innan du inför kreditöverföringar måste du kontakta din bank för att erhålla programvaran som krävs för att överföra elektroniska bankfiler. Du använder programmet för att överföra XML-filerna som innehåller betalningsorder till banken.

## <a name="what-credit-transfer-formats-are-currently-supported"></a>Vilka kreditöverföringsformat stöds för närvarande?
Du bör alltid gå till det delade resursbiblioteket i Microsoft Dynamics Lifecycle services (LCS) och visa en lista över tillgängliga filer som har tillgångstypen **GER-konfiguration**. Nästa avsnitt "Vad måste jag ställa in?" innehåller en länk till ett hjälpavsnitt som beskriver hur du skapar en LCS-databas för att granska tillgängliga konfigurationer och importera valda konfigurationer.

## <a name="what-do-i-have-to-set-up"></a>Vad måste jag ställa in?
-   Innan du skapar kreditöverföringsfiler måste minst en aktiv konfiguration för kreditöverföring importeras till dina ER-konfigurationer. Instruktioner finns i [Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
-   När du konfigurerar betalsätt för leverantörsreskontra markerar du kryssrutan **Generisk elektronisk rapportering** och väljer lämpligt format (för kreditöverföring (t.ex.) **ISO 20022 kreditöverföring (AT)**) som en exportformatkonfiguration.
-   Du måste även ange information om den juridiska personen och om bankkontot.
-   Bankkontonummer, IBAN och ibland SWIFT-koder (BIC) eller andra ID krävs för att skapa giltiga kreditöverföringsbetalningar. Därför måste du ställa in dem för leverantörsbankkonto och bankkontot för organisationen som begär överföringen.
-   Ytterligare information kan krävas, t.ex momsnummer (VAT) för parter som anges i kreditöverföringsmeddelandet. Denna information måste ställas in för leverantörer och för den juridiska personen när det krävs.
-   Vissa betalsätt för leverantörsreskontra, oftast 20022 ISO-baserade betalsätt, kanske kräver ytterligare inställningar för **Uppsättningar av betalningsformatkoder**, som t.ex. **Servicetyp** = **SLEV**. Dessa koder kan användas som ytterligare märkning för betalningstransaktioner under betalningsbearbetning. Standardvärden för betalningskoder, som t.ex. **Kategorisyfte**, **Avgiftspliktig person**, **Lokalt instrument** och **Servicenivå** kan ställas in på två olika platser. Den första platsen är **Leverantörsbetalningsjournal för leverantörsreskontra** och den andra är **Betalsätt för leverantörsreskontra**. När den rader i betalningsjournalen skapas kommer de betalningkodvärden som anges i leverantörsbetalningsjournalen att överföras till en journalrad, om de inte anges används värdena från betalsätt.

## <a name="what-parameters-are-available-for-generating-credit-transfer-payments"></a>Vilka parametrar är tillgängliga för att generera betalning med kreditöverföring?
En lista över specifika parametrar beror på kreditöverföringsformatet. Följande tabell visar de parametrar som du kan använda när du skapar en fil för betalning med ISO 20022-kreditöverföring för Tyskland i en leverantörsbetalningsjournal. Genom att använda alternativen på fliken **Kör i bakgrunden** kan du köra betalningsgenereringar i buntläge.

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
<li><strong>Strd</strong> – Markera det här alternativet för att använda det strukturerade formatet när en betalningsrad kvittas mot en faktura. Det här alternativet är inte tillgängligt för de lands-/regionsspecifika exportformaten för Frankrike, Tyskland eller Nederländerna.</li>
<li><strong>Ustrd</strong> – Markera det här alternativet för att använda det ostrukturerade formatet när betalningen kvittas mot flera fakturor. Fakturanumren för de kvittade fakturorna sammanfogas och används som remitteringsinformation. I efterlevnad av ISO 20022-riktlinjer begränsas ostrukturerad remitteringsinformation till 140 tecken.</li>
</ul></td>
</tr>
<tr class="even">
<td>Antal fakturor</td>
<td>Ange antalet fakturor som <strong>Betalningsavirapporten</strong> skrivs ut från.</td>
</tr>
<tr class="odd">
<td>Löpnummer</td>
<td>Ange ett sekvensnummer för att identifiera filen. Sekvensnumret visas i rapporten <strong>Notering om deltagande</strong>.</td>
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
International Bank Account Number (IBAN) och Bank Identifier Code (BIC) används för att identifiera alla konton i många länder/regioner runt om i världen. Dessa inkluderar 34 SEPA-länder/regioner. Ange BIC i fältet **SWIFT-kod** och IBAN i fältet **IBAN**. För både fordringsägarens och kundens bankkonto finns dessa fält på snabbfliken **Ytterligare identifiering** på fliken **Bankkonto** på sidan **Bankkonton**. Användning av BIC för SEPA-betalningar gäller inte längre.

## <a name="how-do-i-transmit-a-payment-file-to-the-bank"></a>Hur överför jag en betalningsfil till banken?
När du genererar betalningar genereras betalningsfilen och du ombeds att spara den i webbläsaren till en tillgänglig plats. Nästa steg är att skicka XML-filen till banken. Den här processen varierar från bank till bank. Följ instruktionerna från banken om att skicka in filerna till banken för bearbetning.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]