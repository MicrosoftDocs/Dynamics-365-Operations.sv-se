---
title: Skapa en konfiguration för att generera dokument i Excel-format
description: Den här artikeln beskriver hur du utformar ett elektroniskt rapporteringsformat (ER) för att fylla i en Excel-mall och sedan generera utgående dokument i Excelformat.
author: NickSelin
ms.date: 05/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4660aaf438ee091eed30387d984746ac2c3b4bd7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854826"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a>Skapa en konfiguration för att generera dokument i Excel-format

[!include[banner](../includes/banner.md)]

Du kan utforma en formatkonfiguration [elektronisk rapportering (ER)](general-electronic-reporting.md) som har en ER-formatkomponent som du kan konfigurera för att generera ett utgående dokument i ett Microsoft Excel arbetsboksformat. Specifika komponenter i ER-format måste användas för detta syfte.

Om du vill veta mer om den här funktionen följer du stegen i avsnittet [utforma en konfiguration för generering av rapporter i OPENXML-format](tasks/er-design-reports-openxml-2016-11.md).

## <a name="add-a-new-er-format"></a>Lägg till ett nytt ER-format

När du lägger till en ny konfiguration för ER-format i syfte att generera ett utgående dokument i ett Excel-format, måste du antingen välja **Excel**-värdet för attributet **Formattyp** för formatet eller lämna attributet **Formattyp** tomt.

- Om du väljer **Excel** kan du konfigurera formatet så att ett utgående dokument endast skapas i Excel-format.
- Om du lämnar attributet tomt kan du konfigurera formatet så att ett utgående dokument skapas i ett format som stöds av ER-ramverket.

Om du vill konfigurera ER-formatkomponenten för konfigurationen väljer du **Designer** i åtgärdsfönstret och öppnar ER-formatkomponenten för redigering i ER-åtgärdersdesignern.

![Sidan Konfigurationer.](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a>Excel-filkomponent

### <a name="manual-entry"></a>Manuell registrering

Du måste lägga till en **Excel\\fil**-komponent i det konfigurerade ER-formatet för att kunna generera ett utgående dokument i Excel-format.

![Excel-\filkomponent.](./media/er-excel-format-add-file-component.png)

Om du vill ange layouten för det utgående dokumentet bifogar du en Excel-arbetsbok med tillägget .xlsx till komponenten **Excel\\fil** som mall för utgående dokument.

> [!NOTE]
> När du bifogar en mall manuellt måste du använda en [dokumenttyp](../../../fin-ops-core/fin-ops/organization-administration/configure-document-management.md#configure-document-types) som har konfigurerats för detta syfte i [ER-parametrarna](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

![Lägga till en bilaga i Excel\fil-komponenten.](./media/er-excel-format-add-file-component2.png)

Om du vill ange hur den bifogade mallen ska fyllas i när du kör det konfigurerade ER-formatet måste du lägga till kapslade **Ark-**, **Intervall-** och **Cell-** komponenter i **Excel\\fil**-komponenten. Varje kapslad komponent måste associeras med ett namngivet Excel-objekt.

### <a name="template-import"></a>Mallimport

Du kan välja **Importera från Excel** på fliken **Importera** i åtgärds fönstret för att importera en ny mall till ett tomt ER-format. I det här exemplet skapas en **Excel\\-fil** komponent automatiskt, och den importerade mallen kopplas till den. Alla obligatoriska ER-komponenter skapas också automatiskt, baserat på listan med Excel-objekt som upptäcks.

![Välja Importera från Excel.](./media/er-excel-format-import-template.png)

> [!NOTE]
> Om du vill skapa det valfria **Ark**-elementet i det redigerbara ER-formatet ställer du in alternativet **Skapa formatelement för Excel-ark** som **Ja**.

## <a name="sheet-component"></a>Ark-komponent

Komponenten **Ark** anger ett kalkylblad tillhörande den bifogade Excel-arbetsbok som måste fyllas i. Namnet på kalkylbladet i en Excel-mall definieras i egenskapen **Ark** för den här komponenten.

> [!NOTE]
> Denna komponent är valfri för Excel-arbetsböcker som innehåller ett enda kalkylblad.

På fliken **Mappning** i ER-åtgärdsdesignern kan du konfigurera egenskapen **Aktiverad** för en **ark**-komponent i syfte att ange om komponenten ska placeras i ett genererat dokument:

- Om ett uttryck för egenskapen **Aktiverad** har konfigurerats att returnera **True** vid körning, eller om inget uttryck har konfigurerats alls, infogas lämpligt kalkylblad i det genererade dokumentet.
- Om ett uttryck för egenskapen **Aktiverad** har konfigurerATS att returnera **False** vid körning kommer det genererade dokumentet inte att innehålla något kalkylblad.

![Exempel på en ark-komponent.](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a>Intervall-komponent

### <a name="nested-components"></a>Kapslade komponenter

#### <a name="data-typing"></a>Datatyper

**Intervall**-komponenten kan ha andra kapslade ER-komponenter som används för att ange värden i lämpliga intervall.

- Om en komponent i **Text**-gruppen används för att ange värden, anges värdet i ett Excel-intervall som ett textvärde.

    > [!NOTE]
    > Använd det här mönstret om du vill formatera angivna värden baserat på de språk som har definierats i programmet.

- Om komponenten **Cell** för gruppen **Excel** används för att ange värden, så anges värdet i ett Excel-intervall som ett värde för den datatyp som definieras av bindningen för den **Cell**-komponenten. Datatypen kan till exempel vara **Sträng**, **Verklig** eller **Heltal**.

    > [!NOTE]
    > Använd det här mönstret om du vill göra det möjligt för Excel-programmet att formatera angivna värden baserat på språkinställningen för den lokala dator som öppnar det utgående dokumentet.

#### <a name="row-handling"></a>Radhantering

Komponenten **Intervall** kan konfigureras som lodrätt replikerad så att flera rader genereras i ett Excel-kalkylblad. Raderna kan genereras av den överordnade **Intervall**-komponenten eller av dess kapslade **Intervall**-komponenter.

I version 10.0.26 och senare kan du tvinga fram ett genererat kalkylblad för att behålla de genererade raderna på samma sida. Ange alternativet **Behåll rader tillsammans** i ER-formatdesignern som **Ja** för överordnad **Intervall**-komponent i det redigerbara ER-formatet. ER försöker sedan att behålla allt innehåll som genereras av intervallet på samma sida. Om innehållets höjd överstiger det återstående utrymmet på den aktuella sidan läggs en sidbrytning till, och innehållet börjar högst upp på nästa nya sida.

> [!NOTE]
> Vi rekommenderar att du bara konfigurerar alternativet **Behåll rader tillsammans** för intervall som sträcker sig över hela bredden i ett genererat dokument.
>
> Alternativet **Behåll rader tillsammans** kan endast användas för **Excel \> Fil**-komponenter som är konfigurerade att använda en Excel-arbetsboksmall.
>
> Alternativet **Håll ihop rader** fungerar bara när funktionen **Aktivera användning av EPPlus-biblioteket i ramverksfunktionen för elektronisk rapportering** är aktiverad.
>
> Den här funktionen kan användas för **intervallkomponenter** som finns under komponenten **Sida**. Det finns emellertid inga garantier för att [sidfotssummor](er-paginate-excel-reports.md#add-data-sources-to-calculate-page-footer-totals) beräknas korrekt med hjälp av datakällor för [datainsamling](er-data-collection-data-sources.md).

Om du vill lära dig använda detta alternativ följer du exempelstegen i [Designa ett ER-format för att hålla ihop rader på samma Excel-sida](er-keep-excel-rows-together.md).

### <a name="replication"></a>Replikering

Egenskapen **Replikeringsriktning** anger huruvida samt hur ett intervall kommer att upprepas i ett genererat dokument:

- **Ingen replikering** – Lämpligt Excel-intervall upprepas inte i det genererade dokumentet.
- **Vertikalt** – Lämpligt Excel-intervall upprepas vertikalt i det genererade dokumentet. Varje replikerat intervall kommer att placeras under det ursprungliga intervallet i en Excel-mall. Antalet upprepningar definieras av antalet poster i en data källa för den typ av **Postlista** som är bunden till den här ER-komponenten.
- **Horisontellt** – Lämpligt Excel-intervall upprepas horisontellt i det genererade dokumentet. Varje replikerat intervall kommer att placeras till höger om det ursprungliga intervallet i en Excel-mall. Antalet upprepningar definieras av antalet poster i en data källa för den typ av **Postlista** som är bunden till den här ER-komponenten.

    Om du vill veta mer om vågrät replikering följer du stegen i [Använd vågrätt expanderbara intervall för att dynamiskt lägga till kolumner i Excel-rapporter](tasks/er-horizontal-1.md).

### <a name="enabling"></a>Aktiverar

På fliken **Mappning** i ER-åtgärdsdesignern kan du konfigurera egenskapen **Aktiverad** för en **Intervall**-komponent i syfte att ange om komponenten ska placeras i ett genererat dokument:

- Om ett uttryck för egenskapen **Aktiverad** har konfigurerats att returnera **True** vid körning, eller om inget uttryck har konfigurerats alls, ifylles lämpligt intervall i det genererade dokumentet.
- Om ett uttryck för egenskapen **Aktiverad** har konfigurerats att returnera **False** vid körning, och om detta intervall inte representerar hela raderna eller kolumnerna, kommer lämpligt intervall inte att ifyllas i det genererade dokumentet.
- Om ett uttryck för egenskapen **Aktiverad** har konfigurerats att returnera **False** vid körning, och om detta intervall representerar hela raderna eller kolumnerna, kommer det genererade dokumentet att omfatta dessa rader och kolumner som dolda radera och kolumner.

### <a name="resizing"></a>Ändra storlek

Du kan konfigurera din Excel-mall till att använda celler för att presentera textdata. Om du vill vara säker på att hela texten i en cell blir synlig i ett genererat dokument kan du konfigurera den cellen att automatiskt radbryta texten i den. Du kan även konfigurera raden som innehåller cellen att automatiskt justera dess höjd om den radbrutna texten inte är fullt synlig. Mer information finns i avsnittet "Radbryt text i en cell" i [Korrigera data som är avklippt i celler](https://support.microsoft.com/office/fix-data-that-is-cut-off-in-cells-e996e213-6514-49d8-b82a-2721cef6144e).

> [!NOTE]
> En känd [Excel-begränsning](https://support.microsoft.com/topic/you-cannot-use-the-autofit-feature-for-rows-or-columns-that-contain-merged-cells-in-excel-34b54dd7-9bfc-6c8f-5ee3-2715d7db4353) gör att du – även om du konfigurerar celler att radbryta text, samt konfigurerar de rader som innehåller dessa celler att automatiskt höjdjusteras i syfte att rymma den radbrutna texten – kanske inte kan använda Excel-funktionerna **Autopassa** och **Radbrytning** för sammanfogade celler och de rader som innehåller dem. 

Från och med Dynamics 365 Finance-version 10.0.23, när du arbetar i ett genererat dokument, kan du tvinga ER att beräkna höjden för varje enskild rad som konfigurerats att automatiskt höjdanpassas efter innehållet i kapslade celler närhelst den raden innehåller minst en sammanfogad cell som konfigurerats att radbryta den text som finns i densamma. Den beräknade höjden används sedan för att ändra storleken på raden för att säkerställa att alla celler i raden är synliga i det genererade dokumentet.

> [!NOTE]
> Tänk på att funktionen inte fungerar som förväntat när ett anpassat teckensnitt används för att formatera en sammanfogade cell. Eftersom Excel inte erbjuder anpassade teckensnitt behöver det inte innehålla information om anpassad teckenstorlek. Därför kan storleken på den sammanfogade cellen uppskattas på fel sätt.

Följ dessa steg om du vill börja använda den här funktionen när du kör eventuella ER-format som konfigurerats för att använda Excel-mallar för att generera utgående dokument.

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **parametrar för elektronisk rapportering**.
3. På sidan **Parametrar för elektronisk rapportering**, på fliken **Körning**, anger du alternativet **Anpassa radhöjd automatiskt** som **Ja**.

När du vill ändra den här regeln för ett enda ER-format uppdaterar du utkastversionen av det formatet genom att följa stegen nedan.

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **Lokaliseringskonfiguration** i avsnittet **Konfigurationer** väljer du **Rapporteringskonfiguration**.
3. Ppå sidan **Konfigurationer**, i konfigurationsträdet i vänstra fönstret, väljer du en ER_konfiguration som utformats för att använda en Excel-mall i syfte att generera utgående dokument.
4. På snabbfliken **Versioner** väljer du den konfigurationsversion som har statusen **Utkast**.
5. Klicka på **Designer** i åtgärdsfönstret.
6. I formatträdet i vänstra fönstret på sidan **Formatdesigner** väljer du den Excel-komponent som kopplats till en Excel-mall.
7. På fliken **Format**, i fältet **Justera radhöjd**, väljer du ett värde för att ange huruvida ER ska framtvingas vid körning i syfte att ändra höjden på rader i ett utgående dokument som genererats av det redigerade ER-formatet:

    - **Standard** – Använd den allmänna inställningen som är konfigurerad i fältet **Automatisk anpassning av radhöjd** på sidan **Parametrar för elektronisk rapportering**.
    - **Ja** – Åsidosätt den allmänna inställningen och ändra radhöjden vid körning.
    - **Nej** – Åsidosätt den allmänna inställningen och ändra inte radhöjden vid körning.

## <a name="cell-component"></a>Cellkomponent

**Cell**-komponenten används för att fylla i Excel-betitlade celler, figurer och bilder. Om du vill ange ett Excel-namngivet objekt som måste fyllas i av en ER-komponent för en **Cell**, måste du ange namnet på objektet i egenskapen **Excel-intervall** för komponenten **Cell**.

På fliken **Mappning** i ER-åtgärdsdesignern kan du konfigurera egenskapen **Aktiverad** för en **Cell**-komponent i syfte att ange om objektet måste ifyllas i ett genererat dokument:

- Om ett uttryck för egenskapen **Aktiverad** har konfigurerats att returnera **True** vid körning, eller om inget uttryck har konfigurerats alls, ifylles lämpligt objekt i det genererade dokumentet. Bindningen för denna **cell**-komponent anger ett värde som placeras i lämpligt objekt.
- Om ett uttryck för egenskapen **Aktiverad** konfigureras i syfte att returnera **False** vid körning, kommer lämpligt objekt inte att ifyllas i det genererade dokumentet.

När en **cell**-komponent konfigureras för att ange ett värde i en cell, kan den bindas till en datakälla som returnerar värdet för en primitiv datatyp (t.ex. **sträng**, **verklig** eller **heltal**). I det här fallet anges värdet i cellen som ett värde av samma datatyp.

När en **cell**-komponent konfigureras för att ange ett värde i en Excel-figur kan den bindas till en datakälla som returnerar ett värde för en primitiv datatyp (t.ex. **sträng**, **verklig** eller **heltal**). I det här fallet anges värdet i Excel-figuren som figurens text. För värden med datatyper som inte är **strängar** sker konverteringen till text automatiskt.

> [!NOTE]
> Du kan konfigurera en **cell**-komponent så att den fyller i en form endast om en formegenskap för text stöds.

När en **Cell**-komponent konfigureras för att ange ett värde i Excel-bild kan den bindas till en datakälla som returnerar ett värde av datatypen **Behållare** som representerar en bild i ett binärt format. I det här fallet anges värdet i Excel-bilden som en bild.

> [!NOTE]
> Alla Excel-bilder och -former betraktas som förankrade med sitt övre vänstra hörn till en viss Excel-cell eller ett visst Excel-intervall. Om du vill replikera en Excel-bild eller -form måste du konfigurera cellen eller intervallet som den är fäst till som en replikerad cell eller ett intervall.

Mer information om hur du bäddar in bilder och former finns i [Bädda in bilder och former i dokument som du skapar med hjälp av ER](electronic-reporting-embed-images-shapes.md).

## <a name="page-break-component"></a>Komponenten PageBreak

Komponenten **PageBreak** tvingar Excel att påbörja en ny sida. Den här komponenten behövs inte om du vill använda Excels standardsidindelning, men du bör använda den när du vill att Excel följer ditt ER-format för att strukturera sidindelning.

## <a name="page-component"></a><a name="page-component"></a>Sidkomponent

### <a name="overview"></a>Översikt

Du kan använda **sidkomponenten** när du vill att Excel ska följa ditt ER-format och strukturera sidnumrering i ett genererat utgående dokument. När ett ER-format kör komponenter som finns under **sidkomponenten** läggs de sidbrytningar som krävs till automatiskt. Under den här processen beaktas storleken på det genererade innehållet, utskriftsformatet i Excel-mallen och pappersstorleken som valts i Excel-mallen.

Om du måste dela upp ett genererat dokument i olika avsnitt, som har olika sidnumrering, kan du konfigurera flera **sidkomponenter** i varje [arkkomponent](er-fillable-excel.md#sheet-component).

### <a name="structure"></a><a name="page-component-structure"></a>Struktur

Om den första komponenten under **Sidkomponenten** är [Intervallkomponent](er-fillable-excel.md#range-component) där egenskapen **Replikeringsriktning** anges till **Ingen replikering**, detta intervall betraktas som sidhuvudet för sidnumreringen som är baserat på inställningarna för den aktuella **sidkomponenten**. Det Excel-intervall som är kopplat till den här formatkomponenten upprepas högst upp på varje sida som genereras med hjälp av inställningarna för den aktuella **sidkomponenten**.

> [!NOTE]
> För korrekt sidnumrering, om intervallet [Rader att upprepa överst](https://support.microsoft.com/office/repeat-specific-rows-or-columns-on-every-printed-page-0d6dac43-7ee7-4f34-8b08-ffcc8b022409) är konfigurerad i din Excel-mall måste adressen för detta Excel-intervall vara lika med adressen för Excel-intervallet som är associerat med det tidigare beskrivna **Intervallkomponenten**.

Om den sista komponenten under **Sidkomponenten** är **Intervallkomponent** där egenskapen **Replikeringsriktning** anges till **Ingen replikering**, detta intervall betraktas som sidfoten för sidnumreringen som är baserat på inställningarna för den aktuella **sidkomponenten**. Det Excel-intervall som är kopplat till den här formatkomponenten upprepas längst ned på varje sida som genereras med hjälp av inställningarna för den aktuella **sidkomponenten**.

> [!NOTE]
> Vid korrekt sidnumrering bör de Excel-intervall som associeras med **intervallkomponenterna** inte ändras när de körs. Vi rekommenderar inte att du formaterar celler i detta intervall med hjälp av **Radbryt text i en cell** och **Autoanpassning radhöjd** Excel [alternativ](https://support.microsoft.com/office/wrap-text-in-a-cell-2a18cff5-ccc1-4bce-95e4-f0d4f3ff4e84).

Du kan lägga till flera andra **intervallkomponenter** mellan de valfria **intervallkomponenterna** för att ange hur ett genererat dokument ska fyllas i.

Om uppsättningen av kapslade **intervallkomponenter** under **sidkomponenten** inte följer den tidigare beskrivna strukturen, inträffar ett [valideringsfel](er-components-inspections.md#i17) vid designtiden i ER-formatdesignern. Felmeddelandet informerar om att problemet kan orsaka problem vid körning.

> [!NOTE]
> För att generera korrekt resultat, ange inte en bindning för någon **intervallkomponent** under **sidkomponenten** om egenskaper **Replikeringsriktning** för den **intervallkomponenten** anges till **Ingen replikering**, och om intervallet är konfigurerat för att generera sidhuvud eller sidfot.

Om du vill att sidnumreringsrelaterad summering och inventering ska beräkna löpande summor och summor per sida rekommenderar vi att du konfigurerar de datakällor för [datainsamling](er-data-collection-data-sources.md) som krävs. Om du vill veta hur du använder **sidkomponenten** för att sidnumrera ett genererat Excel-dokument kan du gå tillbaka till procedurerna i [Designa ett ER-format för att sidnumrera ett genererat dokument i Excel-format](er-paginate-excel-reports.md).

### <a name="limitations"></a><a name="page-component-limitations"></a>Begränsningar

När du använder **sidkomponenten** för Excel-sidnumrering känner du inte av det slutliga antalet sidor i ett genererat dokument förrän sidnumreringen har slutförts. Därför kan du inte beräkna det totala antalet sidor med hjälp av ER-formler och skriva ut korrekt antal sidor i ett genererat dokument på alla sidor före den sista sidan.

> [!TIP]
> Detta kan du uppnå i ett Excel-sidhuvud eller en sidfot i Excel genom att använda särskild Excel-[formatering](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers) för sidhuvud och sidfot.

Konfigurerade **sida** komponenter beaktas inte när du uppdaterar en Excel-mall i det redigerbara formatet i Dynamics 365 Finance version 10.0.22. Den här funktionen bör användas för ytterligare versioner av Finance.

Om du konfigurerar Excel-mallen till att använda [villkorsformatering](/office/dev/add-ins/excel/excel-add-ins-conditional-formatting), fungerar det kanske inte som förväntats i vissa fall.

### <a name="applicability"></a>Tillämplighet

**Sidkomponenten** fungerar bara för formatkomponenten [Excel-fil](er-fillable-excel.md#excel-file-component) när denna komponent är konfigurerad att använda en mall i Excel. Om du [ersätter](tasks/er-design-configuration-word-2016-11.md) Excel-mallen med en Word-mall och sedan kör det redigerbara ER-formatet, ignoreras **sidkomponenten**.

**Sidkomponenten** fungerar bara när funktionen **Aktivera användning av EPPlus-biblioteket i ramverksfunktionen Elektronisk rapportering** är aktiverad. Ett undantag är inaktiverat vid körning om ER försöker bearbeta **sidkomponenten** när den här funktionen är inaktiverad.

> [!NOTE]
> Ett undantag är ogiltigt vid körning om ett ER-format bearbetar **sidkomponenten** för en Excel-mall som innehåller minst en formel som refererar till en cell som inte är giltig. Du kan förhindra körtidsfel genom att korrigera Excel-mallen på det sätt som beskrivs i [Hur du korrigerar #REF! fel](https://support.microsoft.com/office/how-to-correct-a-ref-error-822c8e46-e610-4d02-bf29-ec4b8c5ff4be).

## <a name="footer-component"></a>Sidfotskomponent

Komponenten **Sidfot** används för att fylla i sidfötter längst ned i ett genererat kalkylblad i en Excel-arbetsbok.

> [!NOTE]
> Du kan lägga till den här komponenten för varje **ark** komponent om du vill ange olika sidfötter för olika kalkylblad i en genererad Excel-arbetsbok.

När du konfigurerar en individ komponenten **Sidfot** kan du använda egenskapen **Sidhuvud/sidfot utseende** för att specificera de sidor som komponenten används till. Följande värden finns:

- **Alla** – Kör den konfigurerade komponenten **Sidfot** för vilken sida som helst i det överordnade Excel-kalkylbladet.
- **Först** – Kör den konfigurerade komponenten **Sidfot** för endast första sidan som helst i det överordnade Excel-kalkylbladet.
- **Jämn** – Kör den konfigurerade komponenten **Sidfot** för endast jämna sidor i överordnade Excel-kalkylbladet.
- **Udda** – Kör den konfigurerade komponenten **Sidfot** för endast udda sidor i överordnade Excel-kalkylbladet.

För en enskild **Ark**-komponent, kan du lägga till flera **Sidfot**-komponenter, var och en har olika värde för egenskapen **Sidhuvud/Sidfot utseende**. På det här sättet kan du generera olika sidfötter för olika typer av sidor i ett Excel-kalkylblad.

> [!NOTE]
> Se till att varje **Sidfot**-komponent som du lägger till i en enkel **Ark**-komponent har ett annat värde för egenskapen **Sidhuvud/Sidfot utseende**. Annars inträffar [ett valideringsfel](er-components-inspections.md#i16). Felmeddelandet som du får informerar dig om inkonsekvensen.

Under den tillagda **Sidfot**-komponent, lägg till de nödvändiga kapslade komponenterna i **Text\\Sträng**, **Text\\DateTime** eller annan typ. Konfigurera bindande element för dessa komponenter om du vill ange hur sidfoten ska fyllas i.

Du kan också använda särskilda [formatkoder](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers) om du vill formatera innehållet i en genererad sidfot korrekt. Om du vill lära dig använda denna metod, följ stegen i [exempel 1](#example-1) senare i detta ämne.

> [!NOTE]
> Tänk på Excel när du konfigurerar ER [gräns](https://support.microsoft.com/office/excel-specifications-and-limits-1672b34d-7043-467e-8e27-269d656771c3) och det maximala antalet tecken för en enda sidhuvud eller sidfot.

## <a name="header-component"></a>Sidhuvudkomponent

Komponenten **Sidhuvud** används för att fylla i sidhuvud längst upp i ett genererat kalkylblad i en Excel-arbetsbok. Den används som komponenten **Sidfot**.

## <a name="edit-an-added-er-format"></a>Redigera ett tillagt ER-format

### <a name="update-a-template"></a>Uppdatera en mall

Du kan välja **Uppdatera från Excel** på fliken **Importera** i åtgärdsfönstret för att importera en uppdaterad mall till ett redigerbart ER-format. Under den här processen ersätts en mall för den valda **Excel\\-filkomponenten** med en ny mall. Innehållet i det redigerbara ER-formatet synkroniseras med innehållet i den uppdaterade ER-mallen.

- En ny komponent för ER-format kommer att skapas automatiskt för alla Excel-namn om komponenten i ER-format inte hittas i det redigerbara formatet.
- Alla ER-formatkomponenter tas bort från det redigerbara ER-formatet om det inte finns något korrekt Excel-namn.

> [!NOTE]
> Ange alternativet **Skapa formatelement för Excel-kalkylblad** som **Ja** om du vill skapa det valfria elementet **Ark** i det redigerbara ER-formatet.
>
> Om det redigerbara ER-formatet ursprungligen innehöll **ark**-element rekommenderar vi att du ställer in alternativet **Skapa formatelement för Excel-kalkylblad** som **Ja** när du importerar en uppdaterad mall. I annat fall kommer alla kapslade element i det ursprungliga **ark**-elementet att skapas från grunden. Därför kommer också alla bindningar för de återskapade formatelementen att gå förlorade i det uppdaterade ER-formatet.

![Alternativet Skapa formatelement för Excel-ark i dialogrutan Uppdatera från Excel.](./media/er-excel-format-update-template.png)

I version 10.0.28 och senare kan du använda alternativet **Uppdatera formatelementen Excel-sidhuvud och Excel-sidfot**.

- När du anger alternativet **Nej** ändras inte formatelementen i Excel-sidhuvud och Excel-sidfot, även om motsvarande sidhuvud eller sidfötter har uppdaterats i kalkylbladen för den importerade mallen i Excel-arbetsbokens format.
- När du anger alternativet **Ja** ändras formatelementen i Excel-sidhuvud och Excel-sidfot, även om motsvarande sidhuvud eller sidfötter har uppdaterats i kalkylbladen för den importerade mallen i Excel-arbetsbokens format.

    - Om strukturen för ett kalkylbladshuvudet eller en sidfot inte har ändrats, eller om det bara har bifogats, uppdateras strukturen för motsvarande formatelement för Excel-sidhuvud eller Excel-sidfot. Bindande formatelement som är kapslade under det här formatelementet för Excel-sidhuvud eller Excel-sidfot kommer att bevaras.
    - Om strukturen för ett kalkylbladshuvud eller sidfot har ändrats, återskapas motsvarande Excel-huvud- eller Excel-sidfotsformatelement. Bindande formatelement som är kapslade under det här formatelementet för Excel-sidhuvud eller Excel-sidfot kommer att tas bort.

![Alternativet Uppdatera Excel-huvud- och sidfotsformatelement i dialogrutan Uppdatera från Excel.](./media/er-excel-format-update-template2.png)

Om du vill veta mer om den här funktionen följer du stegen i [Ändra format för elektronisk rapportering genom att återanvända Excel-mallar](modify-electronic-reporting-format-reapply-excel-template.md).

## <a name="validate-an-er-format"></a>Validera ett ER-format

När du validerar ett ER-format som kan redigeras görs en konsekvenskontroll för att säkerställa att Excel-namnet finns i den Excel-mall som används för närvarande. Du får ett meddelande om eventuella inkonsekvenser. För vissa inkonsekvenser kommer alternativet att åtgärda problem automatiskt att erbjudas.

![Meddelande om valideringsfel.](./media/er-excel-format-validate.png)

## <a name="control-the-calculation-of-excel-formulas"></a>Kontrollera beräkning av Excel-formler

När ett utgående dokument i ett Microsoft Excel arbetsboksformat genereras, kan vissa celler i det här dokumentet innehålla Excel-formler. När funktionen **Aktivera användning av EPPlus bibliotek i ramverket för elektronisk rapportering** är aktiverad kan du styra när formlerna beräknas genom att ändra värdet för **Beräkningsalternativ**-[parametern](https://support.microsoft.com/office/change-formula-recalculation-iteration-or-precision-in-excel-73fc7dac-91cf-4d36-86e8-67124f6bcce4#ID0EAACAAA=Windows) i Excel-mallen som används:

- Välj **Automatisk** för att beräkna om alla beroende formler varje gång som ett genererat dokument läggs till av nya intervaller, celler osv.

    > [!NOTE]
    > Det kan orsaka ett prestandaproblem för Excel-mallar som innehåller många relaterade formler.

- Välj **Manuell** för att undvika omberäkningar av formler när ett dokument genereras.

    > [!NOTE]
    > Omräkning av formel utförs påtvingat manuellt när ett genererat dokument öppnas för förhandsgranskning med Excel.
    > Använd inte det här alternativet om du konfigurerar en ER-destination som förutsätter användning av ett genererat dokument utan förhandsgranskning i Excel (PDF-konvertering, e-post osv.) eftersom det genererade dokumentet kanske inte innehåller värden i celler med formler.

## <a name="example-1-format-footer-content"></a><a name="example-1"></a>Exempel 1: Formatera sidfotsinnehåll

1. Använd de angivna ER-konfigurationerna för att [generera](er-generate-printable-fti-forms.md) ett utskrivbart dokument med fritextfaktura (FTI).
2. Granska sidfoten för det genererade dokumentet. Lägg märke till att det innehåller information om det aktuella sidnumret och det totala antalet sidor i dokumentet.

    ![Granska sidfoten för ett genererat dokument i Excel-format.](./media/er-fillable-excel-footer-1.gif)

3. I ER-formatdesigner, [öppna](er-generate-printable-fti-forms.md#features-that-are-implemented-in-the-sample-er-format) exemplet ER-format för granskning.

    Sidfoten i kalkylbladet **Faktura** genereras baserat på inställningarna för två komponenter **Sträng** som finns under komponenten **Sidfot**:

    - Den första **Sträng** komponent fyller i följande speciella formateringskoder för att tvinga Excel att tillämpa specifik formatering:

        - **&C** – Anpassa sidfotstexten i mitten.
        - **&"Segoe UI,Vanlig"&8** – Visa sidfotstexten i teckensnittet med "Segoe UI Regular" teckensnitt med en storlek på 8 poäng.

    - Den andra komponenten **Sträng** fyller i texten som innehåller det aktuella sidnumret och det totala antalet sidor i det aktuella dokumentet.

    ![Granska ER-formatkomponenten för sidfot på sidan Formatdesigner.](./media/er-fillable-excel-footer-2.png)

4. Anpassa exempelformatet för ER för att ändra den aktuella sidfoten:

    1. [Skapa](er-quick-start2-customize-report.md#DeriveProvidedFormat) ett härlett **Fritextfaktura (Excel) anpassad** ER-format som baseras på exempelformatet för ER.
    2. Lägg till det första nya paret **Sträng** komponenter för **Sidfot** komponent för kalkylbladet **Faktura**:

        1. Lägg till en **Sträng** komponent som justerar företagsnamnet till vänster och presenterar det i åtta punkter "Segoe UI Regular" teckensnitt (**"&L&"Segoe UI,Vanlig"&8"**).
        2. Lägg till **Sträng** komponent som fyller i företagsnamnet (**model.InvoiceBase.CompanyInfo.Name**).

    3. Lägg till det andra nya paret **Sträng** komponenter för **Sidfot** komponent för kalkylbladet **Faktura**:

        1. Lägg till en **Sträng** komponent som justerar bearbetningsdatumet till höger och presenterar det i åtta punkter "Segoe UI Regular" teckensnitt (**"&R&"Segoe UI,Vanlig"&8"**).
        2. Lägg till en **Sträng** komponent som fyller i bearbetningsdatumet i ett anpassat format (**"&nbsp;"&DATEFORMAT(SESSIONTODAY(), "yyyy-MM-dd")**).

        ![Granska ER-formatkomponenten för sidfot på sidan Formatdesigner.](./media/er-fillable-excel-footer-3.png)

    4. [Slutför](er-quick-start2-customize-report.md#CompleteDerivedFormat) utkastversionen av den härledda **fritextfakturan (Excel) anpassade** ER-format.

5. [Konfigurera](er-generate-printable-fti-forms.md#configure-print-management) utskriftshantering för att använda det härledda **fritextfakturan (Excel) anpassade** ER-format istället för ER-exempelformatet.
6. Generera ett utskrivbart FTI-dokument och granska sidfoten för det genererade dokumentet.

    ![Granska sidfoten för ett genererat dokument i Excel-format.](./media/er-fillable-excel-footer-4.gif)

## <a name="example-2-fixing-the-merged-cells-epplus-issue"></a><a name="example-2"></a>Exempel 2: Korrigering av de sammanfogade cellerna EPPlus-problem

Du kan köra ett ER-format för att generera ett utgående dokument i ett Excel-arbetsbokformat. När funktionen **Aktivera användning av EPPlus-biblioteket i ramverket för elektronisk rapportering** är aktiverad i arbetsytan **Funktionshantering** används [EPPlus bibliotek](https://www.nuget.org/packages/epplus/4.5.2.1) för att göra Excel-utdata. På grund av kända [Excel-beteenden](https://answers.microsoft.com/en-us/msoffice/forum/all/deleting-a-range-of-cells-that-includes-merged/8601462c-4e2c-48e0-bd23-848eecb872a9) och begränsningar vad gäller EPPlus-biblioteket kan du dock stöta på följande undantag: "Det går inte att ta bort/skriva över kopplade celler. Ett intervall sammanfogas delvis med ett annat kopplat intervall." Slutför följande exempel om du vill veta vilka typer av Excel-mallar som kan orsaka det här undantaget och hur du löser problemet.

1. Skapa en ny Excel-arbetsbok i Excel-programmet.
2. På kalkylbladet **Sheet1**, lägg till **ReportTitle** namn för cell **A2**.
3. Sammanfoga celler **A1** och **A2**.

    ![Granska resultaten av de sammanslagningar av celler A1 och A2 som har utformats i Excel-arbetsboken i Excel-programmet.](./media/er-fillable-excel-example2-1.png)

3. På sidan **Konfigurationer**, [lägg till ER-format](er-fillable-excel.md#add-a-new-er-format) för att kunna generera ett utgående dokument i Excel-format.
4. På sidan **Formatdesigner**, [importera](er-fillable-excel.md#template-import) den designade Excel-arbetsboken till det tillagda ER-formatet som en ny mall för utgående dokument.
5. På fliken **Mappning** konfigurerar du bindande för komponenten **ReportTitle** för typen [Cell](er-fillable-excel.md#cell-component).
6. Kör det konfigurerade ER-formatet. Lägg märke till att följande undantag är olåst: "Kan inte ta bort/skriva över kopplade celler. Ett intervall sammanfogas delvis med ett annat kopplat intervall."

    ![Granska resultaten av det konfigurerade ER-formatet på sidan Formatdesigner.](./media/er-fillable-excel-example2-2.png)

Du kan korrigera problemet på något av följande sätt:

- **Enklare men ej rekommenderad:** I arbetsytan **Funktionshantering**, inaktivera **Aktivera användning av EPPlus-biblioteket i ramverket för elektronisk rapportering**. Även om det här är enklare kan du få andra problem om du använder den, eftersom vissa ER-funktioner bara stöds när funktionen **Aktivera användning av EPPlus-biblioteket i ramverksfunktionen Elektronisk rapportering är aktiverad**.
- **Rekommenderad:** Följ dessa steg:

    1. Ändra Excel-arbetsboken på något av följande sätt i Excel-programmet:

        - I kalkylbladet **Sheet1**, separera celler **A1** och **A2**.
        - Ändra referensen för **ReportTitle**-namnet från **=Sheet1!$A$2** till **=Sheet1!$A$1**. 

        ![Granska resultaten av att ändra referensen i Excel-arbetsboken som utformats i Excel-programmet.](./media/er-fillable-excel-example2-3.png)

    2. På sidan **Formatdesigner** [importerar](er-fillable-excel.md#template-import) du den ändrade Excel-arbetsboken till det redigerbara ER-formatet för att uppdatera den befintliga mallen.
    3. Kör det ändrade ER-formatet.

        ![Granska det genererade Excel-dokument i Excel skrivbordsprogrammet.](./media/er-fillable-excel-example2-4.png)

## <a name="limitations"></a>Begränsningar

### <a name="known-epplus-library-limitations"></a>Kända begränsningar i EPPlus-biblioteket

#### <a name="external-data-sources"></a>Externa datakällor

Om en av mallarna innehåller ett PivotTable som baseras på en PowerPivot modell som hänvisar till en [extern datakälla](https://support.microsoft.com/office/create-a-pivottable-with-an-external-data-source-db50d01d-2e1c-43bd-bfb5-b76a818a927b) och funktionen **Aktivera användning av EPPlus-biblioteket i ramverket för elektronisk rapportering** är aktiverat får du följande felmeddelande när du kör ett ER-format som använder den mallen för att generera ett utgående dokument i Excel-format: "Cachekällan är inte ett kalkylblad." Du har följande alternativ för att åtgärda detta problem:

- **Rekommenderad:** Gör om den Excel-lösning du använder:

    1. Skapa den del som innehåller pivots i en separat Excel-arbetsbok (arbetsbok A). 
    2. Använd ER för att generera en andra Excel-arbetsbok (arbetsbok B) från Finance som innehåller de uppgifter som krävs. 
    3. Läs arbetsbok B i arbetsbok A så snart arbetsbok B har genererats.

- Stäng av funktionen **Aktivera användning av EPPlus-biblioteket i elektroniskt rapporteringsramverk** att använda ett annat alternativ än EPPlus. 

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering](general-electronic-reporting.md)

[Utforma en konfiguration för rapportgenerering i OPENXML-format](tasks\er-design-reports-openxml-2016-11.md)

[Ändra format för elektronisk rapportering genom att tillämpa mallar från Excel igen](modify-electronic-reporting-format-reapply-excel-template.md)

[Använd horisontellt expanderbara intervall för att dynamiskt lägga till kolumner i Excel-rapporter](tasks/er-horizontal-1.md)

[Bädda in bilder och former i dokument som du skapar med ER](electronic-reporting-embed-images-shapes.md)

[Konfigurera elektronisk rapportering (ER) för att hämta data till Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
