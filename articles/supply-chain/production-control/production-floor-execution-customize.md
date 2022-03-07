---
title: Anpassa körningsgränssnittet för produktionsgolvet
description: I det här ämnet beskrivs hur du utökar aktuella formulär eller skapar nya formulär och knappar för körningsgränssnittet för produktionsgolvet.
author: johanhoffmann
ms.date: 11/08/2021
ms.topic: article
ms.search.form: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-11-08
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 414fe5d6e16ad125bc2b9bb7ed427e5db5180ec9
ms.sourcegitcommit: bc9e75c38e192664cde226ed3a94df5a0b304369
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790994"
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
    [ExtensionOf(classStr(JmgProductionFloorExecutionForm))]
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

## <a name="additional-resources"></a>Ytterligare resurser

- [Styla körningsgränssnittet för produktionsgolvet](production-floor-execution-styles.md)
- [Designa körningsgränssnittet för produktionsgolvet](production-floor-execution-tabs.md)
