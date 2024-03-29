---
title: Periodisering av konstanta kostnader för en tillverkad artikel
description: En tillverkad artikels konstanta kostnader återspeglar driftställtiderna och komponenterna med en konstant kvantitet eller ett konstant kassationsbelopp.
author: JennySong-SH
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcTable, BOMCalcTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 274503
ms.assetid: 535ab25d-a031-4e8c-84ec-478f2987a1ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: d466395859e19874183691e697c8aca3a774d359
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675415"
---
# <a name="amortize-constant-costs-for-a-manufactured-item"></a>Periodisering av konstanta kostnader för en tillverkad artikel

[!include [banner](../includes/banner.md)]

En tillverkad artikels konstanta kostnader återspeglar driftställtiderna och komponenterna med en konstant kvantitet eller ett konstant kassationsbelopp. 

Begreppet kostnadskalkylerad partistorlek används för att periodisera de konstanta kostnaderna i den beräknade kostnaden för en tillverkad artikel. Detta begrepp har flera synonymer, varav en är redovisningspartistorlek. Begreppet periodisering av konstanta kostnader har också flera synonymer, varav en är proportionella konstanta kostnader.

Kostnadskalkylerad partistorlekskvantitet för en tillverkad artikel används i en strukturlisteberäkning. Kvantiteten beror på hur du initierar och utför strukturlisteberäkningen, enligt följande:

-   Standardberäkning av kvantitet i en artikels strukturlisteberäkning − artikelns standardorderkvantitet (för lager) används för kostnadskalkylerad partistorlek, men standardvärdet kan vara en större kvantitet för att avspegla artikelns orderkvantitetsmultipel. Artikelns standardorderkvantitet och multipel kan definieras i dess standardorderinställningar eller i sitespecifika orderinställningar.
-   Specificerad beräkningskvantitet i en artikels strukturlisteberäkning − den angivna beräkningskvantiteten fungerar som kostnadskalkylerad partistorlek för artikeln. Beräkningskvantiteten anges automatiskt till artikelns standardorderkvantitet, men standardvärdet kan ändras manuellt. Den angivna beräkningskvantiteten representerar den kostnadskalkylerade partistorleken för den angivna artikeln och för tillverkade komponenter med strukturlisteradtypen Produktion. Detta beror på förutsättningen att komponenten kommer att produceras i exakt kvantitet. Den kostnadskalkylerade partistorleken för andra tillverkade komponenter med strukturlisteradtypen Artikel avspeglar deras standardorderkvantitet.
-   Specificerad beräkningskvantitet i en artikels strukturlisteberäkning vid tillverkning mot order − den specificerade beräkningskvantiteten fungerar som den kostnadskalkylerade partistorleken för artikeln och dess tillverkade komponenter när nedbrytningsläget Tillverka mot order används för strukturlisteberäkningar. Förutsättningen är att de tillverkade komponenterna produceras i exakt kvantitet, precis som en tillverkade komponent med strukturlisteradtypen Produktion.
-   Angiven beräkningskvantitet i en orderspecifik strukturlisteberäkning − en orderspecifik strukturlisteberäkning kan utföras för en radartikel på en försäljningsorder, försäljningsoffert eller serviceorder. Den angivna beräkningskvantiteten använder kvantiteten för den ursprungliga radartikeln, men standardkvantiteten kan ändras. Du kan välja om nedbrytningsläget Tillverka mot order eller Flera nivåer ska användas för den orderspecifika strukturlisteberäkningen.

Den beräknade mängden av en tillverkad artikels periodiserade konstanta kostnader kallas tillägg.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]