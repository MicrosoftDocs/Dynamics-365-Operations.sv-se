---
title: Arkivera lagertransaktioner
description: I det här avsnittet beskrivs hur du arkiverar data för lagertransaktioner för att förbättra systemets prestanda.
author: sherry-zheng
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTransArchiveProcessForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: b740da1a8a349f4a1a80b41bf717c388fd3db0c0
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881842"
---
# <a name="archive-inventory-transactions"></a>Arkivera lagertransaktioner

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Med tiden fortsätter lagertransaktionsregistret (`InventTrans`) att växa och förbruka mer databasutrymme. Därför kommer frågeställningar som görs mot registret att gradvis bli besvarade. Det här ämnet beskriver användning av funktionen *arkiv för lagertransaktioner* för att arkivera data om lagertransaktioner för att förbättra systemets prestanda.

> [!NOTE]
> Endast ekonomiskt uppdaterade lagertransaktioner kan arkiveras i en vald stängd redovisningsperiod. För att kunna arkiveras måste ekonomiskt uppdaterade utgående lagertransaktioner ha utleveransstatus *Såld* och inkommande lagertransaktioner måste ha inleveransstatus *Inköpt* .

När du arkiverar lagertransaktioner flyttas alla relaterade transaktioner till `InventTransArchive` registret. Transaktioner för lagerutleverans och lagerinleverans arkiveras separat baserat på kombinationen av artikel-ID (`itemId`) och lagerdimension-ID (`inventDimId`) och de placeras i den sammanfattade utgåvan och de sammanfattade inleveranstransaktioner.

Om en `itemId` och `inventDimId` kombinationen bara innehåller en inleverans- eller utleveranstransaktion arkiveras inte transaktionen.

## <a name="turn-on-the-feature-in-your-system"></a>Aktivera funktionen i systemet

Om ditt system inte redan innehåller de funktioner som beskrivs i det här avsnittet, gå till [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktivera funktionen *arkiv för lagertransaktioner*. Observera att denna funktion inte kan inaktiveras när den väl har aktiverats.

## <a name="things-to-consider-before-you-archive-inventory-transactions"></a>Saker du bör tänka på innan du arkiverar lagertransaktioner

Innan du arkiverar lagertransaktioner bör du tänka på följande affärsscenarier eftersom de påverkas av operationen:

- När du granskar lagertransaktioner från relaterade dokument, till exempel inköpsorderrader, visas de som arkiverade. För att granska de arkiverade transaktionerna måste du gå till **Lagerhantering \> Periodiska uppgifter \> Rensa \> Arkiv lagertransaktioner**.
- Lagerstängning kan inte annulleras för arkiverade perioder. Innan du kan annullera en lagerstängning måste du återföra lagertransaktionsarkivet för den relevanta perioden.
- Standardkostnadskonvertering kan inte göras för arkiverade perioder. Innan du kan göra standardkostnadskonvertering måste du återföra lagertransaktionsarkivet för den relevanta perioden.
- Lagerrapporter som kommer från lagertransaktioner påverkas när du arkiverar lagertransaktioner. Dessa rapporter omfattar rapporten för lager åldersfördelning och lagervärderapporter.
- Lagerprognoser kan påverkas om de körs under tidshorisonten för arkiverade perioder.

## <a name="prerequisites"></a>Förutsättningar

Lagertransaktioner kan bara arkiveras under perioder där följande villkor uppfylls:

- Redovisningsperioden måste vara stängd.
- Lagerstängningen måste köras på eller efter till-perioddatumet för arkivet.
- Perioden måste vara minst ett år före arkivets från-perioddatum.
- Inga befintliga lageromberäkningar får finnas.

## <a name="archive-inventory-transactions"></a>Arkivera lagertransaktioner

Följ dessa steg för att arkivera inventeringstransaktioner.

1. Gå till **Lagerhantering** \> **Periodiska uppgifter** \> **Rensa** \> **Lagertransaktionsarkiv**.

    Sidan **Lagertransaktionsarkiv** visas och visar en lista med arkiverade processposter.

    ![Sidan lagertransaktionsarkiv](media/archive-inventory-empty.png "Sidan lagertransaktionsarkiv")

1. I åtgärdsfönstret, välj **Lagertransaktionsarkiv** om du vill skapa ett lagertransaktionsarkiv.
1. I dialogrutan **Lagertransaktionsarkiv** på snabbfliken **Parametrar** ange följande fält:

    - **Från datum i stängd redovisningsperiod** – Välj det tidigaste transaktionsdatumet som ska inkluderas i arkivet.
    - **Till datum i stängd redovisningsperiod** – Välj det senaste transaktionsdatumet som ska inkluderas i arkivet.

    ![Dialogrutan lagertransaktionsarkiv](media/archive-inventory-dates.png "Dialogrutan lagertransaktionsarkiv")

    > [!NOTE]
    > Endast perioder som uppfyller [kraven](#prerequisites) är tillgängliga för val.

1. På snabbfliken **Kör i bakgrunden** ställer du in batchbearbetningsinformation efter behov. Följ de vanligaste stegen för batchjobb i Microsoft Dynamics 365 Supply Chain Management.
1. Välj **OK**.
1. Du får ett meddelande som uppmanar dig att bekräfta att du vill fortsätta. Läs meddelandet noggrant och välj sedan **Ja** om du vill fortsätta.

    Du får ett meddelande om att dina lagertransaktioner arkivjobb har lagts till i batchkön. Jobbet börjar nu att arkivera lagertransaktioner från den valda perioden.

## <a name="view-archived-inventory-transactions"></a>Visa arkiverade lagertransaktioner

Sidan **lagertransaktionsarkiv** visar hela arkiveringshistoriken. Varje rad i rutnätet visar information som t.ex. datum då arkivet skapades, användaren som skapade det och dess status.

![Arkiveringshistorik på sidan en lagertransaktionsarkiv](media/archive-inventory-full.png "Arkiveringshistorik på sidan en lagertransaktionsarkiv")

Välj ett av följande värden i listrutan högst upp på sidan för att filtrera de arkiv som visas i rutnätet:

- **Aktiv** – Visa endast aktiva arkiv, inte återförda arkiv.
- **Alla** – Visa alla arkiv, både aktiva och återförda.

För varje arkiv i rutnätet finns följande information:

- **Aktiv** – En bockmarkering anger att arkivet är aktivt.
- **Från datum** – Datumet för den äldsta transaktionen som kan inkluderas i arkivet.
- **Till datum** – Datumet för den senaste transaktionen som kan inkluderas i arkivet.
- **Tidsplanerad av** – Användarkontot som skapade arkivet.
- **Utförd** – Datum då arkivet skapades.
- **Återför** – En bockmarkering indikerar att arkivet har återförts.
- **Stoppa aktuell uppdatering** – En bockmarkering anger att arkivet pågår, men att det har pausats.
- **Tillstånd** – Arkivets bearbetningsstatus. De möjliga värdena är *Väntar*, *Pågår* och *Slutförd*.

Verktygsfältet ovanför rutnätet innehåller följande knappar som du använder när du arbetar med ett valt arkiv:

- **Arkiverade transaktioner** – Visa fullständiga detaljer om det valda arkivet. Sidan **Arkiverade transaktioner** visar alla transaktioner i arkivet.

    ![Sidan Arkiverade transaktioner](media/archive-inventory-transactions.png "Sidan Arkiverade transaktioner")

    För att få mer information om en viss transaktion på sidan **Arkiverade transaktioner** markerar du den i rutnätet och väljer sedan **Information om arkiverade transaktioner**. Sidan **Information om arkiverade transaktioner** som visas kommer att visa information som redovisningsbokföring, relaterade redovisningsreferenser och ekonomiska dimensioner.

- **Göra paus i arkivering** – Pausa ett valt arkiv som bearbetas just nu. Pausen gäller bara efter det att arkiveringsuppgiften har genererats. Därför kan det ta en kort tid innan pausen börjar gälla. Om ett arkiv har pausats visas en bockmarkering i fältet **Stoppa aktuell uppdatering**.
- **Återuppta arkivering** – Återuppta bearbetning för ett valt arkiv som pausas just nu.
- **Återför** – Återför det valda arkivet. Du kan bara återföra ett arkiv om dess **Tillstånd** anges till *Slutförd*. Om ett arkiv har återställas visas en bockmarkering i fältet **återställa**.
