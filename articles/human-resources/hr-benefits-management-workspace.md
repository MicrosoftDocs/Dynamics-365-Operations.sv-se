---
title: Arbetsyta för förmånshantering
description: I detta avsnitt beskrivs funktionen arbetsyta för förmånshantering i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 01/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 975b620dc911d154f6f67420a957bd72c02321ed
ms.sourcegitcommit: 6b013a423ed91973d60a895330046db2a07d92c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2022
ms.locfileid: "9472724"
---
# <a name="benefits-management-workspace"></a>Arbetsyta för förmånshantering

I detta avsnitt beskrivs funktionen arbetsyta för **förmånshantering** i Dynamics 365 Human Resources.

Arbetsytan **förmånshantering** ger dig en snabb översikt över fördelar som kräver din uppmärksamhet. På denna sida kan du se:

- Summor för artiklar som väntar på åtgärd
- Arbetare med obekräftade val
- Arbetare som nyligen registrerade sig till förmåner
- Arbetare med framtida livshändelser
- Nyanställningar som inte är registrerade
- Arbetare med aktiva livshändelser
- Arbetare med öppna anmälningar som inte har valt några planer

![Arbetsyta för förmånshantering.](./media/hr-benefits-management-workspace.png)

## <a name="view-action-items"></a>Visa åtgärdsobjekt

Du kan visa åtgärdsobjekten genom att välja en panel eller en flik. Om du väljer en flik kan du visa och välja arbetare från arbetsytan.

![Åtgärdsobjekt.](./media/hr-benefits-management-workspace-action-items.png)

Om du väljer en panel går du till sidan för det området. Om du till exempel väljer någon av dessa visas sidan **Arbetares förmånsplaner** filtrerat för medarbetare som du behöver vidta åtgärder för:

- **Obekräftade val**
- **Öppna registreringar utan utcheckade planer**
- **Registrerad för förmåner**
- **Nyanställd som inte registrerats**

![Förmånsplaner för medarbetare.](./media/hr-benefits-management-workspace-plans.png)

Om du väljer **Aktiva livshändelser** eller **Framtida livshändelser** kommer du till en lista över aktiva eller framtida händelser.

![Livshändelser.](./media/hr-benefits-management-workspace-life-events.png)

## <a name="processing"></a>Bearbetas

När du vill bearbeta anmälan, livscykelhändelser eller kursändringsuppdateringar markerar du lämpligt objekt i navigeringsfältet.

![Bearbetas.](./media/hr-benefits-management-workspace-processing.png)

Om du vill visa processresultaten, välj **Processresultat** på sidan.

![Processresultat.](./media/hr-benefits-management-workspace-process-results.png)

Mer information om förmånsbearbetning finns i:.

- [Bearbeta anmälningsberättigande](hr-benefits-process-enrollment-eligibility.md)
- [Bearbeta ändringar av livshändelser](hr-benefits-process-life-event-changes.md)
- [Bearbeta livshändelseberättigande](hr-benefits-process-life-event-eligibility.md)
- [Bearbeta livshändelser](hr-benefits-process-life-events.md)
- [Bearbeta ändringar av sats](hr-benefits-process-rate-changes.md)

## <a name="change-period"></a>Ändringsperiod

Om du vill visa en annan förmånsperiod väljer du den från listrutan **Period**.

![Ändringsperiod.](./media/hr-benefits-management-workspace-period.png)


## <a name="open-enrollment-tab"></a>Öppna fliken anmälan

Du kan visa åtgärdsobjekten genom att välja en panel eller en flik. Om du väljer en flik kan du visa och välja arbetare från arbetsytan.
Fliken **Öppen anmälan** innehåller nyckelmått för den öppna anmälningsprocessen. 

Information om öppen anmälan visas 30 dagar före **anmälans startdatum**. Detta definieras i inställningarna **Perioder** i **Hantering av förmåner** > **Länkar** > **Perioder**, i fältet **Anmälans startdatum**.  Om du vill ändra den här inställningen går du till **Delade Human Resources-parametrar** > **Hantering av förmåner** > **Alternativ för öppna anmälan** och uppdatera fältet **Antal**.  

Följande information finns på fliken **Öppen anmälan**:
 - Medarbetare som inte har startat den öppna anmälningsprocessen
 - Medarbetare som har förs in i arbete
 - Anställda som har genomfört valprocessen
 - Obekräftade val

**Sammanfattningsrutor**

- **Ej startat** – Panelen **Ej startat** visar ett antal anställda som inte har startat anmälningsprocessen. Panelen **Ej startat** är en filtrerad lista som endast visar de anställda som inte har några planer valda, avstått eller checkat ut under perioden för öppen anmälningsplan. Obligatoriska planer ignoreras och inkluderas inte eftersom de väljs som standard för medarbetaren.  Gå tillbaka till panelen om du vill visa en lista med medarbetare som inte har startat den öppna anmälningsprocessen på sidan **Arbetsförmånersplan**.

  > [!NOTE]
  > Om du inte vill spåra den öppna registreringsförloppet för en **Plantyp**, du kan exkludera den genom att gå till **Förmånshantering** > **Länkar** > **Anställdas självbetjäningsparametrar** > **Inställning av paneler för förmånsplaner** och uppdatera fältet **Spåra öppen anmälanförlopp**.  Du kanske till exempel har planer som skapats där **Plantyp** = **Övrigt**. Dessa planer kan vara valfria planer som du inte vill spåra anmälningsförloppet för. Om du inte väljer den här plantypen ignoreras planer av dessa typer när du spårar anmälningsförloppet eller när den slutförts på fliken **Öppen anmälan**. Den här inställningen gäller för den plantyp som valts för alla perioder och juridiska personer.

- **Pågår** – Panelen **Pågår** ger en inventering av anställda som har pågående val. Panelen **Pågår** är en filtrerad lista som endast visar anställda som har minst en plan som avstår eller väljs. Obligatoriska planer ignoreras och inkluderas inte eftersom de väljs som standard för medarbetaren. Du kan se detaljnivå från denna panel för att se de valda och avstängda planerna på sidan **Uppdatering av gruppuppdatering för arbetsförmånsplaner**.

- **Registrerad för förmåner** – Panelen **Registrerad för förmåner** ger ett antal anställda som är fullt inskrivna i förmåner. Panelen **Registrerad för förmåner** är en filtrerad lista som visar anställda som antingen har valt eller avstått från alla planer. Frågan exkluderar planer som inte spåras för öppen registrering på sidan **medarbetarnas självbetjäningsparametrar**. Du kan gå tillbaka från den här panelen om du vill visa en lista med medarbetare på sidan **Arbetsförmånsplaner**.

- **Obekräftade val** – Panelen **Obekräftade val** visar ett antal anställda som har planer som är utvalda eller avstängda och som behöver bekräftas. Du kan minskad detaljnivå från denna panel för att visa **Uppdatering av gruppuppdatering för arbetsförmånsplaner**.

**Aktivitet**

- **Ej startat** – Fliken **Ej startat** visar en lista med anställda som inte har startat anmälningsprocessen. Panelen **Ej startat** är en filtrerad lista som visar de anställda som inte har några planer valda, avstått eller checkat ut under perioden för öppen anmälningsplan. Obligatoriska planer ignoreras och inkluderas inte eftersom de väljs som standard för medarbetaren. Du kan gå nedåt på arbetaren om du vill visa detaljsidan **Förmånsplaner för medarbetare**.

- **Pågående val** – Fliken **Pågående val** visar en lista av anställda som har pågående val. Panelen **Pågående val** är en filtrerad lista som visar anställda som har minst en plan som avstår eller väljs. Obligatoriska planer ignoreras och inkluderas inte eftersom de väljs som standard för medarbetaren. Du kan gå nedåt på arbetaren om du vill visa detaljsidan **Förmånsplaner för medarbetare**.

## <a name="view-more-options"></a>Visa fler alternativ

Om du vill visa mer information eller ytterligare åtgärder väljer du **Länkar**.

![Länkar.](./media/hr-benefits-management-workspace-links.png)

## <a name="see-also"></a>Se även

[Hantering av förmåner – översikt](hr-benefits-management-overview.md)
