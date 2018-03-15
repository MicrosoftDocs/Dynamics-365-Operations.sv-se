--- 
title: " Skapa kassabehörighetsgrupper"
description: "I den här proceduren visas hur du skapar en kassabehörighetsgrupp."
author: scott-tucker
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: bcda7c3a5c2cc97fbc6e4945e4d5f0ec42a7a478
ms.contentlocale: sv-se
ms.lasthandoff: 02/07/2018

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


