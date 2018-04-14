--- 
title: "Ställ in en arbetsmall för inköpsorder"
description: "I den här proceduren fokuseras på inställningarna av en enkel arbetsmall som ska användas när mottagna artiklar inlagras."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fbbe019bdca2d5182466a20370418a14032fe63d
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-a-work-template-for-purchase-orders"></a>Ställ in en arbetsmall för inköpsorder

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren fokuseras på inställningarna av en enkel arbetsmall som ska användas när mottagna artiklar inlagras. Arbetsmallar bestämmer instruktionsuppsättning som visas för lagerställearbetaren på en mobil enhet när artiklar flyttas från inleveransområdet. Du kan använda den här proceduren med uppgifterna i demonstrationsföretaget USMF. Innan du startar guiden skapar du ett arbetspool-id. I det här exemplet används arbetspool-id:t Inkommande. Den här proceduren är avsedd för lagerchefen.

1. Gå till Lagerstyrning > Inställningar > Arbete > Arbetsmallar.
2. Välj Inköpsorder i fältet Typ av arbetsorder.

## <a name="create-a-work-template-header"></a>Skapa ett arbetsmallshuvud
1. Klicka på Ny.
2. Ange ett nummer i fältet Sekvensnummer.
    * I den här sekvensen utvärderas arbetsmallen. Du kan ändra sekvensen vid behov.  
3. Skriv ett värde i fältet Arbetsmall.
    * Detta är den unika identifieraren för mallen.  
4. Skriv ett värde i fältet Beskrivning av arbetsmall.
    * Alternativet Giltig markeras inte förrän du har fyllt i all information som krävs av mallen och klickat på Spara.  
    * En arbetsorder av typen Inköpsorder kan inte bearbetas automatiskt, så lämna alternativet Bearbeta automatiskt med värdet Nej.  
5. Skriv ett värde i fältet ID för arbetspool.
    * Id:n för arbetspooler gör att du kan strukturera arbetsuppgifter i grupper. Det värde som du som anges här är det förvalda värdet för alla arbetsuppgifter som skapas med den här mallen.  
6. Ange 1 i fältet Arbetsprioritet.
    * Detta indikerar värdet för arbetsuppgiften och värdet du anger här är standardinställningen för alla arbetsuppgifter som skapas med hjälp av den här mallen.  
7. Klicka på Spara.
    * Du måste spara arbetsmallhuvudet för att knappen Redigera fråga ska bli tillgänglig.  

## <a name="set-up-the-query-for-the-work-template"></a>Ställa in frågan för arbetsmallen
1. Klicka på Redigera fråga.
    * Vi anger en begränsning som innebär att mallen bara kan användas på ett specifikt lagerställe.  
2. Klicka på Lägg till.
3. Markera vald rad i listan.
4. Skriv lagerställe i fältet Fält.
5. Ange ett värde i fältet Kriterier.
6. Klicka på OK.
7. Klicka på Ja.

## <a name="set-work-template-details"></a>Ställa in arbetsmallinformation
1. Klicka på Ny.
2. Välj Välj i fältet Arbetstyp.
3. Skriv inköp i fältet Arbetsklass-ID.
    * Arbetsklassen att du som anges här är standardinställningen i alla arbetsrader av typen Välj som skapas med den här mallen. Arbetsklassen kan inte ersättas av arbetsorderraderna. Arbetsklasser används för att begränsa och/eller styra typen arbetsorderrader som en lagerställemedarbetare kan behandla på en mobil enhet.  
4. Klicka på Ny.
5. Välj Placera i fältet Arbetstyp.
6. Skriv ett värde i fältet Arbetsklass-ID.
    * Instruktionerna för plock och plats är en uppsättning. Varje plock/platsuppsättning måste ha samma arbetsklass. Använda samma arbetsklass som du gjorde i plockinstruktionen.  
7. Klicka på Spara.
    * Observera att kryssrutan Giltig nu är markerad.  


