---
title: Ställ in momskvittningsperioder
description: Momskvittningsperioder innehåller information om periodintervall för rapportering och betalning av moms.
author: twheeloc
manager: AnnBe
ms.date: 10/15/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1087ed78e91b487ca7157bfdac1d72ae3f477875
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569596"
---
# <a name="set-up-sales-tax-settlement-periods"></a>Ställ in momskvittningsperioder

[!include [task guide banner](../../includes/task-guide-banner.md)]

Momskvittningsperioder innehåller information om periodintervall för rapportering och betalning av moms. En kvittningprocess kan köras för en kvittningsperiod för ett specifikt datumintervall. Alla momskoder som är kopplade till kvittningsperioden kvittas. Beroende på inställningen av den relaterade skattemyndigheten bokförs skatteskulden antingen till en leverantör eller ett redovisningskonto.



I den här uppgiften används demonstrationsföretaget USMF.



1. Gå till Moms > Indirekt moms > Moms > Momskvittningsperioder.
2. Klicka på Ny.
3. I fältet Kvittningsperiod, ange ett värde.
4. Ange ett värde i fältet Beskrivning.
5. I fältet Myndighet väljer du skattekontoret som tar emot rapporter och betalningar som skapats för kvittningsperioden.
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.
8. I fältet Betalningsvillkor, öppna sökningen genom att klicka på den nedrullningsbara knappen.
    * Den relaterade skattemyndigheten kan ställas in som en leverantör och vid momskvittningen skapas en öppen leverantörsfaktura. Förfallodatumet för den öppna leverantörsfakturan definieras i betalningsvillkoren.  
9. Hitta och markera önskad post i listan.
10. Klicka på länken på den valda raden i listan.
11. Välj en typ av kvittningsperiodintervall.
12. Ange antalet periodintervallenheter per period. Till exempel har ett kvartal 3 månader.
13. Markera eller avmarkera kryssrutan Använd batchbearbetning för momskvittning.
    * Kvittningprocessen för kvittningsperioden kan behandlas som batchjobb i bakgrunden. Detta rekommenderas för ett stort antal momstransaktioner inom ett periodintervall.  
14. Markera eller avmarkera kryssrutan Förhindra att motbokade momstransaktioner genereras.
    * Som standard genereras motbokade momstransaktioner under kvittningsprocessen som kan orsaka prestandaproblem om det finns ett stort antal momstransaktioner inom ett periodintervall. Markera denna kryssruta för att förhindra att motbokade momstransaktioner genereras.
15. Expandera periodintervallfliken.
16. Klicka på Lägg till.
17. Markera vald rad i listan.
18. Ange ett datum i fältet Från datum.
19. Ange ett datum i fältet Till datum.
20. Klicka på Nytt periodintervall.
    * När det första periodintervallet har angetts, kan nya perioder skapas automatiskt. Du kan komma tillbaka och lägga till nya periodintervall som krävs.  
21. Stäng sidan.

