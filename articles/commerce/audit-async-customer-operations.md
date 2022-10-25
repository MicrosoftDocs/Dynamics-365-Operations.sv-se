---
title: Granska synkronisering av kundåtgärder i administrationen
description: I den här artikeln förklaras hur du granskar synkronisering av kundoperationer i Microsoft Dynamics 365 Commerce headquarters för att åtgärda eventuella problem med webbplatsanvändaren.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-09-28
ms.openlocfilehash: c615b0b436e01a1423b5611a72f0056b5b14f8e8
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691109"
---
# <a name="audit-synchronization-of-customer-operations-in-headquarters"></a>Granska synkronisering av kundåtgärder i administrationen

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

I den här artikeln förklaras hur du granskar synkronisering av kundoperationer i Microsoft Dynamics 365 Commerce headquarters för att åtgärda eventuella problem med webbplatsanvändaren.

När en organisation börjar anpassa sig efter möjligheten att skapa och redigera kunder asynkront, behöver platsadministratörerna ett sätt att visa och felsöka operationer, baserat på webbplatsanvändarförfrågningar eller processfel. I dessa scenarier ska platsadministratörer kunna granska skapande och redigering av kunder och åtgärda fel genom att använda en självbetjäningsmodell.

## <a name="customer-synchronization-status"></a>Kundsynkroniseringsstatus

När du väljer det asynkrona läget för kundhantering och dess motsvarande funktioner Commerce headquarters-administratörer skapa och schemalägga ett återkommande batchjobb för **P-jobbet**, jobbet **Synkronisera kunder och affärspartners från asynkront läge** och **1010** så att eventuella asynkrona kunder konverteras till synkrona kunder i Commerce headquarters. Synkronisering av åtgärder inom kundhantering sker när dessa jobb körs. För mer information, se [Skapningsläge asynkron kund](async-customer-mode.md).

Som företagsägare kan du utföra följande operationer:

- Visa alla webbplatsanvändares skapa/redigera åtgärder. Detaljer inkluderar status och en tidstämpel.
- Filtrera operationer genom att använda fält och värden i kundregistret för att begränsa redovisningsloggen.
- Visa korta beskrivningar av ändringar tillsammans med statusinformation för att förstå operationer på hög nivå.
- Om du vill misslyckas redigerar du och korrigerar problematiska fält och sparar och synkroniserar sedan specifika kundoperationer.

### <a name="elements-on-the-customer-synchronization-status-page"></a>Element på statussidan för kundsynkronisering

För att se en lista över alla synkroniseringsåtgärder i Commerce headquarters gå till **Handel och detaljhandel \> Kunder \> Kundsynkroniseringsstatus**. I följande bild visas ett exempel på sidan **Kundsynkroniseringsstatus**.

![Sida för kundsynkroniseringsstatus i Commerce headquarters.](media/D365-Commerce-Customer-Mgmt-Audi-Async-Operations.png)

Listan med kundsynkroniseringsåtgärder till vänster om sidan **Kundsynkroniseringsstatus** innehåller som standard följande kolumner:

- Kanalnamn
- Kundkonto
- Asynkront kundkonto
- Tidsstämpel för åtgärd
- Kundsynkroniseringsstatus

Övre högra sidan visar kundkontoinformation, till exempel värdena **Kundkonto**, **Retail Async-åtgärd**, **Kundsynkroniseringsstatus** och **Senast kända fel**.

Avsnittet **Ändra beskrivning** innehåller en beskrivning av typen av kundhanteringsåtgärd som kördes (till exempel kundskapande, kontouppdatering eller synkroniseringsfel med detaljer).

Avsnittet **Kundattribut** innehåller ett rutnät som visar alla kundattribut, tillsammans med gamla och nya värden. Du kan redigera det här avsnittet om du vill ändra kundattributvärden för att åtgärda fel och sedan synkronisera det igen.
