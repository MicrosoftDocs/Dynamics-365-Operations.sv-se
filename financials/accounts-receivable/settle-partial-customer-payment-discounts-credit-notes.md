---
title: "Kvitta en delvis kundbetalning med rabatter på kreditfakturor"
description: "Den här artikeln går igenom ett scenario där en kassarabatt utnyttjas för en kreditfaktura när den ursprungliga fakturan också hade en kassarabatt."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14564
ms.assetid: d9984cef-ddcf-46bd-816d-c01b8cc5cf48
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: e43bcea67d9c408c93258f9b64565560b59fbb88
ms.lasthandoff: 03/31/2017


---

# <a name="settle-a-partial-customer-payment-that-has-discounts-on-credit-notes"></a>Kvitta en delvis kundbetalning med rabatter på kreditfakturor

Den här artikeln går igenom ett scenario där en kassarabatt utnyttjas för en kreditfaktura när den ursprungliga fakturan också hade en kassarabatt. 

Fabrikam låter kunderna få kassarabatter på delbetalningar och även på kreditfakturor (kreditnotor). En kassarabatt kan utnyttjas för en kreditfaktura, när kreditfakturan ställs ut för en faktura som kunden har en kassarabatt på. Istället för att ange en kredit för hela beloppet kan du kreditera kundens saldo för ett belopp exklusive kassarabattprocenten som kunden har. Kvittning parametrar finns i den **parametrar för kundreskontra** sida.

## <a name="invoice-and-credit-note"></a>Faktura och kreditfaktura
Kund 4035 har en faktura på 1 000,00 och en kreditfaktura på 100,00. Alla dokument har 1 procents rabatt om de betalas inom 14 dagar. Arnie kan visa den här informationen på sidan **Kundtransaktioner**.

| Verifikation    | transaktionstyp | Datum      | Faktura  | Debetbelopp i transaktionsvaluta | Kreditbelopp i transaktionsvaluta | Saldo  | Valuta |
|------------|------------------|-----------|----------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10050  | Faktura          | 2015/06/28 | 10050    | 1 000,00                             |                                       | 1 000,00 | USD      |
| CCRN-10050 | Kreditfaktura      | 2015/06/28 | CR-10050 |                                      | 100,00                                | -100,00  | USD      |

## <a name="settle-a-credit-note-with-an-invoice"></a>Kvitta en kreditfaktura med en faktura
Från sidan **Kundtransaktioner** öppnar Arnie sidan **Kvitta transaktioner**. Han kan använda sidan **Kvitta transaktioner** för att kvitta både kreditnotan och fakturan. Som en del av kvittningsprocessen visar han kassarabattdatum och belopp. Han väljer de två dokumenten och klickar på **Bokför** för att kvitta transaktionerna. Det finns en rabatt på -1,00 på kreditfakturan eftersom Fabrikam tillåter rabatter på kreditfakturor.

| Markera     | Använd kassarabatt | Verifikation    | Konto | Datum      | Förfallodatum  | Faktura  | Belopp i transaktionsvalutan | Valuta | Belopp att kvitta |
|----------|-------------------|------------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| Markerad | Normal            | FTI-10050  | 4035    | 2015/06/28 | 2015/07/28 | 10050    | 1 000,00                       | USD      | 990,00           |
| Markerad | Normal            | CCRN-10050 | 4035    | 2015/06/28 | 2015/07/28 | CR-10050 | -100,00                        | USD      | -99,00           |

Information om rabatten visas längst ned på sidan **Kvitta transaktioner**.

|                              |           |
|------------------------------|-----------|
| Kassarabattdatum           | 2015/07/12 |
| Kassarabattbelopp         | -1,00     |
| Använd kassarabatt            | Normal    |
| Utnyttjad kassarabatt          | 0,00      |
| Kassarabattbelopp att utnyttja | -1,00     |

Kvittningen blir 100,00 och ska inkludera en betalning på 99,00 och en rabatt på 1,00.

