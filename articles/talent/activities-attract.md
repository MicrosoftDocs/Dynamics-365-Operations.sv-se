---
title: Aktiviteter i processerna
description: Det här avsnittet innehåller information om olika typer av aktiviteter som kan användas i anställningsprocesserna.
author: ''
manager: AnnBe
ms.date: 02/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: c32db1f563466f05b9fef1a03578392888c0b7e6
ms.sourcegitcommit: 1e32d78868098fd76124bb41363f15c4ec3ea15a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2019
ms.locfileid: "374767"
---
# <a name="activities-in-the-hiring-processes"></a>Aktiviteter i anställningsprocesserna

[!include[banner](../includes/banner.md)]

Aktiviteter kan läggas till som en del av anställningsprocessen i Microsoft Dynamics 365 for Talent: Attract. Aktiviteter kan läggas till en processmall eller kan läggas till direkt till anställningsprocessen i jobbet. När ett jobb har definierats måste en processmall markeras och de aktiviteter som ingår i mallen tillämpas på jobbet. Standardmallen används om en mall inte markerats. Anställningsprocessen kan också ändras för jobbet efter att mallen tillämpas.

> [!NOTE] 
> Processmallar finns i tillägget omfattande anställning.

## <a name="prospect-activity"></a>Potentiella kandidaters aktivitet

Potentiella kandidaters aktivitet styr om potentiella kandidater kan läggas till ett jobb. Som standard kan potentiella kandidaters läggas till ett jobb. Om du vill inaktivera Potentiella kandidaters aktivitet, ange alternativet **Aktivera potentiella kandidater** till **Av**. När Potentiella kandidaters aktivitet aktiveras kan anställande chefer lägga till och visa potentiella kandidater och fliken **Potentiella kandidater** visas på jobbet.

## <a name="application-activity"></a>Ansökningsaktivitet

Ansökningsaktiviteten krävs i anställningsprocessmallen. Om du vill skicka e-post till kandidater när de lämnar in sin ansökan eller läggs till i ansökningsfasen, ange alternativet **skicka e-post till kandidater** till **på**.

## <a name="interview-schedule-and-feedback-activity"></a>Tidsplanering av intervjuer och aktiviteten feedback

Den här aktiviteten har tre komponenter: kandidatens begäran om tillgänglighet, tidsplan och feedback. Använd aktiviteten intervju i jobbmallen om du vill inkludera sökandes begäran tillgänglighet schema och feedback som en del av en process istället för att använda dem som en del av Zayacs individuellt. Mer information finns i [Intervjuplanering och feedback](interview-scheduling-feedback.md).

## <a name="powerapps-activity"></a>PowerApps-aktivitet

PowerApps-aktiviteten låter dig bädda in en Microsoft PowerApps-app i din anställningsprocess. Appen kan krävas för alla sökande, endast interna sökande, endast externa sökande eller ingen sökande. Om appen har markerats som obligatorisk måste den slutföras innan fasen kan gå vidare. Om appen inte är markerad enligt vad som krävs, är aktiviteten ett valfritt steg och fasen kan gå vidare även om appen inte är slutförd.

Om du vill spara PowerApps-aktiviteten till anställningsprocessen måste du ange ett PowerApps-ID. PowerApps-ID finns i [PowerApps](https://web.powerapps.com), välj **appar** och välj sedan **information**.

Om du väljer alternativet **Tillåt lägga till deltagare för den här aktiviteten** kan ytterligare deltagare läggas till en ansökning som använder PowerApps-aktiviteten. Till exempel har en organisation skapat en PowerApps-app som är ett bibliotek med intervjufrågor för tekniska roller. Organisationen anställer nu nya programutvecklare och har lagt till PowerApps-aktiviteten till anställningsprocessen för rollen Programutvecklare. Om alternativet **Tillåt lägga till deltagare för den här aktiviteten** är valt, kan en rekryterarens eller anställande chef som tittar på en ansökande för rollen som programutvecklare lägga till personer till PowerApps-aktiviteten. Dessa personer kan sedan visa appen med intervjufrågorna.

> [!NOTE]
> PowerApps-aktiviteten är endast tillgänglig med tillägget för omfattande anställning.

## <a name="youtube-activity"></a>YouTube-aktivitet

YouTube-aktiviteten låter dig dela en YouTube-video som en del av din anställningsprocess. Om du vill spara YouTube-aktiviteten till anställningsprocessen måste du ange URL-adressen till YouTube-videon. När det gäller PowerApps-aktiviteten kan du tillåta deltagare att läggas till i aktiviteten. Om du väljer alternativet **Visa endast för kandidaten** visas endast videon som en del av kandidatens upplevelse. Den visas inte i anställningsprocessen i Attract.

> [!NOTE]
> YouTube-aktiviteten är endast tillgänglig med tillägget för omfattande anställning.

## <a name="web-content-activity"></a>Webbinnehållsaktivitet

Webbinnehållsaktivitet låter dig bädda in onlineinnehåll i din anställningsprocess. Om du vill spara webbinnehållsaktiviteten till anställningsprocessen måste du ange URL-adressen till innehållet. När det gäller PowerApps- och YouTube-aktiviteten kan du tillåta deltagare att läggas till i aktiviteten. Om du väljer alternativet **Visa endast för kandidaten** visas endast innehållet som en del av kandidatens upplevelse. Den visas inte i anställningsprocessen i Attract. Du kan välja storlek för innehållet som visas.

> [!NOTE]
> Webbinnehållsaktiviteten är endast tillgänglig med tillägget för omfattande anställning.

## <a name="microsoft-forms-activity"></a>Microsoft Forms-aktivitet

Microsoft Forms-aktiviteten låter dig bädda in en Microsoft Forms-formulär i din anställningsprocess. Microsoft Forms låter dig skapa frågeformulär, enkäter och röstningar. Om du vill spara Microsoft Forms-aktiviteten till anställningsprocessen måste du ange URL-adressen till formuläret. När det gäller PowerApps-, YouTube- och webbinnehållsaktiviteten kan du tillåta deltagare att läggas till i aktiviteten. Om du väljer alternativet **Visa endast för kandidaten** visas endast formuläret som en del av kandidatens upplevelse. Den visas inte i anställningsprocessen i Attract.

I Microsoft Forms kan författare ändra inställningarna så att användare utanför deras organisation kan svara på deras enkät eller frågesport. I så fall kan användare skicka in svar anonymt. Om du vill se vem som har fyllt i din enkät eller frågesport kan du kräva att svaranden anger sina namn som en del av undersökningen eller frågesporten.

> [!NOTE]
> Microsoft Forms-aktiviteten är endast tillgänglig med tillägget för omfattande anställning.
