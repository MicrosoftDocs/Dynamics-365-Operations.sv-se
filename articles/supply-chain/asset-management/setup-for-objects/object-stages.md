---
title: Livscykeltillstånd för tillgångar
description: Det här avsnittet beskriver livscykeltillstånd för tillgångar och livscykelmodeller i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetLifecycleModelStateNext, EntAssetObjectLifecycleState, EntAssetLifecycleStateUpdate, EntAssetObjectLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 566036c6361194d910a0fc34bd5d72147585ec4f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437574"
---
# <a name="asset-lifecycle-states"></a>Tillgångs livscykeltillstånd

[!include [banner](../../includes/banner.md)]

 

Det här avsnittet beskriver livscykeltillstånd för tillgångar och livscykelmodeller i tillgångshantering. Tillgångs livscykeltillstånd används för att definiera om tillgången är aktiv eller inaktiv. Du kan till exempel ställa in tillgångs livscykeltillstånd som **skapad**, **aktiv** och **avslutad**.

> [!NOTE]
> - Begär livscykeltillstånd är länkade till livscykeltillstånd för tillgångar. Därför när en begäran ändras till ett nytt livscykeltillstånd ändras tillgången som är kopplad till begäran till ett nytt livscykeltillstånd för tillgångar. Om livscykeltillståndet för en begäran till exempel ändras till **inkommande** ändras livscykeltillståndet för den kopplade tillgången till det livscykeltillstånd som har valts i fältet **inkommande livscykeltillstånd** på snabbfliken **Livscykeltillstånd för tillgångar** på sidan **Livscykelmodeller för tillgångar**. 


Livscykeltillstånd för tillgångar kan ställas in i livscykelmodeller för tillgångar där du kan definiera de nödvändiga livscykeltillstånden för olika typer av tillgångar. Du ställer först in livscykeltillstånd. Sedan skapar du en livscykelmodell och väljer livscykeltillstånd för den.

1. Välj **tillgångshantering** \> **inställningar** \> **tillgångar** \> **livscykeltillstånd**.
2. Skapa ett nytt livscykeltillstånd för tillgångar genom att välja **Nytt**.
3. I fältet **livscykeltillstånd** anger du ett ID för livscykeltillståndet.
4. Ange en beskrivning i fältet **Namn**.

    Fältet **livscykelmodeller** antalet livscykelmodeller för tillgångar som använder det här livscykeltillståndet för tillgångar.

5. Ange alternativet **aktiva** till **ja** om det här livscykeltillståndet ska vara ett aktivt livscykeltillstånd (med andra ord om arbetsorder kan skapas för tillgångar som är i det här livscykeltillståndet).
6. Ange alternativet **ta bort öppna kalenderrader** till **ja** om öppna tillgångskalenderrader som har livscykeltillståndet för tillgångar **skapad** ska tas bort när de är i det här livscykeltillståndet. Den här inställningen är användbar om du vill rensa alla öppna underhållsscheman som inte längre är relevanta för tillgången (till exempel om tillgången inte längre är aktiv).

> [!NOTE]
> Livscykeltillstånd för tillgångar, livscykelmodeller för tillgångar och tillgångstyper är relaterade. De används på samma sätt som livscykeltillstånd för arbetsorder, livscykelmodeller för arbetsorder och arbetsordertyper. 


När du har skapat de nödvändiga livscykeltillstånden för tillgångar kan du ställa in livscykeltillstånd i tillgångens livscykelmodeller.

1. Välj **tillgångshantering** \> **inställningar** \> **tillgångar** \> **livscykelmodeller**.
2. Skapa en ny livscykelmodell för tillgångar genom att välja **Nytt**.
3. I fältet **livscykelmodell** anger du ett ID för livscykelmodell.
4. Ange en beskrivning i fältet **Namn**.

    Fältet **livscykeltillstånd** antalet livscykeltillstånd för tillgångar som väljs i den här livscykelmodellen för tillgångar. Fältet **tillgångstyper** visar antalet tillgångstyper som använder den livscykelmodellen.

5. På snabbfliken **livscykeltillstånd** väljer du de livscykeltillstånd för tillgångar som ska inkluderas i livscykelmodellen för tillgångar.

    - Om du vill använda ett livscykeltillstånd för modellen väljer du den i avsnittet **återstående livscykeltillstånd** och markerar sedan högerpilknappen ![högerpil](media/15-setup-for-objects.png) för att flytta den till avsnittet **Valt livscykeltillstånd**.
    - Om du vill använda alla tillgängliga livscykeltillstånd förmodellen markerar du knappen **Alla alla tillgängliga livscykeltillstånd** knappen ![Alla alla tillgängliga livscykeltillstånd](media/20-setup-for-objects.png). Alla livscykeltillstånd flyttas till avsnittet **markerade livscykeltillstånd**.
    - Om du vill ta bort ett livscykeltillstånd i livscykelmodellen markerar du avsnittet **valda livscykeltillstånd** och markerar sedan vänsterpilknappen ![vänsterpil](media/16-setup-for-objects.png) för att flytta den till avsnittet **Återstående livscykeltillstånd**.

6. Välj **uppdateringar av livscykeltillstånd** för att definiera vilka livscykeltillstånd för tillgångar som kan följa ett valt livscykeltillstånd.
7. Du kan använda snabbfliken **tillgångstillstånd** om du hanterar tillgångar som du tar emot för reparation. I avsnittet **inkommande/utgående** kan du välja livscykeltillstånd för tillgångar för att indikera arbetsflödet för en tillgång som du tar emot för reparation. Om du erbjuder lånetillgångar till kunder eller avdelningar kan du i avsnittet **lån** välja livscykeltillstånd för lånetillgångar.
