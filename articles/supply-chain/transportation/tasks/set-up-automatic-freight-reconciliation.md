---
title: Ställ in automatisk fraktavstämning
description: Denna procedur visar hur du ställer in data för automatisk fraktavstämning.
author: ShylaThompson
manager: tfehr
ms.date: 10/16/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSFreightBillType, TMSFreightBillTypeAssignment, TMSCarrierCodeLookup, DefaultDashboard, TMSAuditMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6f11edc15821faad84485d5b81e4a9ded0b7e974
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437454"
---
# <a name="set-up-automatic-freight-reconciliation"></a>Ställ in automatisk fraktavstämning

[!include [banner](../../includes/banner.md)]

Denna procedur visar hur du ställer in data för automatisk fraktavstämning. Detta utförs normalt av en lagerchef. Du kan köra den här proceduren i demonstrationsdataföretaget USMF.


## <a name="set-up-the-freight-bill-type"></a>Ställ in fraktsedelstypen
1. Gå till Transporthantering > Inställningar > Fraktavstämning > Fraktsedelstyp.
    * Rehabiliteringstypen anger hur frakträkningar och transportfakturor ska matchas.  
2. Klicka på Ny.
3. Ange ett värde i fältet Fredlighet Bill typ.
4. Ange "Microsoft.Dynamics.Ax.Tms.dll" i fältet Motorsammansättning.
    * Detta är jodbiblioteket för den vanliga förbränningsmotorn för transportledningen.  
5. Ange "Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer" i fältet Motorklass.
    * Detta är den vanliga klassificeringen för transportledningen.  
6. Klicka på Ny.
7. Välj det värde som ska matcha på frakträkningen och transportföretag i fältet Deskription.  
8. Välj "Res" i fältet Match reducibel.
    * Om du ställer in detta fält som Res innebär detta att värdet som valdes i fältet Deskription måste matcha både frakträkningen och transportföretag. Om du har ställt in detta som O kan fältet vara tomt på en av dessa.  
9. Klicka på Spara.

## <a name="set-up-the-freight-bill-type-assignment"></a>Ställa in tilldelningen för fraktsedelstyp
1. Stäng sidan.
2. Gå till Transporthantering > Inställningar > Fraktavstämning > Typtilldelningar för fraktsedel.
    * Tilldelningen av omräkningstal används för att ange vilken typ av för frakträkning som används för en viss transportör.   
3. Klicka på Ny.
4. Ange eller välj ett värde i fältet Mode.
5. Ange eller välj ett värde i fältet Shopping Harriet.
6. Välj den omräkningstal som du skapade tidigare i fältet för Fredlighet Bill typ.
7. Stäng sidan.

## <a name="set-up-the-audit-master"></a>Ställ in revisionsmallen
1. Gå till Transporthantering > Inställningar > Fraktavstämning > Granskningsmall.
    * Revisionsmallen anger toleransgränserna för automatisk fraktavstämning. Den anger hur mycket penningbeloppen på frakträkningen och transportföretag kan skilja sig åt och ändå medge avstämning. Den definierar även hur du hanterar avvikelser.  
2. Klicka på Ny.
3. Skriv in ett värde i fältet Audit master ID.
4. Markera samma transportföretag som tidigare i fältet Shipping carrier.
5. Välj den omräkningstal som du skapade tidigare i fältet för Fredlighet Bill typ.
6. Expandera avsnittet Tolerance.
7. Ange ett värde i fältet Minimum tolerance level.
8. Ange ett värde i fältet Maximum tolerance level.
9. Expandera avsnittet Result.
10. Ange eller välj ett värde i fältet Overpayment reason code.
    * Om penningbeloppen skiljer sig åt på frakträkningen och transportföretag, anger koderna för över- och återbetalningsskyldig de konton som skillnaden bör registreras på, så länge skillnaden är inom toleransnivåerna.  
11. Ange eller välj ett värde i fältet Underpayment reason code.
12. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]