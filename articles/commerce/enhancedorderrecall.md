---
title: Åtgärden återkalla order i POS
description: Det här avsnittet handlar om vilka funktioner som finns för att förbättra sidor för orderåterkallning i POS.
author: hhainesms
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 21e8045d754006345f5ad68e1e67579386c6df4a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010084"
---
# <a name="recall-order-operation-in-pos"></a>Åtgärden återkalla order i POS

[!include [banner](includes/banner.md)]

Åtgärden **Återkalla order** i Commerce-POS ger uppdaterade funktioner för ordersökning och filtrering, samt orderspecifik information. Den här funktionen är tillgänglig i Commerce versioner 10.0.15 och senare.

För att aktivera denna funktion, slå på funktionen **Förbättrad åtgärden återkalla order i POS** i arbetsytan **funktionshantering** i Commerce-administration. När du har aktiverat funktionen kan du överväga att uppdatera [bildskärmslayouter](pos-screen-layouts.md) i POS för att dra nytta av vissa av de ändrade funktionerna.

Genom att konfigurera knappen **Återkalla order** kan organisationer distribuera operationen med en fördefinierad visning.

![Konfiguration av knapprutnät](media/recallorderbuttongrid.png)

Visningsalternativen är följande.
- **Inget** – det här alternativet distribuerar åtgärden utan specifik visning. När en användare öppnar åtgärden med den här konfigurationen uppmanas de att söka efter order eller välja från ett fördefinierat orderfilter.
- **Order som ska uppfyllas** – när en användare startar operationen körs en fråga automatiskt för att söka i och visa en lista med order som ska uppfyllas av butiken. Dessa order konfigureras för butikshämtning eller butiksleverans och raderna på dessa order har ännu inte plockats eller packats.
- **Order som ska hämtas** – när en användare startar operationen körs en fråga automatiskt för att söka i och visa en lista med order som är konfigurerade för hämtning i butik eller i användarens nuvarande butik.
- **Order som ska levereras** – när en användare startar operationen körs en fråga automatiskt för att söka i och visa en lista med order som är konfigurerade för leverans från användarens nuvarande butik.

När du startar åtgärden **Återkalla order** från POS, om bildskärmen har konfigurerats till **ingen** kan en användare söka efter och hämta order på något av följande sätt.
- Skanna orderstreckkoder. Det här fältet söker efter ordernummer, kanalreferens och kvitto-ID för matchningar.
- Välj ikonen **Sök order** eller **Sök och filtrera** på AppBar om du vill använda filtreringsfunktionen för att söka efter order som uppfyller filtervillkoren.
- Välj från ett fördefinierat filter på listrutan **Visa order** (order som ska uppfyllas, order som ska hämtas eller order som ska levereras).

![RecallOrderMainMenu](media/recallordermain.png)

När sökkriterier har tillämpats visas en lista med matchande försäljningsorder i programmet.

![RecallOrderDetail](media/orderrecalldetail.png)

En användare kan välja en order i listan om du vill visa mer information. Informationspanelen till höger på skärmen visar specifika uppgifter för den valda ordern, inklusive order raddetaljer, leveransinformation och information om uppfyllelse.

En användare kan välja en operation i AppBar. Beroende på orderns status kan vissa operationer inte aktiveras.

- **Retur** – kör en retur för en eller flera fakturor som hör till den valda kundordern.

- **Avbryt** – utfärda en fullständig annullering av den valda försäljningsordern.

- **Uppfyllelse** – överför användaren till sidan orderuppfyllelse, som kommer att filtreras för den valda ordern. Endast orderrader som är öppna för att fullgöras av användarens butik för den valda ordern kommer att visas.

- **Redigera** – tillåter att användare ändrar den valda kundordern.

- **Hämta** – startar upphämtningsflödet, vilket innebär att användaren kan välja produkter som ska hämtas och skapa en transaktion för upphämtningsförsäljning.
