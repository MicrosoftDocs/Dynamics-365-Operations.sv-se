---
title: "Ställa in säkerhet för Kostnadsredovisningsanalys Power BI-innehåll"
description: "Det här avsnittet beskrivs hur du kan sprida säkerheten i kostnadsredovisning till radnivå säkerhet i Microsoft Power BI-åtkomstnivå. Dessa funktioner hjälper till att säkerställa att användare bara se Power BI data som de har beviljats åtkomst till."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 270294
ms.assetid: 3a7ba8b0-ac57-4159-9cd8-4308f6021f36
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 1e42622e7621c645d7eda3299f78c34c7e41a251
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-security-for-the-cost-accounting-analysis-power-bi-content"></a>Ställa in säkerhet för Kostnadsredovisningsanalys Power BI-innehåll

Det här avsnittet beskrivs hur du kan sprida säkerheten i kostnadsredovisning till radnivå säkerhet i Microsoft Power BI-åtkomstnivå. Dessa funktioner hjälper till att säkerställa att användare bara se Power BI data som de har beviljats åtkomst till.

<a name="overview"></a>Översikt
--------

Den **Kostnadsredovisningsanalys** Microsoft Power BI innehåll används Power BI radnivå säkerhet för att begränsa åtkomsten för en användare. Säkerheten baseras på-åtkomstnivå organisationshierarkin som har ställts in i parametrar för kostnadsredovisning. Mer information om den **Kostnadsredovisningsanalys** Power BI innehåll, se [Kostnadsredovisningsanalys Power BI innehåll](cost-accounting-analysis-content-pack.md).

## <a name="setup"></a>Inställningar
Om du vill sprida åtkomst på resursnivå till Power BI måste Power BI innehållets ägare instruktionerna. **Anmärkning:** användare publicerar den **Kostnadsredovisningsanalys** Power BI innehåll blir automatiskt ägare. Endast en ägare kan ställa in säkerhet i Power BI. Dessutom tills ägaren läggs till andra användare på PowerBI.com, ingen utom ägaren kan se alla data i den **Kostnadsredovisningsanalys** Power BI-innehåll.

1.  Publicera definitionsfilen till Power BI.
2.  Logga in på PowerBI.com.
3.  Hitta datauppsättning för den **Kostnadsredovisningsanalys** Power BI-innehåll.
4.  Öppna säkerhetssidan. 

    [![Öppna säkerhetssidan](https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-1.png)](https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-1.png)

5.  Den **kostnad objektet controller** roll redan har skapats. Lägga till andra medlemmar som ingår i kostnadsredovisning-åtkomstnivå organisationshierarkin. 

    [![Lägga till medlemmar](https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-2.png)](https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-2.png)

Användare som läggs till i **kostnad objektet controller** roll visas endast de data som de får visas enligt definitionen i kostnadsredovisning-åtkomstnivå organisationshierarki. **Anmärkning:** säkerhet på användarnivå som berör brickor och rapporter i Microsoft Dynamics 365 för operationer som är inbäddade från Power BI.

## <a name="updating-security"></a>Uppdatera säkerhet
Om uppdateringar görs i access säkerhetsnivå i kostnadsredovisningen, och du vill Power BI som återspeglar uppdateringarna, måste du uppdatera entiteten butiken för den **Kostnadsredovisningsanalys** Power BI-innehåll. När du har slutfört enhet butiken uppdateringen från Dynamics 365 för operationer måste du uppdatera artefakter på PowerBI.com. Mer information om hur du gör en entitet butiken uppdatering finns [uppdatering enhet butiken](power-bi-integration-entity-store.md#update-entity-store). Ägaren av den **Kostnadsredovisningsanalys** Power BI innehåll måste också göra en entitet butiken uppdatering om nya användare beviljas åtkomst till organisationshierarkin. Dessutom ägare lägga till nya användare till den **kostnad objektet controller** roll i PowerBI.com, så tillämpas för denna säkerhet på radnivå.

## <a name="disabling-security"></a>Inaktivera säkerhet
Utgår vi från att din organisation vill begränsa åtkomst till data. Om du av någon anledning säkerhetsparametrar är inaktiverade när du kör en kostnadsredovisning kan ägaren måste lägga till den **kostnad revisorn** roll i Power BI istället. Om du ändrar säkerhet från ett aktiverade tillstånd till inaktiverad, är det en bra idé att ta bort användare från den **kostnad objektet controller** roll. Och tvärtom när du aktiverar säkerhet igen. Användare kan tillhöra båda rollerna. Gemensam tillgång är unionen av båda rollerna. I fråga om den **Kostnadsredovisningsanalys** Power BI innehåll visas användare som har gemensam tillgång har obegränsad åtkomst till data. Om målet är att använda begränsad åtkomst användarna måste ha tilldelats till endast den **kostnad objektet controller** roll. Dessa säkerhetsuppdateringar på radnivå börjar gälla omedelbart. Berörda användarna uppdatera sina webbläsare.

## <a name="additional-resources"></a>Ytterligare resurser
Mer information om säkerhet för Power BI radnivå finns [hantera säkerheten på din modell i Power BI](https://powerbi.microsoft.com/en-us/documentation/powerbi-admin-rls/#manage-security-on-your-model).


