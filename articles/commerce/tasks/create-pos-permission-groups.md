---
title: Skapa kassabehörighetsgrupper
description: Denna artikel förklarar hur du skapar en kassabehörighetsgrupp.
author: josaw1
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.industry: Retail
ms.search.form: RetailPosPermissionGroup, HcmJob
ms.openlocfilehash: 0aa394e5dc6685954c31cdddae7cdc042b80af29
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277971"
---
# <a name="create-pos-permission-groups"></a>Skapa kassabehörighetsgrupper

[!include [banner](../includes/banner.md)]

Denna artikel förklarar hur du skapar en kassabehörighetsgrupp. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USRT. Den här uppgiften är avsedd för rollen Driftchef (handel).

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
