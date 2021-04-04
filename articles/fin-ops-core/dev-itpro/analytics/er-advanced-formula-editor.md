---
title: Avancerad formelredigerare för elektronisk rapportering
description: I det här avsnittet beskrivs hur avancerad formelredigerare kan användas för att konfigurera uttryck i ER-modellmappning och formatkomponenter.
author: NickSelin
manager: AnnBe
ms.date: 04/10/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8746340eb886ec797afdd58797a4c5e41f93022f
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560151"
---
# <a name="electronic-reporting-advanced-formula-editor"></a><span data-ttu-id="63b1a-103">Avancerad formelredigerare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="63b1a-103">Electronic reporting advanced formula editor</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="63b1a-104">Förutom [elektronisk rapportering](general-electronic-reporting.md)[formelredigeraren](general-electronic-reporting-formula-designer.md) kan du använda den avancerade elektroniska rapportering formelredigeraren för att förbättra upplevelsen av konfigurering av ER-uttryck.</span><span class="sxs-lookup"><span data-stu-id="63b1a-104">In addition to the [Electronic reporting](general-electronic-reporting.md) [formula editor](general-electronic-reporting-formula-designer.md), you can use the advanced Electronic reporting formula editor to improve the experience of configuring Electronic reporting (ER) expressions.</span></span> <span data-ttu-id="63b1a-105">Den avancerade redigeraren är webbläsarbaserad och utrustad med hjälp av [Monaco redigeraren](https://microsoft.github.io/monaco-editor).</span><span class="sxs-lookup"><span data-stu-id="63b1a-105">The advanced editor is browser-based and powered by the [Monaco editor](https://microsoft.github.io/monaco-editor).</span></span> <span data-ttu-id="63b1a-106">De mest använda avancerade redigeringsfunktionerna beskrivs i det här avsnittet:</span><span class="sxs-lookup"><span data-stu-id="63b1a-106">The most commonly used advanced editor features are described in this topic:</span></span>

- [<span data-ttu-id="63b1a-107">Automatisk kodformatering</span><span class="sxs-lookup"><span data-stu-id="63b1a-107">Code autoformatting</span></span>](#Autoformatting)
- [<span data-ttu-id="63b1a-108">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="63b1a-108">IntelliSense</span></span>](#IntelliSense)
- [<span data-ttu-id="63b1a-109">Kodslutförande</span><span class="sxs-lookup"><span data-stu-id="63b1a-109">Code completion</span></span>](#CodeCompletion)
- [<span data-ttu-id="63b1a-110">Kodnavigering</span><span class="sxs-lookup"><span data-stu-id="63b1a-110">Code navigation</span></span>](#CodeNavigation)
- [<span data-ttu-id="63b1a-111">Kodstrukturering</span><span class="sxs-lookup"><span data-stu-id="63b1a-111">Code structuring</span></span>](#CodeStructuring)
- [<span data-ttu-id="63b1a-112">Sök och Ersätt</span><span class="sxs-lookup"><span data-stu-id="63b1a-112">Find and replace</span></span>](#FindAndReplace)
- [<span data-ttu-id="63b1a-113">Datainklistring</span><span class="sxs-lookup"><span data-stu-id="63b1a-113">Data pasting</span></span>](#DataPasting)
- [<span data-ttu-id="63b1a-114">Syntaxfärgning</span><span class="sxs-lookup"><span data-stu-id="63b1a-114">Syntax colorization</span></span>](#SyntaxColorization)

## <a name=""></a><span data-ttu-id="63b1a-115"><a name="ActivateAdvEditor">Aktivera avancerad formelredigerare</a></span><span class="sxs-lookup"><span data-stu-id="63b1a-115"><a name="ActivateAdvEditor">Activate the advanced formula editor</a></span></span>

<span data-ttu-id="63b1a-116">Gör på följande sätt när du vill börja använda den avancerade formelredigeraren i din instans av Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="63b1a-116">Complete the following steps to start using the advanced formula editor in your instance of Microsoft Dynamics 365 Finance.</span></span>

1.  <span data-ttu-id="63b1a-117">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="63b1a-117">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2.  <span data-ttu-id="63b1a-118">På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.</span><span class="sxs-lookup"><span data-stu-id="63b1a-118">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3.  <span data-ttu-id="63b1a-119">I dialogrutan **Användarparametrar** i avsnittet **Körningsspårning** ska du ange parametern **Aktivera avancerad formelredigerare** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="63b1a-119">In the **User parameters** dialog box, in the **Execution tracing** section, set the **Enable advanced formula editor** parameter to **Yes**.</span></span>

<span data-ttu-id="63b1a-120">[![Sidan ER-konfigurationer](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span><span class="sxs-lookup"><span data-stu-id="63b1a-120">[![ER configurations page](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span></span>

> [!NOTE]
> <span data-ttu-id="63b1a-121">Tänk på att den här parametern är specifik för användaren och för företagsspecifika.</span><span class="sxs-lookup"><span data-stu-id="63b1a-121">Be aware that this parameter is user specific and company specific.</span></span>

## <a name=""></a><span data-ttu-id="63b1a-122"><a name="Autoformatting">Automatisk kodformatering</a></span><span class="sxs-lookup"><span data-stu-id="63b1a-122"><a name="Autoformatting">Code autoformatting</a></span></span>

<span data-ttu-id="63b1a-123">När du skriver ett komplext uttryck som består av flera kodrader, kommer indraget för en ny rad automatiskt att baseras på indraget för föregående rad.</span><span class="sxs-lookup"><span data-stu-id="63b1a-123">When you write a complex expression that consists of multiple rows of code, the indentation of a new entered line will be automatic based on the indentation of the previous row.</span></span> <span data-ttu-id="63b1a-124">Du kan markera rader och ändra deras indrag genom att skriva **tabb** eller **Skift + tabb**.</span><span class="sxs-lookup"><span data-stu-id="63b1a-124">You can select lines and change their indentation by typing **Tab** or **Shift+Tab**.</span></span>

<span data-ttu-id="63b1a-125">[![ER-formelredigeraren](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span><span class="sxs-lookup"><span data-stu-id="63b1a-125">[![ER formula editor](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span></span>

<span data-ttu-id="63b1a-126">Med automatisk formatering kan du behålla hela uttrycket väl formaterat så att det blir enklare att underhålla och förenkla förståelsen av den konfigurerade logiken.</span><span class="sxs-lookup"><span data-stu-id="63b1a-126">Autoformatting allows you to keep the entire expression well formatted to make further maintenance easier and to simplify understanding of the configured logic.</span></span>

## <a name=""></a><span data-ttu-id="63b1a-127"><a name="IntelliSense">IntelliSense</a></span><span class="sxs-lookup"><span data-stu-id="63b1a-127"><a name="IntelliSense">IntelliSense</a></span></span>

<span data-ttu-id="63b1a-128">Med hjälp av redigeraren för ordkomplettering kan du skriva uttryck snabbare och undvika skrivfel.</span><span class="sxs-lookup"><span data-stu-id="63b1a-128">The editor provides word completion to help you write expression faster and avoid typos.</span></span> <span data-ttu-id="63b1a-129">När du börjar lägga till ny text innehåller redigeraren automatiskt en lista med funktioner som kan användas i ER-funktioner som innehåller de tecken du har angett.</span><span class="sxs-lookup"><span data-stu-id="63b1a-129">When you start adding new text, the editor automatically offers a list of functions supported in ER functions that contain the characters you have entered.</span></span> <span data-ttu-id="63b1a-130">Du kan även utlösa IntelliSense på valfri plats i ett konfigurerat uttryck genom att skriva **Ctrl+Blanksteg**.</span><span class="sxs-lookup"><span data-stu-id="63b1a-130">You can also trigger IntelliSense in any place of a configured expression by typing **Ctrl+Space**.</span></span>

<span data-ttu-id="63b1a-131">[![ER-formelredigeraren](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span><span class="sxs-lookup"><span data-stu-id="63b1a-131">[![ER formula editor](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span></span>

## <a name=""></a><span data-ttu-id="63b1a-132"><a name="CodeCompletion">Kodslutförande</a></span><span class="sxs-lookup"><span data-stu-id="63b1a-132"><a name="CodeCompletion">Code completion</a></span></span>

<span data-ttu-id="63b1a-133">I redigeraren skapas automatiskt kodslutförande av:</span><span class="sxs-lookup"><span data-stu-id="63b1a-133">The editor automatically provides code completion by:</span></span>

- <span data-ttu-id="63b1a-134">Infoga en avslutande hakparentes när en hakparentes anges, så att markören innanför hakparenteserna hålls.</span><span class="sxs-lookup"><span data-stu-id="63b1a-134">Inserting a closing bracket when an opening  bracket is entered, keeping the cursor inside the brackets.</span></span>
- <span data-ttu-id="63b1a-135">Infoga det andra citattecknet när det första anges och behåll markören inuti citattecken.</span><span class="sxs-lookup"><span data-stu-id="63b1a-135">Inserting the second quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>
- <span data-ttu-id="63b1a-136">Infoga det andra dubla citattecknet när det första anges och behåll markören inuti citattecken.</span><span class="sxs-lookup"><span data-stu-id="63b1a-136">Inserting the second double quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>

<span data-ttu-id="63b1a-137">[![ER-formelredigeraren](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span><span class="sxs-lookup"><span data-stu-id="63b1a-137">[![ER formula editor](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span></span>

<span data-ttu-id="63b1a-138">När du pekar på den skrivna hakparentesen markeras automatiskt den andra hakparentesen för att visa den konstruktion som de stöder.</span><span class="sxs-lookup"><span data-stu-id="63b1a-138">When you point to the typed bracket, the second bracket of this pair is automatically highlighted to show the construct that they support.</span></span>

## <a name=""></a><span data-ttu-id="63b1a-139"><a name="CodeNavigation">Kodnavigering</a></span><span class="sxs-lookup"><span data-stu-id="63b1a-139"><a name="CodeNavigation">Code navigation</a></span></span>

<span data-ttu-id="63b1a-140">Du kan hitta nödvändiga symboler eller rader i uttrycket genom att skriva kommandot **gå till** med hjälp av kommandoraden eller snabbmenyn.</span><span class="sxs-lookup"><span data-stu-id="63b1a-140">You can locate required symbols or lines in your expression by typing the **Go to** command using the command palette or the context menu.</span></span>

<span data-ttu-id="63b1a-141">Om du till exempel vill hoppa till rad **8** gör du så här:</span><span class="sxs-lookup"><span data-stu-id="63b1a-141">For example, to jump to line **8**, do the following:</span></span>

- <span data-ttu-id="63b1a-142">Tryck på **Ctrl+G**, ange värdet **8** och tryck på **retur**.</span><span class="sxs-lookup"><span data-stu-id="63b1a-142">Press **Ctrl+G**, enter the value **8**, and then press **Enter**.</span></span>

  <span data-ttu-id="63b1a-143">- eller -</span><span class="sxs-lookup"><span data-stu-id="63b1a-143">-or-</span></span>

- <span data-ttu-id="63b1a-144">Tryck på **F1**, skriv **G**, välj **Gå till rad**, ange värdet **8** och tryck på **retur**.</span><span class="sxs-lookup"><span data-stu-id="63b1a-144">Press **F1**, type **G**, select **Go to line**, enter the value **8**, and the press **Enter**.</span></span>

<span data-ttu-id="63b1a-145">[![ER-formelredigeraren](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span><span class="sxs-lookup"><span data-stu-id="63b1a-145">[![ER formula editor](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span></span>

## <a name=""></a><span data-ttu-id="63b1a-146"><a name="CodeStructuring">Kodstrukturering</a></span><span class="sxs-lookup"><span data-stu-id="63b1a-146"><a name="CodeStructuring">Code structuring</a></span></span>

<span data-ttu-id="63b1a-147">Koden för vissa funktioner, t.ex. [IF](er-functions-logical-if.md) eller [CASE](er-functions-logical-case.md), struktureras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="63b1a-147">The code for some functions, such as [IF](er-functions-logical-if.md) or [CASE](er-functions-logical-case.md), is automatically structured.</span></span> <span data-ttu-id="63b1a-148">Du kan expandera och komprimera alla vikbara regioner i koden om du vill minska den redigerbara delen av ett uttryck om du bara vill fokusera på det stycke kod som kräver din uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="63b1a-148">You can expand and collapse any or all of the folding regions of this code to reduce the editable part of an expression in order to focus on only  thepiece of code that requires your attention.</span></span> <span data-ttu-id="63b1a-149">Kommandona växla vikning/vika upp kan användas för det.</span><span class="sxs-lookup"><span data-stu-id="63b1a-149">The toggle fold/unfold commands can be used for that.</span></span>

<span data-ttu-id="63b1a-150">Om du till exempel vill vika alla områden gör du så här:</span><span class="sxs-lookup"><span data-stu-id="63b1a-150">For example, to fold all regions, do the following:</span></span>

- <span data-ttu-id="63b1a-151">Tryck **Ctrl+K**</span><span class="sxs-lookup"><span data-stu-id="63b1a-151">Press **Ctrl+K**</span></span>

  <span data-ttu-id="63b1a-152">- eller -</span><span class="sxs-lookup"><span data-stu-id="63b1a-152">-or-</span></span>

- <span data-ttu-id="63b1a-153">Tryck **F1**, tryck **FO**, välj **Vik alla** och tryck på **retur**</span><span class="sxs-lookup"><span data-stu-id="63b1a-153">Press **F1**, press **FO**, select **Fold all**, and then press **Enter**</span></span>

<span data-ttu-id="63b1a-154">Om du till exempel vill vika upp alla områden gör du så här:</span><span class="sxs-lookup"><span data-stu-id="63b1a-154">To unfold all regions, do the following:</span></span>

- <span data-ttu-id="63b1a-155">Tryck **Ctrl+J**</span><span class="sxs-lookup"><span data-stu-id="63b1a-155">Press **Ctrl+J**</span></span>

  <span data-ttu-id="63b1a-156">- eller -</span><span class="sxs-lookup"><span data-stu-id="63b1a-156">-or-</span></span>
  
- <span data-ttu-id="63b1a-157">Tryck **F1**, skriv **UN**, välj **Vik upp alla** och tryck på **retur**</span><span class="sxs-lookup"><span data-stu-id="63b1a-157">Press **F1**, type **UN**, select **Unfold all**, and then press **Enter**</span></span>

<span data-ttu-id="63b1a-158">[![ER-formelredigeraren](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span><span class="sxs-lookup"><span data-stu-id="63b1a-158">[![ER formula editor](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span></span>

## <a name=""></a><span data-ttu-id="63b1a-159"><a name="FindAndReplace">Sök och Ersätt</a></span><span class="sxs-lookup"><span data-stu-id="63b1a-159"><a name="FindAndReplace">Find and replace</a></span></span>

<span data-ttu-id="63b1a-160">Om du vill söka efter förekomster av viss text, markerar du texten i uttrycket och gör följande:</span><span class="sxs-lookup"><span data-stu-id="63b1a-160">To find occurrences of certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="63b1a-161">Tryck på **Ctrl+F** och tryck sedan på **F3** för att söka efter nästa förekomst av den markerade texten **Shift+F3** för att hitta föregående förekomst.</span><span class="sxs-lookup"><span data-stu-id="63b1a-161">Press **Ctrl+F** and then press **F3** to find the next occurrence of the selected text, or press **Shift+F3** to find the previous occurrence.</span></span>

  <span data-ttu-id="63b1a-162">- eller -</span><span class="sxs-lookup"><span data-stu-id="63b1a-162">-or-</span></span>
  
- <span data-ttu-id="63b1a-163">Tryck på **F1**, skriv **F** och välj sedan det alternativ som krävs för att hitta den markerade texten.</span><span class="sxs-lookup"><span data-stu-id="63b1a-163">Press **F1**, type **F**, and then select the required option to find the selected text.</span></span>

<span data-ttu-id="63b1a-164">Om du vill ersätta förekomster av viss text, markerar du texten i uttrycket och gör följande:</span><span class="sxs-lookup"><span data-stu-id="63b1a-164">To replace occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="63b1a-165">Tryck **Ctrl+H**.</span><span class="sxs-lookup"><span data-stu-id="63b1a-165">Press **Ctrl+H**.</span></span> <span data-ttu-id="63b1a-166">Ange alternativ text och välj ersättningsalternativet om du vill ersätta den markerade texten eller alla förekomster av den här texten i det aktuella uttrycket.</span><span class="sxs-lookup"><span data-stu-id="63b1a-166">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

  <span data-ttu-id="63b1a-167">- eller -</span><span class="sxs-lookup"><span data-stu-id="63b1a-167">-or-</span></span>
  
- <span data-ttu-id="63b1a-168">Tryck på **F1**, skriv **R** och välj sedan det alternativ som krävs för att ersätta den markerade texten.</span><span class="sxs-lookup"><span data-stu-id="63b1a-168">Press **F1**, type **R**, and then select the required option to replace the selected text.</span></span> <span data-ttu-id="63b1a-169">Ange alternativ text och välj ersättningsalternativet om du vill ersätta den markerade texten eller alla förekomster av den här texten i det aktuella uttrycket.</span><span class="sxs-lookup"><span data-stu-id="63b1a-169">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

<span data-ttu-id="63b1a-170">Om du vill ändra alla förekomster av viss text, markerar du texten i uttrycket och gör följande:</span><span class="sxs-lookup"><span data-stu-id="63b1a-170">To change all occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="63b1a-171">Tryck på **Ctrl+F2** och ange alternativ text.</span><span class="sxs-lookup"><span data-stu-id="63b1a-171">Press **Ctrl+F2** and then enter the alternative text.</span></span>

  <span data-ttu-id="63b1a-172">- eller -</span><span class="sxs-lookup"><span data-stu-id="63b1a-172">-or-</span></span>
  
- <span data-ttu-id="63b1a-173">Tryck på **F1**, skriv **C** och välj sedan det alternativ som krävs för att ändra den markerade texten.</span><span class="sxs-lookup"><span data-stu-id="63b1a-173">Press **F1**, type **C**, and then select the required option to change the selected text.</span></span> <span data-ttu-id="63b1a-174">Ange alternativ text.</span><span class="sxs-lookup"><span data-stu-id="63b1a-174">Enter the alternative text.</span></span>

<span data-ttu-id="63b1a-175">[![ER-formelredigeraren](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span><span class="sxs-lookup"><span data-stu-id="63b1a-175">[![ER formula editor](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span></span>

## <a name=""></a><span data-ttu-id="63b1a-176"><a name="DataPasting">Datakällor och funktioner klistra in</a></span><span class="sxs-lookup"><span data-stu-id="63b1a-176"><a name="DataPasting">Data sources and functions pasting</a></span></span>

<span data-ttu-id="63b1a-177">Du kan välja **Lägg till data källa** som klistras in i det aktuella uttrycket en datakälla som är markerad på den vänstra panelen i **datakällan**.</span><span class="sxs-lookup"><span data-stu-id="63b1a-177">You can select **Add data source**, which pastes to the current expression a data source that is currently selected on the **Data source** left panel.</span></span> <span data-ttu-id="63b1a-178">Du kan välja **Lägg till funktion** på liknande sätt som klistras in i det aktuella uttrycket en funktion som är markerad på den högra panelen i **funktioner**.</span><span class="sxs-lookup"><span data-stu-id="63b1a-178">Simlilarly, you can select **Add function**, which pastes to the current expression a function that is currently selected on the **Functions** right panel.</span></span> <span data-ttu-id="63b1a-179">Om du använder ER-formelredigeraren klistras en markerad funktion eller en markerad datakälla alltid in i slutet av det konfigurerade uttrycket.</span><span class="sxs-lookup"><span data-stu-id="63b1a-179">If you use the ER formula editor, a selected function or a selected data source will always be pasted to the end of the configured expression.</span></span> <span data-ttu-id="63b1a-180">Om du använder avancerad ER-formelredigeraren klistras en markerad funktion eller en markerad datakälla in i någon del av det konfigurerade uttrycket.</span><span class="sxs-lookup"><span data-stu-id="63b1a-180">When you use the advanced ER formula editor, a selected function or a selected data source can be pasted to any part of the configured expression.</span></span> <span data-ttu-id="63b1a-181">Du måste då använda markören för att ange var du vill klistra in informationen.</span><span class="sxs-lookup"><span data-stu-id="63b1a-181">You will need to use the cursor to specify where you want to paste the data.</span></span>

<span data-ttu-id="63b1a-182">[![ER-formelredigeraren](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span><span class="sxs-lookup"><span data-stu-id="63b1a-182">[![ER formula editor](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span></span>

## <a name=""></a><span data-ttu-id="63b1a-183"><a name="SyntaxColorization">Syntaxfärgning</a></span><span class="sxs-lookup"><span data-stu-id="63b1a-183"><a name="SyntaxColorization">Syntax colorization</a></span></span>

<span data-ttu-id="63b1a-184">För närvarande används olika färger för att belysa följande delar av uttryck:</span><span class="sxs-lookup"><span data-stu-id="63b1a-184">Currently, different colors are used to highlight the following parts of expressions:</span></span>

- <span data-ttu-id="63b1a-185">Texten inom dubbla hakparenteser som kan representera ett etikett-ID för en textkonstant.</span><span class="sxs-lookup"><span data-stu-id="63b1a-185">The text in double brackets that can represent a label ID of a text constant.</span></span>

<span data-ttu-id="63b1a-186">[![ER-formelredigeraren](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span><span class="sxs-lookup"><span data-stu-id="63b1a-186">[![ER formula editor](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span></span>

## <a name="limitations"></a><span data-ttu-id="63b1a-187">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="63b1a-187">Limitations</span></span>

<span data-ttu-id="63b1a-188">Redigeraren stöds för närvarande i följande webbläsare:</span><span class="sxs-lookup"><span data-stu-id="63b1a-188">The editor is currently supported in the following web browsers:</span></span>

- <span data-ttu-id="63b1a-189">Chrome</span><span class="sxs-lookup"><span data-stu-id="63b1a-189">Chrome</span></span>
- <span data-ttu-id="63b1a-190">Edge</span><span class="sxs-lookup"><span data-stu-id="63b1a-190">Edge</span></span>
- <span data-ttu-id="63b1a-191">Firefox</span><span class="sxs-lookup"><span data-stu-id="63b1a-191">Firefox</span></span>
- <span data-ttu-id="63b1a-192">Opera</span><span class="sxs-lookup"><span data-stu-id="63b1a-192">Opera</span></span>
- <span data-ttu-id="63b1a-193">Safari</span><span class="sxs-lookup"><span data-stu-id="63b1a-193">Safari</span></span>

## <a name="additional-resources"></a><span data-ttu-id="63b1a-194">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="63b1a-194">Additional resources</span></span>

- [<span data-ttu-id="63b1a-195">Översikt över elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="63b1a-195">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="63b1a-196">Formeldesigner i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="63b1a-196">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)
- [<span data-ttu-id="63b1a-197">Monaco-redigerare</span><span class="sxs-lookup"><span data-stu-id="63b1a-197">Monaco editor</span></span>](https://microsoft.github.io/monaco-editor)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]