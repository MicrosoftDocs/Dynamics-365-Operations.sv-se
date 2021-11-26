---
title: Använd säkerhetslagerjournalen för att uppdatera minimidisponering för artiklar
description: I detta ämne beskrivs hur du använder säkerhetslagerjournalen för att uppdatera säkerhetslagerkvantitet för artiklar genom att beräkna förslag för minsta disponering baserat på historiska transaktioner.
author: ChristianRytt
ms.date: 10/28/2021
ms.topic: article
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, ReqItemTableSetup, ReqItemTable, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-10-28
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 59e4959898cd961582e1ac1d2285c0c0867ee7af
ms.sourcegitcommit: bc9e75c38e192664cde226ed3a94df5a0b304369
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790995"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage-for-items"></a>Använd säkerhetslagerjournalen för att uppdatera minimidisponering för artiklar

[!include [banner](../../includes/banner.md)]

Säkerhetslager anger en ytterligare kvantitet för en artikel som finns i lager i syfte att minska risken för att artikeln tar slut på lagret. Säkerhetslager används som ett buffertlager om försäljningsorder kommer in men leverantören inte kan möta kundens begärda transportdatum.

Detta ämne beskriver hur använder säkerhetslagerjournaler för att beräkna minsta disponeringsförslag baserat på historiska transaktioner och sedan uppdaterar artikeldisponeringen med förslagen.

## <a name="overview-of-minimum-coverage-usage"></a>Översikt över minsta disponeringsanvändning

Säkerhetslager ställs in på sidan **Artikeldisponering** för respektive artikel. Olika typer av lagerpåfyllnad representeras av olika disponeringskoder. (Mer information finns i [Uppfyllelse av säkerhetslager för artiklar](safety-stock-replenishment.md) .) Alla disponeringskoder använder emellertid det värde som anges i fältet **Minimum** på sidan **Artikeldisponering** för respektive artikel. Det finns två huvudstrategier för att använda fältet **Minimum**:

- **Minimikvantitet för min-/maxsyften** – I det här sättet används minimikvantiteten tillsammans med min-/maxlogik. Detta gäller när fältet **Disponeringskod** är inställt på *Min/Max* för den relevanta artikeln eller disponeringsgruppen. Kvantiteten **Minimum** motsvarar den genomsnittliga dagliga användningen multiplicerad med artikelns ledtid.
- **Minimikvantitet för lagerplansändamål** – I denna metod används den minsta kvantiteten för att representera en lagerplan i kombination med efterfrågeprognoser. Detta gäller när fältet **Disponeringskod** är inställt på *Period* eller *Krav* för relevant artikel eller disponeringsgrupp. Kvantiteten **Minimum** representerar en lagerplan som återspeglar önskad kundservicenivå i syfte att minska tomma lager och delförsändelser samt sänka leveransledtider. Minimikvantiteten återspeglar en procentandel av prognostiserad noggrannhet för en viss artikel. Den representerar inte önskad lagerposition.

Värdet **Minimum** kan anges på tre sätt:

- Manuellt på sidan **artikeldisponering**
- Av ramverket för datahantering (dataentiteter för *artikeldisponering*)
- Genom säkerhetslagerberäkning som utförs av säkerhetslagerjournaler

## <a name="calculate-minimum-coverage-based-on-historical-usage"></a>Beräkna minimidisponering baserat på historisk användning

Säkerhetslagerjournaler används för att beräkna en föreslagen minimikvantitet baserad på en artikels historiska användning, antingen för min-/maxsyften eller för lagerplansändamål. Historisk användning representerar alla utleveranstransaktioner under en angiven period. Dessa utförsäljningstransaktioner inkluderar försäljningsordertransaktioner och lagerjusteringar. Beräkningarna identifierar också vilken inverkan den föreslagna minsta kvantiteten har på lagervärdet och ändringen i lagervärde jämfört med de aktuella minsta kvantiteterna.

Varje journalrad för säkerhetslager representerar en artikel och dess disponeringsdimensioner. Dessa journalrader skapas och visas på sidan **Journalrader för säkerhetslager** (**Huvudplanering \> Huvudplanering \> Körning \> Beräkning av säkerhetslager**). Affärsprocessen för att använda säkerhetslagerjournalerna för beräkning av de föreslagna minsta kvantiteterna beskrivs senare i detta ämne.

Planeraren använder en säkerhetslagerjournal för att beräkna föreslagna minimikvantiteter för valda artiklar, baserat på historisk användning under valda perioder. De föreslagna minimivärdena kan vid behov ändras manuellt, och du kan granska vilken inverkan de föreslagna minimivärdena kan få på lagervärdet. När journalen bokförs uppdateras de kopplade minimikvantiteterna i artikeldisponeringen automatiskt.

### <a name="create-a-new-safety-stock-journal-name"></a>Skapa ett nytt namn på säkerhetslagerjournal.

Du måste skapa minst ett journalnamn för säkerhetslager innan du kan generera den här typen av journal. Vanligtvis kan du använda flera journalnamn för att separera beräkningarna av säkerhetslager.

1. Gå till **Huvudplanering \> Inställningar \> Namn på säkerhetslagerjournaler**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Ställ in följande fält på den nya raden:

    - **Namn** – Ange ett kort namn på journalen.
    - **Beskrivning** – Ange en beskrivning av journalen.
    - **Privat för användargrupp** – Välj en användargrupp för att begränsa målgruppen för det aktuella journalnamnet.
    - **Ta bort rader efter bokföring** – Markera den här kryssrutan om du som standard vill rensa journalrader när du bokför dem. Avmarkera den om du vill behålla alla bokförda rader.

    Fältet **Journaltyp** är skrivskyddat och har förinställts som *Säkerhetslager*.

1. Stäng sidan.

### <a name="create-a-safety-stock-journal-and-lines"></a>Skapa en ny säkerhetslagerjournal och nya rader

Med det här steget skapas en journal och rader läggs automatiskt till i den. Varje rad identifierar en artikel, dess disponeringsdimensioner och flera beräknade kvantiteter från användningshistoriken. De beräknade kvantiteterna inkluderar genomsnittligt antal ärenden per ledtid för atikel, genomsnittligt antal ärenden per månad samt månadsvis standardavvikelse.

#### <a name="automatically-generate-journal-lines"></a>Generera journalrader automatiskt

Journalrader kan bara genereras automatiskt om det inte finns några rader för den journal som för närvarande visas.

Följ dessa steg om du vill generera journalrader automatiskt.

1. Gå till **Huvudplanering \> Huvudplanering \> Körning \> Beräkning av säkerhetslager**.
1. Klicka på **Ny** i åtgärdsfönstret. Enn y säkerhetslagerjournal skapas.
1. På snabbfliken **Information om journalsidhuvud** anger du följande fält:

    - **Namn** – Välj namnet på den säkerhetslagerjournal som raden ska läggas till i.
    - **Beskrivning** – Standardvärdet är beskrivningen av det journalnamn som du väljer. Du kan emellertid redigera värdet efter behov.
    - **Ta bort rader efter bokföring** – Markera den här kryssrutan om du vill rensa journalrader när du bokför dem. Avmarkera den om du vill behålla alla bokförda rader. Inställningen ärvs från det valda journalnamnet.

    Fältet **Journal** är skrivskyddat och visar ID-numret för journalen som du skapar och lägger till rader i.

1. På snabbfliken **Journalrader** väljer du **Skapa rader** i verktygsfältet.
1. I dialogrutan **Skapa journalrader för föreslagna miniminivåer förlager** anger du följande fält:

    - **Från datum** – Välj startdatumet för den period som ärenden ska inkluderas i beräkningen för.
    - **Till datum** – Välj slutdatumet för den period som ärenden ska inkluderas i denna beräkning för. Det måste gå minst två månader mellan start- och slutdatumen.
    - **Beräkna standardavvikelse** – Ange det här alternativet som *Ja* om du vill beräkna standardavvikelsen. Du måste ange detta alternativ som *Ja* om du vill använda alternativet **Använd servicenivå** när du beräknar förslaget (beskrivs längre fram i detta ämne).

1. På snabbfliken **Poster som ska ingå** kan du konfigurera filter och begränsningar för att definiera vilka objekt som inkluderas. (Du kan till exempel filtrera efter värde för **disponeringsgrupp**.) Välj **Filter** omdu vill ööpna en standarddialogruta för frågeredigeraren där du kan definiera urvalskriterier, sorteringskriterier och sammankopplingar. Fälten fungerar precis som de gör för andra typer av frågor i Microsoft Dynamics 365 Supply Chain Management.
1. På snabbfliken **Kör i bakgrunden** väljer du om jobbet ska köras i batchläge och/eller konfigurerar ett återkommande schema. Fälten fungerar precis som de gör för andra typer av [bakgrundsjobb](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) i Supply Chain Management.
1. Välj **OK**. Rader skapas för dimensionerna som har lagertransaktioner.

#### <a name="manually-add-or-remove-journal-lines"></a>Lägga till eller ta bort journalrader manuellt

Du kan när som helst lägga till och/eller ta bort journalrader manuellt (antingen efter eller istället för att generera rader automatiskt). Använd följande knappar i verktygsfältet på snabbfliken för **Journalrader**:

- **Ny** – Lägg till en ny rad. Ange sedan ett värde i varje kolumn för att definiera produkten som du vill beräkna och tillämpa nya minimivärden för. Eftersom föreslagna minimiberäkningar inte är tillgängliga för manuellt tillagda rader visas inga nya värden för **beräknad minimikvantitet** för dessa. Därför måste du ange värdena för **Ny minimikvantitet** manuellt. Du kan emellertid fortfarande visa den potentiella effekten av värdet för **ny minimikvantitet** på lagervärdet och den potentiella lagerändringen jämfört med det för tillfället angivna minimivärdet.
- **Ta bort** – Ta bort vald rad.
- **Radera journalrader** – Radera alla rader i journalen.

### <a name="calculate-a-proposal"></a>Beräkna ett förslag

I det här steget beräknas ett föreslaget minimivärde för varje journalrad och radens potentiella inverkan på lagervärdet. (Det föreslagna minimibeloppet visas som värde för **Beräknad minimikvantitet**.) Du kan utföra beräkningen flera gånger vid behov. Beräkningen uppdaterar värdet för **Beräknad minimikvantitet** som visas för alla journalrader.

Beräkningarna som visas kommer inte att påverka de faktiska värdena för minimikvantitet för varje enskild produkt förrän du väljer **Bokför** i åtgärdsfönstret. Vid den tidpunkten kommer värdena för **Ny minimikvantitet** att appliceras på respektive produkt.

1. Gå till **Huvudplanering \> Huvudplanering \> Körning \> Beräkning av säkerhetslager**.
1. Öppna journalen som du vill beräkna ett förslag för. Du kan även skapa en ny journal enligt beskrivet tidigare i det här ämnet.
1. På snabbfliken **Journalrader** väljer du **Beräkna förslag** i verktygsfältet. (Du behöver inte markera några rader.)
1. I dialogrutan **Skapa försölag för lägsta lagernivå** anger du följande fält:

    - **Använd genomsnittligt problem under ledtiden**  – Välj det här alternativet om du vill generera värden för **Beräknad minimikvantitet** baserat på genomsnittsärende under den angivna perioden. I fältet **Multiplikationsfaktor** anger du sedan ett värde om du vill justera resultatet efter behov. Ange till exempel *1.0* om du vill använda exakt beräknat medelvärde, eller *1.1* för att lägga till en extra buffert på 10 procent.
    - **Använd servicenivå** – Välj det här alternativet om du vill beräkna ett föreslaget minimum baserat på önskad servicenivå. I fältet **Servicenivå** väljer du sedan den servicenivå du vill ha.
    - **Ledtidsmarginal** – Ange ett värde som den normala ledtiden ska utökas med (om du t.ex. vill tillåta administration).
    - **Använd den beräknade minimikvantiteten som ny minimikvantitet** – Ange det här alternativet som *Ja* om du vill kopiera värden automatiskt från kolumnen **Beräknad minimikvantitet** till kolumnen **Ny minimikvantitet** för samtliga rader efter det att beräkningen är slutförd. Om du anger detta alternativ som *Nej* kommer värdet för **Nuvarande minimikvantitet** att kopieras till kolumnen **Ny minimikvantitet** för samtliga rader. Du måste sedan redigera värdena för **Ny minimikvantitet** efter behov.

1. På snabbfliken **Kör i bakgrunden** väljer du om jobbet ska köras i batchläge och/eller konfigurerar ett återkommande schema. Fälten fungerar precis som de gör för andra typer av [bakgrundsjobb](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) i Supply Chain Management.
1. Välj **OK**. Resultatet av beräkningen visas i kolumnen **Beräknad minimikvantitet** på snabbfliken **Journalrader**. I nuläget är värdena bara föreslagna värden som ännu inte har tillämpats på dina produkter.

### <a name="update-minimum-quantity"></a>Uppdatera minsta kvantitet

Du kan markera en valfri rad i en säkerhetslagerjournal och manuellt åsidosätta värdet för fältet **Ny minimikvantitet**.

1. Gå till **Huvudplanering \> Huvudplanering \> Körning \> Beräkning av säkerhetslager**.
1. Öppna journalen du vill redigera. Du kan även skapa en ny journal enligt beskrivet tidigare.
1. På snabbfliken **Journalrader** letar du upp den rad som ska justeras och redigerar sedan värdet i kolumnen **Ny minimikvantitet**. Du kan till exempel ställa in värdet **Ny minimikvantitet** så att det matchar värdet för **Beräknad minimikvantitet**. Om värdet för **Beräknad minimikvantitet** är *0* (noll) kan du ange önskat framtida värde.

### <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>Bokför den nya minsta kvantiteten och verifiera resultatet

Följ dessa steg om du vill bokföra den nya minimikvantiteten och verifiera resultatet.

1. Gå till **Huvudplanering \> Huvudplanering \> Körning \> Beräkning av säkerhetslager**.
1. Öppna journalen som du vill bokföra nya minimikvantiteter för. Du kan även skapa en ny journal enligt beskrivet tidigare.
1. Klicka på **Bokföra** i åtgärdsfönstret.
1. I dialogrutan **Bokför journal** anger du fältet **Överför alla bokföringsfel till en ny journal** efter behov. Du kan sedan välja **OK** för att bokföra journalen.
1. Om du har ändrat värdet **Ny minimikvantitet** för en rad på snabbfliken **Journalrader** kan du bekräfta ändringen genom att följa dessa steg:

    1. Markera länken i kolumnen **Artikelnummer** för raden som du redigerade.
    1. I dialogrutan **Produktinformation** väljer du länken i fältet **Artikelnummer** för att öppna tillhörande frisläppt produktpost.
    1. I åtgärdsfönstret, på fliken **Plan** i gruppen **Disponering** väljer du **Artikeldisponering**.
    1. Notera att värdet för **Minimum** för webbplats och lager som du justerade genom att använda bokförd säkerhetslagerjournal nu har uppdaterats för att matcha din ändring.

## <a name="additional-resources"></a>Ytterligare resurser

- [Säkerhet för artiklar i lageruppfyllelse](safety-stock-replenishment.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
