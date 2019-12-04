---
title: Konfigurera godkännandeprocesser i ett arbetsflöde
description: Använd följande procedur när du vill konfigurera egenskaperna för godkännandeprocessen.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d4032d5e56b9dd014ec0472abfc1b2ad4a15ff1d
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811391"
---
# <a name="configure-approval-processes-in-a-workflow"></a>Konfigurera godkännandeprocesser i ett arbetsflöde

[!include [banner](../includes/banner.md)]

Använd följande procedur när du vill konfigurera egenskaperna för godkännandeprocessen.

Högerklicka godkännandesteget i arbetsflödesredigeraren och klicka sedan på **Egenskaper** för att öppna formuläret **Egenskaper** om du vill godkänna en godkännandeprocess.

## <a name="name-the-approval-process"></a>Namnge godkännandeprocessen

Följ dessa steg om du vill ange ett namn för godkännandeprocessen.

1. Klicka på **Grundinställningar** i det vänstra fönstret.
2. Ange ett unikt namn för godkännandeprocessen i fältet **Namn**.

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a>Ange när systemet ska agera automatiskt på dokumentet

Du kan konfigurera systemet att vidta automatiska åtgärder för dokumentet om vissa villkor uppfylls. Systemet kan till exempel godkänna utgiftsrapporter med totala belopp som understiger 1 000 kronor. Följ dessa steg för att ange när systemet vidtar en åtgärd för dokumentet.

1. Klicka på **Automatiska åtgärder** i det vänstra fönstret.
2. Markera kryssrutan **Aktivera automatiska åtgärder**.
3. Klicka på **Lägg till villkor**.
4. Ange ett villkor.
5. Ange vid behov ytterligare villkor.
6. Slutför följande steg för att bekräfta att de villkor som du har angett har ställts in korrekt:

    1. Klicka på **Testa** för att öppna formuläret **Testa arbetsflödesvillkor**.
    2. Markera en post i området **Validera villkor** i formuläret.
    3. Klicka på **Ja**. Systemet utvärderar posten i syfte att avgöra om den uppfyller villkoren som du angett.
    4. Klicka på **OK** eller **Avbryt** för att återgå till formuläret **Egenskaper**.

7. I listan **Automatisk slutförandeåtgärd** väljer du den åtgärd som systemet ska vidta för dokumentet.

## <a name="specify-when-notifications-are-sent"></a>Ange när meddelanden ska skickas

Du kan skicka meddelanden till andra när ett dokument har godkänts, avvisats, delegerats eller eskalerats, eller när en ändring har begärts. Följ dessa steg för att ange när meddelanden skickas och vem de skickas till.

1. Klicka på **Meddelanden** i det vänstra fönstret.
2. Markera kryssrutan bredvid händelserna för att skicka meddelanden för:

    - **Delegera** – När ett dokument har tilldelats till en annan användare för godkännande.
    - **Eskalera** – När den tilldelade användaren inte har agerat på ett dokument vid angiven tidpunkt.
    - **Godkänn** – När ett dokument har godkänts.
    - **Avvisa** – När ett dokument har avvisats.
    - **Begär ändring** – När den tilldelade användaren har begärt en ändring av ett dokument som skickats in.

3. Välj raden för en händelse som du valde i steg 2.
4. Klicka på fliken **Meddelandetext**.
5. Ange meddelandetexten i textrutan.
6. Om du vill göra texten mer personlig kan du även infoga platshållare som ersätts med lämplig information när de visas för användarna. Följ dessa steg när du vill infoga en platshållare:

    1. Klicka på den plats i textrutan där platshållaren ska visas.
    2. Klicka på **Infoga platshållare**.
    3. Välj önskad platshållare i listan som visas.
    4. Klicka på **Infoga**.

7. Klicka på **Översättningar** för att lägga till översättningar av meddelandet. Följ dessa steg i formuläret som visas:

    1. Klicka på **Lägg till**.
    2. I listan som visas väljer du det språk som du skriver texten i.
    3. I textrutan **Översatt text** anger du texten.
    4. Om du vill anpassa texten kan du infoga platshållare.
    5. Klicka på **Stäng**.

8. Klicka på fliken **Recipient**.
9. Ange till vem som meddelandena ska skickas. I följande register väljer du ett av alternativen, och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 10.

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
    <td><strong>Deltagare</strong></td>
    <td>Användare som tilldelas en specifik grupp eller roll</td>
    <td>
    <ol>
    <li>Klicka på fliken <strong>Role based</strong>när du har markerat <strong>Participant</strong>.</li>
    <li>Välj den grupp- eller rolltyp som du vill skicka meddelanden till i listan <strong>Typ of participant</strong>.</li>
    <li>Välj den grupp eller roll som du vill skicka meddelanden till i listan <strong>Deltagare</strong>.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>Användare av arbetsflöde</strong></td>
    <td>Användare som deltar i det aktuella arbetsflödet</td>
    <td>
    <ol>
    <li>Klicka på fliken <strong>Arbetsflödesanvändar</strong> när du har valt <strong>Arbetsflödesanvändar</strong>.</li>
    <li>Välj en användare som deltar i arbetsflödet i listan <strong>Arbetsflödesanvändar</strong>.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><strong>Användare</strong></td>
    <td>Specifika användare</td>
    <td>
    <ol>
    <li>Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</li>
    <li>Markera de användare som du vill skicka meddelanden till, och flytta sedan dessa användare till listan <strong>Markerade användare</strong>:.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

10. Upprepa stegen 3 till och med 9 för varje enskild händelse som du valde i steg 2.

## <a name="specify-a-final-approver"></a>Ange den slutliga godkännaren

Du kan eventuellt tilldela en slutlig godkännare för situationer där godkännaren är den person, som skickade in dokumentet för godkännande. Följ dessa steg för att ange en slutlig godkännare.

1. Klicka på **Avancerade inställningar** i det vänstra fönstret.
2. Markera rutan **Använd slutlig godkännare**.
3. I listan ska du välja en användare som slutlig godkännare.

## <a name="set-a-time-limit"></a>Ange en tidsgräns

Följ dessa steg om den manuella processen måste slutföras inom en viss tid.

> [!NOTE]
> De alternativ som du väljer i dessa steg åsidosätter alternativen som du valde i områdena **Assignment** och **Escalation** för respektive godkännandesteg.

1. Klicka på **Avancerade inställningar** i det vänstra fönstret.
2. Markera kryssrutan för **elementet** **Ställ in en tidsgräns för arbetsflöden**.
3. Ange när godkännandeprocessen måste vara slutförd i fältet **Duration**. Välj ett av följande alternativ:

    - **Timmar** – Ange det antal timmar inom vilket godkännandeprocessen senast måste ha slutförts. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    - **Dagar** – Ange det antal dagar inom vilket godkännandeprocessen senast måste ha slutförts. Välj sedan den kalender som används inom din organisation, och ange information om organisationens arbetsvecka.
    - **Weeks** – Ange det antal veckor inom vilket godkännandeprocessen senast måste ha slutförts.
    - **Months –** – Välj dag och vecka då godkännandeprocessen senast måste vara slutförd. Du kanske till exempel vill att godkännandeprocessen ska ha slutförts senast på fredagen i den tredje veckan i månaden.
    - **År** – Välj dag, vecka och månad då godkännandeprocessen senast måste vara slutförd. Du kanske till exempel vill att godkännandeprocessen ska ha slutförts senast på fredagen i den tredje veckan i december.

4. Om tidsgränsen överskrids, utför systemet åtgärden i dokumentet. I listan **Åtgärd** väljer du den åtgärd som ska vidtas i systemet.

## <a name="specify-which-actions-are-available-to-the-user"></a>Ange vilka åtgärder som är tillgängliga för användaren

När ett dokument tilldelas en användare för godkännande, måste användaren vidta åtgärder för dokumentet. Följ dessa steg för att ange vilka åtgärder som användaren kan vidta för det inskickade dokumentet.

1. Klicka på **Avancerade inställningar** i det vänstra fönstret.
2. Markera kryssrutan **Godkänn** om du vill att användaren ska kunna godkänna dokumentet.
3. Markera kryssrutan **Avvisa** om du vill att användaren ska kunna avvisa dokumentet.
4. Markerakrysstura **Begär ändring** om du vill att användaren ska kunna begära ändringar i dokumentet.
5. Markera kryssrutan **Delegera** om du vill att användaren ska kunna tilldela dokument till andra användare för godkännande.

> [!NOTE]
> **Kryssrutan Aktivera åtgärder från arbetslistan i Enterprise Portal** stöds inte längre.

## <a name="configure-the-approval-steps"></a>Konfigurera godkännandestegen

En godkännandeprocess består av godkännandesteg. Slutför följande procedur för att lägga till steg i godkännandeprocessen och konfigurera stegen.

1. Dubbelklicka på godkännandeprocessen i arbetsflödesredigeraren. Arbetsflödesredigeraren visar stegen för godkännandeprocessen.
2. Dra steget från området **Arbetsflödeselement** till arbetsytan för att lägga till ett godkännandesteg.
3. Se [Konfigurera godkännandesteg i ett arbetsflöde](configure-approval-step-workflow.md) för att konfigurera ett godkännandesteg.
