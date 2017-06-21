---
title: "Förskottsfakturor kontra förskottsbetalningar"
description: "Den här artikeln beskriver och kontrasterar de två metoderna som organisationer kan använda för förskottsbetalningar. I den ena metoden måste du skapa en förskottsfaktura som är kopplad till en inköpsorder. I den andra metoden skapar du verifikationer för förskottsbetalningsjournal genom att skapa journalposter och välja dem som verifikationer för förskottsbetalningsjournal."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, PurchTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15871
ms.assetid: a0bb5220-73d4-48ae-84d0-46a171c224fa
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c4f127007cea1d8ccd0b4e9ea637f0674775278d
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="prepayment-invoices-vs-prepayments"></a>Förskottsfakturor kontra förskottsbetalningar

[!include[banner](../includes/banner.md)]


Den här artikeln beskriver och kontrasterar de två metoderna som organisationer kan använda för förskottsbetalningar. I den ena metoden måste du skapa en förskottsfaktura som är kopplad till en inköpsorder. I den andra metoden skapar du verifikationer för förskottsbetalningsjournal genom att skapa journalposter och välja dem som verifikationer för förskottsbetalningsjournal.

Organisationer kan utfärda förskottsbetalningar till leverantörer för varor och tjänster, innan dessa varor eller tjänster är uppfyllda. Två metoder kan användas för att utfärda förskottsbetalningar till leverantörer. För att minimera risk kan du följa förskottsbetalningar, genom att definiera förskottsbetalningen i en inköpsorder. För den här metoden måste du skapa en förskottsfaktura som är kopplad till en inköpsorder. Denna metod kallas för förskottsbetalningsfakturering. Organisationer som inte vill följa förskottsbetalningar lika nära eller inte får en förskottsfaktura från deras leverantör, kan använda verifikationer för förskottsbetalningsjournal i stället för metoden förskottsbetalningsfakturering. Du kan skapa verifikationer för förskottsbetalningsjournal, genom att skapa journalposter och välja dem som verifikationer för förskottsbetalningsjournal. För den här metoden kan du inte följa vilka förskottsbetalningar till en leverantör som görs mot inköpsorder. Du kan dock välja en bokförd förskottsbetalning för kvittning mot en inköpsorder.

## <a name="when-to-use-prepayment-invoicing-vs-prepayments"></a>När ska du använda förskottsbetalningsfakturering kontra förskottsbetalningar.
| Förskottsfaktura                                                                | Förskottsbetalningar                                                              |
|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| Definiera förskottsbetalningsvärde på inköpsordern.                                    | Inget förskottsbetalningsvärde är definierat på inköpsordern.                    |
| Nyckel: En förskottsfaktura och en slutfaktura måste bokföras.                       | Ingen förskottsfaktura måste bokföras.                                    |
| Skulder för förskottsbetalningen hålls på kontot för förskottsbetalning, inte AP-kontot. | Skulder för förskottsbetalningen hålls på AP-kontot.                  |
| Leverantörssaldot återspeglar inte förskottsbetalningvärdet genom hela processen.     | Leverantörssaldot återspeglar förskottsbetalningvärdet genom hela processen. |
| Förskottsbetalningsfakturering är tillgänglig i leverantörsreskontra.                         | Förskottsbetalning är tillgänglig i leverantörsreskontra och kundreskontra.    |

## <a name="overview-of-the-prepayment-process"></a>Översikt över förskottsbetalningsprocessen
Redovisningsseden i många länder/regioner kräver att förskottsbetalningar från en kund eller till en leverantör inte ska bokföras på de vanliga samlingskontona för den kunden eller leverantören. Istället ska dessa förskottsbetalningar bokföras på särskilda redovisningskonton för förskottsbetalningar. När en försäljnings- eller inköpsorder görs, utfärdas en faktura till kunden eller från leverantören. Under betalningen av fakturan återförs förskottsbetalningen och momsen på denna förskottsbetalningsverifikation, och fakturabeloppen bokförs automatiskt på de vanliga samlingskontona. Gör så här om du vill skapa en förskottsbetalning.

1.  Ställ in bokföringsprofiler för förskottsbetalning.
2.  I Parametrar för kundreskontra och Parametrar för leverantörsreskontra, under **Redovisning och moms**, väljer du den nya bokföringsprofilen genom parametern **Bokföringsprofil för betalningsjournal vid förskottsbetalning**.
3.  Skapa en betalningsjournal och skapa sedan den nya betalningen.
4.  Du kan flagga betalningen som en förskottsbetalning. Om en betalning flaggas som en förskottsbetalning, bokförs betalningen till kontona som definieras på bokföringsprofilen, som du ställde in i steg 1 och 2. Dessutom beräknas momsen om betalningen markeras som en förskottsbetalning. Alla myndigheter kräver att momsen betalas, när en förskottsbetalning registreras, även om det inte finns en faktura.
5.  Bokför förskottsbetalningen.
6.  Valfritt: Du kan kvitta förskottsbetalningen mot försäljningsordern eller inköpsordern innan du skapar en faktura. På sidan för försäljningsordern eller inköpsordern, i åtgärdsfönstret, använd **Kvitta transaktioner**.
7.  Registrera fakturan, efter att leverantören har levererat varorna eller tjänsterna. Om du kvittade förskottsbetalningen mot inköpsordern eller försäljningordern i steg 6, kvittas förskottsbetalningen automatiskt mot fakturan som du själv har skapat. Om du inte kvittade förskottsbetalningen mot försäljningsordern eller inköpsordern, kan du manuellt kvitta den mot fakturan, genom att **Kvitta transaktioner** på sidan för kunden eller leverantören. Förskottsbetalningbeloppet återförs sedan ut ur det tillfälliga AP/AR-redovisningskontot. Dessutom, om moms beräknade återförs den eftersom fakturan har den verkliga momsen.

## <a name="overview-of-the-prepayment-invoicing-process"></a>Översikt över förskottsfaktureringsprocessen
Förskottsfakturor är en vanlig företagspraxis. En leverantör utfärdar förskottsfakturor för att begära en deposition för inköpet innan inköpsordern är uppfylld. En del leverantörer kan till exempel kräva en förskottsbetalning för anpassade varor eller tjänster. Om en leverantör utfärdar en faktura som begär förskottsbetalning, kan du använda funktionen förskottsbetalningsfakturering. Ett förskottsbetalningsvärde kan definieras på inköpsordern, en förskottsfaktura registreras och betalas, och sedan tillämpas förskottsfakturan till den senaste fakturan. Gör så här om du vill skapa en förskottsbetalning.

1.  Inköpsagenten skapar, bekräftar och skickar sedan in en inköpsorder som leverantören har begärt förskottsbetalningen för. Förskottsbetalningvärdet definieras på inköpsordern som en del i avtalet.
2.  Leverantören skickar in en förskottsfaktura.
3.  Leverantörsreskontrakoordinatorn registrerar förskottsfakturan mot inköpsorder, och sedan betalas förskottsfakturan.
4.  När leverantören har levererat varorna eller tjänsterna, och de relaterade leverantörsfakturorna har kommit, använder leverantörsreskontrakoordinatorn förskottsbetalningsbeloppet som redan har betalats mot fakturan.
5.  Leverantörsreskontrakoordinatorn betalar och kvittar det resterande beloppet på fakturan.





