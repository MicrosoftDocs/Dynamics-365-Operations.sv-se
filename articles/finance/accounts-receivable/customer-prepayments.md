---
title: Kundförbetalningar
description: I det här avsnittet beskrivs hur du ställer in och bearbetar förskottsbetalningar från kunder (även kallade kunddepositioner).
author: twheeloc
ms.date: 04/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, LedgerJournalTransCustPaym, CustParameters
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eb0f2290a38d89d90ac0d30a59e21fb3e9a6d894
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691903"
---
# <a name="customer-prepayments"></a>Kundförbetalningar

[!include [banner](../includes/banner.md)]

Kundens förskottsbetalningar används när du får en betalning från en kund, men det inte finns någon faktura som betalningen kan kvittas mot. Dessa typer av betalningar kallas också för kunddepositioner.

Processen för inställning och arbete med förskottsbetalningar från kunder består av följande grundläggande steg.

1. Skapa en bokföringsprofil för förskottsbetalningar.
2. Ställ in parametern **Bokföringsprofil vid verifikation för förskottsbetalningsjournal**.
3. Skapa en kundbetalningsjournal och markera kryssrutan **Verifikation för förskottsbetalningsjournal** på varje rad.
4. Bokför kundbetalningsjournalen.
5. När en faktura har genererats kvittar du förskottsbetalningen mot den genom att använda sidan **Kvitta öppna transaktioner**.

## <a name="create-a-customer-posting-profile-for-prepayments"></a>Skapa en bokföringsprofil för förskottsbetalningar

När du accepterar förskottsbetalningar eller insättningar från dina kunder innan varor eller tjänster levereras, eller innan det finns en faktura i systemet, vill du vanligtvis bokföra kontanter som en skuld i stället för en tillgång i kontoplanen. Kraven på att bokföra de här beloppen i redovisningen kan dock skilja sig åt, beroende på land eller region. Rådgör därför med dina revisorer om eventuella lokala regler som gäller.

I allmänhet är processen för att skapa en bokföringsprofil som kan användas för förskottsbetalningar densamma som processen för att skapa andra bokföringsprofiler. Den primära differensen är huvudkontot som du väljer i fältet **Sammanfattningskonto**. Mer information finns i [Bokföringsprofiler för kund](customer-posting-profiles.md).

## <a name="define-parameters-for-customer-prepayments"></a>Definiera parametrar för förskottsbetalningar från kunder

Det finns två huvudparametrar för kundreskontra som du måste ta hänsyn till när du konfigurerar systemet för förskottsbetalningar från kunder. Gör på följande sätt när du vill konfigurera parametrarna.

1. Gå till **Kundreskontra \> Inställningar \> Parametrar för kundreskontra**.
2. Valfritt: Under fliken **Redovisning och moms**, under fliken **Betalning**, ställer du in alternativet **Moms på verifikation för förskottsbetalningsjournal** på **Ja**.
3. I fältet **Bokföringsprofil vid verifikation för förskottsbetalningsjournal** väljer du den bokföringsprofils som ska användas när förskottsbetalningar från kunder bokförs.
4. Stäng sidan.

## <a name="create-customer-prepayment-vouchers"></a>Skapa verifikationer för förskottsbetalning från kund

När du skapar kundbetalningsjournalen måste du, för varje betalning, ställa in alternativet **verifikation för förskottsbetalningsjournal** på **Ja** på sidan **Kundbetalningsjournal**. Gör så här om du vill skapa en förskottsbetalning från kund.

1. Gå till **kundreskontra \> Betalningar \> Kundbetalningsjournal**.
2. Välj **Ny** för att skapa en journal.
3. I fältet **Nam** väljer du det journalnamn som ska användas.

    > [!IMPORTANT]
    > Om du ställde in alternativet **Moms på verifikation för förskottsbetalningsjournal** på **Ja** i föregående procedur, måste du välja ett journalnamn där parametern **Belopp inkluderar moms** har valts. 

4. Valfritt: I fältet **Beskrivning** anger du en detaljerad beskrivning.
5. Markera **rader**
6. Om det inte finns någon tom rad väljer du **Ny** för att skapa en rad.
7. I fältet **Datum** anger du det datum då förskottsbetalningen ska bokföras.
8. I fältet **Konto** väljer du kund för förskottsbetalning.
9. Valfritt: I fältet **Beskrivning** anger du en detaljerad beskrivning av transaktionen.
10. I fältet **Kredit** anger du beloppet på förskottsbetalningen.
11. I fältet **Motkonto** väljer du motkonto för betalningen. Välj till exempel det bank- eller huvudkonto som betalningen ska bokföras på.
12. I fältet **Betalningsmetod** väljer du kundens betalningsmetod.
13. Under fliken **Betalning** ställer du in alternativet **Verifikation för förskottsbetalningsjournal** på **Ja**.
14. Upprepa steg 7 till och med 13 för varje ytterligare förskottsbetalning som måste bokföras.
15. Välj **Bokför** för att slutföra journalen.

## <a name="settle-prepayments-with-invoices"></a>Kvitta förskottsbetalningar mot fakturor

Du kan använda arbetsytan **Kundbetalningar** för att enkelt hitta och kvitta betalningar som inte har kvittats helt.

1. På instrumentpanelen **Start** väljer du ikonen **Kundbetalningar**.
2. I avsnittet **Kundtransaktioner**, under fliken **Ej kvittade betalningar**, söker du efter och väljer betalningen som ska kvittas.
3. Välj **Kvitta transaktioner**.
4. Markera kryssrutan **Markera** för fakturan och betalningen som ska kvittas.
5. Vald **bokföring**

Mer information om hur du kvittar öppna transaktioner finns i [översikten över kvittningar](/dynamics365/finance/cash-bank-management/settlement-overview).
