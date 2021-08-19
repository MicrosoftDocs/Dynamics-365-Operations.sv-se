---
title: Fysiska och ekonomiska uppdateringar
description: I det här avsnittet ges en översikt över vilka transaktionstyper som ökar eller minskar lagerkvantiteterna.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3c7b354a7524a6e96da8e2a9eeca0d4f21b9fb0a6d515620ab3fe446425af17c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6734389"
---
# <a name="physical-and-financial-updates"></a>Fysiska och ekonomiska uppdateringar

[!include [banner](../includes/banner.md)]

I det här avsnittet ges en översikt över vilka transaktionstyper som ökar eller minskar lagerkvantiteterna. 

Lagertransaktioner kan uppdateras fysiskt och ekonomiskt i Dynamics 365 Supply Chain Management. I vissa typer av fysiska och ekonomiska transaktioner ökar lagerkvantiteterna, medan andra minskar kvantiteten.

## <a name="physical-increases"></a>Fysiska ökningar
När en fysisk transaktion bokförs får transaktionsposten statusen **Inlevererad**. Följande transaktioner betraktas som fysiska ökningar:

-   Inleverans av inköpsorder
-   Försäljningsorder, följesedelsretur
-   Rapportera en produktionsorder som färdig
-   Biprodukt på plocklista för tillverkningsorder

## <a name="financial-increases"></a>Ekonomiska ökningar
När en ekonomisk inleveranstransaktion bokförs blir statusen för transaktionen som ökar kvantiteten **Inköpt**. Följande transaktioner betraktas som ekonomiska ökningar:

-   Leverantörsfaktura
-   Inköpsorderfaktura för en retur
-   Kostnadskalkylering för tillverkningsorder
-   Lagerjournaler med positiv kvantitet, t.ex. förflyttningar, resultat, inventeringsjournaler, strukturlistor och överföringar

## <a name="transactions-that-increase-quantity"></a>Transaktioner som ökar kvantiteten
Transaktioner som ökar kvantiteten bokförs till den löpande genomsnittliga självkostnaden. Den beräknade löpande genomsnittliga självkostnaden baseras på kostnaden för respektive transaktion för alla lagerdimensioner som spåras ekonomiskt. Mer information om löpande genomsnittliga självkostnaden finns i [Löpande genomsnittlig självkostnad](running-average-cost-price.md).

## <a name="transactions-that-decrease-quantity"></a>Transaktioner som minskar kvantiteten
Den beräknade löpande genomsnittliga självkostnaden används när en transaktion som minskar kvantiteten bokförs, oavsett vilken lagermodell som är associerad med lagret. Transaktionen som minskar kvantiteten får inte tidigare ha markerats till en annan transaktion innan den bokfördes. Om den fysiska lagerbehållningen blir negativ används den lagerkostnad som definierats för artikeln på sidan **Artikel**. 

> [!NOTE]
> Om multisitefunktionen har aktiverats utgörs denna kostnad i stället av den lagerkostnad som definierats för en plats på sidan **Standardorderinställningar** page.

## <a name="physical-issues-vs-financial-issues"></a>Fysiska utleveranser kontra ekonomiska problem.
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]