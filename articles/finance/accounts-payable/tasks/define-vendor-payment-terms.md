---
title: Definiera villkor för leverantörsbetalning
description: Den här artikeln innehåller information om hur du ställer in betalningsvillkor för leverantörsfakturor.
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PaymTerm, CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a676856ed43bf1b78684eac0682e0fdef9c84083
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906483"
---
# <a name="define-vendor-payment-terms"></a>Definiera villkor för leverantörsbetalning

[!include [banner](../../includes/banner.md)]

Den här artikeln innehåller information om hur du ställer in betalningsvillkor för leverantörsfakturor. I den här uppgiften används demonstrationsföretaget USMF.

1. Go to **Navigeringsfönster > Moduler > Leverantörsreskontra > Betalningsinställning > Betalningsvillkor**.
2. Välj **Ny**. **Betalningsvillkoren** används för att definiera hur förfallodatumen ska beräknas. Detta används inte för att definiera hur kassarabattdatum beräknas.  
3. Skriv ett värde i fältet **Betalningsvillkor**.
4. I fältet **Beskrivning** anger du ett värde.
5. Välj ett tal i fältet **Dagar**. Numret som anges här, ska användas för att lägger till förfallodatumet eller till slutet av perioden som identifieras i **betalsättet**. Om du till exempel väljer **Netto**, kommer antalet läggas till förfallodatumet. Om du väljer aktuell månad, kommer det att lägga till numret till sista dagen av den **aktuella månaden** för att beräkna förfallodatumet.  
6. Välj **Spara**.
7. Stäng sidan.
8. Gå till **Leverantörsreskontra > Betalningsinställning > Kassarabatter**.
9. Välj **Ny**.
10. Ange ett ID i fältet **Kassarabatt**.
11. I fältet **Beskrivning** anger du ett värde.
12. Om leverantören ger en nivårabatt, välj nästa kassarabatt, efter att den aktuella har upphörts.
13. Stäng sidan.
14. Välj ett tal i fältet **Dagar**. Den kvantitet som anges i fältet **dagar** som ska användas för att beräkna, **kassarabattdatumet** baserat på vilken väljare valdes i fältet **netto/aktuella**. Om **Netto** markeras, ska kvantitet läggas till fakturadatumet för att bestämma kassarabattdatumet. Om **Aktuell månad** markeras, ska kvantitet läggas till i slutet av valutamånaden för att bestämma kassarabattdatumet.  
15. Ange kassarabatten som en procent i fältet **Rabatt**. 
16. Ange huvudkontot som kassarabatten ska bokföras på för kundfakturor och ange sedan huvudkontot som kassarabatten ska bokföras på för leverantörsfakturor. Om **Rabattmotkonton** anges till **Använd huvudkonto för leverantörsrabatter** ska huvudkontot användas. Om du väljer **Konton på fakturarader** bokförs kassarabatten till samma tillgångs/utgifthuvudkonton på raderna för fakturan.  
17. Välj **Spara**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
