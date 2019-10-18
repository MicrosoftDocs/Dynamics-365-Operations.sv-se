---
title: Implementera anpassade fält för Microsoft Dynamics 365 Project Timesheet-mobilappen på iOS och Android
description: Det här avsnittet innehåller vanliga mönster för hur du använder tillägg för att implementera anpassade fält.
author: KimANelson
manager: AnnBe
ms.date: 05/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: 10.0.3
ms.search.validFrom: 2019-05-29
ms.openlocfilehash: 4343c875da05641c57b7784bf52f1c814dd26d20
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175037"
---
# <a name="implement-custom-fields-for-the-microsoft-dynamics-365-project-timesheet-mobile-app-on-ios-and-android"></a>Implementera anpassade fält för Microsoft Dynamics 365 Project Timesheet-mobilappen på iOS och Android

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller vanliga mönster för hur du använder tillägg för att implementera anpassade fält. Följande avsnitt ingår:

- De olika datatyper som det anpassade fältramverket stöder
- Så här visar du skrivskyddade eller redigerbara fält i tidrapportposter, och sparar de värden som användaren anger tillbaka i databasen
- Visa skrivskyddade fält i tidrapporthuvudet
- Så här integrerar du annan anpassad affärslogik så här anger du standardvärden i fält och gör ytterligare valideringar

## <a name="audience"></a>Målgrupp

Det här avsnittet är avsett för utvecklare som integrerar sina anpassade fält i Microsoft Dynamics 365 Project Timesheet-mobilappen som är tillgängligt för Apple iOS och Google Android. Antagandet är att läsarna är bekant med funktionen för X ++-utveckling och funktionen för projekttidrapporter.

## <a name="data-contract--tstimesheetcustomfield-x-class"></a>Datakontrakt – TSTimesheetCustomField X++-klass

**TSTimesheetCustomField**-klassen är X ++-datakontraktklassen som representerar information om ett anpassat fält för funktionen tidrapport. Listor i anpassade fält skickas till både TSTimesheetDetails datakontrakt och TSTimesheetEntry datakontrakt för att visa anpassade fält i mobilappen.

- **TSTimesheetDetails** - kontrakt för tidrapporthuvudet.
- **TSTimesheetEntry**- tidrapporten för transaktionskontraktet. Grupper av dessa objekt som har samma projektinformation och **timesheetLineRecId**-värde utgör en rad.

### <a name="fieldbasetype-types"></a>fieldBaseType (typer)

Egenskapen **FieldBaseType** för objektet **TsTimesheetCustom** bestämmer vilken typ av fält som visas i appen. Följande **typer** av värden stöds.

| Typers värde | Typ              | Anteckningar |
|-------------|-------------------|-------|
| 0           | Sträng (och fasttexttyp) | Fältet visas som ett textfält. |
| 1           | Heltal           | Värdet visas som ett tal utan decimaler. |
| 2           | Realtal              | Värdet visas som ett tal utan decimaler.<p>Om du vill visa det verkliga värdet som en valuta i appen använder du egenskapen **fieldExtenededType**. Du kan använda egenskapen **numberOfDecimals** för att ange antalet decimaler som visas.</p> |
| 3           | Datum              | Datumformat bestäms av användarens inställning för **Datum-, tids- och nummerformat** som anges under **inställningar för språk- och land/region** i **användaralternativ**. |
| 4           | Boolesk           | |
| 15          | GUID              | |
| 16          | Int64             | |

- Om egenskapen **stringOptions** inte finns i **TSTimesheetCustomField**-objektet får du ett fritextfält till användaren.

    Egenskapen **stringLength** kan användas för att ange den maximala stränglängd som användarna kan ange.

- Om egenskapen **stringOptions** finns i **TSTimesheetCustomField**-objektet är dessa element de enda värden som användarna kan välja med hjälp av alternativ knappar (alternativknappar).

    I det här fallet kan strängfältet användas som ett uppräkningsvärde för användarpostens syfte. Om du vill spara värdet i databasen som en fasttexttyp mappar du strängvärdet manuellt till uppräkningsvärdet innan du sparar till databasen med hjälp av kommandokedjan (se kommandot "Använd kedja av i klassen TSTimesheetEntryService för att spara en tidrapportpost från appen tillbaka till databasen" längre fram i det här avsnittet för ett exempel).

### <a name="fieldextendedtype-tscustomfieldextendedtype"></a>fieldExtendedType (TSCustomFieldExtendedType)

Du kan använda den här egenskapen för att formatera verkliga värden som valuta. Den här metoden kan endast användas om **fieldBaseType**-värdet är **Realtal**.

- **TSCustomFieldExtendedType: ingen** – ingen formatering används.
- **TSCustomFieldExtendedType::valuta** – formatera värdet som valuta.

    När valutaformatet är aktivt kan fältet **stringValue** användas för att skicka den valutakod som ska visas i appen. Värdet är ett skrivskyddat värde.

    Fältet **realValue** innehåller det belopp som ska sparas i databasen.

### <a name="fieldsection-tscustomfieldsection"></a>fieldSection (TSCustomFieldSection)

Du kan använda den här egenskapen för att ange var det anpassade fältet ska visas i appen.

- **TSCustomFieldSection::huvud** – fältet kommer att visas i avsnittet **Visa fler detaljer** i appen. Dessa fält är alltid skrivskyddade.
- **TSCustomFieldSection::rad** – fältet kommer att visas efter alla färdiga radfält på tidrapportposter. Dessa fält kan antingen vara redigerbara eller skrivskyddade.

### <a name="fieldname-fieldnameshort"></a>fieldName (FieldNameShort)

Den här egenskapen identifierar fältet när värden som programmet tillhandahåller sparas i databasen igen.

### <a name="tablename-tablenameshort"></a>tableName (TableNameShort)

Den här egenskapen identifierar fältet när värden som programmet tillhandahåller sparas i databasen igen.

### <a name="iseditable-noyes"></a>isEditable (NoYes)

Ange den här egenskapen till **Ja** för att ange att fältet i avsnittet tidrapportpost ska redigeras av användarna. Ställ in egenskapen på **Nej** för att skrivskydda fältet.

### <a name="ismandatory-noyes"></a>isMandatory (NoYes)

Ange den här egenskapen till **Ja** för att ange att fältet i avsnittet tidrapportpost ska vara obligatorisk.

### <a name="label-str"></a>etikett (str)

Den här egenskapen anger etiketten som visas i nästa fält i appen.

### <a name="stringoptions-list-of-strings"></a>stringOptions (lista över strängar)

Den här egenskapen används endast om **fieldBaseType** har värdet **Sträng**. Om **stringOptions** har angetts, anges de strängvärden som är tillgängliga för markering via alternativknappar (alternativknappar) enligt strängarna i listan. Om det inte finns några strängar tillåts fritextinmatning i strängfältet (se avsnittet "använda en beslutskedja i klassen TSTimesheetEntryService för att spara en tidrapportpost från appen tillbaka till databasen" längre fram i det här avsnittet för ett exempel).

### <a name="stringlength-int"></a>stringLength (int)

Den här egenskapen anger den maximala längden för ett strängfält. Det används endast om **fieldBaseType** har värdet **Sträng**.

### <a name="numberofdecimals-int"></a>numberOfDecimals (int)

Den här egenskapen anger antalet decimaler som visas för ett riktigt fält. Det används endast om **fieldBaseType** har värdet **Riktigt**.

### <a name="ordersequence-int"></a>orderSequence (int)

Den här egenskapen bestämmer i vilken ordning de anpassade fälten visas i appen när fler än ett anpassat fält anges. Fält med lägre nummer visas först.

### <a name="booleanvalue-boolean"></a>booleanValue (boolesk)

För fält av **boolesk** typ skickar den här egenskapen booleskt värde för fältet mellan servern och appen.

### <a name="guidvalue-guid"></a>guidValue (guid)

För fält av **GUID** typ skickar den här egenskapen till den globala unika identifieraren (GUID) för fältet mellan servern och appen.

### <a name="int64value-int64"></a>int64Value (Int64)

För fält av **Int64** typ skickar den här egenskapen Int64 värde för fältet mellan servern och appen.

### <a name="intvalue-int"></a>intValue (int)

För fält av **Int** typ skickar den här egenskapen int värde för fältet mellan servern och appen.

### <a name="realvalue-real"></a>realValue (real)

För fält av **Real** typ skickar den här egenskapen real värde för fältet mellan servern och appen.

### <a name="stringvalue-str"></a>stringValue (str)

För fält av **Sträng** typ skickar den här egenskapen strängvärde för fältet mellan servern och appen. Det används också för fält av **Real** typ som är formaterade som valuta. För dessa fält används egenskapen för att skicka valutakoden till programmet.

### <a name="datevalue-date"></a>dateValue (datum)

Datum för fält av **Datum** typ skickar den här egenskapen datumvärde för fältet mellan servern och appen.

## <a name="show-and-save-a-custom-field-in-the-timesheet-entry-section"></a>Visa och spara ett anpassat fält i avsnittet tidrapportpost

Nedan visas en skärmdump från mobilappen för en tidrapportpost. Den visar färdiga fältet utanför rutan och ett anpassat fält i avsnittet "Tidspost" som kallas "Teststräng" med ett fasttextvärde på "Andra alternativet" som redan är inställt.

![Teststrängens anpassade fält i appen](media/timesheet-entry.jpg)



Nedan visas en skärmbild av användarens mobilapp som väljer ett av de uppräkningsalternativ som är tillgängliga för det anpassade fältet "teststräng".  De två alternativen är "första alternativet" och "andra alternativet" visas som alternativknappar. Det andra alternativet är markerat.

![Alternativknappar (alternativknappar) för det anpassade fältet för teststrängar](media/enum-option.jpg)



### <a name="extend-the-tstimesheetline-table-so-that-it-has-a-custom-field"></a>Utöka TSTimesheetLine-tabellen så att den har ett anpassat fält

I vanliga fall är det troligt att data för ett anpassat fält i avsnittet tidrapportost kommer att sparas i TSTimesheetLine-registret. Andra register kan dock användas om data kan hämtas baserat på en TSTimesheetTrans-post som tillhandahålls, eller om den inte har specifik postkontext (t.ex. om fältet är skrivskyddat i projektparametrarna).

Observera att anpassade fält inte behöver ha några säkerhetsposter i databasen. De kan genereras dynamiskt baserat på X ++-logik. Den här metoden kan vara användbar i skrivskyddade scenarier (se avsnittet "använda en beslutskedja i klassen TSTimesheetDetails, buildCustomFieldListForHeader-metod för att fylla i tidrapportdetaljer" för ett exempel på dynamiskt genererade anpassade fältvärden.)

Nedan visas en skärmbild från Visual Studio av programobjektträdet. Det visar ett tillägg till TSTimesheetLine-registret med TestLineString-fältet tillagt som ett anpassat fält.

![Radsträng](media/b6756b4a3fc5298093327a088a7710fd.png)

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-timesheet-entry-section"></a>Använd en beslutskedja på buildCustomFieldList-metoden i TSTimesheetSettings-klassen för att visa ett fält i postområdet för tidrapport

Den här koden styr bildskärmsinställningarna för fältet i appen. T.ex. styrs typen av fält, etiketten, om fältet är obligatoriskt och vilket avsnitt fältet visas i.

I följande exempel visas ett strängfält i tidsposter. Det här fältet har två alternativ, **första alternativet** och **andra alternativet** som är tillgängliga via alternativknappar (alternativknappar). Fältet i programmet är kopplat till fältet **TestLineString** som läggs till i TSTimesheetLine-registret.

Observera att användning av **TSTimesheetCustomField::newFromMetatdata()**-metoden för att förenkla initieringen av de anpassade fältegenskaperna: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength** och **numberOfDecimals**. Du kan också ställa in dessa parametrar manuellt, som du vill.

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('Second option');
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforentry-method-of-the-tstimesheetentry-class-to-enter-values-in-a-timesheet-entry"></a>Använd en beslutskedja på buildCustomFieldListForEntry-metoden i TSTimesheetEntry-klassen för att ange värden i en tidrapportpost

Metoden **buildCustomFieldListForEntry** används för att ange värden på de sparade tidrapportrader som finns i mobilappen. Den tar en TSTimesheetTrans-post som en parameter. Fält från den posten kan användas för att fylla i det anpassade fältvärdet i appen.

```
...
[ExtensionOf(classStr(TsTimesheetEntry))]
final class TsTimesheetEntry_Extension
{
    protected List buildCustomFieldListForEntry(TSTimesheetTrans _tsTimesheetTrans)
    {
        List customFieldList = next buildCustomFieldListForEntry(_tsTimesheetTrans);
        TSTimesheetLine tsTimesheetLine = _tsTimesheetTrans.timesheetLine();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        tsTimesheetCustomField.parmStringValue(tsTimesheetLine.TestLineString);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('second option;);
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-tstimesheetentryservice-class-to-save-a-timesheet-entry-from-the-app-back-to-the-database"></a>Använd beslutskedjan i TSTimesheetEntryService-klassen för att spara en tidrapportpost från appen tillbaka till databasen

Om du vill återställa ett anpassat fält till databasen i typisk användning måste du utöka flera metoder:

- **TimesheetLineNeedsUpdating**-metoden används för att avgöra om radposten har ändrats av användaren i appen och måste sparas i databasen. Om prestanda inte är ett problem kan den här metoden förenklas så att den alltid returnerar **sant**.
- Metoderna **populateTimesheetLineFromEntryDuringCreate** och **populateTimesheetLineFromEntryDuringUpdate** kan utökas så att de anger värden i TSTimesheetLine-databasposten från TSTimesheetEntry-datakontraktspost som tillhandahålls. I exemplet nedan ska du observera att mappningen mellan databasfältet och transaktionsfältet utförs manuellt via koden X++.
- **PopulateTimesheetWeekFromEntry**-metoden kan också utökas om det anpassade fält som mappas till **TSTimesheetEntry**-objektet måste skriva tillbaka till TSTimesheetLineweek databasregister.

> [!NOTE]
> I följande exempel sparas värdet **firstOption** eller **secondOption** som användaren väljer till databasen som ett råsträngvärde. Om databasfältet är ett fält av typen **fastext** kan dessa värden mappas manuellt till ett uppräkningsvärde och sedan sparas till ett uppräkningsfält i databasregistret.

```
...
[ExtensionOf(classStr(TSTimesheetEntryService))]
final class TSTimesheetEntryService_Extension
{
    protected boolean timesheetLineNeedsUpdating(TSTimesheetLine _tsTimesheetLine,
    TsTimesheetEntry _tsTimesheetEntry)
    {
        boolean ret = next timesheetLineNeedsUpdating(_tsTimesheetLine,
        _tsTimesheetEntry);
        if (!ret)
        {
            */ Loop through custom fields to see if value needs updating*/
            ListEnumerator enumerator =  _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    */ If Custom field value for TestLineString field has changed, We need to update the timesheet line.*/
                    if (_tsTimesheetLine.TestLineString != customField.parmStringValue())
                    {
                        ret = true;
                    }
                }
            }
        }
        return ret;
    }
    protected void populateTimesheetLineFromEntryDuringCreate(TSTimesheetLine
    _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
    {
        next populateTimesheetLineFromEntryDuringCreate(_tsTimesheetLine,
        _tsTimesheetEntry);
        this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
        _tsTimesheetEntry);
        }
        protected void populateTimesheetLineFromEntryDuringUpdate(TSTimesheetLine
        \_tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            next populateTimesheetLineFromEntryDuringUpdate(_tsTimesheetLine,
            _tsTimesheetEntry);
            this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
            _tsTimesheetEntry);
        }
        private void populateTimesheetLineFromCustomFields(TSTimesheetLine
        _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            ListEnumerator enumerator =
            _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    _tsTimesheetLine.TestLineString = customField.parmStringValue();
                }
            }
        }
    }
...
```

## <a name="show-a-custom-field-in-the-timesheet-header-section"></a>Visa och spara ett anpassat fält i avsnittet tidrapporthuvud

Nedan visas en skärmdump från mobilappen för användare som tittar på en tidrapport. Knappen "Mer information" har markerats i det övre högra hörnet för att visa alternativet "Visa mer information".  

![Kommandot Visa mer information](media/show-more.png)



Nedan visas en skärmdump från mobilappen med avsnittet "Mer" på en tidrapport. Ett anpassat fält med namnet "utnyttjandegrad för den här tidrapporten (ett beräknat anpassat fält) har lagts till i avsnittet tidrapportrubrik. Ett skrivskyddat värde på "0,667" har ställts in för det anpassade fältet.

![Avsnittet Mer](media/more-section.jpg)



### <a name="extend-the-tstimesheettable-table-so-that-it-has-a-custom-field"></a>Utöka TSTimesheetTable-tabellen så att den har ett anpassat fält

I vanliga fall är det troligt att data för ett anpassat fält i avsnittet rubrik kommer att dras från TSTimesheetHeader-registret. Andra register kan dock användas om data kan hämtas baserat på en TSTimesheetTable-post som tillhandahålls, eller om den inte har specifik postkontext (t.ex. om fältet är skrivskyddat i projektparametrarna).

Observera att anpassade fält inte behöver ha några säkerhetsposter i databasen. De kan genereras dynamiskt baserat på X ++-logik. I exemplet nedan visas den här metoden.

Fält i rubrikavsnittet är alltid skrivskyddade i appen.

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-header-section"></a>Använd en beslutskedja på buildCustomFieldList-metoden i TSTimesheetSettings-klassen för att visa ett fält i avsnittet rubrik

Den här koden styr bildskärmsinställningarna för fältet i appen. T.ex. styrs typen av fält, etiketten, om fältet är obligatoriskt och vilket avsnitt fältet visas i.

I följande exempel visas ett beräknat värde i rubrik avsnittet i appen.

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforheader-method-of-the-tstimesheetdetails-class-to-fill-in-timesheet-details"></a>Använd en beslutskedja på buildCustomFieldListForHeader-metoden i TSTimesheetDetails-klassen för att fylla i detaljerna för tidrapport

Metoden **buildCustomFieldListForHeader** används för att fylla i tidrapportens rubrikdetaljer i mobilappen. Den tar en TSTimesheetTable-post som en parameter. Fält från den posten kan användas för att fylla i det anpassade fältvärdet i appen. I följande exempel läses inga värden från databasen. I stället används X++-logik för att generera ett beräknat värde som sedan visas i appen.


```
...
[ExtensionOf(classStr(TSTimesheetDetails))]
final class TSTimesheetDetails_Extension
{
    protected List buildCustomFieldListForHeader(TSTimesheetTable
    _tsTimesheetTable)
    {
        List customFieldList = next buildCustomFieldListForHeader(_tsTimesheetTable);
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        real utilizationRate = 0;
        if (_tsTimesheetTable.totalHours() != 0)
        {
            utilizationRate = _tsTimesheetTable.totalHoursBillable() /
            _tsTimesheetTable.totalHours();
        }
        tsTimesheetCustomField.parmRealValue(utilizationRate);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

## <a name="other-configurabilityextensibility-opportunities"></a>Andra konfigurerbara och utökningsmöjligheter

### <a name="adding-additional-validation-for-the-app"></a>Lägger till ytterligare validering för appen

Befintlig logik för tidrapportfunktioner på databasnivå fungerar fortfarande som förväntat. Om du vill avbryta arbetet med att spara eller skicka meddelanden och visa ett visst felmeddelande, kan du lägga till **utlös fel (meddelande till användare")** till koden via ett tillägg för en beslutskedja. Här är tre exempel på användbara utökningsmetoder:

- Om **ValidateWrite** i TSTimesheetLine-tabellen returnerar **falsk** under en spara-åtgärd för en tidrapportrad visas ett felmeddelande i mobilappen.
- Om **validateSubmit** i TSTimesheetTable-tabellen returnerar **falsk** när tidrapporten skickas till appen visas ett felmeddelande för användaren.
- iLogik som fyller i fält (t.ex. **radegenskap**) under **infoga**-metoden i TSTimesheetLine-tabellen kommer fortfarande att köras.

### <a name="hiding-and-marking-out-of-box-fields-as-read-only-via-configuration"></a>Dölja och markera färdiga fält som skrivskyddade via konfiguration

Från projektets parametrar kan du ange att fält i ett färdigt fält som skrivskyddad eller dold i mobilappen. Ställ in alternativen i avsnittet **mobila tidrapporter** på fliken **tidrapport** på sidan **projekthantering och redovisningsparametrar**.

![Projektparametrar](media/5753b8ecccd1d8bb2b002dd538b3f762.png)

### <a name="changing-the-activities-that-are-available-for-selection-via-extensions"></a>Ändra vilka aktiviteter som är tillgängliga för markering via tillägg

De aktiviteter som är tillgängliga för val för ett projekt fylls i via metoderna **getActivitiesForProject()** och **getActivityQuery()** i klassen **TsTimesheetProjectService**. Du kan använda beslutskedja om du vill ändra det här beteendet så att det passar ditt affärsscenario för de aktiviteter som kan väljas för ett visst projekt.

### <a name="entering-a-default-project-category-on-timesheet-entries"></a>Ange en standardkategori för projektet på tidrapportposter

Inmatning av en standardprojektkategori på tidrapportposter sker på tre nivåer. Du kan använda beslutskedja om du vill utöka beteendet på någon av eller alla dessa nivåer för att uppnå önskat beteende. Följande hierarki används:

1. Appen försöker placera standardkategorin från projektresursen. Denna standardkategori ställs in i metoderna **getCurrentUserResource** och **getDelegatedResourcesForCurrentUser** i klassen **TSTimesheetSettingsService**.
2. Om standardkategorin inte finns på projektets resursnivå försöker programmet att hämta den från projektaktiviteten. Denna standardkategori ställs in i metoden **getActivitiesForProject** i klassen **TSTimesheetProjectService**.
3. Om standardkategorin inte finns på projektets aktivitetsnivå tas standardkategorin från projektparametrarna. Denna standardkategori ställs in i metoden **getProjectDetailsbyRule** i klassen **TSTimesheetProjectService**.
