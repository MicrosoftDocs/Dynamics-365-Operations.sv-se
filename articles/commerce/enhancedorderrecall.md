---
title: Åtgärden återkalla order i POS
description: Det här avsnittet handlar om vilka funktioner som finns för att förbättra sidor för orderåterkallning i POS.
author: hhainesms
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 43d6b2e4e5d923b16b02337432fc5259f66c0bf1a8ba1dbf311fb76cb3f085e1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6737614"
---
# <a name="recall-order-operation-in-pos"></a>Åtgärden återkalla order i POS

[!include [banner](includes/banner.md)]

Åtgärden **Återkalla order** i Commerce-POS ger uppdaterade funktioner för ordersökning och filtrering, samt orderspecifik information. Den här funktionen är tillgänglig i Commerce versioner 10.0.15 och senare.

För att aktivera denna funktion, slå på funktionen **Förbättrad åtgärden återkalla order i POS** i arbetsytan **funktionshantering** i Commerce-administration. När du har aktiverat funktionen kan du överväga att uppdatera [bildskärmslayouter](pos-screen-layouts.md) i POS för att dra nytta av vissa av de ändrade funktionerna.

Genom att konfigurera knappen **Återkalla order** kan organisationer distribuera operationen med en fördefinierad visning.

![Konfiguration av knapprutnät.](media/recallorderbuttongrid.png)

Visningsalternativen är följande.
- **Inget** – det här alternativet distribuerar åtgärden utan specifik visning. När en användare öppnar åtgärden med den här konfigurationen uppmanas de att söka efter order eller välja från ett fördefinierat orderfilter.
- **Order som ska uppfyllas** – när en användare startar operationen körs en fråga automatiskt för att söka i och visa en lista med order som ska uppfyllas av användarens nuvarande butik. Dessa order konfigureras för butikshämtning eller butiksleverans och raderna på dessa order har ännu inte plockats eller packats.
- **Order som ska hämtas** – när en användare startar operationen körs en fråga automatiskt för att söka i och visa en lista med order som är konfigurerade för hämtning i butik eller i användarens nuvarande butik.
- **Order som ska levereras** – när en användare startar operationen körs en fråga automatiskt för att söka i och visa en lista med order som är konfigurerade för leverans från användarens nuvarande butik.

När du startar åtgärden **Återkalla order** från POS, om bildskärmen har konfigurerats till **ingen** kan en användare söka efter och hämta order på något av följande sätt.
- Skanna orderstreckkoder. Det här fältet söker efter ordernummer, kanalreferens och kvitto-ID för matchningar.
- Välj ikonen **Sök order** eller **Sök och filtrera** på AppBar om du vill använda filtreringsfunktionen för att söka efter order som uppfyller filtervillkoren.
- Välj från ett fördefinierat filter på listrutan **Visa order** (order som ska uppfyllas, order som ska hämtas eller order som ska levereras).

![RecallOrderMainMenu.](media/recallordermain.png)

När sökkriterier har tillämpats visas en lista med matchande försäljningsorder i programmet. Tänk på att när du använder sök-/filteralternativen behöver de hämtade orderna inte vara order som kopplas till användarens aktuella butik. Den här sökprocessen hämtar och visar alla kundorder som matchar sökkriterierna, även om ordern skapades eller skapades för att uppfyllas av en annan butik/kanal eller lagerställeplats.

![RecallOrderDetail.](media/orderrecalldetail.png)

En användare kan välja en order i listan om du vill visa mer information. Informationspanelen till höger på skärmen visar specifika uppgifter för den valda ordern, inklusive order raddetaljer, leveransinformation och information om uppfyllelse.

En användare kan välja en operation i AppBar. Beroende på orderns status kan vissa operationer inte aktiveras.

- **Retur** – Startar processen för att skapa en retur för någon av de fakturerade produkterna på den valda kundordern.

- **Avbryt** – utfärda en fullständig annullering av den valda försäljningsordern. Det här alternativet är inte tillgängligt för order som initieras via en kundtjänstkanal och kan inte användas för att annullera en order delvis.

- **Uppfyllelse** – överför användaren till sidan orderuppfyllelse, som kommer att filtreras för den valda ordern. Endast orderrader som är öppna för att fullgöras av användarens butik för den valda ordern kommer att visas.

- **Redigera** – tillåter att användare ändrar den valda kundordern. Order kan endast redigeras i [vissa scenarier](customer-orders-overview.md#edit-an-existing-customer-order).

- **Upphämtning** – Det här alternativet är tillgängligt om ordern har en eller flera rader angivna för upphämtning i användarens aktuella butik. Denna åtgärd startar upphämtningsflödet, vilket innebär att användaren kan välja produkter som ska hämtas och skapa en transaktion för upphämtningsförsäljning.

## <a name="add-notifications-to-the-recall-order-operation"></a>Lägga till meddelanden i åtgärden för återkallad order

I version 10.0.18 och senare kan du konfigurera POS-meddelanden och live-panelnotifieringar för åtgärden **återkalla order** om så önskas. Mer information finns i [Visa ordermeddelanden i kassan (POS)](notifications-pos.md).  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
