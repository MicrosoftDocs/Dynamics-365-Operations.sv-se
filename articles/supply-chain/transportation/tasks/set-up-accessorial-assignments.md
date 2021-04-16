---
title: Ställ in tilläggstilldelningar
description: I den här proceduren visas hur du ställer in en tilldelning av tillägg.
author: ShylaThompson
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSAccessorialAssignment
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 06139e87596965a481fc7fb2e2f653594be0ac1e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838476"
---
# <a name="set-up-accessorial-assignments"></a>Ställ in tilläggstilldelningar

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du ställer in en tilldelning av tillägg. Detta görs normalt av en transportkoordinator. Innan du använder den här guiden måste du köra guiden "Ställ in hubbens tilläggsavgifter och tilläggsmallar".


## <a name="set-up-accessorial-assignment"></a>Ställa in Tilldelning av tillägg
1. Gå till Transporthantering > Inställningar > Klassificering > Tilldelning av tillägg.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
4. Växla expanderingen av avsnittet Detaljer.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Hubb.
6. I listan väljer du den hubb som du har skapat en tilläggsmall för när du körde guiden "Ställ in hubbens tilläggsavgifter och tilläggsmallar". 
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Hubbens tilläggs-ID.
8. Klicka på länken på den valda raden i listan.
9. Växla expanderingen av avsnittet Kriterier.
    * I avsnittet Kriterier kan du välja exakta kriterier för när avgiften ska tillämpas, baserat de olika värden som erbjuds här.  
10. Ange alternativet Tillämpa alltid till Ja.
11. Välj ett alternativ i fältet Nivå för tilldelning av tillägg.
12. Växla expanderingen av avsnittet Beräkning.
13. Välj "Fast" i fältet Typ av tilläggsavgift.
    * Typen av tilläggsavgift bestämmer hur du beräknar den verkliga avgiften. I det här exemplet är det en fast avgift.  
14. Ange ett nummer i fältet Tilläggsavgift.
15. Klicka på Spara.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]