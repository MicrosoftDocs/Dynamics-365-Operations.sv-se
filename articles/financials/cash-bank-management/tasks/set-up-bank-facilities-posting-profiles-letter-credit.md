--- 
title: "Ställ in bankkreditlimiter och bokföringsprofiler för en remburs"
description: "Den här proceduren går genom skapandet av bankkreditlimiter och den bokföringsprofil som krävs för att bearbeta remburser."
author: kweekley
manager: AnnBe
ms.date: 10/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 18ad27eb673745d09569f6a49c8bc66132550f35
ms.openlocfilehash: 9ad19534091bdbd8924f90174b720d818b9ed778
ms.contentlocale: sv-se
ms.lasthandoff: 10/27/2017

---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a>Ställ in bankkreditlimiter och bokföringsprofiler för en remburs

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren går genom skapandet av bankkreditlimiter och den bokföringsprofil som krävs för att bearbeta remburser. 

I den här uppgiften används demonstrationsföretaget "USMF".






## <a name="general-ledger-parameter"></a>Redovisningsparameter
1. Gå till Kassa- och bankhantering > Inställningar > Parametrar för kassa- och bankhantering.
2. Expandera bankdokumentavsnittet.
3. Välj alternativet Aktivera importremburs.
4. Välj alternativet Aktivera exportremburs.
5. Klicka på Spara.
6. Stäng sidan.

## <a name="create-bank-facility"></a>Skapa bankkreditlimit
1. Gå till Kassa- och bankhantering > Inställningar > Bankkreditlimiter.
2. Klicka på Ny.
3. I fältet Kreditlimitgrupp, ange bankkreditlimitgruppens namn.
4. I fältet Beskrivning, ange beskrivningen av bankkreditlimitgruppen.
5. Klicka på Spara.
6. Klicka på fliken Kreditlimittyper.
7. Klicka på Ny.
8. I fältet Kreditlimittyp, ange en unik kod.
9. Ange ett värde i fältet Beskrivning.
10. I fältet Kreditlimittyp, öppna sökningen genom att klicka på den nedrullningsbara knappen.
11. Hitta och markera önskad post i listan.
12. Klicka på länken på den valda raden i listan.
13. I fältet Kreditlimitens natur, välj natur för kreditlimiten.
14. Klicka på Spara.
15. Stäng sidan.

## <a name="bank-posting-profile"></a>Bokföringsprofil för bank
1. Gå till Kassa- och bankhantering > Inställningar > Bokföringsprofil för bankdokument.
2. Klicka på Ny.
3. I fältet Konto-/gruppnummer, öppna sökningen genom att klicka på den nedrullningsbara knappen.
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
6. Välj huvudkontot för kvittning.
    * Detta konto används när du beräknar kassaflödesprognosen.  
7. I fältet Avgiftskonto, välj kontot för utgiftstransaktioner.
8. I fältet Marginalkonto, välj kontot för marginaltransaktioner.
    * Det här kontot debiteras när ingångsmarginalen bokförs och krediteras när betalningen bokförs.  
9. Klicka på Spara.


