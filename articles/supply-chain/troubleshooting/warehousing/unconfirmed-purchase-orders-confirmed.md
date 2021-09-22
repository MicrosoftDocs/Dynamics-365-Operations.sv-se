---
title: Uppgiften att uppdatera produktinleveranser bekräftar obekräftade order
description: När uppdatering av produktinleveranser har körts bekräftar systemet ej bekräftade order som har statusen Registrerad. Läs om funktionen som korrigerar det här problemet.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 171a978efc6b55b92f429381e72036cb1b3296c6
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477597"
---
# <a name="unconfirmed-purchase-orders-are-confirmed-after-running-update-product-receipts"></a>Obekräftade inköpsorder bekräftas efter att Uppdatera produktinleveranser har körts

## <a name="symptoms"></a>Symtom

När du har kört den periodiska uppgiften *Uppdatera produktinleveranser* bekräftar systemet automatiskt obekräftade inköpsorder som har statusen för lagertransaktion *Registrerad*.

## <a name="resolution"></a>Lösning

En ny funktion för hantering av inkommande last *Överinleverans av lastkvantiteter* åtgärdar problemet. För att aktivera denna funktion, gå till arbetsytan [Funktionshantering](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) och aktivera följande funktioner i den ordning de listas i:

1. Associera lagertransaktioner för inköpsorder med last
2. Överinleverans av lastkvantiteter

Mer information finns i [bokföra registrerade produktkvantiteter mot inköpsorder](/dynamics365/supply-chain/warehousing/inbound-load-handling).
