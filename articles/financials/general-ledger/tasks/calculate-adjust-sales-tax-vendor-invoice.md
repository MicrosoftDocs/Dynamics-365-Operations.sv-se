---
title: Beräkna och justera moms på en leverantörsfaktura
description: I det här avsnittet beskriver hur du justerar momsen på en leverantörsfaktura Dynamics 365 for Finance and Operations.
author: twheeloc
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 684529087d5348c9e02310f812f8aa6f64c6655f
ms.sourcegitcommit: 016832198c306e8329ad21b5254e7d1cdff74c2f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2019
ms.locfileid: "1862624"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a>Beräkna och justera moms på en leverantörsfaktura

[!include [task guide banner](../../includes/task-guide-banner.md)]

I det här avsnittet beskriver hur du justerar momsen på en leverantörsfaktura Dynamics 365 for Finance and Operations. Om det ursprungliga källdokumentet visar andra momsbelopp än dem som beräknas kan du justera dessa belopp, innan du bokför dem. I den här uppgiften används demonstrationsföretaget DEMF.

1. I navigeringsfönstret går du till **Moduler > Leverantörsreskontra > Fakturor > Fakturajournal**.
2. Välj **Ny**.
3. I fältet **Namn** i den nya raden väljer du ett alternativ i listrutemenyn.
4. Klicka på **Rader** i åtgärdsfönstret.
5. Ange önskade värden i fältet **Konto**.
6. Ange ett värde i fältet **Faktura**.
7. I fältet **Kredit** väljer du ett tal.
8. Ange önskade värden i fältet **Motkonto**.
9. Välj **Moms**.
10. Ange ett tal i fältet **Totalt faktiskt momsbelopp**.
11. På fliken **justering** kan momsbeloppen justeras per momskod.
12. Välj **Återställ utfall till beräknade belopp**.
13. Välj **OK**.
14. Välj **Spara**.

