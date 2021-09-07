---
title: Synkronisera på begäran med prissättningsmotorn Supply Chain Management
description: I det här avsnittet beskrivs hur du använder prissättningsmotorn Microsoft Dynamics 365 Supply Chain Management från Dynamics 365 Sales.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c9f94ec35ebed5a14252377fb543de09cb994ffd
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/24/2021
ms.locfileid: "7416190"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a>Synkronisera på begäran med prissättningsmotorn Supply Chain Management

[!include [banner](../../includes/banner.md)]



Microsoft Dynamics 365 Supply Chain Management inkluderar en prissättningsmotor för hantering av handelsavtal, prislistor, kundbonusprogram, erbjudanden och rabatter. Prissättningsmotorn använder komplexa regler för att fastställa det bästa priset för en given offert eller order. När du använder dubbelriktad skrivning använder du antingen statiska priser eller prissättningsmotorn från Dynamics 365 Supply Chain Management på sidorna offert och order i Dynamics 365 Sales.

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>Använd prissättningsmotorn från Supply Chain Management i Sales

1. I Sales, gå till **Sales \> Order**.
2. Välj **Ny** för att skapa en ny order eller välj en befintlig order i listan **Mina order**.
3. Lägg till en ny orderrad.
4. Om du skapar en ny order väljer du **Prisorder** i åtgärdsfönstret. Om du uppdaterar en befintlig order väljer du **Beräkna om** i åtgärdsfönstret.

    Följande kolumner fylls i automatiskt:

    + Detaljbelopp
    + Rabatt i %
    + Rabatt
    + Belopp före frakt
    + Fraktbelopp
    + Summa moms
    + Totalt belopp
    
5. För att säkerställa att systemet beaktar handels- och försäljningsavtal vid beräkningen av priset:
    1. Navigera till din miljö för Supply Chain Management.
    2. Gå till **Kundreskontra \> Inställningar \> Parametrar för kundreskontra**.
    3. Klicka på fliken **priser** i navigeringsfältet på sidan.
    4. Under snabbfliken **Utvärdering av handelsavtal** avmarkerar du alternativet **manuell inmatning**.

## <a name="how-it-works"></a>Hur det fungerar

När du väljer **prisorder** i Sales anropar funktionen **summor** på fliken **försäljningsorder \> vy** i Supply Chain Management anropas för tillhörande försäljningsorder. Värdena i ordersumman i Sales används för att fylla i motsvarande kolumner i Supply Chain Management.

När försäljningsordersumman beräknas i Supply Chain Management., evaluerar beräkningen de befintliga handelsavtalen och försäljningsavtalen för kunden och de produkter som anges i försäljningsordern. Denna information används för att beräkna summorna. När **prisorder** har valts visar Sales automatiskt alla inställningar som har gjorts i hanteringen av Supply Chain Management.

## <a name="limitations"></a>Begränsningar

När kolumnerna i Sales fylls i gäller följande begränsningar:

+ Inställningarna för avgifter och debiteringar i Supply Chain Management replikeras inte i Sales.
+ Priserna anser inte vara särskilda detaljhandelspris som är angivna i kolumnen **butikskanal** på sidan försäljningsorderrad i Supply Chain Management.
+ Rabatter som definieras i avsnittet **Hantering av handelsavdrag** i Supply Chain Management beaktas inte.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]