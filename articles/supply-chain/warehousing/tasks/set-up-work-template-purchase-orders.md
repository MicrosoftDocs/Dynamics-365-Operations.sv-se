---
title: Ställa in en arbetsmall för inköpsorder
description: I denna artikel beskrivs hur du konfigurerar en enkel arbetsmall som ska användas när mottagna artiklar inlagras.
author: Mirzaab
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkTemplateTable, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee6bc896a979c326001e1596e4a463753005fabf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877375"
---
# <a name="set-up-a-work-template-for-purchase-orders"></a>Ställa in en arbetsmall för inköpsorder

[!include [banner](../../includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar en enkel arbetsmall som ska användas när mottagna artiklar inlagras. Arbetsmallar bestämmer instruktionsuppsättning som visas för lagerställearbetaren på en mobil enhet när artiklar flyttas från inleveransområdet. Du kan använda den här proceduren med uppgifterna i demonstrationsföretaget USMF. Innan du startar guiden skapar du ett arbetspool-id. I det här exemplet används arbetspool-id:t Inkommande. Den här proceduren är avsedd för lagerchefen.

1. I navigeringsfönstret, gå till **Moduler > Lagerstyrning > Inställningar > Arbete > Arbetsmallar**.
2. Välj **Inköpsorder** i fältet **Typ av arbetsorder**.

## <a name="create-a-work-template-header"></a>Skapa ett arbetsmallshuvud
1. Välj **Ny**.
2. Ange ett nummer i fältet **Sekvensnummer**. I den här sekvensen utvärderas arbetsmallen. Du kan ändra sekvensen vid behov.  
3. Skriv ett värde i fältet **Arbetsmall.** Detta är den unika identifieraren för mallen.  
4. Skriv ett värde i fältet **Beskrivning av arbetsmall.**
    - Alternativet **Giltig** markeras inte förrän du har fyllt i all information som krävs av mallen och valt **Spara**.  
    - En arbetsorder av typen **Inköpsorder** kan inte bearbetas automatiskt, så lämna alternativet **Bearbeta automatiskt** med värdet **Nej**.  
5. Skriv ett värde i fältet **ID för arbetspool.** Id:n för arbetspooler gör att du kan strukturera arbetsuppgifter i grupper. Det värde som du som anges här är det förvalda värdet för alla arbetsuppgifter som skapas med den här mallen.  
6. Ange `1` i fältet **Arbetsprioritet**. Detta indikerar värdet för arbetsuppgiften och värdet du anger här är standardinställningen för alla arbetsuppgifter som skapas med hjälp av den här mallen.  
7. Välj **Spara**. Du måste spara arbetsmallhuvudet för att knappen **Redigera fråga** ska bli tillgänglig.  

## <a name="set-up-the-query-for-the-work-template"></a>Ställa in frågan för arbetsmallen
1. Välj **Redigera fråga**. Vi anger en begränsning som innebär att mallen bara kan användas på ett specifikt lagerställe.  
2. Markera **Lägg till**.
3. I fältet **Fält** för den nya raden, ange `warehouse`.
4. I fältet **Kriterier** skriver du ett värde.
5. Välj **OK**.
6. Välj **Ja**.

## <a name="set-work-template-details"></a>Ställa in arbetsmallinformation
1. Välj **Ny**.
2. I fältet **Arbetstyp**, välj **Välj**.
3. I fältet **Arbetsklass-ID**, skriv `purchase`. Arbetsklassen att du som anges här är standardinställningen i alla arbetsrader av typen Välj som skapas med den här mallen. Arbetsklassen kan inte ersättas av arbetsorderraderna. Arbetsklasser används för att begränsa och/eller styra typen arbetsorderrader som en lagerställemedarbetare kan behandla på en mobil enhet.  
4. Välj **Ny**.
5. Välj **Placera** i fältet **Arbetstyp**.
6. Ange ett värde i fältet **Arbetsklass-ID**. Instruktionerna för plock och plats är en uppsättning. Varje plock/platsuppsättning måste ha samma arbetsklass. Använda samma arbetsklass som du gjorde i plockinstruktionen.  
7. Välj **Spara**. Observera att kryssrutan **Giltig** nu är markerad.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]