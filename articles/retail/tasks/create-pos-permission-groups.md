--- 
title: " Skapa kassabehörighetsgrupper"
description: "I den här proceduren visas hur du skapar en kassabehörighetsgrupp."
author: scott-tucker
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: b0c930e3722d1d0b1fff8efad7a785a153436b6d
ms.contentlocale: sv-se
ms.lasthandoff: 07/28/2017

---
# <a name="create-pos-permission-groups"></a> Skapa kassabehörighetsgrupper

[!include[task guide banner](../includes/task-guide-banner.md)]

I den här proceduren visas hur du skapar en kassabehörighetsgrupp. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USRT. Den här uppgiften är avsedd för rollen Driftchef (butik).

1. Gå till Behörighetsgrupper.
2. Klicka på Ny.
3. Skriv ett värde i fältet ID för kassabehörighetsgrupp.
4. Ange ett värde i fältet Beskrivning.
5. Välj Ja i fältet Visa stämpelklocksregistreringar.
    * Nu kan du aktivera eller avaktivera olika behörigheter för din kassabehörighetgrupp. För en del behörigheter kan du ange ett värde som ska användas för att bedöma om kassaanvändaren kan utföra åtgärden.  Den här uppgiftsguiden aktiverar några behörigheter som kan tilldelas en kassör.  
6. Välj Ja i fältet Tillåt att skapa order.
7. Välj Ja i fältet Tillåt att redigera order.
8. Välj Ja i fältet Tillåt att hämta order.
9. Välj Ja i fältet Tillåt att lösenordet ändras.
10. Välj Ja i fältet Tillåt hemlig stängning.
11. Klicka på Spara.
    * När ändringarna har sparats du behöver köra personalfördelningsschemat för att distribuera ändringarna till butikskanaler.  
12. Stäng sidan.
13. Gå till Jobb.
    * Nu tilldelar vi kassabehörighetgruppen till ett jobb.  
14. Hitta och markera önskad post i listan.
15. Klicka på länken på den valda raden i listan.
16. Klicka på Redigera.
17. Expandera avsnittet Jobbklassificering.
18. I fältet Kassabehörighetsgrupp, ange eller välj ett värde.
    * Alla arbetare i befattningar för det här jobbet ska använda den här kassabehörighetsgruppens inställningar, om inte arbetarnas kassabehörigheter har åsidosatts på deras befattningsnivå.  
19. Klicka på Spara.
    * När ändringarna har sparats du behöver köra personalfördelningsschemat för att distribuera ändringarna till butikskanaler.  


