--- 
title: "Ställ in momskvittningsperioder"
description: "Momskvittningsperioder innehåller information om periodintervall för rapportering och betalning av moms."
author: twheeloc
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
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: ab7d3a00a327f42a9f70c954d9b64a360a7f9163
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-sales-tax-settlement-periods"></a>Ställ in momskvittningsperioder

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

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
14. Expandera periodintervallfliken.
15. Klicka på Lägg till.
16. Markera vald rad i listan.
17. Ange ett datum i fältet Från datum.
18. Ange ett datum i fältet Till datum.
19. Klicka på Nytt periodintervall.
    * När det första periodintervallet har angetts, kan nya perioder skapas automatiskt. Du kan komma tillbaka och lägga till nya periodintervall som krävs.  
20. Stäng sidan.


