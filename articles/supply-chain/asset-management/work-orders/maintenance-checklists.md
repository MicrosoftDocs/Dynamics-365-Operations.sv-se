---
title: Underhållschecklistor
description: Det här avsnittet beskriver hur du skapar underhållschecklistor i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderChecklist, EntAssetMobileWorkOrderLineChecklistDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b2ec7130fbe8c397c30cdc2a76f34ecfdfdc0737
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017928"
---
# <a name="maintenance-checklists"></a>Underhållschecklistor

[!include [banner](../../includes/banner.md)]



Underhållschecklistor ställs in på underhållsjobbtyper. Du fyller i checklistor för underhåll som en del av processen med att slutföra en arbetsorder. För mer information om hur du ställer in underhållschecklistor för underhållsjobbtyper på sidan **Standardvärden för underhållsjobbtyp**, se [Kategorier av underhållsjobbtyp och underhållsjobbtyper, varianter av underhållsjobb, yrkesgrenar för underhållsjobb och underhållschecklistor](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).

När du arbetar med underhållschecklistor på en arbetsorder kan du fylla i de fördefinierade underhållschecklistorna som är relaterade till underhållsjobbtyper. Du kan också lägga till fler underhållschecklistor.


## <a name="fill-in-a-maintenance-checklist"></a>Fyll i en underhållschecklista

1. Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Välj arbetsorder och sedan i åtgärdsfönstret på fliken **Arbetsorder** i gruppen **Rader** väljer du **Underhållschecklista**.

3. **Checklista för underhållsjobb för arbetsorder** visar checklistor för alla arbetsorderjobb. Om arbetsorderjobb har olika underhållsjobbtyper kan underhållschecklistorna vara olika för varje arbetsorderjobb. Välj ett arbetsorderjobb som ska användas med den relaterade underhållschecklistan. Detaljerad information om den valda checklisteraden för underhåll visas på snabbfliken **Radinformation**.

4. Slutför alla underhållschecklistor, en i taget, i den ordningsföljd som de visas. Du slutför en underhållschecklisterad genom att fylla i fälten på snabbfliken **Radinformation**. Informationen som krävs för att slutföra en rad kan variera, beroende på radtypen. På en rad av typen **Text** lägger du till en anteckning som förklarar resultatet av din kontroll. På en rad av typen **Mått** anger du räknarvärdet som du läser på utrustningen och du kan också lägga till en anteckning efter behov. En underhållschecklisterad av typen **sidhuvud** används som en rubrik för att gruppera raderna för underhållschecklista nedan. Du behöver inte fylla i ett sidhuvud. För alla andra typer av checklista för underhållsrader kan du lägga till en notering till en rad typen **sidhuvud**.

5. Om instruktioner är relaterade till en underhållschecklisterad är kryssrutan **Instruktioner** markerad. Läs instruktioner för den valda underhållschecklisteraden på fält **Instruktioner** på snabbfliken **Radinformation**.

6. När du har slutfört en underhållschecklista, markerar du kryssrutan **Kontrollerad** på raden för att markera den som slutförd. Om du vill ta bort en underhållschecklisterad eftersom den inte är relevant för arbetsorderjobbet markerar du kryssrutan **Inte tillämpligt** på raden. Om kryssrutan **obligatorisk** är markerad på en underhållschecklisterad måste du markera antingen kryssrutan **Markerad** eller kryssrutan **Inte tillämpligt**.

>[!NOTE]
>Du kan bara uppdatera registreringar av underhållschecklistor om arbetsordern befinner sig i [aktivt](../setup-for-work-orders/work-order-lifecycle-states.md) livscykeltillstånd.  


## <a name="add-a-maintenance-checklist-line"></a>Lägga till en underhållschecklisterad

Underhållschecklistor skapas från definitionen för standardtypen av underhållsjobbtypen och överförs till ett arbetsorderjobb. Vid behov kan du lägga till underhållschecklisterader i ett arbetsorderjobb. Referenslistor för underhåll som du lägger till manuellt får referensen **Manuell**.

1. På sidan **Checklista för underhållsjobb för arbetsorder** väljer du det arbetsorderjobb som du vill lägga till en underhållschecklista till.

2. På snabbfliken **Rader för underhållschecklista** väljer du en rad för underhållschecklista. Tryck sedan på **Nedpil** om du vill infoga en ny rad efter den markerade raden. Nästa nummer i serien infogas automatiskt i fältet **Radnummer**. Om du vill infoga en ny rad före den markerade raden väljer du **Lägg till rad**. 

3. Infoga ett namn på raden för underhållschecklista i fältet **Namn**.

4. Välj en typ för raden för underhållschecklista i fältet **Typ**. Snabbfliken **Radinformation** innehåller relaterade fält för varje typ av underhållschecklista.
    - **Text** - Använd den här typen om du vill lägga till en underhållschecklisterad som har text som beskriver vad som måste göras. Du kan till exempel använda den här typen om vill att en arbetare ska kontrollera eller inspektera något, men du inte förväntar dig ett specifikt (mätbart) resultat. När du har valt den här typen anger du på snabbfliken **detaljer om rader** i fältet **instruktioner** en text som beskriver vad som måste göras.
    - **Sidhuvud** - En underhållschecklisterad av den här typen används som en rubrik för att gruppera raderna för underhållschecklista nedan. Den här typen är användbar om du har flera rader för underhållschecklista som kan delas in i specifika områden. När du har valt den här typen anger du ett beskrivande namn i fältet **Namn**.
    - **Mall** - Den här typen kan inte användas när du lägger till en rad för underhållschecklista manuellt på ett arbetsorderjobb.  
    - **Variabel** - Använd den här typen för att definiera ett möjligt resultat i ett intervall på en rad för underhållschecklista. För information om hur du ställer in variabler för underhållschecklistor finns i [Kategorier av underhållsjobbtyp och underhållsjobbtyper, varianter av underhållsjobb, yrkesgrenar för underhållsjobb och underhållschecklistor](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md). När du har valt den här typen anger du ett beskrivande namn för variabeln i fältet **Namn**. På snabbfliken **Information om rader** i fältet **variabel** väljer du variabeln. I fältet **Instruktioner** anger du en text som beskriver vad som måste göras.
    - **Mått** – Använd den här typen för att registrera ett specifikt mått på underhållschecklisteraden. När du har valt den här typen anger du ett namn för måttet i fältet **Namn**. På snabbfliken **Raddetaljer** i fälten **räknare** och **enhet** anger du lämpliga värden. I fältet **Instruktioner** anger du en text som beskriver vad som måste göras.

5. När du har lagt till raderna för underhåll manuellt fyller du i raderna enligt beskrivningen i avsnittet **Fyll i en underhållschecklista** ovan.

>[!NOTE]
>På sidan **Checklista för underhållsjobb för arbetsorder** kan du inte ta bort rader för underhållschecklista som har referensen **Jobbtyp**. Du kan bara radera rader för underhållschecklista som du eller andra underhållsarbetare har skapat manuellt och som har referensen **Manuell**.

Bilden nedan visar ett exempel på en underhållschecklista.

![Figur 1](media/14-work-orders.png)

