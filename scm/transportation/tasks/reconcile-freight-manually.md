--- 
title: "Stäm av fraktsedel manuellt"
description: "I den här proceduren visas hur du stämmer av frakt manuellt."
author: BibiSp
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 28de4c720cd771f476f379d925e9500e41482aa6
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="reconcile-freight-manually"></a>Stäm av fraktsedel manuellt

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du stämmer av frakt manuellt. Detta görs normalt av en transportkoordinator. Du kan använda den här proceduren i demonstrationsdataföretaget USMF.


## <a name="select-a-load-to-reconcile"></a>Välj en beläggning att stämma av
1. Gå till Transporthantering > Planering > Workbench för lastplanering.
2. Avmarkera kryssrutan Clear the Hide shipped and received. 
3. Välj beläggningen som har beläggningen ID 00006 i listan.

## <a name="create-a-carrier-invoice"></a>Skapa en transportföretagsfaktura
    * Om du stämmer av frakten manuellt och inte får transportfakturor automatiskt, kan du skapa en faktura baserat på frakträkningen.  
1. Klicka på Relaterad information.
2. Klicka på Freight bill details.
3. Klicka på Generate freight bill invoice.
4. Ange ett värde i fältet Faktura.
5. Klicka på OK.

## <a name="reconcile-the-invoice"></a>Stäm av fakturan
    * När du stämmer av en transportföretagsfaktura och en frakträkning görs detta rad för rad.  
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

