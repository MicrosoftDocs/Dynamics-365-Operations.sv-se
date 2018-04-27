---
title: "Konfigurera arbetsflödesegenskaper"
description: "I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för ett arbetsflöde."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 19cc8f92b5bb6d9ddfdc77785e48de17ed005703
ms.openlocfilehash: 7ea35d851613a19889392400e31cf8492d5dc799
ms.contentlocale: sv-se
ms.lasthandoff: 03/23/2018

---

# <a name="configure-workflow-properties"></a>Konfigurera arbetsflödesegenskaper

[!INCLUDE [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar olika egenskaper för ett arbetsflöde.

Öppna arbetsflödet i arbetsflödesredigeraren för att konfigurera ett egenskaperna för ett arbetsflöde. Klicka på arbetsytan i arbetsflödesredigeraren och klicka sedan på **Egenskaper** för att öppna sidan **Egenskaper**. Du kan sedan använda följande procedurer när du vill konfigurera olika egenskaper för arbetsflödet.

## <a name="name-the-workflow"></a>Ge arbetsflödet ett namn
Följ dessa steg när du vill ange ett namn för arbetsflödet.

1.  Klicka på **Grundinställningar** i det vänstra fönstret.
2.  Ange ett unikt namn i fältet **Namn**. Om du till exempel skapar ett arbetsflöde för inköpsrekvisitioner för varje land/region som du har verksamhet i, kan du namnge arbetsflödet för inköpsrekvisitioner **Inköpsrekvisitioner för Danmark** eller **Inköpsrekvisitioner för Spanien**.

## <a name="specify-the-workflow-owner"></a>Ange arbetsflödets ägare
Ägaren till arbetsflödet är den person som administrerar och underhåller arbetsflödet. Följ dessa steg för att ange arbetsflödets ägare.

1.  Klicka på **Grundinställningar** i det vänstra fönstret.
2.  I listan **Ägare** väljer du namnet på den person som ska hantera arbetsflödet.

## <a name="select-an-email-template"></a>Välj en e-postmall
Följ dessa steg för att välja den e-postmall som används för att generera meddelanden om arbetsflödet.

1.  Klicka på **Grundinställningar** i det vänstra fönstret.
2.  Välj mallen i listan **E-postmall för arbetsflödesmeddelanden**.

## <a name="enter-instructions-for-users"></a>Ange instruktioner för användare
Du kan tillhandahålla instruktioner till de användare som skickar dokument för bearbetning och godkännande. Dessa användare kallas även för *upphovsmän*. Anta att du skapar ett arbetsflöde för en inköpsrekvisition och anger instruktioner. Dessa instruktioner kan sedan läsas av användare som anger inköpsrekvisitioner på sidan **Inköpsrekvisitioner**. För att visa instruktioner klickar upphovsmannen klickar på ikonen i meddelandefältet för arbetsflöde. Följ dessa steg om du vill ange instruktioner för användare.

1.  Klicka på **Grundinställningar** i det vänstra fönstret.
2.  Ange instruktionerna i fältet **Sändningsinstruktioner**.
3.  Om du vill anpassa instruktionerna kan du infoga platshållare. Platshållare ersätts med lämpliga data när instruktionerna visas för användarna. Följ dessa steg när du vill infoga en platshållare:
    1.  Klicka på fältet **Sändningsinstruktioner** för att ange var platshållaren ska visas.
    2.  Klicka på **Infoga platshållare**.
    3.  Välj önskad platshållare i listan som visas.
    4.  Klicka på **Infoga**.

4.  Om du vill lägga till översättningar av instruktionerna följer du dessa steg:
    1.  Klicka på **Översättningar**.
    2.  Klicka på **Lägg till** på sidan som visas.
    3.  I listan som visas väljer du det språk som du skriver texten i.
    4.  I fältet **Översatt text** anger du texten.
    5.  Om du vill anpassa texten kan du infoga platshållare. Se steg 3 för instruktioner om hur du anger en platshållare.
    6.  Klicka på **Stäng**.

## <a name="specify-when-this-workflow-is-used"></a>Ange när detta arbetsflöde ska användas
Du kan skapa flera arbetsflöden utifrån samma typ. Du kan till exempel skapa ett arbetsflöde för inköpsrekvisitioner för varje land/region som du har verksamhet i, exempelvis inköpsrekvisitioner för Danmark eller inköpsrekvisitioner för Spanien. Om du har flera arbetsflöden som är baserade på samma typ, måste du ange när respektive arbetsflöde ska användas. För föregående exempel anger du följande villkor:

-   Inköpsrekvisitioner för Danmark används när: land/region = DK:
-   Inköpsrekvisitioner för Spanien används när: land/region = ES:

Följ dessa steg för att ange när arbetsflödet som du konfigurerar ska användas.

1.  Klicka på **Aktivering** i det vänstra fönstret.
2.  Markera kryssrutan **Ange villkor för att köra detta arbetsflöde**.
3.  Klicka på **Lägg till villkor**.
4.  Ange ett villkor.
5.  Ange eventuellt ytterligare villkor som krävs.
6.  Följ dessa steg för att bekräfta att de villkor som du har angett har ställts in korrekt:
    1.  Klicka på **Ja**.
    2.  På sidan **Testa arbetsflödesvillkor**, i avsnittet **Testa arbetsflödesvillkoret**, markerar du en post.
    3.  Klicka på **Ja**. Systemet utvärderar posten i syfte att avgöra om den uppfyller villkoren som du har angett. Om du till exempel skapar ett arbetsflöde för inköpsrekvisition för Spanien, visar området **Validera villkor** på sidan en lista över inköpsrekvisitioner. När du klickar på **Testa** utför systemet en utvärdering av vald inköpsrekvisition för att kontrollera om land/region är ES.
    4.  När du vill återgå till sidan **Egenskaper** klickar du på **OK** eller på **Avbryt**.

## <a name="specify-when-notifications-are-sent"></a>Ange när meddelanden ska skickas
När ett dokument skickas in för bearbetning skapas en arbetsflödesinstans. Du kan skicka meddelanden till användarna när arbetsflödesinstanser som baseras på arbetsflödet har startats, slutförts, annullerats eller stoppats på grund av ett fel. Följ dessa steg för att ange när meddelanden ska skickas.

1.  Klicka på **Meddelanden** i det vänstra fönstret.
2.  Markera kryssrutan för varje händelse som ska utlösa meddelanden:
    -   **Startat** – Skicka meddelanden när en arbetsflödesinstans har startats.
    -   **Stoppat** – Skicka meddelanden när en arbetsflödesinstans har stoppats på grund av ett fel.
    -   **Slutfört** – Skicka meddelanden när en arbetsflödesinstans har slutförts.
    -   **Oåterkalleligt** – Skicka meddelanden när en arbetsflödesinstans har stoppats på grund av ett oåterkalleligt fel.
    -   **Avslutat** – Skicka meddelanden när en arbetsflödesinstans har avslutats.

3.  Välj raden för en händelse som du valde i steg 2.
4.  Ange meddelandetexten i fliken **Meddelandetext**.
5.  Om du vill anpassa texten kan du infoga platshållare. Platshållare ersätts med lämpliga data när texten visas för användarna. Följ dessa steg när du vill infoga en platshållare:
    1.  Klicka i fältet för att ange var platshållaren ska visas.
    2.  Klicka på **Infoga platshållare**.
    3.  Välj önskad platshållare i listan som visas.
    4.  Klicka på **Infoga**.

6.  Följ dessa steg för att lägga till översättningar av texten:
    1.  Klicka på **Översättningar**.
    2.  Klicka på **Lägg till** på sidan som visas.
    3.  I listan som visas väljer du det språk som du skriver texten i.
    4.  I fältet **Översatt text** anger du texten.
    5.  Om du vill anpassa texten kan du infoga platshållare. Se steg 5 för instruktioner om hur du anger en platshållare.
    6.  Klicka på **Stäng**.

7.  Använd följande alternativ för att, i fliken **Mottagare**, ange vem som ska få meddelandena.
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Alternativ</th>
    <th>Meddelandena skickas till dessa användare</th>
    <th>Följ dessa steg om du vill skicka meddelanden</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Deltagare</td>
    <td>Användare som tilldelas en specifik grupp eller roll</td>
    <td><ol>
    <li>Klicka på <strong>Deltagare</strong> i fliken <strong>Mottagare</strong>.</li>
    <li>Välj den typ av grupp eller roll som du vill skicka meddelanden till i fliken <strong>Rollbaserad</strong> i listan <strong>Deltagartyp</strong>.</li>
    <li>Välj den grupp eller roll som du vill skicka meddelanden till i listan <strong>Deltagare</strong>.</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>Användare av arbetsflöde</td>
    <td>Användare som är deltagare i detta arbetsflöde</td>
    <td><ol>
    <li>Klicka på <strong>Användare av arbetsflöde</strong> i fliken <strong>Mottagare</strong>.</li>
    <li>Välj en deltagare i detta arbetsflöde i fliken <strong>Användare av arbetsflöde</strong> i listan <strong>Användare av arbetsflöde</strong>.</li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td>Användare</td>
    <td>Specifika Finance and Operations-användare.</td>
    <td><ol>
    <li>Klicka på <strong>Användare</strong> i fliken <strong>Mottagare</strong>.</li>
    <li>Listan <strong>Tillgängliga användare</strong> i fliken <strong>Användare</strong> innehåller alla Finance and Operations-användare. Markera de användare som du vill skicka meddelanden till, och flytta sedan dessa till listan <strong>Markerade användare</strong>.</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  Upprepa stegen 3 till och med 7 för varje enskild händelse du valde i steg 2.

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a>Kommentera de ändringar som du har gjorts i arbetsflödet
Gör på följande sätt om du vill kommentera de ändringar som du har utfört i arbetsflödet.

1.  Klicka på **Noteringar** i det vänstra fönstret.
2.  Skriv dina kommentarer i fältet **Ange kommentarer om arbetsflödet**.
3.  Granska dina kommentarer. När du har lagt till kommentarer kan du inte ändra dem.
4.  Klicka på **Lägg till** för att lägga till dina kommentarer i området **Kommentarshistorik**.





