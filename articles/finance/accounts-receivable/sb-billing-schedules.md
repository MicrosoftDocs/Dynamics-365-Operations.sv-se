---
title: Skapa faktureringsscheman
description: Det här avsnittet förklarar hur du skapar, tar bort och redigerar faktureringstidsplaner.
author: JodiChristiansen
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: ed31dd96b0115610cfb74aed69f1acc1055bfe56
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690457"
---
# <a name="create-billing-schedules"></a>Skapa faktureringsscheman

[!include [banner](../includes/banner.md)]

På sidan **faktureringstidsplan** kan du skapa, ta bort eller redigera faktureringstidsplan. Du kan också granska listan med en faktureringstidsplan. När du skapar en faktureringstidsplan fastställs standardvärdena för det av den faktureringsgrupp som är kopplad till den. Mer information ställs in på sidan **Faktureringsparametrar för återkommande kontrakt**.

## <a name="create-a-billing-schedule"></a>Skapa en faktureringstidsplan

Följ dessa steg för att skapa en faktureringstidsplan.

1. Välj **Nytt** på sidan **faktureringstidsplan**.
2. I dialogrutan **Skapa faktureringstidsplan** i fältet **Grupp för faktureringstidsplan**, välj en grupp för faktureringstidsplan.
3. I fältet **Kundkonto** markera ett kundkonto.
4. I fältet **Startdatum** välj startdatum och sedan i fältet **antalet perioder** ange antal perioder. Fältet **Slutdatum** uppdateras baserat på antalet perioder som du anger. Om du uppdaterar fältet **Slutdatum för fakturering** uppdateras fältet **Antal perioder** till **0** (noll).
5. Välj **OK**.
6. På sidan **Faktureringstidsplan** på fliken **Allmänt** i fältet **Beskrivning** anger du en beskrivning av faktureringstidsplanen.
7. I fältet **milstolpemall** välj en milstolpemall för **milstolpefakturering**.

Fält som **Fakturakonto** och **Valutakod** uppdateras med information från kunden.

Fälten **Faktureringsfrekvens** och **Faktureringsintervall** ställs automatiskt in baserat på den valda faktureringsschemagruppen.

8. Om du vill skapa separata fakturor ställer du in alternativet **Fakturera separat** på **Ja**.
9. Om du vill förnya ett faktureringsschema automatiskt efter den slutliga faktureringsperioden ställer du in alternativet **Förnya automatiskt** på **Ja** och ställer sedan in **Rader att lägga till per förnyelse**.

Fältet **Parametrar** ställs in automatiskt baserat på värdena på sidan **Återkommande faktureringsparametrar för kontrakt**.

10. För att fördela beloppet proportionellt för ett faktureringsschema, ställ in alternativet **fördela delperioder proportionellt** till **Ja**.
11. För att anpassa faktureringsschemats detaljrader med slutet av en månad, ställ in alternativet **Justera till månad** till **Ja**.
12. I fälten **Startdatum för kontrakt** och **Slutdatum för kontrakt** anger du start- och slutdatum för kontrakten. Dessa datum är endast i informationssyfte.

I fältet **betalning** visas kundens betalningsinformation från kunden. När en radartikel sätts in eller upp är uppsagd går det inte att ändra betalningsinformationen.

> [!NOTE]
> När du konsoliderar fakturor per artikel måste värdet i fälten **Betalningsvillkor**, **Metod** och **Faktureringsschema** matcha. Annars kan fakturorna inte konsolideras.

13. På fliken **Adress** kan du granska och uppdatera fälten **Leveransadress** och **Faktureringsadress**.
14. På fliken **Kontaktinformation** kan du koppla ett slutanvändarkonto till faktureringsschemat.
15. I fälten **Kontaktinfo** kan du ange en kontakt, en e-postadress och en webbadress.
16. Om du vill spåra information om partnerkommissioner ställer du in fält för **partnerkonto** och **partnerprovisionen**. Dessa fält är endast i informationssyfte.
17. På fliken **Summa** kan du visa de olika summorna som har beräknats för faktureringsschemat.
18. På fliken **Spärra** kan du visa granskningsinformation om när faktureringsschemat spärrades när spärren togs bort.
19. På fliken **Uppsägning** kan du visa en historik över uppsägningar som har tillämpats för eller tagits bort från faktureringsschemat.
20. Välj **Spara**.
21. På snabbfliken **faktureringsschemarader** välj **Lägg till rad**.
22. I fältet **Artikelnumret** väljer du artikelnumret. Om artikeln som läggs till är en överordnad artikel i en intäktsdelning uppdateras raderna automatiskt med de underordnade artiklarna. Du kan bara redigera den överordnade artikeln i en intäktsdelning. Alla underordnade artiklar uppdateras sedan.
23. I fältet **Artikeltyp** väljer du artikeltypen.
24. Uppdatera start- och slutdatum.
25. Innan fakturorna skapas kan du ändra faktureringsfrekvensen genom att uppdatera fältet **Faktureringsfrekvens**. När den första fakturan för faktureringsplanen har skapats går det inte att ändra faktureringsfrekvensen.
26. Välj måttenhet för artikeln i fältet **Enhet**.
27. I fältet **Prissättningsmetod** väljer du prismetod för artikeln.

Fältet **Enhetspris** ställs automatiskt in från lagret. Du kan dock uppdatera den om du ändrar prissättningsmetoden till **Fast**.

## <a name="remove-a-line-item"></a>Ta bort en radartikel

Om du vill ta bort en artikel från en faktureringsplan följer du dessa steg.

1. På sidan **faktureringsschema** i fältet **Tidsplaneringsnummer** väljer du numret på faktureringsschemat som ska redigeras.
2. På snabbfliken **Faktureringsschemarader**, välj raden som ska raderas och välj sedan **Ta bort**.
3. Välj **Spara**.

I resten av det här avsnittet beskrivs de åtgärder och den information som är tillgängliga för rader på snabbfliken **Faktureringsschemarader**.

## <a name="billing-schedule-line-actions"></a>Radåtgärder för faktureringsschema

Med knapparna på snabbfliken **Faktureringsschemarader** kan du utföra åtgärder på enskilda rader.

| Knapp | Beskrivning |
|--------|-------------|
| Lägg till rad | Lägg till en rad i faktureringsschemat. |
| Lägg till från artikellista | Lägg till flera artiklar i en faktureringsplan genom att markera dem i en lista. |
| Ta bort | <p>Ta bort den valda raden från faktureringsschemat.</p><p>För artiklar som ingår i en intäktsdelning kan du bara ta bort den överordnade artikeln. Alla kopplade underordnade artiklar tas då automatiskt bort.</p> |
| Visa faktureringsinformation | Se faktureringsinformationen. |
| Säg upp | <p>Avsluta de valda raderna. Den här knappen är endast tillgänglig när de valda raderna har statusvärdet **Aktiv**.</p><p>För artiklar som ingår i en intäktsdelning kan du bara avsluta den överordnade artikeln.</p> |
| Ta bort uppsägning | <p>Ta bort uppsägningen från de valda raderna. Den här knappen är endast tillgänglig när de valda raderna har statusvärdet **Avslutad**.</p><p>För artiklar som ingår i en intäktsdelning kan du ta bort uppsägningen endast från det överordnade objektet.</p> |
| Placera spärr | <p>Välj information om hur den valda raden ska stoppas.</p><p>För artiklar som ingår i en intäktsdelning kan du kan bara spärra den överordnade artikeln.</p> |
| Ta bort spärr | <p>Ta bort spärren från den valda raden.</p><p>För artiklar som ingår i en intäktsdelning kan du ta bort spärren endast från det överordnade objektet.</p> |
| Eskalering och rabatt | Denna knapp är inte tillgänglig för artiklar som ingår i en intäktsdelning, utom överordnade artiklar där intäktsdelningen använder allokeringsmetoden **Nollbelopp**. |
| Periodiseringar | <p>Ange uppskjutningsalternativ för den valda raden.</p><p>Denna knapp är inte tillgänglig för överordnade artiklar i intäktsdelning.</p> |
| Milstolpeallokering | <p>Granska och uppdatera allokeringsinformationen för milstolpar för den valda raden.</p><p>Den här knappen är endast tillgänglig när artikeln på faktureringsplanens rad är en milstolpeartikel.</p> |
| Support och förnyelse | <p>Granska och uppdatera information om stöd och förnyelse för milstolpar för den valda raden.</p><p>Den här knappen är endast tillgänglig när artikeln på faktureringsplanens rad är en stöds- och förnyelseartikel.</p> |
| Visa dimensioner | Visa eller dölj de dimensionskolumner som visas i rutnätet **Fakturaplansrader**. |
| Beräkna enhetspris | <p>Beräkna artikelns enhetspris så att kunden kan betala kontraktsbeloppet på avbetalningar (till exempel per dag, månad, kvartalsvis, halvårsvis eller årligen). Du kan välja kontraktspris och prisfrekvens.</p><p>Du kan visa redovisningsspår för ändringarna: det gamla kontraktets pris och frekvens, det nya kontraktets pris och frekvens, användaren som gjorde ändringen samt datum och tidpunkt för ändringen.</p> |
| Anpassningsdatum | <p>Ange justeringsdatumet för artikeln.</p><p>Om du väljer en artikelgrupp i fältet **Artikelgrupp** använder alla artiklar justeringsdatumet för det första objektet i artikelgruppen i faktureringsschemat. Om fältet **Artikelgrupp** är tomt kan du ange ett justeringsdatum som ska användas för alla artiklar.</p><p>Den här knappen är endast tillgänglig om fältet **faktureringsfrekvens** anges till **årlig**.</p> |
| Ej fakturerad intäkt | <p>Ange att artikeln ska använda funktionen ofakturerad intäkt. Du kan sedan ange konton för ofördelade intäkter och ofördelade rabatter för artikeln.</p><p>Den här knappen är bara tillgänglig för artiklar där fältet **Artikeltyp** är inställt som **Standard**. Den är inte tillgänglig för befintliga faktureringsscheman eller för faktureringsschemarader där fakturan redan har skapats.</p> |
| Lägg till underordnad intäktsdelning | <p>Välj en underordnad artikel att lägga till i försäljningsordern.</p><p>Denna knapp är endast tillgänglig för överordnade artiklar i intäktsdelning.</p> |
| Alternativ för avancerad prissättning | Redigera prissättningsalternativen för en artikel. |

## <a name="billing-schedule-line-details"></a>Raddetaljer för faktureringsschema

När du markerar en rad på snabbflikarna **Faktureringsschemarader** kan du visa specifik information för den raden. Informationen delas upp på olika flikar.

### <a name="general-tab"></a>Fliken Allmänt

Följande information finns på fliken **Allmänt**.

| Fält eller avsnitt | Beskrivning |
|------------------|-------------|
| Användning | <p>Det här avsnittet ger information om användningsobjekt. Det innehåller följande fält:</p><ul><li>**Användar-ID** – Identifieraren för mätaren eller användningsartikeln.</li><li>**Läsalternativ** – Alternativet för användningsläsning: **Läsa** eller **Förbruka**.</li><li>**Uppskattad förbrukning** – Anger den uppskattade förbrukningen för en förbrukningsartikel som har perioder där fakturan inte har skapats. På sidan **Faktureringsdetaljer** kan du granska faktureringsdetaljraderna för uppskattad förbrukning.</li></ul> |
| Externa referenser\* | Det här avsnittet innehåller fälten för **externa** och **radnummer**, där du kan ange extern referensinformation. |
| Milstolpe | <p>Det här avsnittet ger information om milstolpsobjekt. Den innehåller fältet **Beräknat slutförandedatum**, som visar artikelns slutförandedatum.</li></ul> |
| Text | En kommentar till raden. Texten översätts till kundens eller den juridiska personens standardspråk. |
| Artikelgrupp | Artikelgruppen för radartikeln. |
| Anpassningsdatum | Justeringsdatumet för faktureringsschemat. |

\* När du konsoliderar fakturor per artikel på sidan **Generera faktura**, måste fälten **extern referens** matcha. Om även ett tecken är olika, konsolideras inte artiklarna på fakturan. Inga valideringskontroller utförs i något av fältet i avsnittet **externa referens** och värdet i fältet **Radnummer** måste vara ett positivt heltal.

### <a name="address-tab"></a>Fliken Adress

Följande information finns på fliken **Adress**.

| Fält | Beskrivning |
|-------|-------------|
| Leveransadress | <p>Välj leveransadress för radartikel. Standardleveransadressen är den primära leveransadressen från snabbflikarna **Adress**.</p><p>När du ändrar adressen kan du välja följande adressalternativ:</p><ul><li>**Adresser** – Välj en adress för den aktuella kunden.</li><li>**Används** – Välj en adress som för tillfället används för den aktuella kunden.</li><li>**Annan adress** – Välj en adress för en kundpost.</li></ul><p>För artiklar där intäktsdelning används kan endast adressen för den överordnade artikeln redigeras. Adressen för de underordnade artiklarna matchar adressen för den överordnade artikeln och kan inte redigeras separat.</p> |
| Faktureringsadress | <p>Välj faktureringsadress för radartikel. Standardleveransadressen är den primära leveransadressen från snabbflikarna **Adress**. Du kan ändra adressen efter behov, baserat på syftet med de tillgängliga adresserna:</p><ul><li>Om ingen av adresserna har syftet med **Faktura** är standardadressen växel till den primära adressen för kunden, oavsett syfte.</li><li>Om en eller flera adresser har syftet **Faktura** är standardadressen för växel till den adress som senast angavs.</li><li>Om en eller flera adresser har syftet **Faktura** och en av fakturaadresserna är inställd som den primära adressen, är standardadressen för växeln den adress som har syftet **Faktura** och anges som primär adress.</li><li>För artiklar där intäktsdelning används kan endast adressen för den överordnade artikeln redigeras. Adressen för de underordnade artiklarna matchar adressen för den överordnade artikeln och kan inte redigeras separat.</li></ul> |

### <a name="product-tab"></a>Fliken produkt

Följande information finns på fliken **Produkt**.

| Fält eller avsnitt | Beskrivning |
|------------------|-------------|
| Lagringsdimensioner | <p>Det här avsnittet visar lagringsinformationen för artikeln. Den innehåller fältet **Serienummer**, som visar artikelns serienummer.</p><p>Serienumret kopieras från den första försäljningsordern under support- och förnyelseprocessen. För artiklar där intäktsdelning används kopieras serienummer för den överordnade artikeln till alla underordnade artiklar. Serienumret kopieras när alternativet **Kopiera serienummer** ställs inpå **Ja** på sidan **Faktureringsparametrar för återkommande kontrakt**.</li></ul> |
| Produktdimensioner | Produktdetaljerna för artikeln och värdena uppdateras automatiskt baserat på värdet **variantnummer** som valts för raden i faktureringsplanen. |

### <a name="account-tab"></a>Fliken Konto

Följande information finns på fliken **Konto**.

| Fält | Beskrivning |
|-------|-------------|
| Huvudkonto | Huvudkontot som skapas på försäljningsraden. Standardvärdet kommer från försäljningsordern. Fältet kan redigeras. |
| Ekonomiska dimensioner för artikel | <p>Värdena för den ekonomiska standarddimensionen, baserade på kund- och artikelposten.</p><p>För artiklar där intäktsdelning används använder de underordnade artiklarna de ekonomiska dimensionsvärdena för kund- och artikelposterna, enligt tidigare beskrivet. Om du måste uppdatera värdena för den ekonomiska dimensionen för underordnade artiklar, kan du importera dataenheten.</p> |

### <a name="renewals-tab"></a>Fliken förnyelse

Följande information finns på fliken **förnyelse**.

| Fält | Beskrivning |
|-------|-------------|
| Förnya automatiskt | <p>Ett värde som anger om faktureringsschemaraden förnyas automatiskt för nästa faktureringsperiod:</p><ul><li>**Ja** – Faktureringsschemaraden förnyas automatiskt för nästa faktureringsperiod när du skapar en faktura.</li><li>**Nej** – Raden i faktureringsschemat förnyas inte automatiskt. Du måste förnya faktureringsplanen manuellt.</li></ul> |
| Rader som ska läggas till per förnyelse | Antalet rader som ska läggas till en tidsplan för fakturering. |

Dessutom finns följande knappar tillgängliga på **förnyelse**.

| Knapp | Beskrivning |
|--------|-------------|
| Granska journalpost ofakturerad intäkt | Visa alla ändringar för artiklar som använder funktionen för ofakturerade intäkter. |
| Lägg till förnyelseperiod | Lägg till en förnyelseperiod för artikeln. Startdatumet för den nya förnyelseperioden är nästa datum efter slutdatumet för föregående period. Fälten **Slutdatum för förnyelse**, **Startdatum för periodisering**, **Slutdatum för periodisering**, **Artikelkvantitet** och **Enhetspris** kan uppdateras. |
| Ändra förnyelseperiod | <p>Ändra ett förnyelsevillkor. För det första termen kan du ändra start- och slutdatumen innan den ursprungliga journalposten skapas. Startdatumet kan inte ändras för efterföljande villkor. Det är alltid nästa datum efter föregående års slut.</p><p>Om det finns ett existerande begrepp efter det att du har ändrat det, kan datumet på termen inte ändras. I det här fallet kan bara fälten **Kvantitet** och **Enhetspris** för artikeln uppdateras.</p><p>Det finns till exempel tre termer. <ul><li>Det går inte att ändra det första termen eftersom den redan har startat.</li><li>För den andra perioden går det bara att ändra kvantitet och enhetspris.</li><li>För tredje perioden kan alla värden utom startdatumet ändras. Med mallalternativet **Tidsplaneras dessutom** kan du skapa ett periodiseringsschema som baseras på mallen för artikeln för ej fakturerad intäkt. När det här alternativet är inställt på **Ja**, väljer du periodiseringsmallen i fältet **Mall** och ändrar start- och slutdatumen efter behov. Efterföljande förnyelsetermer använder samma de mall. Förnyelsemallen kan dock ändras.</p></li></ul> |

### <a name="termination-tab"></a>Fliken avslutning

Följande information finns på fliken **avslutning**.

| Fält | Beskrivning |
|-------|-------------|
| Uppsägningsdatum | Datumet när raden i faktureringsplanen avslutas. Standardvärdet kommer från fältet **Uppsägningsdatum** i rubriken. Du kan dock ändra värdet som du vill. |
| Uppsägningstyp | Typ av uppsägning. Standardvärdet kommer från fältet **Uppsägningstyp** i rubriken. |

### <a name="hold-tab"></a>Fliken Spärra

Om intäkts- och kostnadsuppskjutningar används, visas fliken **Spärra** visar periodiseringsdatumet.

### <a name="escalation-and-discount-tab"></a>Fliken Eskalering och rabatt

Följande information finns på fliken **Eskalering och rabatt**:

| Fält | Beskrivning |
|-------|-------------|
| Eskalering | <p>Välj om eskaleringar ska tillåtas för faktureringsschemaraden. Alla eskaleringsrad från huvudet används när faktureringsschemaraden skapas.</p><ul><li>**Ja** – Eskalering kan användas för raden. När det här alternativet har valts kan du ställa in eskaleringarna för faktureringsschemaraderna på sidan **Eskalering och rabatt**.</li><li>**Nej** – Eskalering kan inte användas för raden.</li></ul><p>Standardinställningen baseras på den valda **gruppen för faktureringsschema**.</p> |

### <a name="price-changes-tab"></a>Fliken Prisförändringar

För rader som ändras från **Standard** pris till **Fast** pris innehåller rutnätet på fliken **Prisändringar** följande kolumner:

- Ändringsdatum
- Ändrat av användare
- Standardpris
- Fast pris
- Prisuppdatering
