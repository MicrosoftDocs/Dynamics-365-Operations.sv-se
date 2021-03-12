---
title: Konfigurera manuella beslut i ett arbetsflöde
description: I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för ett manuellt beslut.
author: ChrisGarty
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d351facbce02355ddb4bdf91d43d9df561e4f3b5
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798863"
---
# <a name="configure-manual-decisions-in-a-workflow"></a>Konfigurera manuella beslut i ett arbetsflöde

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för ett manuellt beslut.

Högerklicka det manuella beslutet och klicka sedan på **Egenskaper** för att öppna sidan **Egenskaper** om du vill konfigurera ett manuellt beslut i arbetsflödesredigeraren. Använd sedan följande procedurer när du vill konfigurera egenskaperna för det manuella beslutet.

## <a name="name-the-decision"></a>Namnge beslutet

Följ dessa steg när du vill ange ett namn för det manuella beslutet.

1. Klicka på **Grundinställningar** i det vänstra fönstret.
2. Ange ett unikt namn för det manuella beslutet i fältet **Namn**.

## <a name="enter-a-subject-line-and-instructions"></a>Ange en ämnesrad och instruktioner

Du måste ange en ämnesrad och instruktioner för användare som är tilldelade det manuella beslutet. Om du till exempel konfigurerar ett beslut för inköpsrekvisitioner kan användaren som tilldelats beslutet se ämnesraden och instruktionerna på sidan **Inköpsrekvisitioner**. Ämnesraden visas i ett meddelandefält på sidan. Användaren kan sedan klicka på ikonen i meddelandefältet för att visa instruktionerna. Följ dessa steg när du vill ange en ämnesrad och instruktioner.

1. Klicka på **Grundinställningar** i det vänstra fönstret.
2. Ange ämnesraden i fliken **Instruktioner**, i fältet **Arbetsuppgift**.
3. Om du vill göra ämnesraden mer personlig kan du infoga platshållare. Platshållare ersätts med lämpliga data när ämnesraden visas för användarna. Följ dessa steg när du vill infoga en platshållare:

    1. Klicka på den plats i textrutan där platshållaren ska visas.
    2. Klicka på **Infoga platshållare**.
    3. Välj önskad platshållare i listan som visas.
    4. Klicka på **Infoga**.

4. Om du vill lägga till översättningar av ämnesraden följer du dessa steg:

    1. Klicka på **Översättningar**.
    2. Klicka på **Lägg till** på sidan som visas.
    3. I listan som visas väljer du det språk som du skriver texten i.
    4. I fältet **Översatt text** anger du texten.
    5. Om du vill anpassa texten kan du infoga platshållare enligt vad som beskrivs i steg 3.
    6. Klicka på **Stäng**.

5. I fältet **Arbetsuppgiftsinstruktioner** anger du instruktionerna.
6. Om du vill anpassa instruktionerna kan du infoga platshållare. Platshållare ersätts med lämpliga data när instruktionerna visas för användarna. Följ dessa steg när du vill infoga en platshållare:

    1. Klicka på den plats i textrutan där platshållaren ska visas.
    2. Klicka på **Infoga platshållare**.
    3. Välj önskad platshållare i listan som visas.
    4. Klicka på **Infoga**.

7. Om du vill lägga till översättningar av instruktionerna följer du dessa steg:

    1. Klicka på **Översättningar**.
    2. Klicka på **Lägg till** på sidan som visas.
    3. I listan som visas väljer du det språk som du skriver texten i.
    4. I fältet **Översatt text** anger du texten.
    5. Om du vill anpassa texten kan du infoga platshållare enligt vad som beskrivs i steg 6.
    6. Klicka på **Stäng**.

## <a name="specify-the-possible-outcomes-of-a-decision"></a>Ange möjliga resultat av ett beslut

Vanligtvis ställs en fråga till beslutsfattaren när ett dokument tilldelas till en beslutsfattare. Svaret på frågan är oftast **Ja** eller **Nej** eller **Sant** eller **Falskt**. Gör på följande sätt när du vill ange möjliga resultat av det manuella beslutet.

1. Klicka på **Grundinställningar** i det vänstra fönstret.
2. Ange namnet på resultatet eller alternativet i fliken **Resultat**, i fältet **Resultat 1**.
3. Följ dessa steg för att lägga till översättningar av resultaten:

    1. Klicka på **Översättningar**.
    2. Klicka på **Lägg till** på sidan som visas.
    3. I listan som visas väljer du det språk som du skriver texten i.
    4. I fältet **Översatt text** anger du texten.
    5. Klicka på **Stäng**.

4. Ange namnet på resultatet eller alternativet i fältet **Resultat 2**.
5. Följ dessa steg för att lägga till översättningar av resultaten:

    1. Klicka på **Översättningar**.
    2. Klicka på **Lägg till** på sidan som visas.
    3. I listan som visas väljer du det språk som du skriver texten i.
    4. I fältet **Översatt text** anger du texten.
    5. Klicka på **Stäng**.

## <a name="specify-when-notifications-are-sent"></a>Ange när meddelanden ska skickas

Du kan skicka meddelanden till andra när ett beslut har fattats, delegerats eller eskalerats. Följ dessa steg för att ange när meddelanden skickas och vem de skickas till.

1. Klicka på **Meddelanden** i det vänstra fönstret.
2. Markera kryssrutan bredvid händelserna som meddelandena ska skickas för:

    - **\[Val 1\]** – Den tilldelade användaren har valt **\[Val 1\]**.
    - **\[Val 2\]** – Den tilldelade användaren har valt **\[Val 2\]**.
    - **Delegera** – Den tilldelade användaren har delegerat beslutet till en annan användare.
    - **Eskalera** – Den tilldelade användaren har inte fattat beslutet inom angiven tid.

3. Välj raden för en händelse som du valde i steg 2.
4. Ange meddelandetexten i textrutan i fliken **Meddelandetext**.
5. Om du vill anpassa meddelandet kan du infoga platshållare. Platshållare ersätts med lämpliga data när meddelandet visas för användarna. Följ dessa steg när du vill infoga en platshållare:

    1. Klicka på den plats i textrutan där platshållaren ska visas.
    2. Klicka på **Infoga platshållare**.
    3. Välj önskad platshållare i listan som visas.
    4. Klicka på **Infoga**.

6. Om du vill lägga till översättningar av meddelandet följer du dessa steg:

    1. Klicka på **Översättningar**.
    2. Klicka på **Lägg till** på sidan som visas.
    3. I listan som visas väljer du det språk som du skriver texten i.
    4. I fältet **Översatt text** anger du texten.
    5. Om du vill anpassa texten kan du infoga platshållare enligt vad som beskrivs i steg 5.
    6. Klicka på **Stäng**.

7. Ange vem meddelandena ska skickas till i fliken **Mottagare**. I följande register väljer du ett av alternativen och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 8.

    <table>
    <thead>
    <tr>
    <th>Alternativ</th>
    <th>Meddelandemottagare</th>
    <th>Ytterligare steg</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Deltagare</td>
    <td>Användare som tilldelas en specifik grupp eller roll</td>
    <td>
    <ol>
    <li>Välj <strong>Deltagare</strong> i fliken <strong>Rollbaserad</strong> i listan <strong>Deltagartyp</strong> innan du väljer den grupp- eller rolltyp som du vill skicka meddelanden till.</li>
    <li>Välj den grupp som du vill skicka meddelanden till i listan <strong>Deltagare</strong>.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Användare av arbetsflöde</td>
    <td>Användarna i det aktuella arbetsflödet</td>
    <td>
    <ul>
    <li>När du har valt <strong>Användare av arbetsflöde</strong> i fliken <strong>Användare av arbetsflöde</strong> väljer du en användare som deltar i arbetsflödet i listan <strong>Användare av arbetsflöde</strong>.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Användare</td>
    <td>Specifika användare</td>
    <td>
    <ol>
    <li>Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</li>
    <li>Listan <strong>Tillgängliga användare</strong> innehåller alla användare. Markera de användare som du vill skicka meddelanden till, och flytta sedan dessa användare till listan <strong>Markerade användare</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. Upprepa stegen 3 till och med 7 för varje enskild händelse du valde i steg 2.

## <a name="assign-a-decision"></a>Tilldela ett beslut

Följ dessa steg för att ange vem som ska tilldelas ett manuellt beslut.

1. Klicka på **Tilldelning** i det vänstra fönstret.
2. I fliken **Tilldelningstyp** väljer du ett av alternativen i följande register, och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 3.

    <table>
    <thead>
    <tr>
    <th>Alternativ</th>
    <th>Användare som tilldelats beslutet</th>
    <th>Ytterligare steg</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Deltagare</td>
    <td>Användare som tilldelas en specifik grupp eller roll</td>
    <td>
    <ol>
    <li>Välj <strong>Deltagare</strong> och sedan fliken <strong>Rollbaserad</strong> i listan <strong>Deltagartyp</strong> för att välja den typ av grupp eller roll som du vill tilldela beslutet.</li>
    <li>Välj den grupp eller roll som du vill tilldela beslutet i listan <strong>Deltagare</strong>.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Hierarki</td>
    <td>Användare i en specifik organisationshierarki</td>
    <td>
    <ol>
    <li>Välj <strong>Hierarki</strong> innan du går vidare och väljer fliken <strong>Hierarkival</strong> i listan <strong>Hierarkityp</strong>, och sedan väljer den hierarkityp som du vill tilldela beslutet.</li>
    <li>Systemet måste hämta ett intervall med användarnamn i hierarkin. Dessa namn representerar användare som kan tilldelas beslutet. Följ dessa steg för att ange start- och slutpunkt för det intervall användarnamn som systemet hämtar: <ol>
    <li>Markera en person i listan <strong>Starta från</strong> för att ange startpunkten.</li>
    <li>Klicka på <strong>Lägg till villkor</strong> för att ange slutpunkten. Ange därefter ett villkor som avgör var någonstans i hierarkin som systemet slutar att hämta namn.</li>
    </ol>
    </li>
    <li>I fliken <strong>Hierarkialternativ</strong> väljer du de användare i intervallet som ska tilldelas steget: <ul>
    <li><strong>Tilldela samtliga hämtade användare</strong> – Beslutet tilldelas alla användare i spannet.</li>
    <li><strong>Tilldela endast till senast hämtade användare</strong> – Beslutet tilldelas endast den senaste användaren i intervallet.</li>
    <li><strong>Exkludera användare med följande villkor</strong> – Beslutet har inte tilldelats någon användare i spannet som uppfyller ett visst villkor. Klicka på <strong>Lägg till villkor</strong> för att ange villkoret.</li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Användare av arbetsflöde</td>
    <td>Användarna i det aktuella arbetsflödet</td>
    <td>
    <ul>
    <li>När du har valt <strong>Användare av arbetsflöde</strong> i fliken <strong>Användare av arbetsflöde</strong> väljer du en användare som deltar i arbetsflödet i listan <strong>Användare av arbetsflöde</strong>.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Användare</td>
    <td>Specifika användare</td>
    <td>
    <ol>
    <li>Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</li>
    <li>Listan <strong>Tillgängliga användare</strong> innehåller alla användare. Markera de användare som ska tilldelas beslutet och flytta sedan dessa till listan <strong>Markerade användare</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. I fliken **Tidsgräns**, i fältet **Tidslängd**, anger du hur mycket tid som användaren har på sig att fatta beslutet. Välj ett av följande alternativ:

    - **Timmar** – Ange antalet timmar som användaren har på sig att fatta beslutet. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    - **Dagar** – Ange antalet dagar som användaren har på sig att fatta beslutet. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    - **Veckor** – Ange antalet veckor som användaren har på sig att fatta beslutet.
    - **Månader –** – Välj dag och vecka då användaren senast måste svara. Du kanske till exempel vill att användaren ska fatta beslutet senast på fredagen i den tredje veckan i månaden.
    - **År –** – Välj dag, vecka och månad då användaren senast måste svara. Du kanske till exempel vill att användaren ska fatta beslutet senast på fredagen i den tredje veckan i december.

    Om användaren inte fattar beslutet inom den tilldelade tiden, är beslutet försenat. Ett beslut som är försenat eskaleras, baserat på de alternativ som du väljer i avsnittet **Eskalering** på sidan.

## <a name="specify-what-happens-when-a-decision-is-overdue"></a>Ange vad som ska hända när ett beslut är försenat

Om en användare inte fattar beslutet inom den tilldelade tiden, är beslutet försenat. Ett beslut som är försenat kan eskaleras eller automatiskt tilldelas en annan användare. Följ dessa steg för att eskalera beslutet om det är försenat.

1. Klicka på **Eskalering** i det vänstra fönstret.
2. Markera kryssrutan **Använd eskaleringsväg** om du vill skapa en eskaleringsväg. Systemet tilldelar automatiskt beslutet till de användare som listats i eskaleringsvägen. Till exempel representerar följande register en eskaleringsväg.

    | Sekvens | Eskaleringsväg            |
    |----------|----------------------------|
    | 1        | Tilldela till: Donna           |
    | 2        | Tilldela till: Erin            |
    | 3        | Slutgiltig åtgärd; \[Val 1\] |

    I detta scenario tilldelar systemet det försenade beslutet till Donna. Om Donna inte fattar beslutet inom angiven tidsperiod, tilldelar systemet beslutet till Erin. Om Erin inte fattar beslutet inom angiven tidsperiod, väljer systemet **\[Val 1\]** som beslut.

3. Klicka på **Lägg till eskalering** för att lägga till en användare i eskaleringsvägen. I följande register väljer du ett av alternativen och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 4.

    <table>
    <thead>
    <tr>
    <th>Alternativ</th>
    <th>Användare som beslutet eskaleras till</th>
    <th>Ytterligare steg</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Hierarki</td>
    <td>Användare i en specifik organisationshierarki</td>
    <td>
    <ol>
    <li>Välj <strong>Hierarki</strong> innan du går vidare och väljer fliken <strong>Hierarkival</strong> och, i listan <strong>Hierarkityp</strong>, den hierarkityp som du vill eskalera beslutet till.</li>
    <li>Systemet måste hämta ett intervall med användarnamn i hierarkin. Dessa namn representerar användare som beslutet kan eskaleras till. Följ dessa steg för att ange start- och slutpunkt för det intervall användarnamn som systemet hämtar: <ol>
    <li>Markera en person i listan <strong>Starta från</strong> för att ange startpunkten.</li>
    <li>Klicka på <strong>Lägg till villkor</strong> för att ange slutpunkten. Ange därefter ett villkor som avgör var någonstans i hierarkin som systemet slutar att hämta namn.</li>
    </ol>
    </li>
    <li>I fliken <strong>Hierarkialternativ</strong> väljer du de användare i intervallet som ska tilldelas beslutet: <ul>
    <li><strong>Tilldela till samtliga hämtade användare</strong> – Beslutet eskaleras till alla användare i intervallet.</li>
    <li><strong>Tilldela endast till senast hämtade användare</strong> – Beslutet eskaleras endast till den senaste användaren i intervallet.</li>
    <li><strong>Exkludera användare med följande villkor:</strong> – Beslutet eskaleras inte till någon användare i intervallet som uppfyller ett visst villkor. Klicka på <strong>Lägg till villkor</strong> för att ange villkoret.</li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Användare av arbetsflöde</td>
    <td>Användarna i det aktuella arbetsflödet</td>
    <td>
    <ul>
    <li>När du har valt <strong>Användare av arbetsflöde</strong> i fliken <strong>Användare av arbetsflöde</strong> väljer du en användare som deltar i arbetsflödet i listan <strong>Användare av arbetsflöde</strong>.</li>
    </ul>
    </td>
    </tr>
    <tr>
    <td>Användare</td>
    <td>Specifika användare</td>
    <td>
    <ol>
    <li>Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</li>
    <li>Listan <strong>Tillgängliga användare</strong> innehåller alla användare. Markera de användare som beslutet ska eskaleras till, och flytta sedan dessa till listan <strong>Markerade användare</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. I fliken **Tidsgräns**, i fältet **Tidslängd**, anger du hur mycket tid som användaren har på sig att fatta beslutet. Välj ett av följande alternativ:

    - **Timmar** – Ange antalet timmar som användaren har på sig att fatta beslutet. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    - **Dagar** – Ange antalet dagar som användaren har på sig att fatta beslutet. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    - **Veckor** – Ange antalet veckor som användaren har på sig att fatta beslutet.
    - **Månader –** – Välj dag och vecka då användaren senast måste svara. Du kanske till exempel vill att användaren ska fatta beslutet senast på fredagen i den tredje veckan i månaden.
    - **År –** – Välj dag, vecka och månad då användaren senast måste svara. Du kanske till exempel vill att användaren ska fatta beslutet senast på fredagen i den tredje veckan i december.

5. Upprepa steg 3 och 4 för varje användare som ska läggas till i eskaleringsvägen. Du kan ändra alla användarnas ordningsföljd.
6. Om användarna i eskaleringsvägen inte fattar beslutet inom den tillåtna tidsperioden, kommer systemet att fatta beslutet. Om du vill ange vilket alternativ som systemet väljer, välj då raden **Åtgärd** och sedan en åtgärd i fliken **Slutåtgärd**.

## <a name="set-a-time-limit"></a>Ange en tidsgräns

Följ dessa steg om beslutet måste fattas inom en viss tid.

> [!NOTE]
> De alternativ som du väljer i denna procedur åsidosätter alternativen som du valde i avsnitten **Tilldelning** och **Eskalering** på sidan.

1. Klicka på **Avancerade inställningar** i det vänstra fönstret.
2. Markera kryssrutan **Ange en tidsgräns för arbetsflödeselement**.
3. Ange när beslutet måste fattas i fältet **Tidslängd**. Välj ett av följande alternativ:

    - **Timmar** – Ange antalet timmar. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    - **Dagar** – Ange antalet dagar. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    - **Veckor** – Ange antalet veckor.
    - **Månader –** – Välj dag och vecka då beslutet senast måste vara fattat. Du kanske till exempel vill att beslutet ska vara fattat senast på fredagen i den tredje veckan i månaden.
    - **År –** – Välj dag, vecka och månad då beslutet senast måste vara fattat. Du kanske till exempel vill att beslutet ska vara fattat senast på fredagen i den tredje veckan i december.

4. Om tidsgränsen överskrids kommer systemet att fatta beslutet. I listan **Åtgärd** väljer du det alternativ som systemet ska vidta.
