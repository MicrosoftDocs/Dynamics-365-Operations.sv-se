---
title: Konfigurera konsolideringspolicyer för leverans
description: I det här avsnittet beskrivs hur du ställer in standard- och anpassade konsolideringspolicyer för leveranser.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, TMSMode, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 0d6ab6c034a5c341432f661cf1e729dfd3e5c239
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996410"
---
# <a name="configure-shipment-consolidation-policies"></a>Konfigurera konsolideringspolicyer för leverans

[!include [banner](../includes/banner.md)]

Konsolideringsprocessen för leveranser som använder konsolideringspolicyer för leveranser möjliggör automatisk leveranskonsolidering vid automatisk och manuell frisläppning till lagerstället. När du har aktiverat den här funktionen måste du konfigurera de ursprungliga policyerna. Om inga policyer konfigureras kommer varje enskild försäljningsrad att generera en separat leverans med en enda beläggninsrad.

Scenarierna som presenteras i det här avsnittet beskriver hur du ställer in standard- och anpassade konsolideringspolicyer.

## <a name="turn-on-the-shipment-consolidation-policies-feature"></a>Aktivera funktionen för konsolideringspolicyer för leverans

> [!IMPORTANT]
> I det [första scenariot](#scenario-1) som beskrivs i det här avsnittet måste du först ställa in ett lagerställe så att detta använder den tidigare leveranskonsolideringen. Du kommer sedan att göra policyer för leveranskonsolidering tillgängliga. På så sätt kan du uppleva hur uppgraderingsscenariot fungerar. Om du tänker använda en demodatamiljö för att gå igenom det första scenariot ska du inte aktivera funktionen innan du kör scenariot.

Innan du kan använda funktionen *Policyer för leveanskonsolidering* måste du aktivera den i systemet. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionsnamn:** *Konsolidera leverans*

## <a name="make-demo-data-available"></a>Gör demodata tillgängliga

Varje scenario i det här avsnittet innehåller referenservärden och -poster som ingår i den standarddemodata som finns för Microsoft Dynamics 365 Supply Chain Management. Om du vill använda de värden som finns här på samma sätt som i övningarna måste du arbeta i en miljö där demonstrationsdata har installerats samt ställa in den juridiska personen på **USMF** innan du börjar.

## <a name="scenario-1-configure-default-shipment-consolidation-policies"></a><a name="scenario-1"></a>Scenario 1: Konfigurera konsolideringspolicyer för standardleverans

Det finns två situationer där du måste konfigurera det lägsta antalet standardpolicyer när du har aktiverat funktionen för *Konsolideringspolicyer för leverans*:

- Du uppgraderar en miljö som redan innehåller data.
- Du ställer in en helt ny miljö.

### <a name="upgrade-an-environment-where-warehouses-are-already-configured-for-cross-order-consolidation"></a>Uppgradera en miljö där lagerställen redan har konfigurerats för konsolidering mellan order

När du startar den här proceduren bör funktionen *Konsolideringspolicyer för leverans* inaktiveras i syfte att simulera en miljö där funktionen för grundläggande konsolidering av flera order redan har använts. Du använder sedan funktionshanteringen för att aktivera funktionen så att du kan lära dig att ställa in policyer för leverans efter uppgraderingen.

Följ de här stegen om du vill ställa in standardpolicyer för leveranskonsolidering i en miljö där lagerställen redan har konfigurerats för konsolidering av flera order.

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Lagerställen**.
1. I listan söker du efter och öppnar önskad post för lagerställe (t.ex. lager *24* i **USMF**-demodata).
1. I åtgärdsfönstret väljer du **Redigera**.
1. På snabbfliken **Lageerställe** ställer du in alternativet **Konsolidera leverans vid släpp till lagerställe** som *Ja*.
1. Upprepa steg 2 till och med 4 för alla andra lagerställen där konsolidering krävs.
1. Stäng sidan.
1. Använd [funktionshanteringen](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera funktionen *Policyer för leveranskonsolidering*. I arbetsytan **Funktionshantering** heter funktionen *Konsolidera leverans*.
1. Gå till **Lagerstyrnings \> Inställningar \> Släpp till lagerställe \> Policyer för leveranskonsolidering**. Du kanske måste uppdatera webbläsaren för att se det nya menyalternativet **Policyer för leveranskonsolidering** när du har aktiverat funktionen.
1. I åtgärdsfönstret väljer du **Skapa standardinställningar** för att skapa följande policyer:

    - En **CrossOrder**-policy för policytypen *Försäljningsorder* (förutsatt att du har minst ett lagerställe som har ställts in för att använda den tidigare konsolideringsfunktionen)
    - En **standard**-policy för policytypen *försäljningsorder*
    - En **standard**-policy för policytypen *Överföringsproblem*
    - En **CrossOrder**-policy för policytypen *Överföringsproblem* (förutsatt att du har minst ett lagerställe som har ställts in för att använda den tidigare konsolideringsfunktionen)

    > [!NOTE]
    > - Båda **CrossOrder**-policyerna beaktar samma uppsättning fält som den tidigare logiken, förutom fältet för ordernumret. (Detta fält används för att konsolidera rader till levranser, baserat på faktorer som lagerställe, leveransens transportmetod samt adress.)
    > - Båda **standard**-policyerna beaktar samma uppsättning fält som den tidigare logiken, inklusive fältet för ordernumret. (Detta fält används för att konsolidera rader till leveranser, baserat på faktorer som ordernummer, lagerställe, leveransens transportmetod samt adress.)

1. Välj policyn **CrossOrder** för policytypen *Försäljningsorder* och välj sedan **Redigera fråga** i åtgärdsfönstret.
1. I dialogrutan för frågeredigeraren kan du se att de lagerställen listas där alternativet **Konsolidera leverans vid släpp till lagerställe** är inställt på *Ja*. De inkluderas därför i frågan.

### <a name="create-default-policies-for-a-new-environment"></a>Skapa standardpolicyer för en ny miljö

Följ de här stegen om du vill ställa in standardpolicyer för leveranskonsolidering i en helt ny miljö.

1. Använd [funktionshanteringen](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera funktionen *Policyer för leveranskonsolidering* om du inte redan har gjort det. I arbetsytan **Funktionshantering** heter funktionen *Konsolidera leverans*.
1. Gå till **Lagerstyrnings \> Inställningar \> Släpp till lagerställe \> Policyer för leveranskonsolidering**.
1. I åtgärdsfönstret väljer du **Skapa standardinställningar** för att skapa följande policyer:

    - En **standard**-policy för policytypen *försäljningsorder*
    - En **standard**-policy för policytypen *Överföringsproblem*

    > [!NOTE]
    > Båda **standard**-policyerna beaktar samma uppsättning fält som den tidigare logiken, inklusive fältet för ordernumret. (Detta fält används för att konsolidera rader till leveranser, baserat på faktorer som ordernummer, lagerställe, leveransens transportmetod samt adress.)

## <a name="scenario-2-configure-custom-shipment-consolidation-policies"></a>Scenario 2: Konfigurera konsolideringspolicyer för anpassad leverans

I det här scenariot visas hur du ställer in anpassade konsolideringspolicyer för leverans. Anpassade policyer kan stödja komplexa företagsbehov där leveranskonsolidering är beroende av flera olika villkor. För varje enskild exempelpolicy längre fram i det här scenariot ingår en kort beskrivning av affärsärendet. Dessa exempelpolicyer bör ställas in i en sekvens som garanterar en hierarkisk utvärdering av frågorna. (Med andra ord bör de policyer som har flest villkor utvärderas med högst prioritet.)

### <a name="turn-on-the-feature-and-prepare-master-data-for-this-scenario"></a>Aktivera funktionen och förbered huvuddatan för scenariot

Innan du kan gå igenom övningarna i det här scenariot måste du aktivera funktionen och förbereda den huvuddata som krävs för filtreringen enligt beskrivningen i följande underavsnitt. (Dessa förutsättningar gäller även scenarier som anges i [Exempelscenarier i hur man använder policyer för leveranskonsolidering](#example-scenarios).)

#### <a name="turn-on-the-feature-and-create-the-default-policies"></a>Aktivera funktionen och skapa standardpolicyerna

Använd funktionshantering om du vill aktivera funktionen - om du inte redan har aktiverat den - och skapa de standardkonsolideringspolicyer som beskrivs i [Scenario 1](#scenario-1).

#### <a name="create-two-new-product-filter-codes"></a>Skapa två nya produktfilterkoder

1. Gå till **Lagerhantering \> Inställningar \> Produktfilter \> Produktfilter** och lägg till två produktfilter:

    - Produktfilter 1:

        - **Filterkod:** *Brandfarlig*
        - **Filterrubrik:** *Kod 4*

    - Produktfilter 2:

        - **Filterkod:** *Explosivt*
        - **Filterrubrik:** *Kod 4*

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Öppna produkten med artikelnummer *M9200*. (Den produkt du väljer måste vara aktiverad för avancerade \[WMS\]-processer för lagerställen, och denna produkt är föraktiverad för WMS-processer i **USMF**-demodatan.)
1. På snabbfliken **Lagerställe** anger du fältet **Kod 4** som *Brandfarlig*.
1. Stäng sidan.
1. Öppna produkten med artikelnummer *M9201*. (Den här produkten har också föraktiverats för WMS-processer i **USMF**-demodatan.)
1. På snabbfliken **Lagerställe** anger du fältet **Kod 4** som *Explosivt*.
1. Stäng sidan.

#### <a name="create-a-new-transportation-mode-of-delivery"></a>Skapa ett nytt transportsätt för leverans

1. Gå till **Transporthantering \> Inställningar \> Leverantörer \> Läge**.
1. Skapa ett transportläge som ska användas i konsolideringsfrågor och ge den namnet *Flygfrakt*.
1. Gå till **Transporthantering \> Inställningar \> Transportföretag \> Transportföretag**.
1. Skapa ett transportföretag med följande inställningar:

    - **Transportföretag:** *Flygfrakt*
    - **Namn:** *Flygfrakt*
    - **Läge:** *Flygfrakt*

1. På snabbfliken **Tjänster** för det nya transportföretaget lägger du till en rad med följande inställningar:

    - **Transportföretag:** *Flyg*
    - **Transportmetod:** *Flyg*

1. Klicka på **Spara** i åtgärdsfönstret.

    > [!NOTE]
    > När du sparar det nya transportföretaget anges fältet **Leveranssätt** för den nya raden i rutnätet **Tjänster** automatiskt som *Flygfrakt*. När du använder leveranssättet *Flygfrakt* för en försäljningsorder kommer leveranssättet *Flygfrakt* att användas för relaterade leveranser.

#### <a name="create-an-order-pool"></a>Skapa en orderpool

1. Gå till **Försäljning och marknadsföring \> Inställningar \> Försäljningsorder \> Orderpooler**.
1. Skapa en orderpool som ska användas för konsolideringsfrågan. Denna orderpool ska ha följande inställningar:

    - **Pool:** Ange ett heltal som inte redan används av någon annan pool.
    - **Namn:** *ShipCons*

1. Gå till **Försäljning och marknadsföring \> Kunder \> Alla kunder**.
1. Öppna kunden som har kontonummer *USA-003*.
1. På snabbfliken **Standardinställningar för försäljningsorder** ställer du in fältet **Försäljningsorderpool** till den orderpool som du just har skapat.
1. Stäng sidan och upprepa steg 4 och 5 för kunden som har kontonummer *US-004*.

### <a name="create-example-policy-1"></a>Skapa exempelpolicy 1

I det här exemplet ska du skapa en *kund- +läges* policy som kan användas i följande affärsfall:

- Policyn kommer att fråga efter ett specifikt kundkonto (*US-001*) och ett specifikt leveranssätt (*Flygfrakt*).
- Konsolidering med öppna leveranser är inaktiverade.
- Konsolidering sker per order-ID. (Med andra ord sker separata leveranser per order, lagerställe och så vidare.)

Följ stegen nedan om du vill skapa en leveranskonsolideringspolicy för affärsärendet.

1. Gå till **Lagerstyrnings \> Inställningar \> Släpp till lagerställe \> Policyer för leveranskonsolidering**.
1. Ställ in fältet **Policytyp** som *Försäljningsorder*.
1. I åtgärdsfönstret väljer du **Ny** du vill skapa en policy med följande inställningar:

    - **Policyns namn:** *CustomerMode*
    - **Policybeskrivning:** *Kundkonto och leveranssätt*

1. Lämna alternativet **Konsolidera med öppna leveranser** inställt på *Nej*.
1. Klicka på **Spara** i åtgärdsfönstret.
1. På snabbfliken **Konsolideringsfält**, i listan **Återstående fält**, markerar du den rad där fältet **Fältnamn** är inställt på *Leveranssätt*.
1. Välj knappen **Lägg till** ![Högerpil](media/forward-button.png) om du vill flytta fältet till listan **Valda fält**.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. I dialogrutan för frågeredigeraren, på fliken **Intervall**, letar du upp raden där fältet **Fält** är inställt på *Kundkonto* och ställer in fältet **Kriterium** för den raden som *USA – 001*.
1. Välj **Lägg till** för att lägga till en rad med följande inställningar i rutnätet:

    - **Register:** *Orderrader*
    - **Härlett register:** *Orderrader*
    - **Fält:** *Leveranssätt*
    - **Kriterier:** *Flygfrakt*

1. Välj **OK** för att stänga dialogrutan.

> [!NOTE]
> För det här affärsärendet kommer orderrader för kund *US-001* som använder leveranssättet *Flygfrakt* inte att konsolideras mellan order. Denna policy är avsedd att användas först i en sekvens i fall där leveranser för alla andra leveranssätt konsolideras för kunden.

### <a name="create-example-policy-2"></a>Skapa exempelpolicy 2

I det här exemplet kommer du att skapa en policy om *farligt gods* som kan användas i följande affärsfall:

- Policyn kommer att fråga efter en specifik filterkod (*farligt*) och ett specifikt leveranssätt (*Flygfrakt*).
- Konsolidering med öppna leveranser är aktiverat.
- Konsolidering sker mellan order. (Med andra ord sker separata leveranser per konto, lagerställe och så vidare, men bara inom den artikelgrupp som anges i frågan.)

Följ stegen nedan om du vill skapa en leveranskonsolideringspolicy för affärsärendet.

1. Gå till **Lagerstyrnings \> Inställningar \> Släpp till lagerställe \> Policyer för leveranskonsolidering**.
1. Ställ in fältet **Policytyp** som *Försäljningsorder*.
1. I åtgärdsfönstret väljer du **Ny** du vill skapa en policy med följande inställningar:

    - **Policynamn:** *Artikeltyp*
    - **Policybeskrivning:** *Konsolidera samma typ av artiklar mellan order*

1. Ange alternativet **Konsolidera med öppna leveranser** som *Ja*.
1. Klicka på **Spara** i åtgärdsfönstret.
1. På snabbfliken **Konsolideringsfält**, i listan **Återstående fält**, markerar du den rad där fältet **Fältnamn** är inställt på *Leveranssätt*.
1. Välj knappen **Lägg till** ![Högerpil](media/forward-button.png) om du vill flytta fältet till listan **Valda fält**.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. I dialogrutan för frågeredigeraren, i fliken **Kopplingar**, expanderar och väljer du **Register \> Läs in information** i trädet.
1. Välj **Lägg till registerkoppling**.
1. I relationsrutnätet som visas söker du efter samt markerar den rad där fältet **Relatioer** är inställt på *Artikelnummer för lagerställe (artikelnummer)* och väljer sedan **Välj**. 
1. På fliken **Intervall** väljer du **Lägg till** för att lägga till en rad med följande inställningar i rutnätet:

    - **Register:** *Artikelnummer för lagerställe*
    - **Härlett register:** *Artikelnummer för lagerställe*
    - **Fält:** *Kod 4*
    - **Kriterier:** *Brandfarligt*

1. Välj **OK** för att stänga dialogrutan.

> [!NOTE]
> För det här affärsärendet konsolideras alla orderrader där artiklar har en specifik filterkod (det vill säga där fältet **kod 4** är inställt på *Brandfarlig*) kommer att konsolideras med andra artiklar av samma typ mellan olika order. Om det finns en öppen leverans för samma konto, lagerställe och grupp med artiklar, kommer de nya raderna att kopplas till den.

### <a name="create-example-policy-3"></a>Skapa exempelpolicy 3

I det här exemplet kommer du att skapa en policy om *Kundbehov* som kan användas i följande affärsfall:

- Policyn kommer att fråga efter ett specifikt kundkonto.
- Konsolidering med öppna leveranser är aktiverat.
- Konsolidering sker mellan order men baseras på kundrekvisitioner. (Med andra ord grupperas flera order till leveranser, baserat på samma kundrekvisitionsnummer och lagerställe.)

Följ stegen nedan om du vill skapa en leveranskonsolideringspolicy för affärsärendet.

1. Gå till **Lagerstyrnings \> Inställningar \> Släpp till lagerställe \> Policyer för leveranskonsolidering**.
1. Ställ in fältet **Policytyp** som *Försäljningsorder*.
1. I åtgärdsfönstret väljer du **Ny** du vill skapa en policy med följande inställningar:

    - **Policyns namn:** *CustomerOrderNo*
    - **Policybeskrivning:** *Konsolidera rader baserat på kundens inköpsorder*

1. Ange alternativet **Konsolidera med öppna leveranser** som *Ja*.
1. Klicka på **Spara** i åtgärdsfönstret.
1. På snabbfliken **Konsolideringsfält**, i listan **Återstående fält**, markerar du den rad där fältet **Fältnamn** är inställt på *Kundrekvisition*.
1. Välj knappen **Lägg till** ![Högerpil](media/forward-button.png) om du vill flytta fältet till listan **Valda fält**.
1. I listan **Återstående fält** väljer du den rad där fältet **Fältnamn** är inställt på *Leveranssätt*.
1. Välj knappen **Lägg till** ![Högerpil](media/forward-button.png) om du vill flytta fältet till listan **Valda fält**.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. I dialogrutan för frågeredigeraren, på fliken **Intervall**, letar du upp raden där fältet **Fält** är inställt på *Kundkonto* och ställer in fältet **Kriterium** för den raden som *US-001*.
1. Välj **OK** för att stänga dialogrutan.

> [!NOTE]
> För det här affärsärendet konsolideras alla orderrader där försäljningsorder har samma kundrekvisitionsnummer till en och samma leverans, oavsett försäljningsordernummer. (Kundrekvisitionsnumret används som kundens inköpsorder\[IO\]-nummer.) Om det finns en öppen leverans för samma konto, lagerställe och kundrekvisition kommer de nya raderna att kopplas till den. Denna policy kan användas om kunden skickar fler orderrader som har samma inköpsordernummer flera gånger under en dag och vill att alla rader ska grupperas i en och samma leverans. (Med andra ord kommer det att finnas en fraktsedel och en följesedel.)

### <a name="create-example-policy-4"></a>Skapa exempelpolicy 4

I det här exemplet kommer du att skapa en policy om *Kunder som tillåter konsolidering* som kan användas i följande affärsfall:

- Policyn kommer att fråga efter en specifik orderpool i syfte att identifiera kunder som accepterar konsoliderade leveranser.
- Konsolidering med öppna leveranser är inaktiverade.
- Konsolidering sker mellan order med hjälp av de fält som väljs av den förvalda CrossOrder-policyn (för att replikera den tidigare **Konsolidera leverans vid släpp till lagerställe**).

- Du kan åsidosätta regeln på en försäljningsorder genom att välja en annan orderpool.

Följ stegen nedan om du vill skapa en leveranskonsolideringspolicy för affärsärendet.

1. Gå till **Lagerstyrnings \> Inställningar \> Släpp till lagerställe \> Policyer för leveranskonsolidering**.
1. Ställ in fältet **Policytyp** som *Försäljningsorder*.
1. I åtgärdsfönstret väljer du **Ny** du vill skapa en policy med följande inställningar:

    - **Policynamn:** *Orderpool*
    - **Policybeskrivning:** *Konsolidera över order baserat på orderpool*

1. Lämna alternativet **Konsolidera med öppna leveranser** inställt på *Nej*.
1. Klicka på **Spara** i åtgärdsfönstret.
1. På snabbfliken **Konsolideringsfält**, i listan **Återstående fält**, markerar du den rad där fältet **Fältnamn** är inställt på *Leveranssätt*.
1. Välj knappen **Lägg till** ![Högerpil](media/forward-button.png) om du vill flytta fältet till listan **Valda fält**.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. På fliken **Intervall** i dialogrutan för frågeredigerare väljer du **Lägg till** för att lägga till en rad med följande inställningar i rutnätet:

    - **Register:** *Försäljningsorder*
    - **Härlett register:** *Försäljningsorder*
    - **Fält:** *Pool*
    - **Kriterier:** *ShipCons*

1. Välj **OK** för att stänga dialogrutan.

> [!NOTE]
> För detta affärsärende konsolideras alla orderrader där försäljningsordern tillhör samma order till en enda leverans mellan försäljningsorder för samma konto, lagerställe och leveranssätt. I stället för till adresspoolen kan du använda ett annat fält för att särskilja en grupp med kunder och använda försäljningsorderrubriken som standard. Du kan använda den här metoden om kunden, inte lagerstället, driver fram konsolideringen. (I den tidigare konsolideringslogiken drev lagerstället behovet av konsolidering.)

### <a name="create-example-policy-5"></a>Skapa exempelpolicy 5

I det här exemplet kommer du att skapa en policy om *Lagerställen som tillåter konsolidering* som kan användas i följande affärsfall:

- Policyn kommer att fråga efter en specifik orderpool i syfte att identifiera lagerställen som kan konsolidera leveranser.
- Konsolidering med öppna leveranser är inaktiverade.
- Konsolidering sker mellan order med hjälp av de fält som väljs av den förvalda CrossOrder-policyn (för att replikera den tidigare **Konsolidera leverans vid släpp till lagerställe**).

Vanligtvis kan detta affärsärendet åtgärdas med hjälp av de standardprinciper som du skapade i [Scenario 1](#scenario-1). Du kan emellertid även skapa likartade policyer manuellt genom att följa stegen nedan.

1. Gå till **Lagerstyrnings \> Inställningar \> Släpp till lagerställe \> Policyer för leveranskonsolidering**.
1. Ställ in fältet **Policytyp** som *Försäljningsorder*.
1. I åtgärdsfönstret väljer du **Ny** du vill skapa en policy med följande inställningar:

    - **Policynamn:** *Orderomspännande*
    - **Policybeskrivning:** *Orderomspännande konsolidering för specifika lagerställen*

1. Lämna alternativet **Konsolidera med öppna leveranser** inställt på *Nej*.
1. Klicka på **Spara** i åtgärdsfönstret.
1. På snabbfliken **Konsolideringsfält**, i fältet **Återstående fält**, markerar du den rad där fältet **Fältnamn** är inställt på *Leveranssätt*.
1. Välj knappen **Lägg till** ![Högerpil](media/forward-button.png) om du vill flytta fältet till listan **Valda fält**.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. I dialogrutan för frågeredigeraren, på fliken **Intervall**, letar du upp raden där fältet **Fält** är inställt på *Lagerställe* och ställer in fältet **Kriterium** för den raden som *61, 63*.
1. Välj **OK** för att stänga dialogrutan.

### <a name="set-the-order"></a>Ställ in order

Nu när du har skapat alla dina policyer måste du ange den ordningsföljd som de ska tillämpas i. Om du vill använda en hierarkisk metod där de policyer som har flest villkor utvärderas med högsta prioritet följer du stegen nedan.

1. Gå till **Lagerstyrnings \> Inställningar \> Släpp till lagerställe \> Policyer för leveranskonsolidering**.
1. Ställ in fältet **Policytyp** som *Försäljningsorder*.
1. Markera varje princip som visas i den vänstra kolumnen och använd sedan knapparna **Flytta upp** och **Flytta ned** i åtgärdsfönstret för att ordna policyerna i följande ordning:

    1. CustomerMode
    1. Artikeltyp
    1. CustomerOrderNo
    1. Orderpool
    1. Orderomfattande
    1. Standard

## <a name="example-scenarios-of-how-to-use-shipment-consolidation-policies"></a><a name="example-scenarios"></a> Exempelscenarier på hur du använder policyer för leveranskonsolidering

I följande scenarier visas hur du kan använda de konsolideringspolicyer för leverans som du skapade när du läste det här ämnet. Varje scenario leder dig igenom en leveranskonsolideringsprocess som använder konsolideringspolicyer för leveranser vid automatisk och manuell frisläppning till lagerstället:

- Scenario 1 – [Konsolidera leveranser när dessa släpps till lagerstället med hjälp av automatisk frisläppning av försäljningsorder](../warehousing/consolidate-shipments-automatic.md)
- Scenario 2 – [Konsolidera leveranser när policyn för leveranskonsolidering åsidosätts från sidan Frisläpp till lagerställe](../warehousing/consolidate-shipments-release-to-warehouse-override.md)
- Scenario 3 – [Konsolidera leveranser genom att använda Frisläpp till lagerställe från workbench för lastplanering](../warehousing/consolidate-shipments-load-planning-workbench.md)
- Scenario 4 – [Konsolidera leveranser genom att använda workbench för leveranskonsolidering](../warehousing/consolidate-shipments-manual-workbench.md)
- Scenario 5 – [Konsolidera leveranser manuellt via sidan Konsolidera leveranser](../warehousing/consolidate-shipments-manual-form.md)


## <a name="additional-resources"></a>Ytterligare resurser

- [Policyer för leveranskonsolidering](about-shipment-consolidation-policies.md)
