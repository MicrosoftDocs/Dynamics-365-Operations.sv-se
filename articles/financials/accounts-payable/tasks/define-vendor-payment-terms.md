--- 
title: "Definiera villkor för leverantörsbetalning"
description: "Ställ in betalningsvillkor för leverantörsfakturor."
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PaymTerm, CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a00ca73b1bc301960132a86846749d12c39ed3f7
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="define-vendor-payment-terms"></a>Definiera villkor för leverantörsbetalning

[!include [task guide banner](../../includes/task-guide-banner.md)]

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


