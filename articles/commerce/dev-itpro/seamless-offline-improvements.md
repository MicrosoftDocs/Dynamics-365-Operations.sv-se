---
title: Sömlös offline-växlare för presentkort och kreditnotor
description: Denna artikel innehåller en översikt över förbättringar som ger en sömlös offline-växel för specifika betalningstyper.
author: BrianShook
ms.date: 02/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 20120-02-28
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: e0416a61bd5fd3b875b427ad8a6313d0e9936f0d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869171"
---
# <a name="seamless-offline-switch-for-gift-card-and-credit-memo-operations"></a>Sömlös offline-växlare för presentkort och kreditnotor

[!include [banner](../includes/banner.md)]

Om en kassaenhet (POS) förlorar sin anslutning till kanaldatabasen, kan de flesta kassaåtgärder och transaktioner som pågår fortsätta efter att kassören har fått ett varningsmeddelande om att anslutningen bryts. I vissa fall har transaktioner emellertid element som är beroende av realtidsservice och dessa element stöds inte när kassan. I denna artikel beskrivs vissa funktioner som hjälper dig att minska den förlorade anslutningen i dessa scenarier.

## <a name="completing-gift-card-transactions-in-offline-mode"></a>Slutför presentkortstransaktioner i offlineläge

Interna presentkort är beroende av realtidsservice, eftersom saldot för presentkort måste hanteras centralt i Microsoft Dynamics 365 Commerce-administration. För att förhindra bedrägerier eller andra synkroniseringsproblem låses presentkort så snart de har lagts till i en transaktion. Låsfunktionen ser till att ett presentkort inte kan användas på flera terminaler samtidigt. När transaktionen har slutförts uppdateras presentkortet och tas bort.

Om kassan förlorar anslutningen efter att ett presentkort har lagts till i en transaktion, kan det dock bli oanvändbart. För att förhindra att den här situationen har Dynamics 365 Commerce en parameter som aktiverar transaktioner som inkluderar en presentkortsrad som ska slutföras medan kassan är offline. När den här parametern är aktiverad sparas presentkortstransaktioner som tvingas offline tillsammans med offline-transaktioner och de synkroniseras till Commerce headquarters när offline-transaktioner synkroniseras. Synkroniseringen låser även upp presentkortet så att det kan användas i en annan terminal.

Om du vill att funktionen ska ingå presentkortstransaktioner efter att du växlat till offlineläge, gå till fliken **Bokföring** på sidan **Commerce-parametrar**. På den fliken letar du upp snabbfliken **presentkort** och konfigurerar **Tillåt presentkortstransaktioner i offlineläge** till **ja**.

![Presentkortsinställning för offline.](../media/gift.png)

Commerce-parametrar cachelagras normalt. När den här parametern har uppdaterats och distributionsplanen har initierats för att synkronisera ändringen till kanalen, kan ändringen därför ta upp till 24 timmar innan ändringen börjar gälla. Återställ Microsoft Internet Information Services (IIS) om du vill att ändringen ska börja gälla omedelbart.

## <a name="completing-credit-memo-transactions-in-offline-mode"></a>Slutför transaktioner för kreditnota i offlineläge

Precis som interna presentkort underhålls kreditnotor centralt i Commerce headquarters. Commerce har en parameter som gör att transaktioner för kreditnota kan slutföras medan kassan är offline. Den här parametern fungerar som den presentkortsparameter som nämndes i föregående avsnitt. När parametern aktiveras synkroniseras de transaktioner för kreditnota som försätts i offlineläge till kanaldatabasen, tillsammans med andra transaktioner som utfördes medan kassan var offline.

Om du vill att funktionen ska ingå transaktioner för kreditnota efter att du växlat till offlineläge, gå till fliken **Bokföring** på sidan **Commerce-parametrar**. På den fliken letar du upp snabbfliken **kreditnota** och konfigurerar **Tillåt transaktioner för kreditnota i offlineläge** till **ja**.

![Inställning för kreditnota offline.](../media/creditmemo.png)

Commerce-parametrar cachelagras normalt. När den här parametern har uppdaterats och distributionsplanen har initierats för att synkronisera ändringen till kanalen, kan ändringen därför ta upp till 24 timmar innan ändringen börjar gälla. Återställ IIS om du vill att ändringen ska börja gälla omedelbart.

## <a name="related-articles"></a>Relaterade artiklar

- [Offline kassafunktionalitet (POS)](../pos-offline-functionality.md)
- [Verksamhet för online- och offlinekassor (POS)](../pos-operations.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]