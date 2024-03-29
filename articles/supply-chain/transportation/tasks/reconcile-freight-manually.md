---
title: Stäm av fraktsedel manuellt
description: I den här proceduren visas hur du stämmer av frakt manuellt.
author: Weijiesa
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily, TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8afec41cdb10185077d39a665d0153df1c9bdb9f
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672750"
---
# <a name="reconcile-freight-manually"></a>Stäm av fraktsedel manuellt

[!include [banner](../../includes/banner.md)]]

I den här proceduren visas hur du stämmer av frakt manuellt. Detta görs normalt av en transportkoordinator. Du kan använda den här proceduren i demonstrationsdataföretaget USMF.


## <a name="select-a-load-to-reconcile"></a>Välj en beläggning att stämma av
1. Gå till Transporthantering > Planering > Workbench för lastplanering.
2. Avmarkera kryssrutan Clear the Hide shipped and received. 
3. Välj beläggningen som har beläggningen ID 00006 i listan.

## <a name="create-a-carrier-invoice"></a>Skapa en transportföretagsfaktura
Om du stämmer av frakten manuellt och inte får transportfakturor automatiskt, kan du skapa en faktura baserat på frakträkningen.  
1. Klicka på Relaterad information.
2. Klicka på Freight bill details.
3. Klicka på Generate freight bill invoice.
4. Ange ett värde i fältet Faktura.
5. Klicka på OK.

## <a name="reconcile-the-invoice"></a>Stäm av fakturan
När du stämmer av en transportföretagsfaktura och en frakträkning görs detta rad för rad.  
1. Klicka på Match freight bills and invoices.
2. Expandera avsnittet Invoice details.
3. Expandera avsnittet Unmatched freight bill details.
4. Markera vald rad i listan.
5. Klicka på Match.
6. Expandera avsnittet Matched freight bill details.

## <a name="submit-the-invoice-for-approval"></a>Skicka fakturan för godkännande
1. Klicka på Submit for approval.
2. Stäng sidan.
3. Rensa kryssrutan Hide approved. 
4. Klicka på Vendor invoice journals.
5. Klicka för att följa länken i fältet Reference journal number.
6. Klicka på Rader.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]