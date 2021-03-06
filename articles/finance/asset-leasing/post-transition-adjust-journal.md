---
title: Bokföra journalposter för övergångsjustering i Leasing av tillgångar
description: I det här avsnittet beskrivs de funktioner som gör att du kan låta en leasingportfölj övergå till de nya redovisningsstandarderna för leasing, Accounting Standards Codification Topic 842 (ASC 842) och International Financial Reporting Standard 16 (IFRS 16).
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ea61a0d6e30695a2ef6b93529fcf3d21882c9cd2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819780"
---
# <a name="post-transition-adjustment-journal-entries-in-asset-leasing"></a>Bokföra journalposter för övergångsjustering i Leasing av tillgångar

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs de funktioner som gör att du kan låta en leasingportfölj övergå till de nya redovisningsstandarderna för leasing: Accounting Standards Codification Topic 842 (ASC 842), som är standarden för god redovisningssed i USA (US GAAP, Generally Accepted Accounting Principles), samt International Financial Reporting Standard 16 (IFRS 16).

Information om hur du konfigurerar en bok för övergången till de nya standarderna finns i [Konfigurera leasingböcker](set-up-lease-books.md).

När du skapar en journalpost för en övergångsjustering skapas en journalpost. Den här posten återspeglar balansräkningens inverkan på registreringen av leasingen enligt de nya standarderna på detta datum. Rätt tillgångskonto debiteras det bokförda värdet på detta datum och skuldkontot krediteras. Skillnaden debiteras eller krediteras balanserade vinstmedel.

Om du vill bokföra en övergångsjustering i enlighet med de nya redovisningsstandarderna följer du stegen nedan.

1. På sidan **Sammanfattning av leasing** väljer du leasingen och väljer sedan **Böcker**.
2. Välj **Betalningsplan** i boken.
3. I dialogrutan **Betalningsplan** väljer du **Bekräfta**. Stäng sedan dialogrutan.
4. Välj **Övergångsjustering**.

    > [!NOTE]
    > En övergångsjustering kan bara skapas för leasingböcker som har tilldelats till en bok där fältet **Övergångsbok** är tillgängligt. Om värdet i fältet **Leasingens start** är senare än övergångsdatumet, kommer värdet i fältet **Övergångsjustering** inte att uppdateras.

5. För att visa journalposten väljer du **Journaler för leasing av tillgångar**.
6. Välj den nya journalen och välj sedan **Bokför**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]