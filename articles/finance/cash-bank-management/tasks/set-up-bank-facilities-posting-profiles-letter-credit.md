---
title: Ställ in bankkreditlimiter och bokföringsprofiler för en remburs
description: Den här proceduren går genom skapandet av bankkreditlimiter och den bokföringsprofil som krävs för att bearbeta remburser.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7fe5b2ba43c4fcb4855c742bdb6f8209ebd92d68
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779473"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a>Ställ in bankkreditlimiter och bokföringsprofiler för en remburs

[!include [banner](../../includes/banner.md)]

Den här proceduren går genom skapandet av bankkreditlimiter och den bokföringsprofil som krävs för att bearbeta remburser. 

I den här uppgiften används demonstrationsföretaget USMF.


## <a name="general-ledger-parameter"></a>Redovisningsparameter
1. Gå till **Kassa- och bankhantering > Inställningar > Parametrar för kassa- och bankhantering**.
2. Expandera **bankdokument** avsnittet.
3. Välj alternativet **Aktivera importremburs**.
4. Välj alternativet **Aktivera exportremburs**.
5. Klicka på **Spara**.
6. Stäng sidan.

## <a name="create-bank-facility"></a>Skapa bankkreditlimit
1. Gå till **Kassa- och bankhantering > Inställningar > Bankkreditlimiter**.
2. Klicka på **Ny**.
3. I fältet **Kreditlimitgrupp**, ange bankkreditlimitgruppens namn.
4. I fältet **Beskrivning**, ange beskrivningen av bankkreditlimitgruppen.
5. Klicka på **Spara**.
6. Klicka på fliken **Kreditlimittyper**.
7. Klicka på **Ny**.
8. I fältet **Kreditlimittyp**, ange en unik kod.
9. I fältet **Beskrivning** anger du ett värde.
10. I fältet **Kreditlimittyp**, öppna sökningen genom att klicka på den nedrullningsbara knappen.
11. Hitta och markera önskad post i listan.
12. Klicka på länken på den valda raden i listan.
13. I fältet **Kreditlimitens natur**, välj natur för kreditlimiten.
14. Klicka på **Spara**.
15. Stäng sidan.

## <a name="bank-posting-profile"></a>Bokföringsprofil för bank
1. Gå till **Kassa- och bankhantering > Inställningar > Bokföringsprofil för bankdokument**.
2. Klicka på **Ny**.
3. I fältet **Konto-/gruppnummer**, öppna sökningen genom att klicka på den nedrullningsbara knappen.
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
6. Välj huvudkontot för kvittning.
    * Detta konto används när du beräknar kassaflödesprognosen.  
7. I fältet **Avgiftskonto**, välj kontot för utgiftstransaktioner.
8. I fältet **Marginalkonto**, välj kontot för marginaltransaktioner.
    * Det här kontot debiteras när ingångsmarginalen bokförs och krediteras när betalningen bokförs.  
9. Klicka på **Spara**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
