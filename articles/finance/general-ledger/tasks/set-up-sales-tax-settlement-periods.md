---
title: Ställ in momskvittningsperioder
description: Det här avsnittet innehåller information om hur du ställer in momskvittningsperioder i Dynamics 365 Finance.
author: twheeloc
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 83587df3963d215fec020150e6b707e431c1b6eb
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944787"
---
# <a name="set-up-sales-tax-settlement-periods"></a>Ställ in momskvittningsperioder

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller information om hur du ställer in momskvittningsperioder. Momskvittningsperioder innehåller information om periodintervall för rapportering och betalning av moms. En kvittningprocess kan köras för en kvittningsperiod för ett specifikt datumintervall. Alla momskoder som är kopplade till kvittningsperioden kvittas. Beroende på inställningen av den relaterade skattemyndigheten bokförs skatteskulden antingen till en leverantör eller ett redovisningskonto.

I den här uppgiften används demonstrationsföretaget USMF.

1. I navigeringsfönstret går du till **Moduler > Skatt > Indirekta skatter > Moms > Momskvittningsperioder.**
2. Välj **Ny**.
3. Ange ett värde i fältet **Kvittningsperiod**.
4. I fältet **Beskrivning** anger du ett värde.
5. I fältet **Myndighet** väljer du skattekontoret som tar emot rapporter och betalningar som skapats för kvittningsperioden.
6. Hitta och markera önskad post i listan.
7. I fältet **Betalningsvillkor** väljer du önskad post i den nedrullningsbara menyn. Den relaterade skattemyndigheten kan ställas in som en leverantör och vid momskvittningen skapas en öppen leverantörsfaktura. Förfallodatumet för den öppna leverantörsfakturan definieras i betalningsvillkoren.  
8. Välj en typ av kvittningsperiodintervall.
9. Ange antalet periodintervallenheter per period. Till exempel har ett kvartal 3 månader.
10. Markera eller avmarkera kryssrutan **Använd batchbearbetning för momskvittning**. Kvittningprocessen för kvittningsperioden kan behandlas som batchjobb i bakgrunden. Detta rekommenderas för ett stort antal momstransaktioner inom ett periodintervall.
11. Markera eller avmarkera kryssrutan **Förhindra att motbokade momstransaktioner genereras**. Som standard genereras motbokade momstransaktioner under kvittningsprocessen som kan orsaka prestandaproblem om det finns ett stort antal momstransaktioner inom ett periodintervall. Markera denna kryssruta för att förhindra att motbokade momstransaktioner genereras.
12. Expandera fliken **Periodintervall**.
13. Markera **Lägg till**.
14. Ange ett datum i fältet **Från-datum** på den nya raden.
15. I fältet **Till-datum**, anger du ett datum.
16. Välj **Nytt periodintervall**. När det första periodintervallet har angetts, kan nya perioder skapas automatiskt. Du kan komma tillbaka och lägga till nya periodintervall som krävs.  
17. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
