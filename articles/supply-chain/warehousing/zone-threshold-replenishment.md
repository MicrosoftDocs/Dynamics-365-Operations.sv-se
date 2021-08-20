---
title: Zontröskel för lagerpåfyllnad
description: Vid en zonbaserad lagerpåfyllnad används en återanskaffningsstrategi av minsta/högsta (min/max), men den utvärderar hela lagerzoner istället för bara enskilda platser. Därför kan lagerchefer lära sig snabbare om ytterligare lager krävs i en plockzon.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocDirHint, WHSLocDirTable, WHSRequestType
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 4dde844d38448b2de5c5e0c9b2da4a16405f83c0d72f3a20b9e29afe84d322ac
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6743492"
---
# <a name="zone-threshold-replenishment"></a>Zontröskel för lagerpåfyllnad

[!include [banner](../includes/banner.md)]

Vid en zonbaserad lagerpåfyllnad används en [återanskaffnings](replenishment.md)-strategi av minsta/högsta (min/max), men den utvärderar hela lagerzoner istället för bara enskilda platser. Därför kan lagerchefer lära sig snabbare om ytterligare lager krävs i en plockzon.

Inställningen för den här funktionen liknar inställningen för platsbaserad lagerpåfyllnad. När du ställer in en mall för den minsta/högsta lagerpåfyllnad kan du också ange om tröskeln ska utvärderas per lagerställe eller per zon. Om du ställer in utvärdering som baseras på zoner måste du lägga till specifika zoner i urvalsfrågan för zoner.

T.ex. platsbaserad min/max lagerpåfyllnad, zonbaserade krav på min/max lagerpåfyllnad baseras på inställningen av ett minsta lagertröskelvärde som utlöser ett lagerpåfyllningsarbete för valda artiklar. Detta lagerpåfyllningsarbete ökar lagret till det angivna maximala tröskelvärdet för zonen.

> [!NOTE]
> Zonåteranskaffningsprocesser för produktvarianter stöds inte i den aktuella versionen.


Till skillnad från platsbaserad minsta lagerpåfyllnad, kräver zonbaserade min/max lagerpåfyllnad inte fasta platser för att utvärdera om platser ska lagra en viss artikel. Med hjälp av zonbaserad lagerpåfyllnad kan du därför använda min/max lagerpåfyllnad även om du inte har fasta platser för varje artikel eller artikelvariant i lagerstället. När en kvantitet i zonen ligger under det angivna minimitröskelvärdet skapas lagerpåfyllnadsarbetet. Platsdirektiv avgör vilken plats lagret ska placeras i.

## <a name="turn-on-the-zone-threshold-replenishment-feature"></a>Aktivera funktionen Zontröskel för lagerpåfyllnad

Innan du kan använda funktionen *Zontröskel för lagerpåfyllnad* den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionens namn:** *Zontröskel för lagerpåfyllnad*

## <a name="set-up-zone-based-replenishment"></a><a name="setup"></a>Ställ in zonbaserad lagerpåfyllnad

Om du vill ställa in zonbaserad lagerpåfyllnad måste du konfigurera flera delar av systemet. Det här avsnittet innehåller en introduktion till de olika inställningarna och innehåller datavärden för demonstrationer som du kan ange om du vill arbeta genom scenariot i slutet av det här avsnittet.

### <a name="set-up-directive-codes"></a>Ställ in direktivkoder

[Direktivkoder](control-warehouse-location-directives.md) låter dig vara mer specifik när du definierar platsmallen som används i en arbetsmall. Varje kod bestämmer ett gemensamt värde som du kan referera till när du konfigurerar respektive malltyp.

#### <a name="view-and-edit-directive-codes"></a>Visa och redigera direktivkoder

Gå till om du vill se eller redigera dina direktivkoder **Lagerstyrning \> Inställning \> Direktivkoder**.

#### <a name="prepare-demo-data-directive-codes"></a>Förbered demodata, direktivkoder

Det här exemplet visar hur du förbereder en direktivkod. Om du planerar att arbeta genom scenariot i slutet av det här avsnittet ska du använda de datavärden för demon som finns här. I annat fall använder du dina egna värden.

1. Välj den juridiska personen **USMF** för att arbeta med demodata.
1. Gå till **Lagerstyrning \> Inställningar \> Direktivkoder**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.
1. I den nya raden anger du följande värden:

    - **Direktivkod:** _Zonlagerp_
    - **Direktivbeskrivning:** _Zonlagerpåfyllnad_

1. Välj **Spara** för att spara den nya koden.

### <a name="set-up-replenishment-templates"></a>Konfigurera mallar för lagerpåfyllnad

[Mallar för min/max lagerpåfyllnad](tasks/set-up-min-max-replenishment-process.md) är den primära mekanismen för att bibehålla optimala nivåer på plockplatser. I dessa mallar måste du ställa in de regler som ska användas för att fylla på lagret i lagerstället. Påfyllningen som mallarna kan användas för inkluderar zonbaserad lagerpåfyllnad.

#### <a name="view-and-edit-replenishment-templates"></a>Visa och redigera påfyllnadsmallar

En mall för lagerpåfyllnad är en uppsättning regler som kontrollerar hur en plats fylls på. Du väljer en mall som styr när och hur påfyllnaden görs. Om du vill visa eller redigera dina påfyllningsmallar, gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Mallar för lagerpåfyllnad**.

#### <a name="prepare-a-demo-data-replenishment-template"></a>Förbereda en demodata mall för lagerpåfyllnad

Det här exemplet visar hur du förbereder en mall för lagerpåfyllnad. Om du planerar att arbeta genom scenariot i slutet av det här avsnittet ska du använda de datavärden för demon som finns här. I annat fall använder du dina egna värden.

1. Välj den juridiska personen **USMF** för att arbeta med demodata.
1. Gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Mall för lagerpåfyllnad**.
1. Välj **Redigera** om du vill placera sidan i redigeringsläge.
1. I åtgärdsfönstret, välj **Ny** om du vill lägga till en rad i rutnätet **Översikt**.
1. I den nya raden anger du följande värden. Acceptera standardvärden för alla andra fält.

    - **Lagerpåfyllnadsmall:** _Zon min/max lagerp_
    - **Beskrivning:** _Zon min/max lagerpåfyllnad_
    - **Lagerpåfyllnadstyp:** _Minimum eller maximum_

1. Välj **Spara**.
1. Medan den nya raden fortfarande är markerad i rutnätet **Översikt**, välj **Ny** ovanför rutnätet **Information om mall för lagerpåfyllnad** för att lägga till en rad som är kopplad till *Zon min/max lagerp* som du just skapade.
1. I den nya raden anger du följande värden:

    - **Löpnummer:** Ange _1_.
    - **Beskrivning:** Ange _Välj zonlagerpåfyllnad_.
    - **Påfyllningsenhet:** Välj _ea_.
    - **Begärandetyp:** Lämna det här fältet tomt.
    - **Direktivkod:** Det här fältet länkar påfyllningsmallen med ett platsdirektiv. Välj den versionskod för demodata som du skapade tidigare (_Zonlagerp_).
    - **Arbetsmall:** Lämna det här fältet tomt.
    - **Minsta kvantitet:** Det här fältet anges den kvantitet som påfyllnaden ska utlösas vid. Ange _50_.
    - **Högsta kvantitet:** Det här fältet anger den maximala kvantiteten för en artikel som kan finnas i en zon. Genererat återanskaffningsarbete ökar lagret till denna kvantitet. Ange _150_.
    - **Enhet:** Det här fältet anger enheten för minimi- och maximivärden. Välj _ea_.
    - **Efterfråganökning:** Välj _Avrunda uppåt_.
    - **Fyll på tomma fasta lagerplatser:** Välj denna kryssruta.
    - **Fyll endast på tomma fasta lagerplatser:** Rensa den här kryssrutan.
    - **Läget produktfråga:** Välj _Produktfråga_.
    - **Tröskelomfattning för lagerpåfyllnad:** Det här fältet definieras om mallen ska utvärdera per zon eller efter ett visst lagerställe. Välj _Zon_.
    - **Lagerställe:** Välj _61_.

1. Välj **Välj produkter** ovanför rutnätet **Information om mall för lagerpåfyllnad**.
1. I dialogrutan **Produktfråga** på fliken **Intervall** välj **Lägg till** om du vill lägga till en rad i rutnätet.
1. I den nya raden anger du följande värden:

    - **Register:** _Artiklar_
    - **Härlett register:** _Artiklar_
    - **Fält:** _Artikelnummer_
    - **Kriterier:** _A0001_

1. Välj **OK** om du vill spara din fråga och stänga dialogrutan.
1. Välj **Välj zoner att fylla på** ovanför rutnätet **Information om mall för lagerpåfyllnad**.
1. I dialogrutan **Zonfråga** på fliken **Intervall** om du vill lägga till en rad i rutnätet.
1. I den nya raden anger du följande värden:

    - **Register:** _Lagerställezon_
    - **Härlett register:** _Lagerställezon_
    - **Fält:** _zon-ID_
    - **Kriterier:** _VÅNING_

1. Välj **OK** om du vill spara din fråga och stänga dialogrutan.

### <a name="set-up-location-directives"></a>Ställ in platsdirektiv

Till skillnad från platsbaserad min/max påfyllnadsenhet, zonbaserade min/max lagerpåfyllnad kräver att du måste ställa in både platsdirektiv för plockning och platsdirektiv för placering eftersom systemet utvärderar hela zonen istället för bara plockningsplatsen för utgående arbete.

#### <a name="view-and-edit-location-directives"></a>Visa och redigera platsdirektiv

Gå till om du vill se eller redigera dina platsdirektiv **Lagerstyrning \> Inställning \> Platsdirektiv**.

Se nästa avsnitt för exempel som visar hur du använder inställningarna för att skapa de obligatoriska platsdirektiven för plockning och platsdirektiven för placering.

#### <a name="prepare-demo-data-location-directives"></a>Förbered demodata, platsdirektiv

Om du vill förbereda demodata så att de kan användas i scenariot i slutet av det här ämnet måste du skapa två platsdirektiv: ett för plockning och en för placering.

##### <a name="create-a-replenishment-pick-directive"></a>Skapa en platsdirektiv för lagerpåfyllnad

1. Välj den juridiska personen **USMF** för att arbeta med demodata.
1. Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.
1. I vänster ruta ange fältet **Arbetsordertyp** till _Lagerpåfyllnad_.
1. I åtgärdsfönstret, välj **Ny** för att skapa ett nytt direktiv.
1. Ange följande värden.

    - **Löpnummer:** Acceptera standardvärdet.
    - **Namn:** Ange _Zonlpockning_.
    - **Arbetstyp:** Välj _Plocka_.
    - **Plats:** Välj _6_.
    - **Lagerställe:** Välj _61_.
    - **Direktivkod:** Lämna det här fältet tomt.
    - **Flera SKU:** Ange det här alternativet till _Nej_.

1. Välj **Spara** om du vill skapa ett direktiv med de inställningar som du har konfigurerat hittills.
1. På snabbfliken **Rader** välj **Ny** för att lägga till en rad i rutnätet.
1. Ställ in följande värden på denna nya rad:

    - **Löpnummer:** Ange _1_.
    - **Från kvantitet:** Ange _0_.
    - **Till kvantitet:** Ange _10000000_.
    - **Enhet:** Lämna detta fält tomt.
    - **Lokalisera kvantitet:** Välj _Ingen_.
    - **Begränsa efter enhet:** avmarkera kryssrutan.
    - **Avrunda till enhet:** avmarkera den här kryssrutan.
    - **Sök efter förpackningskvantitet:** avmarkera den här kryssrutan.
    - **Tillåt delning:** Markera kryssrutan.

1. Välj **Spara** för att spara den nya raden.
1. Även om den nya raden fortfarande är markerad i rutnätet **Rader** välj **Ny** snabbfliken **Åtgärder för platsdirektiv** för att lägga till en rad i rutnätet.
1. I den nya raden anger du följande värden:

    - **Löpnummer:** Ange _1_.
    - **Namn:** Ange _Plockning från bulk_.
    - **Användning av fast lagerplats:** Välj _Fasta och ej fasta platser_.
    - **Tillåt negativt lager:** Avmarkera den här kryssrutan.
    - **Batchaktiverad:** Avmarkera den här kryssrutan.
    - **Strategi:** Välj _ingen_.

1. Välj **Spara** för att spara den nya åtgärden.
1. Medan den nya åtgärden fortfarande är markerad väljer du **Redigeringsfråga** ovanför rutnätet **Platsdirektivåtgärd**.
1. Dialogruta för fråga visas där du kan välja vilka platser som ska fyllas på från. På fliken **intervall**, välj **Lägg till** om du vill lägga till rutnätet.
1. I den nya raden anger du följande värden:

    - **Register:** _platser_
    - **Härlett register:** _platser_
    - **Fält:** _zon-ID_
    - **Kriterier:** _BULK_

1. Välj **OK** om du vill spara din fråga och stänga dialogrutan.
1. Välj **Spara** om du vill spara dina platsdirektiv.

##### <a name="create-a-replenishment-put-directive"></a>Skapa ett placeringsdirektiv för lagerpåfyllnad

1. På sidan **Platsdirektiv** i det vänstra fönstret, kontrollerar du att fältet **Typ av arbetsorder** fortfarande är inställt på _Lagerpåfyllnad_.
1. I åtgärdsfönstret, välj **Ny** för att skapa ett nytt direktiv.
1. Ange följande värden.

    - **Löpnummer:** Acceptera standardvärdet.
    - **Namn:** Ange _Zonplacering_.
    - **Arbetsordertyp:** Välj _Placera_.
    - **Plats:** Välj _6_.
    - **Lagerställe:** Välj _61_.
    - **Direktivkod:** Välj _Zonlagerp_ om du vill länka det här platsdirektivet till den lagerpåfyllnadsmall som du skapade tidigare med hjälp av koden som du skapade tidigare.
    - **Flera SKU:** Ange det här alternativet till _Nej_.

1. Välj **Spara** om du vill skapa ett direktiv med de inställningar som du har konfigurerat hittills.
1. På snabbfliken **Rader** välj **Ny** för att lägga till en rad i rutnätet.
1. Ställ in följande värden på denna nya rad:

    - **Löpnummer:** Ange _1_.
    - **Från kvantitet:** Ange _0_.
    - **Till kvantitet:** Ange _10000000_.
    - **Enhet:** Lämna detta fält tomt.
    - **Lokalisera kvantitet:** Välj _Ingen_.
    - **Begränsa efter enhet:** avmarkera kryssrutan.
    - **Avrunda till enhet:** avmarkera den här kryssrutan.
    - **Sök efter förpackningskvantitet:** avmarkera den här kryssrutan.
    - **Tillåt delning:** Markera kryssrutan.

1. Välj **Spara** för att spara den nya raden.
1. Även om den nya raden fortfarande är markerad i rutnätet **Rader** välj **Ny** snabbfliken **Åtgärder för platsdirektiv** för att lägga till en rad i rutnätet.
1. I den nya raden anger du följande värden:

    - **Löpnummer:** Ange _1_.
    - **Namn:** Ange _Zonplacering_.
    - **Användning av fast lagerplats:** Välj _Fasta och ej fasta platser_.
    - **Tillåt negativt lager:** Avmarkera den här kryssrutan.
    - **Batchaktiverad:** Avmarkera den här kryssrutan.
    - **Strategi:** Välj _konsolidera_.

1. Välj **Spara** för att spara den nya åtgärden.
1. Medan den nya åtgärden fortfarande är markerad väljer du **Redigeringsfråga** ovanför rutnätet **Platsdirektivåtgärd**.
1. Dialogruta för fråga visas där du kan välja vilka zonen som ska fyllas på till. Den här zonen ska vara samma zon som anges i mallen för lagerpåfyllnad. På fliken **intervall**, välj **Lägg till** om du vill lägga till rutnätet.
1. I den nya raden anger du följande värden:

    - **Register:** _platser_
    - **Härlett register:** _platser_
    - **Fält:** _zon-ID_
    - **Kriterier:** _VÅNING_

1. Välj **OK** om du vill spara din fråga och stänga dialogrutan.
1. Välj **Spara** om du vill spara dina platsdirektiv.

## <a name="scenario"></a>Scenario

Det här avsnittet innehåller ett exempel på ett scenario som visar hur funktionen fungerar.

### <a name="prepare-the-sample-data-that-is-required-for-the-sample-scenario"></a>Förbered de exempeldata som krävs för exempelscenariot

Innan du börjar arbeta i scenariot måste du aktivera exempeldata och ställa in funktionen enligt beskrivningen i det här avsnittet och i tidigare avsnitt i detta ämne.

#### <a name="use-the-usmf-legal-entity"></a>Använd USMF juridiska personen

Om du vill arbeta genom detta scenario med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats. Dessutom måste du välja den **USMF** juridiska personen innan du börjar.

#### <a name="prepare-additional-sample-data"></a>Förbered ytterligare exempeldata

När du har valt den juridiska personen för **USMF** lägger du till de ytterligare exempeldata som krävs, enligt beskrivningen i avsnittet [Ställ in zonbaserad lagerpåfyllnad](#setup) tidigare i det här avsnittet.

#### <a name="check-your-on-hand-inventory"></a>Kontrollera behållningslagret

Följ dessa steg för att se till att systemet har tillräckligt med inventering för att stödja exempelscenariot.

1. Kontrollera att det finns lagerbehållning för artikel *A0001* på två olika platser i pockzonen (*VÅNING*) som anges i mall för lagerpåfyllnad. Det totala lagret bör dock vara mindre än den obligatoriska minimikvantiteten (*50*) som anges i mallen för lagerpåfyllnad. På så sätt kan du simulera hur beräkningen sker för hela zonen istället för bara för en enda plats. **Med någon av lagerprocesserna kan du justera lagret efter behov.**
1. Kontrollera att det finns tillräckligt med lager för artikeln *A0001* på en bulkplats som är angiven i området välj plats för zon där lagerpåfyllnadsarbetet ska plocka artiklar från zon-ID *BULK*. Det totala lagret måste vara mindre än den obligatoriska maximala kvantiteten (*150*) som anges i mallen för lagerpåfyllnad.
1. Valfritt men rekommenderat: Följ de här stegen för att skapa en lagerjusteringsjournal:

    1. Gå till **Lagerhantering \> Journalposter \> Artiklar \> Lagerjustering**.
    1. Välj **Ny**.
    1. I dialogrutan **Skapa lagerjournal** i fältet **Lagerställe** välj *61*.
    1. Välj **OK**.
    1. På snabbfliken **Journalrader** använder du knappen **Ny** för att lägga till tre rader i rutnätet och anger följande värden. När du är klar med inställningarna för varje rad väljer du **Spara**.

        - **Rad 1:**

            - **Artikelnummer:** *A0001*
            - **Plats:** *6*
            - **Lagerställe:** *61*
            - **Plats:** *02A01R1S1B*
            - **ID-nummer:** Välj ett befintligt ID-nummer i listan eller skapa ett nytt ID-nummer.
            - **Kvantitet:** *1000*

        - **Rad 2:**

            - **Artikelnummer:** *A0001*
            - **Plats:** *6*
            - **Lagerställe:** *61*
            - **Plats:** *07A01R2S1B*
            - **ID-nummer:** Välj ett befintligt ID-nummer i listan eller skapa ett nytt ID-nummer.
            - **Kvantitet:** *15*

        - **Rad 3:**

            - **Artikelnummer:** *A0001*
            - **Plats:** *6*
            - **Lagerställe:** *61*
            - **Plats:** *07A01R1S1B*
            - **ID-nummer:** Välj ett befintligt ID-nummer i listan eller skapa ett nytt ID-nummer.
            - **Kvantitet:** *10*

    1. I åtgärdsfönstret, välj **Validera**. Åtgärda eventuella fel som hittas innan du går vidare till nästa steg.
    1. I åtgärdsfönstret, välj **Bokför** för att bokföra lager till lagerstället.

### <a name="sample-scenario-run-zone-based-minmax-replenishment"></a>Exempelscenario: kör zonbaserad min/max lagerpåfyllnad

När alla exempeldata som krävs finns på sin ställe kan du utlösa lagerpåfyllnad genom att följa stegen nedan.

1. Gå till **Lagerstyrning \> Lagerpåfyllnad \> Lagerpåfyllnad**.
1. I dialogrutan **Lagerpåfyllnad** på snabbfliken **Poster som ska ingå** väljer **Filter**.
1. I dialogrutan **Förfrågning** fliken **Sortiment** redigera standardtabellraden på följande sätt:

    - **Register:** Välj _lagerpåfyllnadsmallar_.
    - **Härlett register:** Välj _lagerpåfyllnadsmallar_.
    - **Fält:** Välj _lagerpåfyllnadsmall_.
    - **Kriterier:** Välj _Zon min/max lagerp_. Den här påfyllnadsmall är den påfyllnadsmall som du skapade när du förbereder demodata för det här scenariot.

1. Välj **OK** om du vill spara frågan och gå tillbaka dialogrutan **Lagerpåfyllnad**.
1. Klicka på **OK** om du vill köra mall för lagerpåfyllnad.

Lagerpåfyllnadsarbetet skapas nu för att plocka lagret från den *BULK* och sedan fylla på det till *VÅNING*.

## <a name="notes-and-tips"></a>Anteckningar och tips

Här följer några anmärkningar och tips för hur du arbetar med funktionen:

- Om du vill ställa in påfyllningsarbetet som går till önskad zon kan du länka påfyllnadsgrupp och mallrad för lagerpåfyllnad på något av följande sätt:

    - Redigera frågan för direktivrubrik för plats och filtrera de valda mallrad för lagerpåfyllnad.
    - Använd en direktivkod på raden för lagerpåfyllnad och matcha den med platsdirektiv för placering.

- Om du använder dynamiska platser kommer lagerpåfyllnadsarbetet att skapas antingen för den första tillgängliga platsen eller för en plats som redan innehåller lager om åtgärden platsdirektiv har ställts in för att använda strategin **konsolidering**.
- Om du använder fast lagerplats i stället för zoner bör du använda [standard för min/max lagerpåfyllnad](tasks/set-up-min-max-replenishment-process.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]