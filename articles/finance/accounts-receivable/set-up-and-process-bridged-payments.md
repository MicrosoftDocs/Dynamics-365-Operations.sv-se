---
title: Ställa in och behandla interimsbetalningar
description: I den här artikeln beskrivs hur du ställer in och behandla till interimsbetalningar. En interimsbetalning är en betalning som bokförs i redovisningen i två steg.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode, VendPaymMode, LedgerJournalTable, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, LedgerJournalTransDaily
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f0609e333fb16ba189b6a971f88fbb5bf900fec
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887989"
---
# <a name="set-up-and-process-bridged-payments"></a>Ställ in och behandla interimsbetalningar

[!include [banner](../includes/banner.md)]

En interimsbetalning är en betalning som bokförs i redovisningen i två steg. Den här metoden används vanligtvis när betalningsmetoden är inställd på **Bank** och du bara måste bokföra transaktioner på bankkontot om transaktionen har raderat banken. Du kan dock även använda det för ett redovisningskonto. I det här fallet flyttar systemet beloppet från ett huvudkonto till ett annat när interimsbokning bearbetas.

Du kan skapa interimsbetalningar från leverantörsreskontra eller kundreskontra. Även om den här artikeln förklarar hur du konfigurerar interimsbokföring för kundreskontra, är stegen för leverantörsreskontratransaktioner liknande.

## <a name="set-up-bridging-posting"></a>Konfigurera interimsbokning

Om du vill använda bokföring av interimsbokföring måste du ställa in en eller flera betalningsmetoder så att de använder bokföringsmetoden **Interimsbokning**. Du måste sedan välja ett interimskonto.

1. Gå till **Kundreskontra &gt; Betalningsinställning &gt; Betalningsmetoder**.
2. Välj en befintlig betalningsmetod om du vill aktivera interimsbokning. Du kan också skapa en ny betalningsmetod.
3. Markera kryssrutan **Interimsbokning**.
4. I fältet **Interimskonto** väljer du det huvudkonto som betalningar ska bokföras på innan de rensas till bankkontot.
5. Stäng sidan.

## <a name="process-and-transfer-bridging-posting"></a>Bearbeta och överföra interimsbokningen

Följ dessa steg för att skapa och bearbeta interimsbokning.

1. Gå till **kundreskontra &gt; Betalningar &gt; Kundbetalningsjournal**.
2. Välj **Ny** för att skapa en journal.
3. Ange sedan ett namn i fältet **Namn**.
4. Lägg till rader i kundbetalningsjournalen och välj den betalningsmetod som har konfigurerats för interimsbokningen.
5. Bokför journalen. Transaktionerna kommer att bokföras på huvudkontot som du valde i fältet **Interimskonto** i föregående procedur.

När transaktionerna har rensat banken och du vill överföra betalningen från interimskontot till det betalkonto som är specificerat för betalningssättet, följ dessa steg.

1. Gå till **Redovisning &gt; Journalposter &gt; Allmänna journaler**.
2. Välj **Ny** för att skapa en journal.
3. Ange sedan ett namn i fältet **Namn**.
4. Välj **Rader** för att öppna journaldetaljerna.
5. Välj **Funktioner &gt; Välj relevant interimstransaktion**.
6. Markera varje betalning som har raderats och välj sedan **Godta**.
7. Bokför journalen.
