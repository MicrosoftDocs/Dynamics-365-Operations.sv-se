---
title: Bearbeta upphämtning av kundorder i POS
description: Denna artikel förklarar funktionerna som är tillgängliga i kassaprogrammet (POS) för bearbetning av upphämtning av kundorder.
author: Hhainesms
ms.date: 01/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 0a886f156fff96f3b7e6026c405d3c8700d57f62
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910479"
---
# <a name="process-customer-order-pickups-in-pos"></a>Bearbeta upphämtning av kundorder i POS

[!include [banner](includes/banner.md)]

När en [kundorder](customer-orders-overview.md) skapas för upphämtning i butik kan en butiksägare använda kassaprogrammet för att starta upphämtning av lager. POS kör den slutliga betalningsregistreringen vid behov. Den slutför också lager- och ekonomisk bokföring för de kvantiteter som hämtas upp.

Om du är butiksanvändare kan du utföra upphämtningen genom att använda antingen åtgärden **Återkalla order** eller åtgärden **Orderuppfyllelse** i POS. Om du vill göra åtgärden **Upphämtning** tillgänglig, måste du först följa ett av dessa steg:

- Om du vill använda åtgärden **Återkalla order** söker du efter och väljer den order som ska hämtas upp.
- Om du vill använda åtgärden **Orderuppfyllelse** söker du efter och markerar en eller flera orderrader.

Om den valda ordern eller orderraderna inte är konfigurerad för upphämtning i denna specifika butik, eller om ordern redan har plockats upp helt, kommer åtgärden **Upphämtning** inte att vara tillgänglig.

![Upphämtningsåtgärd.](media/pickupoperation.png)

I Microsoft Dynamics 365 Commerce version 10.0.17 och senare kan funktionen **Förbättrad användarupplevelse för bearbetning av upphämtningsorder i POS** aktiveras via Funktionshanteringen i Commerce headquarters. Om den här funktionen är inaktiverad kan användarna inte välja upphämtningskvantiteter. Som standard är den fullständiga kvantiteten som beställts för raden den kvantitet som ska hämtas upp. Den här erfarenheten kan vara problematisk, detta eftersom användarna kan glömma bort att välja vissa artiklar för upphämtning när de utför upphämtningen via orderuppfyllelse.

Funktionen **Förbättrad användarupplevelse för bearbetning av upphämtningsorder i POS** ger användaren större kontroll över valet av produkter som ska hämtas upp samt kvantiteten av dessa produkter. Användarna behöver inte markera alla rader i försäljningsordern på uppfyllelsesidan innan de väljer **Hämta**. Alla artiklar som kan hämtas upp visas. Användare kan ange flera rader för upphämtning även om endast en produktrad har valts.

När funktionen **Förbättra användarupplevelse för bearbetning av upphämtningsorder i POS** är aktiverad och du väljer åtgärden **Hämta**, visas dialogrutan **Hämta**. Där kan du välja de artiklar och kvantiteter som ska hämtas upp. Som standard betraktas all beställd kvantitet som har lager i plockad eller packad status som tillgänglig för upphämtning. Som standard anges den kvantiteten som upphämtningskvantitet. Du kan ändra kvantiteten som angavs om kvantiteten inte har värdet 0 (noll) och inte överskrider den totala öppna kvantiteten (dvs. ej fakturerad) för den valda raden.

![Dialogrutan Hämta.](media/pickupselect.png)

När du har valt de kvantiteter som ska hämtas och sedan valt **Hämta** visas transaktionssidan. Om funktionen för [flerkanalsbetalningar](omni-channel-payments.md) har aktiverats och det finns förauktoriserade kreditkortsbetalningar registrerade, måste du tillämpa betalningen.

På transaktionssidan beräknar systemet de belopp som förfaller genom beräkning av det totala beloppet som förfaller för de valda upphämtningsartiklarna och sedan subtrahera eventuella tidigare använda insättningar eller auktoriserade kreditkortsbetalningar. Du måste bearbeta betalning för att slutföra upphämtningstransaktionen. Om [skärmlayouten](pos-screen-layouts.md) på transaktionssidan har konfigurerats att omfatta åtgärden **Slutför transaktion** och inget belopp förfaller, kan du slutföra transaktionen utan att välja något betalsätt. Om åtgärden **Slutför transaktion** inte finns att tillgå kan du välja länken **Beloppet 0,00 USD förfaller** i fönstret **Summor** för att slutföra transaktionen utan att behöva välja ett betalsätt.

![Transaktionssida för en upphämtningstransaktion för kundorder.](media/pickupcart.png)

## <a name="changing-pickup-lines-or-quantities"></a>Ändra upphämtningsrader eller kvantiteter

Om du måste ändra upphämtningskvantiteten efter det att du har valt artiklarna som ska hämtas, kan du välja **Ange kvantitet**. Du kan inte konfigurera upphämtningskvantiteten som **0** (noll) eller öka den till ett värde som överstiger den icke-fakturerade kvantitet som återstår för beställd rad. Om du vill ta bort en upphämtningsrad från transaktionsvagnen väljer du **Annullera transaktion**. Den aktuella transaktionen stoppas och flödet för åtgärden **Hämta** startas om.

Om funktionen **Förbättra användarupplevelsen för upphämtning av order i kassan** är aktiverad, kan organisationer lägga till en knapp för åtgärden **Ändras upphämtningsrader** på transaktionens skärmlayout. När du har skapat kundvagnen för upphämtningstransaktion i POS och valt artiklar kan du välja **Ändra upphämtningsrader** om du måste ändra hämtningsartiklar men inte vill annullera hela transaktionen. I dialogrutan **Ändra upphämtningsrader** som visas, kan du ändra upphämtningsartiklarna och kvantiteterna. Transaktionsvagnen uppdateras sedan efter dina ändringar.

![Ändra dialogrutan för upphämtningsartiklar.](media/pickupchange.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]