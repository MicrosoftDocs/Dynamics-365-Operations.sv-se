---
title: Förskottsfakturor kontra förskottsbetalningar
description: Den här ämnet beskriver och kontrasterar de två metoderna som organisationer kan använda för förskottsbetalningar.
author: abruer
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, PurchTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 15871
ms.assetid: a0bb5220-73d4-48ae-84d0-46a171c224fa
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f05f1d8d2a1fb454f3f227d2cc8138f2b779ff87
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716337"
---
# <a name="prepayment-invoices-vs-prepayments"></a>Förskottsfakturor kontra förskottsbetalningar

[!include [banner](../includes/banner.md)]

Den här ämnet beskriver och kontrasterar de två metoderna som organisationer kan använda för förskottsbetalningar. En metod skapar en förskottsfaktura som är kopplad till en inköpsorder. I den andra metoden skapar du verifikationer för förskottsbetalningsjournal genom att skapa journalposter och välja dem som verifikationer för förskottsbetalningsjournal.

Organisationer kan utfärda förskottsbetalningar till leverantörer för varor och tjänster, innan dessa varor eller tjänster är uppfyllda. Två metoder kan användas för att utfärda förskottsbetalningar till leverantörer. För att minimera risk kan du följa förskottsbetalningar, genom att definiera förskottsbetalningen i en inköpsorder. För den här metoden måste du skapa en förskottsfaktura som är kopplad till en inköpsorder. Denna metod kallas för förskottsbetalningsfakturering. Organisationer som inte vill följa förskottsbetalningar lika nära eller inte får en förskottsfaktura från deras leverantör, kan använda verifikationer för förskottsbetalningsjournal i stället för metoden förskottsbetalningsfakturering. Du kan skapa verifikationer för förskottsbetalningsjournal, genom att skapa journalposter och välja dem som verifikationer för förskottsbetalningsjournal. För den här metoden kan du inte följa vilka förskottsbetalningar till en leverantör som görs mot inköpsorder. Du kan dock välja en bokförd förskottsbetalning för kvittning mot en inköpsorder.

## <a name="when-to-use-prepayment-invoicing-vs-prepayments"></a>När ska du använda förskottsbetalningsfakturering kontra förskottsbetalningar.

| Förskottsfaktura                                                                | Förskottsbetalningar                                                              |
|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| Definiera förskottsbetalningsvärde på inköpsordern.                                    | Inget förskottsbetalningsvärde är definierat på inköpsordern.                    |
| En förskottsfaktura och en slutfaktura måste bokföras.                       | Ingen förskottsfaktura måste bokföras.                                    |
| Skulder för förskottsbetalningen hålls på kontot för förskottsbetalning, inte AP-kontot. | Skulder för förskottsbetalningen hålls på AP-kontot.                  |
| Leverantörssaldot återspeglar inte förskottsbetalningvärdet genom hela processen.     | Leverantörssaldot återspeglar förskottsbetalningvärdet genom hela processen. |
| Förskottsbetalningsfakturering är tillgänglig i leverantörsreskontra.                         | Förskottsbetalning är tillgänglig i leverantörsreskontra och kundreskontra.    |

## <a name="overview-of-the-prepayment-process"></a>Översikt över förskottsbetalningsprocessen
Redovisningspraxis i många länder/regioner kräver att förskottsbetalningar från en kund eller till en leverantör inte bokförs på de vanliga samlingskontona för den kunden eller leverantören. Istället ska dessa förskottsbetalningar bokföras på särskilda redovisningskonton för förskottsbetalningar. När en försäljnings- eller inköpsorder görs, utfärdas en faktura till kunden eller från leverantören. Under betalningen av fakturan återförs förskottsbetalningen och momsen på denna förskottsbetalningsverifikation, och fakturabeloppen bokförs automatiskt på de vanliga samlingskontona. Gör så här om du vill skapa en förskottsbetalning.

1.  Ställ in bokföringsprofiler för förskottsbetalning.
2.  I Parametrar för kundreskontra och Parametrar för leverantörsreskontra, under **Redovisning och moms**, väljer du den nya bokföringsprofilen genom parametern **Bokföringsprofil för betalningsjournal vid förskottsbetalning**.
3.  Skapa en betalningsjournal och sedan den nya betalningen.
4.  Du kan flagga betalningen som en förskottsbetalning. Om en betalning flaggas som en förskottsbetalning, bokförs betalningen till de konton som definieras i den bokföringsprofil som du konfigurerade i steg 1 och 2. Dessutom beräknas momsen om betalningen markeras som en förskottsbetalning. Vissa myndigheter kräver att momsen betalas när en förskottsbetalning registreras, även om det inte finns någon faktura.
5.  Bokför förskottsbetalningen.
6.  Valfritt: Du kan kvitta förskottsbetalningen mot försäljningsordern eller inköpsordern innan du skapar en faktura. På sidan för försäljnings- eller inköpsordern använder du **Kvitta transaktioner** i åtgärdsfönstret.
7.  Registrera fakturan, efter att leverantören har levererat varorna eller tjänsterna. Om du kvittade förskottsbetalningen mot inköpsordern eller försäljningordern i steg 6, kvittas förskottsbetalningen automatiskt mot fakturan som du själv har skapat. Om du inte kvittade förskottsbetalningen mot försäljnings- eller inköpsordern kan du manuellt kvitta den mot fakturan genom att använda **Kvitta transaktioner** på sidan för kunden eller leverantören. Förskottsbetalningbeloppet återförs sedan ut ur det tillfälliga AP/AR-redovisningskontot. Dessutom, om moms beräknade återförs den eftersom fakturan har den verkliga momsen.

## <a name="overview-of-the-prepayment-invoicing-process"></a>Översikt över förskottsfaktureringsprocessen
Förskottsfakturor är en vanlig affärspraxis. En leverantör utfärdar förskottsfakturor för att begära en deposition för inköpet innan inköpsordern är uppfylld. En del leverantörer kan till exempel kräva en förskottsbetalning för anpassade varor eller tjänster. Om en leverantör utfärdar en faktura som begär förskottsbetalning, kan du använda funktionen förskottsbetalningsfakturering. Ett förskottsbetalningsvärde kan definieras på inköpsordern, en förskottsfaktura registreras och betalas, varefter förskottsfakturan implementeras på den senaste fakturan. Gör så här om du vill skapa en förskottsbetalning.

1.  Inköpsagenten skapar, bekräftar och skickar sedan in en inköpsorder som leverantören har begärt förskottsbetalningen för. Förskottsbetalningvärdet definieras på inköpsordern som en del i avtalet.
2.  Leverantören skickar in en förskottsfaktura.
3.  Leverantörsreskontrakoordinatorn registrerar förskottsfakturan mot inköpsorder, och sedan betalas förskottsfakturan.
4.  Leverantören skickar en begäran om betalning (som kallas standardleverantörsfaktura). När leverantören har levererat varorna eller tjänsterna, och de relaterade standard leverantörsfakturorna har kommit, använder leverantörsreskontrakoordinatorn förskottsbetalningsbeloppet som redan har betalats mot standardfakturan.
5.  Leverantörsreskontrakoordinatorn betalar och kvittar det resterande beloppet på standardfakturan.

## <a name="set-up-parameters-to-enable-the-prepayment-invoicing-process"></a>Ställ in parametrar för att aktivera faktureringsprocessen för förskottsbetalningen
Ett förskottsbetalningskonto måste definieras på fliken **Inköpsorder** på sidan **Lagerbokföring** (**Lagerhantering \> Inställningar \> Bokföring \> Bokföring**). Förskottsbetalningskontot uppdateras, vanligtvis debiteras, när förskottsbetalningsfakturan bokförs. Saldot på förskottsbetalningskontot återförs när standardfakturan som används på förskottsbetalningsfakturan bokförs. Om du inte kvittar förskottsbetalningsfakturan mot en betalning innan du tillämpar förskottsbetalningsfakturan på standardfakturan, kommer redovisningsposterna från den bokförda förskottsbetalningsfakturan att återföras när standardfakturan bokförs.

Motbokning av sammanfattning konto för kundreskontra definieras i profilen för **leverantörsbokföring**. Klicka på för att definiera standardinläggsprofilen **Leverantörsreskontra \>Inställningar \> Parametrar för leverantörsreskontra \>fliken Redovisning och moms \> Bokföringsprofil med leverantörsfaktura för förskottsbetalning**.

**Policy för förskottsansökan** anger om systemet automatiskt kommer att tillämpa avvecklade förskottsfakturor på den slutliga fakturan som skapades manuellt. Fakturor som skapas med hjälp av en dataenhet refererar inte till **programpolicyn för förskottsbetalning**. Du måste använda kvittade förskottsbetalningsfakturor manuellt på fakturor som har skapats med en dataenhet. Om du vill definiera policyn går du till **Leverantörsreskontra \>Inställningar \> Parametrar för leverantörsreskontra \> fliken Redovisning och moms \> Programpolicyn för förskottsbetalning**. Om fältet **Programpolicyn för förskottsbetalning** anges till **Automatisk**, förskottsfakturan markeras automatiskt för avräkning med den slutliga fakturan. Om fältet är inställt på **Meddelande** visas en visuell indikation av att en förskottsbetalningsfaktura är tillgänglig för användning när den slutgiltiga fakturan skapas.

## <a name="create-a-purchase-order-that-contains-prepayment-invoice-information"></a>Skapa en inköpsorder som innehåller information om förskottsbetalningsfaktura
När en leverantör säger att han eller hon behöver förskottsbetalning av varor och tjänster som finns på en inköpsorder, måste du definiera förskottsbetalningsvärdet för den associerade inköpsordern. Gå till **Leverantörsreskontra \> Vanliga \> Inköpsorder \> Alla inköpsorder** och hitta leverantörens inköpsorder. I åtgärdsfönstret, välj fliken **Inköp** och välj sedan **Förskottsbetalningar**. Ange information för förskottsfakturan, inklusive en beskrivning, värdet på förskottet, om förskottet är ett fast belopp eller en procentsats och ett förskottskategori-ID. 

Observera att flera förskottsbetalningsdefinitioner på en inköpsorder inte är tillåtna. Om du behöver tillåta flera förskottsbetalningar på en inköpsorder bokför du betalningarna med hjälp av betalningsjournalen istället för en förskottsbetalningsfaktura.

Förskottsbetalningen kan tas bort från inköpsordern om du inte redan har kvittat en betalning mot den bokförda förskottsbetalningsfakturan eller bokfört standardfakturan. Välj om du vill ta bort information om förskottsbetalning från inköpsordern **Leverantörsreskontra \> Vanliga \> Purchase orders \> Alla inköpsorder** och hitta leverantörens inköpsorder. I åtgärdsfönstret, välj fliken **Inköp** och välj sedan **Ta bort betalningar**.

## <a name="create-and-post-a-prepayment-invoice"></a>Skapa och bokföra en förskottsfaktura
Om du vill registrera leverantörens förskottsbetalningsfaktura går du till sidan **Leverantörsfaktura** genom att välja alternativet **Förskottsbetalningsfaktura** på sidan **Inköpsorder** (**Leverantörsreskontra \> Vanliga \> Inköpsorder \> Alla inköpsorder \> fliken Faktura \> Förskottsbetalningsfaktura**). Ange information om förskottsfakturan, bland annat fakturanumret. Du kan inte ändra kvantiteter för en förskottsfaktura. Om leverantören har fakturerat ett delbelopp av förskottsbetalningsvärdet som har definierats på inköpsordern kan du uppdatera enhetspriset så att det återspeglar delvärdet.

När förskottsfakturan bokförs kommer leverantörsbalansen och förskottskontot att uppdateras. Värde **förskottsbetalningsprogram** på förskottsdefinitionen i inköpsordern kommer också att uppdateras. De ekonomiska standarddimensionsposterna för den bokförda förskottsbetalningsverifikationen tas från huvudinformationen på inköpsordern.

## <a name="post-and-settle-payments-for-the-prepayment-invoice"></a>Bokföra och kvitta betalningar för förskottsbetalningsfakturan
Fakturan förskottsbetalningen betalas sedan från sidan **Betalningsjournal**. Om du vill öppna betalningsjournaler klickar du på **Leverantörsreskontra \> Journaler \> Betalningar \> Betalningsjournal**. Efter att betalningen har betalats till förskottsfakturan, inköpsorderns värde **Återstående ansökning om förskottsbetalning** kommer att uppdateras.

Innan du bokför standardfakturan för förskottsbetalningsfakturan kan du återföra kvittningen av betalningen från förskottsbetalningsfakturan. Efter att en standardfaktura tillämpats på förskottsfakturan kan betalningsavräkningen dock inte återföras från förskottsfakturan.

## <a name="post-the-standard-vendor-invoice-for-the-purchase-order-and-apply-the-prepayment-invoice-to-the-standard-invoice"></a>Bokför standardleverantörsfakturan för inköpsordern och använd förskottsbetalningsfakturan på standardfakturan
Registrera standardfakturan som du får från leverantören. Som en del av den här processen kan du tillämpa den kvittade förskottsbetalningsfakturan på leverantörsfakturan så att värdet på fakturan reduceras med beloppet som redan har betalats. Om du använder förskottsbetalningsfakturan på leverantörsfakturan kommer redovisningsposter från förskottsbetalningsfakturan att återföras.

## <a name="application-of-the-prepayment-invoice-after-posting-the-standard-invoice"></a>Tillämpning av förskottsbetalningsfaktura efter bokföring av standardfakturan
Om du glömmer att tillämpa förskottsbetalningen på standardleverantörsfakturan vid bokningstillfället för leverantörsfakturan kommer den avräknade förskottsbetalningen att vara tillgänglig för andra fakturor från denna leverantör från sidan **Leverantör** (**Leverantörsreskontra \> Vanliga \> Leverantörer \> Alla leverantörer \> fliken Faktura \> Använd**).

## <a name="reversal-of-the-prepayment-application-process"></a>Återföring av ansökningsprocessen för förskottsbetalning
Om du behöver avaktivera eller omvända tillämpningen av en förskottsfaktura från en standardfaktura väljer du åtgärden **Återför** från sidan **Leverantörer** (**Leverantörsreskontra \> Vanliga \> Leverantörer \> Alla leverantörer \> fliken Faktura \> Återför**). När förskottsbetalningsansökan har återförts kan du använda förskottsbetalningen på en annan standardfaktura. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
