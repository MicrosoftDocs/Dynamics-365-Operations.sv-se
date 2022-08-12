---
title: Registrera förbrukning
description: Denna artikel innehåller förklaringar av hur du registrerar förbrukning i Tillgångshantering.
author: johanhoffmann
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderJournal, EntAssetWorkOrderAddSparePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 729ef6aae228ad1e528945031567b92c44cdf256
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111767"
---
# <a name="register-consumption"></a>Registrera förbrukning

[!include [banner](../../includes/banner.md)]

 

När ett underhållsjobb har slutförts på en arbetsorder är nästa steg att göra förbrukningsregistreringar och bokföra journalerna. Du kan göra registreringar av följande förbrukningstyper: timmar, artiklar och utgifter. De olika förbrukningstyperna registreras och bokförs på **Arbetsorderjournaler**. Journalinställningarna i **Tillgångshantering** används för att skapa och bokföra separata journaler för timmar, artiklar och utgifter i modulen **Projekthantering och redovisning**.

I vissa fall kanske kan lägga till eller ta bort prognosrader på en arbetsorder. Inställningen av en livscykeltillstånd för arbetsorder, den relaterade projekttypen och de fasregler som gäller för projekttypen bestämmer om du kan lägga till eller redigera journalrader. Mer information om livscykeltillstånd för arbetsorder och relaterade projektfaser finns i [Prognoser, arbetsorder och projekt](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).

>[!NOTE]
>Det är möjligt att konfigurera automatisk bokföring av journaler i ett livscykeltillstånd för arbetsorder. Mer information finns i [Livscykeltillstånd för arbetsorder](../setup-for-work-orders/work-order-lifecycle-states.md).

1. Klicka på **Tillgångshantering** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Välj arbetsorder och klicka på **Journaler**.

3. Klicka på **Kopiera från prognos** om du vill överföra alla prognosrader som kan kopplas till arbetsordern. Du kan välja vilka förbrukningstyper du vill överföra.

4. Om det behövs kan du lägga till fler förbrukningsrader på relevant snabbflik genom att klicka på **Lägg till rad** och fylla i data på raden.

5. Klicka på **Validera journaler** om du vill validera journalraderna före bokföring.

6. Klicka på **Bokför journaler** för att bokföra journalraderna.

7. När du har bokfört förbrukningsjournalerna kan du uppdatera livscykelstadiet för arbetsorder. Om du till exempel vill ange att arbetsordern har slutförts, kan du uppdatera livscykel stadiet till "avslutad".

    - I fältet **Visa** som placerades högst upp på sidan **Arbetsorderjournaler** väljer du vilka journalrader som ska visas: **alla**, **inte bokförda** eller **bokförda**. Bokförda journaler är markerade i kryssrutan **Bokförd**.  
    - När artikelrader skapas i arbetsorderjournalen överförs automatiskt produktdimensioner och spårningsdimensioner som är relaterade till artikeln till journalraden.  

På bilden nedan visas ett exempel på tim- och artikelregistreringar i en arbetsorder i **Arbetsorderjournaler**.

![Figur 1.](media/01-consumption.png)


## <a name="split-hours-on-work-orders-with-several-work-order-jobs"></a>Dela timmar på arbetsorder med flera arbetsorderjobb

Om en arbetsorder innehåller flera jobb för arbetsorder kan du registrera arbetstimmar med funktionen **Dela timmar**, vilket innebär att en timregistreringsrad kan fördelas jämnt på varje arbetsorderjobb.

1. Klicka på **Tillgångshantering** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.

2. Välj arbetsorder och klicka på **Journaler**.

3. Välj den timregistreringsrad som du vill dela och klicka på **Dela timmar**.

4. I dialogrutan **Dela timmar på underhållsjobb för arbetsorder** visas namnet på den arbetare som är inloggad i automatiskt i fältet **Arbetare**. Om det behövs kan du välja en annan arbetare.

5. Välj en kategori för timregistreringen i fältet **Kategori**.

6. Infoga antal arbetstimmar som ska delas i fältet **Timmar**.

    ![Figur 2.](media/02-consumption.png)

7. Klicka på **OK**.

*Exempel:* På bilden nedan visas journalrader för en arbetsorder som innehåller tre arbetsorderjobb. Den första raden, som innehåller tre arbetstimmar, har delats upp och en arbetstimme har registrerats för varje arbetsorderjobb. När de tre timregistreringsraderna har skapats, bestämmer du vad du ska göra med den ursprungliga timregistreringsraden (den första raden i exemplet). Du kan behålla den som den är eller ta bort den. 

![Figur 3.](media/03-consumption.png)

## <a name="financial-dimensions-on-consumption-registrations"></a>Ekonomiska dimensioner för förbrukningsregistreringar

När du gör förbrukningsregistreringar läggs ekonomiska dimensioner som hör till de olika registreringstyperna till i registreringarna i en specifik sekvens. 

- *Tim- och utgiftsregistrering:* Först läggs ekonomiska dimensioner från journalhuvudet till, om det finns några. Därefter läggs ekonomiska dimensioner från det relaterade arbetsorderprojektet till. Slutligen läggs ekonomiska dimensioner från resursen (arbetaren) till.

- *Artikelregistreringar:* Först läggs ekonomiska dimensioner från journalhuvudet till, om det finns några. Därefter läggs ekonomiska dimensioner från det relaterade arbetsorderprojektet till. Därefter läggs ekonomiska dimensioner från webbplatsen till. Slutligen läggs ekonomiska dimensioner från artikeln till.

>[!NOTE]
>För alla tre registreringstyperna valideras kombinationen av ekonomisk dimension, och ogiltiga kombinationer görs tomma. Detta är standardinställningar med andra appar för ekonomi och drift.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
