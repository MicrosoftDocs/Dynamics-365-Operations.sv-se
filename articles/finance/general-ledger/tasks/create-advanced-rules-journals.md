---
title: Skapa avancerade regler för journaler
description: Den här proceduren går igenom hur du kan skapa avancerade regler för journaler.
author: aprilolson
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalControl, CompanyLookup, LedgerJournalPostControl
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f5cc41f19928fd415fb54073fd733f97a3e7aa01
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8717430"
---
# <a name="create-advanced-rules-for-journals"></a>Skapa avancerade regler för journaler

[!include [banner](../../includes/banner.md)]

Den här proceduren går igenom hur du kan skapa avancerade regler för journaler. Detta inkluderar att ställa in begränsningar för journalkontroll och användarbokföring. I proceduren används demonstrationsföretag USMF.


## <a name="set-up-journal-control"></a>Ställ in journalkontroll
1. I **Navigeringsfönstret**, gå till **Moduler > Redovisning > Journalkonfiguration > Journalnamn**.
2. Hitta och markera önskad post i listan.
3. Klicka på **Journalkontroll** i **Åtgärdsfönstret**.
4. På snabbfliken **Vilka kontotyper kan bokföras**, klicka på **Lägg till**.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Företagskonton**.
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.
8. På snabbfliken **Vilka segmentvärden är giltiga för den här journalen** klicka på **Lägg till**.
9. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Kontostruktur**.
10. Hitta och markera önskad post i listan.
11. Klicka på länken på den valda raden i listan.
12. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Segment**.
13. Klicka på länken på den valda raden i listan.
14. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Från-värde**.
15. Hitta och markera önskad post i listan.
16. Klicka på länken på den valda raden i listan.
17. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Till-värde**.
18. Hitta och markera önskad post i listan.
19. Klicka på länken på den valda raden i listan.

## <a name="set-up-posting-restrictions"></a>Konfigurera bokföringsrestriktioner
1. Stäng sidan.
2. Klicka på **Bokföringsrestriktioner**.
3. Välj Efter användargrupp i fältet **Hur vill du ställa in bokföringsrestriktioner**.
4. Markera gruppen du vill tillåta bokföring för när det gäller journalnamnet i trädet.
5. Klicka på **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
