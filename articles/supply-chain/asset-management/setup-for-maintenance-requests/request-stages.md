---
title: Livscykeltillstånd för underhållsbegäran
description: I det här avsnittet beskrivs hur du ställer in livscykeltillstånd för underhållsbegäran i tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 07/26/2019
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
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 151db9ca8a121759e39b690ec296b36a18dc1729
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571172"
---
# <a name="maintenance-request-lifecycle-states"></a>Underhållsbegärans livscykeltillstånd

[!include [banner](../../includes/banner.md)]

 


Livscykeltillstånd för underhållsbegäran definierar stadier som en begäran kan gå igenom. Exempel är **skapad**, **aktiv** och **avslutad**. När en underhållsbegäran konverteras till en arbetsorder, bör livscykeltillstånd för underhållsbegäran uppdateras till **avslutad** eller **stängd** för att indikera att underhållsbegäran inte längre är aktiv. På listsidan **Alla underhållsbegäran** visas alla underhållsbegäran, oavsett livscykeltillstånd.

## <a name="set-up-maintenance-request-lifecycle-states"></a>Ställ in livscykeltillstånd för underhållsbegäran

1. Välj **tillgångshantering** \> **inställningar** \> **underhållsbegäran** \> **livscykeltillstånd**.
2. Välj **ny** för att skapa ett livscykeltillstånd för underhållsbegäran.
3. I fältet **livscykeltillstånd** anger du ett ID för livscykeltillståndet.
4. Ange sedan ett namn i fältet **Namn**.

    På snabbfliken **Detaljer** visar fältet **livscykelmodeller** antalet livscykelmodeller för underhållsbegäran som använder det här livscykeltillståndet.

5. På snabbfliken **allmänt** anger du alternativet **aktiva** till **ja** om en underhållsbegäran ska vara aktiv medan den är i det här livscykeltillståndet.
6. Ange alternativet **Ange faktiskt slut** till **ja** om ett faktiskt slutdatum och en faktisk tid automatiskt ska anges i en underhållsbegäran i det här livscykeltillståndet.
7. Ange alternativet **skapa arbetsorder** till **ja** om en arbetsorder kan skapas från en underhållsbegäran i det här livscykeltillståndet.
8. Ange alternativet **ta bort** till **ja** om en underhållsbegäran kan tas bort när den är i det här livscykeltillståndet.
9. På snabbfliken **uppdatera** är alternativen **inkommande** och **utgående** i avsnittet **tillgång** relevanta om du använder depåreparation. Ange lämpligt alternativ till **ja** om tillgången livscykeltillstånd för tillgångar som väljs för underhållsbegäran ska uppdateras automatiskt till **inkommande** eller **utgående** när livscykeltillståndet för underhållsbegäran är inställt på **inkommande** eller **utgående**.

Följande illustration visar ett exempel på sidan **livscykeltillståndet för underhållsbegäran**.

![Sidan Underhållsbegärans livscykeltillstånd](media/02-setup-for-requests.png)

> [!NOTE]
> Livscykeltillstånd för underhållsbegäran, livscykeltillståndsgrupper och typer är relaterade till och används på samma sätt som livscykeltillstånd för arbetsorder, livscykeltillståndsgrupper och typer. 

## <a name="set-up-maintenance-request-lifecycle-models"></a>Ställ in livscykelmodeller för underhållsbegäran

När du har skapat de livscykeltillstånd som krävs för dina underhållsbegäranden kan de delas upp i livscykeltillståndsgrupper eller livscykelmodeller. Livscykelmodeller för underhållbegäran används för att skapa flödet som kan användas för olika typer av underhållbegäranden. Som ett minimum ska en standardlivscykelmodell för underhållsbegäran skapas.

1. Välj **tillgångshantering** \> **inställningar** \> **underhållsbegäran** \> **livscykelmodell**.
2. Välj **ny** för att skapa ett livscykelmodell  för underhållsbegäran.
3. I fältet **livscykelmodell** anger du ett ID för livscykelmodell.
4. Ange sedan ett namn i fältet **Namn**.

    På snabbfliken **Detaljer** visar fältet **livscykeltillstånd** antalet livscykeltillstånd som väljs i den här livscykelmodellen. Fältet **underhållsbegärantyper** visar antalet underhållsbegärantyper som använder den här livscykelmodellen.

5. På snabbfliken **livscykeltillstånd** väljer du de livscykeltillstånd som ska inkluderas i livscykelmodellen.

    - Om du vill inkludera ett livscykeltillstånd i livscykelmodellen markerar du avsnittet **återstående livscykeltillstånd** och markerar sedan högerpilknappen ![högerpil](media/03-setup-for-requests.png) för att flytta den till avsnittet **Valt livscykeltillstånd**.
    - Om du vill inkludera alla tillgängliga livscykeltillstånd i livscykelmodellen markerar du knappen **Välj alla tillgängliga tillstånd** knappen ![Välj alla tillgängliga tillstånd](media/04-setup-for-requests.png). Alla livscykeltillstånd flyttas till avsnittet **markerade livscykeltillstånd**.
    - Om du vill ta bort ett livscykeltillstånd i livscykelmodellen markerar du avsnittet **valda livscykeltillstånd** och markerar sedan vänsterpilknappen ![vänsterpil](media/05-setup-for-requests.png) för att flytta den till avsnittet **Återstående livscykeltillstånd**.

6. På snabbfliken **allmänt** är fälten i avsnittet **uppdateringar** relevanta om du använder depåreparation.

    - I den **livscykeltillstånd för mottagen tillgång** väljer du det livscykeltillstånd för tillgång som väljs på en underhållsbegäran ska uppdateras automatiskt när de tas emot för depåreparation.
    - I fältet **livscykeltillstånd för levererad tillgång** väljer du det livscykeltillstånd för tillgång som väljs på en underhållsbegäran ska uppdateras automatiskt när de returneras efter reparation.

Följande illustration visar ett exempel på sidan **livscykelmodeller för underhållsbegäran**.

![Sidan Livscykelmodeller för underhållsbegäran](media/06-setup-for-requests.png)
