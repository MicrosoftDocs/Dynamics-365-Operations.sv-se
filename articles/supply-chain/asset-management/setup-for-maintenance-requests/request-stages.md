---
title: Livscykeltillstånd för underhållsbegäran
description: I denna artikel beskrivs hur du konfigurerar livscykeltillstånd för underhållsbegäran i Tillgångshantering.
author: johanhoffmann
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetRequestLifecycleState, EntAssetRequestLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 81b30820adf11f0239ea8ff9d1886b5738e38162
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862726"
---
# <a name="maintenance-request-lifecycle-states"></a>Underhållsbegärans livscykeltillstånd

[!include [banner](../../includes/banner.md)]

 


Livscykeltillstånd för underhållsbegäran definierar stadier som en begäran kan gå igenom. Exempel är **skapad**, **aktiv** och **avslutad**. När en underhållsbegäran konverteras till en arbetsorder, bör livscykeltillstånd för underhållsbegäran uppdateras till **avslutad** eller **stängd** för att indikera att underhållsbegäran inte längre är aktiv. På listsidan **Alla underhållsbegäran** visas alla underhållsbegäran, oavsett livscykeltillstånd.

## <a name="set-up-maintenance-request-lifecycle-states"></a>Ställ in livscykeltillstånd för underhållsbegäran

1. Välj **Tillgångshantering** \> **inställningar** \> **underhållsbegäran** \> **livscykeltillstånd**.
2. Välj **ny** för att skapa ett livscykeltillstånd för underhållsbegäran.
3. I fältet **livscykeltillstånd** anger du ett ID för livscykeltillståndet.
4. Ange sedan ett namn i fältet **Namn**.

    På snabbfliken **Detaljer** visar fältet **livscykelmodeller** antalet livscykelmodeller för underhållsbegäran som använder det här livscykeltillståndet.

5. På snabbfliken **allmänt** anger du alternativet **aktiva** till **ja** om en underhållsbegäran ska vara aktiv medan den är i det här livscykeltillståndet.
6. Ange alternativet **Ange faktiskt slut** till **ja** om ett faktiskt slutdatum och en faktisk tid automatiskt ska anges i en underhållsbegäran i det här livscykeltillståndet.
7. Ange alternativet **skapa arbetsorder** till **ja** om en arbetsorder kan skapas från en underhållsbegäran i det här livscykeltillståndet.
8. Ange alternativet **ta bort** till **ja** om en underhållsbegäran kan tas bort när den är i det här livscykeltillståndet.
9. På snabbfliken **Uppdatera** är alternativen **inkommande** och **utgående** i avsnittet **tillgång** relevanta om du använder depåreparation. Ställ in rätt alternativ på **Ja** om tillgångens livscykeltillstånd för tillgångar som väljs i en begäran om underhåll bör uppdateras automatiskt till **inkommande** eller **utgående** när livscykeltillståndet för underhållsbegäran är inställt på **inkommande** eller **utgående**.

Följande illustration visar ett exempel på sidan **livscykeltillståndet för underhållsbegäran**.

![Sidan Livscykeltillstånd för underhållsbegäran.](media/02-setup-for-requests.png)

> [!NOTE]
> Livscykeltillstånd för underhållsbegäran, livscykeltillståndsgrupper och typer är relaterade till och används på samma sätt som livscykeltillstånd för arbetsorder, livscykeltillståndsgrupper och typer. 

## <a name="set-up-maintenance-request-lifecycle-models"></a>Ställ in livscykelmodeller för underhållsbegäran

När du har skapat de livscykeltillstånd som krävs för dina underhållsbegäranden kan de delas upp i livscykeltillståndsgrupper eller livscykelmodeller. Livscykelmodeller för underhållbegäran används för att skapa flödet som kan användas för olika typer av underhållbegäranden. Som ett minimum ska en standardlivscykelmodell för underhållsbegäran skapas.

1. Välj **Tillgångshantering** \> **inställningar** \> **underhållsbegäran** \> **livscykelmodell**.
2. Välj **ny** för att skapa en livscykelmodell för underhållsbegäran.
3. I fältet **livscykelmodell** anger du ett ID för livscykelmodell.
4. Ange sedan ett namn i fältet **Namn**.

    På snabbfliken **Detaljer** visar fältet **livscykeltillstånd** antalet livscykeltillstånd som väljs i den här livscykelmodellen. Fältet **underhållsbegärantyper** visar antalet underhållsbegärantyper som använder den här livscykelmodellen.

5. På snabbfliken **livscykeltillstånd** väljer du de livscykeltillstånd som ska inkluderas i livscykelmodellen.

    - Om du vill inkludera ett livscykeltillstånd i livscykelmodellen markerar du det i avsnittet **Återstående livscykeltillstånd** och väljer sedan höger pilknapp ![Högerpil.](media/03-setup-for-requests.png) för att flytta den till avsnittet **Valda livscykeltillstånd**.
    - Om du vill inkludera alla tillgängliga livscykeltillstånd i livscykelmodellen markerar du knappen **Välj alla tillgängliga tillstånd** ![Välj alla tillgängliga tillstånd.](media/04-setup-for-requests.png). Alla livscykeltillstånd flyttas till avsnittet **markerade livscykeltillstånd**.
    - Om du vill ta bort ett livscykeltillstånd från livscykelmodellen markerar du det i avsnittet **Valt livscykeltillstånd** och väljer sedan vänster pilknapp ![Vänsterpil.](media/05-setup-for-requests.png) för att flytta det till avsnittet **Återstående livscykeltillstånd**.

6. På snabbfliken **allmänt** är fälten i avsnittet **uppdateringar** relevanta om du använder depåreparation.

    - I den **livscykeltillstånd för mottagen tillgång** väljer du det livscykeltillstånd för tillgång som väljs på en underhållsbegäran ska uppdateras automatiskt när de tas emot för depåreparation.
    - I fältet **livscykeltillstånd för levererad tillgång** väljer du det livscykeltillstånd för tillgång som väljs på en underhållsbegäran ska uppdateras automatiskt när de returneras efter reparation.

Följande illustration visar ett exempel på sidan **livscykelmodeller för underhållsbegäran**.

![Sidan Livscykelmodeller för underhållsbegäran.](media/06-setup-for-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]