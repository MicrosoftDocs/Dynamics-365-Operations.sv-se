---
title: Anpassa körningsgränssnittet för produktionsgolvet
description: I denna artikel beskrivs hur du utökar aktuella formulär eller skapar nya formulär och knappar för körningsgränssnittet för produktionsgolvet.
author: johanhoffmann
ms.date: 05/04/2022
ms.topic: article
ms.search.form: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-11-08
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 13fa6c2f3c30a820585d1b5a758f57ec563664d1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845994"
---
# <a name="customize-the-production-floor-execution-interface"></a>Anpassa körningsgränssnittet för produktionsgolvet

[!include [banner](../includes/banner.md)]

Utvecklare kan utöka aktuella formulär eller skapa egna formulär och knappar för körningsgränssnittet för produktionsgolvet. När du har lagt till koden för dessa nya element kan administratörer eller chefer på verkstadsgolvet enkelt lägga till dem i gränssnittet med hjälp av standardkonfigurationskontrollerna.

Nedan visas några möjliga lösningar om nya kolumner behövs i ett huvudformulär:

- Utöka formuläret `JmgProductionFloorExecutionMainGrid` och lägg till önskade fält.
- Skapa ett nytt formulär och lägg till det som en ny huvudvy (flik).

## <a name="add-a-new-button-action"></a>Lägg till en ny knapp (åtgärd)

Om du vill lägga till en ny knapp (åtgärd) följer du dessa steg för att skapa en klass som implementerar din anpassade åtgärd.

1. Skapa en ny klass med namnet `<ExtensionPrefix>_JmgProductionFloorExecution<ActionName>Action`, där

    - `<ExtensionPrefix>` identifierar unikt din lösning, vanligtvis med hjälp av ditt företagsnamn.
    - `<ActionName>` är ett unikt namn på klassen. Det identifierar vanligtvis åtgärdstypen.

1. Den nya klassen måste utöka `JmgProductionFloorExecutionAction`-klassen.
1. Åsidosätt alla nödvändiga metoder.

Du kan till exempel titta på koden för följande klasser:

- `JmgProductionFloorExecutionBreakAction` – En klass för en enkel åtgärd som inte behöver några poster.
- `JmgProductionFloorExecutionReportFeedbackAction` – En klass som innehåller mer komplexa funktioner.

När du är klar visas den nya knappen (åtgärden) automatiskt på sidan **Designflikar** i Microsoft Dynamics 365 Supply Chain Management. Du (eller en admin eller verkstadsgolvchef) kan där enkelt lägga till den i det primära eller sekundära verktygsfältet, på samma sätt som du kan lägga till standardknapparna. Se instruktioner i [Designa körningsgränssnittet för produktionsgolv](production-floor-execution-tabs.md).

## <a name="add-a-new-main-view"></a>Lägg till en ny huvudvy

1. Skapa ett nytt formulär med önskade element och funktioner. Observera att detta formulär är ett nytt formulär, inte ett filnamnstillägg. Namnge formuläret `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`, där

    - `<ExtensionPrefix>` identifierar unikt din lösning, vanligtvis med hjälp av ditt företagsnamn.
    - `<FormName>` är ett unikt namn på formuläret.

1. Skapa ett menyobjekt med namnet `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`.
1. Skapa ett tillägg kallat `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension`, där `getMainMenuItemsList`-metoden utökas genom att det nya menyalternativet läggs till i listan. Följande kod visar ett exempel.

    ```xpp
    [ExtensionOf(classStr(JmgProductionFloorExecutionMenuItemProvider))]
    public final class <ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>_Extension{
        static public List getMainMenuItemsList()
        {
            List menuItemList = next getMainMenuItemsList();
            menuItemList.addEnd(menuItemDisplayStr(<ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>));
            return menuItemList;
        }
    ```

När du är klar visas den nya huvudvyn automatiskt i kombinationsrutan **Huvudvy** på sidan **Designflikar** i Supply Chain Management. Du (eller en admin eller verkstadsgolvchef) kan där enkelt lägga till den i nya eller befintliga flikar, på samma sätt som du kan lägga till standardhuvudvyerna. Se instruktioner i [Designa körningsgränssnittet för produktionsgolv](production-floor-execution-tabs.md).

## <a name="add-a-details-view"></a>Lägg till en detaljvy

1. Skapa ett nytt formulär med önskade element och funktioner. Observera att detta formulär är nytt, inte ett filnamnstillägg. Namnge formuläret `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`, där 

    - `<ExtensionPrefix>` identifierar unikt din lösning, vanligtvis med hjälp av ditt företagsnamn.
    - `<FormName>` är ett unikt namn på formuläret.

1. Skapa ett menyobjekt kallat `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`.
1. Skapa ett tillägg kallat `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension`, där `getDetailsMenuItemList`-metoden utökas genom att det nya menyalternativet läggs till i listan.

När du är klar visas den nya detaljvyn automatiskt i kombinationsrutan **Detaljvy** på sidan **Designflikar** i Supply Chain Management. Du (eller en admin eller verkstadsgolvchef) kan där enkelt lägga till den i nya eller befintliga flikar, på samma sätt som du kan lägga till detaljvyerna. Se instruktioner i [Designa körningsgränssnittet för produktionsgolv](production-floor-execution-tabs.md).

## <a name="add-a-numeric-keypad-to-a-form-or-dialog"></a>Lägga till en numerisk knappsats i ett formulär eller en dialogruta

I följande exempel visas hur du lägger till numeriska knappsatser i ett formulär.

1. Antalet numeriska knappsatskontroller som varje formulär innehåller måste vara lika med antalet numeriska knappsatser i det formuläret.

    ```xpp
    private JmgProductionFloorExecutionNumpadController   numpadController1;
    private JmgProductionFloorExecutionNumpadController   numpadController2;
    private JmgProductionFloorExecutionNumpadController   numpadController3;
    ```

1. Konfigurera beteendet för varje numerisk knappsatskontroller, och koppla varje numerisk knappsatskontroller till en numerisk knappsatsdel.

    ```xpp
    /// <summary>
    /// Initializes all numpad controllers, defines their behavior and connects them with numpad form parts.
    /// </summary>
    public void initializeNumpadController()
    {
        numpadController1 = new JmgProductionFloorExecutionNumpadController();
        numpadController1.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_1);
        QuantityNumpad1.getPartFormRun().setNumpadController(numpadController1);
    
        numpadController2 = new JmgProductionFloorExecutionNumpadController();
        numpadController2.parmNumpadEnabled(false);
        numpadController2.parmNumpadValue(333.56);
        numpadController2.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_2);
        QuantityNumpad2.getPartFormRun().setNumpadController(numpadController2);
    }
    ```

## <a name="use-a-numeric-keypad-as-a-pop-up-dialog"></a>Använd en numeriskt knappsats som en popup-dialogruta

I följande exempel visas ett sätt att konfigurera en numerisk knappsatskontroller för en popup-dialogruta.

```xpp
private void setupNumpadController()
{
    numpadController = new JmgProductionFloorExecutionNumpadController();
    numpadController.parmShouldNumpadShowOkCancelButtons(true);
    numpadController.setNumpadValueToParentFormDelegate += eventhandler(this.setQtyValueFromNumpad);
}
```

I följande exempel visas ett sätt att öppna popup-dialogrutan för numerisk knappsats..

```xpp
Args args = new Args();
args.name(formstr(JmgProductionFloorExecutionNumpad));
args.menuItemName(menuItemDisplayStr(JmgProductionFloorExecutionNumpad));
args.caller(element);
Object formRun = classfactory.formRunClass(args);
formRun.init();
formRun.setNumpadController(numpadController);
numpadController.setValueToNumpad(333.56);
formRun.run();
```

## <a name="add-a-date-and-time-controls-to-a-form-or-dialog"></a>Lägga till en datum- och tidskontroll i ett formulär eller en dialogruta

I det här avsnittet visas hur du lägger till datum- och tidskontroller i ett formulär eller en dialogruta. Med den pekanvändarvänliga datum- och tidskontrollen kan medarbetare ange datum och tider. Följande skärmbilder visar hur kontrollerna vanligtvis visas på sidan. Tidskontrollen ger både 12-timmars- och 24-timmarsversioner. Den version som visas följer inställningarna för användarkontot under vilket gränssnittet körs.

![Exempel på datumkontroll](media/pfe-customize-date-control.png "Exempel på datumkontroll")

![Tidskontrollexempel med 12-timmarsklocka.](media/pfe-customize-time-control-12h.png "Tidskontrollexempel med 12-timmarsklocka")

![Tidskontrollexempel med 24-timmarsklocka.](media/pfe-customize-time-control-24h.png "Tidskontrollexempel med 24-timmarsklocka")

Följande procedur visar ett exempel på hur du lägger till datum- och tidskontroller i ett formulär.

1. Lägg till en kontrollant i formuläret för varje datum- och tidskontroll som formuläret ska innehålla. (Antalet kontrollanter måste vara lika med antalet datum- och tidskontroller i formuläret.)

    ```xpp
    private JmgProductionFloorExecutionDateTimeController  dateFromController; 
    private JmgProductionFloorExecutionDateTimeController  dateToController; 
    private JmgProductionFloorExecutionDateTimeController  timeFromController; 
    private JmgProductionFloorExecutionDateTimeController  timeToController;
    ```

1. Deklarera de variabler som krävs (av typen `utcdatetime`).

    ```xpp
    private utcdatetime fromDateTime;
    private utcdatetime toDateTime;
    ```

1. Skapa metoder där datetime uppdateras av datum- och tidskontrollerna. Exemplet nedan visar en sådan metod.

    ```xpp
    private void setFromDateTime(utcdatetime _value)
        {
            fromDateTime = _value;
        }
    ```

1. Konfigurera beteendet för varje datetime-kontrollant och koppla varje kontrollant så att den formar en del. I följande exempel visas hur du konfigurerar data för kontroller för från-datum och tid från. Du kan lägga till liknande kod för datum till- och tid till-kontroller (visas inte).

    ```xpp
    /// <summary>
    /// Initializes all date and time controllers, defines their behavior, and connects them with the form parts.
    /// </summary>
    private void initializeDateControlControllers()
    {
        dateFromController = new JmgProductionFloorExecutionDateTimeController();
        dateFromController.setDateControlValueToCallerFormDelegate += eventhandler(this.setFromDateTime);
        dateFromController.parmDateTimeValue(fromDateTime);
    
        timeFromController = new JmgProductionFloorExecutionDateTimeController();
        timeFromController.setDateControlValueToCallerFormDelegate += eventhandler(this.setFromDateTime);
        timeFromController.parmDateTimeValue(fromDateTime);
        
        DateFromFormPart.getPartFormRun().setDateControlController(dateFromController, timeFromController);
        TimeFromFormPart.getPartFormRun().setTimeControlController(timeFromController, dateFromController);
        
        ...

    }
    ```

    Om allt du behöver är en datumkontroll kan du hoppa över tidskontrollinställningarna och i stället bara konfigurera datumkontrollen som visas i följande exempel:

    ```xpp
    {
        dateFromController = new JmgProductionFloorExecutionDateTimeController();
        dateFromController.setDateControlValueToCallerFormDelegate += eventhandler(this.setFromDateTime);
        dateFromController.parmDateTimeValue(fromDateTime);
    
        DateFromFormPart.getPartFormRun().setDateControlController(dateFromController, null);
    }
    ```

## <a name="additional-resources"></a>Ytterligare resurser

- [Styla körningsgränssnittet för produktionsgolvet](production-floor-execution-styles.md)
- [Designa körningsgränssnittet för produktionsgolvet](production-floor-execution-tabs.md)
