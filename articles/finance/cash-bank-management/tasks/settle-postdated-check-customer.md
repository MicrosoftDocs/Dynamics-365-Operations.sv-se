---
title: Kvitta en efterdaterad check från en kund
description: Du kan kvitta en postdaterad check när checken har clearats av banken.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPostDatedChecks, SystemDate, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab591fc3ac529e65c15ee083377954a83363edd528861aff9bc449bfc10c7735
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771738"
---
# <a name="settle-a-postdated-check-from-a-customer"></a>Kvitta en efterdaterad check från en kund

[!include [banner](../../includes/banner.md)]

Du kan kvitta en postdaterad check när checken har clearats av banken. Den ekonomiska transaktionen stäms också av mot interimskontotransaktionen för den postdaterade checken. 

Följande uppgifter måste ha slutförts innan du börjar med den här.

1) Ställ in efterdaterade checkar

2) Registrera och bokför en efterdaterad check för en kund 



Rollen för den här uppgiftsguiden är Kassaförvaltare.



I den här proceduren används demonstrationsföretaget USMF.

1. Gå till Kredit och inkasso > Förfrågningar och rapporter > Betalningar > Kunds efterdaterade checkar.
2. Klicka på Kvitta.
3. Klicka på Kvitta clearingposter.
    * Kvitta kundkontot för checktransaktionen.  
4. Stäng sidan.
5. Gå till Redovisning > Journalposter > Allmänna journaler.
6. I fältet Visa, välj ett alternativ.
7. Markera eller avmarkera kryssrutan Visa enbart användarskapade.
8. Hitta och markera önskad post i listan.
9. Klicka på Rader.
10. Klicka på Verifikation.
11. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]