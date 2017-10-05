---
title: "Startsida för Leverantörsreskontra"
description: "Det här ämnet ger en översikt över leverantörsreskontra."
author: twheeloc
manager: AnnBe
ms.date: 08/18/2017
ms.topic: index-page
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 21901
ms.assetid: 1e4c2ac4-077b-4678-8733-5cec8f6ff659
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 741166608de504512cc0ad48cb7cd4b2d50b6c80
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="accounts-payable-home-page"></a>Startsida för Leverantörsreskontra

[!include[banner](../includes/banner.md)]


Det här ämnet ger en översikt över leverantörsreskontra. 

Det går att registrera leverantörsfakturor manuellt eller ta emot dem elektroniskt genom en datatabell. När fakturorna har angetts eller tagits emot går det att granska och godkänna dem med en fakturagodkännandejournal eller sidan **Leverantörsfaktura**. Det går att använda fakturamatchning, leverantörsfakturapolicyer och arbetsflöden för att automatisera granskningen, så att fakturor som uppfyller vissa villkor godkänns automatiskt och de återstående fakturorna flaggas för granskning av en auktoriserad användare.

**Affärsprocesser**

[![Affärsprocess](./media/AP-process.PNG)](./media/AP-process.PNG)

## <a name="set-up-accounts-payable"></a>Ställa in leverantörsreskontra

Ställa in leverantörsgrupper, leverantörer, bokföringsprofiler, olika betalningsalternativ och parametrar angående leverantörer, avgifter, leveranser och destinationer, skuldsedlar och andra typer av leverantörsreskontrainformation. 

[Konfigurera leverantörsreskontra](accounts-payable-overview.md)

[Redovisningsfördelningar och poster i reskontrajournal för leverantörsfakturor](accounting-distributions-subledger-journal-entries-vendor-invoices.md) 

[Omräkning i utländsk valuta för Leverantörsreskontra och Kundreskontra](../cash-bank-management/foreign-currency-revaluation-accounts-payable-accounts-receivable.md)

## <a name="configure-vendor-invoices"></a>Konfigurera leverantörsfakturor

Använd Leverantörsreskontra för att spåra fakturor och utgående utgifter till leverantörer.

[Fakturamatchning för leverantörsreskontra](accounts-payable-invoice-matching.md)

[Bokföringsprofiler för leverantörer](vendor-posting-profiles.md)

[Konfigurera validering av fakturamatchning för leverantörsreskontra](tasks/set-up-accounts-payable-invoice-matching-validation.md)

[Trevägsmatchningspolicyer](three-way-matching-policies.md)

[Fakturamatchning och koncerninterna inköpsorder](invoice-matching-intercompany-purchase-orders.md)

[Åtgärda avvikelser under matchning av fakturasummor](resolve-invoice-totals-invoice-matching-discrepancies.md)

[Standardmotkonton för leverantörsfakturajournaler och fakturagodkännandejournaler](default-offset-accounts-vendor-invoice-journals.md)

[Mobila fakturagodkännanden](mobile-invoice-approvals.md)

[Arbetsyta för leverantörssamarbetesfakturering](vendor-portal-invoicing-workspace.md)

[Automation av leverantörsfaktura](vendor-invoice-automation.md)

## <a name="configure-vendor-payments"></a>Konfigurera leverantörsbetalningar 

Tilldela en systemdefinierad betalningstyp, till exempel check, elektronisk betalning eller skuldsedel, till en användardefinierad betalningsmetod. Betalningstyper är valfria, men de är användbara när du validerar elektroniska betalningar och snabbt vill kunna fastställa vilken betalningstyp som en betalning använder. 

[Arbetsyta för leverantörsbetalningar](vendor-payments-workspace.md)

[Definiera leverantörsbetalningsavgifter](tasks/define-vendor-payment-fees.md)

[Definiera villkor för leverantörsbetalning](tasks/define-vendor-payment-terms.md)

[Betalningskontrollöversikt](positive-pay-overview.md)

[Ställa in och generera betalningskontrollfiler](set-up-generate-positive-pay-files.md)

[Skapa leverantörsbetalningar med ett betalningsförslag](create-vendor-payments-payment-proposal.md)

[Leverantörsbetalningar för ett delbelopp](vendor-payments-partial-amount.md)

[Ta en rabatt som är högre än den beräknade rabatten för en leverantörsbetalning](take-discount-more-calculated-discount-vendor-payment.md)

[Ta en kassarabatt utanför kassarabattperioden](take-cash-discount-outside-cash-discount-timeframe.md)

[Elektronisk rapportering för leverantörscheckar](electronic-reporting-sample-vendor-checks.md)

[Återför en leverantörsbetalning](reverse-vendor-payment.md)

[Översikt över förskottsfakturor och förskottsbetalningar](prepayments-invoices-vs-prepayments.md)

[Centraliserade leverantörsreskontrabetalningar](centralized-payments-accounts-payable.md)

## <a name="settlements"></a>Kvittningar

I följande avsnitt finns information om kvittningar. Kvittning är en process där betalningar kvittas mot fakturor. 

[Konfigurera kvittning](../cash-bank-management/configure-settlement.md)

[Kvitta en leverantörsdelbetalning före rabattdatumet](settle-partial-vendor-payment-before-discount-or-final-payment-after.md)

[Kvitta en leverantörsdelbetalning som har rabatter på leverantörskreditfakturor](settle-partial-vendor-payment-discounts-vendor-credit-notes.md)

[Kvitta en leverantörsdelbetalning som har flera rabattperioder](settle-partial-vendor-payment-multiple-discount-periods.md)

[Kvitta en leverantörsdelbetalning eller slutlig betalning före rabatt](settle-partial-vendor-payment-or-final-payment-before-discount.md)

[En verifikation med flera kund- eller leverantörsposter](single-voucher-multiple-customer-vendor-records.md)



### <a name="additional-resources"></a>Ytterligare resurser

#### <a name="whats-new-and-in-development"></a>Vad är nytt och under utveckling

Öppna [översikten till Microsoft Dynamics 365](https://roadmap.dynamics.com/) för att visa vilka nya funktioner som har lanserats och nya funktioner under utveckling. 

#### <a name="blogs"></a>Bloggar

Det finns åsikter, nyheter och annan information om leverantörsreskontra och andra lösningar i [bloggen Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise).

Det finns många inlägg om leverantörsreskontra i [Microsoft Dynamics AX produktteamblogg](https://blogs.msdn.microsoft.com/dax/). En del av inläggen skrevs för den föregående versionen av leverantörsreskontra, men samma begrepp gäller fortfarande och procedurerna är liknande i den aktuella versionen.

I [bloggen Microsoft Dynamics Operations Partner Community](https://community.dynamics.com/partner/b/operationspartnercommunityblog) får Microsoft Dynamics Partners en resurs där de kan få mer information om vad som är nytt och trendar i MBS Operations.

#### <a name="task-guides"></a>Uppgiftsguider
Mer hjälp är tillgänglig som uppgiftsguider i Finance and Operations. Klicka på knappen Hjälp på valfri sida för att få åtkomst till uppgiftsguiderna.

#### <a name="videos"></a>Videoklipp

Ta en titt på instruktionsfilmerna som finns på [YouTube-kanalen för Microsoft Dynamics 365](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).





