---
title: Konfigurera godkännandesteg i ett arbetsflöde
description: I det här avsnittet beskrivs hur du konfigurerar egenskaperna för ett godkännandesteg.
author: sericks007
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192161
ms.assetid: 8b478e3d-d6b4-403b-aae0-f639a71ca36c
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5bd5300a061e12ccabdea83c20863c95e15fe19
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180061"
---
# <a name="configure-approval-steps-in-a-workflow"></a>Konfigurera godkännandesteg i ett arbetsflöde

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar egenskaperna för ett godkännandesteg.

Högerklicka på godkännandesteget och klicka sedan på **Egenskaper** för att öppna sidan **Egenskaper**, om du vill konfigurera ett godkännandesteg i arbetsflödesredigeraren. Använd sedan följande procedurer när du vill konfigurera egenskaperna för godkännandesteget.

## <a name="name-the-step"></a>Ange ett namn på steget
Följ dessa steg när du vill ange ett namn för godkännandesteget.

1. Klicka på **Grundinställningar** i det vänstra fönstret.
2. Ange ett unikt namn för godkännandesteget i fältet **Namn**.

## <a name="enter-a-subject-line-and-instructions"></a>Ange en ämnesrad och instruktioner

Du måste ange en ämnesrad och instruktioner för användare som har tilldelats godkännandesteget. Om du till exempel konfigurerar ett godkännandesteg för inköpsrekvisitioner kan användaren som tilldelats steget se ämnesraden och instruktionerna på sidan **Inköpsrekvisitioner**. Ämnesraden visas i ett meddelandefält på sidan. Användaren kan sedan klicka på ikonen i meddelandefältet för att läsa instruktionerna. Följ dessa steg när du vill ange en ämnesrad och instruktioner.

1. Klicka på **Grundinställningar** i det vänstra fönstret.
2. Ange ämnesraden i fältet **Ämne för arbetsartikel**.
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

## <a name="assign-the-approval-step"></a>Tilldela godkännandesteget

Gör på följande sätt när du vill ange vem som ska tilldelas godkännandesteget.

1. Klicka på **Tilldelning** i det vänstra fönstret.
2. I fliken **Tilldelningstyp** väljer du ett av alternativen i följande register, och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 3.

    <table>
    <thead>
    <tr>
    <th>Alternativ</th>
    <th>Användare som tilldelas godkännandesteget</th>
    <th>Ytterligare steg</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Deltagare</td>
    <td>Användare som tilldelas en specifik grupp eller roll</td>
    <td>
    <ol>
    <li>Välj <strong>Deltagare</strong> i fliken <strong>Rollbaserad</strong> i listan <strong>Deltagartyp</strong> innan du väljer den grupp- eller rolltyp som du vill tilldela steget.</li>
    <li>Välj den grupp eller roll i listan <strong>Deltagare</strong> som du vill tilldela steget.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Hierarki</td>
    <td>Användare i en specifik organisationshierarki</td>
    <td>
    <ol>
    <li>Välj <strong>Hierarki</strong> innan du går vidare och väljer fliken <strong>Hierarkival</strong> i listan <strong>Hierarkityp</strong> och väljer den hierarkityp som du vill tilldela steget.</li>
    <li>Systemet måste hämta ett intervall med användarnamn i hierarkin. Dessa namn representerar användare som kan tilldelas steget. Följ dessa steg för att ange start- och slutpunkt för det intervall användarnamn som systemet hämtar: <ol>
    <li>Markera en person i listan <strong>Starta från</strong> för att ange startpunkten.</li>
    <li>Klicka på <strong>Lägg till villkor</strong> för att ange slutpunkten. Ange därefter ett villkor som avgör var någonstans i hierarkin som systemet slutar att hämta namn.</li>
    </ol>
    </li>
    <li>I fliken <strong>Hierarkialternativ</strong> väljer du de användare i intervallet som ska tilldelas steget: <ul>
    <li><strong>Tilldela samtliga hämtade användare</strong> – Steget tilldelas alla användare i intervallet.</li>
    <li><strong>Tilldela endast till senast hämtade användare</strong> – Steget tilldelas endast den senaste användaren i intervallet.</li>
    <li><strong>Exkludera användare med följande villkor</strong> – Steget har inte tilldelats till någon användare i intervallet som uppfyller ett visst villkor. Klicka på <strong>Lägg till villkor</strong> för att ange villkoret.</li>
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
    <li>Listan <strong>Tillgängliga användare</strong> innehåller alla systemanvändare. Markera de användare som ska tilldelas steget och flytta sedan dessa till listan <strong>Markerade användare</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. I fliken **Tidsgräns**, i fältet **Tidslängd**, anger du hur mycket tid användaren har på sig att vidta åtgärder/svara på dokument som når godkännandesteget. Välj ett av följande alternativ:

    - **Timmar** – Ange antalet timmar som användaren har på sig att svara. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    - **Dagar** – Ange antalet dagar som användaren har på sig att svara. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    - **Veckor** – Ange antalet veckor som användaren har på sig att svara.
    - **Månader –** – Välj dag och vecka då användaren senast måste svara. Du kanske till exempel vill att användaren ska svara senast på fredagen i den tredje veckan i månaden.
    - **År** – Välj dag, vecka och månad då användaren senast måste svara. Du kanske till exempel vill att användaren ska svara senast på fredagen i den tredje veckan i december.

    Om användaren inte vidtar åtgärder för dokumentet inom den tilldelade tiden, är dokumentet försenat. Ett dokument som försenas eskaleras, baserat på de alternativ som du väljer i avsnittet **Eskalering** på sidan.

4. Om du har tilldelat godkännandesteget till flera användare eller grupper av användare, välj då ett av följande alternativ i fliken **Slutförandepolicy**:

    - **Enskild godkännare** – Den åtgärd som tillämpas på dokumentet avgörs av den första personen som svarar. Till exempel har Sam skickat in en utgiftsrapport på 15 000 dollar. Utgiftsrapporten tilldelas för närvarande Sue, Jo och Bill. Om Sue är den första personen som svarar på dokumentet, är det hon som bestämmer vilken åtgärd som ska vidtas. Om Sue avvisar dokumentet, avslås det och skickas tillbaka till Sam. Om Sue godkänner dokumentet, skickas det vidare till Ann för godkännande.

        ![Arbetsflöde med en godkännandeprocess](./media/workflow_multipleusersinstep.gif)

    - **Majoritet av godkännare** – Den åtgärd som tillämpas på dokumentet avgörs när majoriteten av godkännarna har svarat. Till exempel har Sam skickat in en utgiftsrapport på 15 000 dollar. Utgiftsrapporten tilldelas för närvarande Sue, Jo och Bill. Om Sue och Jo är de första två godkännarna som svarar, tillämpas den åtgärd de vidtar på dokumentet.

        - Om Sue godkänner dokumentet men Jo avvisar det, avslås dokumentet och skickas tillbaka till Sam.
        - Om både Sue och Jo godkänner dokumentet, skickas det till Ann för godkännande.

    - **Procent av godkännare** – Den åtgärd som tillämpas på dokumentet avgörs när en viss procent av godkännarna har svarat. Till exempel har Sam skickat in en utgiftsrapport på 15 000 dollar. Utgiftsrapporten tilldelas för närvarande Sue, Jo och Bill, och du har angett **50** som procentandel. Om Sue och Jo och är de två första godkännarna som svarar, används den åtgärd som de vidtar på dokumentet eftersom de uppfyller kravet på 50 procent av godkännarna.

        - Om Sue godkänner dokumentet men Jo avvisar det, avslås dokumentet och skickas tillbaka till Sam.
        - Om både Sue och Jo godkänner dokumentet, skickas det till Ann för godkännande.

    - **Alla godkännare** – Alla godkännare måste godkänna dokumentet. I annat fall kan inte arbetsflödet fortsätta. Till exempel har Sam skickat in en utgiftsrapport på 15 000 dollar. Utgiftsrapporten tilldelas för närvarande Sue, Jo och Bill. Om Sue och Jo godkänner dokumentet men Bill avvisar det, avslås dokumentet och skickas tillbaka till Sam. Om Sue, Jo och Bill alla godkänner dokumentet, skickas det till Ann för godkännande.

## <a name="specify-when-the-approval-step-is-required"></a>Ange när godkännandesteget krävs

Du kan ange när godkännandesteget krävs. Godkännandesteget kan alltid krävas, eller också kan det krävas endast om specifika villkor uppfylls.

### <a name="the-approval-step-is-always-required"></a>Godkännandesteget krävs alltid

Följ dessa steg om godkännandesteget alltid krävs.

1. Klicka på **Villkor** i det vänstra fönstret.
2. Välj alternativet **Kör alltid det här steget**.

### <a name="the-approval-step-is-required-in-specific-conditions"></a>Godkännandesteget krävs under vissa förhållanden

Godkännandesteget som du konfigurerar kanske endast krävs då specifika villkor uppfylls. Om du till exempel konfigurerar ett godkännandesteg för ett inköpsrekvisitionsarbetsflöde, kan du tillämpa att godkännandesteget endast inträffar om inköpsrekvisitionens belopp överstiger 10 000 dollar. Följ dessa steg för att ange när godkännandesteget krävs.

1. Klicka på **Villkor** i det vänstra fönstret.
2. Välj alternativet **Kör bara det här steget när följande villkor uppfylls**.
3. Ange ett villkor.
4. Ange eventuellt ytterligare villkor som krävs.
5. Följ dessa steg för att bekräfta att de villkor som du har angett har ställts in korrekt:

    1. Klicka på **Ja**.
    2. På sidan **Testa arbetsflödesvillkor**, i avsnittet **Testa arbetsflödesvillkoret**, markerar du en post.
    3. Klicka på **Ja**. Systemet utvärderar posten i syfte att avgöra om den uppfyller villkoren som du angett.
    4. När du vill återgå till sidan **Egenskaper** klickar du på **OK** eller på **Avbryt**.

## <a name="specify-what-happens-when-the-document-is-overdue"></a>Ange vad som ska hända när dokumentet är försenat

Om en användare inte vidtar åtgärder för ett dokument inom den tilldelade tiden, är dokumentet försenat. Ett dokument som är försenat kan eskaleras eller automatiskt tilldelas till en annan användare för godkännande. Följ dessa steg för att eskalera dokumentet om det är försenat.

1. Klicka på **Eskalering** i det vänstra fönstret.
2. Markera kryssrutan **Använd eskaleringsväg** om du vill skapa en eskaleringsväg. Systemet tilldelar automatiskt dokumentet till de användare som listats i eskaleringsvägen. Till exempel representerar följande register en eskaleringsväg.

    | Sekvens | Eskaleringsväg      |
    |----------|----------------------|
    | 1        | Tilldela till: Donna     |
    | 2        | Tilldela till: Erin      |
    | 3        | Slutlig åtgärd: Avvisa |

    I detta scenario tilldelar systemet det försenade dokumentet till Donna. Om Donna inte svarar inom angiven tidsperiod, tilldelar systemet dokumentet till Erin. Om Erin inte svarar inom angiven tidsperiod, avslår systemet dokumentet.

3. Klicka på **Lägg till eskalering** för att lägga till en användare i eskaleringsvägen. I fliken **Tilldelningstyp** väljer du ett av alternativen i följande register och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 4.

    <table>
    <thead>
    <tr>
    <th>Alternativ</th>
    <th>Användare som dokumentet eskaleras till</th>
    <th>Ytterligare steg</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Hierarki</td>
    <td>Användare i en specifik organisationshierarki</td>
    <td>
    <ol>
    <li>Välj <strong>Hierarki</strong> innan du går vidare och väljer fliken <strong>Hierarkival</strong> i listan <strong>Hierarkityp</strong> och därefter den hierarkityp som du vill eskalera dokumentet till.</li>
    <li>Systemet måste hämta ett intervall med användarnamn i hierarkin. Dessa namn representerar användare som dokumentet kan eskaleras till. Följ dessa steg för att ange start- och slutpunkt för det intervall användarnamn som systemet hämtar: <ol>
    <li>Markera en person i listan <strong>Starta från</strong> för att ange startpunkten.</li>
    <li>Klicka på <strong>Lägg till villkor</strong> för att ange slutpunkten. Ange därefter ett villkor som avgör var någonstans i hierarkin som systemet slutar att hämta namn.</li>
    </ol>
    </li>
    <li>I fliken <strong>Hierarkialternativ</strong> väljer du de användare i intervallet som dokumentet ska eskaleras till: <ul>
    <li><strong>Tilldela till samtliga hämtade användare</strong> – Dokumentet eskaleras till alla användare i intervallet.</li>
    <li><strong>Tilldela endast till senast hämtade användare</strong> – Dokumentet eskaleras endast till den senaste användaren i intervallet.</li>
    <li><strong>Exkludera användare med följande villkor</strong> – Dokumentet har inte eskalerats till någon användare i intervallet som uppfyller ett visst villkor. Klicka på <strong>Lägg till villkor</strong> för att ange villkoret.</li>
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
    <li>Listan <strong>Tillgängliga användare</strong> innehåller alla användare. Markera de användare som dokumentet ska eskaleras till, och flytta sedan dessa till listan <strong>Markerade användare</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. I fliken **Tidsgräns**, i fältet **Tidslängd**, anger du hur mycket tid som användaren har på sig att vidta åtgärder/svara på dokument som når godkännandesteget. Välj ett av följande alternativ:

    - **Timmar** – Ange antalet timmar som användaren har på sig att svara. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    - **Dagar** – Ange antalet dagar som användaren har på sig att svara. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    - **Veckor** – Ange antalet veckor som användaren har på sig att svara.
    - **Månader –** – Välj dag och vecka då användaren senast måste svara. Du kanske till exempel vill att användaren ska svara senast på fredagen i den tredje veckan i månaden.
    - **År** – Välj dag, vecka och månad då användaren senast måste svara. Du kanske till exempel vill att användaren ska svara senast på fredagen i den tredje veckan i december.

5. Upprepa steg 3 och 4 för varje användare som ska läggas till i eskaleringsvägen. Du kan ändra alla användarnas ordningsföljd.
6. Om användarna i eskaleringsvägen inte svarar inom den tillåtna tidsperioden, kommer automatiska åtgärder att vidtas för dokumentet. Om du vill ange den åtgärd som systemet ska vidta, välj då raden **Åtgärd** och sedan en åtgärd i fliken **Slutåtgärd**.
