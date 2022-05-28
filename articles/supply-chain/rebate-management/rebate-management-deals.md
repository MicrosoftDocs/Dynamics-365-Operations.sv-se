---
title: Rabatthanteringserbjudanden
description: Det här avsnittet beskriver hur du skapar rabatthanteringserbjudanden. Erbjudanden används för att kontrollera olika metoder och baser för beräkning av rabatter och royalties. De omfattar regler för inkludering och undantag.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateDeal
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 76cdbf21cfbc0db7b363d0fbf60a1ecd0046efc1
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689703"
---
# <a name="rebate-management-deals"></a>Rabatthanteringserbjudanden

[!include [banner](../includes/banner.md)]

Rabatthanteringserbjudanden används för att kontrollera olika metoder och baser för beräkning av rabatter och royalties. De omfattar regler för inkludering och undantag. Det finns tre typer av rabatthanteringserbjudanden: kundrabatter, kundroyalties och leverantörsrabatter. Alla tre typerna använder liknande inställningar. I det här avsnittet visas skillnader mellan de länder där de finns.

## <a name="create-a-deal"></a>Skapa ett erbjudande

1. Gå till **Rabatthantering \> Rabatthanteringserbjudanden \> Alla rabatthanteringserbjudanden**. På listsidan **Alla rabatthanteringserbjudanden** kan du skapa och arbeta med alla tre typer.

    Alternativt följer du ett av stegen. I alla fall innehåller listsidan som visas alla samma inställningar som listsidan **Alla rabatthanteringserbjudanden**, men det filtreras för att visa erbjudanden av endast en typ.

    - Gå till **Rabatthantering \> Rabatthanteringserbjudanden \> Kundrabatterbjudanden** om du bara vill skapa kundrabatterbjudanden.
    - Gå till **Rabatthantering \> Rabatthanteringserbjudanden \> Kundroyaltyerbjudanden** om du bara vill skapa kundroyaltyerbjudanden.
    - Gå till **Rabatthantering \> Rabatthanteringserbjudanden \> Leverantörsrabatterbjudanden** om du bara vill skapa leverantörsrabatterbjudanden.

1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Skapa nytt erbjudande**, ställ in följande fält:

    - **Rabatthanteringserbjudande** – Om du har [ställt in en nummerserie](rebate-management-parameters.md) för rabatterbjudanden sätts detta fält automatiskt till ett unikt systemgenererat ID. Annars måste du ange ett unikt ID.
    - **Beskrivning** – Ange en beskrivning av erbjudandet.
    - **Modul** – Välj den typ av partner som erbjudandet gäller för (*Kund* eller *Leverantör*). Beroende på vilken sida du startade från kan det här fältet ställas in automatiskt baserat på den valda erbjudandetypen. I det här fallet är fältet skrivskyddat. 
    - **Typ** – Välj typ av erbjudande (*Rabatt* eller *Royalty*). Beroende på vilken sida du startade från kan det här fältet ställas in automatiskt baserat på den valda erbjudandetypen. I det här fallet är fältet skrivskyddat. 
    - **Stäm av efter** – Välj hur erbjudandet ska beräknas och avstämmas:

        - *Behandla* – En enda rabatt ska behandlas för alla rabatter och avdrag i erbjudandet.
        - *Rad* – Rabatter ska bearbetas för varje rad i en deal.

    - **Bokföringsprofil** – Välj den [bokföringsprofil](rebate-management-posting.md) som ska användas för transaktioner där erbjudandet gäller. Det här fältet är endast tillgängligt om fältet **Stäm av efter** anges till *Erbjudande*. Om det är inställt på *Rad* tilldelar du profilen senare för varje rad som du lägger till i erbjudandet.
    - **Bokföringsprofil för garanti** – Välj den [bokföringsprofil](rebate-management-posting.md) som ska användas för garantitransaktioner. Bokföringsprofiler krävs för garantitransaktioner endast om garantin gäller för en royalty. Annars visas ett fel när garantierna bokförs, även om ingen bokföringsprofil har angetts, även om en bokföringsprofil inte är obligatorisk. Det här fältet är endast tillgängligt om fältet **Typ** anges till *Royalty*. 
    - **Rabattutleverans** – Välj hur rabatten eller royaltyn ska betalas:

        - *Ekonomi* – Generera en kreditfaktura med fritext eller debetfaktura för leverantörsreskontra så att pengar kan betalas eller tas emot senare. Observera att provisioner **kan** användas med rabatter där det här alternativet har valts. Det här alternativet är endast tillgängligt om fältet **Typ** anges till *Royalty*.
        - *Artikel* – Generera en försäljningsorder för artiklar enligt erbjudandeinställningarna. På den här försäljningsordern tilldelas varje artikel ett pris på 0 (noll). Observera att provisioner **inte kan** användas med rabatter där det här alternativet har valts.

    - **Rabattvaluta** – Välj den valuta som ska användas när rabatten, avdraget eller royaltyn betalas.
    - **Dokumentnoteringar** – Ange noteringar om erbjudandet, efter behov.
    - **Ackumulerad garanti** – Du kan endast ange alternativet *Ja* om fältet **Typ** är inställt på *Royalty*. Det här alternativet påverkar beräkningen av löneavdragsbetalningar. Här är ett exempel:

        - Garantin för affären är att sälja ett värde som leder till en betalning på 10 000 USD per kvartal.
        - Den organisation som säljer varorna säljer ett värde som medför att avdragsbetalningen blir 12 000 USD under kvartal 1. Resultatet blir en 12 000 USD som betalas, minus 10 000 USD garanti.
        - Om alternativet **Ackumulerad garanti** anges till *Ja* gäller de ytterligare 2 000 USD som betalades under kvartal 1 för kvartal 2. Därför garanteras kunden 8 000 USD (10 000 USD garanti minus den ytterligare betalningen på 2 000 USD).
        - I kvartal 2 registrerar du försäljning som utlöser en royalty på 5 000.
        - Systemet identifierar en betalning på 3 000 USD (8 000 USD garanti minus 5 000 betalda royalties).
        - Om alternativet **Ackumulerad garanti** är inställt på *Nej* garanteras hela 10 000 USD varje kvartal. Denna garanti motsvarar en föreslagen betalning på 5 000 USD under kvartal 2 (10 000 USD garanti minus 5 000 USD betalda royalties).

1. Välj **OK** för att skapa erbjudandet och stänga dialogrutan.

Med den här proceduren skapas rubriknivån för det nya erbjudandet. Sedan lägger du till rader i erbjudandet.

## <a name="add-lines-to-a-deal"></a>Lägga till rader i ett erbjudande

När du har skapat ett erbjudande enligt beskrivningen i det föregående avsnittet kan du öppna den från listsidan. Du kan sedan lägga till rader för att identifiera kunderna eller leverantörerna, artiklarna, tidsramarna, ett underlag och beräkningsmetoder för erbjudandet. Ett erbjudande kan ha en eller flera rader. Om ett erbjudande har flera rader är de i allmänhet av samma typ, eller så är samma parametrar associerade med dem. Tills du lägger till rader i ett erbjudande gör erbjudande inte något.

1. Öppna lämplig listsida för rabattavtal på det sätt som beskrivs i det föregående avsnittet.
1. Hitta och öppna det erbjudande som du vill arbeta med.
1. På snabbfliken **Rabatthantering** markerar du en av följande knappar om du vill lägga till en erbjudanderad i rutnätet:

    - **Lägg till rad** – Lägg till en ny tom erbjudanderad.
    - **Kopiera rad** – Om en befintlig erbjudanderad liknar den erbjudanderad som du vill lägga till kan du välja den här knappen för att kopiera lägga till en kopia av den. Den nya raden innehåller alla inställningar från relaterad rabatthanteringsinformation. Du kan sedan redigera inställningarna. Du uppdaterar normalt artikelrelationen och rabattprocenten.

1. Ställ in följande fält på den nya erbjudanderaden:

    - **Rabatthanteringsnummer** – Om du har [ställt in en nummerserie](rebate-management-parameters.md) för rabatthanteringsnummer sätts detta fält automatiskt till ett unikt systemgenererat ID. Annars måste du ange ett unikt ID.
    - **Typ** – Den typ av avtal som raden gäller för ( *Rabatt* eller *Royalty*). Värdet kopieras från rubriken och kan inte ändras.
    - **Beskrivning** – Ange en beskrivning av erbjudanderaden.
    - **Företag** – Välj det företag (juridisk person) som erbjudanderaden gäller för. Under bearbetningen kan användarna bara bearbeta erbjudanderade som har tilldelats företaget som de för närvarande använder. Listsidan **Kundrabatterbjudanden** ger en vy över flera företag, baserat på användarens säkerhetsåtkomst. Du kan bara redigera och bearbeta rabatter för det företag som du för närvarande använder.
    - **Kontokod** – Välj omfattningen av kunder eller leverantörer som avtalsraden gäller för:

        - *Register* – Den här raden gäller för en viss kund eller leverantör.
        - *Grupp* – Den här raden gäller för en grupp kunder eller leverantörer. Mer information om hur du ställer in grupper finns i [Rabatthanteringsgrupper](rebate-management-groups.md).
        - *Alla* – Den här raden gäller för alla kunder eller leverantörer.

    - **Kontorelation** – Om du har valt fältet *Tabell* i **Kontokod** välj den kund eller leverantör som affären gäller. Om du väljer *Grupp* ska du välja leverantörsgruppen. Om du väljer *Alla* är det här fältet inte tillgängligt.
    - **Artkelkod** – Välj omfattningen av artiklar som erbjudanderaden gäller för:

        - *Register* – Den här raden gäller för en viss artikel.
        - *Grupp* – Den här raden gäller för en grupp artikel. Mer information om hur du ställer in grupper finns i [Rabatthanteringsgrupper](rebate-management-groups.md).
        - *Alla* – Erbjudanderaden gäller för alla artiklar.

    - **Artikelrelation** – Om du har valt fältet *Tabell* i **Artikelkod** välj den artikel som erbjudanderaden gäller. Om du väljer *Grupp* ska du välja artikelgruppen. Om du väljer *Alla* är det här fältet inte tillgängligt.
    - **Enhetstyp** – Välj den enhetstyp som gäller för erbjudanderaden (*Lagerenhet* eller *Nominell viktenhet*). Observera att det här fältet kan vara tomt för äldre poster. I det här fallet används värdet för *Lagerenhet*.
    - **(Lagerhanteringsparametrar)** – I de återstående fälten på transaktionsraden anger du värden för lagerhanteringsparametrarna som ska användas för att definiera de artiklar som ingår i affären (t.ex. artikelstorlek, färg, stil, plats och lager). Välj om du vill lägga till eller ta bort dimensionerna **Visa dimensioner** i åtgärdsfönstret.

1. Klicka på **Spara** i åtgärdsfönstret.
1. Om du vill begränsa den uppsättning artiklar som en erbjudanderad gäller för, markerar du raden och sedan på snabbflikarna **Rabatthantering**, välj **Filter** för att öppna standard dialogruta **Förfrågan**.
1. För varje erbjudanderad som du lägger till ställer du in beräkningsdetaljerna och övrig information på snabbfliken **Rabatthanteringsdetaljer**, enligt beskrivningen i nästa avsnitt.

## <a name="add-rebate-management-details-to-a-deal-line"></a>Lägg till rabatt administrationsinformation i ett erbjudanderad

För varje rad i erbjudande måste du ställa in information på snabbfliken **Rabatthanteringsdetaljer**. Först väljer du den hanterade raden snabbfliken på **Rabatthantering** . Ställ sedan in värden för den raden med hjälp av de olika flikarna på snabbflikarna **Rabatthanteringsinformation**. Följande delgrupper beskriver hur du använder varje flik.

### <a name="settings-on-the-general-tab"></a>Inställningar på fliken Redovisning

På fliken **Allmänt** på snabbfliken **Rabatthanteringsinformation** kan du ställa in beräkningsmetod och underlag för den valda raden. Den här inställningen styr om ett minsta inköp krävs, bokföringsprofilerna som är kopplade till avtalsraden och detaljerna för beräkningen. Följande register beskriver de fält som är tillgängliga.

| Fält | beskrivning |
|---|---|
| Beräkningsmetod | Välj vilken metod som ska användas när den valda avtalsraden kombineras med andra avtalsrader (*Stegvis*, *Ackumulerad*, *Rullande* eller *Summa*). Värdet i det här fältet kan påverka resultatet av dina rabattberäkningar. En fullständig beskrivning av varje metod och exempel som visar hur den påverkar rabattberäkningen finns i avsnittet [Beräkningsmetoder för erbjudanderader](#calc-methods) längre fram i det här avsnittet. |
| Bas | Välj om rabatten ska tillämpas på kvantitet (det vill säga det totala antalet enheter som köps eller säljs) eller värde (det vill säga det totala priset för varor som köps eller säljs). |
| Transaktionstyp | <p>Välj tidpunkt i processen när beräkningen ska ske:</p><ul><li>*Order* – Använd den beställda kvantiteten eller det beställda värdet som grund för beräkningen.</li><li>*Levererad* – Använd den levererade kvantiteten eller det beställda värdet som grund för beräkningen.</li><li>*Faktura* – Använd den fakturerade kvantiteten eller det beställda värdet som grund för beräkningen.</li></ul> |
| Enhet | Om du har valt *Kvantitet* i fältet **Bas** ska du välja enheten som kvantiteten måste anges i. |
| Minimibelopp | Ange det minsta belopp som måste betalas per period. Du kan ange ett negativt värde om du vill tillåta negativa rabattbelopp om kreditnotor överskrider försäljningen för perioden. |
| Princip för rabattreducering | Välj [princip för rabattreducering](rebate-reduction-principle.md) som gäller erbjudanderaden. |
| Variantnummer | Om erbjudanderaden gäller för en artikel som har varianter väljer du den variant som erbjudanderaden gäller för. |
| Bas för leverantörsrabatt | <p>Det här fältet visas bara för leverantörsrabatter (d.v.s. erbjudanden där fältet **Modul** är inställt på *Leverantör*). Markera basen för leverantörsrabatten.</p><ul><li>*Inköpsorder* – Rabatten som leverantören tar emot baseras på kvantiteten eller värdet på inköpsordern.</li><li>*Försäljningsorder* – Leverantören får ett rabatt endast efter att varorna har sålts. Rabatten baseras på kvantiteten eller värdet på försäljningsordern.</li></ul> |
| Prisbas | <p>Det här fältet visas bara för leverantörsrabatter (erbjudanden där fältet **Modul** är inställt på *Leverantör*). Om du har valt *Försäljningsorder* i fältet **Underlag för leverantörsrabatt**, ska du välja en prisbas:</p><ul><li><p>*FIFO* – Den periodiska uppgiften **Beräkna FIFO-inköpspris** måste köras för att rabatten ska beräknas. (Om du vill köra uppgiften går du till **Rabatthantering \> Periodiska uppgifter \> Beräkna FIFO-inköpspris**.) En regel för först in, först ut (FIFO) används för att beräkna värdet på det lager som säljs. Det här värdet används sedan för att beräkna leverantörsrabatterna. Här är ett exempel:</p><ul><li>**Sålda lager:** 1 000 enheter 3,00 USD styck = 3 000 USD</li><li>**Aktuellt inköpspris, baserat på FIFO:** 2,00 USD</li><li>**Arbetsberäkning:** *Sålda enheter* × *Aktuellt inköpspris* = 1 000 × 2,00 USD = 2 000 USD</li></ul></li><li><p>*Senaste inköpspris* – Värdet från den senaste inköpstransaktionen används för att beräkna leverantörsrabatterna. Här är ett exempel:</p><ul><li>**Sålda lager:** 1 000 enheter 3,00 USD styck = 3 000 USD</li><li>**Senaste inköpspris:** 2,00 USD</li><li>**Arbetsberäkning:** *Sålda enheter* × *Senaste inköpspris* = 1 000 × 2,00 USD = 2 000 USD</li></ul></li><li><p>*Genomsnittligt inköpspris* – Det viktade medelvärdet för de senaste *X* månaderna används för att beräkna leverantörsrabatterna. Om du väljer det här alternativet måste du ange antalet månader i fältet **Antal månader** (som endast är tillgängligt om fältet **Prisunderlag** är inställt på *Genomsnittligt inköpspris*). Här är ett exempel:</p><ul><li>**Sålda lager:** 1 000 enheter 3,00 USD styck = 3 000 USD</li><li>**Genomsnittligt inköpspris:** 2,00 USD</li><li>**Arbetsberäkning:** *Sålda enheter* × *Genomsnittligt inköpspris* = 1 000 × 2,00 USD = 2 000 USD</li></ul></li><li><p>*Försäljningspris* – Försäljningspriset används för att beräkna leverantörsrabatterna. Här är ett exempel:</p><ul><li>**Sålda lager:** 1 000 enheter 3,00 USD styck = 3 000 USD</li><li>**Genomsnittligt inköpspris:** 2,00 USD</li><li>**Arbetsberäkning:** *Sålda enheter* × *Försäljningspris* = 1 000 × 3,00 USD = 3 000 USD</li></ul></li></ul> |
| Antal månader | Det här fältet visas bara för leverantörsrabatter (erbjudanden där fältet **Modul** är inställt på *Leverantör*). Om du har valt *Genomsnittligt inköpspris* i fältet **Prisunderlag** anger du antalet månader som ska användas. |
| Bokföringsprofil | Välj den [bokföringsprofil](rebate-management-posting.md) som gäller för den valda erbjudanderaden. Denna profil används bara när fältet **Stäm av efter** i avtalshuvudet är inställt på *Rad*. Om fältet **Stäm av efter** vid är inställt på *Erbjudande* används alltid den bokföringsprofil som anges i erbjudanderubriken. Om ingen bokföringsprofil har ställts in på erbjudanderaden används den bokföringsprofil som anges i erbjudanderubriken. |
| Bokföringsprofil för garanti | Det här fältet fungerar som fältet **Bokföringsprofil**, men det gäller endast för royalties. |
| Betalningstyp | Betalningstypen för bokföringsprofilen som valts för erbjudandet. |
| Moms inklusive | Välj om transaktionen ska inkluderas i moms. Inkluderad moms är endast relevant när fältet **Bas** har värdet *Värde*. Fakturabeloppet används som momsbeloppet. Om rabattberäkningen baseras på en procentsats, multipliceras rabattprocenten med det belopp som inkluderas i momsen. Observera att beräkningen använder momsvärdet från avtalsraden. |
| Inkludera kreditfakturor | <p>Ange alternativet *Ja* om kreditnotor ska inkluderas i rabattberäkningen.</p><p>Om du ställer in alternativet till *Ja*, varierar effekten, beroende på värdet i fältet **Transaktionstyp**:</p><ul><li>Om fältet **Transaktionstyp** ställs in på *Faktura*, faktorn för beräkningen i kreditfakturor. Denna konfiguration är den vanliga konfigurationen.</li><li>Om fältet **Transaktionstyp** är inställt på *Order*, faktorn för beräkningen både i försäljningsorder som har negativa värden och öppna returnerade order.</li></ul> |
| Rabatterat belopp | Ange alternativet *Ja* om du vill basera beräkningen på det rabatterade beloppet för artikeln eller artiklarna i fall där rabatter ges för rabatter på raden. |
| Endast betalade fakturor | Ange det här alternativet till *Ja* om beräkningen endast ska beakta fullt betalda fakturor. (Det innebär alltså inte att rabatter beräknas för delvis betalda fakturor.) Det här alternativet är endast tillgängligt om fältet **Transaktionstyp** är inställt på *Faktura*. |
| Inkludera fritextfaktura | Ange alternativet *Ja* för att inkludera fritextfakturor i beräkningen. Fritextfakturor kan endast inkluderas för erbjudanderader där fältet **Artikelkod** är inställt på *Alla*. |
| Inkludera kvittningsrabatt | Ange alternativet *Ja* om du vill minska rabatten med den första kvittningsrabatten. Det antas att organisationen tar den första kvittningsrabatten. Ange detta alternativ till *Nej* om du vill aktivera kvittningsrabatten som ska användas senare. |
| Dokumentnoteringar | Ange noteringar som ska användas som transaktionstext på journalrader för rabattransaktioner. |

### <a name="settings-on-the-dates-tab"></a>Inställningar på fliken Datum

Inställningarna på fliken **Datum** på snabbfliken **Rabatthanteringsinformation** definierar frekvensen och tidpunkten för beräkningarna som anges på fliken **Allmänt**. De bestämmer hur beräkningar sker under bearbetningstiden.

På den här fliken kan du ange datumintervallet som det valda erbjudandet gäller för samt beräkningsfrekvensen. Du kan även ange om garantin ska bokföras och när.

Du kan använda knapparna i verktygsfältet för att lägga till datumrader i rutnätet eller för att ta bort dem. Om det finns flera datumrader får de giltiga datumintervallen inte överlappa varandra. I annat fall visas ett felmeddelande när du försöker spara affären.

Följande register beskriver de fält som är tillgängliga för varje datumrad.

| Fält | beskrivning |
|---|---|
| Från-datum | Ange det första datumet som datumraden gäller för. Om datumen "från" och "till" anges i sidhuvudet i erbjudandet används de som standardvärden för varje ny datumrad. |
| Till-datum | Ange det sista datumet som datumraden gäller för. Om datumen "från" och "till" anges i sidhuvudet i erbjudandet används de som standardvärden för varje ny datumrad. |
| Per | Ange hur ofta erbjudanderaden ska beräknas. Ange ett heltal här och välj sedan en enhet i fältet **Ackumulera efter**. Om du till exempel vill beräkna varannan vecka ställer du in fältet **Per** till *2* och **Ackumulera efter** till *Veckor*. |
| Ackumulera efter | Välj den enhet som gäller för inställningen **Per**. Välj *Livstid* för att beräkna över hela livslängden för erbjudanderaden. Välj *Anpassad period* för att välja en period som i redovisningen. I detta fall måste du också ställa in fältet **Periodtyp**. |
| Periodtyp | Det här fältet är endast tillgängligt om fältet **Ackumulera av efter** anges till *Anpassad period*. De värden som är tillgängliga för urval kommer från de periodtyper som är definierade i redovisningen. |
| Första dagen i veckan | Ange hur veckor identifieras för perioden. Det här fältet är endast tillgängligt om fältet **Ackumulera efter** anges till *Veckor*. |
| Anspråk per | Ange hur ofta rabattavtal kan begärts för erbjudanderaden. Ange ett heltal här och välj sedan en enhet i fältet **Anspråk efter**. |
| Anspråk efter | Välj den enhet som gäller för inställningen **Anspråk efter**. Välj *Livstid* om du vill tillåta anspråk bara en gång under hela erbjudanderadens livstid. Välj *Anpassad period* för att välja en period som i redovisningen. I detta fall måste du också ställa in fältet **Typ av anspråksperiod**. |
| Typ av anspråksperiod | Det här fältet är endast tillgängligt om fältet **Anspråk efter** anges till *Anpassad period*. De värden som är tillgängliga för urval kommer från de periodtyper som är definierade i redovisningen. |
| Process vid bokföring | Markera den här kryssrutan om anspråksraden ska behandlas vid bokföringstid. Detta alternativ är endast tillgängligt för erbjudanderader där fältet **Transaktionstyp** på fliken **Allmänt** är inställt på *Levererad* eller *Faktura*. För reservering bokförs provisionen när leveransfakturan eller fakturan genereras. |
| Garanti per | Det här fältet gäller endast royaltyerbjudanden. Ange hur ofta garantin för royaltyn ska beräknas under perioden som definieras i inställningen **Ackumulera efter**. Ange ett heltal här och välj sedan en betalningsenhet i fältet **Garanti betald**. |
| Garanti betald | <p>Det här fältet gäller endast royaltyerbjudanden. Det fungerar tillsammans med fältet **Garanti per** för att definiera att frekvensen för garantiberäkningen. Välj ett av följande värden:</p><ul><li><p>*Början på perioden* – Garantin betalas i början av avtalsperioden som är definierad för datumraden. Den fullständiga garantin behandlas först. Bara värdet av royalties som överstiger beloppen bokförs som en royalty. Här är ett exempel:</p><ul><li>**Garantiminimum:** 10 000 USD mer än två månader.</li><li>**Månad 1:** 10 000 USD bokfördes som en garanti och 0 USD i royalties bokfördes.</li><li>**Månad 2:** 2 000 USD bokfördes till royalties och 0 USD i garantier bokfördes.</li><li>**Arbetsberäkning:** *Resterande garanti* – *Bokförda royalties* = 0 – 2 000 =-2 000 USD.</li></ul><p>Eftersom en royaltybetalning på 2 000 USD krävs, skapas en journal för 2 000 USD.</p><p>**Obs!** Garantin ska beräknas och bokföras tillsammans med avdragsavsättningen för den första perioden.</p></li><li><p>*Periodslut* – Garantin ska inte betalas förrän i slutet av avdragsavtalet, enligt vad som definierats på datumraden. Här är ett exempel:</p><ul><li>**Garantiminimum:** 10 000 USD mer än två månader.</li><li>**Månad 1:** 5 000 USD har bokförts som en royalty och en journal har skapats.</li><li>**Månad 2:** 7 000 USD har bokförts som en royalty och en journal har skapats.</li><li>**Arbetsberäkning:** Eftersom royalties överstiger garantibeloppet bokförs 0 USD bokföras på garantin.</li></ul><p>**Obs!** Garantin ska beräknas och bokföras endast tillsammans med avdrag och rabattransaktion för den sista perioden.</p></li></ul> |
| Garantiminimum | Det här fältet gäller endast royaltyerbjudanden. Ange minimibeloppet för garantin för en royalty, i den valuta som är definierad i erbjudanderubriken. |

### <a name="settings-on-the-lines-tab"></a>Inställningar på fliken Rader

På fliken **Rader** på snabbfliken **Rabatthanteringsinformation** kan du definiera beräkningsrader för den valda erbjudanderaden. Varje beräkningsrad innehåller en kvantitets- eller värdetröskel och ett relaterat kompensationsbelopp eller tillhörande artiklar. Fältet **Bas** på den **allmänna** anger om varje beräkningsrad baseras på en kvantitet eller ett värde.

Du kan använda knapparna i verktygsfältet för att lägga till beräkningsrader i rutnätet eller för att ta bort dem. Du kan ha val annat antal beräkningsrader. Om det finns flera beräkningsrader får emellertid kvantiteten "till" och "från" eller värdeintervallen inte överlappa.

Följande register beskriver de fält som är tillgängliga för varje beräkningsrad.

| Fält | beskrivning |
|---|---|
| Från kvt/värde | Ange minsta kvantitet eller värde som beräkningsraden gäller för. |
| Till kvt/värde | Ange högsta kvantitet eller värde som beräkningsraden gäller för. |
| Rabatthanteringsmetod | <p>Det här fältet är bara tillgängligt för erbjudanden där fältet **Rabattutleverans** är inställt på *Ekonomisk*. Välj den metod du vill använda för beräkning av rabatten.</p><ul><li>*Fast* – Ett fast prisbelopp används för raden.</li><li>*Procent* – En procent av försäljningsbeloppet används.</li><li>*Kurs* – Ett fast prisbelopp per order används.</li></ul><p>**Viktigt:** Vi rekommenderar starkt att du använder samma metod för alla beräkningsrader på fliken **Rader**. Om en ny metod krävs skapar du en ny avtalsrad. Kom ihåg att du kan använda knappen **Kopiera rad** på snabbfliken **Rabatthantering** för att skapa en ny avtalsrad från en befintlig avtalsrad.</p><p>**Obs!** Om fältet **Rabattutleverans** är inställt på *Artikel* är det här fältet alltid inställt på *Fast*. Mer information om hur du anger artiklarna finns i texten som följer den här tabellen. |
| Rabatthanteringsbelopp | Det här fältet är bara tillgängligt för erbjudanden där **Rabattutleverans** är inställt på *Ekonomisk*. Ange det belopp som ska användas för att beräkna rabatten, baserat på den metod som du har valt i fältet **Rabatthanteringsmetod**. |

Som tidigare tabell nämns, för transaktioner där fältet **Rabattutleverans** i rubriken är inställt på *Artikel*, måste du ange de artiklar som ska tillhandahållas för varje beräkningsrad på fliken **Rader**. Följ dessa steg om du vill ange artiklarna.

1. Skapa den beräkningsrad som behövs om den inte finns på fliken **Rader** och markera den.
1. Om erbjudandet inte har sparats sedan du skapade beräkningsraden väljer du **Spara** i åtgärdsfönstret.
1. På fliken **Rader**, välj **Artiklar**.
1. På sidan **Artiklar**, använd knapparna i åtgärdsfönstret för att lägga till objekt i rutnätet eller ta bort objekt efter behov. För varje rad anger du följande fält:

    - **Artikelnummer** – Välj den artikel som ska tillhandahållas.
    - **(Övriga dimensioner)** – Om du måste använda flera dimensioner för att definiera artikeln (till exempel artikelkonfiguration, storlek, färg, utförande, webbplats eller lagerställe) anger du dem. Välj om du vill lägga till eller ta bort tillgängliga dimensioner, välj **Visa dimensioner** i åtgärdsfönstret.
    - **Kvantitet** – Ange den kvantitet som ska anges efter att tröskelvärdet för den valda beräkningsraden har uppfyllts.
    - **Enhet** – Välj den enhet som värdet **kvantitet** angivet i.
    - **Flera** – Det här fältet arbetar tillsammans med fältet **Kvantitet**. På en artikelrad anger du till exempel fältet **Kvantitet** till *2* och fältet **Flera** av *100*. Om du sedan har en total försäljningsorderkvantitet på 150 blir två av artiklarna gratis (två per 100).

### <a name="settings-on-the-inventory-dimensions-tab"></a>Inställningarna på fliken Lagerdimensioner

Fliken **Lagerdimensioner** på snabbfliken **Rabatthanteringsinformation** visar alla tillgängliga dimensionsvärden för produkten som har angetts för den valda raden. Den omfattar dimensioner som inte visas på snabbfliken **Rabatthantering**. Du kan bara redigera värden för de dimensioner som gäller för den valda produkten.

Du kan lägga till fler dimensioner i rutnätet på snabbfliken **Rabatthantering** genom att välja **Visa dimensioner** i åtgärdsfönstret.

## <a name="calculation-methods-for-deal-lines"></a><a name="calc-methods"></a>Beräkningsmetoder för erbjudanderader

Varje gång du ställer in detaljer för en av raderna, enligt beskrivningen i det föregående avsnittet, måste du välja beräkningsmetod för den raden. I det här avsnittet förklaras de olika beräkningsmetoderna och här ges exempel som visar hur de olika metoderna beräknar det totala rabattbeloppet för order och erbjudanderader. I dessa exempel är order och raderna identiska. Det är bara beräkningsmetoderna som skiljer sig åt.

### <a name="stepped-calculation-method"></a>Stegvis beräkningsmetod

Den stegvisa beräkningsmetoden beräknas stegvis, där varje avtalsrad stegvis bidrar till rabatten tills försäljningskvantiteten eller värdet uppnås. Stegen kan baseras på antingen kvantiteten eller värdet på de varor som säljs, beroende på inställningen i fältet **Bas** på fliken **Allmänt** på snabbfliken **Rabatthanteringsinformation**.

En avtalsrad ställs till exempel in så att fältet **Beräkningsmetod** får värdet *Stegvis* och fältet **Bas** får värdet *Värde*. Den omfattar beräkningsrader som innehåller följande rabatter:

- **Rad A:** 10 procent upp till 1 000 USD
- **Rad B:** 25 procent upp till 2 500 USD

Om värdet av de varor som köpts in eller sålts 2 000 USD, beräknas den resulterande 350 USD på följande sätt:

- **Rabatt (A):** *Tröskel (A)* × *Procent (A)* = 1 000 USD × 10 procent = 100 USD
- **Rabatt (B):** (*Värde såld* – *Tröskel (A)*) × *Procent (B)* = (2 000 USD – 1 000 USD) × 25 procent = 250 USD
- **Total rabatt:** *Rabatt (A)* + *Rabatt (B)* = 100 + 250 = 350 USD

Om fältet **Bas** ställs in på *Kvantitet* istället för *Värde*, stegvisa beräkningsmetoden på liknande sätt. Det första steget används för den identifierade kvantiteten tills det andra steget uppnås. Det andra steget används sedan för all kvantitet över det första steget tills det tredje steget uppnås. Den här processen fortsätter sedan genom alla efterföljande steg.

### <a name="cumulative-calculation-method"></a>Ackumulerad beräkningsmetod

Den ackumulerade beräkningsmetoden använder bara en beräkningsrad för att beräkna rabatten. Om flera beräkningsrader är tillgängliga för den totala raden används den beräkningsrad med det högsta värdet eller den högsta kvantiteten som nås för hela kvantiteten eller värdet. Liksom andra beräkningsmetoder använder den kumulativa metoden inställningen av fältet **Bas** på fliken **Allmänt** på snabbfliken **Rabatthanteringsinformation** för att avgöra om försäljningskvantiteten eller försäljningsvärdet används för att beräkna rabatterna.

En avtalsrad ställs till exempel in så att fältet **Beräkningsmetod** får värdet *Ackumulerad* och fältet **Bas** får värdet *Värde*. Den omfattar beräkningsrader som innehåller följande rabatter:

- **Rad A:** 10 procent upp till 1 000 USD
- **Rad B:** 25 procent upp till 2 500 USD

Om värdet på varorna som köptes eller sålts är 2 000 USD, använder beräkningen endast rad B. Den resulterande rabatten på 500 USD beräknas på följande sätt:

- **Total rabatt:** *Värde såld* × *Rabatt (B)* = 2 000 × 25 procent = 500 USD

### <a name="rolling-calculation-method"></a>Rullande beräkningsmetod

Den rullande beräkningsmetoden beräknar alla möjliga beräkningsrader för erbjudandet. Om det finns flera beräkningsrader, och fler än en av dem uppnås, används alla beräkningsrader som nås, men högre tröskelvärden gäller för varje procent. Liksom andra beräkningsmetoder använder den rullande metoden inställningen av fältet **Bas** på fliken **Allmänt** på snabbfliken **Rabatthanteringsinformation** för att avgöra om försäljningskvantiteten eller försäljningsvärdet används för att beräkna rabatterna.

En avtalsrad ställs till exempel in så att fältet **Beräkningsmetod** får värdet *Rullande* och fältet **Bas** får värdet *Värde*. Den omfattar beräkningsrader som innehåller följande rabatter:

- **Rad A:** 10 procent upp till 1 000 USD
- **Rad B:** 25 procent upp till 2 500 USD

Om värdet av de varor som köpts in eller sålts 2 000 USD, beräknas den resulterande 600 USD på följande sätt:

- **Rabatt (A):** *Tröskel (A)* × *Procent (A)* = 1 000 USD × 10 procent = 100 USD
- **Rabatt (B):** *Värde såld* × *Procent (B)* = 2 000 × 25 procent = 500 USD
- **Total rabatt:** *Rabatt (A)* + *Rabatt (B)* = 100 + 500 = 600 USD

### <a name="total-calculation-method"></a>Total beräkningsmetod

Den totala beräkningsmetoden använder alla beräkningsrader för att beräkna rabatten. Den totala kvantiteten används för att beräkna rabatten för varje beräkningsrad som nås, och varje beräkningsrad tillämpar sin procentsats på hela beloppet. Liksom andra beräkningsmetoder använder den totala metoden inställningen av fältet **Bas** på fliken **Allmänt** på snabbfliken **Rabatthanteringsinformation** för att avgöra om försäljningskvantiteten eller försäljningsvärdet används för att beräkna rabatterna.

En avtalsrad ställs till exempel in så att fältet **Beräkningsmetod** får värdet *Total* och fältet **Bas** får värdet *Värde*. Den omfattar beräkningsrader som innehåller följande rabatter:

- **Rad A:** 10 procent upp till 1 000 USD
- **Rad B:** 25 procent upp till 2 500 USD

Om värdet av de varor som köpts in eller sålts 2 000 USD, beräknas den resulterande 700 USD på följande sätt:

- **Rabatt (A):** *Värde såld* × *Procent (A)* = 2 000 × 10 procent = 200 USD
- **Rabatt (B):** *Värde såld* × *Procent (B)* = 2 000 × 25 procent = 500 USD
- **Total rabatt:** *Rabatt (A)* + *Rabatt (B)* = 200 + 500 = 700 USD
