---
title: Granska den konfigurerade ER-komponenten för att förhindra körningsproblem
description: Den här artikeln innehåller information om hur du granskar de konfigurerade komponenterna för elektroniska rapporter (ER) för att förhindra problem som kan uppstå vid körning.
author: kfend
ms.date: 09/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.custom: 220314
ms.assetid: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner
ms.openlocfilehash: 1ca59d6c26dbcf065adb952409da30002d951f62
ms.sourcegitcommit: a1d14836b40cfc556f045c6a0d2b4cc71064a6af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2022
ms.locfileid: "9476865"
---
# <a name="inspect-the-configured-er-component-to-prevent-runtime-issues"></a>Granska den konfigurerade ER-komponenten för att förhindra körningsproblem

[!include[banner](../includes/banner.md)]

Alla konfigurerade [elektronisk rapporterings- (ER)](general-electronic-reporting.md) [format](er-overview-components.md#format-components-for-outgoing-electronic-documents) och [modellmappning](er-overview-components.md#model-mapping-component) kan [valideras](er-fillable-excel.md#validate-an-er-format) vid designtillfället. Under valideringen görs en konsekvenskontroll för att förhindra körningsproblem som kan uppstå, t. ex. körningsfel och prestandaförsämring. För varje problem som hittas tillhandahålls sökvägen till ett problematiskt element. För vissa problem är en automatisk korrigering tillgänglig.

Som standard används valideringen automatiskt i följande fall för en återställningskonfiguration som innehåller de tidigare nämnda återställningskomponenterna:

- Du [importerar](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally) en ny version av en ER-konfiguration till din instans av Microsoft Dynamics 365 Finance.
- Du ändrar status för den redigerbara ER-konfigurationen från **Utkast** till **Slutförd**.
- Du [baserar om](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase) en redigerbar ER-konfiguration genom att använda en ny basversion.

Du kan uttryckligen köra den här valideringen. Välj ett av följande tre alternativ och följ de steg som tillhandahålls:

- Alternativ 1:

    1. Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.
    2. I konfigurationsträdet i det vänstra fönstret väljer du önskad ER-konfiguration som innehåller mappningskomponenten för ER-formatet eller ER-modellen.
    3. I snabbfliken **Versioner** väljer du önskad version för vald ER-konfiguration.
    4. I åtgärdsfönstret, välj **Validera**.

- Alternativ 2, för ett ER-format:

    1. Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.
    2. I konfigurationsträdet i det vänstra fönstret väljer du önskad ER-konfiguration som innehåller mappningskomponenten för ER-formatet eller ER-modellmappningen.
    3. I snabbfliken **Versioner** väljer du önskad version för vald ER-konfiguration.
    4. Klicka på **Designer** i åtgärdsfönstret.
    5. På snabbfliken **Formatdesigner** på åtgärdsfönstret väljer du **Validera**.

- Alternativ 3 för en ER-modellmappning:

    1. Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.
    2. I konfigurationsträdet i det vänstra fönstret väljer du önskad ER-konfiguration som innehåller mappningskomponenten för ER-modellen.
    3. I snabbfliken **Versioner** väljer du önskad version för vald ER-konfiguration.
    4. Klicka på **Designer** i åtgärdsfönstret.
    5. På sidan **Modell till mappning av datakälla** i åtgärdsfönstret, välj **Designer**.
    6. På sidan **Modellmappningsdesigner** väljer du **Validera** i åtgärdsfönstret.

Om du vill hoppa över valideringen när konfigurationen importeras följer du stegen nedan.

1. Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.
2. På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.
3. Ange alternativet **Validera konfigurationen efter import** till **Nej**.

Följ stegen nedan om du vill hoppa över valideringen när versionens status ändras eller baseras om.

1. Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.
2. På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.
3. Ställ in alternativet **Hoppa över valideringen när konfigurationens status ändras eller baseras om** till **Ja**.

ER använder följande kategorier för att gruppera konsekvenskontrollgranskningar:

- **Körbarhet** – granskningar som identifierar kritiska problem som kan inträffa under körning. De här problemen finns oftast på en **Fel**-nivå. 
- **Prestanda** – granskningar som identifierar problem som kan orsaka ineffektiv körning av konfigurerade ER-komponenter. De här problemen finns oftast på nivån **Varning**.
- **Dataintegritet** – granskningar som upptäcker problem som kan leda till dataförlust eller körningsproblem. De här problemen finns oftast på nivån **Varning**.

## <a name="list-of-inspections"></a>Förteckning över granskningar

Följande tabell ger en översikt över granskningar som ER tillhandahåller. Om du vill ha mer information om dessa kontroller använder du länkarna i den första kolumnen för att gå till relevanta avsnitt i det här ämnet. I dessa avsnitt beskrivs de typer av komponenter som ER granskar och hur du kan konfigurera om ER-komponenter för att undvika problem.

<table>
<thead>
<tr>
<th>Namn</th>
<th>Kategori</th>
<th>Nivå</th>
<th>Meddelande</th>
</tr>
</thead>
<tbody>
<tr>
<td><a href='#i1'>Typkonvertering</a></td>
<td>Körbarhet</td>
<td>Fel</td>
<td>
<p>Det går inte att konvertera uttryck av typen &lt;typ&gt; till fält av typen &lt;typ&gt;.</p>
<p><b>Körningsfel:</b> Undantag av typen</p>
</td>
</tr>
<tr>
<td><a href='#i2'>Typkompatibilitet</a></td>
<td>Körbarhet</td>
<td>Fel</td>
<td>
<p>Det går inte att använda det konfigurerade uttrycket som bindning för det aktuella formatelementet till en datakälla eftersom det här uttrycket returnerar värdet för datatypen &lt;typ&gt; som ligger utanför omfattningen av datatyper som stöds av det aktuella formatelementet av typen &lt;typ&gt;.</p>
<p><b>Körningsfel:</b> Undantag av typen</p>
</td>
</tr>
<tr>
<td><a href='#i3'>Konfigurationselement saknas</a></td>
<td>Körbarhet</td>
<td>Fel</td>
<td>
<p>Sökväg hittades inte &lt;sökväg&gt;.</p>
<p><b>Körningsfel:</b> Elementet för konfigurationen &lt;sökväg&gt; hittades inte</p>
</td>
</tr>
<tr>
<td><a href='#i4'>Körbarhet för ett uttryck med funktionen FILTER</a></td>
<td>Körbarhet</td>
<td>Fel</td>
<td>
<p>Listuttrycket för funktionen FILTER är inte frågningsbart.</p>
<p><b>Körningsfel:</b> Filtrering stöds inte. Validera konfigurationen om du vill ha mer information.</p>
</td>
</tr>
<tr>
<td rowspan='2'><a href='#i5'>Körbarhet för en GROUPBY datakälla</a></td>
<td>Körbarhet</td>
<td>Fel</td>
<td>Sökvägen &lt;sökväg&gt; stöder inte frågor.</td>
</tr>
<tr>
<td>Körbarhet</td>
<td>Fel</td>
<td>
<p>Gruppera efter-funktionen kan inte utföras med fråga.</p>
<p><b>Körningsfel:</b> Gruppera efter-funktionen kan inte utföras med fråga.</p>
</td>
</tr>
<tr>
<td><a href='#i6'>Körbarhet för en JOIN datakälla</a></td>
<td>Körbarhet</td>
<td>Fel</td>
<td>
<p>Det går inte att koppla en lista &lt;sökväg&gt; som inte är ett filter i fråga.</p>
<p><b>Körningsfel:</b> Funktionen Kopplad datakälla ska vara ett filteruttryckberäknat fält som har anropats felaktigt.</p>
</td>
</tr>
<tr>
<td><a href='#i7'>Funktionen FILTER jämfört med WHERE</a></td>
<td>Prestanda</td>
<td>Varning</td>
<td>Det är bättre att använda FILTER-funktionen för uttrycket än WHERE med hänsyn till prestanda. Välj Korrigera om du vill ersätta automatiskt.</td>
</tr>
<tr>
<td><a href='#i8'>Funktionen ALLITEMSQUERY jämfört med ALLITEMS</a></td>
<td>Prestanda</td>
<td>Varning</td>
<td>Det är bättre att använda ALLITEMSQUERY-funktionen för uttrycket än ALLITEMS med hänsyn till prestanda. Välj Korrigera om du vill ersätta automatiskt.</td>
</tr>
<tr>
<td><a href='#i9'>Hänsyn tas till tomma listärenden</a></td>
<td>Körbarhet</td>
<td>Varning</td>
<td>
<p>Listan &lt;sökväg&gt; har ingen kontroll av en tomma listärende, vilket kan resultera i att fel uppstår vid körning. Lägg till en kontroll för tom listärende.</p>
<p><b>Körningsfel:</b> Listan är tom vid &lt;sökväg&gt;</p>
<p><b><a href='#i9a'>Potentiellt problem</a>:</b> Raden fylls i när en datakälla den fylls på från innehåller flera poster</p>
</td>
</tr>
<tr>
<td><a href='#i10'>Körbarhet för ett uttryck med funktionen FILTER (cachelagring)</a></td>
<td>Körbarhet</td>
<td>Fel</td>
<td>
<p>Det går inte att använda FILTER funktionen för den valda typen av datakälla. En datakälla av typen tabellposter kan endast användas om den inte är cachelagrad och inte har manuellt tillagda kapslade datakällor.</p>
<p><b>Körningsfel:</b> Filtrering stöds inte. Validera konfigurationen om du vill ha mer information.</p>
</td>
</tr>
<tr>
<td><a href='#i11'>Bindning saknas</a></td>
<td>Körbarhet</td>
<td>Varning</td>
<td>
<p>Sökväg &lt;sökväg&gt; har ingen bindning till någon datakälla när modellens mappning används.</p>
<p><b>Körningsfel:</b> Sökväg &lt;sökväg&gt; är inte bunden</p>
</td>
</tr>
<tr>
<td><a href='#i12'>Mall som inte är länkad</a></td>
<td>Dataintegritet</td>
<td>Varning</td>
<td>Fil &lt;namn&gt; är inte länkat till några filkomponenter och tas bort när status för konfigurationsversionen ändras.</td>
</tr>
<tr>
<td><a href='#i13'>Inte synkroniserat format</a></td>
<td>Dataintegritet</td>
<td>Varning</td>
<td>Definierat namn &lt;komponentnamn&gt; finns inte i Excel-arket &lt;arknamn&gt;</td>
</tr>
<tr>
<td><a href='#i14'>Inte synkroniserat format</a></td>
<td>Dataintegritet</td>
<td>Varning</td>
<td>
<p>&lt;Taggat Word-innehållskontroll&gt; märke existerar inte i Word-mallfilen</p>
<p><b>Körningsfel:</b> &lt;Taggat Word-innehållskontroll&gt; märke existerar inte i Word-mallfilen.</p>
</td>
</tr>
<tr>
<td><a href='#i15'>Ingen standardmappning</a></td>
<td>Dataintegritet</td>
<td>Fel</td>
<td>
<p>Mer än en modellmappning finns för &lt;modellnamn (rotbeskrivning)&gt; datamodell i konfiguration &lt;konfigurationsnamn separerade med komma&gt;. Ställ in en av konfigurationerna som standard</p>
<p><b>Körningsfel:</b> Mer än en modellmappning finns för &lt;modellnamn (rotbeskrivning)&gt; datamodell i konfiguration &lt;konfigurationsnamn separerade med komma&gt;. Ställ in en av konfigurationerna som standard.</p>
</td>
</tr>
<tr>
<td><a href='#i16'>Inkonsekvent inställning av komponenter för sidhuvud eller sidfot</a></td>
<td>Dataintegritet</td>
<td>Fel</td>
<td>
<p>Sidhuvuden/sidfötter (&lt;komponenttyp: sidhuvud och sidfot&gt;) är inkonsekvent</p>
<p><b>Körtid:</b> Den senast konfigurerade komponenten används vid körning om utkastversionen av det konfigurerade ER-formatet körs.</p>
</td>
</tr>
<tr>
<td><a href='#i17'>Inkonsekvent inställning av sidkomponent</a></td>
<td>Dataintegritet</td>
<td>Fel</td>
<td>Det finns fler än två intervallkomponenter utan replikering. Ta bort onödiga komponenter.</td>
</tr>
<tr>
<td><a href='#i18'>Körbarhet för ett uttryck med funktionen ORDERBY</a></td>
<td>Körbarhet</td>
<td>Fel</td>
<td>
<p>Listuttrycket för funktionen ORDERBY är inte frågningsbart.</p>
<p><b>Körningsfel:</b> Sortering stöds inte. Validera konfigurationen om du vill ha mer information.</p>
</td>
</tr>
<tr>
<td><a href='#i19'>Föråldrade program artefakter</a></td>
<td>Dataintegritet</td>
<td>Varning</td>
<td>
<p>Elementet &lt;sökväg&gt;har markerats som föråldrat.<br>eller<br>Elementet &lt;sökväg&gt; är markerad som föråldrad med meddelande &lt;meddelandetext&gt;.</p>
<p><b>Exempel på körtidsfel:</b> klass &lt;sökväg&gt; hittas inte.</p>
</td>
</tr>
</tbody>
</table>

## <a name="type-conversion"></a><a id="i1"></a>Typkonvertering

ER kontrollerar om datatypen för ett datamodellfält är kompatibel med datatypen för ett uttryck som har konfigurerats som bindning för det fältet. Om datatyperna är inkompatibla uppstår ett valideringsfel i ER-modellmappningsdesignern. Det meddelande får är ett tillstånd som innebär att ER inte kan konvertera ett uttryck av typen A till ett fält av typen B.

Följande steg visar hur det här problemet kan uppstå.

1. Börja konfigurera ER-datamodellen och ER-modellmappningskomponenterna samtidigt.
2. Lägg till ett fält med namnet **X** i datamodellträdet och välj **Heltal** som datatyp.

    ![X-fält och datatypen Heltal lades till i datalägesträdet på sidan Datamodell.](./media/er-components-inspections-01.png)

3. I formgivaren för modellkartläggning, i **Datakällor** lägger du till en datakälla av typen **Beräknat fält**.
4. Namnge den nya datakällan **Y** och konfigurera den så att den innehåller uttrycket `INTVALUE(100)`.
5. Bind **X** till **Y**.
6. I datamodelldesignern ändrar du datatyp för fältet **X** från **Heltal** till **Int64**.
7. Välj **Validera** för att granska den redigerbara modellmappningskomponenten på sidan **Modellmappningsdesigner**.

    ![Validera den redigerbara modellmappningskomponenten på sidan Modellmappningsdesigner.](./media/er-components-inspections-01.gif)

8. Välj **Validera** för att kontrollera modellmappningskomponenten för den markerade ER-konfigurationen på sidan **Konfigurationer**.

    ![Inspektera modellmappningskomponenten på sidan Konfigurationer.](./media/er-components-inspections-01a.png)

9. Observera att ett valideringsfel uppstår. Meddelandet anger att värdet för typen **Heltal** som uttrycket `INTVALUE(100)` för datakällan **Y** returnerar inte kan lagras i datamodellfältet **X** för typen **Int64**.

Följande bild visar det körningsfel som uppstår om du ignorerar varningen och väljer **Kör** för att köra ett format som konfigurerats att använda modellmappningen.

![Körningsfel på sidan Formatdesigner.](./media/er-components-inspections-01b.png)

### <a name="automatic-resolution"></a>Automatisk lösning

Det finns inget alternativ för automatisk korrigering av det här problemet.

### <a name="manual-resolution"></a>Manuell lösning

#### <a name="option-1"></a>Alternativ 1

Uppdatera datamodellstrukturen genom att ändra datatypen för fältet datamodell så att den matchar datatypen för det uttryck som är konfigurerat för fältets bindning. I föregående exempel måste datatyp för fältet **X** ändras tillbaka till **Heltal**.

#### <a name="option-2"></a>Alternativ 2

Uppdatera modellmappningen genom att ändra uttrycket för den datakälla som är bunden till datamodellfältet. I föregående exempel måste uttrycket för datakällan **Y** ändras till `INT64VALUE(100)`.

## <a name="type-compatibility"></a><a id="i2"></a>Typkompatibilitet

ER kontrollerar om datatypen för ett formatelement är kompatibel med datatypen för ett uttryck som har konfigurerats som bindning för det formatelementet. Om datatyperna är inkompatibla uppstår ett valideringsfel i ER-åtgärdsdesignern. Meddelandet du får om att det inte går inte att använda det konfigurerade uttrycket som bindning för det aktuella formatelementet till en datakälla eftersom uttrycket returnerar ett värde för datatypen A som ligger utanför omfattningen av datatyper som stöds av det aktuella formatelementet av typen B.

Följande steg visar hur det här problemet kan uppstå.

1. Börja konfigurera ER-datamodellen och ER-formatkomponenterna samtidigt.
2. Lägg till ett fält med namnet **X** i datamodellträdet och välj **Heltal** som datatyp.
3. I formatstrukturträdet lägger du till ett formatelement av typen **Numeriskt**.
4. Namnge det nya formatelementet **Y**. I fältet **Numerisk typ** väljer du **Heltal** som datatyp.
5. Bind **X** till **Y**.
6. I formatstrukturträdet ändrar du datatyp för formatet **Y** från **Heltal** till **Int64**.
7. Välj **Validera** för att granska den redigerbara formatkomponenten på sidan **Formatdesigner**.

    ![Validera av typkompatibilitet på sidan Formatdesigner.](./media/er-components-inspections-02.gif)

8. Observera att ett valideringsfel uppstår. Meddelandet anger att det konfigurerade uttrycket endast kan acceptera **Int64**-värden. Därför kan värdet i datamodellfältet **X** för typen **Heltal** inte anges i formatelementet **Y**.

### <a name="automatic-resolution"></a>Automatisk lösning

Det finns inget alternativ för automatisk korrigering av det här problemet.

### <a name="manual-resolution"></a>Manuell lösning

#### <a name="option-1"></a>Alternativ 1

Uppdatera formatstrukturen genom att ändra datatypen för formatelementet **Numerisk** så att den matchar datatypen för det uttryck som är konfigurerat för elementets bindning. I föregående exempel måste typen **Numerisk** för formatelementet **X** ändras tillbaka till **Heltal**.

#### <a name="option-2"></a>Alternativ 2

Uppdatera formatmappningen för formatelementet **X** genom att ändra uttrycket från `model.X` till `INT64VALUE(model.X)`.

## <a name="missing-configuration-element"></a><a id="i3"></a>Konfigurationselement saknas

ER kontrollerar om bindningsuttrycken bara innehåller datakällor som har konfigurerats i den redigerbara ER-komponenten. För varje bindning som innehåller en datakälla som saknas i den redigerbara ER-komponenten uppstår ett valideringsfel i ER-åtgärdsdesignern eller ER-modellmappningsdesignern.

Följande steg visar hur det här problemet kan uppstå.

1. Börja konfigurera ER-datamodellen och ER-modellmappningskomponenterna samtidigt.
2. Lägg till ett fält med namnet **X** i datamodellträdet och välj **Heltal** som datatyp.

    ![Datamodellträd med X-fält och datatypen Heltal på sidan Datamodell.](./media/er-components-inspections-01.png)

3. I formgivaren för modellkartläggning, i **Datakällor** lägger du till en datakälla av typen **Beräknat fält**.
4. Namnge den nya datakällan **Y** och konfigurera den så att den innehåller uttrycket `INTVALUE(100)`.
5. Bind **X** till **Y**.
6. I modellmappningsdesignern, i rutan **Datakällor**, ta bort **Y** datakälla.
7. Välj **Validera** för att granska den redigerbara modellmappningskomponenten på sidan **Modellmappningsdesigner**.

    ![Inspekterar den redigerbara ER-modellmappningskomponenten på sidan Modellmappningsdesigner.](./media/er-components-inspections-03.gif)

8. Observera att ett valideringsfel uppstår. Meddelandet anger att bindningen för datamodellfältet **X** innehåller sökvägen som refererar till datakällan **Y** men den datakällan hittas inte.

### <a name="automatic-resolution"></a>Automatisk lösning

Välj **Avbind** för att åtgärda det här problemet automatiskt genom att ta bort bindningen som saknas för datakällan.

### <a name="manual-resolution"></a>Manuell lösning

#### <a name="option-1"></a>Alternativ 1

Avbind datamodellfältet **X** för att sluta referera till den obefintliga datakällan **Y**.

#### <a name="option-2"></a>Alternativ 2

I modellmappningsdesignern, fönster **Datakällor**, lägg till **Y** datakälla igen.

## <a name="executability-of-an-expression-with-filter-function"></a><a id="i4"></a>Körbarhet för ett uttryck med funktionen FILTER

Den inbyggda ER-funktionen [FILTER](er-functions-list-filter.md) används för att komma åt programtabeller, vyer eller dataentiteter genom att ett enda SQL-anrop görs för att hämta de data som behövs i en postlista. En datakälla för typen **Postlista** används som argument för den här funktionen och anger programkällan för anropet. ER kontrollerar om det går att upprätta en direkt SQL-fråga till en datakälla som det refereras till i `FILTER`-funktionen. Om det inte går att upprätta en direkt fråga, uppstår ett valideringsfel i ER-modellmappningsdesignern. Meddelandet som du tar emot anger att ER-uttrycket som innehåller `FILTER`-funktionen inte kan köras under körning.

Följande steg visar hur det här problemet kan uppstå.

1. Börja att konfigurera ER-modellmappningskomponenten.
2. Lägg till en datakällan för typen **Dynamics 365 for Operations \\ tabellposter**.
3. Namnge den nya datakällan **Leverantör**. I fältet **Vabell** väljer du **VendTable** för att ange att denna datakälla ska begära tabellen VendTable.
4. Lägg till en datakälla för typen **Beräknat fält**.
5. Namnge den nya datakällan **FilteredVendor** och konfigurera den så att den innehåller uttrycket `FILTER(Vendor, Vendor.AccountNum="US-101")`.
6. Välj **Validera** för att granska den redigerbara modellmappningskomponenten på sidan **Modellmappningsdesigner** och kontrollera att uttrycket `FILTER(Vendor, Vendor.AccountNum="US-101")` i datakällan **Leverantör** kan läsas.
7. Ändra datakällan **Levarantör** genom att lägga till ett kapslat fält av typen **Beräknat fält** för att hämta det trimmade leverantörskontonumret.
8. Namnge det nya kapslade fältet **$AccNumber** och konfigurera det så att det innehåller uttrycket `TRIM(Vendor.AccountNum)`.
9. Välj **Validera** för att granska den redigerbara modellmappningskomponenten på sidan **Modellmappningsdesigner** och kontrollera att uttrycket `FILTER(Vendor, Vendor.AccountNum="US-101")` i datakällan **Leverantör** kan läsas.

    ![Verifiering av uttrycket som har FILTER-funktionen kan sökas på sidan Modellmappningsdesigner.](./media/er-components-inspections-04.gif)

10. Observera att ett valideringsfel inträffar eftersom datakällan **Leverantör** innehåller ett kapslat fält av typen **Beräknat fält** som inte tillåter att uttrycket för datakällan **FilteredVendor** översätts till den direkta SQL-instruktionen.

Följande bild visar det körningsfel som uppstår om du ignorerar varningen och väljer **Kör** för att köra ett format som konfigurerats att använda modellmappningen.

![Körningsfel som uppstår vid körning av det redigerbara formatet på sidan Formatdesigner.](./media/er-components-inspections-04a.png)

### <a name="automatic-resolution"></a>Automatisk lösning

Det finns inget alternativ för automatisk korrigering av det här problemet.

### <a name="manual-resolution"></a>Manuell lösning

#### <a name="option-1"></a>Alternativ 1

I stället för att lägga till ett kapslat fält av typen **Beräknat fält** i datakällan **Leverantör**, lägger du till det kapslade fältet **$AccNumber** i datakällan **FilteredVendor** och konfigurerar det så att det innehåller uttrycket `TRIM(FilteredVendor.AccountNum)`. På så sätt kan uttrycket `FILTER(Vendor, Vendor.AccountNum="US-101")` köras på SQL-nivå och beräkna det kapslade fältet **$AccNumber** efteråt.

#### <a name="option-2"></a>Alternativ 2

Ändra uttrycket för datakällan **FilteredVendor** från `FILTER(Vendor, Vendor.AccountNum="US-101")` till `WHERE(Vendor, Vendor.AccountNum="US-101")`. Vi rekommenderar inte att du ändrar uttrycket för en tabell som har en stor mängd data (transaktionstabell) eftersom alla poster hämtas och urval av de nödvändiga poster som krävs görs i minnet. Därför kan den här metoden orsaka dålig prestanda. Mer information finns i [ER-funktionen WHERE](er-functions-list-where.md).

## <a name="executability-of-a-groupby-data-source"></a><a id="i5"></a>Körbarhet för en GROUPBY datakälla

Med datakällan **GROUPBY** delas frågeresultat upp i grupper av poster, vanligtvis i syfte att utföra en eller flera sammansättningar för varje grupp. Varje **GROUPBY** datakälla kan konfigureras så att den körs antingen på databasnivå eller i minnet. När en **GROUPBY** datakälla konfigureras så att den körs på databasnivå kontrollerar ER om en direkt SQL-fråga kan skapas till en datakälla som refereras till i den datakällan. Om det inte går att upprätta en direkt fråga, uppstår ett valideringsfel i ER-modellmappningsdesignern. Meddelandet som du får anger att den konfigurerade **GROUPBY** datakällan inte kan köras under körning.

Följande steg visar hur det här problemet kan uppstå.

1. Börja att konfigurera ER-modellmappningskomponenten.
2. Lägg till en datakällan för typen **Dynamics 365 for Operations \\ tabellposter**.
3. Namnge den nya datakällan **Trans**. I fältet **Tabell** väljer du **VendTrans** för att ange att denna datakälla ska begära VendTrans-tabellen.
4. Lägg till en datakälla av typen **Gruppera efter**.
5. Namnge den nya datakällan **GroupedTrans** och konfigurera den på följande sätt:

    - Välj datakällan **Trans** som källa för poster som ska grupperas.
    - I fältet **Körningsplats** väljer du **Fråga** för att ange att du vill köra den här datakällan på databasnivå.

    ![Konfigurera datakällan på parametersidan Redigera "Gruppera efter".](./media/er-components-inspections-05a.gif)

6. Välj **Validera** för att granska den redigerbara modellmappningskomponenten på sidan **Modellmappningsdesigner** och kontrollera att den konfigurerade datakällan **GroupedTrans** kan frågas.
7. Ändra datakällan **Trans** genom att lägga till ett kapslat fält av typen **Beräknat fält** för att hämta det trimmade leverantörskontonumret.
8. Namnge den nya datakällan **$AccNumber** och konfigurera den så att den innehåller uttrycket `TRIM(Trans.AccountNum)`.

    ![Konfigurera datakällan på sidan Modellmappningsdesigner.](./media/er-components-inspections-05a.png)

9. Välj **Validera** för att granska den redigerbara modellmappningskomponenten på sidan **Modellmappningsdesigner** och kontrollera att den konfigurerade datakällan **GroupedTrans** kan frågas.

    ![Validera ER-modellmappningskomponenten och verifiera att datakällan GroupedTrans på sidan Modellmappningsdesigner kan sökas.](./media/er-components-inspections-05b.png)

10. Observera att ett valideringsfel inträffar eftersom datakällan **Trans** innehåller ett kapslat fält av typen **Beräknat fält** som inte tillåter att uttrycket för datakällan **GroupedTrans** översätts till den direkta SQL-instruktionen.

Följande bild visar det körningsfel som uppstår om du ignorerar varningen och väljer **Kör** för att köra ett format som konfigurerats att använda modellmappningen.

![Körningstidfel som uppstår när varningen på sidan Formatdesigner ignoreras.](./media/er-components-inspections-05c.png)

### <a name="automatic-resolution"></a>Automatisk lösning

Det finns inget alternativ för automatisk korrigering av det här problemet.

### <a name="manual-resolution"></a>Manuell lösning

#### <a name="option-1"></a>Alternativ 1

I stället för att lägga till ett kapslat fält av typen **Beräknat fält** i datakällan **Trans**, lägger du till det kapslade fältet **$AccNumber** för objektet **GroupedTrans.lines** från datakällan **GroupedTrans** och konfigurerar det så att det innehåller uttrycket `TRIM(GroupedTrans.lines.AccountNum)`. På så sätt kan datakällan **GroupedTrans** köras på SQL-nivå och beräkna det kapslade fältet **$AccNumber** efteråt.

#### <a name="option-2"></a>Alternativ 2

Ändra värdet för fältet **Körningsplats** för datakällan **GroupedTrans** från **Fråga** till **I minnet**. Vi rekommenderar inte att du ändrar värdet för en tabell som har en stor mängd data (transaktionstabell) eftersom alla poster hämtas och gruppering och sammansättning görs i minnet. Därför kan den här metoden orsaka dålig prestanda.

## <a name="executability-of-a-join-data-source"></a><a id="i6"></a>Körbarhet för en JOIN datakälla

Datakällan [JOIN](er-join-data-sources.md) kombineras poster från två eller flera databastabeller, baserat på relaterade fält. Varje **JOIN** datakälla kan konfigureras så att den körs antingen på databasnivå eller i minnet. När en **JOIN** datakälla konfigureras så att den körs på databasnivå kontrollerar ER om en direkt SQL-fråga kan skapas till datakällor som refereras till i den datakällan. Om det inte går att upprätta en direkt SQL-fråga med minst en refererad datakälla uppstår ett valideringsfel i ER-modellmappningsdesignern. Meddelandet som du får anger att den konfigurerade **JOIN** datakällan inte kan köras under körning.

Följande steg visar hur det här problemet kan uppstå.

1. Börja att konfigurera ER-modellmappningskomponenten.
2. Lägg till en datakällan för typen **Dynamics 365 for Operations \\ tabellposter**.
3. Namnge den nya datakällan **Leverantör**. I fältet **Vabell** väljer du **VendTable** för att ange att denna datakälla ska begära tabellen VendTable.
4. Lägg till en datakällan för typen **Dynamics 365 for Operations \\ tabellposter**.
5. Namnge den nya datakällan **Trans**. I fältet **Tabell** väljer du **VendTrans** för att ange att denna datakälla ska begära VendTrans-tabellen.
6. Lägg till en datakälla av typen **Beräknat fält** som det kapslade fältet i datakällan **Leverantör**.
7. Namnge den nya datakällan **FilteredTrans** och konfigurera den så att den innehåller uttrycket `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)`.
8. Lägg till en datakälla av typen **Koppling**.
9. Namnge den nya datakällan **JoinedList** och konfigurera den på följande sätt:

    1. Lägg till datakällan **Leverantör** som den första uppsättningen med poster att koppla.
    2. Lägg till datakällan **Vendor.FilteredTrans** som den andra uppsättningen med poster att koppla. Välj **INNER** som typ.
    3. I fältet **Körning** väljer du **Fråga** för att ange att du vill köra den här datakällan på databasnivå.

    ![Konfigurera datakällan på sidan Kopplingsdesigner.](./media/er-components-inspections-06a.gif)

10. Välj **Validera** för att granska den redigerbara modellmappningskomponenten på sidan **Modellmappningsdesigner** och kontrollera att den konfigurerade datakällan **JoinedList** kan frågas.
11. Ändra uttrycket för datakällan **Vendor.FilteredTrans** från `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)` till `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)`.
12. Välj **Validera** för att granska den redigerbara modellmappningskomponenten på sidan **Modellmappningsdesigner** och kontrollera att den konfigurerade datakällan **JoinedList** kan frågas.

    ![Validera den redigerbara modellmappningskomponenten och kontrollera att datakällan JoinedList kan sökas på sidan Modellmappningsdesigner.](./media/er-components-inspections-06b.png)

13. Observera att ett valideringsfel inträffar eftersom uttrycket för datakällan **Vendor.FilteredTrans** inte kan översättas till det direkta SQL-anropet. Det direkta SQL-anropet tillåter inte heller att anropet för datakällan **JoinedList** översätts till den direkta SQL-instruktionen.

    ![Körningsfel från misslyckad validering av datakällan JoinedList på sidan Modellmappningsdesigner.](./media/er-components-inspections-06c.png)

Följande bild visar det körningsfel som uppstår om du ignorerar varningen och väljer **Kör** för att köra ett format som konfigurerats att använda modellmappningen.

![Kör det redigerbara formatet på sidan Formatdesigner.](./media/er-components-inspections-06e.png)

### <a name="automatic-resolution"></a>Automatisk lösning

Det finns inget alternativ för automatisk korrigering av det här problemet.

### <a name="manual-resolution"></a>Manuell lösning

#### <a name="option-1"></a>Alternativ 1

Ändra uttrycket för datakällan **Vendor.FilteredTrans** från `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)` tillbaka till `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)`, som varningen uppmanar till.

![Uppdaterat uttryck för datakällan på sidan Modellmappningsdesigner.](./media/er-components-inspections-06d.png)

#### <a name="option-2"></a>Alternativ 2

Ändra värdet för fältet **Kör** för datakällan **JoinedList** från **Fråga** till **I minnet**. Vi rekommenderar inte att du ändrar värdet för en tabell som har en stor mängd data (transaktionstabell) eftersom alla poster hämtas och gruppering och kopplingen görs i minnet. Därför kan den här metoden orsaka dålig prestanda. En valideringsvarning visas som informerar dig om den här risken.

## <a name="preferability-of-filter-vs-where-function"></a><a id="i7"></a>Funktionen FILTER jämfört med WHERE

Den inbyggda ER-funktionen [FILTER](er-functions-list-filter.md) används för att komma åt programtabeller, vyer eller dataentiteter genom att ett enda SQL-anrop görs för att hämta de data som behövs i en postlista. Funktionen [WHERE](er-functions-list-where.md) hämtar alla poster från den angivna källan och registrerar urvalet i minnet. En datakälla för typen **Postlista** används som argument för båda funktionerna och anger en källa att hämta poster. ER kontrollerar om det går att upprätta ett direkt SQL-anrop till en datakälla som det refereras till i funktionen **WHERE**. Om det inte går att upprätta ett direkt anrop, uppstår en valideringsvarning i ER-modellmappningsdesignern. Det meddelande du får rekommenderar att du använder **FILTER**-funktionen i stället för **WHERE**-funktionen för att öka effektiviteten.

Följande steg visar hur det här problemet kan uppstå.

1. Börja att konfigurera ER-modellmappningskomponenten.
2. Lägg till en datakällan för typen **Dynamics 365 for Operations \\ tabellposter**.
3. Namnge den nya datakällan **Trans**. I fältet **Tabell** väljer du **VendTrans** för att ange att denna datakälla ska begära VendTrans-tabellen.
4. Lägg till en datakälla av typen **Beräknat fält** som det kapslade fältet i datakällan **Leverantör**.
5. Namnge den nya datakällan **FilteredTrans** och konfigurera den så att den innehåller uttrycket `WHERE(Trans, Trans.AccountNum="US-101")`.
6. Lägg till en datakällan för typen **Dynamics 365 for Operations \\ tabellposter**.
7. Namnge den nya datakällan **Leverantör**. I fältet **Vabell** väljer du **VendTable** för att ange att denna datakälla ska begära tabellen VendTable.
8. Lägg till en datakälla för typen **Beräknat fält**.
9. Namnge den nya datakällan **FilteredVendor** och konfigurera den så att den innehåller uttrycket `WHERE(Vendor, Vendor.AccountNum="US-101")`.
10. Välj **Validera** för att granska den redigerbara modellmappningskomponenten på sidan **Modellmappningsdesigner**.

    ![Granska den redigerbara modellmappningskomponenten på sidan Modellmappningsdesigner.](./media/er-components-inspections-07a.png)

11. Observera att valideringsvarningar rekommenderar att du använder **FILTER**-funktionen i stället för **WHERE**-funktionen för datakällorna **FilteredVendor** och **FilteredTrans**.

    ![Rekommendation att använda FILTER-funktionen istället för WHERE-funktionen på sidan Modellmappningsdesigner.](./media/er-components-inspections-07b.png)

### <a name="automatic-resolution"></a>Automatisk lösning

Välj **Korrigera** för att automatiskt ersätta **WHERE**-funktionen med **FILTER**-funktionen i uttrycket för alla datakällor som visas i rutnätet på fliken **Varningar** för denna typ av granskning.

Alternativt kan du välja raden för en enskild varning i rutnätet och sedan välja **Korrigera valda**. I det här fallet ändras uttrycket automatiskt enbart i datakällan som nämns i den valda varningen.

![Välj Korrigera för att automatiskt ersätta WHERE-funktionen med FILTER-funktionen på sidan Modellmappningsdesigner.](./media/er-components-inspections-07c.png)

### <a name="manual-resolution"></a>Manuell lösning

Du kan manuellt justera uttrycken för alla datakällor som nämns i valideringsrutnätet genom att ersätta **WHERE**-funktionen med **FILTER**-funktionen.

## <a name="preferability-of-allitemsquery-vs-allitems-function"></a><a id="i8"></a>Funktionen ALLITEMSQUERY jämfört med ALLITEMS

De inbyggda ER-funktionerna [ALLITEMS](er-functions-list-allitems.md) och [ALLITEMSQUERY](er-functions-list-allitemsquery.md) returnerar ett platt **Postlista**-värde som består av en lista med poster som representerar alla element som matchar den angivna sökvägen. ER kontrollerar om det går att upprätta ett direkt SQL-anrop till en datakälla som det refereras till i funktionen **ALLITEMS**. Om det inte går att upprätta ett direkt anrop, uppstår en valideringsvarning i ER-modellmappningsdesignern. Det meddelande du får rekommenderar att du använder funktionen **ALLITEMSQUERY** i stället för funktionen **ALLITEMS** för att öka effektiviteten.

Följande steg visar hur det här problemet kan uppstå.

1. Börja att konfigurera ER-modellmappningskomponenten.
2. Lägg till en datakällan för typen **Dynamics 365 for Operations \\ tabellposter**.
3. Namnge den nya datakällan **Leverantör**. I fältet **Vabell** väljer du **VendTable** för att ange att denna datakälla ska begära tabellen VendTable.
4. Lägg till en datakälla för typen **Beräknat fält** för att hämta poster för flera leverantörer:
5. Namnge den nya datakällan **FilteredVendor** och konfigurera den så att den innehåller uttrycket `FILTER(Vendor, OR(Vendor.AccountNum="US-101",Vendor.AccountNum="US-102"))`.
6. Lägg till en datakälla för typen **Beräknat fält** för att hämta transaktioner för all filtrerade leverantörer:
7. Namnge den nya datakällan **FilteredVendorTrans** och konfigurera den så att den innehåller uttrycket `ALLITEMS(FilteredVendor.'<Relations'.'VendTrans.VendTable_AccountNum')`.
8. Välj **Validera** för att granska den redigerbara modellmappningskomponenten på sidan **Modellmappningsdesigner**.

    ![Inspektera den redigerbara modellmappningskomponenten på sidan Modellmappningsdesigner.](./media/er-components-inspections-08a.png)

9. Observera att en valideringsvarning uppstår. Det här meddelandet rekommenderar att du använder funktionen **ALLITEMSQUERY** i stället för funktionen **ALLITEMS** för datakällan **FilteredVendorTrans**.

    ![Rekommendation att använda ALLITEMSQUERY-funktionen istället för ALLITEMS-funktionen på sidan Modellmappningsdesigner.](./media/er-components-inspections-08b.png)

### <a name="automatic-resolution"></a>Automatisk lösning

Välj **Korrigera** för att automatiskt ersätta funktionen **ALLITEMS** med funktionen **ALLITEMSQUERY** i uttrycket för alla datakällor som visas i rutnätet på fliken **Varningar** för denna typ av granskning.

Alternativt kan du välja raden för en enskild varning i rutnätet och sedan välja **Korrigera valda**. I det här fallet ändras uttrycket automatiskt enbart i datakällan som nämns i den valda varningen.

![Välj Korrigera valda på sidan Modellmappningsdesigner.](./media/er-components-inspections-08c.png)

### <a name="manual-resolution"></a>Manuell lösning

Du kan manuellt justera uttrycken för alla datakällor som nämns i valideringsrutnätet genom att ersätta **ALLITEMS**-funktionen med **ALLITEMSQUERY**-funktionen.

## <a name="consideration-of-empty-list-cases"></a><a id="i9"></a>Hänsyn tas till tomma listärenden

Du kan konfigurera ditt ER-format eller den ER-modellmappningskomponent för att hämta fältvärdet för en datakälla av typen **Postlista**. ER kontrollerar om din design tar hänsyn till när en datakälla som har anropats inte innehåller några poster (dvs den är tom) för att förhindra körningsfel när ett värde hämtas från ett fält i en post som inte finns.

Följande steg visar hur det här problemet kan uppstå.

1. Börja konfigurera ER-datamodellen, ER-modellmappningen och ER-formatkomponenterna samtidigt.
2. Lägg till ett rotobjekt med namnet **Root3** i datamodellträdet.
3. Ändra **Root3**-objektet genom att lägga till ett kapslat objekt av typen **Postlista**.
4. Namnge det nya kapslade objektet **Leverantör**.
5. Ändra objektet **Leverantör** på följande sätt:

    - Lägg till ett kapslat fält av typen **Sträng** och ge det namnet **Namn**.
    - Lägg till ett kapslat fält av typen **Sträng** och ge det namnet **AccountNumber**.

    ![Lägga till kapslade fält på sidan Datamodell.](./media/er-components-inspections-09a.png)

6. I formgivaren för modellkartläggning, i typen **Datakällor** lägger du till en datakälla av typen **Dynamics 365 for Operations \\ tabellposter**.
7. Namnge den nya datakällan **Leverantör**. I fältet **Vabell** väljer du **VendTable** för att ange att denna datakälla ska begära tabellen VendTable.
8. Lägg till en datakälla för typen **Allmänt \\ Användarindataparametrar** för att söka efter ett leverantörskonto i körningsdialogen.
9. Namnge den nya datakällan **RequestedAccountNum**. I fältet **Etikett** anger du **Leverantörens kontonummer**. I fältet **Åtgärdens datatypnamn** lämnar du standardvärdet, **Beskrivning**.
10. Lägg till en datakälla för typen **Beräknat fält** för att filtrera en leverantör som det frågas om.
11. Namnge den nya datakällan **FilteredVendor** och konfigurera den så att den innehåller uttrycket `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
12. Bind datamodellobjekten till konfigurerade datakällor på följande sätt:

    - Bind **FilteredVendor** till **Leverantör**.
    - Bind **FilteredVendor.AccountNum** till **Vendor.AccountNumber**.
    - Bind **FilteredVendor.'name()'** till **Vendor.Name**.

    ![Binda datamodellartiklar på sidan Modellmappningsdesigner.](./media/er-components-inspections-09b.png)

13. I formatstrukturträdet lägger du till följande objekt för att skapa ett utgående dokument i XML-format som innehåller leverantörsinformation:

    1. Lägg till **Instruktion** rot-XML-element.
    2. För XML-elementet **Instruktion** lägger du till det XML-kapslade elementet **Part**.
    3. För XML-elementet **Part** lägger du till följande kapslade XML-attribut:

        - Namn
        - AccountNum

14. Bind formatelement till tillhandahållna datakällor på följande sätt:

    - Bind formatelementet **Instruktion\\Part\\Namn** till datakällfältet **model.Vendor.Name**.
    - Bind formatelementet **Instruktion\\Part\\AccountNum** till datakällfältet **model.Vendor.AccountNumber**.

15. Välj **Validera** för att granska den redigerbara formatkomponenten på sidan **Formatdesigner**.

    ![Validera formatelementen som du har bundit till datakällor på sidan Formatdesigner.](./media/er-components-inspections-09c.png)

16. Observera att ett valideringsfel uppstår. Meddelandet anger att det kan finnas ett fel för konfigurerade formatkomponenterna **Statement\\Party\\Name** och **Statement\\Party\\AccountNum** vid körning om listan `model.Vendor` är tom.

    ![Valideringsfel som meddelar eventuella fel på konfigurerade formatkomponenter.](./media/er-components-inspections-09d.png)

Följande bild visar det körningsfel som uppstår om du ignorerar varningen och väljer **Kör** för att köra formatet och väljer kontonummer för en leverantör som inte finns. Eftersom den begärda leverantören inte finns är listan `model.Vendor` tom (dvs den kommer inte att innehålla några poster).

![Körningsfel som uppstår när formatmappningen körs.](./media/er-components-inspections-09e.png)

### <a name="automatic-resolution"></a>Automatisk lösning

För den valda raden i rutnätet på fliken **Varningar** kan du välja **Avbind**. Bindningen som pekas på i kolumnen **Sökväg** tas automatiskt bort från formatelementen.

### <a name="manual-resolution"></a>Manuell lösning

#### <a name="option-1"></a>Alternativ 1

Du kan binda formatelementet **Statement\\Party\\Name** till datakällobjektet `model.Vendor`. Vid körning anropar den här bindningen datakällan `model.Vendor` först. När `model.Vendor` returnerar en tom postlista körs inte de kapslade formatelementen. Därför visas inga valideringsvarningar för den här formatkonfigurationen.

![Bind formatelementet till datakällsartikeln på sidan Formatdesigner.](./media/er-components-inspections-09e.gif)

#### <a name="option-2"></a>Alternativ 2

Ändra bindningen för formatelementet **Instruktion\\Part\\Namn** från `model.Vendor.Name` till `FIRSTORNULL(model.Vendor).Name`. Den uppdaterade bindningen konverterar villkorat den första posten i datakällan `model.Vendor` för typen **Postlista** till en ny datakälla för typen **Post**. Den nya datakällan innehåller samma uppsättning fält.

- Om minst en post är tillgänglig i datakällan `model.Vendor` fylls fälten i posten i med värdena för fälten i för första posten i datakällan `model.Vendor`. I det här fallet returnerar den uppdaterade bindningen leverantörsnamnet.
- I annat fall fylls alla fält i posten som skapas med standardvärdet för fältets datatyp. I det här fallet returneras den tomma strängen som standardvärde för datatypen **Sträng**.

Därför uppstår inga valideringsvarningar för formatelementet **Instruktion\\Part\\Namn** när det är bundet till uttrycket `FIRSTORNULL(model.Vendor).Name`.

![Ändrad bindning löser valideringsvarningar på sidan Formatdesigner.](./media/er-components-inspections-09f.gif)

#### <a name="option-3"></a>Alternativ 3

Om du uttryckligen vill ange de data som anges i ett genererat dokument när datakällan `model.Vendor` för typen **Postlista** returneras inga poster (texten **Inte tillgänglig** i exemplet), ändra bindningen för formatelementet **Statement\\Party\\Name** från `model.Vendor.Name` t `IF(NOT(ISEMPTY(model.Vendor)), model.Vendor.Name, "Not available")`. Du kan även använda uttrycket `IF(COUNT(model.Vendor)=0, model.Vendor.Name, "Not available")`.

### <a name="additional-consideration"></a><a id="i9a"></a>Ytterligare övervägande

Granskningen varnar också för ett annat potentiellt problem. Som standard, när du binder formatelementen **Statement\\Party\\Name** och **Statement\\Party\\AccountNum** till lämpliga fält i datakällan `model.Vendor` för typen **Postlista** kommer dessa bindningar att köras och använda värdena för lämpliga fält i första posten i datakällan `model.Vendor` om den listan inte är tom.

Eftersom du inte bundit formatelementet **Statement\\Party** med datakällan `model.Vendor` kommer inte elementet **Statement\\Party** att itereras för alla poster i datakällan `model.Vendor` under formatkörningen. I stället fylls ett genererat dokument med information från endast den första posten i postlistan, om listan innehåller flera poster. Därför kan det finnas ett problem om formatet är avsett att fylla ett genererat dokument med information om alla leverantörer från datakällan `model.Vendor`. Du löser det här problemet genom att binda elementet **Statement\\Party** till datakällan `model.Vendor`.

## <a name="executability-of-an-expression-with-filter-function-caching"></a><a id="i10"></a>Körbarhet för ett uttryck med funktionen FILTER (cachelagring)

Flera inbyggda ER-funktioner inklusive [FILTER](er-functions-list-filter.md) och [ALLITEMSQUERY](er-functions-list-allitemsquery.md) används för att komma åt programtabeller, vyer eller dataentiteter genom att ett enda SQL-anrop görs för att hämta de data som behövs i en postlista. En datakälla för typen **Postlista** används som argument för alla dessa funktioner och anger programkälla för anropet. ER kontrollerar om det går att upprätta ett direkt SQL-anrop till en datakälla som det refereras till i en av funktionerna. Om det inte går att upprätta ett direkt anrop eftersom datakällan är märkt som [cachelagrad](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace) uppstår ett valideringsfel i ER-modellmappningsdesignern. Meddelandet som du får anger att ER-uttrycket som innehåller en av dessa funktioner inte kan köras under körning.

Följande steg visar hur det här problemet kan uppstå.

1. Börja att konfigurera ER-modellmappningskomponenten.
2. Lägg till en datakällan för typen **Dynamics 365 for Operations \\ tabellposter**.
3. Namnge den nya datakällan **Leverantör**. I fältet **Vabell** väljer du **VendTable** för att ange att denna datakälla ska begära tabellen VendTable.
4. Lägg till en datakälla för typen **Allmänt \\ Användarindataparametrar** för att söka efter ett leverantörskonto i körningsdialogen.
5. Namnge den nya datakällan **RequestedAccountNum**. I fältet **Etikett** anger du **Leverantörens kontonummer**. I fältet **Åtgärdens datatypnamn** lämnar du standardvärdet, **Beskrivning**.
6. Lägg till en datakälla för typen **Beräknat fält** för att filtrera en leverantör som det frågas om.
7. Namnge den nya datakällan **FilteredVendor** och konfigurera den så att den innehåller uttrycket `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
8. Markera den konfigurerade datakällan **Leverantör** som cachelagrad.

    ![Konfigurera modellmappningskomponenten på sidan Modellmappningsdesigner.](./media/er-components-inspections-10a.gif)

9. Välj **Validera** för att granska den redigerbara modellmappningskomponenten på sidan **Modellmappningsdesigner**.

    ![Validera den FILTER-funktion som används för cacheminnets leverantörsdatakälla på sidan Modellmappningsdesigner.](./media/er-components-inspections-10a.png)

10. Observera att ett valideringsfel uppstår. Meddelandet anger att funktionen **FILTER** inte kan tillämpas på den cachelagrade datakällan **Leverantör**.

Följande bild visar det körningsfel som uppstår om du ignorerar varningen och väljer **Kör** för att köra formatet.

![Körningsfel som uppstår under formatmappningskörning på sidan Formatdesigner.](./media/er-components-inspections-10b.png)

### <a name="automatic-resolution"></a>Automatisk lösning

Det finns inget alternativ för automatisk korrigering av det här problemet.

### <a name="manual-resolution"></a>Manuell lösning

#### <a name="option-1"></a>Alternativ 1

Ta bort **Cache**-flaggan från datakällan **Leverantör**. Datakällan **FilteredVendor** blir då körbar, men datakällan **Leverantör** som refereras i VendTable-tabellen kommer att öppnas varje gång datakällan **FilteredVendor** anropas.

#### <a name="option-2"></a>Alternativ 2

Ändra uttrycket för datakällan **FilteredVendor** från `FILTER(Vendor, Vendor.AccountNum="US-101")` till `WHERE(Vendor, Vendor.AccountNum="US-101")`. I detta fall kommer datakällan **Leverantör** som det refereras till i VendTable-tabellen enbart att öppnas vid första anropet för datakällan **Leverantör**. Urvalet av poster kommer dock att göras i minnet. Därför kan den här metoden orsaka dålig prestanda.

## <a name="missing-binding"></a><a id="i11"></a>Bindning saknas

När du konfigurerar en ER-formatkomponent, erbjuds bas-ER-datamodellen som standard datakälla för ER-formatet. När det konfigurerade ER-formatet kör används [standard modellmappning](er-country-dependent-model-mapping.md) för basmodellen för att fylla datamodellen med programdata. I ER-formatdesignern visas en varning om du binder ett formatelement till ett datamodellobjekt som inte är bunden till någon datakälla i modellmappningen som för närvarande är vald som standardmodellmappning för det redigerbara formatet. Den här typen av bindning kan inte köras vid körning eftersom det format som körs inte kan fylla ett bundet element med programdata. Därför uppstår ett fel under körningen.

Följande steg visar hur det här problemet kan uppstå.

1. Börja konfigurera ER-datamodellen, ER-modellmappningen och ER-formatkomponenterna samtidigt.
2. Lägg till ett rotobjekt med namnet **Root3** i datamodellträdet.
3. Ändra objektet **Root3** genom att lägga till ett nytt kapslat objekt av typen **Postlista**.
4. Namnge det nya kapslade objektet **Leverantör**.
5. Ändra objektet **Leverantör** på följande sätt:

    - Lägg till ett kapslat fält av typen **Sträng** och ge det namnet **Namn**.
    - Lägg till ett kapslat fält av typen **Sträng** och ge det namnet **AccountNumber**.

    ![Lägga till kapslade fält i leverantörsartikeln på sidan Datamodell.](./media/er-components-inspections-11a.png)

6. I formgivaren för modellkartläggning, i typen **Datakällor** lägger du till en datakälla av typen **Dynamics 365 for Operations \\ tabellposter**.
7. Namnge den nya datakällan **Leverantör**. I fältet **Vabell** väljer du **VendTable** för att ange att denna datakälla ska begära tabellen VendTable.
8. Lägg till en datakälla av typen **Allmänt \\ Användarindataparametrar** för att fråga efter ett leverantörskonto i körningsdialogen.
9. Namnge den nya datakällan **RequestedAccountNum**. I fältet **Etikett** anger du **Leverantörens kontonummer**. I fältet **Åtgärdens datatypnamn** lämnar du standardvärdet, **Beskrivning**.
10. Lägg till en datakälla för typen **Beräknat fält** för att filtrera en leverantör som det frågas om.
11. Namnge den nya datakällan **FilteredVendor** och konfigurera den så att den innehåller uttrycket `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)`.
12. Bind datamodellobjekten till konfigurerade datakällor på följande sätt:

    - Bind **FilteredVendor** till **Leverantör**.
    - Bind **FilteredVendor.AccountNum** till **Vendor.AccountNumber**.

    > [!NOTE]
    > Datamodellfältet **Vendor.Name** förblir obundet.

    ![Datamodellsartiklar som är bundna till konfigurerade datakällor och en datalägesartikel som förblir obunden på sidan Modellmappningsdesigner.](./media/er-components-inspections-11b.png)

13. I formatstrukturträdet lägger du till följande objekt för att skapa ett utgående dokument i XML-format som innehåller information om leverantör som det frågas om:

    1. Lägg till **Instruktion** rot-XML-element.
    2. För XML-elementet **Instruktion** lägger du till det XML-kapslade elementet **Part**.
    3. För XML-elementet **Part** lägger du till följande kapslade XML-attribut:

        - Namn
        - AccountNum

14. Bind formatelementen till tillhandahållna datakällor på följande sätt:

    - Bind formatelementet **Statement\\Party** till datakällobjektet `model.Vendor`.
    - Bind formatelementet **Instruktion\\Part\\Namn** till datakällfältet **model.Vendor.Name**.
    - Bind formatelementet **Instruktion\\Part\\AccountNum** till datakällfältet **model.Vendor.AccountNumber**.

15. Välj **Validera** för att granska den redigerbara formatkomponenten på sidan **Formatdesigner**.

    ![Validera ER-formatkomponenten på sidan Formatdesigner.](./media/er-components-inspections-11c.png)

16. Observera att en valideringsvarning uppstår. Meddelandet anger att datakällfältet **model.Vendor.Name** inte är bundet till någon datakälla i modellmappningen som är konfigurerad för att användas av formatet. Därför kanske inte formatelementet **Instruktion\\Part\\Namn** fylls i vid körning och det inträffar ett körningsundantag.

    ![Validera ER-formatkomponenten på sidan Formatdesigner.](./media/er-components-inspections-11d.png)

Följande bild visar det körningsfel som uppstår om du ignorerar varningen och väljer **Kör** för att köra formatet.

![Köra det redigerbara formatet på sidan Formatdesigner.](./media/er-components-inspections-11e.png)

### <a name="automatic-resolution"></a>Automatisk lösning

Det finns inget alternativ för automatisk korrigering av det här problemet.

### <a name="manual-resolution"></a>Manuell lösning

#### <a name="option-1"></a>Alternativ 1

Ändra den konfigurerade modellmappningen genom att lägga till en bindning för datakällfältet **model.Vendor.Name**.

#### <a name="option-2"></a>Alternativ 2

Ändra det konfigurerade formatet genom att ta bort en bindning för formatelementet **Instruktion\\Part\\Namn**.

## <a name="not-linked-template"></a><a id="i12"></a>Mall som inte är länkad

När du konfigurerar en ER-formatkomponent [manuellt](er-fillable-excel.md#manual-entry) för att använda en mall för att generera ett utgående dokument, måste du manuellt lägga till elementet **Excel\\Fil**, lägga till mallen som krävs som bilaga till den redigerbara komponenten och välja bilagan i det tillagda elementet **Excel\\Fil**. På så sätt anger du att det tillagda elementet kommer att fylla i den markerade mallen under körning. När du konfigurerar en formatkomponentversion i **Utkast**-status kan du lägga till flera mallar i den redigerbara komponenten, och sedan välja varje mall i elementet **Excel\\Fil** för att köra ER-formatet. På så sätt kan du se hur olika mallar fylls i vid körning. Om du har mallar som inte är markerade i något **Excel\\Fil**-element, varnas du för att mallarna kommer att tas bort från versionen av den redigerbara ER-formatkomponenten när dess status ändras från **Utkast** till **Slutförd**.

Följande steg visar hur det här problemet kan uppstå.

1. Börja att konfigurera ER-formatkomponenten.
2. Lägg till elementet **Excel\\Fil** i formatstrukturträdet.
3. För elementet **Excel\\Fil** som du just har lagt till lägger du till en Excel-arbetsbokfil **A.xlsx** som bilaga. Använd dokumenttypen som konfigurerats i [ER-parametrarna](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) för att ange minne för ER-formatmallar.
4. För elementet **Excel\\Fil** lägger du till ytterligare en Excel-arbetsbokfil **B.xlsx** som bilaga. Använd samma dokumenttyp som används för arbetsbokfilen A.
5. I elementet **Excel\\Fil** väljer du arbetsbokfil A.
6. Välj **Validera** för att granska den redigerbara formatkomponenten på sidan **Formatdesigner**.

    ![Validera den redigerbara formatkomponenten i arbetsbokfilen på sidan Formatdesigner.](./media/er-components-inspections-12a.gif)

7. Observera att en valideringsvarning uppstår. Meddelandet anger att arbetsbokfilen B.xlsx inte är länkad till några komponenter och att den tas bort när status för konfigurationsversionen har ändrats.

### <a name="automatic-resolution"></a>Automatisk lösning

Det finns inget alternativ för automatisk korrigering av det här problemet.

### <a name="manual-resolution"></a>Manuell lösning

Ändra det konfigurerade formatet genom att ta bort alla mallar som inte är länkade till något **Excel\\Fil**-element.

## <a name="not-synced-format"></a><a id="i13"></a>Inte synkroniserat format

När du [konfigurerar](er-fillable-excel.md) en ER-formatkomponent manuellt för att använda en Excel-mall för att generera ett utgående dokument, kan du manuellt lägga till elementet **Excel\\Fil**, lägga till mallen som krävs som bilaga till den redigerbara komponenten och välja bilagan i det tillagda elementet **Excel\\Fil**. På så sätt anger du att det tillagda elementet kommer att fylla i den markerade mallen under körning. Eftersom den tillagda Excel-mallen är externt utformad kan det redigerbara ER-formatet innehålla Excel-namn som saknas i mallen som har lagts till. I ER-formatdesignern varnas du för eventuell inkonsekvens mellan egenskaperna hos egenskaperna för ER-formatelement som refererar till namn som inte finns i den tillagda Excel-mallen.

Följande steg visar hur det här problemet kan uppstå.

1. Börja att konfigurera ER-formatkomponenten.
2. Lägg till elementet **Rapport** från **Excel\\Fil** i formatstrukturträdet.
3. För elementet **Excel\\Fil** som du just har lagt till lägger du till en Excel-arbetsbokfil **A.xlsx** som bilaga. Använd dokumenttypen som konfigurerats i [ER-parametrarna](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) för att ange minne för ER-formatmallar.

    > [!IMPORTANT]
    > Kontrollera att den tillagda Excel-arbetsboken inte innehåller namnet **ReportTitle**.

4. Lägg till **Excel\\Cell**-elementet **Titel** som kapslat element för elementet **Rapport**. I fältet **Excel-intervall** anger du **ReportTitle**.
5. Välj **Validera** för att granska den redigerbara formatkomponenten på sidan **Formatdesigner**.

    ![Validera kapslade element och fält på sidan Formatdesigner.](./media/er-components-inspections-13a.png)

6. Observera att en valideringsvarning uppstår. Meddelandet anger att namnet **ReportTitle** inte finns i arket **Blad1** i den Excel-mall du använder.

    ![Valideringsvarning att namnet ReportTitle inte finns på Flik1 i Excel-mallen.](./media/er-components-inspections-13b.png)

### <a name="automatic-resolution"></a>Automatisk lösning

Det finns inget alternativ för automatisk korrigering av det här problemet.

### <a name="manual-resolution"></a>Manuell lösning

#### <a name="option-1"></a>Alternativ 1

Ändra det konfigurerade formatet genom att ta bort alla element som refererar till Excel-namn som saknas i mallen.

#### <a name="option-2"></a>Alternativ 2

[Uppdatera](er-fillable-excel.md#template-import) det redigerbara ER-formatet genom att importera en Excel-mall. Strukturen för det redigerbara ER-formatet [synkroniseras](modify-electronic-reporting-format-reapply-excel-template.md) med strukturen i den importerade ER-mallen.

### <a name="additional-consideration"></a>Ytterligare övervägande

Information om hur formatstrukturen kan synkroniseras med en ER-mall i mallredigeraren i [Hantering av affärsdokument](er-business-document-management.md) finns i [Uppdatera strukturen för en affärsdokumentmall](er-bdm-update-structure.md).

## <a name="not-synced-with-a-word-template-format"></a><a id="i14"></a>Inte synkroniserat med ett Word-mallformat

När du [konfigurerar](er-fillable-excel.md) en ER-formatkomponent manuellt för att använda en Word-mall för att generera ett utgående dokument, kan du manuellt lägga till elementet **Excel\\Fil**, lägga till Word-mallen som krävs som bilaga till den redigerbara komponenten och välja bilagan i det tillagda elementet **Excel\\Fil**.

> [!NOTE]
> När Word-dokumentet bifogas presenterar ER-formatdesignern det redigerbara elementet som **Word\\Fil**.

På så sätt anger du att det tillagda elementet kommer att fylla i den markerade mallen under körning. Eftersom den tillagda Word-mallen är externt utformad kan det redigerbara ER-formatet innehålla referenser till Word-innehållskontroller som saknas i den tillagda mallen. I ER-formatdesignern varnas du för eventuell inkonsekvens mellan egenskaperna hos egenskaperna för ER-formatelement som refererar till innehållskontroll som inte finns i den tillagda Word-mallen.

För ett exempel som visar hur problemet kan uppstå, se [Konfigurera det redigerbara formatet för att undertrycka sammanfattningsavsnittet](er-design-configuration-word-suppress-controls.md#configure-to-suppress-control).

### <a name="automatic-resolution"></a>Automatisk lösning

Det finns inget alternativ för automatisk korrigering av det här problemet.

### <a name="manual-resolution"></a>Manuell lösning

#### <a name="option-1"></a>Alternativ 1

Ändra det konfigurerade formatet genom att radera formeln **Ta bort** från formatelementet som nämns i valideringsvarningen.

#### <a name="option-2"></a>Alternativ 2

Ändra den använda Word-mallen med [lägg till](er-design-configuration-word-suppress-controls.md#tag-control) önskad tagg till relevant Word-innehållskontroll.

## <a name="no-default-mapping"></a><a id="i15"></a>Ingen standardmappning

När [Bindning saknas](#i11) inspektion görs, utvärderas de inspekterade formatbindningarna mot bindningarna för den relevanta modellmappningskomponenten. Eftersom du kan importera [flera](./tasks/er-manage-model-mapping-configurations-july-2017.md) ER-mappningskonfigurationer för din Finance-instans och varje konfiguration kan innehålla tillämplig modellmappningskomponent. En konfiguration måste väljas som standardkonfiguration. Annars, när du försöker köra, redigera eller validera det inspekterade ER-formatet, kommer ett undantag att inträffa och du får följande meddelande: "Mer än en modellmappning finns för \<model name (root descriptor)\> datamodell i konfigurationerna \<configuration names separated by comma\>. Ställ in en av konfigurationerna som standard."

Ett exempel på hur det här problemet kan uppstå och hur det kan åtgärdas finns i [Hantera flera härledda mappningar för en enskild modellrot](er-multiple-model-mappings.md).

## <a name="inconsistent-setting-of-header-or-footer-components"></a><a id="i16"></a>Inkonsekvent inställning av komponenter för sidhuvud eller sidfot

När du [konfigurerar](er-fillable-excel.md) en ER-formatkomponent till att använda en Excel-mall för att generera ett utgående dokument, kan du lägga till **Excel\\Rubrik** komponent för att fylla i rubriker högst upp på ett kalkylblad i en Excel-arbetsbok. Du kan också lägga till **Excel\\Sidfot** komponent för att fylla i sidfot längst ner på ett kalkylblad. För varje **Excel\\Sidhuvud** eller **Excel\\Sidfot** komponent som du lägger till måste du ställa in egenskapen **Sidhuvud/Sidfot utseende** för att specificera de sidor som komponenten körs för. Eftersom du kan konfigurera flera komponenter för **Excel\\Sidhuvud** eller **Excel\\Sidfot** för en **Ark** komponent och du kan skapa olika sidhuvuden eller sidfot för olika typer av sidor i ett Excel-kalkylblad, måste du konfigurera en enda **Excel\\Sidhuvud** eller **Excel\\Sidfot** komponent för ett specifikt värde för egenskapen **Sidhuvud/sidfot utseende**. Om mer än en **Excel\\Sidhuvud** eller **Excel\\Sidfot** komponenten är konfigurerad för ett specifikt värde av egenskapen **Sidhuvud/Sidfot utseende** ett valideringsfel uppstår och du får följande felmeddelande: "Sidhuvud/Sidfot (&lt;komponenttyp: Sidhuvud eller Sidfot&gt;) är inkonsekvent."

### <a name="automatic-resolution"></a>Automatisk lösning

Det finns inget alternativ för automatisk korrigering av det här problemet.

### <a name="manual-resolution"></a>Manuell lösning

#### <a name="option-1"></a>Alternativ 1

Ändra det konfigurerade formatet genom att ta bort en av de inkonsekventa komponenterna **Excel\\Sidhuvud** eller **Excel\\Sidfot**.

#### <a name="option-2"></a>Alternativ 2

Ändra värdet på egenskapen för **Sidhuvud/Sidfot utseende** för någon av de inkonsekventa komponenterna **Excel\\Sidhuvud** eller **Excel\\Sidfot**.

## <a name="inconsistent-setting-of-page-component"></a><a id="i17"></a>Inkonsekvent inställning av sidkomponent

När du [konfigurerar](er-fillable-excel.md) en ER-formatkomponent för att använda en Excel-mall för att generera ett utgående dokument, kan du lägga till **Excel\\Sid**-komponent i sidnumrering av ett genererat dokument med hjälp av ER-formler. För varje **Excel\\sid**-komponent som du lägger till kan du lägga till många kapslade intervallkomponenter och fortfarande vara [intervall](er-fillable-excel.md#range-component)-komponenter och fortfarande vara kompatibel med följande [struktur](er-fillable-excel.md#page-component-structure):

- Den första kapslade **intervall**-komponenten kan konfigureras så att egenskapen **Replikeringsriktning** ställs in på **Ingen replikering**. Detta intervall används för att skapa sidrubriker i genererade dokument.
- Du kan lägga till många andra kapslade **intervall** komponenter där egenskapen **Replikeringsriktning** är inställd på **Lodrät**. De här intervallen används för att fylla i genererade dokument.
- Den sista kapslade **intervall**-komponenten kan konfigureras så att egenskapen **Replikeringsriktning** ställs in på **Ingen replikering**. Det här intervallet används för att skapa sidfot i genererade dokument och för att lägga till sidbrytningar.

Om du inte följer den här strukturen för ett ER-format i ER-formatdesignern vid designtid, inträffar ett valideringsfel och följande felmeddelande visas: "Det finns fler än två intervallkomponenter utan replikering. Ta bort onödiga komponenter.

### <a name="automatic-resolution"></a>Automatisk lösning

Det finns inget alternativ för automatisk korrigering av det här problemet.

### <a name="manual-resolution"></a>Manuell lösning

#### <a name="option-1"></a>Alternativ 1

Ändra det konfigurerade formatet genom att ändra egenskapen för **Replikeringsriktning** för alla inkonsekventa **Excel\\intervall**-komponenter.

## <a name="executability-of-an-expression-with-orderby-function"></a><a id="i18"></a>Körbarhet för ett uttryck med funktionen ORDERBY

Den inbyggda [ORDERBY](er-functions-list-orderby.md) ER-funktionen används för att sortera posterna för en ER-datakälla av typen **[Postlista](er-formula-supported-data-types-composite.md#record-list)** som angetts som ett argument för funktionen.

Argument för funktionen `ORDERBY` kan [anges](er-functions-list-orderby.md#syntax-2) för att sortera poster över apptabeller, vyer eller dataenheter genom att göra ett enda databasanrop för att få sorterad data som en lista med poster. En datakälla för typen **Postlista** används som argument för den här funktionen och anger programkällan för anropet.

ER kontrollerar om det går att upprätta en direkt databasfråga till en datakälla som det refereras till i `ORDERBY`-funktionen. Om det inte går att upprätta en direkt fråga, uppstår ett valideringsfel i ER-modellmappningsdesignern. Meddelandet som du tar emot anger att ER-uttrycket som innehåller `ORDERBY`-funktionen inte kan köras under körning.

Följande steg visar hur det här problemet kan uppstå.

1. Börja att konfigurera ER-modellmappningskomponenten.
2. Lägg till en datakällan för typen **Dynamics 365 for Operations \\ tabellposter**.
3. Namnge den nya datakällan **Leverantör**. I fältet **Tabell** väljer du **VendTable** för att ange att denna datakälla ska begära tabellen **VendTable**.
4. Lägg till en datakälla för typen **Beräknat fält**.
5. Namnge den nya datakällan **OrderedVendors** och konfigurera den så att den innehåller uttrycket `ORDERBY("Query", Vendor, Vendor.AccountNum)`.
 
    ![Konfigurera datakällan på sidan Modellmappningsdesigner.](./media/er-components-inspections-18-1.png)

6. Välj **Validera** för att granska den redigerbara modellmappningskomponenten på sidan **Modellmappningsdesigner** och kontrollera att uttrycket i datakällan **OrderedVendors** kan läsas.
7. Ändra datakällan **Levarantör** genom att lägga till ett kapslat fält av typen **Beräknat fält** för att hämta det trimmade leverantörskontonumret.
8. Namnge det nya kapslade fältet **$AccNumber** och konfigurera det så att det innehåller uttrycket `TRIM(Vendor.AccountNum)`.
9. Välj **Validera** för att granska den redigerbara modellmappningskomponenten på sidan **Modellmappningsdesigner** och kontrollera att uttrycket i datakällan **Leverantör** kan läsas.

    ![Verifiering av uttrycket i datakällan Leverantör kan sökas på sidan Modellmappningsdesigner.](./media/er-components-inspections-18-2.png)

10. Observera att ett valideringsfel inträffar eftersom datakällan **Leverantör** innehåller ett kapslat fält av typen **Beräknat fält** som inte tillåter att uttrycket för datakällan **OrderedVendors** översätts till den direkta databasinstruktionen. Samma fel inträffar vid körning om du ignorerar valideringsfelet och väljer **Kör** för att köra den här modellmappningen.

### <a name="automatic-resolution"></a>Automatisk lösning

Det finns inget alternativ för automatisk korrigering av det här problemet.

### <a name="manual-resolution"></a>Manuell lösning

#### <a name="option-1"></a>Alternativ 1

I stället för att lägga till ett kapslat fält av typen **Beräknat fält** i datakällan **Leverantör**, lägger du till det kapslade fältet **$AccNumber** i datakällan **FilteredVendors** och konfigurerar fältet så att det innehåller uttrycket `TRIM(FilteredVendor.AccountNum)`. På så sätt kan uttrycket `ORDERBY("Query", Vendor, Vendor.AccountNum)` köras på databasnivå och beräkningen av det kapslade fältet **$AccNumber** kan göras efteråt.

#### <a name="option-2"></a>Alternativ 2

Ändra uttrycket för datakällan **FilteredVendors** från `ORDERBY("Query", Vendor, Vendor.AccountNum)` till `ORDERBY("InMemory", Vendor, Vendor.AccountNum)`. Vi rekommenderar inte att du ändrar uttrycket för en tabell som har en stor mängd data (transaktionstabell) eftersom alla poster hämtas och beställning av de nödvändiga poster som krävs görs i minnet. Därför kan den här metoden orsaka dålig prestanda.

## <a name="obsolete-application-artifact"></a><a id="i19"></a>Föråldrade program artefakter

När du designar en ER-modellmappningskomponent eller en ER-formatkomponent kan du konfigurera ett ER-uttryck för att anropa en program artefakt i ER, till exempel ett databasregister, en klassmetod osv. I ekonomiversion 10.0.30 och senare kan du tvinga ER att varna dig om att den refererade program artefakten har markerats i källkoden som föråldrad. Varningen kan vara praktisk eftersom gamla artefakter vanligtvis tas bort automatiskt från källkoden. Om du får information om en artefakts status kan du sluta använda den föråldrade artefakten i den redigerbara ER-komponenten innan den tas bort från källkoden, vilket förhindrar fel vid anrop av icke-existerande program artefakter från en ER-komponent när den körs.

Aktivera funktionen **Validera föråldrade element i elektroniska rapporteringsdatakällor** i arbetsytan för **funktionshantering** så att du kan börja utvärdera det föråldrade attributet för program artefakter under inspektionen av en redigerbar ER-komponent. Det föråldrade attributet utvärderas för närvarande för följande typer av program artefakter:

- Databastabell
    - Fält för tabell
    - Metod för tabell
- Appklass
    - Metod för klass

> [!NOTE]
> En varning inträffar under inspektionen av den redigerbara ER-komponenten för en datakälla som endast refererar till en föråldrad artefakt om denna datakälla används i minst en bindande av den här ER-komponenten.

> [!TIP]
> När klassen [SysObsoleteAttribute](../dev-ref/xpp-attribute-classes.md#sysobsoleteattribute) används för att meddela kompilatorn att utfärda varningsmeddelanden istället för fel, inspektionsvarningen presenterar den specificerade varningen i källkoden vid designtidpunkten i **Detaljer** på sidan **Modellmappningsdesigner** eller **Formatdesigner**.

I följande bild visas en valideringsvarning som inträffar när det föråldrade fältet `DEL_Email` i programregistret `CompanyInfo` är bundet till ett datamodellfält med hjälp av den konfigurerade `company` datakällan.

![Granska valideringsvarningarna i snabbfliken Detaljer på sidan Modellmappningsdesigner.](./media/er-components-inspections-19a.png)

### <a name="automatic-resolution"></a>Automatisk lösning

Det finns inget alternativ för automatisk korrigering av det här problemet.

### <a name="manual-resolution"></a>Manuell lösning

Ändra den konfigurerade modellmappningen eller -formatet genom att ta bort alla bindande uppgifter till en datakälla som refererar till en föråldrad program artefakt.

## <a name="additional-resources"></a>Ytterligare resurser

[ALLITEMS ER-funktionen](er-functions-list-allitems.md)

[ALLITEMSQUERY ER-funktionen](er-functions-list-allitemsquery.md)

[INT64VALUE ER-funktion](er-functions-conversion-int64value.md)

[INTVALUE ER-funktion](er-functions-conversion-intvalue.md)

[FILTER ER-funktion](er-functions-list-filter.md)

[WHERE ER-funktionen](er-functions-list-where.md)

[Använd JOIN datakällor i ER-modellmappningar för att hämta data från flera programtabeller](er-join-data-sources.md)

[Spåra körningen av ER-format för att felsöka prestandaproblem](trace-execution-er-troubleshoot-perf.md)

[Hantering av affärsdokument – översikt](er-business-document-management.md)

[Ignorera Word-innehållskontroller i genererade rapporter](er-design-configuration-word-suppress-controls.md)

[Hantera flera härledda mappningar för en enskild modellrot](er-multiple-model-mappings.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
