---
title: Visa semestersaldon i körningsgränssnittet för produktionsgolvet
description: Denna artikel innehåller ett exempelscenario som visar hur du konfigurerar Microsoft Dynamics 365 Supply Chain Management så att detta använder lönestatistik för att ge medarbetare en översikt över sina semestersaldon för innevarande år.
author: johanhoffmann
ms.date: 04/22/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-04-22
ms.dyn365.ops.version: 10.0.XX
ms.openlocfilehash: 2a6b6f52bfa7539b7c9bb5841536b0d564d0274c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852285"
---
# <a name="show-vacation-balances-in-the-production-floor-execution-interface"></a>Visa semestersaldon i körningsgränssnittet för produktionsgolvet

[!include [banner](../includes/banner.md)]

Denna artikel innehåller ett exempelscenario som visar hur du konfigurerar Microsoft Dynamics 365 Supply Chain Management så att detta använder lönestatistik för att ge varje medarbetare en översikt över sina semestersaldon för innevarande år. Medarbetarna kan se sina semestersaldon i dialogrutan **Min dag** i gränssnittet för körningsgränssnittet för produktionsgolvet.

I detta scenario används den danska semesterlagen, där semesteråret gäller från den 1 september till den 31 augusti. I det här scenariot har ditt företag anställt en ny medarbetare och beviljar den medarbetaren ett saldo på 10 semesterdagar för resten av det aktuella semesteråret.

## <a name="turn-on-the-required-features"></a>Aktivera de nödvändiga funktionerna

För att köra det här scenariot måste du aktivera funktionen *Vyn "Min dag" för körningsgränssnittet för produktionsgolvet* i [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Information om hur du aktiverar den här och andra funktioner för gränssnittet för produktionsgolvskörning finns i [Konfigurera körningsgränssnittet för produktionsgolvet](production-floor-execution-configure.md).

## <a name="make-sample-data-available"></a>Gör exempeldata tillgängliga

Om du vill arbeta genom detta scenario med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats. Dessutom måste du välja den **USMF** juridiska personen innan du börjar.

## <a name="create-a-new-pay-type"></a>Skapa en ny lönetyp

Börja med att skapa en ny *lönetyp* som spårar medarbetares intjänade semesterdagar (vilket även kallas deras *semestersaldo*). Vanligtvis används lönetyper för att beräkna arbetares lön. Den lönetyp som du skapar här används dock för att beräkna ett saldo.

1. Gå till **Tid och närvaro \> Inställningar \> Lön \> Lönetyper**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.
1. På den nya raden anger du följande värden:

    - **Lönetyp:** *5151-1*
    - **Beskrivning:** *Räknare för semesterdagar för arbetare*
    - **Inkludera i export:** *Nej*

## <a name="update-the-pay-agreement"></a>Uppdatera löneavtal

I det här avsnittet redigerar du ett befintligt *löneavtal* genom att lägga till den nya lönetypen och konfigurera regler som definierar hur varje arbetares semestersaldo justeras när semesterdagar registreras.

1. Gå till **Tid och närvaro \> Inställningar \> Lön \> Löneavtal**.
1. Välj det löneavtal där du vill konfigurera semesterpolicyn. (Om du arbetar med standard USMF-exempeldata finns det bara ett löneavtal, *Man*.)
1. Kontrollera att det valda löneavtalet är giltigt för aktuellt datum. Om du arbetar med standard USMF-exempeldata, fältet **Till datum** för *Man* löneavtalet kan sättas till ett datum som ligger i det förflutna. Ändra värdet så att det blir ett år eller två senare, efter behov.
1. Klicka på **Avtalsrader** i åtgärdsfönstret.
1. På sidan **Löneavtalsrader** på snabbfliken **Översikt** ställ in följande värden i verktygsfältet:

    - I den första listrutan, välj **Måndag**.
    - I den andra listrutan väljer du **Frånvaro**.

1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.
1. Ställ in fältet **Lönetyp** på den lönetyp som du skapade för det här scenariot (*5151–1*) på den nya raden. Lämna alla andra fält inställda på sina standardvärden.
1. Medan den nya raden fortfarande är vald, på snabbfliken **Allmänt**, ange följande värden:

    - **Frånvarokod:** *Semester*
    - **Använd fast kvantitet:** *Ja*
    - **Konstant:** *-1*

1. I åtgärdsfönstret väljer du **Kopiera dag**.
1. I dialogrutan **Kopiera dag** ange följande värden:

    - **Tisdag**, **onsdag**, **torsdag** och **fredag:** *Ja*
    - **Skriva över:** *Ja*
    - **Frånvaro:** *Ja*

1. Välj **OK**.

## <a name="create-a-payroll-statistic-group"></a>Skapa lönestatistikgrupp

*Lönestatistikgrupper* för att konfigurera statistik för arbetares registreringar under en period. I det här scenariot ska du använda en lönestatistikgrupp för att beräkna antalet semesterdagar som medarbetare får under en semesterperiod. I Danmark körs semesterperioden från den 1 september till den 31 augusti.

1. Gå till **Tid och närvaro \> Inställningar \> Lön \> Lönestatistikgrupper**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.
1. På den nya raden anger du följande värden:

    - **Lönestatistikgrupp:** *VAC*
    - **Beskrivning:** *Semestersaldo*
    - **Överför:** *Nej*

1. Med den nya raden fortsatt vald väljer du **Inställningar** i åtgärdsfönstret.
1. I åtgärdsrutan på sidan **Inställningar** väljer du **Ny** för att lägga till en rad i rutnätet.
1. På nya rader, ange fältet **Lönetyp** till *5151-1*.
1. Markera och hålla ned (eller högerklicka) i fältet **Periodkod** och sedan välja **Visa detaljer**. Du kan nu konfigurera den periodkod som du ska tilldela det här fältet senare.
1. På sidan **Periodkod** väljer du i åtgärdsfönstret **Ny** för att lägga till en rad i rutnätet.
1. På den nya raden anger du följande värden:

    - **Periodkod:** *VacYear*
    - **Beskrivning:** *Semesterår*
    - **Frekvens:** *År*

1. Med den nya raden fortsatt vald väljer du **Generera perioder** i åtgärdsfönstret.
1. I dialogrutan **Generera perioder** anger du följande värden:

    - **Ange startdatum för perioden:** *1 september 2021*
    - **Periodens längd:** *5*

1. Välj **OK**.
1. Stäng sidan **Periodtyper** om du vill återgå till sidan **Lönestatistikgrupper**.
1. Ställ in fältet **Periodkod** till den periodtyp som du just skapade (*VacYear*).

## <a name="create-a-statistical-balance-setup"></a>Skapa inställning av statistisk balans

I det här avsnittet skapar du en *inställning av statistisk balans* som är länkad till lönestatistikgruppen som du skapade i föregående avsnitt. Senare ska du koppla den här inställningen för statistisk balans till vyn **Min dag** i körningsgränssnittet för produktionsgolvet. Vyn **Min dag** kan du sedan visa semestersaldon för lönetypen som har tilldelats den associerade lönestatistikgruppen.

1. Gå till **Tid och närvaro \> Inställningar \> Lön \> Inställning av statistisk balans**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.
1. På den nya raden anger du följande värden:

    - **Lönestatistikgrupp:** *VAC*
    - **Externt namn:** *Semestersaldo*
    - **Flex:** *Nej*

## <a name="create-a-manual-premium"></a>Skapa manuell bonus

*Manuell bonus* används normalt för att bevilja arbetare extra lön för extra arbete. I det här scenariot skapar du en manuell bonus som du kan använda för att konfigurera den ursprungliga semestersaldot för varje arbetare.

1. Gå till **Tid och närvaro \> Inställningar \> Lön \> Manuella bonusar**.
1. I åtgärdsfönstret väljer du **Ny** för att lägga till en post.
1. I den nya posten anger du följande värden:

    - **Bonus:** *VAC*
    - **Beskrivning:** *Justeringar av medarbetares semestersaldo*
    - **Lönetyp:** *5151-1*

## <a name="set-a-workers-initial-vacation-balance-and-adjust-it-by-one-day"></a>Ställa in en arbetares ursprungliga semestersaldo och justera det med en dag

Löneadministratörer använder sidan **Godkänn** om du vill granska och godkänna arbetares dagliga registreringar. I det här scenariot får du rollen administratör så att du kan konfigurera den ursprungliga semestersaldot för en arbetare och registrera semesterdagar som arbetaren tar.

1. Gå till **Tid och närvaro \> Granska och godkänn \> Godkänn**.
1. I dialogrutan **Godkänn** anger du följande fält:

    - **Godkännandegrupp** – Välj den godkännandegrupp som du tillhör. (Om du arbetar med standard USMF-exempeldata finns det bara en godkännandegrupp, *AdmMan*.)
    - **Visa hela gruppen, 1 dag** – Markera alternativet och ställ sedan in fältet till aktuellt datum.

1. Välj **OK**.
1. På sidan **Godkänn** visas en lista med poster som matchar dina kriterier. Välj den arbetare som du vill godkänna. Om du arbetar med standard USMF-exempeldata väljer du arbetare *000496* (*Christina Portra*).
1. Bevilja den valda arbetaren 10 semesterdagar:

    1. Med arbetaren fortsatt vald väljer du **Bonusrader** i åtgärdsfönstret.
    1. På sidan **Bonusrader** väljer du i åtgärdsfönstret **Ny** för att lägga till en rad i rutnätet.
    1. På den nya raden anger du följande värden:

        - **Bonus:** *VAC*
        - **Kvantitet:** *10*

    1. Stäng sidan **Bonusrader**.

1. Registrera på sidan **Godkänn** att arbetaren har använt en av sina semesterdagar på det aktuella datumet:

    1. Medan arbetaren fortfarande är vald, i den nedre delen av sidan, på fliken **Översikt**, välj **Ny** i verktygsfältet för att lägga till en rad i rutnätet.
    1. På den nya raden anger du följande värden:

        - **Journalregistreringstyp:** *Frånvaro*
        - **Referens:** *Semester*

    1. Välj **Överför** i verktygsfältet i den övre delen av sidan om du vill använda semestersaldot och beräkna avdraget.

## <a name="configure-the-production-floor-execution-interface-so-that-it-includes-the-my-day-dialog-box"></a>Konfigurera körningsgränssnittet för produktionsgolvet så att det inkluderar dialogrutan Min dag

I det här avsnittet lägger du till en knapp för **Min dag** i körningsgränssnittet för produktionsgolvet. Arbetarna kan sedan använda den här knappen för att öppna dialogrutan **Min dag**.

1. Gå till **Produktionskontroll \> Inställningar \> Tillverkningskörning \> Konfigurera körningsgränssnittet för produktionsgolvet**.
1. Välj en konfiguration som *Standard*.
1. Klicka på **Designflikar** i åtgärdsfönstret.
1. På sidan **Designflikar** i listfönstret, välj *Alla jobb* för att visa inställningarna för den fliken. Fältet **Huvudvy** ska nu visa ett värde på *Alla jobb*.
1. I åtgärdsfönstret väljer du **Redigera**.
1. På snabbfliken **Sekundärt verktygsfält** i kolumnen **Tillgängliga åtgärder**, välj **Min dag**. Välj sedan högerpilen för att flytta den till kolumnen **Valda åtgärder**.

## <a name="check-your-balance-in-the-production-floor-execution-interface"></a>Kontrollera saldot i körningsgränssnittet för produktionsgolvet

I det här avsnittet loggar du in på körningsgränssnittet för produktionsgolvet som den arbetare vars semestertid du ställt in tidigare. Du öppnar sedan dialogrutan **Min dag** för att visa ditt semestersaldo.

1. Gå till **Produktionskontroll \> Inställning \> Tillverkningskörning \> Körningsgränssnittet för produktionsgolvet**.
1. Om du uppmanas att välja en konfiguration väljer du den konfiguration som du ställt in tidigare i det här scenariot (*Standard*).
1. Logga in som den användare du ställt in tidigare i det här scenariot. Om du arbetar med standard USMF-exempeldata bör du kunna logga in genom att ange *123* i fältet **ID-bricka**. Denna ID-bricka tillhör Christina Portra.
1. Välj **Min dag** i det vänstra verktygsfältet.
1. Kontrollera avsnittet **Saldon** i dialogrutan. I det här avsnittet ska du nu visa att du har ett saldo på nio semesterdagar.
