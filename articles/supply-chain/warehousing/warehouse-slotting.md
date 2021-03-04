---
title: Artikelplacering för lagerställe
description: Den här ämnet innehåller information om artikelplacering för lagerställe. Artikelplacering för lagerställe låter dig konsolidera efterfrågan per artikel och enhet från order som har status beställt, reserverat eller frisläppt. Det underlättar för lagerchefer att planera plockningsplatser innan de frigör order till lagerstället och skapar plockningsarbete.
author: mirzaab
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation, WHSSlotDemandLocated, WHSSlotDemand, WHSSlotUOMTier, WHSSlotTemplate, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 31b86837735ca16610a1d304eab611b12a6aceeb
ms.sourcegitcommit: be4b9d557511bbb43e71a93f2c3b23b5f1a4669d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/24/2020
ms.locfileid: "4627759"
---
# <a name="warehouse-slotting"></a>Artikelplacering för lagerställe

[!include [banner](../includes/banner.md)]

Flera funktioner artikelplacering för distributionslager är tillgängliga för att hjälpa till lagerchefer att planera plockningsplatser innan de frigör order till lagerstället och skapar plockningsarbete.

*Funktioner för artikelplacering* för lagerställe låter dig konsolidera efterfrågan per artikel och enhet från order som har status *beställt*, *reserverat* eller *frisläppt*. Genererade behov kan sedan tillämpas på platser som ska användas för plockning, baserat på kvantitet, enhet, fysiska dimensioner, fasta platser och mycket mer. När artikelplaceringsplanen har fastställts kan du skapa ett lagerpåfyllnadsarbete för att hämta en lämplig lagermängd till varje plats.

Funktionen *Artikelplacering för distributionslager för överföringsorder* kan lagerchefer fylla på plockplatser baserat på efterfrågan från överföringsorder som ännu inte släppts till lagret. Det säkerställer att plockplatser innehåller alla artiklar som krävs för överföringsorder när de har frisläppts till lagerställe. Denna funktion kräver att du även aktiverar funktionen för funktionen *Artikelplacering för distributionslager*.

Funktionen *förbättrad allokering av artikelplacering för distributionslager* lägger till ett alternativ för de mallrader som används i funktionen *artikelplacering för distributionslager*. Alternativet gör det möjligt att överväga befintlig lagerbehållning på en målplats. Därför kan färre påfyllningar genereras för artikelplacering. Funktionen *förbättrad allokering av artikelplacering för distributionslager* kräver att du även aktiverar funktionen *artikelplacering för distributionslager*. Den kan också användas tillsammans med funktionen *Artikelplacering för distributionslager för överföringsorder*.

## <a name="turn-on-the-warehouse-slotting-features"></a>Aktivera funktionen artikelplacering för lagerställe

Innan du kan använda dessa funktioner måste de aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera status för dessa funktioner och aktivera dem om de behövs. Aktivera följande funktioner om det behövs:

- Lagerställets tilldelningsfunktion
- Artikelplacering i distributionslager för överföringsorder

    > [!IMPORTANT]
    > Funktionen för *Funktionen artikelplacering för lagerställe* måste aktiveras före den här funktionen.

- Förbättringar av allokering av artikelplacering i distributionslager

    > [!IMPORTANT]
    > Funktionen för *Funktionen artikelplacering för lagerställe* måste aktiveras före den här funktionen.

## <a name="set-up-warehouse-slotting"></a>Ställ in artikelplacering för lagerställe

Om du vill använda artikelplacering för lagerställe måste du ställa följande element i systemet:

- Måttenhetsnivåer för artikelplacering
- Direktivkoder
- Artikelplaceringsmallar
- Platsdirektiv

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a>Skapa måttenhetsnivåer för artikelplacering

Enhetsmåttnivåer gör att flera måttenheter kan grupperas tillsammans i en artikelplacering. Om t.ex. flera storlekar av lådorna har valts från samma låda, kan en nivå skapas för alla storlekar. **En rad måste skapas för varje måttenhet som ska ingå i nivån.**

1. Gå till **Lagerstyrning \> Inställningar \> Påfyllning \> Måttenhetsnivåer för artikelplacering**.
1. Välj **Ny**.
1. I rubriken anger du följande värden:

    - **Enhetsnivå:** *EaBoxPl*
    - **Beskrivning:** *Varje låda, lastpall*

1. Välj **Spara**.
1. På snabbfliken **Måttenheter** välj **Ny** för att lägga till en rad i rutnätet.
1. Ställ in följande värden på denna nya rad:

    - **Enhet:** *låda*
    - **Beskrivning:** Lämna det här fältet tomt. Den fylls i automatiskt när du sparar ändringarna.
    - **Enhetsklass:** *kvantitet*

1. Välj **Ny** om du vill lägga till andra rad i rutnätet.
1. Ställ in följande värden på denna nya rad:

    - **Enhet:** *ea*
    - **Beskrivning:** Lämna det här fältet tomt. Den fylls i automatiskt när du sparar ändringarna.
    - **Enhetsklass:** *kvantitet*

1. Välj **Ny** om du vill lägga till tredje rad i rutnätet.
1. Ställ in följande värden på denna nya rad:

    - **Enhet:** *PL*
    - **Beskrivning:** Lämna det här fältet tomt. Den fylls i automatiskt när du sparar ändringarna.
    - **Enhetsklass:** *kvantitet*

1. Välj **Spara** för att spara nivån.

### <a name="create-a-directive-code-for-slotting"></a>Skapa en direktivkod för artikelplacering

Du måste välja den direktivkod som ska associeras med en mall.

1. Gå till **Lagerstyrning \> Inställningar \> Direktivkoder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **Direktivkod**, ange *Artikelplacering*.
1. I fältet **Beskrivning av direktivkod**, ange *Artikelplacering*.

### <a name="set-up-slotting-templates"></a>Ställ in artikelplaceringsmallar

Varje artikelplaceringsmall styr hur lagret tilldelas till platser för ett visst lagerställe. Varje mall måste innehålla en rad för varje artikelplaceringsspecifikation. Använd procedurerna i det här avsnittet om du vill ställa in artikelplaceringsmallar.

1. Gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Artikelplaceringsmallar**.
1. Skapa en ny mall genom att välja **Nytt**.

Sedan måste du ställa in mallhuvudet, artikelplaceringsspecifikation och platsdirektiven, enligt beskrivningen i följande underavsnitt. Inställningen för artikelplacering för överföringsorder liknar inställningen för artikelplacering för försäljningsorder, men **Efterfrågetyp** anges till *Överföringsorder* istället för *Försäljningsorder*.

#### <a name="set-up-the-header-for-a-sales-order-slotting-template"></a>Ställ in rubriken för en mall för att skapa en försäljningsorder

1. Ange följande värden i mallens rubrik:

    - **Artikelplaceringsmall:** _61_
    - **Beskrivning:** _61_
    - **Efterfrågetyp:** *försäljningsorder*

        > [!NOTE]
        > För närvarande är *Försäljningsorder* och *Överföringsorder* de enda typer av efterfrågan som stöds. Du kan bara välja *Överföringsorder* om funktionen *Artikelplacering i distributionslager för överföringsorder* är aktiverad.

    - **Efterfrågestrategi:** _beställt_

        Följande värden finns i detta fält:

        - **Beställt** – hela den beställda kvantiteten på försäljningsordern ska behandlas som efterfrågan.
        - **Reserverat** – endast försäljningsorderradens kvantitet som är reserverade (fysiska och beställda) ska betraktas som efterfrågan.
        - **Frisläppt** – den frisläppta kvantiteten ska behandlas som efterfrågan.

    - **Lagerställe:** _61_
    - **Tillåt påfyllnad av efterfrågan att använda icke-reserverade kvantiteter:** _Ja_

Du kan även ange en fråga för att begränsa omfattningen av den efterfrågan som utvärderas.

#### <a name="set-up-slotting-specifications-for-each-template"></a>Ställa in en artikelplaceringsspecifikation för varje mall

För varje försäljningsordermall som du skapar lägger du till en rad för varje artikelplaceringsspecifikation genom att följa stegen nedan.

1. På snabbfliken **Information artikelplaceringsspecifikation** välj **Ny** för att skapa en mallrad.
1. Ställ in följande värden på denna nya rad:

    - **Sekvens:** _1_
    - **Beskrivning:** _Fast plats_
    - **Minsta kvantitet:** _1_

        I det här fältet definieras den minsta kvantitet efter frågan som krävs för raden.

    - **Högsta kvantitet:** _1000000_

        I det här fältet definieras den högsta kvantitet för efterfrågan som är giltig för raden.

    - **Enhet:** Lämna detta fält tomt.

        I det här fältet anges den måttenhet som lägsta och högsta kvantiteter refererar till.

    - **Måttenhetsnivå:** _EaBoxPl_

        I det här fältet definieras den enhetsnivå för efterfrågan som är giltig för raden. (Mer information finns i avsnittet [Ange måttenhetsnivå för artikelplacering](#unit-tiers) tidigare i det här avsnittet.)

    - **Tilldela kortkriterier:** _Överväg kvantitet_

        Följande värden finns i detta fält:

        - **Antag vara tom** – det här systemet ska anta att alla platser i plockområdet är tomma och inte ska kontrollera lagerställen.
        - **Överväg kvantitet** – Systemet bör kontrollera platserna i plockningsområdet för inventering och bör hoppa över alla platser som inte är tomma.
        - **Överväg lagerbehållning** – systemet bör kontrollera om det finns icke reserverade kvantiteter för artikeln på efterfrågeraden. Om kvantiteten är tillräckligt stor för att kunna uppfylla minst en enhet av efterfrågeraden, reduceras den genererade artikelplaceringsposten med det tillgängliga beloppet. Om efter frågan t.ex. är 10 ärenden och ett ärende är i handen, kommer den efterfrågan att vara nio ärende. Om efterfrågan är 10 ärenden och varje är i handen, kommer den efterfrågan att vara 10 ärenden. Det här värdet är bara tillgängligt om funktionen *Förbättringar av allokering av artikelplacering i distributionslager* är aktiverad.

    - **Direktiv kod:** _Artikelplacering_

        I det här fältet definieras det platsdirektiv som används för att hitta plockplatsen för påfyllningsarbetet.

    - **Spillplats:** lämna det här fältet tomt.

        Det här fältet definierar det lagerställe som har placerats på om det inte går att hitta en plats för kvantiteten när raden bearbetas.

    - **Tillåt låt upp:** _Ja_

        Om det här alternativet är inställt på *Ja*, kommer flyttningsarbetet att skapas för att ta ut lagret med lagerställen, men där inget har öppnats. Mallen körs sedan igen. Den här gången ignoreras lagret på platserna. Den här funktionen fungerar bäst om fältet **Tilldela kortplatskriterier** är inställt på _Överväg kvantitet_.

    - **Användning av fast lagerplats:** _Endast fasta lagerplatser för produkten_

        Följande värden finns i detta fält:

        - **Fasta och icke-fasta lagerplatser** – systemet ska inte begränsas till att bara använda fasta lagerplatser.
        - **Endast fasta lagerplatser för produkten** – systemet ska endast kortas till platser som är fasta lagerplatser för produkten.
        - **Endast fasta lagerplatser för produktvarianten** – systemet ska endast kortas till platser som är fasta lagerplatser för produktvarianten.

> [!NOTE]
> Om artikelplaceringsmallen innehåller minst en rad där fältet **Tilldela kortkriterier** anges *Överväg lagerbehållning*, minskningar är inte längre tillåtna för någon rad i mallen.

1. Välj **Spara**.
1. Klicka på **Ny** för att skapa en andra mallrad.
1. Ställ in följande värden på denna nya rad:

    - **Sekvens:** _2_
    - **Beskrivning:** _andra_
    - **Minsta kvantitet:** _1_
    - **Högsta kvantitet:** _1000000_
    - **Enhet:** Lämna detta fält tomt.
    - **Enhetsnivå:** _EaBoxPl_
    - **Tilldela kortkriterier:** _Överväg kvantitet_
    - **Direktiv kod:** _Artikelplacering_
    - **Spillplats:** lämna det här fältet tomt.
    - **Tillåt låt upp:** _Ja_
    - **Använda fasta lagerplatser:** _Fasta och ej fasta platser_

    I frågan för den andra raden kommer du nu att ange de kriterier som används för att bestämma vilka platser som efter frågan för den raden kan avsättas till.

1. Välj raden där fältet **Sekvens** är inställt på *2*.
1. Välj **Redigera fråga**.
1. På fliken **intervall**, välj **Lägg till** om du vill lägga till en rad i rutnätet.
1. Ställ in följande värden på denna nya rad:

    - **Register:** *platser*
    - **Härlett register:** *platser*
    - **Fält:** *platsprofil-ID*
    - **Kriterier:** *Plocka-06* (Välj det dubbla plustecknet \[**++**\] i fältet för att expandera listan och välj sedan *Plocka-06* - *Plockplats 6*.)

1. Välj **OK**.

#### <a name="set-up-location-directives"></a>Ställ in platsdirektiv

Minst ett platsdirektiv måste ställas in för att stödja plockning av artikelplacering. Använd procedurerna i det här avsnittet om du vill skapa ett nytt *platsdirektiv för påfyllnad* för plockning av artikelplacering.

1. Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.
1. I vänstra fönstret i fältet **Typ av arbetsorder** väljer du *lagerpåfyllnad*.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I rubriken för det nya platsdirektivet anger du i fältet **Namn** *61 plocka artikelplacering*.
1. I fältet **Löpnummer** acceptera standardvärdet.

##### <a name="configure-the-location-directives-fasttab"></a>Konfigurera snabbfliken platsdirektiv

1. Ange följande värden på snabbfliken **Platsdirektiv**. Acceptera standardvärden för alla andra fält.

    - **Arbetstyp:** _plockning_
    - **Plats:** _6_
    - **Lagerställe:** _61_
    - **Direktiv kod:** _Artikelplacering_

1. Välj **Spara** om du vill göra snabbfliken **Rader** tillgänglig.

##### <a name="configure-the-lines-fasttab"></a>Konfigurera snabbfliken Rader

1. På snabbfliken **Rader**, klicka på **Ny** för att skapa en ny rad.
1. Ställ in följande värden på denna nya rad.

    - **Från kvantitet:** _0_
    - **Till kvantitet:** _1000000_

1. Acceptera standardvärden för kvarvarande fält.
1. Välj **Spara** om du vill göra snabbfliken **Platsdirektivåtgärd** tillgänglig.

##### <a name="configure-the-location-directive-actions-fasttab"></a>Konfigurera snabbfliken Platsdirektivåtgärder

1. På snabbfliken **Platsdirektivåtgärder** välj **Ny** för att skapa en rad.
1. Ställ in följande värden på denna nya rad. Acceptera standardvärden för alla andra fält.

    - **Löpnummer:** Acceptera standardvärdet.
    - **Namn:** _Bulk_
    - **Strategi:** _ingen_

1. Acceptera standardvärden för kvarvarande fält.
1. Välj **Spara** om du vill göra knappen **Redigera fråga** tillgänglig.

##### <a name="edit-the-query"></a>Redigera frågan

1. På snabbfliken **Platsdirektivåtgärder** välj **Redigera fråga**.
1. På fliken **intervall**, välj **Lägg till** om du vill lägga till en rad i rutnätet.
1. Ställ in följande värden på denna nya rad:

    - **Register:** *platser*
    - **Härlett register:** *platser*
    - **Fält:** *zon-ID*
    - **Kriterier:** *Bulk* (Välj det dubbla plustecknet \[**++**\] i fältet för att expandera listan och välj sedan *Bulk*.)

1. Välj **OK**.

## <a name="scenario"></a>Scenario

### <a name="set-up-the-scenario"></a>Ställ in scenario

I det här scenariot ska du använda de inbyggda exempeldata och skapa posterna som beskrivs i det här avsnittet.

#### <a name="use-the-usmf-sample-data"></a>Använd exempeldata för USMF

Om du vill arbeta genom detta scenario med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats. Dessutom måste du välja den **USMF** juridiska personen innan du börjar.

#### <a name="create-demand"></a>Skapa efterfrågan

Skapa den efter frågan som du vill använda skåra på genom att följa stegen nedan.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Skapa en försäljningsorder genom att välja **Ny**.
1. I dialogrutan **Skapa försäljningsorder** i fältet **Kundkonto** välj _US-007_.
1. I fältet **Lagerställe**, välj _61_.
1. Välj **OK**.
1. Den nya försäljningsordern öppnas. Den innehåller en tom rad i snabbfliken **Försäljningsorderrader**. Ställ in följande värden på denna rad:

    - **Artikel:** _L0101_
    - **Kvantitet:** _20_

1. Välj **Lägg till rad** för att lägga till en nya rad och ställa in följande värden:

    - **Artikel:** _T0100_
    - **Kvantitet:** _8_

1. Välj **Spara**.
1. Skapa en andra försäljningsorder genom att välja **Ny**.
1. I dialogrutan **Skapa försäljningsorder** i fältet **Kundkonto** välj _US-008_.
1. I fältet **Lagerställe**, välj _61_.
1. Den nya försäljningsordern öppnas. Den innehåller en tom rad i snabbfliken **Försäljningsorderrader**. Ställ in följande värden på denna rad:

    - **Artikel:** _T0100_
    - **Kvantitet:** _1_

1. Välj **Spara**.

### <a name="walk-through-a-typical-slotting-scenario"></a>Gå igenom ett vanligt artikelplaceringsscenario

När alla nödvändiga element är på rätt sätt, så som beskrivs i föregående avsnitt, är du redo att testa funktionen genom att arbeta igenom varje övning i det här avsnittet.

#### <a name="generate-demand"></a>Generera efterfrågan

1. Gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Artikelplaceringsmallar** och välj artikelplaceringsmallen som du skapade tidigare.
1. Välj **efterfrågeprognoser** i åtgärdsfönstret. Det här kommandot utvärderar alla efter frågan i systemet och matchar den i artikelplaceringsmallen. Den totala efter frågan på alla order konsolideras sedan på en rad per kvantitet/måttenhet. Ett informationsmeddelande visas när processen har slutförts.

#### <a name="slotting-demand"></a>Efterfrågan för artikelplacering

*Behovet av artikelplacering* visar resultatet av efterfrågegenereringen, baserat på inställningarna för den artikelplaceringsmallen.

- I åtgärdsfönstret, välj **Behovet av artikelplacering** du vill visa resultaten från kommandot **Efterfrågeprognoser**. Raderna i artikelplaceringsbehov kan redigeras. Du kan ta bort en rad, lägga till en ny rad eller redigera raddetaljerna.

> [!NOTE]
> Du kan redigera efter frågan manuellt eller också kan du importera den från ett externt system genom att använda datahantering. Det som finns i artikelplaceringsbehov kommer att användas i nästa steg, oavsett var det kom från.

#### <a name="locate-demand"></a>Hitta efterfrågan

Efter att efterfrågan har genererats måste du använda kommandot **Hitta efterfrågan** för att generera den *Artikelplaceringsplanen*.

- Välj **Hitta efterfrågan** i åtgärdsfönstret. Artikelplaceringsprocessen körs. Ett informationsmeddelande visas när processen har slutförts.

#### <a name="slotting-plan"></a>Plan för artikelplacering

Artikelplaceringsplanen visar platsen som varje artikel/kvantitet har tilldelats för, om spill användes, om det är fråga om att arbeta med rader och vilka mallrader som användes. *Alla efterfrågan som inte kan skåras markeras i artikelplacering.*

- I åtgärdsfönstret, välj **Artikelplaceringsplan** du vill visa resultaten.

> [!NOTE]
> - Processen **Generera efterfrågan**, **Hitta efterfrågan** och **Kör lagerpåfyllnad** processer i ett begränsat läge. (Dessa processer är tillgängliga från åtgärdsfönstret på sidan **artikelplaceringsmallar**).
> - Processer **Generera efterfrågan**, **Lokalisera efterfrågan** och **Kör lagerpåfyllnad** processer har ett lås för att säkerställa att de inte kan utlösas samtidigt. I annat fall kan data som används tas bort.
> - Processerna **Generera efterfrågan** och **Lokalisera efterfrågan** visar en varning om körningen inte genererade poster, eller om det saknas information om posterna.
> - När du väljer en **Plan för artikelplacering** har inte sidan knapparna **Ny**, **Redigera** eller **Ta bort** i åtgärdsfönstret eftersom datakällan inte kan redigeras.
> - När du väljer **Kör påfyllnad**, validerar systemet den valda platsens mall och processer.

#### <a name="create-replenishment"></a>Skapa lagerpåfyllnad

När du har skapat en artikelplaceringsplan måste du skapa *lagerpåfyllningsarbete* baserat på planen.

- I åtgärdsfönstret, klicka på **Kör lagerpåfyllnad**. Ett informationsmeddelande visas när processen har slutförts. Det här meddelandet visar antalet huvuden som har skapats för versions-ID för arbete.

De platsdirektiv som kommer att användas identifieras utifrån den direktivkod som anges på varje rad i en mall.

## <a name="tips"></a>Tips:

### <a name="set-up-automatic-slotting"></a>Ställ in automatisk artikelplacering

När alla nödvändiga element är på plats kan du ställa in artikelplacering så att de körs automatiskt genom att följa stegen nedan.

1. Gå till **Lagerstyrning \> Lagerpåfyllnad \> Köra artikelplacering**.
1. Ange de artikelplaceringssteg som ska köras. Välj ett eller flera av följande artikelplaceringssteg:

    - Generera efterfrågan
    - Hitta efterfrågan
    - Skapa lagerpåfyllnadsarbete

    > [!NOTE]
    > Artikelplaceringsstegen är progressiva. Om du vill välja *Hitta efterfrågan* måste du först välja *Generera efterfrågan*.

1. Ange vilken artikelplaceringsmall som ska användas.
1. Ställ in upprepning så att körningen sker automatiskt om du vill.

I övningarna i scenariot ska du **inte** ställa in automatisk artikelplacering.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]