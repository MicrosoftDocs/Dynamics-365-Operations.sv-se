---
title: Skapa en räntekod med ett intervall
description: Räntekoder kan ställas in för att beräkna olika räntebelopp baserat på ett värdeintervall.
author: ShivamPandey-msft
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c18269d277f64433da35e7dc1675cd3afda8e070
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835038"
---
# <a name="create-an-interest-code-with-a-range"></a>Skapa en räntekod med ett intervall

[!include [banner](../../includes/banner.md)]
Räntekoder kan ställas in för att beräkna olika räntebelopp baserat på ett värdeintervall. I den här proceduren visas hur du lägger till en räntekod och lägger till ett intervall i den.

1. Gå till Kredit och inkasso > Ränta > Ställ in räntekoder.
2. Klicka på Ny.
3. I fältet Räntekod, ange räntekodens namn.
4. I fältet Beskrivning anger du en beskrivning av räntekoden.
5. Välj Månad.
6. Expandera avsnittet Earnings.
7. Expandera avsnittet Earnings by currency.
8. I fältet Redovisningsbokföringskonto, ange önskade värden.
9. I fältet Ränta per intervall, välj Månader.
10. Klicka på Lägg till.
11. I fältet Beskrivning anger du en beskrivning för valutan och intervallet.
12. Klicka på Spara.
13. Klicka på Intervall.
14. Klicka på Ny.
15. Ange Från-värdet 0 och ange sedan ränteprocenten per månad som ska användas för att beräkna räntan. I vårt exempel är den 1,5.
16. Klicka på Ny.
17. Ange nästa Från-värde till 4, vilket är den första månaden du beräknar ett nytt räntebelopp.
18. Ange den ränteprocent per månad som ska användas för att beräkna räntan från och med månad 4. Välj 2.0 i det här exemplet.
19. Klicka på Ny.
20. Ange nästa Från-värde till 7, vilket är den nästa månad du beräknar ett nytt räntebelopp.
21. Ange den ränteprocent per månad som ska användas för att beräkna räntan från och med månad 7. Välj 2.5 i det här exemplet.
22. Avsluta inställningarna genom att klicka på Stäng.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]