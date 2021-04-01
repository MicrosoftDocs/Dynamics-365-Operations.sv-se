---
title: Ändra arbetspool för arbete
description: I det här avsnittet beskrivs hur du kan använda knappen Ändra arbetsgrupp för arbetsuppgifter när du vill ändra arbetsgrupp för befintligt arbete.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPool,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 61b988cf2501812e940f726e02d8fc1bcee2c035
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233065"
---
# <a name="change-work-pool-on-work"></a>Ändra arbetspool för arbete

[!include [banner](../includes/banner.md)]

Du kan använda arbetspooler för att strukturera arbete i grupper. Du kan till exempel skapa en arbetspool för att klassificera arbete som uppstår på ett visst lagerställe.

Med funktionen *Ändra arbetspool för arbete* lägger till en knapp **Ändra arbetspool** i åtgärdsfönstret för arbetsuppgifter. Därför kan lagerchefer enkelt ändra arbetsgruppen för befintligt arbete. Med hjälp av den här funktionen reagerar våra chefer snabbt på ändringar på verkstadsgolvet och förbättrar deras förmåga att anpassa sig till att ändra situationer och behovet att överföra arbete till en annan arbetsgrupp.

## <a name="turn-on-the-change-work-pool-on-work-feature"></a>Aktivera funktionen ändra arbetspool för arbete

Innan du börjar ställa in eller använda den här funktionen måste du se till att den är tillgänglig i ditt-system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionens namn:** *Ändra arbetspool för arbete*

## <a name="set-up-the-change-work-pool-on-work-feature"></a>Ange funktionen ändra arbetspool för arbete

Om du vill använda den här funktionen måste du ha ställt in vissa arbetspooler. Du kan också ställa in arbetsmallarna så att de tilldelar en pool automatiskt. Om du vill arbeta i ett exempelscenario som finns senare i det här avsnittet konfigurerar du systemet enligt beskrivningen i det här avsnittet.

### <a name="set-up-work-pools"></a>Ställa in arbetspooler

Med hjälp av arbetspooler kan du ordna arbetsuppgifter efter typ. Om du vill arbeta med funktionen *Ändra arbetspool för arbete* måste du ha minst två arbetspooler tillgängliga. Så här lägger du till arbetspooler.

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetspooler**.
1. Om du arbetar med demo data från **USMF** företaget och kommer att arbeta genom exempelscenariot senare i det här avsnittet, lägger du till två arbetspooler som har följande inställningar:

    - Arbetspool 1:

        - **Arbetspools-ID:** *Webshop*
        - **Beskrivning:** *Webbutik*

    - Arbetspool 2:

        - **Arbetspools-ID:** *CallCenter*
        - **Beskrivning:** *Kundtjänst*

1. Klicka på **Spara** i åtgärdsfönstret.

### <a name="set-up-work-templates"></a>Ställ in arbetsmallar

För varje arbetsmall kan du ställa in en standardpool för arbetsgrupp, efter behov. För varje relevant mall tilldelar du en arbetsgrupp i kolumnen **arbetspools-ID**. I det här fallet ärver alla arbetsuppgifter som genereras med hjälp av en given mall automatiskt den tilldelade arbetsgruppen. Om du arbetar med demo data från **USMF** företaget och kommer att arbeta genom exempelscenariot senare i det här avsnittet, följ dessa steg.

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.
1. I åtgärdsfönstret, välj **Redigera** för att placera sidan i redigeringsläge.
1. Redigera mallen genom att ange följande värden:

    - **Arbetsmallen:** *62 Välj för packa*
    - **Arbetspools-ID:** *Webshop*

1. Välj **Spara**.

## <a name="example-scenario"></a>Exempelscenario

Det här scenariot visar hur du ändrar flödet för bearbetning för en befintlig arbetsuppgift genom att ändra dess arbetsgrupp. Den använder demodata från **USMF** företaget och de inställningar som föreslogs tidigare i det här avsnittet.

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Skapa en försäljningsorder och släpp den på lagerstället

1. Kontrollera att det finns tillräckligt lagerbehållning för artiklarna *A0001* och *A0002* i lagerställe *62*. Gå till **lagerstyrning \> förfrågningar och rapporter \> behållningslistan** och redigera filtren som det visas här:

    - **Lagerställe** värdet börjar med *62*.
    - **Artikelnummer** värdet är antingen *A001* eller *A002*.

    Demonstrationsdata ska ha kvantiteten 10 styck.

    Sedan måste du skapa en försäljningsorder.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - **Kundkonto:** *US-007*
    - **Lagerställe:** *62*

1. Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.
1. Den nya försäljningsordern öppnas. Detta bör innehålla en ny tom rad i rutnätet på snabbfliken **försäljningsorderrader**. Ställ in följande värden på denna rad:

    - **Artikelnummer:** *A0001*
    - **Kvantitet:** *2*

1. I menyn **Lager** ovanför rutnätet, välj **Reservation**.
1. På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** för att reservera lager.
1. Stäng sidan.
1. På snabbfliken **Försäljningsorderrader** välj **Lägg till rad** för att lägga till en ny rad i din försäljningsorder. Ställ in följande värden på denna rad:

    - **Artikelnummer:** *A0002*
    - **Kvantitet:** *2*

1. I menyn **Lager** ovanför rutnätet, välj **Reservation**.
1. På sidan **Reservation** i åtgärdsfönstret, välj **Reservera parti** för att reservera lager.
1. Stäng sidan.
1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.
1. Du får informationsmeddelanden som visar det påfyllnads-ID och leverans-ID som skapades från versionen. Gör en notering av påfyllnad-ID.

### <a name="review-the-outbound-wave"></a>Granska den utgående påfyllnaden

1. Gå till **lagerstyrning \> utgående påfyllningar \> leveranspåfyllningar \> alla påfyllningar**.
1. I rutnätet söker du efter det påfyllnads-ID som skapades från frisläppningen av försäljningsordern.
1. Välj påfyllnads-ID för att visa detaljerna.
1. På snabbfliken **Påfyllnadsrader** ser du till att ett leverans-ID visas för försäljningsordern.

    > [!TIP]
    > Om alternativet **Bearbeta påfyllnaden vid släpp till lager** anges till *Nej* i inställningarna för mallen leverans påfyllnad, måste du bearbeta påfyllnad manuellt genom att välja **Process** från flik **Påfyllnad** på åtgärdsfönstret för att skapa arbete.

1. Kontrollera att påfyllnad har bearbetats. Den här bearbetningen skapar det begärda arbetet.

### <a name="view-work-details-and-change-the-work-pool"></a>Visa arbetsdetaljer och ändra arbetsgruppen

Du kan använda sidan **Arbetsuppgifter** för att se det arbete som skapades och för att hantera arbetspoolen.

1. Gå till **Lagerstyrning \> Arbete \> Arbetsdetaljer**.
1. Markera raden för det arbete som just har skapats. I kolumnen **Ordernummer** visas försäljningsordernumret.

    Fältet **arbetspools-ID** kommer att anges till det arbetspools-ID som har angetts i arbetsmallen.

    > [!TIP]
    > Om fältet **arbetspools-ID** lägger du till kolumnen i rutnätet och uppdaterar sidan.

1. Om du vill ändra vilken arbetsgrupp som är associerad med arbets-ID väljer du **Arbete** välj **Ändra arbetspool-ID**.
1. I dialogrutan **Ändra arbetspool** på snabbfliken **Parametrar** i fältet **Arbetspool-ID** välj *CallCenter*.
1. Välj **OK** om du vill använda ändringen.
1. Observera att värdet i fältet **arbetspools-ID** nu har ändrats till *CallCenter*.

> [!IMPORTANT]
> När **Ändra arbetspool** visas kanske fältet **arbetspool-ID** är tomt som standard. Om fältet är tomt när du väljer **OK** för att tillämpa ändringarna tas arbetspoolen bort helt från arbetet.
>
> Förutom att växla mellan arbetspooler kan du använda den här proceduren för att lägga till en resurspool i en arbetsuppgift som inte har en eller för att ta bort en resurspool från valfri arbetsuppgift som har en sådan.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]