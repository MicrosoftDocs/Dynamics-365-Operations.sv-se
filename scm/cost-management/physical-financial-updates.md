---
title: Fysiska och ekonomiska uppdateringar
description: "I det här avsnittet ges en översikt över vilka transaktionstyper som ökar eller minskar lagerkvantiteterna."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: a0eeb5a57f9b82150150752c64e89c2c91856889
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Fysiska och ekonomiska uppdateringar
<a id="physical-and-financial-updates" class="xliff"></a>

[!include[banner](../includes/banner.md)]


I det här avsnittet ges en översikt över vilka transaktionstyper som ökar eller minskar lagerkvantiteterna. 

Lagertransaktioner kan uppdateras fysiskt och ekonomiskt i Microsoft Dynamics 365 for Finance and Operations. I vissa typer av fysiska och ekonomiska transaktioner ökar lagerkvantiteterna, medan andra minskar kvantiteten.

## Fysiska ökningar
<a id="physical-increases" class="xliff"></a>
När en fysisk transaktion bokförs får transaktionsposten statusen **Inlevererad**. Följande transaktioner betraktas som fysiska ökningar:

-   Inleverans av inköpsorder
-   Försäljningsorder, följesedelsretur
-   Rapportera en produktionsorder som färdig
-   Biprodukt på plocklista för tillverkningsorder

## Ekonomiska ökningar
<a id="financial-increases" class="xliff"></a>
När en ekonomisk inleveranstransaktion bokförs blir statusen för transaktionen som ökar kvantiteten **Inköpt**. Följande transaktioner betraktas som ekonomiska ökningar:

-   Leverantörsfaktura
-   Inköpsorderfaktura för en retur
-   Kostnadskalkylering för tillverkningsorder
-   Lagerjournaler med positiv kvantitet, t.ex. förflyttningar, resultat, inventeringsjournaler, strukturlistor och överföringar

## Transaktioner som ökar kvantiteten
<a id="transactions-that-increase-quantity" class="xliff"></a>
Transaktioner som ökar kvantiteten bokförs till den löpande genomsnittliga självkostnaden. Finance and Operations beräknar en löpande genomsnittlig självkostnad som baseras på kostnaden för respektive transaktion för alla lagerdimensioner som spåras ekonomiskt. Mer information om löpande genomsnittliga självkostnaden finns i [Löpande genomsnittlig självkostnad](running-average-cost-price.md).

## Transaktioner som minskar kvantiteten
<a id="transactions-that-decrease-quantity" class="xliff"></a>
Finance and Operations använder den beräknade löpande genomsnittliga självkostnaden när en transaktion som minskar kvantiteten bokförs, oavsett vilken lagermodell som är associerad med lagret. Transaktionen som minskar kvantiteten får inte tidigare ha markerats till en annan transaktion innan den bokfördes. Om den fysiska lagerbehållningen blir negativ använder Finance and Operations den lagerkostnad som definierats för artikeln på sidan **Artikel**. **Obs!** Om multisitefunktionen har aktiverats utgörs denna kostnad i stället av den lagerkostnad som definierats för en plats på sidan **Standardorderinställningar** page.

## Fysiska utleveranser kontra ekonomiska problem.
<a id="physical-issues-vs-financial-issues" class="xliff"></a>
När en fysisk utleveranstransaktion bokförs blir transaktionspostens status **Avdragen**. Följande transaktioner betraktas som fysiska utleveranser:

-   Plocklistejournal för tillverkningsorder
-   Följesedel för försäljningsorder
-   Inköpsorder, följesedelsretur

När en ekonomisk transaktion bokförs får transaktionsposten statusen **Såld**. Följande transaktioner betraktas som ekonomiska utleveranser:

-   Avsluta en produktionsorder
-   Försäljningsorderfaktura
-   Leverantörsfakturaretur
-   Lagerjournaler med negativ kvantitet, t.ex. förflyttningar, resultat, inventeringsjournaler, strukturlistor och överföringar

Transaktioner som minskar kvantiteten bokförs till den löpande genomsnittliga självkostnaden. Därför måste lagerstängningsprocessen kvitta utleveranstransaktioner mot inleveranstransaktioner baserat på den lagermodell som har valts för varje artikel.




