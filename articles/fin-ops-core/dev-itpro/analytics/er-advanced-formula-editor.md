---
title: Avancerad formelredigerare för elektronisk rapportering
description: I det här avsnittet beskrivs hur avancerad formelredigerare kan användas för att konfigurera uttryck i ER-modellmappning och formatkomponenter.
author: NickSelin
ms.date: 06/17/2021
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
ms.openlocfilehash: f7f80928e1d3f5d4892f72d4bd2fd09b70a26c1f
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270717"
---
# <a name="electronic-reporting-advanced-formula-editor"></a><span data-ttu-id="b18af-103">Avancerad formelredigerare för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="b18af-103">Electronic reporting advanced formula editor</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b18af-104">Förutom [elektronisk rapportering](general-electronic-reporting.md)[formelredigeraren](general-electronic-reporting-formula-designer.md) kan du använda den avancerade elektroniska rapportering formelredigeraren för att förbättra upplevelsen av konfigurering av ER-uttryck.</span><span class="sxs-lookup"><span data-stu-id="b18af-104">In addition to the [Electronic reporting](general-electronic-reporting.md) [formula editor](general-electronic-reporting-formula-designer.md), you can use the advanced Electronic reporting formula editor to improve the experience of configuring Electronic reporting (ER) expressions.</span></span> <span data-ttu-id="b18af-105">Den avancerade redigeraren är webbläsarbaserad och utrustad med hjälp av [Monaco redigeraren](https://microsoft.github.io/monaco-editor).</span><span class="sxs-lookup"><span data-stu-id="b18af-105">The advanced editor is browser-based and powered by the [Monaco editor](https://microsoft.github.io/monaco-editor).</span></span> <span data-ttu-id="b18af-106">De mest använda avancerade redigeringsfunktionerna beskrivs i det här avsnittet:</span><span class="sxs-lookup"><span data-stu-id="b18af-106">The most commonly used advanced editor features are described in this topic:</span></span>

- [<span data-ttu-id="b18af-107">Automatisk kodformatering</span><span class="sxs-lookup"><span data-stu-id="b18af-107">Code autoformatting</span></span>](#Autoformatting)
- [<span data-ttu-id="b18af-108">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="b18af-108">IntelliSense</span></span>](#IntelliSense)
- [<span data-ttu-id="b18af-109">Kodslutförande</span><span class="sxs-lookup"><span data-stu-id="b18af-109">Code completion</span></span>](#CodeCompletion)
- [<span data-ttu-id="b18af-110">Kodnavigering</span><span class="sxs-lookup"><span data-stu-id="b18af-110">Code navigation</span></span>](#CodeNavigation)
- [<span data-ttu-id="b18af-111">Kodstrukturering</span><span class="sxs-lookup"><span data-stu-id="b18af-111">Code structuring</span></span>](#CodeStructuring)
- [<span data-ttu-id="b18af-112">Sök och Ersätt</span><span class="sxs-lookup"><span data-stu-id="b18af-112">Find and replace</span></span>](#FindAndReplace)
- [<span data-ttu-id="b18af-113">Datainklistring</span><span class="sxs-lookup"><span data-stu-id="b18af-113">Data pasting</span></span>](#DataPasting)
- [<span data-ttu-id="b18af-114">Syntaxfärgning</span><span class="sxs-lookup"><span data-stu-id="b18af-114">Syntax colorization</span></span>](#SyntaxColorization)

## <a name=""></a><span data-ttu-id="b18af-115"><a name="ActivateAdvEditor">Aktivera avancerad formelredigerare</a></span><span class="sxs-lookup"><span data-stu-id="b18af-115"><a name="ActivateAdvEditor">Activate the advanced formula editor</a></span></span>

<span data-ttu-id="b18af-116">Gör på följande sätt när du vill börja använda den avancerade formelredigeraren i din instans av Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="b18af-116">Complete the following steps to start using the advanced formula editor in your instance of Microsoft Dynamics 365 Finance.</span></span>

1.  <span data-ttu-id="b18af-117">Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="b18af-117">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2.  <span data-ttu-id="b18af-118">På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.</span><span class="sxs-lookup"><span data-stu-id="b18af-118">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3.  <span data-ttu-id="b18af-119">I dialogrutan **Användarparametrar** i avsnittet **Körningsspårning** ska du ange parametern **Aktivera avancerad formelredigerare** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b18af-119">In the **User parameters** dialog box, in the **Execution tracing** section, set the **Enable advanced formula editor** parameter to **Yes**.</span></span>

<span data-ttu-id="b18af-120">[![Dialogrutan användarparametrar, Aktivera avancerad formelredigerare parameter markerad](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span><span class="sxs-lookup"><span data-stu-id="b18af-120">[![User parameters dialog box, Enable advanced formula editor parameter highlighted](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span></span>

> [!NOTE]
> <span data-ttu-id="b18af-121">Tänk på att den här parametern är specifik för användaren och för företagsspecifika.</span><span class="sxs-lookup"><span data-stu-id="b18af-121">Be aware that this parameter is user specific and company specific.</span></span>

<span data-ttu-id="b18af-122">Från och med Microsoft Dynamics 365 Finance version 10.0.19 kan du styra vilken ER-formelredigerare som erbjuds som standard.</span><span class="sxs-lookup"><span data-stu-id="b18af-122">Starting in Microsoft Dynamics 365 Finance version 10.0.19, you can control what ER formula editor is offered by default.</span></span> <span data-ttu-id="b18af-123">Gör på följande sätt om du vill aktivera den avancerade receptredigeraren för alla användare och företag i den aktuella ekonomiinstansen.</span><span class="sxs-lookup"><span data-stu-id="b18af-123">Complete the following steps to enable the advanced formula editor for all users and companies of the current Finance instance.</span></span>

1.  <span data-ttu-id="b18af-124">Öppna arbetsytan **Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="b18af-124">Open the **Feature management** workspace.</span></span>
2.  <span data-ttu-id="b18af-125">Sök efter och välj funktionen **Ställ in ER avancerade formelredigerare som standard för alla användare** i listan och välj **Aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="b18af-125">Find and select the feature **Set the ER advanced formula editor as the default one for all users** in the list, and then select **Enable now**.</span></span>
3.  <span data-ttu-id="b18af-126">Gå till **Organisationsadministration** > **Elektronisk rapportering** > **Konfigurationer**.</span><span class="sxs-lookup"><span data-stu-id="b18af-126">Go to **Organization administration** > **Electronic reporting** > **Configurations**.</span></span>
4.  <span data-ttu-id="b18af-127">På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** i gruppen **Avancerad inställningar** markerar du **Använd parametrar**.</span><span class="sxs-lookup"><span data-stu-id="b18af-127">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
5.  <span data-ttu-id="b18af-128">I dialogrutan **Användarparametrar** hitta parametern **Inaktivera avancerad formelredigerare** och kontrollera att den anges till **Nej**.</span><span class="sxs-lookup"><span data-stu-id="b18af-128">In the **User parameters** dialog box, find the **Disable advanced formula editor** parameter and verify that it is set to **No**.</span></span>

<span data-ttu-id="b18af-129">[![Dialogrutan användarparametrar, Inaktivera avancerad formelredigerare parameter markerad](./media/ER-AdvEditor-Activate2.png)](./media/ER-AdvEditor-Activate2.png)</span><span class="sxs-lookup"><span data-stu-id="b18af-129">[![User parameters dialog box, Disable advanced formula editor parameter highlighted](./media/ER-AdvEditor-Activate2.png)](./media/ER-AdvEditor-Activate2.png)</span></span>

> [!NOTE]
> <span data-ttu-id="b18af-130">Värdena i parametrarna **Aktivera avancerad formelredigerare** och **Inaktivera avancerad formelredigerare** hålls separerade för varje användare och erbjuds i dialogrutan **Användarparametrar** beroende på statusen för funktionen **Ställ in ER-avancerad formelredigerare som standard för alla användare**.</span><span class="sxs-lookup"><span data-stu-id="b18af-130">The values of the parameters **Enable advanced formula editor** and **Disable advanced formula editor** are kept separate for each user and offered on the **User parameters** dialog box depending on the status of the **Set the ER advanced formula editor as the default one for all users** feature.</span></span>

## <a name=""></a><span data-ttu-id="b18af-131"><a name="Autoformatting">Automatisk kodformatering</a></span><span class="sxs-lookup"><span data-stu-id="b18af-131"><a name="Autoformatting">Code autoformatting</a></span></span>

<span data-ttu-id="b18af-132">När du skriver ett komplext uttryck som består av flera kodrader, kommer indraget för en ny rad automatiskt att baseras på indraget för föregående rad.</span><span class="sxs-lookup"><span data-stu-id="b18af-132">When you write a complex expression that consists of multiple rows of code, the indentation of a new entered line will be automatic based on the indentation of the previous row.</span></span> <span data-ttu-id="b18af-133">Du kan markera rader och ändra deras indrag genom att skriva **tabb** eller **Skift + tabb**.</span><span class="sxs-lookup"><span data-stu-id="b18af-133">You can select lines and change their indentation by typing **Tab** or **Shift+Tab**.</span></span>

<span data-ttu-id="b18af-134">[![ER-formelredigeraren som visar att markera rader och ändrar indrag](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span><span class="sxs-lookup"><span data-stu-id="b18af-134">[![ER formula editor gif showing selecting lines and changing the indentation](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span></span>

<span data-ttu-id="b18af-135">Med automatisk formatering kan du behålla hela uttrycket väl formaterat så att det blir enklare att underhålla och förenkla förståelsen av den konfigurerade logiken.</span><span class="sxs-lookup"><span data-stu-id="b18af-135">Autoformatting allows you to keep the entire expression well formatted to make further maintenance easier and to simplify understanding of the configured logic.</span></span>

## <a name=""></a><span data-ttu-id="b18af-136"><a name="IntelliSense">IntelliSense</a></span><span class="sxs-lookup"><span data-stu-id="b18af-136"><a name="IntelliSense">IntelliSense</a></span></span>

<span data-ttu-id="b18af-137">Med hjälp av redigeraren för ordkomplettering kan du skriva uttryck snabbare och undvika skrivfel.</span><span class="sxs-lookup"><span data-stu-id="b18af-137">The editor provides word completion to help you write expression faster and avoid typos.</span></span> <span data-ttu-id="b18af-138">När du börjar lägga till ny text innehåller redigeraren automatiskt en lista med funktioner som kan användas i ER-funktioner som innehåller de tecken du har angett.</span><span class="sxs-lookup"><span data-stu-id="b18af-138">When you start adding new text, the editor automatically offers a list of functions supported in ER functions that contain the characters you have entered.</span></span> <span data-ttu-id="b18af-139">Du kan även utlösa IntelliSense på valfri plats i ett konfigurerat uttryck genom att skriva **Ctrl+Blanksteg**.</span><span class="sxs-lookup"><span data-stu-id="b18af-139">You can also trigger IntelliSense in any place of a configured expression by typing **Ctrl+Space**.</span></span>

<span data-ttu-id="b18af-140">[![ER-formelredigeraren som visar utlösande IntelliSense](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span><span class="sxs-lookup"><span data-stu-id="b18af-140">[![ER formula editor gif showing triggering IntelliSense](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span></span>

## <a name=""></a><span data-ttu-id="b18af-141"><a name="CodeCompletion">Kodslutförande</a></span><span class="sxs-lookup"><span data-stu-id="b18af-141"><a name="CodeCompletion">Code completion</a></span></span>

<span data-ttu-id="b18af-142">I redigeraren skapas automatiskt kodslutförande av:</span><span class="sxs-lookup"><span data-stu-id="b18af-142">The editor automatically provides code completion by:</span></span>

- <span data-ttu-id="b18af-143">Infoga en avslutande hakparentes när en hakparentes anges, så att markören innanför hakparenteserna hålls.</span><span class="sxs-lookup"><span data-stu-id="b18af-143">Inserting a closing bracket when an opening  bracket is entered, keeping the cursor inside the brackets.</span></span>
- <span data-ttu-id="b18af-144">Infoga det andra citattecknet när det första anges och behåll markören inuti citattecken.</span><span class="sxs-lookup"><span data-stu-id="b18af-144">Inserting the second quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>
- <span data-ttu-id="b18af-145">Infoga det andra dubla citattecknet när det första anges och behåll markören inuti citattecken.</span><span class="sxs-lookup"><span data-stu-id="b18af-145">Inserting the second double quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>

<span data-ttu-id="b18af-146">[![ER-formelredigeraren som visar redigeraren automatiskt som tillhandahåller kodslutförande](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span><span class="sxs-lookup"><span data-stu-id="b18af-146">[![ER formula editor gif showing the editor automatically providing code completion](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span></span>

<span data-ttu-id="b18af-147">När du pekar på den skrivna hakparentesen markeras automatiskt den andra hakparentesen för att visa den konstruktion som de stöder.</span><span class="sxs-lookup"><span data-stu-id="b18af-147">When you point to the typed bracket, the second bracket of this pair is automatically highlighted to show the construct that they support.</span></span>

## <a name=""></a><span data-ttu-id="b18af-148"><a name="CodeNavigation">Kodnavigering</a></span><span class="sxs-lookup"><span data-stu-id="b18af-148"><a name="CodeNavigation">Code navigation</a></span></span>

<span data-ttu-id="b18af-149">Du kan hitta nödvändiga symboler eller rader i uttrycket genom att skriva kommandot **gå till** med hjälp av kommandoraden eller snabbmenyn.</span><span class="sxs-lookup"><span data-stu-id="b18af-149">You can locate required symbols or lines in your expression by typing the **Go to** command using the command palette or the context menu.</span></span>

<span data-ttu-id="b18af-150">Om du till exempel vill hoppa till rad **8** gör du så här:</span><span class="sxs-lookup"><span data-stu-id="b18af-150">For example, to jump to line **8**, do the following:</span></span>

- <span data-ttu-id="b18af-151">Tryck på **Ctrl+G**, ange värdet **8** och tryck på **retur**.</span><span class="sxs-lookup"><span data-stu-id="b18af-151">Press **Ctrl+G**, enter the value **8**, and then press **Enter**.</span></span>

  <span data-ttu-id="b18af-152">- eller -</span><span class="sxs-lookup"><span data-stu-id="b18af-152">-or-</span></span>

- <span data-ttu-id="b18af-153">Tryck på **F1**, skriv **G**, välj **Gå till rad**, ange värdet **8** och tryck på **retur**.</span><span class="sxs-lookup"><span data-stu-id="b18af-153">Press **F1**, type **G**, select **Go to line**, enter the value **8**, and the press **Enter**.</span></span>

<span data-ttu-id="b18af-154">[![ER-formelredigeraren som visar hur du hittar delar av ett uttryck med hjälp av kommandoskala](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span><span class="sxs-lookup"><span data-stu-id="b18af-154">[![ER formula editor gif showing how to locate parts of an expression using the command palette](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span></span>

## <a name=""></a><span data-ttu-id="b18af-155"><a name="CodeStructuring">Kodstrukturering</a></span><span class="sxs-lookup"><span data-stu-id="b18af-155"><a name="CodeStructuring">Code structuring</a></span></span>

<span data-ttu-id="b18af-156">Koden för vissa funktioner, t.ex. [IF](er-functions-logical-if.md) eller [CASE](er-functions-logical-case.md), struktureras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b18af-156">The code for some functions, such as [IF](er-functions-logical-if.md) or [CASE](er-functions-logical-case.md), is automatically structured.</span></span> <span data-ttu-id="b18af-157">Du kan expandera och komprimera alla vikbara regioner i koden om du vill minska den redigerbara delen av ett uttryck om du bara vill fokusera på det stycke kod som kräver din uppmärksamhet.</span><span class="sxs-lookup"><span data-stu-id="b18af-157">You can expand and collapse any or all of the folding regions of this code to reduce the editable part of an expression in order to focus on only  thepiece of code that requires your attention.</span></span> <span data-ttu-id="b18af-158">Kommandona växla vikning/vika upp kan användas för det.</span><span class="sxs-lookup"><span data-stu-id="b18af-158">The toggle fold/unfold commands can be used for that.</span></span>

<span data-ttu-id="b18af-159">Om du till exempel vill vika alla områden gör du så här:</span><span class="sxs-lookup"><span data-stu-id="b18af-159">For example, to fold all regions, do the following:</span></span>

- <span data-ttu-id="b18af-160">Tryck **Ctrl+K**</span><span class="sxs-lookup"><span data-stu-id="b18af-160">Press **Ctrl+K**</span></span>

  <span data-ttu-id="b18af-161">- eller -</span><span class="sxs-lookup"><span data-stu-id="b18af-161">-or-</span></span>

- <span data-ttu-id="b18af-162">Tryck **F1**, tryck **FO**, välj **Vik alla** och tryck på **retur**</span><span class="sxs-lookup"><span data-stu-id="b18af-162">Press **F1**, press **FO**, select **Fold all**, and then press **Enter**</span></span>

<span data-ttu-id="b18af-163">Om du till exempel vill vika upp alla områden gör du så här:</span><span class="sxs-lookup"><span data-stu-id="b18af-163">To unfold all regions, do the following:</span></span>

- <span data-ttu-id="b18af-164">Tryck **Ctrl+J**</span><span class="sxs-lookup"><span data-stu-id="b18af-164">Press **Ctrl+J**</span></span>

  <span data-ttu-id="b18af-165">- eller -</span><span class="sxs-lookup"><span data-stu-id="b18af-165">-or-</span></span>
  
- <span data-ttu-id="b18af-166">Tryck **F1**, skriv **UN**, välj **Vik upp alla** och tryck på **retur**</span><span class="sxs-lookup"><span data-stu-id="b18af-166">Press **F1**, type **UN**, select **Unfold all**, and then press **Enter**</span></span>

<span data-ttu-id="b18af-167">[![ER-formelredigeraren som visar koden viks ut](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span><span class="sxs-lookup"><span data-stu-id="b18af-167">[![ER formula editor gif showing code being unfolded](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span></span>

## <a name=""></a><span data-ttu-id="b18af-168"><a name="FindAndReplace">Sök och Ersätt</a></span><span class="sxs-lookup"><span data-stu-id="b18af-168"><a name="FindAndReplace">Find and replace</a></span></span>

<span data-ttu-id="b18af-169">Om du vill söka efter förekomster av viss text, markerar du texten i uttrycket och gör följande:</span><span class="sxs-lookup"><span data-stu-id="b18af-169">To find occurrences of certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="b18af-170">Tryck på **Ctrl+F** och tryck sedan på **F3** för att söka efter nästa förekomst av den markerade texten **Shift+F3** för att hitta föregående förekomst.</span><span class="sxs-lookup"><span data-stu-id="b18af-170">Press **Ctrl+F** and then press **F3** to find the next occurrence of the selected text, or press **Shift+F3** to find the previous occurrence.</span></span>

  <span data-ttu-id="b18af-171">- eller -</span><span class="sxs-lookup"><span data-stu-id="b18af-171">-or-</span></span>
  
- <span data-ttu-id="b18af-172">Tryck på **F1**, skriv **F** och välj sedan det alternativ som krävs för att hitta den markerade texten.</span><span class="sxs-lookup"><span data-stu-id="b18af-172">Press **F1**, type **F**, and then select the required option to find the selected text.</span></span>

<span data-ttu-id="b18af-173">Om du vill ersätta förekomster av viss text, markerar du texten i uttrycket och gör följande:</span><span class="sxs-lookup"><span data-stu-id="b18af-173">To replace occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="b18af-174">Tryck **Ctrl+H**.</span><span class="sxs-lookup"><span data-stu-id="b18af-174">Press **Ctrl+H**.</span></span> <span data-ttu-id="b18af-175">Ange alternativ text och välj ersättningsalternativet om du vill ersätta den markerade texten eller alla förekomster av den här texten i det aktuella uttrycket.</span><span class="sxs-lookup"><span data-stu-id="b18af-175">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

  <span data-ttu-id="b18af-176">- eller -</span><span class="sxs-lookup"><span data-stu-id="b18af-176">-or-</span></span>
  
- <span data-ttu-id="b18af-177">Tryck på **F1**, skriv **R** och välj sedan det alternativ som krävs för att ersätta den markerade texten.</span><span class="sxs-lookup"><span data-stu-id="b18af-177">Press **F1**, type **R**, and then select the required option to replace the selected text.</span></span> <span data-ttu-id="b18af-178">Ange alternativ text och välj ersättningsalternativet om du vill ersätta den markerade texten eller alla förekomster av den här texten i det aktuella uttrycket.</span><span class="sxs-lookup"><span data-stu-id="b18af-178">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

<span data-ttu-id="b18af-179">Om du vill ändra alla förekomster av viss text, markerar du texten i uttrycket och gör följande:</span><span class="sxs-lookup"><span data-stu-id="b18af-179">To change all occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="b18af-180">Tryck på **Ctrl+F2** och ange alternativ text.</span><span class="sxs-lookup"><span data-stu-id="b18af-180">Press **Ctrl+F2** and then enter the alternative text.</span></span>

  <span data-ttu-id="b18af-181">- eller -</span><span class="sxs-lookup"><span data-stu-id="b18af-181">-or-</span></span>
  
- <span data-ttu-id="b18af-182">Tryck på **F1**, skriv **C** och välj sedan det alternativ som krävs för att ändra den markerade texten.</span><span class="sxs-lookup"><span data-stu-id="b18af-182">Press **F1**, type **C**, and then select the required option to change the selected text.</span></span> <span data-ttu-id="b18af-183">Ange alternativ text.</span><span class="sxs-lookup"><span data-stu-id="b18af-183">Enter the alternative text.</span></span>

<span data-ttu-id="b18af-184">[![ER-formelredigeraren som visar hitta och ersätta](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span><span class="sxs-lookup"><span data-stu-id="b18af-184">[![ER formula editor gif showing find and replace](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span></span>

## <a name=""></a><span data-ttu-id="b18af-185"><a name="DataPasting">Datakällor och funktioner klistra in</a></span><span class="sxs-lookup"><span data-stu-id="b18af-185"><a name="DataPasting">Data sources and functions pasting</a></span></span>

<span data-ttu-id="b18af-186">Du kan välja **Lägg till data källa** som klistras in i det aktuella uttrycket en datakälla som är markerad på den vänstra panelen i **datakällan**.</span><span class="sxs-lookup"><span data-stu-id="b18af-186">You can select **Add data source**, which pastes to the current expression a data source that is currently selected on the **Data source** left panel.</span></span> <span data-ttu-id="b18af-187">Du kan välja **Lägg till funktion** på liknande sätt som klistras in i det aktuella uttrycket en funktion som är markerad på den högra panelen i **funktioner**.</span><span class="sxs-lookup"><span data-stu-id="b18af-187">Simlilarly, you can select **Add function**, which pastes to the current expression a function that is currently selected on the **Functions** right panel.</span></span> <span data-ttu-id="b18af-188">Om du använder ER-formelredigeraren klistras en markerad funktion eller en markerad datakälla alltid in i slutet av det konfigurerade uttrycket.</span><span class="sxs-lookup"><span data-stu-id="b18af-188">If you use the ER formula editor, a selected function or a selected data source will always be pasted to the end of the configured expression.</span></span> <span data-ttu-id="b18af-189">Om du använder avancerad ER-formelredigeraren klistras en markerad funktion eller en markerad datakälla in i någon del av det konfigurerade uttrycket.</span><span class="sxs-lookup"><span data-stu-id="b18af-189">When you use the advanced ER formula editor, a selected function or a selected data source can be pasted to any part of the configured expression.</span></span> <span data-ttu-id="b18af-190">Du måste då använda markören för att ange var du vill klistra in informationen.</span><span class="sxs-lookup"><span data-stu-id="b18af-190">You will need to use the cursor to specify where you want to paste the data.</span></span>

<span data-ttu-id="b18af-191">[![ER-formelredigeraren som visar hur du lägger till en datakälla och klistrar in en funktion](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span><span class="sxs-lookup"><span data-stu-id="b18af-191">[![ER formula editor gif showing adding a data source and pasting a function](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span></span>

## <a name=""></a><span data-ttu-id="b18af-192"><a name="SyntaxColorization">Syntaxfärgning</a></span><span class="sxs-lookup"><span data-stu-id="b18af-192"><a name="SyntaxColorization">Syntax colorization</a></span></span>

<span data-ttu-id="b18af-193">För närvarande används olika färger för att belysa följande delar av uttryck:</span><span class="sxs-lookup"><span data-stu-id="b18af-193">Currently, different colors are used to highlight the following parts of expressions:</span></span>

- <span data-ttu-id="b18af-194">Texten inom dubbla hakparenteser som kan representera ett etikett-ID för en textkonstant.</span><span class="sxs-lookup"><span data-stu-id="b18af-194">The text in double brackets that can represent a label ID of a text constant.</span></span>

<span data-ttu-id="b18af-195">[![ER-formelredigeraren](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span><span class="sxs-lookup"><span data-stu-id="b18af-195">[![ER formula editor](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span></span>

## <a name="limitations"></a><span data-ttu-id="b18af-196">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="b18af-196">Limitations</span></span>

<span data-ttu-id="b18af-197">Redigeraren stöds för närvarande i följande webbläsare:</span><span class="sxs-lookup"><span data-stu-id="b18af-197">The editor is currently supported in the following web browsers:</span></span>

- <span data-ttu-id="b18af-198">Chrome</span><span class="sxs-lookup"><span data-stu-id="b18af-198">Chrome</span></span>
- <span data-ttu-id="b18af-199">Edge</span><span class="sxs-lookup"><span data-stu-id="b18af-199">Edge</span></span>
- <span data-ttu-id="b18af-200">Firefox</span><span class="sxs-lookup"><span data-stu-id="b18af-200">Firefox</span></span>
- <span data-ttu-id="b18af-201">Opera</span><span class="sxs-lookup"><span data-stu-id="b18af-201">Opera</span></span>
- <span data-ttu-id="b18af-202">Safari</span><span class="sxs-lookup"><span data-stu-id="b18af-202">Safari</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b18af-203">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b18af-203">Additional resources</span></span>

- [<span data-ttu-id="b18af-204">Översikt över elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="b18af-204">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="b18af-205">Formeldesigner i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="b18af-205">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)
- [<span data-ttu-id="b18af-206">Monaco-redigerare</span><span class="sxs-lookup"><span data-stu-id="b18af-206">Monaco editor</span></span>](https://microsoft.github.io/monaco-editor)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
