---
title: Lägg till aktiviteter till en anställningsprocess
description: Det här avsnittet innehåller information om olika typer av aktiviteter som du kan lägga till i anställningsprocesserna i Microsoft Dynamics 365 Talent - Attract.
author: hasrivas
manager: AnnBe
ms.date: 05/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: ce8c0bd74a41b9857538b37d0875583d06e8c11d
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124783"
---
# <a name="add-activities-to-a-hiring-process"></a>Lägg till aktiviteter till en anställningsprocess

[!include [banner](includes/banner.md)]

Aktiviteter kan läggas till som en del av anställningsprocessen i Microsoft Dynamics 365 Talent: Attract. Aktiviteter kan läggas till en processmall eller kan läggas till direkt till anställningsprocessen i jobbet. När ett jobb har definierats måste en processmall markeras och de aktiviteter som ingår i mallen tillämpas på jobbet. Standardmallen används om en mall inte markerats. Anställningsprocessen kan också ändras för jobbet efter att mallen tillämpas.

> [!NOTE] 
> Processmallar finns i tillägget omfattande anställning. Mer information finns i [vilken version av Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="prospect-activity"></a>Potentiella kandidaters aktivitet

Potentiella kandidaters aktivitet styr om potentiella kandidater kan läggas till ett jobb. Som standard kan potentiella kandidaters läggas till ett jobb. Om du vill inaktivera Potentiella kandidaters aktivitet, ange alternativet **Aktivera potentiella kandidater** till **Av**. När Potentiella kandidaters aktivitet aktiveras kan anställande chefer lägga till och visa potentiella kandidater och fliken **Potentiella kandidater** visas på jobbet.

> [!NOTE]
> Om du vill att kandidater ska kunna läggas till ett jobb från LinkedIn måste du ange alternativet **aktivera potentiella kunder** till **på**.

## <a name="application-activity"></a>Ansökningsaktivitet

Ansökningsaktiviteten krävs i anställningsprocessmallen. Om du vill skicka e-post till kandidater när de lämnar in sin ansökan eller läggs till i ansökningsfasen, ange alternativet **skicka e-post till kandidater** till **på**.

## <a name="interview-schedule-and-feedback-activity"></a>Tidsplanering av intervjuer och aktiviteten feedback

Den här aktiviteten har tre komponenter: kandidatens begäran om tillgänglighet, tidsplan och feedback. Använd aktiviteten intervju i jobbmallen om du vill inkludera sökandes begäran tillgänglighet schema och feedback som en del av en process istället för att använda dem som en del av Zayacs individuellt. Mer information finns i [Intervjuplanering och feedback](interview-scheduling-feedback.md).

## <a name="power-apps-activity"></a>Power Apps-aktivitet

Power Apps-aktiviteten låter dig bädda in en Microsoft Power Apps-app i din anställningsprocess. Appen kan krävas för alla sökande, endast interna sökande, endast externa sökande eller ingen sökande. Om appen har markerats som obligatorisk måste den slutföras innan fasen kan gå vidare. För att anses vara klar måste fältet **JobApplicationStatus** ställas in på **Slutförd**. Det här fältet finns i entiteten JobApplicationActivity så att Power Apps-appar måste uppdatera fältet innan fasen kan avancera. Om appen inte är markerad enligt vad som krävs, är aktiviteten ett valfritt steg och fasen kan gå vidare även om appen inte är slutförd.

Om du vill spara Power Apps-aktiviteten till anställningsprocessen måste du ange ett Power Apps-ID. För att hitta Power Apps-ID, gå till [Power Apps](https://web.powerapps.com), välj **Appar** och välj sedan **Information**.

Som standard är Power Apps-aktiviteten tillgänglig för anställande chef, rekryteraren och deras ombud. Om du väljer alternativet **Tillåt lägga till deltagare för den här aktiviteten** kan ytterligare deltagare från anställningsteamet läggas till en ansökning som använder Power Apps-aktiviteten. Till exempel har en organisation skapat en Power Apps-app som är ett bibliotek med intervjufrågor för tekniska roller. Organisationen anställer nu nya programutvecklare och har lagt till Power Apps-aktiviteten till anställningsprocessen för rollen Programutvecklare. Om alternativet **Tillåt lägga till deltagare för den här aktiviteten** är valt, kan en rekryterarens eller anställande chef som tittar på en ansökande för rollen som programutvecklare lägga till intervjuare till Power Apps-aktiviteten. Dessa personer kan sedan visa appen med intervjufrågorna.

> [!NOTE]
> Power Apps-aktiviteten är endast tillgänglig med tillägget för omfattande anställning. Mer information finns i [vilken version av Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="youtube-activity"></a>YouTube-aktivitet

YouTube-aktiviteten låter dig dela en YouTube-video som en del av din anställningsprocess. Om du vill spara YouTube-aktiviteten till anställningsprocessen måste du ange URL-adressen till YouTube-videon. Du kan visa innehållet på **anställningsteamet**, **endast interna kandidater**, **endast externa kandidater** eller **alla kandidater**. När det gäller Power Apps-aktiviteten kan du tillåta deltagare från anställningsteam att läggas till i aktiviteten. Om du väljer att visa innehållet för kandidater visas videon endast som en del av kandidatens erfarenhet och inte i anställningsprocessen.

> [!NOTE]
> YouTube-aktiviteten är endast tillgänglig med tillägget för omfattande anställning. Mer information finns i [vilken version av Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="web-content-activity"></a>Webbinnehållsaktivitet

Webbinnehållsaktivitet låter dig bädda in onlineinnehåll i din anställningsprocess. Om du vill spara webbinnehållsaktiviteten till anställningsprocessen måste du ange URL-adressen till innehållet. Du kan visa innehållet på **anställningsteamet**, **endast interna kandidater**, **endast externa kandidater** eller **alla kandidater**. När det gäller Power Apps- och YouTube-aktiviteten kan du tillåta deltagare från anställningsteam att läggas till i aktiviteten. Om du väljer att visa innehållet för kandidater visas webbinnehållet endast som en del av kandidatens erfarenhet och inte i anställningsprocessen. Du kan välja storlek för innehållet som visas.

> [!NOTE]
> Webbinnehållsaktiviteten är endast tillgänglig med tillägget för omfattande anställning. Mer information finns i [vilken version av Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="microsoft-forms-activity"></a>Microsoft Forms-aktivitet

Microsoft Forms-aktiviteten låter dig bädda in en Microsoft Forms-aktivitet i din anställningsprocess. Microsoft Forms låter dig skapa frågeformulär, enkäter och röstningar. Om du vill spara Microsoft Forms-aktiviteten till anställningsprocessen måste du ange URL-adressen till formuläret. Du kan visa innehållet på **anställningsteamet**, **endast interna kandidater**, **endast externa kandidater** eller **alla kandidater**. När det gäller Power Apps-, YouTube- och webbinnehållsaktiviteter kan du tillåta deltagare från anställningsteam att läggas till i aktiviteten. Om du väljer att visa innehållet för kandidater visas formuläret endast som en del av kandidatens erfarenhet och inte i anställningsprocessen.

I Microsoft Forms kan författare ändra inställningarna så att användare utanför deras organisation kan svara på deras enkät eller frågesport. I så fall kan användare skicka in svar anonymt. Om du vill se vem som har fyllt i din enkät eller frågesport kan du kräva att svaranden anger sina namn som en del av undersökningen eller frågesporten.

> [!NOTE]
> Microsoft Forms-aktiviteten är endast tillgänglig med tillägget för omfattande anställning. Mer information finns i [vilken version av Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

## <a name="offer-activity"></a>Erbjudandeaktivitet

Anställningsprocessmallen kräver erbjudandeaktiviten. Om du vill använda appen för integrerad erbjudandehantering, ange **Starta appen erbjudandehantering för förberedelse av erbjudande** till **På**. Om den här inställningen är inaktiverad visas inte kandidaten i erbjudandeappen måste du manuellt spåra uppdateringar till kandidatens erbjudandeaktivitet. Om du vill definiera om anställningschefer kan förbereda erbjudandet för kandidaten i erbjudandeappen anger du **Anställande chefer kan förbereda erbjudande** till **På**. Om jobbet har flera befattningar kopplade till det kan du bestämma om du vill förbereda flera erbjudanden mot samma befattningsnummer. Om du endast vill tillåta ett erbjudande per befattning per jobb, ange **Tillåt att befattningar återanvänds inom ett jobb** till **Av**.

> [!NOTE]
> Appen för integrerad erbjudandehantering är endast tillgänglig med tillägget för omfattande anställning. Mer information finns i [vilken version av Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).


