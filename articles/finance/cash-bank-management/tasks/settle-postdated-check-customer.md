---
title: Kvitta en efterdaterad check från en kund
description: Du kan kvitta en postdaterad check när checken har clearats av banken.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPostDatedChecks, SystemDate, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e61ac6d6785dd0383d5e5dcaca4cc55bf6deb52
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780026"
---
# <a name="settle-a-postdated-check-from-a-customer"></a>Kvitta en efterdaterad check från en kund

[!include [banner](../../includes/banner.md)]

Du kan kvitta en postdaterad check när checken har clearats av banken. Den ekonomiska transaktionen stäms också av mot interimskontotransaktionen för den postdaterade checken. 

Följande uppgifter måste ha slutförts innan du börjar med den här.

1) Ställ in efterdaterade checkar

2) Registrera och bokför en efterdaterad check för en kund 



Rollen för den här uppgiftsguiden är Kassaförvaltare.



I den här proceduren används demonstrationsföretaget USMF.

1. Gå till **Kredit och inkasso > Förfrågningar och rapporter > Betalningar > Kunds efterdaterade checkar**.
2. Klicka på **Kvitta**.
3. Klicka på **Kvitta clearingposter**.
    * Kvitta kundkontot för checktransaktionen.  
4. Stäng sidan.
5. Gå till **Redovisning > Journalposter > Allmänna journaler**.
6. I fältet **Visa**, välj ett alternativ.
7. Markera eller avmarkera kryssrutan **Visa enbart användarskapade**.
8. Hitta och markera önskad post i listan.
9. Klicka på **Rader**.
10. Klicka på **Verifikation**.
11. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
