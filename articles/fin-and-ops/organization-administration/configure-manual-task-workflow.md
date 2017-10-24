---
title: "Konfigurera en manuell uppgift i ett arbetsflöde"
description: "I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för en manuell uppgift."
author: sericks007
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 192191
ms.assetid: 27f1afde-ff26-4b6f-8c11-27ec49130bbb
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 98e25e1a132f0767b9c58334f177845c222c3863
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="configure-a-manual-task-in-a-workflow"></a>Konfigurera en manuell uppgift i ett arbetsflöde

[!include[banner](../includes/banner.md)]


I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för en manuell uppgift.

Högerklicka uppgiften och klicka sedan på **Egenskaper** för att öppna sidan **Egenskaper** om du vill konfigurera en manuell uppgift i arbetsflödesredigeraren. Använd sedan följande procedurer när du vill konfigurera egenskaperna för den manuella uppgiften.

## <a name="name-the-task"></a>Ange ett namn på uppgiften
Följ dessa steg när du vill ange ett namn för den manuella uppgiften.

1.  Klicka på **Grundinställningar** i det vänstra fönstret.
2.  I fältet **Namn** anger du ett unikt namn för uppgiften.

## <a name="enter-a-subject-line-and-instructions"></a>Ange en ämnesrad och instruktioner
Du måste ange en ämnesrad och instruktioner för användare som är tilldelade till uppgiften. Om du till exempel konfigurerar en uppgift för inköpsrekvisitioner, kan användaren som tilldelats uppgiften se ämnesraden och instruktionerna på sidan **Inköpsrekvisitioner**. Ämnesraden visas i ett meddelandefält på sidan. Användaren kan sedan klicka på ikonen i meddelandefältet för att visa instruktionerna. Följ dessa steg när du vill ange en ämnesrad och instruktioner.

1.  Klicka på **Grundinställningar** i det vänstra fönstret.
2.  Ange ämnesraden i fältet **Ämne för arbetsartikel**.
3.  Om du vill göra ämnesraden mer personlig kan du infoga platshållare. Platshållare ersätts med lämpliga data när ämnesraden visas för användarna. Följ dessa steg när du vill infoga en platshållare:
    1.  Klicka på den plats i textrutan där platshållaren ska visas.
    2.  Klicka på **Infoga platshållare**.
    3.  Välj önskad platshållare i listan som visas.
    4.  Klicka på **Infoga**.

4.  Om du vill lägga till översättningar av ämnesraden följer du dessa steg:
    1.  Klicka på **Översättningar**.
    2.  Klicka på **Lägg till** på sidan som visas.
    3.  I listan som visas väljer du det språk som du skriver texten i.
    4.  I fältet **Översatt text** anger du texten.
    5.  Om du vill anpassa texten kan du infoga platshållare enligt vad som beskrivs i steg 3.
    6.  Klicka på **Stäng**.

5.  I fältet **Arbetsuppgiftsinstruktioner** anger du instruktionerna.
6.  Om du vill anpassa instruktionerna kan du infoga platshållare. Platshållare ersätts med lämpliga data när instruktionerna visas för användarna. Följ dessa steg när du vill infoga en platshållare:
    1.  Klicka på den plats i textrutan där platshållaren ska visas.
    2.  Klicka på **Infoga platshållare**.
    3.  Välj önskad platshållare i listan som visas.
    4.  Klicka på **Infoga**.

7.  Om du vill lägga till översättningar av instruktionerna följer du dessa steg:
    1.  Klicka på **Översättningar**.
    2.  Klicka på **Lägg till** på sidan som visas.
    3.  I listan som visas väljer du det språk som du skriver texten i.
    4.  I fältet **Översatt text** anger du texten.
    5.  Om du vill anpassa texten kan du infoga platshållare enligt vad som beskrivs i steg 6.
    6.  Klicka på **Stäng**.

## <a name="assign-the-task"></a>Tilldela åtgärden
Följ dessa steg för att ange vem som ska tilldelas den manuella uppgiften.

1.  Klicka på **Tilldelning** i det vänstra fönstret.
2.  I fliken **Tilldelningstyp** väljer du ett av alternativen i följande register, och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 3.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Alternativ</th>
    <th>Användare som tilldelas uppgiften</th>
    <th>Ytterligare steg</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Deltagare</td>
    <td>Användare som tilldelas en specifik grupp eller roll</td>
    <td><ol>
    <li>Välj <strong>Deltagare</strong> i fliken <strong>Rollbaserad</strong> i listan <strong>Deltagartyp</strong>, innan du väljer den grupp- eller rolltyp som du vill tilldela steget.</li>
    <li>Välj den grupp eller roll i listan <strong>Deltagare</strong> som du vill tilldela uppgiften.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Hierarki</td>
    <td>Användare i en specifik organisationshierarki</td>
    <td><ol>
    <li>Välj <strong>Hierarki</strong> innan du går vidare och väljer fliken <strong>Hierarkival</strong> i listan <strong>Hierarkityp</strong> och väljer den hierarkityp som du vill tilldela uppgiften.</li>
    <li>Systemet måste hämta ett intervall med användarnamn i hierarkin. Dessa namn representerar användare som kan tilldelas uppgiften. Följ dessa steg för att ange start- och slutpunkt för det intervall användarnamn som systemet hämtar: <ol>
    <li>Markera en person i listan <strong>Starta från</strong> för att ange startpunkten.</li>
    <li>Klicka på <strong>Lägg till villkor</strong> för att ange slutpunkten. Ange därefter ett villkor som avgör var någonstans i hierarkin som systemet slutar att hämta namn.</li>
    </ol></li>
    <li>I fliken <strong>Hierarkialternativ</strong> väljer du de användare i intervallet som ska tilldelas uppgiften: <ul>
    <li><strong>Tilldela samtliga hämtade användare</strong> – Uppgiften tilldelas alla användare i intervallet.</li>
    <li><strong>Tilldela endast till senast hämtade användare</strong> – Uppgiften tilldelas endast den senaste användaren i intervallet.</li>
    <li><strong>Exkludera användare med följande villkor</strong> – Uppgiften tilldelas inte till någon användare i intervallet som uppfyller ett visst villkor. Klicka på <strong>Lägg till villkor</strong> för att ange villkoret.</li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td>Användare av arbetsflöde</td>
    <td>Användarna i det aktuella arbetsflödet</td>
    <td><ul>
    <li>När du har valt <strong>Användare av arbetsflöde</strong> i fliken <strong>Användare av arbetsflöde</strong> väljer du en användare som deltar i arbetsflödet i listan <strong>Användare av arbetsflöde</strong>.</li>
    </ul></td>
    </tr>
    <tr class="even">
    <td>Användare</td>
    <td>Specifika användare av Microsoft Dynamics 365 for Finance and Operations</td>
    <td><ol>
    <li>Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</li>
    <li>Listan <strong>Tillgängliga användare</strong> innehåller alla Finance and Operations-användare. Markera de användare som ska tilldelas uppgiften och flytta sedan dessa till listan <strong>Markerade användare</strong>.</li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td>Kö</td>
    <td>En arbetsuppgiftskö</td>
    <td><ol>
    <li>Klicka på fliken <strong>Köbaserad</strong>när du har markerat <strong>Kö</strong>.</li>
    <li>Följ dessa steg om du vill tilldela uppgiften till en specifik kö: <ol>
    <li>I listan <strong>Kötyp</strong> väljer du <strong>Arbetsuppgiftskö</strong>.</li>
    <li>Välj kön i listan <strong>Könamn</strong>.</li>
    </ol></li>
    <li>Om ett visst villkor ska bestämma vilken kö beslutet har tilldelats, följer du dessa steg: <ol>
    <li>I listan <strong>Kötyp</strong> väljer du <strong>Villkorsbelagda arbetsuppgiftsköer</strong>.</li>
    <li>I listan <strong>Könamn</strong> väljer du <strong>Villkorsbaserad kö</strong>.</li>
    </ol></li>
    </ol>
    <strong>Obs!</strong> Detta alternativ används bara för vissa arbetsflöden, till exempel ärendehantering.</td>
    </tr>
    </tbody>
    </table>

3.  I fliken **Tidsgräns** i fältet **Tidslängd** anger du hur mycket tid som användaren har på sig att slutföra uppgiften. Välj ett av följande alternativ:
    -   **Timmar** – Ange antalet timmar som användaren har på sig att slutföra uppgiften. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    -   **Dagar** – Ange antalet dagar som användaren har på sig att slutföra uppgiften. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    -   **Veckor** – Ange antalet veckor som användaren har på sig att slutföra uppgiften.
    -   **Månader –** – Välj dag och vecka då användaren senast måste slutföra uppgiften. Du kanske till exempel vill att användaren ska slutföra uppgiften senast på fredagen i den tredje veckan i månaden.
    -   **År** – Välj dag, vecka och månad då användaren senast måste slutföra uppgiften. Du kanske till exempel vill att användaren ska slutföra uppgiften senast på fredagen i den tredje veckan i december.

    Om användaren inte slutför uppgiften inom den tilldelade tiden, är uppgiften försenad. En uppgift som försenas eskaleras, baserat på de alternativ som du väljer i avsnittet **Eskalering** på sidan.

## <a name="specify-what-happens-when-the-task-is-overdue"></a>Ange vad som händer när en uppgift är försenad
Om en användare inte slutför den manuella uppgiften inom den tilldelade tiden, är uppgiften försenad. En uppgift som är försenad kan eskaleras eller automatiskt tilldelas en annan användare. Följ dessa steg för att eskalera uppgiften om den är försenad.

1.  Klicka på **Eskalering** i det vänstra fönstret.
2.  Markera kryssrutan **Använd eskaleringsväg** om du vill skapa en eskaleringsväg. Systemet tilldelar automatiskt uppgiften till de användare som har listats i eskaleringsvägen. Till exempel representerar följande register en eskaleringsväg.

    | Sekvens | Eskaleringsväg      |
    |----------|----------------------|
    | 1        | Tilldela till: Donna     |
    | 2        | Tilldela till: Erin      |
    | 3        | Slutlig åtgärd: Avvisa |

    I detta scenario tilldelar systemet den försenade uppgiften till Donna. Om Donna inte slutför uppgiften inom angiven tidsperiod, tilldelar systemet uppgiften till Erin. Om Erin inte slutför uppgiften inom den tilldelade tiden, avslår systemet dokumentet som skickats in för bearbetning.
3.  Klicka på **Lägg till eskalering** för att lägga till en användare i eskaleringsvägen. I fliken **Tilldelningstyp** väljer du ett av alternativen i följande register och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 4.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Alternativ</th>
    <th>Användare som uppgiften eskaleras till</th>
    <th>Ytterligare steg</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Hierarki</td>
    <td>Användare i en specifik organisationshierarki</td>
    <td><ol>
    <li>Välj <strong>Hierarki</strong> innan du går vidare och väljer fliken <strong>Hierarkival</strong> i listan <strong>Hierarkityp</strong> och väljer den hierarkityp som du vill eskalera uppgiften till.</li>
    <li>Systemet måste hämta ett intervall med användarnamn i hierarkin. Dessa namn representerar användare som uppgiften kan eskaleras till. Följ dessa steg för att ange start- och slutpunkt för det intervall användarnamn som systemet hämtar: <ol>
    <li>Markera en person i listan <strong>Starta från</strong> för att ange startpunkten.</li>
    <li>Klicka på <strong>Lägg till villkor</strong> för att ange slutpunkten. Ange därefter ett villkor som avgör var någonstans i hierarkin som systemet slutar att hämta namn.</li>
    </ol></li>
    <li>I fliken <strong>Hierarkialternativ</strong> väljer du de användare i intervallet som uppgiften ska eskaleras till: <ul>
    <li><strong>Tilldela samtliga hämtade användare</strong> – Uppgiften eskaleras till alla användare i intervallet.</li>
    <li><strong>Tilldela endast till senast hämtade användare</strong> – Uppgiften eskaleras endast till den senaste användaren i intervallet.</li>
    <li><strong>Exkludera användare med följande villkor</strong> – Denna uppgift eskaleras inte till någon användare i intervallet som uppfyller ett visst villkor. Klicka på <strong>Lägg till villkor</strong> för att ange villkoret.</li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Användare av arbetsflöde</td>
    <td>Användarna i det aktuella arbetsflödet</td>
    <td><ul>
    <li>När du har valt <strong>Användare av arbetsflöde</strong> i fliken <strong>Användare av arbetsflöde</strong> väljer du en användare som deltar i arbetsflödet i listan <strong>Användare av arbetsflöde</strong>.</li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td>Användare</td>
    <td>Specifika Finance and Operations-användare.</td>
    <td><ol>
    <li>Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</li>
    <li>Listan <strong>Tillgängliga användare</strong> innehåller alla Finance and Operations-användare. Markera de användare som uppgiften ska eskaleras till, och flytta sedan dessa till listan <strong>Markerade användare</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

4.  I fliken **Tidsgräns** i fältet **Tidslängd** anger du hur mycket tid som användaren har på sig att slutföra uppgiften. Välj ett av följande alternativ:
    -   **Timmar** – Ange antalet timmar som användaren har på sig att slutföra uppgiften. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    -   **Dagar** – Ange antalet dagar som användaren har på sig att slutföra uppgiften. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    -   **Veckor** – Ange antalet veckor som användaren har på sig att slutföra uppgiften.
    -   **Månader –** – Välj dag och vecka då användaren senast måste slutföra uppgiften. Du kanske till exempel vill att användaren ska slutföra uppgiften senast på fredagen i den tredje veckan i månaden.
    -   **År** – Välj dag, vecka och månad då användaren senast måste slutföra uppgiften. Du kanske till exempel vill att användaren ska slutföra uppgiften senast på fredagen i den tredje veckan i december.

5.  Upprepa steg 3 och 4 för varje användare som ska läggas till i eskaleringsvägen. Du kan ändra alla användarnas ordningsföljd.
6.  Om användarna i eskaleringsvägen inte slutför uppgiften inom den tillåtna tidsperioden, utförs uppgiften automatiskt i systemet. Om du vill ange den åtgärd som systemet ska vidta, välj då raden **Åtgärd** och sedan en åtgärd i fliken **Slutåtgärd**.

## <a name="specify-when-the-system-automatically-acts-on-the-task"></a>Ange när systemet ska agera automatiskt på uppgiften
Du kan konfigurera systemet så att detta automatiskt utför en manuell uppgift när särskilda villkor uppfylls. Till exempel kräver en uppgift att en medlem av utgiftsrapportavdelningen granskar de kvitton som skickas in tillsammans med en utgiftsrapport. Enligt företagets policy måste denna uppgift utföras om det totala beloppet för utgiftsrapporten är större än 100 USD. I så fall kan du konfigurera systemet för att automatiskt markera uppgiften som **Slutförd** om totalbeloppet är mindre än 100. Följ dessa steg för att ange när systemet vidtar en åtgärd för den manuella uppgiften.

1.  Klicka på **Automatiska åtgärder** i det vänstra fönstret.
2.  Markera kryssrutan **Aktivera automatiska åtgärder**.
3.  Klicka på **Lägg till villkor**.
4.  Ange ett villkor.
5.  Ange eventuellt ytterligare villkor som krävs.
6.  Följ dessa steg för att bekräfta att de villkor som du har angett har ställts in korrekt:
    1.  Klicka på **Ja**.
    2.  På sidan **Testa arbetsflödesvillkor**, i avsnittet **Testa arbetsflödesvillkoret**, markerar du en post.
    3.  Klicka på **Ja**. Systemet utvärderar posten i syfte att avgöra om den uppfyller villkoren som du angett.
    4.  När du vill återgå till sidan **Egenskaper** klickar du på **OK** eller på **Avbryt**.

7.  I listan **Automatisk slutförandeåtgärd** väljer du den åtgärd som systemet ska vidta för uppgiften.

## <a name="specify-when-notifications-are-sent"></a>Ange när meddelanden ska skickas
Du kan skicka meddelanden till andra när en manuell uppgift har delegerats, eskalerats, slutförts eller avvisats, eller när en ändring har begärts. Följ dessa steg för att ange när meddelanden skickas och vem de skickas till.

1.  Klicka på **Meddelanden** i det vänstra fönstret.
2.  Markera kryssrutan bredvid händelserna som meddelandena ska skickas för:
    -   **Delegera** – Den här uppgiften har tilldelats till en annan användare.
    -   **Eskalera** – Den tilldelade användaren har inte slutfört uppgiften inom angiven tid.
    -   **Slutför** – Den tilldelade användaren har slutfört uppgiften.
    -   **Avvisa** – Den tilldelade användaren har avvisat dokumentet som skickats in.
    -   **Begär ändring** – Den tilldelade användaren har begärt en ändring av dokumentet som skickats in.

3.  Välj raden för en händelse som du valde i steg 2.
4.  Ange meddelandetexten i textrutan i fliken **Meddelandetext**.
5.  Om du vill anpassa meddelandet kan du infoga platshållare. Platshållare ersätts med lämplig information när meddelandet visas för användarna. Följ dessa steg när du vill infoga en platshållare:
    1.  Klicka på den plats i textrutan där platshållaren ska visas.
    2.  Klicka på **Infoga platshållare**.
    3.  Välj önskad platshållare i listan som visas.
    4.  Klicka på **Infoga**.

6.  Om du vill lägga till översättningar av meddelandet följer du dessa steg:
    1.  Klicka på **Översättningar**.
    2.  Klicka på **Lägg till** på sidan som visas.
    3.  I listan som visas väljer du det språk som du skriver texten i.
    4.  I fältet **Översatt text** anger du texten.
    5.  Om du vill anpassa texten kan du infoga platshållare enligt vad som beskrivs i steg 5.
    6.  Klicka på **Stäng**.

7.  Ange vem meddelandena ska skickas till i fliken **Mottagare**. I följande register väljer du ett av alternativen och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 8.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Alternativ</th>
    <th>Meddelandemottagare</th>
    <th>Ytterligare steg</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Deltagare</td>
    <td>Användare som tilldelas en specifik grupp eller roll</td>
    <td><ol>
    <li>Välj <strong>Deltagare</strong> i fliken <strong>Rollbaserad</strong> i listan <strong>Deltagartyp</strong> innan du väljer den grupp- eller rolltyp som du vill skicka meddelanden till.</li>
    <li>Välj den grupp eller roll som du vill skicka meddelanden till i listan <strong>Deltagare</strong>.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Användare av arbetsflöde</td>
    <td>Användarna i det aktuella arbetsflödet</td>
    <td><ul>
    <li>När du har valt <strong>Användare av arbetsflöde</strong> i fliken <strong>Användare av arbetsflöde</strong> väljer du en användare som deltar i arbetsflödet i listan <strong>Användare av arbetsflöde</strong>.</li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td>Användare</td>
    <td>Specifika Finance and Operations-användare.</td>
    <td><ol>
    <li>Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</li>
    <li>Listan <strong>Tillgängliga användare</strong> innehåller alla Finance and Operations-användare. Markera de användare som du vill skicka meddelanden till, och flytta sedan dessa användare till listan <strong>Markerade användare</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  Upprepa stegen 3 till och med 7 för varje enskild händelse du valde i steg 2.

## <a name="set-a-time-limit"></a>Ange en tidsgräns
Följ dessa steg om den manuella uppgiften måste slutföras inom en viss tid. 

**Obs!** De alternativ som du väljer i denna procedur åsidosätter alternativen som du valde i avsnitten **Tilldelning** och **Eskalering** på sidan.

1.  Klicka på **Avancerade inställningar** i det vänstra fönstret.
2.  Markera kryssrutan **Ange en tidsgräns för arbetsflödeselement**.
3.  Ange när uppgiften måste vara slutförd i fältet **Tidslängd**. Välj ett av följande alternativ:
    -   **Timmar** – Ange det antal timmar inom vilket uppgiften måste slutföras. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    -   **Dagar** – Ange det antal dagar inom vilket uppgiften måste slutföras. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    -   **Veckor** – Ange det antal veckor inom vilket uppgiften måste slutföras.
    -   **Månader –** – Välj dag och vecka då uppgiften senast måste vara slutförd. Du kanske till exempel vill att uppgiften ska ha slutförts senast på fredagen i den tredje veckan i månaden.
    -   **År –** – Välj dag, vecka och månad då uppgiften senast måste vara slutförd. Du kanske till exempel vill att uppgiften ska ha slutförts senast på fredagen i den tredje veckan i december.

4.  Om tidsgränsen överskrids, utförs åtgärden automatiskt i systemet. I listan **Åtgärd** väljer du den åtgärd som ska vidtas i systemet.

## <a name="specify-which-actions-are-available-to-the-user"></a>Ange vilka åtgärder som är tillgängliga för användaren
När den manuella uppgiften tilldelas en användare, måste användaren vidta åtgärder för uppgiften. Följ dessa steg för att ange vilka åtgärder som användaren kan vidta för uppgiften. **Obs!** Vilka åtgärder som står till buds varierar beroende på hur uppgiften har utformats.

1.  Klicka på **Avancerade inställningar** i det vänstra fönstret.
2.  Markera kryssrutan **Slutförd** om du vill att användaren ska kunna markera uppgiften som **Slutförd**.
3.  Markera kryssrutan **Avvisa** om du vill att användaren ska kunna avvisa det inskickade dokumentet.
4.  Markera kryssrutan **Begär ändring** om du vill att användaren ska kunna begära ändringar av dokumentet som skickats.
5.  Markera kryssrutan **Delegera** om du vill att användaren ska kunna tilldela uppgiften till en annan användare.
6.  Markera kryssrutan **Överlåt** om du vill att användaren ska kunna överlåta uppgiften till en annan användare i arbetsuppgiftskön.
7.  Markera kryssrutan **Frisläpp** om du vill att användaren ska kunna överlåta uppgiften till arbetsuppgiftskön. En annan användare kan sedan slutföra uppgiften.





