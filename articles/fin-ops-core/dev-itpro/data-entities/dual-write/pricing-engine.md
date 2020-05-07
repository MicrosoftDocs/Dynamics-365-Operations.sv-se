---
title: Synkronisera med Dynamics 365 Supply Chain Management prissättningsmotorn på begäran
description: I det här avsnittet beskrivs hur du använder prissättningsmotorn Microsoft Dynamics 365 Supply Chain Management från Dynamics 365 Sales.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 5ffc0358ff58b2a05aa84b4467a27d88b5e1ec42
ms.sourcegitcommit: 984604fd651d74aa49a2d7513f096faaf49f9f27
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/18/2020
ms.locfileid: "3270346"
---
# <a name="sync-with-the-dynamics-365-supply-chain-management-pricing-engine-on-demand"></a>Synkronisera med Dynamics 365 Supply Chain Management prissättningsmotorn på begäran

[!include [banner](../../includes/banner.md)]



Microsoft Dynamics 365 Supply Chain Management inkluderar en prissättningsmotor för hantering av handelsavtal, prislistor, kundbonusprogram, erbjudanden och rabatter. Prissättningsmotorn använder komplexa regler för att fastställa det bästa priset för en given offert eller order. När du använder dubbelriktad skrivning använder du antingen statiska priser eller prissättningsmotorn från Dynamics 365 Supply Chain Management på sidorna offert och order i Dynamics 365 Sales.

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>Använd prissättningsmotorn från Supply Chain Management i Sales

1. I Sales, gå till **Sales \> Order**.
2. Välj **Ny** för att skapa en ny order eller välj en befintlig order i listan **Mina order**.
3. Lägg till en ny orderrad.
4. Om du skapar en ny order väljer du **Prisorder** i åtgärdsfönstret. Om du uppdaterar en befintlig order väljer du **Beräkna om** i åtgärdsfönstret.

    Följande fält fylls i automatiskt:

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

När du väljer **prisorder** i Sales anropar funktionen **summor** på fliken **försäljningsorder \> vy** i Supply Chain Management anropas för tillhörande försäljningsorder. Värdena i ordersumman i Sales används för att fylla i motsvarande fält i Supply Chain Management.

När försäljningsordersumman beräknas i Supply Chain Management., evaluerar beräkningen de befintliga handelsavtalen och försäljningsavtalen för kunden och de produkter som anges i försäljningsordern. Denna information används för att beräkna summorna. När **prisorder** har valts visar Sales automatiskt alla inställningar som har gjorts i hanteringen av Supply Chain Management.

## <a name="limitations"></a>Begränsningar

När fälten i Sales fylls i gäller följande begränsningar:

+ Inställningarna för avgifter och debiteringar i Supply Chain Management replikeras inte i Sales.
+ Priserna anser inte vara särskilda detaljhandelspris som är angivna i fältet **butikskanal** på sidan försäljningsorderrad i Supply Chain Management.
+ Rabatter som definieras i avsnittet **Hantering av handelsavdrag** i Supply Chain Management beaktas inte.
