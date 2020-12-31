---
title: Avancerad formelredigerare för elektronisk rapportering
description: I det här avsnittet beskrivs hur avancerad formelredigerare kan användas för att konfigurera uttryck i ER-modellmappning och formatkomponenter.
author: NickSelin
manager: AnnBe
ms.date: 04/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 14eb8a59b64a49649768f93befdf8e6e8dcf8105
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685393"
---
# <a name="electronic-reporting-advanced-formula-editor"></a>Avancerad formelredigerare för elektronisk rapportering

[!include [banner](../includes/banner.md)]

Förutom [elektronisk rapportering](general-electronic-reporting.md)[formelredigeraren](general-electronic-reporting-formula-designer.md) kan du använda den avancerade elektroniska rapportering formelredigeraren för att förbättra upplevelsen av konfigurering av ER-uttryck. Den avancerade redigeraren är webbläsarbaserad och utrustad med hjälp av [Monaco redigeraren](https://microsoft.github.io/monaco-editor). De mest använda avancerade redigeringsfunktionerna beskrivs i det här avsnittet:

- [Automatisk kodformatering](#Autoformatting)
- [IntelliSense](#IntelliSense)
- [Kodslutförande](#CodeCompletion)
- [Kodnavigering](#CodeNavigation)
- [Kodstrukturering](#CodeStructuring)
- [Sök och Ersätt](#FindAndReplace)
- [Datainklistring](#DataPasting)
- [Syntaxfärgning](#SyntaxColorization)

## <a name=""></a><a name="ActivateAdvEditor">Aktivera avancerad formelredigerare</a>

Gör på följande sätt när du vill börja använda den avancerade formelredigeraren i din instans av Microsoft Dynamics 365 Finance.

1.  Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2.  På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.
3.  I dialogrutan **Användarparametrar** i avsnittet **Körningsspårning** ska du ange parametern **Aktivera avancerad formelredigerare** till **Ja**.

[![Sidan ER-konfigurationer](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)

> [!NOTE]
> Tänk på att den här parametern är specifik för användaren och för företagsspecifika.

## <a name=""></a><a name="Autoformatting">Automatisk kodformatering</a>

När du skriver ett komplext uttryck som består av flera kodrader, kommer indraget för en ny rad automatiskt att baseras på indraget för föregående rad. Du kan markera rader och ändra deras indrag genom att skriva **tabb** eller **Skift + tabb**.

[![ER-formelredigeraren](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)

Med automatisk formatering kan du behålla hela uttrycket väl formaterat så att det blir enklare att underhålla och förenkla förståelsen av den konfigurerade logiken.

## <a name=""></a><a name="IntelliSense">IntelliSense</a>

Med hjälp av redigeraren för ordkomplettering kan du skriva uttryck snabbare och undvika skrivfel. När du börjar lägga till ny text innehåller redigeraren automatiskt en lista med funktioner som kan användas i ER-funktioner som innehåller de tecken du har angett. Du kan även utlösa IntelliSense på valfri plats i ett konfigurerat uttryck genom att skriva **Ctrl+Blanksteg**.

[![ER-formelredigeraren](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)

## <a name=""></a><a name="CodeCompletion">Kodslutförande</a>

I redigeraren skapas automatiskt kodslutförande av:

- Infoga en avslutande hakparentes när en hakparentes anges, så att markören innanför hakparenteserna hålls.
- Infoga det andra citattecknet när det första anges och behåll markören inuti citattecken.
- Infoga det andra dubla citattecknet när det första anges och behåll markören inuti citattecken.

[![ER-formelredigeraren](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)

När du pekar på den skrivna hakparentesen markeras automatiskt den andra hakparentesen för att visa den konstruktion som de stöder.

## <a name=""></a><a name="CodeNavigation">Kodnavigering</a>

Du kan hitta nödvändiga symboler eller rader i uttrycket genom att skriva kommandot **gå till** med hjälp av kommandoraden eller snabbmenyn.

Om du till exempel vill hoppa till rad **8** gör du så här:

- Tryck på **Ctrl+G**, ange värdet **8** och tryck på **retur**.

  - eller -

- Tryck på **F1**, skriv **G**, välj **Gå till rad**, ange värdet **8** och tryck på **retur**.

[![ER-formelredigeraren](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)

## <a name=""></a><a name="CodeStructuring">Kodstrukturering</a>

Koden för vissa funktioner, t.ex. [IF](er-functions-logical-if.md) eller [CASE](er-functions-logical-case.md), struktureras automatiskt. Du kan expandera och komprimera alla vikbara regioner i koden om du vill minska den redigerbara delen av ett uttryck om du bara vill fokusera på det stycke kod som kräver din uppmärksamhet. Kommandona växla vikning/vika upp kan användas för det.

Om du till exempel vill vika alla områden gör du så här:

- Tryck **Ctrl+K**

  - eller -

- Tryck **F1**, tryck **FO**, välj **Vik alla** och tryck på **retur**

Om du till exempel vill vika upp alla områden gör du så här:

- Tryck **Ctrl+J**

  - eller -
  
- Tryck **F1**, skriv **UN**, välj **Vik upp alla** och tryck på **retur**

[![ER-formelredigeraren](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)

## <a name=""></a><a name="FindAndReplace">Sök och Ersätt</a>

Om du vill söka efter förekomster av viss text, markerar du texten i uttrycket och gör följande:

- Tryck på **Ctrl+F** och tryck sedan på **F3** för att söka efter nästa förekomst av den markerade texten **Shift+F3** för att hitta föregående förekomst.

  - eller -
  
- Tryck på **F1**, skriv **F** och välj sedan det alternativ som krävs för att hitta den markerade texten.

Om du vill ersätta förekomster av viss text, markerar du texten i uttrycket och gör följande:

- Tryck **Ctrl+H**. Ange alternativ text och välj ersättningsalternativet om du vill ersätta den markerade texten eller alla förekomster av den här texten i det aktuella uttrycket.

  - eller -
  
- Tryck på **F1**, skriv **R** och välj sedan det alternativ som krävs för att ersätta den markerade texten. Ange alternativ text och välj ersättningsalternativet om du vill ersätta den markerade texten eller alla förekomster av den här texten i det aktuella uttrycket.

Om du vill ändra alla förekomster av viss text, markerar du texten i uttrycket och gör följande:

- Tryck på **Ctrl+F2** och ange alternativ text.

  - eller -
  
- Tryck på **F1**, skriv **C** och välj sedan det alternativ som krävs för att ändra den markerade texten. Ange alternativ text.

[![ER-formelredigeraren](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)

## <a name=""></a><a name="DataPasting">Datakällor och funktioner klistra in</a>

Du kan välja **Lägg till data källa** som klistras in i det aktuella uttrycket en datakälla som är markerad på den vänstra panelen i **datakällan**. Du kan välja **Lägg till funktion** på liknande sätt som klistras in i det aktuella uttrycket en funktion som är markerad på den högra panelen i **funktioner**. Om du använder ER-formelredigeraren klistras en markerad funktion eller en markerad datakälla alltid in i slutet av det konfigurerade uttrycket. Om du använder avancerad ER-formelredigeraren klistras en markerad funktion eller en markerad datakälla in i någon del av det konfigurerade uttrycket. Du måste då använda markören för att ange var du vill klistra in informationen.

[![ER-formelredigeraren](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)

## <a name=""></a><a name="SyntaxColorization">Syntaxfärgning</a>

För närvarande används olika färger för att belysa följande delar av uttryck:

- Texten inom dubbla hakparenteser som kan representera ett etikett-ID för en textkonstant.

[![ER-formelredigeraren](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)

## <a name="limitations"></a>Begränsningar

Redigeraren stöds för närvarande i följande webbläsare:

- Chrome
- Edge
- Firefox
- Opera
- Safari

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)
- [Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)
- [Monaco-redigerare](https://microsoft.github.io/monaco-editor)
