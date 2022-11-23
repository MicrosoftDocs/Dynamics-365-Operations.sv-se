---
title: Kvitta en efterdaterad check för en leverantör
description: Kvitta en efterdaterad check som utfärdats till en leverantör när banken har rensat checktransaktionen efter att checken har förfallit till betalning och avförts av banken.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3e3816a2f1c95d568a173cb07daad0473703da9c
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779512"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a>Kvitta en efterdaterad check för en leverantör

[!include [banner](../../includes/banner.md)]

Kvitta en efterdaterad check som utfärdats till en leverantör när banken har rensat checktransaktionen efter att checken har förfallit till betalning och avförts av banken. 

Slutför följande procedurer innan du börjar med denna:

1) Ställ in efterdaterade checkar

2) Registrera och bokför en efterdaterad check för en leverantör



Rollen för den här proceduren är Kassaförvaltare. I den här proceduren används demonstrationsföretaget USMF.

1. Gå till **Leverantörsreskontra > Betalningar > Leverantörens efterdaterade checkar**.
2. Klicka på **Kvitta**.
3. Klicka på **Kvitta clearingposter**.
    * Kvitta leverantörskontot för checktransaktionen.  
4. Stäng sidan.
5. Gå till **Redovisning > Journalposter > Allmänna journaler**.
6. I fältet **Visa**, välj **Alla**.
7. Markera eller avmarkera kryssrutan **Visa enbart användarskapade**.
8. Markera vald rad i listan.
9. Klicka på **Rader**.
10. Klicka på **Verifikation**.
11. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
