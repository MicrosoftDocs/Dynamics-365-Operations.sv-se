---
title: Beräkna och justera moms på en leverantörsfaktura
description: I det här avsnittet beskriver hur du justerar momsen på en leverantörsfaktura Dynamics 365 Finance.
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
ms.openlocfilehash: 2f3521f7bc56659fc6f7a6d47f581ddbfea16523
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139977"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a>Beräkna och justera moms på en leverantörsfaktura

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskriver hur du justerar momsen på en leverantörsfaktura. Om det ursprungliga källdokumentet visar andra momsbelopp än dem som beräknas kan du justera dessa belopp, innan du bokför dem. I den här uppgiften används demonstrationsföretaget DEMF.

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

