---
title: Visa journalposter och transaktioner
description: Det här avsnittet innehåller information om de olika sätten att visa journalposter och transaktioner.
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.custom: 13031
ms.assetid: 281c7ea6-4dfd-4d1f-994f-c361ee299dbe
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b8ae038001e799666907fd1ba7bec09765785f45
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4978471"
---
# <a name="view-journal-entries-and-transactions"></a>Visa journalposter och transaktioner

[!include [banner](../includes/banner.md)]

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
-   **Skriv ut journalen** – den här rapporten visar resultatet av en bokförd journal. Du kan köra rapporten efter journalbatchnummer eller journaltyp eller lägga till ytterligare fält.
-   **Bokförda transaktioner per journal** – I rapporten visas transaktionerna som har bokförts i en journal grupperade efter verifikation.
-   **Transaktionslista efter datum** – Den här rapporten visar alla transaktioner per datum, tillsammans med journalnummer, verifikation och redovisningskonto. Den visar också transaktionerna i transaktionsvalutan, kontovalutan och rapporteringsvalutan.
-   **Transaktionsursprung** – Den här transaktionsrapporten visar konto efter journal och efter transaktionsvalutan, kontovalutan och rapporteringsvalutan. Den visar också varje rad i journalen som användes som avräkning.


## <a name="additional-resources"></a>Ytterligare resurser
- [Balanser på huvudbokskonto](general-ledger-account-balances.md) 
- [Utforskare för redovisningskälla](../accounts-payable/accounting-source-explorer.md)
- [Översikt över ekonomisk rapportering](financial-reporting-getting-started.md)
- [Visa poster eller transaktioner i redovisningsjournal](tasks/view-journal-entries-or-transactions.md)



