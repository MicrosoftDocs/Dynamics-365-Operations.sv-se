---
title: " Skapa kassabehörighetsgrupper"
description: I den här proceduren visas hur du skapar en kassabehörighetsgrupp.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailPosPermissionGroup, HcmJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1b30c9a1d7fe4598695423ba700ebc88a794a49c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566374"
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

