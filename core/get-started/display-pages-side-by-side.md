---
title: "Visa sidor sida vid sida med ikonen Öppna i nytt fönster"
description: "Denna artikel förklarar hur du visar sidor sida vid sida i Microsoft Dynamics 365 for Operations."
author: aneesmsft
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e29d436560590e844e92180a6d1e2ad53d019662
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="display-pages-side-by-side-using-the-open-in-new-window-icon"></a>Visa sidor sida vid sida med ikonen Öppna i nytt fönster

[!include[banner](../includes/banner.md)]


Denna artikel förklarar hur du visar sidor sida vid sida i Microsoft Dynamics 365 for Operations.

Microsoft Dynamics 365 for Operations hjälper dig att utföra uppgifter effektivt. I vissa fall vill du kanske visa flera sidor sida vid sida för att slutföra uppgifter snabbt. Som ett exempel vill du kanske validera eller ange rader i mer än en journal. För att göra detta måste vanligen du gå fram och tillbaka mellan sidan som visar en lista med journaler och sidan som visar rader för en viss journal. Funktionen **Öppna i nytt fönster** gör det dock möjligt att visa dessa sidor sida vid sida så att du kan utföra dina uppgifter snabbt. Om vi fortsätter med exemplet ovan kan du klicka på ikonen **Öppna i nytt fönster** när du visar raderna. [![open-in-new-window-icon](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png) Klicka på ikonen **Öppna i nytt fönster** för att öppna radsidan i en ny popup-webbläsare, varefter den ursprungliga webbläsaren navigerar tillbaka i historiken till sidan som visar listan med journaler. Du kan sedan visa båda sidorna sida vid sida. När du är klar med att visa en journal, kan du ändra den valda journalen på journallistsidan och radsidan i popup-fönstret visar automatiskt raderna i den nya valda journalen. [![visa-sidor-sida-vid-sida](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png) Den dynamiska länkningen och uppdateringen inträffar på grund av relationerna som finns mellan datan bakom dessa sidor. Om systemet inte är medvetet om relationen mellan data, uppdateras inte popup-fönstret automatiskt som svar på en ändring i fönstret där det har sitt ursprung. Vissa sidor har flera vyer, till exempel rutnät, huvudvy och detaljvy. Ikonen **Öppna i nytt fönster** gör att hela sidan öppnas i det nya webbläsarfönstret. Du kan därför inte behålla två vyer av samma sida som sida vid sida med funktionen **Öppna i nytt fönster**. Nästan alla sådana sidor har dock en navigeringslista som du kan använda för att växla mellan poster och uppnå en liknande effekt. Innan du använder funktionen **Öppna i nytt fönster** bör du konfigurera webbläsarens popup-blockerare så att denna tillåter popup-fönster från Dynamics 365 for Operations-webbplatsen. Du kan exempelvis tillåta popup-fönster från "\*.dynamics.com". Funktionen **Öppna i nytt fönster** är endast tillgänglig när det finns fler än en sida som är öppen i fönstret. Popup-fönstret stängs även automatiskt när det inte finns några fler öppna sidor (det vill säga när den sista sidan i det fönstret stängs.) Dynamics 365 for Operations stänger också öppna sidor när du navigerar till ett annat område i programmet. Om du har öppna popup-fönster och navigerar till ett annat område i programmet stängs därför popup-fönster automatiskt, eftersom sidorna i dessa fönster stängdes av systemet. Det övre fältet i popup-fönster visar information om företaget som sidan öppnades i och är skrivskyddat. Popup-fönster beror också på huvudwebbläsarfönstret för Dynamics 365 for Operations. Om huvudfönstret stängs eller uppdateras, blir alla öppna popup-fönster skrivskyddade. Det innebär att du fortfarande kan visa informationen i dessa fönster, men du kan inte interagera med den.




