---
title: Bekräfta planerade order
description: I denna artikel beskrivs hur du bekräftar planerade order. När planerade order bekräftas omvandlas de till faktiska inköpsorder, överföringsorder eller produktionsorder.
author: t-benebo
ms.date: 08/09/2022
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c2e4294cb54e9ba41467f505e361d5ee45f1f27d
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740533"
---
# <a name="firm-planned-orders"></a>Bekräfta planerade order

[!include [banner](../../includes/banner.md)]

Planerade order måste *bekräftas* (det vill säga, frisläppas) som ett led i huvudplaneringsprocessen. När planerade order bekräftas omvandlas de till faktiska inköpsorder, överföringsorder eller produktionsorder. Dessa order kallas även *frisläppta order* eller *öppna order*.

Det finns tre metoder för att bekräfta planerade order:

- **Manuellt bekräftande** – Välj specifika planerade order i en lista och starta sedan processen manuellt.
- **Auto-bekräftande** – Definiera en förvald bekräftad tidsgräns för disponeringsgrupper, enskilda artiklar och kombinationer av artiklar och huvudplaner. Under körningar av huvudplaneringen bekräftas sedan planerade order automatiskt om orderdatumet ligger inom den angivna tidsgränsen för bekräftelse.
- **Frågebaserat bekräftande** – Definiera en fråga för att välja planerade order baserat på deras egenskaper. Du kan konfigurera ett batchjobb för att köra frågan och bekräfta matchande order i ett vanligt schema.

I denna artikel beskrivs de olika metoderna i detalj.

## <a name="enable-the-features-that-are-described-in-this-article"></a><a name="enable-features"></a>Aktivera funktionerna som beskrivs i denna artikel

De flesta planerade orderfunktioner är tillgängliga i alla standardinstallationer av Microsoft Dynamics 365 Supply Chain Management. Några av funktionerna som beskrivs i denna artikel måste dock inaktiveras i Funktionshantering innan du kan använda dem.

### <a name="turn-parallelized-firming-of-planned-orders-on-or-off"></a>Aktivera eller inaktivera parallell bekräftelse av planerade order

Parallelliserat bekräftande gör det snabbare att bekräfta processen genom att parallellisera den i flera trådar. Det här arbetssättet kan vara användbart när många planerade order ska bekräftas. Om du vill använda den här funktionen måste funktionen *Parallell bekräftad planerade order* vara aktiverad för ditt system. 

Från och med version 10.0.21 av Supply Chain Management är denna funktion aktiverad som standard. Från och med version 10.0.25 av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras. Om du kör en version som är äldre än 10.0.25 kan du slå på eller av denna funktion genom att gå till [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)och söka efter funktionen *Parallell bekräftelse av planerade order*.

### <a name="turn-planned-order-firming-with-filtering-on-or-off"></a>Aktivera eller inaktivera planerad orderbekräftelse med filtrering

Med bekräftad order med filtrering kan du definiera logiska kriterier för val av vilka planerade order som ska bekräftas. Du kan också förhandsgranska vilka planerade order som valts, köra processen i bakgrunden och/eller schemalägga den som ett batchjobb.

Innan du kan använda funktionen måste den aktiveras i ditt system. Från och med version 10.0.25 av Supply Chain Management är denna funktion aktiverad som standard. Från och med version 10.0.29 version av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras. Om du kör en version som är äldre än 10.0.29 kan administratörer aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Bekräfta planerad order med filtrering* i arbetsytan [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="turn-auto-firming-for-planning-optimization-on-or-off"></a>Aktivera eller inaktivera auto-bekräftande för Planeringsoptimering

Med auto-bekräftande kan du bekräfta planerade order som en del av huvudplaneringsprocessen inom tidsgränsramarna för bekräftelse. Auto-bekräftande stöds alltid för planeringsmotorn som är inbyggd i Supply Chain Management. Om du vill använda den tillsammans med Planeringsoptimering måste du även aktivera funktionen.

Från och med version 10.0.21 av Supply Chain Management är denna funktion aktiverad som standard. Från och med version 10.0.29 av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras. Om du kör en version som är äldre än 10.0.29 kan du slå på eller av denna funktion genom att gå till [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)och söka efter funktionen *Automatisk bekräftelse för Planeringsoptimering*.

## <a name="manually-firm-planned-orders"></a>Bekräfta planerade order manuellt

Om du vill bekräfta planerade order manuellt hittar och väljer du de planerade order som du vill bekräfta innan du startar bekräftelseprocessen manuellt.

1. [Öppna listsidan för planerade order](approved-planned-order.md#view-planned-orders).
1. Använd fälten **Filter** och **Plan** samt kolumnrubriker för att filtrera och sortera listan så att du kan hitta de planerade order som du söker.
1. Markera kryssrutan för respektive planerad order som du vill bekräfta. Om du vill bekräfta alla planerade order som för närvarande visas på sidan (utifrån de filter som du har använt) hoppar du över det här steget.
1. Välj en av följande knappar i åtgärdsfönstret:

    - **Bekräfta** – Bekräfta endast valda planerade order.
    - **Bekräfta alla** – Bekräfta alla planerade order som för tillfället visas på sidan (baserat på de filter du har använt), oavsett vilka kryssrutor som har markerats. Detta alternativ kan vara användbart om du bekräftar många planerade order.

1. I dialogrutan **Bekräftelse**, på snabbfliken **Parametrar**, anger du följande fält: (Många av dessa fält tar sina standardvärden från fliken **Standarduppdatering** på sidan **Parametrar för huvudplanering**.)

    - **Uppdatera märkning** – Välj vilken lagermärkningsprincip du vill använda när planerade order bekräftas.
    - **Stoppa bekräftelse om ett fel inträffar** – Ställ in det här alternativet som *Ja* om du vill sluta bekräfta alla valda planerade order om ett fel inträffar i någon av dem. Detta alternativet måste ställas in på *Nej* om alternativet **Parallellisera bekräftande** är inställt på *Ja*.
    - **Parallellt bekräftande** – Detta alternativ är bara tillgängligt om funktionen [*Parallellt bekräftande av planerade order*](#enable-features) är aktiverad i systemet och du har valt två eller flera planerade order för bekräftande. Ställ in alternativet på *Ja* om du vill köra processerna för bekräftande parallellt. Parallellt bekräftande kan förbättra prestandan.
    - **Antal trådar** – Detta alternativ är bara tillgängligt om funktionen [*Parallellt bekräftande av planerade order*](#enable-features) är aktiverad i systemet och du har angett alternativet **Parallellisera bekräftande** som *Ja*. Ange det antal trådar som ska användas för att parallellisera bekräftandeprocessen. Information om hur du använder det här alternativet i huvudplaneringen finns i [Förbättra prestandan för huvudplaneringen](../master-planning-performance.md#number-of-threads).

        > [!NOTE]
        > Ett värde på *0* (noll) för fältet **Antal trådar** ökar huvudplaneringens körtid. Därför rekommenderar vi att du alltid anger detta fält till ett värde som är större än 0.

    - **Gruppera efter leverantör** – Ange detta alternativ som *Ja* om du vill gruppera planerade inköpsorder och skapa en inköpsorder per leverantör i sambandmed bekräftelse. Du kan också skapa en inköpsorder som har en rad för respektive planerad order.
    - **Gruppera efter köpargrupp** – Ange detta alternativ som *Ja* för att gruppera ihop planerade inköpsorder och skapa en enda inköpsorder där du slår samman leverantören och köpargruppen. Om du vill använda det här alternativet måste du också ange alternativet **Gruppera efter leverantör** som *Ja*.
    - **Gruppera efter inköpsavtal** – Ange det här alternativet till *Ja* om du vill gruppera planerade inköpsorder som har samma leverantör som befintliga inköpsavtal och skapa en inköpsorder per inköpsavtal. Det här alternativet aktiveras automatiskt när **Gruppera efter leverantör** aktiveras. Om du vill använda **Gruppera efter inköpsavtal**, **Sök efter inköpsavtal** måste anges till *Ja* på sidan **Huvudplaneringsparametrar**.
    - **Gruppera efter period** (i avsnittet **Inköpsorder**) – Välj den period som planerade inköpsorder ska grupperas efter. Om du vill använda det här alternativet måste du också välja alternativet **Gruppera efter leverantör**.
    - **Gruppera efter period** (i avsnittet **Överföringar**) – Välj den period som planerade överföringsorder ska grupperas efter. Orderna grupperas efter värdena i **Från lagerställe** och **Till lagerställe**.

    > [!NOTE]
    > Alla alternativ för "Gruppera efter" gör att systemet konverterar varje planerad order till en rad i den enskilda inköpsordern som resultatet av grupperingen.

    ![Snabbfliken Parametrar i dialogrutan Bekräftelse.](./media/manual-firming.png "Snabbfliken Parametrar i dialogrutan Bekräftelse")

1. På snabbfliken **Kör i bakgrunden** ställer du in jobbet så att det körs i batchläge. Det är dock ingen mening med att konfigurera ett återkommande schema när du håller på att bekräfta manuellt. Fälten fungerar precis som för andra typer av [bakgrundsjobb](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) i Supply Chain Management. För manuell bekräftelse bearbetas dock endast valda planerade order i batchjobbet. Inga order som passar de filter som för tillfället används på sidan bearbetas.
1. Välj **OK** om du vill använda inställningarna och generera bekräftade order.

## <a name="auto-firm-planned-orders"></a>Bekräfta planerade order automatiskt

Med auto-bekräftande kan du bekräfta planerade order som en del av huvudplaneringsprocessen. Du kan definiera en förvald bekräftad tidsgräns för disponeringsgrupper, enskilda artiklar och kombinationer av artiklar och huvudplaner. Under körningar av huvudplaneringen bekräftas sedan planerade order automatiskt om orderdatumet ligger inom den angivna tidsgränsen för bekräftelse. Planerade order som genereras av Planeringsoptimering och den inaktuella huvudplaneringsmotorn hanterar orderdatumet (det vill säga startdatumet) på olika sätt.

> [!NOTE]
> Auto-bekräftande av planerade inköpsorder kan endast ske för artiklar som kopplats med en leverantör.
> 
> Härledda order (det vil säga inköpsorder för underleverantörer) som bekräftas erhåller statusen *Undergår granskning* om ändringsspårning är påslagen.

> [!IMPORTANT]
> Innan funktionen som beskrivs i det här avsnittet kan användas med Planeringsoptimering måste funktionen [*Auto-bekräftande för Planeringsoptimering*](#enable-features) aktiveras i ditt system enligt beskrivet i början av denna artikel. Auto-bekräftande kan alltid användas med den inaktuella huvudplaneringsmotorn.

### <a name="auto-firming-with-planning-optimization-vs-the-deprecated-master-planning-engine"></a>Auto-bekräftande med Planeringsoptimering kontra den inaktuella planeringsmotorn

Både Planeringsoptimeringen och den inaktuella huvudplaneringsmotorn kan användas för att bekräfta planerade order automatiskt. Det finns emellertid några viktiga skillnader. Planeringsoptimeringen använder till exempel orderdatum (dvs. startdatum) för att avgöra vilka planerade order som ska bekräftas, medan den inaktuella huvudplaneringsmotorn använder behovsdatumet (dvs. slutdatumet). I följande register sammanfattas skillnaderna.

| Funktion | Planeringsoptimering | Inaktuell huvudplaneringsmotor |
|---|---|---|
| **Utgångsdatum** | Automatisk bekräftelse baseras på orderdatumet (startdatum). | Automatisk bekräftelse baseras på behovsdatum (slutdatum). |
| **Produktionstid** | Eftersom orderdatumet (startdatum) utlöser bekräftelsen behöver du inte tänka på produktionstiden som en del av den bekräftade tidsgränsen. | För att garantera att order bekräftas i tid måste den bekräftade tidsgränsen vara längre än produktionstiden. |
| **Order för den aktuella veckan** | Om du vill bekräfta alla order som måste påbörjas under den aktuella veckan måste den bekräftade tidsgränsen vara en vecka. | För att bekräfta alla order som måste påbörjas under den aktuella veckan måste den bekräftade tidsgränsen vara produktionstiden plus en vecka. |

### <a name="set-up-auto-firming-and-the-firming-time-fence"></a>Ställ in automatisk bekräftande och den bekräftande tidsgränsen

Du aktiverar auto-bekräftande genom att tilldela en automatiskt bekräftad tidsgräns till relevanta disponeringsinställningar, enligt beskrivningen senare i det här avsnittet. Om auto-bekräftande inte har aktiverats för några disponeringsinställningar, eller om planeringen har startat från en viss sida, till exempel sidan **Nettokrav** för en frisläppt produkt, hoppas den automatiska bekräftandeprocessen över.

Grupperings- och markeringsalternativ för auto-bekräftande får sina värden från fliken **Standarduppdatering** på sidan för **huvudplaneringsparametrar**.

Den automatiskt bekräftande tidsgränsen definieras av antalet dagar du anger för relevanta disponeringsinställningar. Du kan slå på automatiskt bekräftad tidsgräns och styra den bekräftande tidsgränsen på följande sätt:

- Om du vill definiera förvald bekräftad tidsgräns för en disponeringsgrupp går du till **Huvudplanering \> Inställningar \> Disponering \> Disponeringsgrupper** och väljer en disponeringsgrupper. Ange sedan antalet dagar på snabbfliken **övrigt** i fältet **Automatisk bekräftelse av tidsgräns (dagar)**.
- Om du vill skriva över den bekräftande tidsgränsen som har definierats för disponeringsgruppen för en specifik artikel går du till **Produktinformationshantering \> Frisläppta produkter**. I åtgärdsfönstret väljer du **Plan** och sedan **Artikeldisposition**. På fliken **Allmänt** väljer du sedan **Åsidosätt tidsgrän** och, i fältet **Automatisk tidsgräns för bekräftelse (dagar)** anger du antalet dagar.
- Om du vill skriva över den tidsgräns för bekräftelse som har definierats för disponeringsgruppen och artikeldisponering för en viss huvudplan går du till **Huvudplanering \> Inställningar \> Huvudplaner** och väljer en huvudplan. På snabbfliken **Tidsgräns i dagar** anger du sedan alternativet **Bekräftande** som *Ja* och anger antalet dagar.

Om du konfigurerar alla tidigare nämnda tidsgränser som *0* (noll), inaktiveras auto-bekräftande effektivt för relevanta, omfattade artiklar.

## <a name="firm-planned-orders-by-using-a-query"></a>Bekräfta planerade order med hjälp av en fråga

Med hjälp av frågebaserat bekräftande kan du planera bekräftande baserat på kriterier som definieras i förväg. Till skillnad från auto-bekräftande kan frågebaserat bekräftande göra det möjligt att automatiskt bekräfta olika deluppsättningar av order vid olika tidpunkter. Dessutom kan du använda antingen manuella eller automatiska funktioner för att bekräfta olika typer av planerade order. Du kan också förhandsgranska vilka bekräftade order som väljs utifrån dina inställningar. Därför kan du bekräfta att valet passar dina önskemål.

Du kan kombinera automatisk bekräftande med frågebaserat bekräftande. Till exempel har ett frågebaserat bekräftandejobb en tidsgräns framåt som är längre än tidsgränsen för en matchande automatiskt bekräftad disponeringskonfiguration. Därför bearbetas det frågebaserade bekräftandejobbet innan det automatiska bekräftandet utlöses. Du kan använda det här beteendet om du vill schemalägga order för vissa leverantörer på ett annat sätt än order för liknande produkter från andra leverantörer.

> [!IMPORTANT]
> Innan funktionen som beskrivs i detta avsnitt kan användas måste funktionen [*Planerat orderbekräftande med filtrering*](#enable-features) aktiveras i systemet enligt beskrivet i början av denna artikel.

Följ de här stegen om du vill bekräfta en planerad order med hjälp av frågebaserad bekräftandeprocess.

1. Gå till **Huvudplanering \> Huvudplanering \> Kör \> Planerat orderbekräftande**.
1. I dialogrutan **Planerat orderbekräftande**, på snabbfliken **Parametrar**, anger du alternativ för grundläggande bearbetning, märkning och gruppering. Dessa alternativ fungerar på samma sätt som i dialogrutan **Bekräfta**. (Se föregående avsnitt för beskrivningar.) I avsnittet **Plan** ställer du sedan in följande fält, som är unika för dialogrutan **Planerad orderbekräftelse**:

    - **Plan** – Välj den huvudplan som ska användas när de planerade order som hittas i den här frågan bekräftas.
    - **Bekräfta tidsgräns i dagar framåt** – Välj hur långt in i framtiden som olika krav och andra överväganden måste beräknas i huvudplaneringen.
    - **Bekräfta tidsgräns i dagar bakåt** – Välj hur långt i det förgångna som olika krav och andra överväganden måste beräknas i huvudplaneringen.

    ![Snabbfliken Parametrar i dialogrutan Planerad orderbekräftelse.](./media/planned-order-firming-main-1.png "Snabbfliken Parametrar i dialogrutan Planerad orderbekräftelse")

1. Ange vilka poster som ska ingå i ordern genom att klicka på knappen **Filter** på snabbfliken **Poster att inkludera**. En standarddialogruta för fråga visas där du kan definiera urvalskriterier, sorteringskriterier och sammankopplingar. Fälten fungerar precis som för andra typer av frågor i Supply Chain Management. Fälten här är skrivskyddade och visar värden som är relaterade till frågan.

    ![Snabbfliken Poster att inkludera i dialogrutan Planerad orderbekräftelse.](./media/planned-order-firming-main-2.png "Snabbfliken Poster att inkludera i dialogrutan Planerad orderbekräftelse")

1. Välj **Förhandsgranskning** om du vill förhandsgranska innehållet i den bekräftade ordern, baserat på de inställningar du gjort hittills. Listan över planerade order som ska bekräftas visas som ett meddelande. Du kan sedan justera inställningarna efter behov tills förhandsgranskningen visar den bekräftade ordern så som du har tänkt dig.

    ![Exempel på en bekräftad orderförhandsgranskning.](./media/planned-order-firming-preview.png "Exempel på en bekräftad orderförhandsgranskning")

    > [!WARNING]
    > Med den här funktionen kan alla planerade order som matchar filterkriteriet bekräftas. Okritiskt bekräftande av planerade order kan leda till att ett stort antal oönskade inköps-, överförings- och tillverkningsorder skapas. Innan du fortsätter ska du alltid använda knappen **Förhandsgranskning** för att validera posterna som ska ingå.

1. På snabbfliken **Kör i bakgrunden** konfigurerar du jobbet så att det körs i batchläge och/eller konfigurerar du ett återkommande schema. Fälten fungerar precis som de gör för andra typer av [bakgrundsjobb](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) i Supply Chain Management.
1. Välj **OK** om du vill använda inställningarna och generera bekräftade order.

## <a name="track-firmed-orders"></a>Spåra bekräftade order

Följ de här stegen om du vill spåra en planerad order som har bekräftats:

1. [Öppna listsidan för planerade order](approved-planned-order.md#view-planned-orders).
1. Öppna eller välj den planerade order som du vill spåra.
1. I åtgärdsfönstret: På fliken **Visa**, i gruppen **Visa**, väljer du **Bekräftelsehistorik**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
