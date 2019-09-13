---
title: Skapa kassabehörighetsgrupper
description: Det här avsnittet förklarar hur du skapar en kassabehörighetsgrupp.
author: scott-tucker
manager: AnnBe
ms.date: 08/20/2019
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
ms.openlocfilehash: 4e6782c60aa659523775cc6c4eb1694430a4bf4f
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914841"
---
# <a name="create-pos-permission-groups"></a>Skapa kassabehörighetsgrupper

[!include[task guide banner](../includes/task-guide-banner.md)]

Det här avsnittet förklarar hur du skapar en kassabehörighetsgrupp. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USRT. Den här uppgiften är avsedd för rollen Driftchef (butik).

1. I navigeringsfönstret, gå till **Moduler > Butik > Medarbetare > Behörighetsgrupper**.
2. Välj **Ny**.
3. Skriv ett värde i fältet **ID för kassabehörighetsgrupp**.
4. I fältet **Beskrivning** anger du ett värde.
5. Välj **Ja** i fältet **Visa stämpelklocksregistreringar**. Nu kan du aktivera eller avaktivera olika behörigheter för din kassabehörighetgrupp. För en del behörigheter kan du ange ett värde som ska användas för att bedöma om kassaanvändaren kan utföra åtgärden. Den här uppgiftsguiden aktiverar några behörigheter som kan tilldelas en kassör.  
6. Välj **Ja** i fältet **Tillåt att skapa order**.
7. Välj **Ja** i fältet **Tillåt att redigera order**.
8. Välj **Ja** i fältet **Tillåt att hämta order**.
9. Välj **Ja** i fältet **Tillåt att lösenordet ändras**.
10. Välj **Ja** i fältet **Tillåt hemlig stängning**.
11. Välj **Spara**. När ändringarna har sparats du behöver köra personalfördelningsschemat för att distribuera ändringarna till butikskanaler. 
12. I navigeringsfönstret, gå till **Moduler > Personal > Jobb > Jobb**.
13. Nu tilldelar vi kassabehörighetgruppen till ett jobb. Hitta och markera önskad post i listan.
14. Välj **Redigera**.
15. Expandera avsnittet **Jobbklassificering**.
16. I fältet Kassabehörighetsgrupp, ange eller välj ett värde. Alla arbetare i befattningar för det här jobbet ska använda den här kassabehörighetsgruppens inställningar, om inte arbetarnas kassabehörigheter har åsidosatts på deras befattningsnivå.  
17. Välj **Spara**. När ändringarna har sparats du behöver köra personalfördelningsschemat för att distribuera ändringarna till butikskanaler.  

