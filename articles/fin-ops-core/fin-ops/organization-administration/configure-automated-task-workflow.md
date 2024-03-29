---
title: Konfigurera automatiska uppgifter i ett arbetsflöde
description: I den här artikeln beskrivs hur du konfigurerar egenskaperna för en automatisk uppgift.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192061
ms.assetid: c0aceb57-b5e6-4ef3-91e7-89a21c9f048a
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b482338c436ea9226d31f74c823ee1dc141b24cd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891765"
---
# <a name="configure-automated-tasks-in-a-workflow"></a>Konfigurera automatiska uppgifter i ett arbetsflöde

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

I den här artikeln beskrivs hur du konfigurerar egenskaperna för en automatisk uppgift.

Högerklicka på uppgiften och klicka sedan på **Egenskaper** för att öppna sidan **Egenskaper** om du vill konfigurera en automatisk uppgift i arbetsflödesredigeraren. Använd sedan följande procedurer när du vill konfigurera egenskaperna för den automatiska uppgiften.

## <a name="name-the-task"></a>Ange ett namn på uppgiften

Följ dessa steg när du vill ange ett namn för den automatiska uppgiften.

1. Klicka på **Grundinställningar** i det vänstra fönstret.
2. I fältet **Namn** anger du ett unikt namn för uppgiften.

## <a name="specify-when-notifications-are-sent"></a>Ange när meddelanden ska skickas

Du kan skicka meddelanden till andra personer när en automatisk uppgift har körts eller annullerats. Följ dessa steg för att ange när meddelanden skickas och vem de skickas till.

1. Klicka på **Meddelanden** i det vänstra fönstret.
2. Markera kryssrutan bredvid händelserna för att skicka meddelanden för:

    - **Utförande** – Meddelanden skickas när uppgiften har körts.
    - **Annullerad** – Meddelanden skickas när uppgiften har annullerats.

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
    <li>Välj den grupp eller roll som du vill skicka meddelanden till i listan <strong>Deltagare</strong>.</li>
    </ol>
    </td>
    </tr>
    <tr>
    <td>Användare av arbetsflöde</td>
    <td>Användare som deltar i det aktuella arbetsflödet</td>
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]