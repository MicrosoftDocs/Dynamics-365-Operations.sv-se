---
title: Konfigurera arbetsflödesegenskaper
description: I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för ett arbetsflöde.
author: ChrisGarty
manager: AnnBe
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4d01a784b0f0cbfce30f1197278f015b236ef0b8
ms.sourcegitcommit: e55efd2f62bf60f678108c09ad4701a76b20cc68
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/17/2020
ms.locfileid: "3698154"
---
# <a name="configure-workflow-properties"></a>Konfigurera arbetsflödesegenskaper

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för ett arbetsflöde.

Öppna arbetsflödet i arbetsflödesredigeraren för att konfigurera ett egenskaperna för ett arbetsflöde. Klicka på arbetsytan i arbetsflödesredigeraren och klicka sedan på **Egenskaper** för att öppna sidan **Egenskaper**. Du kan sedan använda följande procedurer när du vill konfigurera olika egenskaper för arbetsflödet.

## <a name="name-the-workflow"></a>Ge arbetsflödet ett namn

Följ dessa steg när du vill ange ett namn för arbetsflödet.

1. Klicka på **Grundinställningar** i det vänstra fönstret.
2. Ange ett unikt namn i fältet **Namn**. Om du till exempel skapar ett arbetsflöde för inköpsrekvisitioner för varje land/region som du har verksamhet i, kan du namnge arbetsflödet för inköpsrekvisitioner **Inköpsrekvisitioner för Danmark** eller **Inköpsrekvisitioner för Spanien**.

## <a name="specify-the-workflow-owner"></a>Ange arbetsflödets ägare

Ägaren till arbetsflödet är den person som administrerar och underhåller arbetsflödet. Följ dessa steg för att ange arbetsflödets ägare.

1. Klicka på **Grundinställningar** i det vänstra fönstret.
2. I listan **Ägare** väljer du namnet på den person som ska hantera arbetsflödet.

## <a name="select-an-email-template"></a>Välj en e-postmall

Följ dessa steg för att välja den e-postmall som används för att skapa meddelanden om arbetsflödet.

1. Klicka på **Grundinställningar** i det vänstra fönstret.
2. Välj mallen i listan **E-postmall för arbetsflödesmeddelanden**.

## <a name="enter-instructions-for-users"></a>Ange instruktioner för användare

Du kan tillhandahålla instruktioner till de användare som skickar dokument för bearbetning och godkännande. Dessa användare kallas även för *upphovsmän*. Anta att du skapar ett arbetsflöde för en inköpsrekvisition och anger instruktioner. Dessa instruktioner kan sedan läsas av användare som anger inköpsrekvisitioner på sidan **Inköpsrekvisitioner**. För att visa instruktioner klickar upphovsmannen klickar på ikonen i meddelandefältet för arbetsflöde. Följ dessa steg om du vill ange instruktioner för användare.

1. Klicka på **Grundinställningar** i det vänstra fönstret.
2. Ange instruktionerna i fältet **Sändningsinstruktioner**.
3. Om du vill anpassa instruktionerna kan du infoga platshållare. Platshållare ersätts med lämpliga data när instruktionerna visas för användarna. Följ dessa steg när du vill infoga en platshållare:

    1. Klicka på fältet **Sändningsinstruktioner** för att ange var platshållaren ska visas.
    2. Klicka på **Infoga platshållare**.
    3. Välj önskad platshållare i listan som visas.
    4. Klicka på **Infoga**.

4. Om du vill lägga till översättningar av instruktionerna följer du dessa steg:

    1. Klicka på **Översättningar**.
    2. Klicka på **Lägg till** på sidan som visas.
    3. I listan som visas väljer du det språk som du skriver texten i.
    4. I fältet **Översatt text** anger du texten.
    5. Om du vill anpassa texten kan du infoga platshållare. Se steg 3 för instruktioner om hur du anger en platshållare.
    6. Klicka på **Stäng**.

## <a name="specify-when-this-workflow-is-used-through-activation-conditions"></a>Ange när det här arbetsflödet används med aktiveringsvillkor

Du kan skapa flera arbetsflöden utifrån samma arbetsflödestyp. Om du har flera arbetsflöden som är baserade på samma typ, måste du ange när respektive arbetsflöde ska användas med aktiveringsvillkor. Om aktiveringsvillkoren inte uppfylls används standardarbetsflödet. Om det bara finns en definierad arbetsflödeskonfiguration för en arbetsflödestyp, kommer arbetsflödeskonfigurationen att användas oavsett aktiveringsvillkoren.

Du kan till exempel skapa ett arbetsflöde för inköpsrekvisitioner för varje land/region som du har verksamhet i, exempelvis inköpsrekvisitioner för Danmark eller inköpsrekvisitioner för Spanien med följande villkor.

- Inköpsrekvisitioner för Danmark används när: land/region = DK:
- Inköpsrekvisitioner för Spanien används när: land/region = ES:

Följ dessa steg för att ange när arbetsflödet som du konfigurerar ska användas.

1. Klicka på **Aktivering** i det vänstra fönstret.
2. Markera kryssrutan **Ange villkor för att köra detta arbetsflöde**.
3. Klicka på **Lägg till villkor**.
4. Ange ett villkor.
5. Ange eventuellt ytterligare villkor som krävs.
6. Kör genom arbetsflödet med några målposter för att verifiera att villkoret innehåller och exkluderar poster.

## <a name="specify-when-notifications-are-sent"></a>Ange när meddelanden ska skickas

När ett dokument skickas in för bearbetning skapas en arbetsflödesinstans. Du kan skicka meddelanden till användarna när arbetsflödesinstanser som baseras på arbetsflödet har startats, slutförts, annullerats eller stoppats på grund av ett fel. Följ dessa steg för att ange när meddelanden ska skickas.

1. Klicka på **Meddelanden** i det vänstra fönstret.
2. Markera kryssrutan för varje händelse som ska utlösa meddelanden:

    - **Startat** – Skicka meddelanden när en arbetsflödesinstans har startats.
    - **Stoppat** – Skicka meddelanden när en arbetsflödesinstans har stoppats på grund av ett fel.
    - **Slutfört** – Skicka meddelanden när en arbetsflödesinstans har slutförts.
    - **Oåterkalleligt** – Skicka meddelanden när en arbetsflödesinstans har stoppats på grund av ett oåterkalleligt fel.
    - **Avslutat** – Skicka meddelanden när en arbetsflödesinstans har avslutats.

3. Välj raden för en händelse som du valde i steg 2.
4. Ange meddelandetexten i fliken **Meddelandetext**.
5. Om du vill anpassa texten kan du infoga platshållare. Platshållare ersätts med lämpliga data när texten visas för användarna. Följ dessa steg när du vill infoga en platshållare:

    1. Klicka i fältet för att ange var platshållaren ska visas.
    2. Klicka på **Infoga platshållare**.
    3. Välj önskad platshållare i listan som visas.
    4. Klicka på **Infoga**.
    5. En gemensam platshållare med **Meddelandetext** som ska inkluderas är "Senaste anteckningar: %Workflow.Last note%”, som visar alla kommentarer från föregående steg.

6. Följ dessa steg för att lägga till översättningar av texten:

    1. Klicka på **Översättningar**.
    2. Klicka på **Lägg till** på sidan som visas.
    3. I listan som visas väljer du det språk som du skriver texten i.
    4. I fältet **Översatt text** anger du texten.
    5. Om du vill anpassa texten kan du infoga platshållare. Se steg 5 för instruktioner om hur du anger en platshållare.
    6. Klicka på **Stäng**.

7. Använd följande alternativ för att, i fliken **Mottagare**, ange vem som ska få meddelandena.

    <table>
    <thead>
    <tr>
    <th>Alternativ</th>
    <th>Meddelandena skickas till dessa användare</th>
    <th>Följ dessa steg om du vill skicka meddelanden</th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td>Deltagare</td>
    <td>Användare som tilldelas en specifik grupp eller roll</td>
    <td>
    <ol>
    <li>Klicka på <strong>Deltagare</strong> i fliken <strong>Mottagare</strong>.</li>
    <li>Välj den typ av grupp eller roll som du vill skicka meddelanden till i fliken <strong>Rollbaserad</strong> i listan <strong>Deltagartyp</strong>.</li>
    <li>Välj den grupp eller roll som du vill skicka meddelanden till i listan <strong>Deltagare</strong>.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Användare av arbetsflöde</td>
    <td>Användare som är deltagare i detta arbetsflöde</td>
    <td>
    <ol>
    <li>Klicka på <strong>Användare av arbetsflöde</strong> i fliken <strong>Mottagare</strong>.</li>
    <li>Välj en deltagare i detta arbetsflöde i fliken <strong>Användare av arbetsflöde</strong> i listan <strong>Användare av arbetsflöde</strong>.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Användare</td>
    <td>Specifika användare</td>
    <td>
    <ol>
    <li>Klicka på <strong>Användare</strong> i fliken <strong>Mottagare</strong>.</li>
    <li>Fliken <strong>Användare</strong> i listan <strong>Tillgängliga användare</strong> innehåller alla användare. Markera de användare som du vill skicka meddelanden till, och flytta sedan dessa till listan <strong>Markerade användare</strong>.</li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. Upprepa stegen 3 till och med 7 för varje enskild händelse du valde i steg 2.

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a>Kommentera de ändringar som du har gjorts i arbetsflödet

Gör på följande sätt om du vill kommentera de ändringar som du har utfört i arbetsflödet.

1. Klicka på **Noteringar** i det vänstra fönstret.
2. Skriv dina kommentarer i fältet **Ange kommentarer om arbetsflödet**.
3. Granska dina kommentarer. När du har lagt till kommentarer kan du inte ändra dem.
4. Klicka på **Lägg till** för att lägga till dina kommentarer i området **Kommentarshistorik**.
