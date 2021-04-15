---
title: Skapa kassabehörighetsgrupper
description: Det här avsnittet förklarar hur du skapar en kassabehörighetsgrupp.
author: scott-tucker
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailPosPermissionGroup, HcmJob
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1d4634ec275d3d1c2a131c4c1d61cc983e485b14
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798499"
---
# <a name="create-pos-permission-groups"></a>Skapa kassabehörighetsgrupper

[!include [banner](../includes/banner.md)]

Det här avsnittet förklarar hur du skapar en kassabehörighetsgrupp. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USRT. Den här uppgiften är avsedd för rollen Driftchef (handel).

1. I navigeringsfönstret, gå till **Moduler > Butik och handel > Medarbetare > Behörighetsgrupper**.
2. Välj **Ny**.
3. Skriv ett värde i fältet **ID för kassabehörighetsgrupp**.
4. I fältet **Beskrivning** anger du ett värde.
5. Välj **Ja** i fältet **Visa stämpelklocksregistreringar**. Nu kan du aktivera eller avaktivera olika behörigheter för din kassabehörighetgrupp. För en del behörigheter kan du ange ett värde som ska användas för att bedöma om kassaanvändaren kan utföra åtgärden. Den här uppgiftsguiden aktiverar några behörigheter som kan tilldelas en kassör.  
6. Välj **Ja** i fältet **Tillåt att skapa order**.
7. Välj **Ja** i fältet **Tillåt att redigera order**.
8. Välj **Ja** i fältet **Tillåt att hämta order**.
9. Välj **Ja** i fältet **Tillåt att lösenordet ändras**.
10. Välj **Ja** i fältet **Tillåt hemlig stängning**.
11. Välj **Spara**. När ändringarna har sparats du behöver köra personalfördelningsschemat för att distribuera ändringarna till handelskanaler. 
12. I navigeringsfönstret, gå till **Moduler > Personal > Jobb > Jobb**.
13. Nu tilldelar vi kassabehörighetgruppen till ett jobb. Hitta och markera önskad post i listan.
14. Välj **Redigera**.
15. Expandera avsnittet **Jobbklassificering**.
16. I fältet Kassabehörighetsgrupp, ange eller välj ett värde. Alla arbetare i befattningar för det här jobbet ska använda den här kassabehörighetsgruppens inställningar, om inte arbetarnas kassabehörigheter har åsidosatts på deras befattningsnivå.  
17. Välj **Spara**. När ändringarna har sparats du behöver köra personalfördelningsschemat för att distribuera ändringarna till kanaler.  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]