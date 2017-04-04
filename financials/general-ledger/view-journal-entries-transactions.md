---
title: Visa journalposter och transaktioner
description: "Det här avsnittet innehåller information om de olika sätten att visa journalposter och transaktioner."
author: RobinARH
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerTransVoucher
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13031
ms.assetid: 281c7ea6-4dfd-4d1f-994f-c361ee299dbe
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: a6848ea9c05536ac18a038b1864c9ccb9408964c
ms.lasthandoff: 03/31/2017


---

# <a name="view-journal-entries-and-transactions"></a>Visa journalposter och transaktioner

Det här avsnittet innehåller information om de olika sätten att visa journalposter och transaktioner. 

Användare som vill visa journaler och transaktioner kan göra det på flera sätt. De kan använda förfrågningssidor som innehåller vidaresökningsmöjligheter eller också kan de använda olika rapportalternativ i redovisningen.

## <a name="voucher-transactions"></a>Verifikationstransaktioner
**Verifikationstransaktioner** är en förfrågningssida där du kan välja bland olika register och fält för att ange villkor för saldot eller transaktionen som du söker efter. Du kan till exempel visa alla transaktioner för ett visst datum eller konto eller alla transaktioner av typen **Pågående** som är i ett visst bokföringsskikt. Som standard visar sidan journalnumret, verifikationen, datumet och huvudkontot, men du kan lägga till ytterligare register, fält och kriterier för att begränsa sökningen.

## <a name="audit-trail"></a>Redovisningsspårning
**Redovisningsspårning** är en förfrågningssida som visar transaktionstyperna, beskrivningarna, vem som skapade transaktionerna och när de skapades. Från sidan **Redovisningsspårning** kan du visa verifikationstransaktionerna.

## <a name="financial-reports"></a>Ekonomiska rapporter
Du kan även undersöka och analysera redovisningstransaktioner genom att köra ekonomiska rapporter. Eftersom designen av ekonomiska kan baseras på konton, dimensioner, kontokategorier eller en kombination av dessa tre, kan du visa transaktioner genom att söka vidare på olika sätt. Om du behöver mer information för redovisningstransaktioner, kan du också inkludera flera transaktionsegenskaper i rapportdesignen. Dessutom kan du om du vill visa transaktionerna som utgör ett redovisningssaldo kan du söka nedåt till kontotransaktioner, på samma sätt som du kan från sidan **Råbalans**.

## <a name="ledger-reports"></a>Redovisningsrapporter
Förutom ekonomiska rapporter kan du använda följande redovisningsrapporter om du vill visa redovisningstransaktioner:

-   **Dimensionsutdrag** – Den här rapporten visar transaktioner per dag och konto, och det finns också alternativ för att kunna visa transaktioner per dimension och period.
-   **Redovisningstransaktionslista** – Den här rapporten visar transaktioner i transaktionsvalutan, redovisningsvalutan och rapporteringsvalutan på ett konto.
-   **Skriv ut journalen** – den här rapporten visas resultatet av en bokförd journal. Du kan köra rapporten efter Journalbatchnummer eller journaltyp eller lägga till ytterligare fält.
-   **Bokförda transaktioner per journal** – I rapporten visas transaktionerna som har bokförts i en journal grupperade efter verifikation.
-   **Transaktionslista efter datum** – Den här rapporten visar alla transaktioner per datum, tillsammans med journalnummer, verifikation och redovisningskonto. Den visar också transaktionerna i transaktionsvalutan, kontovalutan och rapporteringsvalutan.
-   **Transaktionsursprung** – Den här transaktionsrapporten visar konto efter journal och efter transaktionsvalutan, kontovalutan och rapporteringsvalutan. Den visar också varje rad i journalen som användes som avräkning.


Mer information finns [redovisningskontosaldon](general-ledger-account-balances.md), [redovisning Utforskaren för datakällor](\financials\accounts-payable\accounting-source-explorer) och [ekonomisk rapportering](financial-reporting-getting-started.md)


