---
title: Automatisk uppdatering av tillgångsräknare
description: Det här avsnittet beskriver automatisk uppdatering av tillgångsräknare i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 97e6912cd37d6f82d8bf022141f04645a3364ee1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875910"
---
# <a name="automatic-update-of-asset-counters"></a>Automatisk uppdatering av tillgångsräknare

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

I föregående avsnitt beskrivs manuell registrering av tillgångsräknare. Inställning av tillgångsräknare beskrivs i [Räknare](../setup-for-objects/counters.md).

Räknarvärden kan också uppdateras automatiskt från produktionsregistreringar, baserat på produktionstimmar eller produktionskvantitet. Detta görs i **Uppdatera tillgångsräknare**. Du kan uppdatera en eller flera tillgångar genom att infoga en parameter, **Från datum**. Den här parametern anger startdatum för produktionsregistreringar (timmar eller kvantitet producerad), dvs. startdatumet som räknarvärden ska uppdateras från.

Alla tillgångar som är relaterade till en resurs *och* har tillgångsräknare, som har ställts in för uppdatering baserad på producerad kvantitet eller produktionstimmar, tas med i en automatisk uppdatering och nya räknarvärden skapas.

För räknare som baseras på produktionskvantitet, ingår godkänd kvantitet och felregistrerad kvantitet i beräkningen. Om enheten som används för registrering av producerad kvantitet skiljer sig från den enhet som används på räknaren, konverteras kvantiteten till räknarenheten.

Som nämnts ovan kan automatiska räknare uppdateras från produktionsregistreringar. Därför måste den tillgång som du vill uppdatera räknare automatiskt för vara relaterad till en resurs (dator). Följande beskrivningar ger en översikt över inställning och bearbetning av produktionsorder (i modulen **Produktionskontroll**), som används som grund för automatisk uppdatering av räknare på en till gång i modulen **Tillgångshantering**.

När producerade kvantiteter eller produktionstimmar har registrerats för resursen kan du uppdatera de relaterade räknarna för tillgångar.

1. Klicka på **Tillgångshantering** > **Periodisk** > **Tillgångar** > **Uppdatera tillgångsräknare**.

2. Välj startdatum för den automatiska uppdateringen i fältet **Från datum**.

>[!NOTE]
>Datumet i det här fältet är "pågående arbete"-datumet från **Flödestransaktioner** (**Produktionskontroll** > **Förfrågningar och rapporter** > **Produktion** > **Flödestransaktioner** >  fältet **Fysiskt datum**).

3. Om du vill välja vissa tillgångar, tillgångstyper eller resurser för den automatiska uppdateringen klickar du på **Filter** på snabbfliken **Poster som ska ingå** och gör de relevanta valen.

4. På snabbfliken **Kör i bakgrunden** kan du ställa in den automatiska uppdateringen som ett batchjobb, efter behov.

![Figur 1](media/12-work-orders.png)

5. Klicka på **OK**. När uppdateringen av tillgångsräknaren är färdig kan du se de räknarregistreringar relaterade till tillgången i **Tillgångsräknare** (**Tillgångshantering** > **Allmänt** > **Tillgångar** > **Alla tillgångar** > välj tillgång > knappen **Räknare**).

I **Tillgångsräknarsummor** kan du få en översikt över den senaste registreringen som gjorts för alla räknartyper för alla tillgångar. Klicka på **Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **Sammanlagt värde för tillgång**. Vyn liknar **Tillgångsräknare**, men du kan inte lägga till eller redigera registreringar i **Sammanlagt värde för tillgång**. Den är endast för översikt.

![Figur 2](media/13-work-orders.png)


- Det går fortfarande att skapa manuella räknarvärderegistreringar för räknartyper som uppdateras automatiskt. Mer information finns i avsnittet "Manuell uppdatering av tillgångsräknare".
- Du kan ställa in räknare som är relaterade till en annan räknare, vilket innebär att när en räknare uppdateras, uppdateras relaterade räknare automatiskt samtidigt. Information om hur du ställer in relaterade räknare finns i [Räknare](../setup-for-objects/counters.md).
