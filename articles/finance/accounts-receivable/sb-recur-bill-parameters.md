---
title: Faktureringsparametrar för återkommande kontrakt
description: I den här artikeln beskrivs hur du ställer in standardvärdena för faktureringsscheman som skapas vid återkommande kontraktsfakturering. Här förklaras också hur du skapar faktureringsschemagrupper.
author: JodiChristiansen
ms.date: 11/04/2021
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
ms.openlocfilehash: cb60253f3cbb8c991ef2e106abdb1c685bf22171
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903346"
---
# <a name="recurring-contract-billing-parameters"></a>Faktureringsparametrar för återkommande kontrakt

Använd sidan **Faktureringsparametrar för återkommande kontrakt** för att ställa in standardvärdena för faktureringsscheman som skapas i Återkommande kontraktsfakturering. Alla faktureringsscheman som du skapar använder inledningsvis dessa standardvärden. Du kan dock ändra värdena för varje faktureringsschema när det behövs.

## <a name="general-tab"></a>Fliken Allmänt

1. På sidan **Faktureringsparametrar för återkommande kontrakt** på fliken **Allmänt** på fältet **Fakturaschemagrupp** väljer du en faktureringsschemagrupp. För information om hur du ställer in faktureringsschemagrupper, se avsnittet [grupper för prenumerationsfakturering](#set-up-billing-schedule-groups) senare i detta ämne.
2. I fältet **Uppsägningstyp**, välj hur den slutliga fakturan beräknas när ett faktureringsschema avslutas:

    - **Justera tidsplan** – Klipp av faktureringsschemat på uppsägningsdatumet, ändra schemats status till **Senaste fakturering** och justera det tillhörande uppskovsschemat genom att återföra det belopp som inte längre måste redovisas. Om faktureringsstartdatumet in ligger efter uppsägningsdatumet tas de återstående faktureringsperioderna bort.
    - **Fakturera resterande** – Lägg till eventuella återstående belopp i faktureringsschemat till uppsägningsperioden, ändra schemats status till **Sista fakturering** och uppdatera periodiseringstidsplan. Om faktureringens startdatum in ligger efter uppsägningsdatumet läggs det totala beloppet för alla återstående faktureringsperioder till i faktureringsperioden, och de återstående faktureringsperioderna tas bort.
    - **Ingen justering** – Avsluta faktureringsschema på uppsägningsdatumet. Inga justeringar görs i faktureringsplanen.

3. I fältet **Unik schematyp**, välj **Ingen** för att ange att kunder är begränsade till ett enda faktureringsschema. Välj **Per kund** eller **Per slutanvändare** om du vill ange att kunderna är begränsade till ett unikt schema.
4. Ange alternativet **Anpassa till månad** till **Ja** för att anpassa faktureringsschemats detaljrader med slutet av en månad när ett faktureringsschema skapas eller uppdateras. Ange **Inget** om du vill använda stegvisa datum.
5. Ställ in alternativet **Fördela delperioder** till **Ja** för att fördela faktureringsbelopp baserat på antalet dagar i perioden. Ange att **inget** ska ha samma belopp i varje faktureringsperiod, oavsett antal dagar.
6. Om du ställer in alternativet **Fördela delperioder** till **Ja**, ange fältet **Proportionell fördelning** till **Dagligen** för att fördela beloppen utifrån antalet dagar i perioden. Ange den till **Månatlig** för att ha lika mycket varje månad.
7. Ange om nya faktureringsscheman ska vänta som standard.

    > [!NOTE]
    > Om du vill ta bort gränsen för ett faktureringsschema måste användaren vara en del av en användargrupp. Välj **Ta bort spärr för åsidosättning av användargrupp** för att skapa en användargrupp där alternativet **Tillåt borttagning av spärr** är aktiverad.

8. I fältet **Typ av fakturatransaktion**, välj standardfaktura transaktionstyp för nya faktureringsscheman.
9. Ställ in alternativet **Anpassa periodisering till fakturering** till **Ja** för att anpassa motsvarande uppskjutningsschema så att det använder samma datum som faktureringsschemat. Ange **Inget** om du vill ha olika datum.
10. Om du använder intäktsdelningsfunktionen, ställ in alternativet **Skapa intäktsdelning automatiskt** till **Ja** när objekt läggs till i ett faktureringsschema. Kryssrutan **Intäktsdelning** markeras automatiskt på faktureringsschemaraden om artikeln anges som en intäktsdelningsartikel. Ange alternativet **Nej** om du vill markera kryssrutan **Intäktsdelning**.
11. Ställ in fälten för att skapa försäljningsorder:

    - Fakturor kan konsolideras per period, kund eller artikel. Alla kombinationer av värden **Ja** och **Nej** kan ställas in. Fakturor kan också delas upp efter artikelgrupp.
    - Följande bokföringsalternativ är tillgängliga för fakturor:

        - **Skapa försäljningsorder** – Skapa endast försäljningsordern.
        - **Visa bokföringsfaktura** – Fakturera försäljningsordern och öppna en sida där du manuellt kan bokföra fakturan.
        - **Skapa fritextfaktura** – Välj det här alternativet om du använder fritextfakturor.
        - **Bokför faktura automatiskt** – Fakturera försäljningsordern och bokför den automatiskt.

    - Ställ in alternativet **Lägg till faktureringsdatum i artikelbeskrivning** till **Ja** för att lägga till en beskrivning som inkluderar faktureringsstart- och slutdatum.
    - Ställ in alternativet **Exkludera nollförbrukning** till **Ja** för att utesluta faktureringsschemarader som inte har någon förbrukning. Ställ in det till **Nej** om du vill inkludera raderna i försäljningsordern.
    - Ställ in alternativet **Skriv inte ut underordnade artiklar** till **Ja** om du inte vill skriva ut de underordnade artiklarna för en intäkt som har delats på försäljningsordern. Endast den överordnade artikeln kommer att synas på fakturan. Om nettobeloppet för de (dolda) underordnade artiklarna är en summa som inte är noll, visar nettobeloppet för den överordnade raden en sammanfattning av de underordnade raderna. Ställ in alternativet **Nej** om du vill skriva ut alla underordnade artiklar under den överordnade artikeln på försäljningsfakturan.

12. Ställ in fält för stöd och support:

    - Ställ in alternativet **Aktivera support och förnyelse automatiskt** till **Ja** för att automatiskt använda support- och förnyelsefunktionen på en försäljningsorder.
    - I fältet **Support- och förnyelsenivå** välj standardnivå för support och förnyelse.
    - I fältet **Support- och förnyelsekvantitet** ange kvantitet för support och förnyelse.
    - I fältet **Standardstartdatum för support och förnyelse** ange datumet som ska användas som standardstartdatum för support och förnyelser:

        - **Transaktionsdatum** – Använd transaktionsdatum som startdatum.
        - **Början på aktuell månad** – Använd den 1:a i aktuell månad som startdatum.
        - **Början på nästa månad** – Använd den 1:a i nästa månad som startdatum. Om transaktionsdatumet är det första används det första i innevarande månad.
        - **15-regeln** – Använd den första i innevarande månad som startdatum om transaktionsdatumet är mellan den första och den femtonde i månaden. Om transaktionsdatumet är den 16:e eller senare använder du den 1:a i nästkommande månad som startdatum.

    - Ställ in alternativet **Inkludera rabatt i beräkningen** till **Ja** om du vill inkludera rabattbeloppet i support- eller rabattbeloppet. Ställ in det till **Nej** om du vill exkludera rabattbeloppet.
    - I fälten **Supportfrekvens** och **Förnyelsefrekvens** välj frekvensen som ska användas när support- och förnyelseobjekt läggs till i ett faktureringsschema: **Dagligen**, **Månatlig**, **Kvartalsvis**, **Halvårsvis** eller **Årligen**.
    - Ställ in alternativet **Anpassa per artikelgrupp** till **Ja** för att anpassa start- och slutdatumen för nya artiklar till befintliga artiklar, baserat på artikelgruppen.
    - Ange alternativet **Anpassa till nästa ej fakturerade period** till **Ja** för att fastställa anpassningsdatumet för en förnyelseartikel baserat på datumet för nästa ofakturerade period efter att förnyelsen startar.
    - Ställ in alternativet **Kopiera serienummer** till **Ja** om du vill kopiera artikelserienumret från den ursprungliga försäljningsorderraden till motsvarande faktureringsplansrad.

13. Om du använder eskalering i faktureringsschemat ska du välja den metod som ska användas för beräkningen av konsumtionsprisindexet.
14. Ställ in alternativet **Spåra prisändring** till **Ja** om du vill ha en registrering av prisändringar på rader i faktureringsschemat. Om en rad i ett faktureringsschema ändras manuellt från standard till plan, och ett nytt pris registreras, spåras redovisningsinformationen på raden i faktureringsschemat. Ställ in alternativet till **Nej** om du inte vill spåra dessa ändringar.
15. Ange om poster ska filtreras efter startdatum eller slutdatum som standard på sidan **Generera faktura**.
16. Om du använder funktionen **Ej fakturerad intäkt** anger du här vilka alternativ som används:

    - Ställ in alternativet **Bokför allmän journal automatiskt** till **Ja** om du vill att den allmänna journalen ska skapas och bokföras samtidigt. Ange **Nej** om du vill skapa den allmänna journalen och sedan bokföra den manuellt.
    - Välj i fältet **Standardjournalnamn** det standardjournalnamn som ska användas när den allmänna journalen skapas.
    - I fältet **Kortfristig ej debiterad metod**, välj kortfristig ej debiterad metod om du använder en sådan. Om du väljer **Ingen** används inte funktionen på kortare sikt med ej fakturerade intäkter. Välj **Rullande perioder** om du alltid vill använda 12 månader eller **Fast år** för att använda resterande räkenskapsår.

17. Ange de alternativ som används när en faktureringsplan och dess rader avslutas:

    - **Utfärda kredit** – Skapa en kreditnota när ett faktureringsschema eller en faktureringsschemarad avslutas.
    - **Kreditjustering** – Skapa en kreditjustering för ett faktureringsschema när en rad har avslutats. Kreditjusteringen visas i en framtida faktureringsperiod för faktureringsschemat. Kreditjusteringen kommer att uppdatera fakturabeloppet automatiskt för nästa faktureringsperiod tills kredit har slutförts för faktureringsschemat.
    - **Ingen kredit** – Skapa inte en kreditjustering eller en kreditnota när ett faktureringsschema eller en faktureringsschemarad avslutas. Det här alternativet är endast tillgängligt när du använder alternativet **Ingen justering** för att avsluta ett faktureringsschema.

## <a name="sequence-number-tab"></a>Fliken Sekvensnummer

Använd fliken **Sekvensnummer** på sidan **Faktureringsparametrar för återkommande kontrakt** för kontrakt för att ställa in standardvärdet för faktureringsschemanummer. Standardvärdena ställs in på sidan **Nummerserier** (**Organisationadministration \> Nummerserier \> Nummerserier**).

## <a name="set-up-billing-schedule-groups"></a>Ställ in schemagrupper för prenumerationsfakturering

Använd sidan **Fakturaschemagrupp** för att skapa fakturaschemagrupp för återkommande kontraktsfakturering. När ett nytt faktureringsschema skapas och en faktureringsschemagrupp tillämpas på det, kommer värdena som definieras på sidan **Fakturaschemagrupp** anges som standardvärden för faktureringsschemat. Du kan ändra något av standardvärdena för det specifika faktureringsschema som du skapar. Du kan ställa in flera faktureringsschemagrupper och sedan tilldela en av dem som standard faktureringsschemagrupp på sidan **Faktureringsparametrar för återkommande kontrakt**.

Skapa en faktureringsschemagrupp för fakturering med återkommande kontraktsfakturering genom att följa dessa steg.

1. På sidan **Fakturaschemagrupp** väljer du **Ny** för att skapa en fakturaschemagrupp.
2. I fältet **Fakturaschemagrupp**, ange en unik identifierare.
3. Ange en beskrivning i fältet **beskrivning**.
4. I fältet **Faktureringsfrekvens**, ange hur ofta faktureringsschemat faktureras en kund: **En gång**, **Dagligen**, **Månatlig**, **Kvartalsvis**, **Halvårsvis** eller **Årligen**.
5. I fältet **Faktureringsintervall**, ange ett faktureringsintervall. Ställ till exempel in fältet **Faktureringsfrekvens** till **Månadsvis** och fältet **Faktureringsintervall** till **2** för att fakturera varannan månad.
6. I fältet **Prissättningsmetod** välj standardprissättningsmetoden för varor i faktureringsschemat:

    - **Standard** – Beräkna enhetspriset baserat på den totala kvantiteten som har registrerats, och använd standardpriset från sidan **Frisläppta produkter** i Produktinformationshantering.
    - **Fast** – Använd ett fast pris som angetts på faktureringsschemaraden.
    - **Nivå** – Beräkna priset per enhet med en fast kvantitet inom olika hakparenteser. Varje nivå måste fyllas i innan det flyttas till nästa prissättningsparentes.
    - **Fast nivå** – Beräkna priset per enhet med en fast kvantitet och utökade prisbelopp inom olika hakparenteser. Priset som debiteras i en faktureringsperiod använder det utökade priset som motsvarar den nivå där faktureringskvantiteten finns.

7. I fältet **artikeltyp**, välj typen av objekt för faktureringsgruppen:

    - **Standard** – Välj detta värde om kvantiteten är statisk.
    - **Användning** – Välj detta värde för artiklar av mättyp eller förbrukningstyp. Om du väljer detta värde, ställ in fältet **Alternativet för användningsavläsning** till **Avläsning** för att ange värdet (avläsningen) för en faktureringsperiod på en mätare eller enhet. Det förbrukade värdet beräknas utifrån den föregående faktureringsperioden och den aktuella inläsningen som du anger.
    - **Milstolpe** – Välj det här värdet om du vill använda faktureringsfunktionen för milstolpar. Om du väljer det här värdet väljer du milstolpemallen i fältet **Milstolpemall** om du använder en sådan.
    - **Förbrukning** – Välj det här värdet om du vill ange det värde som förbrukas under en faktureringsperiod.

8. Ställ in alternativet **Fakturera separat** till **Ja** om du vill skapa en kombination av konsoliderade fakturor och separata fakturor för samma kund. En kund har till exempel fem faktureringsscheman. Tre av dem konsolideras på en enda faktura, men för var och en av de två krävs en separat faktura. Ange alternativet **Nej** om du endast vill skapa en konsoliderad faktura för kunden.
9. Ange alternativet **Förnya automatiskt** till **Ja** för att automatiskt förnya det återkommande faktureringsschemat för nästa faktureringsperiod när fakturan skapas. Ange den till **Nej** för att manuellt förnya faktureringsschemat. I fältet **Rader som ska läggas till per förnyelse**, ange hur många rader som ska läggas till för varje förnyelse.
10. Ställ in alternativet **Eskalering** till **Ja** för att tillämpa *eskaleringar* (prisökningar) på faktureringsschemana som hör till den här faktureringsschemagruppen.
