---
title: Automatisk uppdatering av tillgångsräknare
description: Det här avsnittet beskriver automatisk uppdatering av tillgångsräknare i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d3e8619439545cf3ea42f84a6dd7ee6ffdf1026e
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021940"
---
# <a name="automatic-update-of-asset-counters"></a>Automatisk uppdatering av tillgångsräknare

[!include [banner](../../includes/banner.md)]

Mer information om manuell registrering av tillgångsräknare finns i [Manuell uppdatering av tillgångsräknare](../work-orders/manual-update-of-asset-counters.md). Mer information om hur du ställer in tillgångsräknare finns i [räknare](../setup-for-objects/counters.md).

Räknarvärden kan också uppdateras automatiskt från produktionsregistreringar, baserat på produktionstimmar eller produktionskvantitet (det vill säga den kvantitet som produceras). Uppdateringen görs på sidan **uppdatera tillgångsräknare**. Du kan uppdatera en eller flera tillgångar genom att konfigurera en parameter, **Från datum**. Den här parametern anger startdatum för produktionsregistreringar (produktionstimmar eller produktionskvantiteter). Med andra ord anges det datum då räknarens värden ska uppdateras.

Alla tillgångar som är relaterade till en resurs *och* har tillgångsräknare, som har ställts in för uppdatering baserad på produktionstimmar eller produktionskvantitet tas med i en automatisk uppdatering. Nya räknarvärden kommer att skapas.

För räknare som baseras på produktionskvantiteten inkluderar antalet både den godkända kvantiteten och den felkvantitet som är registrerad. Om enheten som används för registrering av produktionskvantitet skiljer sig från den som används på räknaren, konverteras kvantiteten så att den motsvarar räknarenheten.

Som nämnts ovan kan automatiska räknare uppdateras från produktionsregistreringar. Därför måste den tillgång som du vill uppdatera räknare automatiskt för vara relaterad till en resurs (dator). När producerade kvantiteter eller produktionstimmar har registrerats för resursen kan du uppdatera de relaterade räknarna för tillgångar.

1. Klicka på **Tillgångshantering** > **Periodisk** > **Tillgångar** > **Uppdatera tillgångsräknare**.

2. Välj startdatum för den automatiska uppdateringen i fältet **Från datum**.

    >[!NOTE]
    >Datumet i det här fältet är "pågående arbete"-datumet från **Flödestransaktioner** (**Produktionskontroll** > **Förfrågningar och rapporter** > **Produktion** > **Flödestransaktioner** >  fältet **Fysiskt datum**).

3. På snabbfliken **Poster som ska ingå** kan du välja specifika tillgångar, tillgångstyper eller resurser för den automatiska uppdateringen. Välj **filter** och gör relevanta val.

4. På snabbfliken **Kör i bakgrunden** kan du ställa in den automatiska uppdateringen som ett batchjobb, efter behov.

    Bilden nedan visar ett exempel på dialogrutan **Uppdatera tillgångsräknare**.

    ![Figur 1](media/12-work-orders.png)

5. Välj **OK**. 

När uppdateringen av tillgångsräknaren har genomförts kan du visa de räknarregistreringar som är relaterade till tillgången på sidan **Tillgångsräknare**. Välj **Tillgångshantering** > **Allmänt** > **Tillgångar** > **Alla tillgångar**, välj tillgången och sedan i åtgärdsfönstret på fliken **Tillgång** i gruppen **Förebyggande** väljer du **Räknare**.

På sidan **Sammanlagt värde för tillgång** kan du få en översikt över den senaste registreringen som gjorts för alla räknartyper för alla tillgångar. Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **Sammanlagt värde för tillgång**. Den här sidan liknar sidan **Tillgångsräknare**, men du kan inte lägga till eller redigera registreringar. Den är endast för översikt.

Bilden nedan visar ett exempel på sidan **Sammanlagt värde för tillgång**.

![Figur 2](media/13-work-orders.png)

Observera följande:

- Du kan fortfarande skapa manuella räknarvärderegistreringar för räknartyper som uppdateras automatiskt. Mer information finns i  [Manuell uppdatering av tillgångsräknare](../work-orders/manual-update-of-asset-counters.md).

- Du kan ställa in räknare som är relaterade till en annan räknare. I detta fall uppdateras relaterade räknare automatiskt samtidigt när en räknare uppdateras. Mer information om hur du ställer in relaterade räknare finns i [räknare](../setup-for-objects/counters.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]