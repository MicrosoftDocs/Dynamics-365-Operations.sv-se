---
title: Underhållschecklistor
description: Det här avsnittet beskriver hur du skapar underhållschecklistor i tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 325ff1fa0811d6aac5189cc69f21483fce6b3e8f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875909"
---
# <a name="maintenance-checklists"></a>Underhållschecklistor


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Underhållschecklistor ställs in på underhållsjobbtyper och används när du arbetar på en arbetsorder. Att fylla i checklistor för underhåll utgör en del av arbetet med att slutföra en arbetsorder. Se avsnittet [ Kategorier av underhållsjobbtyp och underhållsjobbtyper, varianter av underhållsjobb, yrkesgrenar för underhållsjobb och underhållschecklistor](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md) för mer information om hur du ställer in underhållschecklistor i underhållsjobbtyper i formuläret **Standardvärden för underhållsjobbtyp**.

När du arbetar med underhållschecklistor på en arbetsorder kan du fylla i de fördefinierade underhållschecklistorna som är relaterade till underhållsjobbtyper. Det går också att lägga till ytterligare underhållschecklistor.

## <a name="fill-out-a-maintenance-checklist"></a>Fyll i en underhållschecklista

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Välj arbetsorder och klicka på **Underhållschecklista**.

3. I **Checklista för underhållsjobb för arbetsorder** visas underhållschecklistor för alla arbetsorderjobb. Om arbetsorderjobb har olika underhållsjobbtyper kan underhållschecklistorna vara olika för varje arbetsorderjobb. Välj ett arbetsorderjobb som ska användas med den relaterade underhållschecklistan. Detaljerad information om den valda checklisteraden för underhåll visas på snabbfliken **Radinformation**.

4. Slutför alla underhållschecklistor, en i taget, i den ordningsföljd som de visas. En underhållschecklisterad av typen "Sidhuvud" används som en rubrik för att gruppera raderna för underhållschecklista nedan. Du måste inte fylla i ett sidhuvud, men för alla radtyper för underhållschecklistor är det möjligt att lägga till en **notering** i huvudet.

5. Om instruktioner är relaterade till en underhållschecklisterad är kryssrutan **Instruktioner** markerad. Läs instruktioner för den valda underhållschecklisteraden på snabbfliken **Radinformation** > avsnittet **Instruktioner**.

6. Den information som krävs för att slutföra en underhållschecklista kan variera beroende på den relaterade typen av underhållschecklista. Du slutför en underhållschecklisterad genom att fylla i fälten på snabbfliken **Radinformation**. På en rad av typen "Text" lägger du till exempel till en **notering** som förklarar vad resultatet av checklisteraden är. På en rad av typen "Mått" lägger du till det **räknarvärde** som du läser på utrustningen, och du kan också lägga till en **notering** om det behövs.

- När du har slutfört en underhållschecklista, markerar du kryssrutan **Kontrollerad** på raden för att markera den som slutförd. Om du vill ta bort en underhållschecklisterad eftersom den inte är relevant för arbetsorderjobbet markerar du kryssrutan **Inte tillämpligt** på raden. Om en underhållschecklisterad är markerad som **obligatorisk** måste du markera den som antingen "Kontrollerad" eller "Inte tillämpligt".  
- Du kan bara uppdatera registreringar av underhållschecklistor om arbetsordern befinner sig i [aktivt](../setup-for-work-orders/work-order-lifecycle-states.md) livscykeltillstånd.  


## <a name="add-a-maintenance-checklist-line"></a>Lägga till en underhållschecklisterad

Underhållschecklistor skapas från definitionen för standardtypen av underhållsjobbtypen och överförs till ett arbetsorderjobb. Vid behov kan du lägga till underhållschecklisterader i ett arbetsorderjobb. Manuellt tillagda underhållschecklisterader hämtar referensen "Manuell".

1. I **Checklista för underhållsjobb för arbetsorder** väljer du det arbetsorderjobb som du vill lägga till en underhållschecklista till.

2. Välj en underhållschecklisterad på snabbfliken **Rader för underhållschecklista** och tryck på nedåtpil på tangentbordet om du vill lägga till en ny rad efter den valda checklisteraden. Nästa nummer i serien infogas automatiskt i fältet **Radnummer**. Du kan också välja en rad för underhållschecklista och klicka på knappen **Lägg till rad** om du vill infoga en ny rad ovanför den valda checklisteraden.

3. Infoga ett namn på raden för underhållschecklista i fältet **Namn**.

4. Välj en typ för raden för underhållschecklista i fältet **Typ**. För varje typ av underhållschecklista visas relaterade fält på snabbfliken **Radinformation**.  
  a. "Text" används för att lägga till en rad för underhållschecklista med en textbeskrivning av vad du ska göra. Den här typen av underhållschecklista kan användas om du vill att en arbetare ska kontrollera eller inspektera något, utan att förvänta sig ett specifikt (mätbart) resultat. Infoga en beskrivning av vad du ska göra i avsnittet **Instruktioner** på snabbfliken **Radinformation**. b. "Sidhuvud" används som en rubrik för att gruppera de rader för underhållschecklista som visas under huvudet. Det är användbart om du har flera rader för underhållschecklista som kan delas in i specifika områden. Infoga ett beskrivande namn i fältet **Namn**.  
  c. "Mall" kan inte användas när du lägger till en rad för underhållschecklista manuellt på ett arbetsorderjobb.  
  d. "Variabel" används för att definiera ett möjligt resultat i ett intervall på en rad för underhållschecklista. Inställningen av variabler för underhållschecklistor beskrivs i [Kategorier av underhållsjobbtyp och underhållsjobbtyper, varianter av underhållsjobb, yrkesgrenar för underhållsjobb och underhållschecklistor](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md). Infoga ett namn för att beskriva variabeln i fältet **Namn**. Välj variabeln i fältet **Variabel**. Infoga en beskrivning av vad du ska göra i avsnittet **Instruktioner** på snabbfliken **Radinformation**.  
  e. "Mått" används för att registrera ett specifikt mått. Infoga ett namn för måttet i fältet **Namn**. På snabbfliken **Radinformation** väljer du **Räknare** och **Enhet**. Infoga en beskrivning av vad du ska göra i avsnittet **Instruktioner**.  

5. När du har lagt till raderna för underhållschecklista manuellt fyller du i raderna enligt beskrivningen i ovanstående avsnitt.

>[!NOTE]
>I **Checklista för underhållsjobb för arbetsorder** kan du inte ta bort rader för underhållschecklista som har referensen "Jobbtyp". Du kan bara radera rader för underhållschecklista med referensen "Manuell", som du eller andra underhållsarbetare har skapat manuellt.


![Figur 1](media/14-work-orders.png)

