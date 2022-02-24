---
title: Visa sidor sida vid sida med funktionen Öppna i nytt fönster
description: Det här avsnittet beskriver hur du visar sidor sida vid sida.
author: aneesmsft
manager: AnnBe
ms.date: 11/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35ade352edf31fe895a9b9118a8ad7d5fe6c0bde
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798413"
---
# <a name="show-pages-side-by-side-using-the-open-in-new-window-feature"></a>Visa sidor sida vid sida med funktionen Öppna i nytt fönster

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du visar sidor sida vid sida.

Du kanske vill visa flera sidor sida vid sida för att slutföra uppgifter snabbt. Som ett exempel vill du kanske validera eller ange rader i mer än en journal. För att validera eller fylla i rader i mer än en journal måste du vanligen gå fram och tillbaka mellan sidan som visar en lista med journaler och sidan som visar rader för en viss journal. Funktionen **Öppna i nytt fönster** gör det dock möjligt att visa dessa sidor sida vid sida så att du kan utföra dina uppgifter snabbt.

Om vi fortsätter med exemplet ovan kan du klicka på ikonen **Öppna i nytt fönster** när du visar raderna.

[![Klicka på ikonen för Öppna i nytt fönster.](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png)

Om du klickar på ikonen **Öppna i nytt fönster** öppnas radsidan i en ny popup-webbläsare, och navigerar sedan den ursprungliga webbläsaren bakåt i historiken till sidan som visade listan med journaler. Du kan sedan visa båda sidorna sida vid sida. När du har visat en journal, kan du ändra den valda journalen på journallistsidan och radsidan i popup-fönstret visar automatiskt raderna i den nya valda journalen.

[![Du kan visa båda sidorna sida vid sida.](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png)

Den dynamiska länkningen och uppdateringen inträffar på grund av relationerna som finns mellan data bakom dessa sidor. Om systemet inte är medvetet om relationen mellan data, uppdateras inte popup-fönstret automatiskt som svar på en ändring i fönstret där det har sitt ursprung.

Vissa sidor har flera vyer, till exempel rutnät, huvudvy och detaljvy. Ikonen **Öppna i nytt fönster** gör att hela sidan öppnas i det nya webbläsarfönstret. Du kan därför inte behålla två vyer av samma sida som sida vid sida med funktionen **Öppna i nytt fönster**. Nästan alla sådana sidor har dock en navigeringslista som du kan använda för att växla mellan poster och uppnå en liknande effekt.

Innan du använder funktionen **Öppna i nytt fönster** måste du konfigurera webbläsarens blockering av popup-fönster till att tillåta popup-fönster från webbadressen för webbplatsen. Du kan exempelvis tillåta popup-fönster från "\*.dynamics.com".

Funktionen **Öppna i nytt fönster** är endast tillgänglig när det finns fler än en sida som är öppen i fönstret. Popup-fönstret stängs även automatiskt när det inte finns några fler öppna sidor (det vill säga när den sista sidan i det fönstret stängs.) Systemet stänger även öppna sidor när du navigerar till ett annat område i programmet. Om du har öppna popup-fönster och navigerar till ett annat område i programmet stängs därför popup-fönster automatiskt, eftersom sidorna i dessa fönster stängdes av systemet.

Det övre fältet i popup-fönster visar information om företaget som sidan öppnades i och är skrivskyddat. Popup-fönstren använder även de huvudsakliga webbläsarfönstret. Om huvudfönstret stängs eller uppdateras, blir alla öppna popup-fönster skrivskyddade. I det här fallet kan du fortfarande visa informationen i dessa fönster, men du kan inte interagera med den.
