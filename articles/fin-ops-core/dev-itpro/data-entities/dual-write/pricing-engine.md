---
title: Synkronisera på begäran med prissättningsmotorn Supply Chain Management
description: Detta ämne beskriver hur du använder prissättningsmotorn i Microsoft Dynamics 365 Supply Chain Management från Microsoft Dynamics 365 Sales.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 259bdd5f868945c3857b045fbd3cbd4fceb26951
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862231"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a>Synkronisera på begäran med prissättningsmotorn Supply Chain Management

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management inkluderar en prissättningsmotor för hantering av handelsavtal, prislistor, kundbonusprogram, erbjudanden och rabatter. Prissättningsmotorn använder komplexa regler för att fastställa det bästa priset för en given offert eller order. När du använder dubbelriktad skrivning använder du antingen statisk prissättning eller prissättningsmotorn från Supply Chain Management på sidorna **Offert** och **Order** i Microsoft Dynamics 365 Sales.

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>Använd prissättningsmotorn från Supply Chain Management i Sales

1. I Sales, gå till **Sales \> Order**.
1. Välj **Ny** för att skapa en ny order eller välj en befintlig order i listan **Mina order**.
1. Lägg till en ny orderrad.
1. Om du skapar en ny order väljer du **Prisorder** i åtgärdsfönstret. Om du uppdaterar en befintlig order väljer du **Beräkna om** i åtgärdsfönstret.
1. Följande kolumner fylls i automatiskt:

    - Detaljbelopp
    - Rabatt i %
    - Rabatt
    - Belopp före frakt
    - Fraktbelopp
    - Summa moms
    - Totalt belopp

> [!NOTE]
> En liknande process tillämpas när du skapar offerter.

## <a name="how-it-works"></a>Hur det fungerar

När du skapar en order i Försäljning blir den ordern omedelbart synkroniserad till Supply Chain Management genom att använda de värden du angett i Försäljning. När du väljer **Prisorder** eller **Prisoffert** i Försäljning beräknar Supply Chain Management priset för varje orderrad och den totala ordern, baserat på handelsavtalsreglerna som definieras i Supply Chain Management. De nya, beräknade värdena synkroniseras sedan tillbaka till Försäljning.

## <a name="set-trade-agreement-evaluation-options-in-supply-chain-management"></a>Ange alternativ för utvärdering av handelsavtal i Supply Chain Management

Du kan konfigurera Supply Chain Management till att antingen följa eller ignorera handelsavtal när det beräknar priset på en order som skapats i Försäljning. För att konfigurera detta alternativ, följ dessa steg.

1. Logga in i din miljö för Supply Chain Management.
1. Gå till **Kundreskontra \> Inställningar \> Parametrar för kundreskontra**.
1. På fliken **Priser** > på snabbfliken **handelsavtalsutvärdering** lägger du till eller tar bort raden för policyn **Manuell inmatning** efter behov. Att denna policy finns eller inte styr om prissättningsmotorn för Supply Chain Management automatiskt ska gå före det försäljningspris som angetts i Försäljning.

    - Om policyn **Manuell inmatning** *inte* finns med i konfigurationen för **handelsavtalsutvärdering** är Supply Chain Management prismallen. När en användare väljer **Prisorder** eller **Prisoffert** i åtgärdsfönstret i Försäljning anropas prissättningsmotorn för Supply Chain Management och det försäljningspris som angetts i Försäljning skrivs över, såvida det inte motsvarar det försäljningspris som beräknas i Supply Chain Management.
    - Om policyn **Manuell inmatning** *finns med* i konfigurationen för **handelsavtalsutvärdering** är Försäljning prismallen. Försäljningspriset som angetts i Försäljning hindras från att skrivas över automatiskt när en användare väljer **Prisorder** eller **Prisoffert** i åtgärdsfönstret i Försäljning.
    - Orderrader och offertrader som har ett värde för **pris per enhet** och/eller **rabatt** som uppgår till *0* (noll) i Försäljning behandlas som ett specialfall. Om ett relevant handelsavtalspris är tillgängligt kommer Supply Chain Management *alltid* att tillämpa det på dessa fält, oavsett inställningarna för **Utvärdering av handelsavtal**.

    Ett exempel på dessa fall finns i scenarierna som följer.

## <a name="example-scenario-1-trade-agreement-evaluation-without-the-manual-entry-option"></a>Exempelscenario 1: Utvärdering av handelsavtal utan alternativet Manuell inmatning

I detta scenario inkluderar konfigurationen **Handelsavtalsutvärdering** i Supply Chain Management *inte* policyn **Manuell inmatning**. En Försäljningsanvändare registrerar en orderrad som har ett försäljningspris som inte är noll i Försäljning, och inget försäljningspris har definierats för artikeln i Supply Chain Management.

1. I Försäljning skapar en användare en orderrad som har ett värde för **Pris per enhet** på 1 USD.
1. Orderraden synkroniseras till Supply Chain Management med försäljningspriset 1 USD.
1. I Försäljning väljer användaren **Prisorder** i åtgärdsfönstret.
1. Supply Chain Management söker efter relevanta priser och rabatter och beräknar sedan summorna. Eftersom artikeln inte har något försäljningspris i Supply Chain Management uppdaterar beräkningen raden så att den har ett försäljningspris som 0 USD.
1. Det nya försäljningspriset för raden synkroniseras tillbaka till Försäljning.
1. Resultatet är en orderrad i Försäljning som har ett försäljningspris på 0 USD.

## <a name="example-scenario-2-trade-agreement-evaluation-with-the-manual-entry-option"></a>Exempelscenario 2: Utvärdering av handelsavtal med alternativet Manuell inmatning

I detta scenario *inkluderar* konfigurationen **Handelsavtalsutvärdering** i Supply Chain Management policyn **Manuell inmatning**. En Försäljningsanvändare registrerar en orderrad som har ett försäljningspris som inte är noll i Försäljning. Supply Chain Management innehåller ett handelsavtal som anger ett försäljningspris på 2 USD för den beställda artikeln.

1. I Försäljning skapar en användare en orderrad för en artikel som har ett värde för **Pris per enhet** på 1 USD.
1. Orderraden synkroniseras till Supply Chain Management med försäljningspriset 1 USD.
1. I Försäljning väljer användaren **Prisorder** i åtgärdsfönstret.
1. Eftersom konfigurationen för **handelsavtalsutvärdering** i Supply Chain Management innehåller policyn **Manuell inmatning** ändras inte försäljningspriset, även om ett tillämpligt handelsavtal anger ett annat försäljningspris.
1. Försäljningspriset förblir oförändrat i Försäljning och i Supply Chain Management.

## <a name="example-scenario-3-trade-agreement-evaluation-for-an-item-that-has-a-sales-price-of-zero-in-sales"></a>Exempelscenario 3: Utvärdering av handelsavtal för en artikel som har ett försäljningspris på noll i Försäljning

I detta scenario *inkluderar* konfigurationen **Handelsavtalsutvärdering** i Supply Chain Management policyn **Manuell inmatning**. En Försäljningsanvändare registrerar en orderrad som har försäljningspriset 0 (noll) i Försäljning. Supply Chain Management innehåller ett handelsavtal som anger ett försäljningspris på 2 USD för en beställd artikel.

1. I Försäljning skapar en användare en orderrad som har värdet **Pris per enhet** på 0 USD och ett värde för **Radrabatt** på 0 USD.
1. Orderraden synkroniseras till Supply Chain Management med försäljningspriset 0 USD.
1. Eftersom det har mottagit en orderrad med försäljningspriset 0 (noll) anropar Supply Chain Management sin prissättningsmotor, även om alternativet **Manuell inmatning** är aktiverat. Prissättningsmotorn returnerar försäljningspriset på 2 USD som upprättats i handelsavtalet och uppdaterar orderraden i Supply Chain Management.
1. Det uppdaterade försäljningspriset är ännu inte synkroniserat med orderraden i Försäljning.
1. I Försäljning väljer användaren **Prisorder** i åtgärdsfönstret.
1. Orderraden i Supply Chain Management behåller försäljningspriset på 2 USD, som nu synkroniseras tillbaka till Försäljning. Därför uppdateras värdet **Pris per enhet** för orderraden i Försäljning från pris 0 USD till 2 USD.
1. I Försäljning anger användaren ett nytt värde för **Radrabatt** på 0,50 USD. Försäljning beräknar nu att värdet för **Utökat belopp** för raden är 1,50 USD.
1. Orderraden synkroniseras till Supply Chain Management med värdet 0,50 USD för **Radrabatt**.
1. I Försäljning väljer användaren **Prisorder** i åtgärdsfönstret.
1. Inga priser eller rabatter ändras för orderraden i Försäljning.

## <a name="limitations"></a>Begränsningar

När kolumnerna i Sales fylls i gäller följande begränsningar:

- Inställningarna för avgifter och debiteringar i Supply Chain Management replikeras inte i Sales.
- Priserna anser inte vara särskilda detaljhandelspris som är angivna i kolumnen **butikskanal** på sidan försäljningsorderrad i Supply Chain Management.
- Rabatter som definieras i avsnittet **Hantering av handelsavdrag** i Supply Chain Management beaktas inte.
- Priser tar inte hänsyn till försäljningsavtal.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
