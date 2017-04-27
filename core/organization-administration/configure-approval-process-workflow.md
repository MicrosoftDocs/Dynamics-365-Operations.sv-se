---
title: "Konfigurera en godkännandeprocess i ett arbetsflöde"
description: "Använd följande procedur när du vill konfigurera egenskaperna för godkännandeprocessen."
author: sericks007
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 579e393ef64bc5ad72d129ac08ac215c524d5c55
ms.lasthandoff: 03/31/2017


---

# <a name="configure-an-approval-process-in-a-workflow"></a>Konfigurera en godkännandeprocess i ett arbetsflöde

Använd följande procedur när du vill konfigurera egenskaperna för godkännandeprocessen.

Högerklicka godkännandesteget i arbetsflödesredigeraren och klicka sedan på **Egenskaper** för att öppna formuläret **Egenskaper** om du vill godkänna en godkännandeprocess.
Namnge godkännandeprocessen
-------------------------

Följ dessa steg om du vill ange ett namn för godkännandeprocessen.
1.  Klicka på **Grundinställningar** i det vänstra fönstret.
2.  Ange ett unikt namn för godkännandeprocessen i fältet **Name**.

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a>Ange när systemet ska agera automatiskt på dokumentet
Du kan konfigurera systemet att vidta automatiska åtgärder för dokumentet om vissa villkor uppfylls. Systemet kan till exempel godkänna utgiftsrapporter med totala belopp som understiger 1 000 kronor. Följ dessa steg för att ange när systemet vidtar en åtgärd för dokumentet.
1.  Klicka på **Automatiska åtgärder** i det vänstra fönstret.
2.  Markera kryssrutan **Aktivera automatiska åtgärder**.
3.  Klicka på **Lägg till villkor**.
4.  Ange ett villkor.
5.  Ange vid behov ytterligare villkor.
6.  Slutför följande steg för att bekräfta att de villkor som du har angett har ställts in korrekt:
    1.  Klicka på **Test** för att öppna formuläret **Test workflow condition**.
    2.  Markera en post i området **Validera villkor** i formuläret.
    3.  Klicka på **Ja**. Systemet utvärderar posten i syfte att avgöra om den uppfyller villkoren som du angett.
    4.  Klicka på **OK** eller **Avbryt** för att återgå till formuläret **Egenskaper**.

7.  I listan **Auto complete action** väljer du den åtgärd som systemet ska vidta för dokumentet.

## <a name="specify-when-notifications-are-sent"></a>Ange när meddelanden ska skickas
Du kan skicka meddelanden till andra när ett dokument har godkänts, avvisats, delegerats eller eskalerats, eller när en ändring har begärts. Följ dessa steg för att ange när meddelanden skickas och vem de skickas till.
1.  Klicka på **Meddelanden** i det vänstra fönstret.
2.  Markera kryssrutan bredvid händelserna för att skicka meddelanden för:
    -   **Delegera** – När ett dokument har tilldelats till en annan användare för godkännande.
    -   **Eskalera** – När den tilldelade användaren inte har agerat på ett dokument vid angiven tidpunkt.
    -   **Godkänn** – När ett dokument har godkänts.
    -   **Avvisa** – När ett dokument har avvisats.
    -   **Begär ändring** – När den tilldelade användaren har begärt en ändring av ett dokument som skickats in.

3.  Välj raden för en händelse som du valde i steg 2.
4.  Klicka på fliken **Notification text**.
5.  Ange meddelandetexten i textrutan.
6.  Om du vill göra texten mer personlig kan du även infoga platshållare som ersätts med lämplig information när de visas för användarna. Följ dessa steg när du vill infoga en platshållare:
    1.  Klicka på den plats i textrutan där platshållaren ska visas.
    2.  Klicka på **Infoga platshållare**.
    3.  Välj önskad platshållare i listan som visas.
    4.  Klicka på **Infoga**.

7.  Klicka på **Översättningar** för att lägga till översättningar av meddelandet. Följ dessa steg i formuläret som visas:
    1.  Klicka på **Lägg till**.
    2.  I listan som visas väljer du det språk som du skriver texten i.
    3.  I textrutan **Translated text** anger du texten.
    4.  Om du vill anpassa texten kan du infoga platshållare.
    5.  Klicka på **Stäng**.

8.  Klicka på fliken **Recipient**.
9.  Ange till vem som meddelandena ska skickas. I följande register väljer du ett av alternativen, och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 10.

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
    <td><strong>Deltagare</strong></td>
    <td>Användare som tilldelas en specifik grupp eller roll</td>
    <td><ol>
    <li>Klicka på fliken <strong>Role based</strong>när du har markerat <strong>Participant</strong>.</li>
    <li>Välj den grupp- eller rolltyp som du vill skicka meddelanden till i listan <strong>Typ of participant</strong>.</li>
    <li>Välj den grupp eller roll som du vill skicka meddelanden till i listan <strong>Deltagare</strong>.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><strong>Användare av arbetsflöde</strong></td>
    <td>Användare som deltar i det aktuella arbetsflödet</td>
    <td><ol>
    <li>Klicka på fliken <strong>Workflow user</strong> när du har valt <strong>Workflow user</strong>.</li>
    <li>Välj en användare som deltar i arbetsflödet i listan <strong>Workflow user</strong>.</li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td><strong>Användare</strong></td>
    <td>Specifika Microsoft Dynamics 365 for Operations-användare</td>
    <td><ol>
    <li>Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</li>
    <li>Listan <strong>Tillgängliga användare</strong> innehåller alla Microsoft Dynamics 365 for Operations-användare. Markera de användare som du vill skicka meddelanden till, och flytta sedan dessa användare till listan <strong>Selected users</strong>:.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

10. Upprepa stegen 3 till och med 9 för varje enskild händelse som du valde i steg 2.

## <a name="specify-a-final-approver"></a> Ange den slutliga godkännaren
Du kan eventuellt tilldela en slutlig godkännare för situationer där godkännaren är den person, som skickade in dokumentet för godkännande. Följ dessa steg för att ange en slutlig godkännare.
1.  Klicka på **Avancerade inställningar** i det vänstra fönstret.
2.  Markera rutan **Use final approver**.
3.  I listan ska du välja en användare som slutlig godkännare.

## <a name="set-a-time-limit"></a>Ange en tidsgräns
Följ dessa steg om den manuella processen måste slutföras inom en viss tid.
| **Obs! **                                                                                                                                                |
|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| De alternativ som du väljer i dessa steg åsidosätter alternativen som du valde i områdena **Assignment** och **Escalation** för respektive godkännandesteg. |

1.  Klicka på **Avancerade inställningar** i det vänstra fönstret.
2.  Markera kryssrutan för elementet **Set a time limit for the workflow******.
3.  Ange när godkännandeprocessen måste vara slutförd i fältet **Duration**. Välj ett av följande alternativ:
    -   **Hours** – Ange det antal timmar inom vilket godkännandeprocessen senast måste ha slutförts. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    -   **Days** – Ange det antal dagar inom vilket godkännandeprocessen senast måste ha slutförts. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    -   **Weeks** – Ange det antal veckor inom vilket godkännandeprocessen senast måste ha slutförts.
    -   **Months –** – Välj dag och vecka då godkännandeprocessen senast måste vara slutförd. Du kanske till exempel vill att godkännandeprocessen ska ha slutförts senast på fredagen i den tredje veckan i månaden.
    -   **Years** – Välj dag, vecka och månad då godkännandeprocessen senast måste vara slutförd. Du kanske till exempel vill att godkännandeprocessen ska ha slutförts senast på fredagen i den tredje veckan i december.

4.  Om tidsgränsen överskrids, utför systemet åtgärden i dokumentet. I listan **Åtgärd** väljer du den åtgärd som ska vidtas i systemet.

## <a name="specify-which-actions-are-available-to-the-user"></a>Ange vilka åtgärder som är tillgängliga för användaren
När ett dokument tilldelas en användare för godkännande, måste användaren vidta åtgärder för dokumentet. Följ dessa steg för att ange vilka åtgärder som användaren kan vidta för det inskickade dokumentet.
1.  Klicka på **Avancerade inställningar** i det vänstra fönstret.
2.  Markera kryssrutan **Godkänn** om du vill att användaren ska kunna godkänna dokumentet.
3.  Markera kryssrutan **Avvisa** om du vill att användaren ska kunna avvisa dokumentet.
4.  Markerakrysstura **Begär ändring** om du vill att användaren ska kunna begära ändringar i dokumentet.
5.  Markera kryssrutan **Delegera** om du vill att användaren ska kunna tilldela dokument till andra användare för godkännande.

**Obs!**: Kryssrutan **Enable actions from the work list in Enterprise Portal ** stöds inte längre.

## <a name="configure-the-approval-steps"></a> Konfigurera godkännandestegen
En godkännandeprocess består av godkännandesteg. Slutför följande procedur för att lägga till steg i godkännandeprocessen och konfigurera stegen.
1.  Dubbelklicka på godkännandeprocessen i arbetsflödesredigeraren. Arbetsflödesredigeraren visar stegen för godkännandeprocessen.
2.  Dra steget från området **Workflow elements** till arbetsytan för att lägga till ett godkännandesteg.
3.  Se [Configure an approval step](http://axhelp.dynamics.com/en/wiki/configure-an-approval-step/) för att konfigurera ett godkännandesteg.




