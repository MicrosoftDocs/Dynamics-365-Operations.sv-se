---
title: Skapa en räntekod med ett intervall
description: Räntekoder kan ställas in för att beräkna olika räntebelopp baserat på ett värdeintervall.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2d76ae320ee43a473b64afe311876cc94b953b20
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "367649"
---
# <a name="create-an-interest-code-with-a-range"></a>Skapa en räntekod med ett intervall

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

