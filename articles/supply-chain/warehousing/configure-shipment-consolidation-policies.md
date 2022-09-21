---
title: Konfigurera konsolideringspolicyer för leverans
description: I denna artikel beskrivs hur du konfigurerar standard- och anpassade konsolideringspolicyer för leveranser.
author: Mirzaab
ms.date: 09/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, TMSMode, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 0312d425d2ebc5311e894030423a916b90f1881a
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/08/2022
ms.locfileid: "9427993"
---
# <a name="configure-shipment-consolidation-policies"></a>Konfigurera konsolideringspolicyer för leverans

[!include [banner](../includes/banner.md)]

Konsolideringsprocessen för leveranser som använder konsolideringspolicyer för leveranser möjliggör automatisk leveranskonsolidering vid automatisk och manuell frisläppning till lagerstället. När du har aktiverat den här funktionen måste du konfigurera de ursprungliga policyerna. Om inga policyer konfigureras kommer varje enskild försäljningsrad att generera en separat leverans med en enda beläggninsrad.

Scenarierna som presenteras i denna artikel beskriver hur du konfigurerar standard- och anpassade konsolideringspolicyer.

> [!WARNING]
> Om du uppgraderar ett Microsoft Dynamics 365 Supply Chain Management-system där du har använt den gamla funktionen för leveranskonsolidering kan konsolideringen sluta fungera som du förväntat dig, om du inte följer de anvisningar som ges här.
>
> I installationer av Supply Chain Management där funktionen *Policyer för leveranskonsolidering* är avstängd, aktiverar du leveranskonsolidering genom att använda inställningen **Konsolidera leverans vid frisläppning till lagerställe** för varje enskilt lagerställe. Den här funktionen är obligatorisk i version 10.0.29. När den är påslagen, inställningen **Konsolidera leverans vid frisläppning till lagerställe** inställningen blir dold, och funktionaliteten ersätts av *policyer för leveranskonsolidering* som beskrivs i den här artikeln. Varje policy konsoliderar konsolideringsregler och innehåller en fråga som kontrollerar var policyn gäller. När du först aktiverar funktionen definieras inga policyer för leveranskonsolidering på sidan **Policyer för leveranskonsolidering**. När inga principer har definierats använder systemet det äldre beteendet. Därför fortsätter varje befintligt lager att respektera sitt inställning **Konsolidera leverans vid frisläppning till lagerställe**, även om den inställningen nu är dold. När du har skapat minst en konsolideringspolicy för en försändelse, har dock inte inställningarna **Konsolidera leverans vid frisläppning till lagerställe** har inte längre någon effekt och konsolideringsfunktionaliteten styrs helt av policyerna.
>
> När du har definierat minst en konsolideringspolicy för försändelser kontrollerar systemet konsolideringsprinciperna varje gång en order frisläpps till lagerstället. Systemet bearbetar policyerna genom att använda den rangordning som definieras av värde respektive **policysekvens**. Den använder den första policyn där frågan matchar den nya ordern. Om inga frågor matchar beställningen genererar varje orderrad en separat leverans med en enda beläggningsrad. Som reserv rekommenderar vi därför att du skapar en standardpolicy som gäller för alla lagerställen och grupper efter ordernummer. Ge den här reservpolicyn det högsta **Policy sekvens**, så att det bearbetas sist.
>
> Om du vill återskapa det äldre beteendet måste du skapa en policy som inte grupperas efter ordernummer och som har frågekriterier som omfattar alla relevanta lagerställen.

## <a name="turn-on-the-shipment-consolidation-policies-feature"></a>Aktivera funktionen för konsolideringspolicyer för leverans

För att använda funktionen *Policyer för leveranskonsolidering* måste du aktivera den i systemet. Från och med version 10.0.29 version av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras. Om du kör en version som är äldre än 10.0.29 kan administratörer aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Policyer för leveranskonsolidering* i arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-your-initial-consolidation-policies"></a><a name="initial-policies"></a>Konfigurera dina första konsolideringspolicyer

Om du arbetar med ett nytt system eller ett system där du precis har aktiverat funktionen *Policyer för leveranskonsolidering* för första gången, följ dessa steg för att ställa in dina första policyer för konsolidering av leveranser.

1. Gå till **Warehouse managements \> Inställningar \> Släpp till lagerställe \> Policyer för leveranskonsolidering**.
1. I åtgärdsfönstret väljer du **Skapa standardinställningar** för att skapa följande policyer:

    - En policy som namnges *standard*-policy för policytypen *försäljningsorder*.
    - En policy som namnges *standard*-policy för policytypen *Överför leverans*.
    - En policy som namnges *CrossOrder*-policy för policytypen *Överför leverans*. (Denna policy skapas endast om du har minst ett lagerställe där det äldre **Konsolidera leverans vid frisläppning till lagerställe** till lagerställeinställning har aktiverats.)
    - En policy som namnges *CrossOrder*-policy för policytypen *försäljningsorder*. (Denna policy skapas endast om du har minst ett lagerställe där det äldre **Konsolidera leverans vid frisläppning till lagerställe** till lagerställeinställning har aktiverats.)

    > [!NOTE]
    > - Båda *CrossOrder*-policyerna beaktar samma uppsättning fält som den tidigare logiken. De tar dock även hänsyn till ordernummerfältet. (Detta fält används för att konsolidera rader till levranser, baserat på faktorer som lagerställe, leveransens transportmetod samt adress.)
    > - Båda *Standardvärde*-policyerna beaktar samma uppsättning fält som den tidigare logiken. De tar dock även hänsyn till ordernummerfältet. (Detta fält används för att konsolidera rader till leveranser, baserat på faktorer som ordernummer, lagerställe, leveransens transportmetod samt adress.)

1. Om systemet genererade en *CrossOrder* för policytypen *Försäljningsorder* och välj sedan **Redigera fråga** i åtgärdsfönstret. I frågeredigeraren kan du se vilket av dina lager **Konsolidera leverans vid frisläppning till lagerställe** var tidigare aktiverad för. Därför återskapar den här policyn dina tidigare inställningar för dessa lagerställen.
1. Anpassa de nya standardpolicyerna som krävs genom att lägga till eller ta bort fält och/eller redigera frågorna. Du kan också lägga till så många nya policyer som du behöver. Exempel på hur du anpassar och konfigurerar principer finns i exempelscenariot senare i den här artikeln.

## <a name="scenario-configure-custom-shipment-consolidation-policies"></a>Scenario: Konfigurera konsolideringspolicyer för anpassad leverans

Det här scenariot ger ett exempel som visar hur du ställer in anpassade policyer för försändelsekonsolidering och sedan testar dem med hjälp av demodata. Anpassade policyer kan stödja komplexa företagsbehov där leveranskonsolidering är beroende av flera olika villkor. För varje enskild exempelpolicy längre fram i det här scenariot ingår en kort beskrivning av affärsärendet. Dessa exempelpolicyer bör ställas in i en sekvens som garanterar en hierarkisk utvärdering av frågorna. (Med andra ord bör de policyer som har flest villkor utvärderas med högst prioritet.)

### <a name="make-demo-data-available"></a>Gör demodata tillgängliga

Det här scenariot i detta ämne innehåller värdet och poster som ingår i den standard [demodata](../../fin-ops-core/fin-ops/get-started/demo-data.md) som finns för Supply Chain Management. Om du vill använda de värden som finns här på samma sätt som i övningarna måste du arbeta i en miljö där demonstrationsdata har installerats samt konfigurera den juridiska personen på *USMF* innan du börjar.

### <a name="prepare-master-data-for-this-scenario"></a>Förbered huvuddata för det här scenariot

Innan du kan gå igenom övningarna i det här scenariot måste du och förbereda den huvuddata som krävs för filtreringen enligt beskrivningen i följande underavsnitt. (Dessa förutsättningar gäller även scenarier som anges i avsnitten [Exempelscenarier i hur du använder policyer för leveranskonsolidering](#example-scenarios).)

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
1. Välj knappen **Lägg till** ![Höger pil](media/forward-button.png) om du vill flytta fältet till listan **Markerade fält**.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. I dialogrutan för frågeredigeraren, på fliken **Intervall**, letar du upp raden där fältet **Fält** är inställt på *Kundkonto* och konfigurerar fältet **Kriterium** för den raden som *USA – 001*.
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
1. Välj knappen **Lägg till** ![Höger pil](media/forward-button.png) om du vill flytta fältet till listan **Markerade fält**.
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
1. Välj knappen **Lägg till** ![Höger pil](media/forward-button.png) om du vill flytta fältet till listan **Markerade fält**.
1. I listan **Återstående fält** väljer du den rad där fältet **Fältnamn** är inställt på *Leveranssätt*.
1. Välj knappen **Lägg till** ![Höger pil](media/forward-button.png) om du vill flytta fältet till listan **Markerade fält**.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. I dialogrutan för frågeredigeraren, på fliken **Intervall**, letar du upp raden där fältet **Fält** är inställt på *Kundkonto* och konfigurerar fältet **Kriterium** för den raden som *US-001*.
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
1. Välj knappen **Lägg till** ![Höger pil](media/forward-button.png) om du vill flytta fältet till listan **Markerade fält**.
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

Vanligtvis kan detta affärsärendet åtgärdas med hjälp av de standardprinciper som du skapade i [Konfigurera dina första konsolideringspolicyer](#initial-policies). Du kan emellertid även skapa likartade policyer manuellt genom att följa stegen nedan.

1. Gå till **Lagerstyrnings \> Inställningar \> Släpp till lagerställe \> Policyer för leveranskonsolidering**.
1. Ställ in fältet **Policytyp** som *Försäljningsorder*.
1. I åtgärdsfönstret väljer du **Ny** du vill skapa en policy med följande inställningar:

    - **Policynamn:** *Orderomspännande*
    - **Policybeskrivning:** *Orderomspännande konsolidering för specifika lagerställen*

1. Lämna alternativet **Konsolidera med öppna leveranser** inställt på *Nej*.
1. Klicka på **Spara** i åtgärdsfönstret.
1. På snabbfliken **Konsolideringsfält**, i fältet **Återstående fält**, markerar du den rad där fältet **Fältnamn** är inställt på *Leveranssätt*.
1. Välj knappen **Lägg till** ![Höger pil](media/forward-button.png) om du vill flytta fältet till listan **Markerade fält**.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. I dialogrutan för frågeredigeraren, på fliken **Intervall**, letar du upp raden där fältet **Fält** är inställt på *Lagerställe* och konfigurerar fältet **Kriterium** för den raden som *61, 63*.
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

I följande scenarier visas hur du kan använda de konsolideringspolicyer för leverans som du skapade när du läste denna artikel. Varje scenario leder dig igenom en leveranskonsolideringsprocess som använder konsolideringspolicyer för leveranser vid automatisk och manuell frisläppning till lagerstället:

- Scenario 1 – [Konsolidera leveranser när dessa släpps till lagerstället med hjälp av automatisk frisläppning av försäljningsorder](../warehousing/consolidate-shipments-automatic.md)
- Scenario 2 – [Konsolidera leveranser när policyn för leveranskonsolidering åsidosätts från sidan Frisläpp till lagerställe](../warehousing/consolidate-shipments-release-to-warehouse-override.md)
- Scenario 3 – [Konsolidera leveranser genom att använda Frisläpp till lagerställe från workbench för lastplanering](../warehousing/consolidate-shipments-load-planning-workbench.md)
- Scenario 4 – [Konsolidera leveranser genom att använda workbench för leveranskonsolidering](../warehousing/consolidate-shipments-manual-workbench.md)
- Scenario 5 – [Konsolidera leveranser manuellt via sidan Konsolidera leveranser](../warehousing/consolidate-shipments-manual-form.md)


## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över policyer för leveranskonsolidering](about-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
