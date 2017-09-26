--- 
title: "Definiera villkor för leverantörsbetalning"
description: "Ställ in betalningsvillkor för leverantörsfakturor."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: cbac3b27c25377abff341c4bf259e553c14a4ae8
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="define-vendor-payment-terms"></a>Definiera villkor för leverantörsbetalning

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ställ in betalningsvillkor för leverantörsfakturor. I den här uppgiften används demonstrationsföretaget USMF.

1. Gå till Leverantörsreskontra > Betalningsinställning > Betalningsvillkor.
2. Klicka på Ny.
    * Betalningsvillkoren används för att definiera hur förfallodatumen ska beräknas. Detta används inte för att definiera hur kassarabattdatum beräknas.  
3. Skriv ett värde i fältet Betalningsvillkor.
4. Ange ett värde i fältet Beskrivning.
5. Välj ett tal i fältet Dagar.
    * Numret som anges här, ska användas för att lägger till förfallodatumet eller till slutet av perioden som identifieras i betalningsmetoden. Om du till exempel väljer nettobehov, kommer antalet läggas till förfallodatumet. Om du väljer aktuell månad, kommer det att lägga till numret till sista dagen av den aktuella månaden för att beräkna förfallodatumet.  
6. Klicka på Spara.
7. Stäng sidan.
8. Gå till Leverantörsreskontra > Betalningsinställning > Kassarabatter.
9. Klicka på Ny.
10. Ange ett ID i fältet Kassarabatt.
11. Ange ett värde i fältet Beskrivning.
12. Om leverantören ger en nivårabatt, välj nästa kassarabatt, efter att den aktuella har upphörts.
13. Stäng sidan.
14. Välj ett tal i fältet Dagar.
    * Den kvantitet som anges i fältet dagar som ska användas för att beräkna, kassarabattdatumet baserat på vilken väljare valdes i fältet netto/aktuella fältet. Om Netto markeras, ska kvantitet läggas till fakturadatumet för att bestämma kassarabattdatumet. Om Aktuell månad markeras, ska kvantitet läggas till i slutet av valutamånaden för att bestämma kassarabattdatumet.  
15. Ange kassarabatten som en procent i fältet Rabatt, 
16. Ange huvudkontot som kassarabatten ska bokföras på för kundfakturor.
17. Ange huvudkontot som kassarabatten ska bokföras på för leverantörsfakturor.
    * Om Rabattmotkonton är Huvudkonto för leverantörsrabatter ska huvudkontot användas.  Om du väljer Konton på fakturarader bokförs kassarabatten till samma tillgångs/utgifthuvudkonton på raderna för fakturan.  
18. Klicka på Spara.

