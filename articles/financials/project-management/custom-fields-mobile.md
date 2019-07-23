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
ms.sourcegitcommit: 19859d8566a8c7840066b2c10c6b08b67f1b83f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2019
ms.locfileid: "1618006"
---
# <a name="implement-custom-fields-for-the-microsoft-dynamics-365-project-timesheet-mobile-app-on-ios-and-android"></a><span data-ttu-id="175cc-103">Implementera anpassade fält för Microsoft Dynamics 365 Project Timesheet-mobilappen på iOS och Android</span><span class="sxs-lookup"><span data-stu-id="175cc-103">Implement custom fields for the Microsoft Dynamics 365 Project Timesheet mobile app on iOS and Android</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="175cc-104">Det här avsnittet innehåller vanliga mönster för hur du använder tillägg för att implementera anpassade fält.</span><span class="sxs-lookup"><span data-stu-id="175cc-104">This topic provides common patterns for using extensions to implement custom fields.</span></span> <span data-ttu-id="175cc-105">Följande avsnitt ingår:</span><span class="sxs-lookup"><span data-stu-id="175cc-105">The following topics are covered:</span></span>

- <span data-ttu-id="175cc-106">De olika datatyper som det anpassade fältramverket stöder</span><span class="sxs-lookup"><span data-stu-id="175cc-106">The various data types that the custom field framework supports</span></span>
- <span data-ttu-id="175cc-107">Så här visar du skrivskyddade eller redigerbara fält i tidrapportposter, och sparar de värden som användaren anger tillbaka i databasen</span><span class="sxs-lookup"><span data-stu-id="175cc-107">How to show read-only or editable fields on timesheet entries, and save user-provided values back to the database</span></span>
- <span data-ttu-id="175cc-108">Visa skrivskyddade fält i tidrapporthuvudet</span><span class="sxs-lookup"><span data-stu-id="175cc-108">How to show read-only fields on the timesheet header</span></span>
- <span data-ttu-id="175cc-109">Så här integrerar du annan anpassad affärslogik så här anger du standardvärden i fält och gör ytterligare valideringar</span><span class="sxs-lookup"><span data-stu-id="175cc-109">How to integrate other custom business logic to enter default values in fields and do additional validation</span></span>

## <a name="audience"></a><span data-ttu-id="175cc-110">Målgrupp</span><span class="sxs-lookup"><span data-stu-id="175cc-110">Audience</span></span>

<span data-ttu-id="175cc-111">Det här avsnittet är avsett för utvecklare som integrerar sina anpassade fält i Microsoft Dynamics 365 Project Timesheet-mobilappen som är tillgängligt för Apple iOS och Google Android.</span><span class="sxs-lookup"><span data-stu-id="175cc-111">This topic is intended for developers who are integrating their custom fields into the Microsoft Dynamics 365 Project Timesheet mobile application that is available for Apple iOS and Google Android.</span></span> <span data-ttu-id="175cc-112">Antagandet är att läsarna är bekant med funktionen för X ++-utveckling och funktionen för projekttidrapporter.</span><span class="sxs-lookup"><span data-stu-id="175cc-112">The assumption is that readers are familiar with X++ development and project timesheet functionality.</span></span>

## <a name="data-contract--tstimesheetcustomfield-x-class"></a><span data-ttu-id="175cc-113">Datakontrakt – TSTimesheetCustomField X++-klass</span><span class="sxs-lookup"><span data-stu-id="175cc-113">Data contract – TSTimesheetCustomField X++ class</span></span>

<span data-ttu-id="175cc-114">**TSTimesheetCustomField**-klassen är X ++-datakontraktklassen som representerar information om ett anpassat fält för funktionen tidrapport.</span><span class="sxs-lookup"><span data-stu-id="175cc-114">The **TSTimesheetCustomField** class is the X++ data contract class that represents information about a custom field for timesheet functionality.</span></span> <span data-ttu-id="175cc-115">Listor i anpassade fält skickas till både TSTimesheetDetails datakontrakt och TSTimesheetEntry datakontrakt för att visa anpassade fält i mobilappen.</span><span class="sxs-lookup"><span data-stu-id="175cc-115">Lists of the custom field objects are passed on both the TSTimesheetDetails data contract and the TSTimesheetEntry data contract to show custom fields in the mobile app.</span></span>

- <span data-ttu-id="175cc-116">**TSTimesheetDetails** - kontrakt för tidrapporthuvudet.</span><span class="sxs-lookup"><span data-stu-id="175cc-116">**TSTimesheetDetails** - The timesheet header contract.</span></span>
- <span data-ttu-id="175cc-117">**TSTimesheetEntry**- tidrapporten för transaktionskontraktet.</span><span class="sxs-lookup"><span data-stu-id="175cc-117">**TSTimesheetEntry** - The timesheet transaction contract.</span></span> <span data-ttu-id="175cc-118">Grupper av dessa objekt som har samma projektinformation och **timesheetLineRecId**-värde utgör en rad.</span><span class="sxs-lookup"><span data-stu-id="175cc-118">Groups of these objects that have the same project information and **timesheetLineRecId** value constitute a line.</span></span>

### <a name="fieldbasetype-types"></a><span data-ttu-id="175cc-119">fieldBaseType (typer)</span><span class="sxs-lookup"><span data-stu-id="175cc-119">fieldBaseType (Types)</span></span>

<span data-ttu-id="175cc-120">Egenskapen **FieldBaseType** för objektet **TsTimesheetCustom** bestämmer vilken typ av fält som visas i appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-120">The **FieldBaseType** property on the **TsTimesheetCustom** object determines the type of the field that appears in the app.</span></span> <span data-ttu-id="175cc-121">Följande **typer** av värden stöds.</span><span class="sxs-lookup"><span data-stu-id="175cc-121">The following **Types** values that are supported.</span></span>

| <span data-ttu-id="175cc-122">Typers värde</span><span class="sxs-lookup"><span data-stu-id="175cc-122">Types value</span></span> | <span data-ttu-id="175cc-123">Typ</span><span class="sxs-lookup"><span data-stu-id="175cc-123">Type</span></span>              | <span data-ttu-id="175cc-124">Anteckningar</span><span class="sxs-lookup"><span data-stu-id="175cc-124">Notes</span></span> |
|-------------|-------------------|-------|
| <span data-ttu-id="175cc-125">0</span><span class="sxs-lookup"><span data-stu-id="175cc-125">0</span></span>           | <span data-ttu-id="175cc-126">Sträng (och fasttexttyp)</span><span class="sxs-lookup"><span data-stu-id="175cc-126">String (and Enum)</span></span> | <span data-ttu-id="175cc-127">Fältet visas som ett textfält.</span><span class="sxs-lookup"><span data-stu-id="175cc-127">The field appears as a text field.</span></span> |
| <span data-ttu-id="175cc-128">1</span><span class="sxs-lookup"><span data-stu-id="175cc-128">1</span></span>           | <span data-ttu-id="175cc-129">Heltal</span><span class="sxs-lookup"><span data-stu-id="175cc-129">Integer</span></span>           | <span data-ttu-id="175cc-130">Värdet visas som ett tal utan decimaler.</span><span class="sxs-lookup"><span data-stu-id="175cc-130">The value is shown as a number without decimal places.</span></span> |
| <span data-ttu-id="175cc-131">2</span><span class="sxs-lookup"><span data-stu-id="175cc-131">2</span></span>           | <span data-ttu-id="175cc-132">Realtal</span><span class="sxs-lookup"><span data-stu-id="175cc-132">Real</span></span>              | <span data-ttu-id="175cc-133">Värdet visas som ett tal utan decimaler.</span><span class="sxs-lookup"><span data-stu-id="175cc-133">The value is shown as a number that has decimal places.</span></span><p><span data-ttu-id="175cc-134">Om du vill visa det verkliga värdet som en valuta i appen använder du egenskapen **fieldExtenededType**.</span><span class="sxs-lookup"><span data-stu-id="175cc-134">To show the real value as a currency in the app, use the **fieldExtenededType** property.</span></span> <span data-ttu-id="175cc-135">Du kan använda egenskapen **numberOfDecimals** för att ange antalet decimaler som visas.</span><span class="sxs-lookup"><span data-stu-id="175cc-135">You can use the **numberOfDecimals** property to set the number of decimal places that are shown.</span></span></p> |
| <span data-ttu-id="175cc-136">3</span><span class="sxs-lookup"><span data-stu-id="175cc-136">3</span></span>           | <span data-ttu-id="175cc-137">Datum</span><span class="sxs-lookup"><span data-stu-id="175cc-137">Date</span></span>              | <span data-ttu-id="175cc-138">Datumformat bestäms av användarens inställning för **Datum-, tids- och nummerformat** som anges under **inställningar för språk- och land/region** i **användaralternativ**.</span><span class="sxs-lookup"><span data-stu-id="175cc-138">Date formats are determined by the user's **Date, times, and number format** setting that is specified under **Language and country/region preference** in **User options**.</span></span> |
| <span data-ttu-id="175cc-139">4</span><span class="sxs-lookup"><span data-stu-id="175cc-139">4</span></span>           | <span data-ttu-id="175cc-140">Boolesk</span><span class="sxs-lookup"><span data-stu-id="175cc-140">Boolean</span></span>           | |
| <span data-ttu-id="175cc-141">15</span><span class="sxs-lookup"><span data-stu-id="175cc-141">15</span></span>          | <span data-ttu-id="175cc-142">GUID</span><span class="sxs-lookup"><span data-stu-id="175cc-142">GUID</span></span>              | |
| <span data-ttu-id="175cc-143">16</span><span class="sxs-lookup"><span data-stu-id="175cc-143">16</span></span>          | <span data-ttu-id="175cc-144">Int64</span><span class="sxs-lookup"><span data-stu-id="175cc-144">Int64</span></span>             | |

- <span data-ttu-id="175cc-145">Om egenskapen **stringOptions** inte finns i **TSTimesheetCustomField**-objektet får du ett fritextfält till användaren.</span><span class="sxs-lookup"><span data-stu-id="175cc-145">If the **stringOptions** property isn't provided on the **TSTimesheetCustomField** object, a free-text field is provided to the user.</span></span>

    <span data-ttu-id="175cc-146">Egenskapen **stringLength** kan användas för att ange den maximala stränglängd som användarna kan ange.</span><span class="sxs-lookup"><span data-stu-id="175cc-146">The **stringLength** property can be used to set the maximum string length that users can enter.</span></span>

- <span data-ttu-id="175cc-147">Om egenskapen **stringOptions** finns i **TSTimesheetCustomField**-objektet är dessa element de enda värden som användarna kan välja med hjälp av alternativ knappar (alternativknappar).</span><span class="sxs-lookup"><span data-stu-id="175cc-147">If the **stringOptions** property is provided on the **TSTimesheetCustomField** object, those list elements are the only values that users can select by using option buttons (radio buttons).</span></span>

    <span data-ttu-id="175cc-148">I det här fallet kan strängfältet användas som ett uppräkningsvärde för användarpostens syfte.</span><span class="sxs-lookup"><span data-stu-id="175cc-148">In this case, the string field can act as an enum value for the purpose of user entry.</span></span> <span data-ttu-id="175cc-149">Om du vill spara värdet i databasen som en fasttexttyp mappar du strängvärdet manuellt till uppräkningsvärdet innan du sparar till databasen med hjälp av kommandokedjan (se kommandot "Använd kedja av i klassen TSTimesheetEntryService för att spara en tidrapportpost från appen tillbaka till databasen" längre fram i det här avsnittet för ett exempel).</span><span class="sxs-lookup"><span data-stu-id="175cc-149">To save the value to the database as an enum, manually map the string value back to the enum value before you save to the database by using chain of command (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</span></span>

### <a name="fieldextendedtype-tscustomfieldextendedtype"></a><span data-ttu-id="175cc-150">fieldExtendedType (TSCustomFieldExtendedType)</span><span class="sxs-lookup"><span data-stu-id="175cc-150">fieldExtendedType (TSCustomFieldExtendedType)</span></span>

<span data-ttu-id="175cc-151">Du kan använda den här egenskapen för att formatera verkliga värden som valuta.</span><span class="sxs-lookup"><span data-stu-id="175cc-151">You can use this property to format real values as currency.</span></span> <span data-ttu-id="175cc-152">Den här metoden kan endast användas om **fieldBaseType**-värdet är **Realtal**.</span><span class="sxs-lookup"><span data-stu-id="175cc-152">This approach is applicable only when the **fieldBaseType** value is **Real**.</span></span>

- <span data-ttu-id="175cc-153">**TSCustomFieldExtendedType: ingen** – ingen formatering används.</span><span class="sxs-lookup"><span data-stu-id="175cc-153">**TSCustomFieldExtendedType:None** – No formatting is applied.</span></span>
- <span data-ttu-id="175cc-154">**TSCustomFieldExtendedType::valuta** – formatera värdet som valuta.</span><span class="sxs-lookup"><span data-stu-id="175cc-154">**TSCustomFieldExtendedType::Currency** – Format the value as currency.</span></span>

    <span data-ttu-id="175cc-155">När valutaformatet är aktivt kan fältet **stringValue** användas för att skicka den valutakod som ska visas i appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-155">When currency formatting is active, the **stringValue** field can be used pass the currency code that should be shown in the app.</span></span> <span data-ttu-id="175cc-156">Värdet är ett skrivskyddat värde.</span><span class="sxs-lookup"><span data-stu-id="175cc-156">The value is a read-only value.</span></span>

    <span data-ttu-id="175cc-157">Fältet **realValue** innehåller det belopp som ska sparas i databasen.</span><span class="sxs-lookup"><span data-stu-id="175cc-157">The **realValue** field contains the money amount that should be saved to the database.</span></span>

### <a name="fieldsection-tscustomfieldsection"></a><span data-ttu-id="175cc-158">fieldSection (TSCustomFieldSection)</span><span class="sxs-lookup"><span data-stu-id="175cc-158">fieldSection (TSCustomFieldSection)</span></span>

<span data-ttu-id="175cc-159">Du kan använda den här egenskapen för att ange var det anpassade fältet ska visas i appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-159">You can use this property specify where the custom field should appear in the app.</span></span>

- <span data-ttu-id="175cc-160">**TSCustomFieldSection::huvud** – fältet kommer att visas i avsnittet **Visa fler detaljer** i appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-160">**TSCustomFieldSection::Header** – The field will appear in the **View more details** section in the app.</span></span> <span data-ttu-id="175cc-161">Dessa fält är alltid skrivskyddade.</span><span class="sxs-lookup"><span data-stu-id="175cc-161">These fields are always read-only.</span></span>
- <span data-ttu-id="175cc-162">**TSCustomFieldSection::rad** – fältet kommer att visas efter alla färdiga radfält på tidrapportposter.</span><span class="sxs-lookup"><span data-stu-id="175cc-162">**TSCustomFieldSection::Line** – The field will appear after all the out-of-box line fields on timesheet entries.</span></span> <span data-ttu-id="175cc-163">Dessa fält kan antingen vara redigerbara eller skrivskyddade.</span><span class="sxs-lookup"><span data-stu-id="175cc-163">These fields can be either editable or read-only.</span></span>

### <a name="fieldname-fieldnameshort"></a><span data-ttu-id="175cc-164">fieldName (FieldNameShort)</span><span class="sxs-lookup"><span data-stu-id="175cc-164">fieldName (FieldNameShort)</span></span>

<span data-ttu-id="175cc-165">Den här egenskapen identifierar fältet när värden som programmet tillhandahåller sparas i databasen igen.</span><span class="sxs-lookup"><span data-stu-id="175cc-165">This property identifies the field when values that the app provides are saved back to the database.</span></span>

### <a name="tablename-tablenameshort"></a><span data-ttu-id="175cc-166">tableName (TableNameShort)</span><span class="sxs-lookup"><span data-stu-id="175cc-166">tableName (TableNameShort)</span></span>

<span data-ttu-id="175cc-167">Den här egenskapen identifierar fältet när värden som programmet tillhandahåller sparas i databasen igen.</span><span class="sxs-lookup"><span data-stu-id="175cc-167">This property identifies the field when values that the app provides are saved back to the database.</span></span>

### <a name="iseditable-noyes"></a><span data-ttu-id="175cc-168">isEditable (NoYes)</span><span class="sxs-lookup"><span data-stu-id="175cc-168">isEditable (NoYes)</span></span>

<span data-ttu-id="175cc-169">Ange den här egenskapen till **Ja** för att ange att fältet i avsnittet tidrapportpost ska redigeras av användarna.</span><span class="sxs-lookup"><span data-stu-id="175cc-169">Set this property to **Yes** to specify that the field in the timesheet entry section should be editable by users.</span></span> <span data-ttu-id="175cc-170">Ställ in egenskapen på **Nej** för att skrivskydda fältet.</span><span class="sxs-lookup"><span data-stu-id="175cc-170">Set the property to **No** to make the field read-only.</span></span>

### <a name="ismandatory-noyes"></a><span data-ttu-id="175cc-171">isMandatory (NoYes)</span><span class="sxs-lookup"><span data-stu-id="175cc-171">isMandatory (NoYes)</span></span>

<span data-ttu-id="175cc-172">Ange den här egenskapen till **Ja** för att ange att fältet i avsnittet tidrapportpost ska vara obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="175cc-172">Set this property to **Yes** to specify that the field in the timesheet entry section should be mandatory.</span></span>

### <a name="label-str"></a><span data-ttu-id="175cc-173">etikett (str)</span><span class="sxs-lookup"><span data-stu-id="175cc-173">label (str)</span></span>

<span data-ttu-id="175cc-174">Den här egenskapen anger etiketten som visas i nästa fält i appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-174">This property specifies the label that is shown next the field in the app.</span></span>

### <a name="stringoptions-list-of-strings"></a><span data-ttu-id="175cc-175">stringOptions (lista över strängar)</span><span class="sxs-lookup"><span data-stu-id="175cc-175">stringOptions (List of Strings)</span></span>

<span data-ttu-id="175cc-176">Den här egenskapen används endast om **fieldBaseType** har värdet **Sträng**.</span><span class="sxs-lookup"><span data-stu-id="175cc-176">This property is applicable only when **fieldBaseType** is set to **String**.</span></span> <span data-ttu-id="175cc-177">Om **stringOptions** har angetts, anges de strängvärden som är tillgängliga för markering via alternativknappar (alternativknappar) enligt strängarna i listan.</span><span class="sxs-lookup"><span data-stu-id="175cc-177">If **stringOptions** is set, the string values that are available for selection via option buttons (radio buttons) are specified by the strings in the list.</span></span> <span data-ttu-id="175cc-178">Om det inte finns några strängar tillåts fritextinmatning i strängfältet (se avsnittet "använda en beslutskedja i klassen TSTimesheetEntryService för att spara en tidrapportpost från appen tillbaka till databasen" längre fram i det här avsnittet för ett exempel).</span><span class="sxs-lookup"><span data-stu-id="175cc-178">If no strings are provided, free-text entry in the string field is allowed (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</span></span>

### <a name="stringlength-int"></a><span data-ttu-id="175cc-179">stringLength (int)</span><span class="sxs-lookup"><span data-stu-id="175cc-179">stringLength (int)</span></span>

<span data-ttu-id="175cc-180">Den här egenskapen anger den maximala längden för ett strängfält.</span><span class="sxs-lookup"><span data-stu-id="175cc-180">This property specifies the maximum length for a string field.</span></span> <span data-ttu-id="175cc-181">Det används endast om **fieldBaseType** har värdet **Sträng**.</span><span class="sxs-lookup"><span data-stu-id="175cc-181">It's applicable only when **fieldBaseType** is set to **String**.</span></span>

### <a name="numberofdecimals-int"></a><span data-ttu-id="175cc-182">numberOfDecimals (int)</span><span class="sxs-lookup"><span data-stu-id="175cc-182">numberOfDecimals (int)</span></span>

<span data-ttu-id="175cc-183">Den här egenskapen anger antalet decimaler som visas för ett riktigt fält.</span><span class="sxs-lookup"><span data-stu-id="175cc-183">This property specifies the number of decimal places that are shown for a real field.</span></span> <span data-ttu-id="175cc-184">Det används endast om **fieldBaseType** har värdet **Riktigt**.</span><span class="sxs-lookup"><span data-stu-id="175cc-184">It's applicable only when **fieldBaseType** is set to **Real**.</span></span>

### <a name="ordersequence-int"></a><span data-ttu-id="175cc-185">orderSequence (int)</span><span class="sxs-lookup"><span data-stu-id="175cc-185">orderSequence (int)</span></span>

<span data-ttu-id="175cc-186">Den här egenskapen bestämmer i vilken ordning de anpassade fälten visas i appen när fler än ett anpassat fält anges.</span><span class="sxs-lookup"><span data-stu-id="175cc-186">This property controls the order in which the custom fields are shown in the app when more than one custom field is specified.</span></span> <span data-ttu-id="175cc-187">Fält med lägre nummer visas först.</span><span class="sxs-lookup"><span data-stu-id="175cc-187">Fields that have lower numbers are shown first.</span></span>

### <a name="booleanvalue-boolean"></a><span data-ttu-id="175cc-188">booleanValue (boolesk)</span><span class="sxs-lookup"><span data-stu-id="175cc-188">booleanValue (boolean)</span></span>

<span data-ttu-id="175cc-189">För fält av **boolesk** typ skickar den här egenskapen booleskt värde för fältet mellan servern och appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-189">For fields of the **Boolean** type, this property passes the Boolean value of the field between the server and the app.</span></span>

### <a name="guidvalue-guid"></a><span data-ttu-id="175cc-190">guidValue (guid)</span><span class="sxs-lookup"><span data-stu-id="175cc-190">guidValue (guid)</span></span>

<span data-ttu-id="175cc-191">För fält av **GUID** typ skickar den här egenskapen till den globala unika identifieraren (GUID) för fältet mellan servern och appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-191">For fields of the **GUID** type, this property passes the globally unique identifier (GUID) value of the field between the server and the app.</span></span>

### <a name="int64value-int64"></a><span data-ttu-id="175cc-192">int64Value (Int64)</span><span class="sxs-lookup"><span data-stu-id="175cc-192">int64Value (int64)</span></span>

<span data-ttu-id="175cc-193">För fält av **Int64** typ skickar den här egenskapen Int64 värde för fältet mellan servern och appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-193">For fields of the **Int64** type, this property passes the int64 value of the field between the server and the app.</span></span>

### <a name="intvalue-int"></a><span data-ttu-id="175cc-194">intValue (int)</span><span class="sxs-lookup"><span data-stu-id="175cc-194">intValue (int)</span></span>

<span data-ttu-id="175cc-195">För fält av **Int** typ skickar den här egenskapen int värde för fältet mellan servern och appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-195">For fields of the **Int** type, this property passes the int value of the field between the server and the app.</span></span>

### <a name="realvalue-real"></a><span data-ttu-id="175cc-196">realValue (real)</span><span class="sxs-lookup"><span data-stu-id="175cc-196">realValue (real)</span></span>

<span data-ttu-id="175cc-197">För fält av **Real** typ skickar den här egenskapen real värde för fältet mellan servern och appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-197">For fields of the **Real** type, this property passes the real value of the field between the server and the app .</span></span>

### <a name="stringvalue-str"></a><span data-ttu-id="175cc-198">stringValue (str)</span><span class="sxs-lookup"><span data-stu-id="175cc-198">stringValue (str)</span></span>

<span data-ttu-id="175cc-199">För fält av **Sträng** typ skickar den här egenskapen strängvärde för fältet mellan servern och appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-199">For fields of the **String** type, this property passes the string value of the field between the server and the app.</span></span> <span data-ttu-id="175cc-200">Det används också för fält av **Real** typ som är formaterade som valuta.</span><span class="sxs-lookup"><span data-stu-id="175cc-200">It's also used for fields of the **Real** type that are formatted as currency.</span></span> <span data-ttu-id="175cc-201">För dessa fält används egenskapen för att skicka valutakoden till programmet.</span><span class="sxs-lookup"><span data-stu-id="175cc-201">For those fields, the property is used to pass the currency code to the app.</span></span>

### <a name="datevalue-date"></a><span data-ttu-id="175cc-202">dateValue (datum)</span><span class="sxs-lookup"><span data-stu-id="175cc-202">dateValue (date)</span></span>

<span data-ttu-id="175cc-203">Datum för fält av **Datum** typ skickar den här egenskapen datumvärde för fältet mellan servern och appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-203">For fields of the **Date** type, this property passes the date value of the field between the server and the app.</span></span>

## <a name="show-and-save-a-custom-field-in-the-timesheet-entry-section"></a><span data-ttu-id="175cc-204">Visa och spara ett anpassat fält i avsnittet tidrapportpost</span><span class="sxs-lookup"><span data-stu-id="175cc-204">Show and save a custom field in the timesheet entry section</span></span>

<span data-ttu-id="175cc-205">Nedan visas en skärmdump från mobilappen för en tidrapportpost.</span><span class="sxs-lookup"><span data-stu-id="175cc-205">Below is a screenshot from the mobile app of a timesheet entry creation.</span></span> <span data-ttu-id="175cc-206">Den visar färdiga fältet utanför rutan och ett anpassat fält i avsnittet "Tidspost" som kallas "Teststräng" med ett fasttextvärde på "Andra alternativet" som redan är inställt.</span><span class="sxs-lookup"><span data-stu-id="175cc-206">It shows the out-of-box fields and a custom field in the "Time entry" section called "Test string" with an enum value of "Second option" already set.</span></span>

![Teststrängens anpassade fält i appen](media/timesheet-entry.jpg)



<span data-ttu-id="175cc-208">Nedan visas en skärmbild av användarens mobilapp som väljer ett av de uppräkningsalternativ som är tillgängliga för det anpassade fältet "teststräng".</span><span class="sxs-lookup"><span data-stu-id="175cc-208">Below is a screenshot from the mobile app of the user selecting one of the enum options available for the "Test string" custom field.</span></span>  <span data-ttu-id="175cc-209">De två alternativen är "första alternativet" och "andra alternativet" visas som alternativknappar.</span><span class="sxs-lookup"><span data-stu-id="175cc-209">The two options are "First option" and "Second option" shown as radio buttons.</span></span> <span data-ttu-id="175cc-210">Det andra alternativet är markerat.</span><span class="sxs-lookup"><span data-stu-id="175cc-210">The second option is currently selected.</span></span>

![Alternativknappar (alternativknappar) för det anpassade fältet för teststrängar](media/enum-option.jpg)



### <a name="extend-the-tstimesheetline-table-so-that-it-has-a-custom-field"></a><span data-ttu-id="175cc-212">Utöka TSTimesheetLine-tabellen så att den har ett anpassat fält</span><span class="sxs-lookup"><span data-stu-id="175cc-212">Extend the TSTimesheetLine table so that it has a custom field</span></span>

<span data-ttu-id="175cc-213">I vanliga fall är det troligt att data för ett anpassat fält i avsnittet tidrapportost kommer att sparas i TSTimesheetLine-registret.</span><span class="sxs-lookup"><span data-stu-id="175cc-213">In typical scenarios, it's likely that the data for a custom field in the timesheet entry section will be saved to the TSTimesheetLine table.</span></span> <span data-ttu-id="175cc-214">Andra register kan dock användas om data kan hämtas baserat på en TSTimesheetTrans-post som tillhandahålls, eller om den inte har specifik postkontext (t.ex. om fältet är skrivskyddat i projektparametrarna).</span><span class="sxs-lookup"><span data-stu-id="175cc-214">However, other tables can be used if the data can be retrieved based on a TSTimesheetTrans record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</span></span>

<span data-ttu-id="175cc-215">Observera att anpassade fält inte behöver ha några säkerhetsposter i databasen.</span><span class="sxs-lookup"><span data-stu-id="175cc-215">Note that custom fields don't have to have any backing database records.</span></span> <span data-ttu-id="175cc-216">De kan genereras dynamiskt baserat på X ++-logik.</span><span class="sxs-lookup"><span data-stu-id="175cc-216">They can be dynamically generated based on X++ logic.</span></span> <span data-ttu-id="175cc-217">Den här metoden kan vara användbar i skrivskyddade scenarier (se avsnittet "använda en beslutskedja i klassen TSTimesheetDetails, buildCustomFieldListForHeader-metod för att fylla i tidrapportdetaljer" för ett exempel på dynamiskt genererade anpassade fältvärden.)</span><span class="sxs-lookup"><span data-stu-id="175cc-217">This approach can be useful in read-only scenarios (see the “Use chain of command on the TSTimesheetDetails class, buildCustomFieldListForHeader method to fill in timesheet details” section for an example of dynamically generated custom field values.)</span></span>

<span data-ttu-id="175cc-218">Nedan visas en skärmbild från Visual Studio av programobjektträdet.</span><span class="sxs-lookup"><span data-stu-id="175cc-218">Below is a screenshot from Visual Studio of the Application Object Tree.</span></span> <span data-ttu-id="175cc-219">Det visar ett tillägg till TSTimesheetLine-registret med TestLineString-fältet tillagt som ett anpassat fält.</span><span class="sxs-lookup"><span data-stu-id="175cc-219">It shows an extension of the TSTimesheetLine table with the TestLineString field added as a custom field.</span></span>

![Radsträng](media/b6756b4a3fc5298093327a088a7710fd.png)

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-timesheet-entry-section"></a><span data-ttu-id="175cc-221">Använd en beslutskedja på buildCustomFieldList-metoden i TSTimesheetSettings-klassen för att visa ett fält i postområdet för tidrapport</span><span class="sxs-lookup"><span data-stu-id="175cc-221">Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the timesheet entry section</span></span>

<span data-ttu-id="175cc-222">Den här koden styr bildskärmsinställningarna för fältet i appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-222">This code controls the display settings for the field in the app.</span></span> <span data-ttu-id="175cc-223">T.ex. styrs typen av fält, etiketten, om fältet är obligatoriskt och vilket avsnitt fältet visas i.</span><span class="sxs-lookup"><span data-stu-id="175cc-223">For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</span></span>

<span data-ttu-id="175cc-224">I följande exempel visas ett strängfält i tidsposter.</span><span class="sxs-lookup"><span data-stu-id="175cc-224">The following example shows a string field on time entries.</span></span> <span data-ttu-id="175cc-225">Det här fältet har två alternativ, **första alternativet** och **andra alternativet** som är tillgängliga via alternativknappar (alternativknappar).</span><span class="sxs-lookup"><span data-stu-id="175cc-225">This field has two options, **First option** and **Second option**, that are available via option buttons (radio buttons).</span></span> <span data-ttu-id="175cc-226">Fältet i programmet är kopplat till fältet **TestLineString** som läggs till i TSTimesheetLine-registret.</span><span class="sxs-lookup"><span data-stu-id="175cc-226">The field in the app is associated with the **TestLineString** field that is added to the TSTimesheetLine table.</span></span>

<span data-ttu-id="175cc-227">Observera att användning av **TSTimesheetCustomField::newFromMetatdata()**-metoden för att förenkla initieringen av de anpassade fältegenskaperna: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength** och **numberOfDecimals**.</span><span class="sxs-lookup"><span data-stu-id="175cc-227">Note the use of the **TSTimesheetCustomField::newFromMetatdata()** method to simplify the initialization of the custom field properties: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength**, and **numberOfDecimals**.</span></span> <span data-ttu-id="175cc-228">Du kan också ställa in dessa parametrar manuellt, som du vill.</span><span class="sxs-lookup"><span data-stu-id="175cc-228">You can also set these parameters manually, as you prefer.</span></span>

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

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforentry-method-of-the-tstimesheetentry-class-to-enter-values-in-a-timesheet-entry"></a><span data-ttu-id="175cc-229">Använd en beslutskedja på buildCustomFieldListForEntry-metoden i TSTimesheetEntry-klassen för att ange värden i en tidrapportpost</span><span class="sxs-lookup"><span data-stu-id="175cc-229">Use chain of command on the buildCustomFieldListForEntry method of the TSTimesheetEntry class to enter values in a timesheet entry</span></span>

<span data-ttu-id="175cc-230">Metoden **buildCustomFieldListForEntry** används för att ange värden på de sparade tidrapportrader som finns i mobilappen.</span><span class="sxs-lookup"><span data-stu-id="175cc-230">The **buildCustomFieldListForEntry** method is used to enter values on the saved timesheet lines in the mobile app.</span></span> <span data-ttu-id="175cc-231">Den tar en TSTimesheetTrans-post som en parameter.</span><span class="sxs-lookup"><span data-stu-id="175cc-231">It takes a TSTimesheetTrans record as a parameter.</span></span> <span data-ttu-id="175cc-232">Fält från den posten kan användas för att fylla i det anpassade fältvärdet i appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-232">Fields from that record can be used to fill in the custom field value in the app.</span></span>

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

### <a name="use-chain-of-command-on-the-tstimesheetentryservice-class-to-save-a-timesheet-entry-from-the-app-back-to-the-database"></a><span data-ttu-id="175cc-233">Använd beslutskedjan i TSTimesheetEntryService-klassen för att spara en tidrapportpost från appen tillbaka till databasen</span><span class="sxs-lookup"><span data-stu-id="175cc-233">Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database</span></span>

<span data-ttu-id="175cc-234">Om du vill återställa ett anpassat fält till databasen i typisk användning måste du utöka flera metoder:</span><span class="sxs-lookup"><span data-stu-id="175cc-234">To save a custom field back to the database in typical usage, you must extend multiple methods:</span></span>

- <span data-ttu-id="175cc-235">**TimesheetLineNeedsUpdating**-metoden används för att avgöra om radposten har ändrats av användaren i appen och måste sparas i databasen.</span><span class="sxs-lookup"><span data-stu-id="175cc-235">The **timesheetLineNeedsUpdating** method is used to determine whether the line record has been changed by the user in the app and must be saved to the database.</span></span> <span data-ttu-id="175cc-236">Om prestanda inte är ett problem kan den här metoden förenklas så att den alltid returnerar **sant**.</span><span class="sxs-lookup"><span data-stu-id="175cc-236">If performance isn't a concern, this method can be simplified so that it always returns **true**.</span></span>
- <span data-ttu-id="175cc-237">Metoderna **populateTimesheetLineFromEntryDuringCreate** och **populateTimesheetLineFromEntryDuringUpdate** kan utökas så att de anger värden i TSTimesheetLine-databasposten från TSTimesheetEntry-datakontraktspost som tillhandahålls.</span><span class="sxs-lookup"><span data-stu-id="175cc-237">The **populateTimesheetLineFromEntryDuringCreate** and **populateTimesheetLineFromEntryDuringUpdate** methods can be extended so that they enter values in the TSTimesheetLine database record from the TSTimesheetEntry data contract record that is provided.</span></span> <span data-ttu-id="175cc-238">I exemplet nedan ska du observera att mappningen mellan databasfältet och transaktionsfältet utförs manuellt via koden X++.</span><span class="sxs-lookup"><span data-stu-id="175cc-238">In the example that follows, notice how the mapping between the database field and the entry field is manually done via X++ code.</span></span>
- <span data-ttu-id="175cc-239">**PopulateTimesheetWeekFromEntry**-metoden kan också utökas om det anpassade fält som mappas till **TSTimesheetEntry**-objektet måste skriva tillbaka till TSTimesheetLineweek databasregister.</span><span class="sxs-lookup"><span data-stu-id="175cc-239">The **populateTimesheetWeekFromEntry** method can also be extended if the custom field that is mapped to the **TSTimesheetEntry** object must write back to the TSTimesheetLineweek database table.</span></span>

> [!NOTE]
> <span data-ttu-id="175cc-240">I följande exempel sparas värdet **firstOption** eller **secondOption** som användaren väljer till databasen som ett råsträngvärde.</span><span class="sxs-lookup"><span data-stu-id="175cc-240">The following example saves the **firstOption** or **secondOption** value that the user selects to the database as a raw string value.</span></span> <span data-ttu-id="175cc-241">Om databasfältet är ett fält av typen **fastext** kan dessa värden mappas manuellt till ett uppräkningsvärde och sedan sparas till ett uppräkningsfält i databasregistret.</span><span class="sxs-lookup"><span data-stu-id="175cc-241">If the database field is a field of the **Enum** type, those values can be manually mapped to an enum value and then saved to an enum field on the database table.</span></span>

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

## <a name="show-a-custom-field-in-the-timesheet-header-section"></a><span data-ttu-id="175cc-242">Visa och spara ett anpassat fält i avsnittet tidrapporthuvud</span><span class="sxs-lookup"><span data-stu-id="175cc-242">Show a custom field in the timesheet header section</span></span>

<span data-ttu-id="175cc-243">Nedan visas en skärmdump från mobilappen för användare som tittar på en tidrapport.</span><span class="sxs-lookup"><span data-stu-id="175cc-243">Below is a screenshot from the mobile app of a user viewing a timesheet.</span></span> <span data-ttu-id="175cc-244">Knappen "Mer information" har markerats i det övre högra hörnet för att visa alternativet "Visa mer information".</span><span class="sxs-lookup"><span data-stu-id="175cc-244">The "More information" button has been selected in the upper-right corner to show the "View more details" option.</span></span>  

![Kommandot Visa mer information](media/show-more.png)



<span data-ttu-id="175cc-246">Nedan visas en skärmdump från mobilappen med avsnittet "Mer" på en tidrapport.</span><span class="sxs-lookup"><span data-stu-id="175cc-246">Below is a screenshot from the mobile app showing the “More” section of a timesheet.</span></span> <span data-ttu-id="175cc-247">Ett anpassat fält med namnet "utnyttjandegrad för den här tidrapporten (ett beräknat anpassat fält) har lagts till i avsnittet tidrapportrubrik.</span><span class="sxs-lookup"><span data-stu-id="175cc-247">A custom field called “Utilization rate of this timesheet (computed custom field)” has been added to the timesheet header section.</span></span> <span data-ttu-id="175cc-248">Ett skrivskyddat värde på "0,667" har ställts in för det anpassade fältet.</span><span class="sxs-lookup"><span data-stu-id="175cc-248">A read-only value of "0.667" is set on the custom field.</span></span>

![Avsnittet Mer](media/more-section.jpg)



### <a name="extend-the-tstimesheettable-table-so-that-it-has-a-custom-field"></a><span data-ttu-id="175cc-250">Utöka TSTimesheetTable-tabellen så att den har ett anpassat fält</span><span class="sxs-lookup"><span data-stu-id="175cc-250">Extend the TSTimesheetTable table so that it has a custom field</span></span>

<span data-ttu-id="175cc-251">I vanliga fall är det troligt att data för ett anpassat fält i avsnittet rubrik kommer att dras från TSTimesheetHeader-registret.</span><span class="sxs-lookup"><span data-stu-id="175cc-251">In typical scenarios, it's likely that the data for a custom field in the header section will be pulled from the TSTimesheetHeader table.</span></span> <span data-ttu-id="175cc-252">Andra register kan dock användas om data kan hämtas baserat på en TSTimesheetTable-post som tillhandahålls, eller om den inte har specifik postkontext (t.ex. om fältet är skrivskyddat i projektparametrarna).</span><span class="sxs-lookup"><span data-stu-id="175cc-252">However, other tables can be used if the data can be retrieved based on a TSTimesheetTable record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</span></span>

<span data-ttu-id="175cc-253">Observera att anpassade fält inte behöver ha några säkerhetsposter i databasen.</span><span class="sxs-lookup"><span data-stu-id="175cc-253">Note that custom fields don't have to have any backing database records.</span></span> <span data-ttu-id="175cc-254">De kan genereras dynamiskt baserat på X ++-logik.</span><span class="sxs-lookup"><span data-stu-id="175cc-254">They can be dynamically generated based on X++ logic.</span></span> <span data-ttu-id="175cc-255">I exemplet nedan visas den här metoden.</span><span class="sxs-lookup"><span data-stu-id="175cc-255">The example that follows shows this approach.</span></span>

<span data-ttu-id="175cc-256">Fält i rubrikavsnittet är alltid skrivskyddade i appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-256">Fields in the header section are always read-only in the app.</span></span>

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-header-section"></a><span data-ttu-id="175cc-257">Använd en beslutskedja på buildCustomFieldList-metoden i TSTimesheetSettings-klassen för att visa ett fält i avsnittet rubrik</span><span class="sxs-lookup"><span data-stu-id="175cc-257">Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the header section</span></span>

<span data-ttu-id="175cc-258">Den här koden styr bildskärmsinställningarna för fältet i appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-258">This code controls the display settings for the field in the app.</span></span> <span data-ttu-id="175cc-259">T.ex. styrs typen av fält, etiketten, om fältet är obligatoriskt och vilket avsnitt fältet visas i.</span><span class="sxs-lookup"><span data-stu-id="175cc-259">For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</span></span>

<span data-ttu-id="175cc-260">I följande exempel visas ett beräknat värde i rubrik avsnittet i appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-260">The following example shows a computed value in the header section in the app.</span></span>

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

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforheader-method-of-the-tstimesheetdetails-class-to-fill-in-timesheet-details"></a><span data-ttu-id="175cc-261">Använd en beslutskedja på buildCustomFieldListForHeader-metoden i TSTimesheetDetails-klassen för att fylla i detaljerna för tidrapport</span><span class="sxs-lookup"><span data-stu-id="175cc-261">Use chain of command on the buildCustomFieldListForHeader method of the TSTimesheetDetails class to fill in timesheet details</span></span>

<span data-ttu-id="175cc-262">Metoden **buildCustomFieldListForHeader** används för att fylla i tidrapportens rubrikdetaljer i mobilappen.</span><span class="sxs-lookup"><span data-stu-id="175cc-262">The **buildCustomFieldListForHeader** method is used to fill in the timesheet header details in the mobile app.</span></span> <span data-ttu-id="175cc-263">Den tar en TSTimesheetTable-post som en parameter.</span><span class="sxs-lookup"><span data-stu-id="175cc-263">It takes a TSTimesheetTable record as a parameter.</span></span> <span data-ttu-id="175cc-264">Fält från den posten kan användas för att fylla i det anpassade fältvärdet i appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-264">Fields from that record can be used to fill in the custom field value in the app.</span></span> <span data-ttu-id="175cc-265">I följande exempel läses inga värden från databasen.</span><span class="sxs-lookup"><span data-stu-id="175cc-265">The following example doesn't read any values from the database.</span></span> <span data-ttu-id="175cc-266">I stället används X++-logik för att generera ett beräknat värde som sedan visas i appen.</span><span class="sxs-lookup"><span data-stu-id="175cc-266">Instead, it uses X++ logic to generate a computed value that is then shown in the app.</span></span>


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

## <a name="other-configurabilityextensibility-opportunities"></a><span data-ttu-id="175cc-267">Andra konfigurerbara och utökningsmöjligheter</span><span class="sxs-lookup"><span data-stu-id="175cc-267">Other configurability/extensibility opportunities</span></span>

### <a name="adding-additional-validation-for-the-app"></a><span data-ttu-id="175cc-268">Lägger till ytterligare validering för appen</span><span class="sxs-lookup"><span data-stu-id="175cc-268">Adding additional validation for the app</span></span>

<span data-ttu-id="175cc-269">Befintlig logik för tidrapportfunktioner på databasnivå fungerar fortfarande som förväntat.</span><span class="sxs-lookup"><span data-stu-id="175cc-269">Existing logic for timesheet functionality at the database level will still work as expected.</span></span> <span data-ttu-id="175cc-270">Om du vill avbryta arbetet med att spara eller skicka meddelanden och visa ett visst felmeddelande, kan du lägga till **utlös fel (meddelande till användare")** till koden via ett tillägg för en beslutskedja.</span><span class="sxs-lookup"><span data-stu-id="175cc-270">To interrupt the completion of save or submit operations and show a specific error message, you can add **throw error("message to user")** to the code via a chain of command extension.</span></span> <span data-ttu-id="175cc-271">Här är tre exempel på användbara utökningsmetoder:</span><span class="sxs-lookup"><span data-stu-id="175cc-271">Here are three examples of useful extensible methods:</span></span>

- <span data-ttu-id="175cc-272">Om **ValidateWrite** i TSTimesheetLine-tabellen returnerar **falsk** under en spara-åtgärd för en tidrapportrad visas ett felmeddelande i mobilappen.</span><span class="sxs-lookup"><span data-stu-id="175cc-272">If **validateWrite** on the TSTimesheetLine table returns **false** during a save operation for a timesheet line, an error message is shown in the mobile app.</span></span>
- <span data-ttu-id="175cc-273">Om **validateSubmit** i TSTimesheetTable-tabellen returnerar **falsk** när tidrapporten skickas till appen visas ett felmeddelande för användaren.</span><span class="sxs-lookup"><span data-stu-id="175cc-273">If **validateSubmit** on the TSTimesheetTable table returns **false** during timesheet submission in the app, an error message is shown to the user.</span></span>
- <span data-ttu-id="175cc-274">iLogik som fyller i fält (t.ex. **radegenskap**) under **infoga**-metoden i TSTimesheetLine-tabellen kommer fortfarande att köras.</span><span class="sxs-lookup"><span data-stu-id="175cc-274">Logic that fills in fields (for example, **Line Property**) during the **insert** method on the TSTimesheetLine table will still run.</span></span>

### <a name="hiding-and-marking-out-of-box-fields-as-read-only-via-configuration"></a><span data-ttu-id="175cc-275">Dölja och markera färdiga fält som skrivskyddade via konfiguration</span><span class="sxs-lookup"><span data-stu-id="175cc-275">Hiding and marking out-of-box fields as read-only via configuration</span></span>

<span data-ttu-id="175cc-276">Från projektets parametrar kan du ange att fält i ett färdigt fält som skrivskyddad eller dold i mobilappen.</span><span class="sxs-lookup"><span data-stu-id="175cc-276">From the project parameters, you can make out-of-box fields read-only or hidden in the mobile app.</span></span> <span data-ttu-id="175cc-277">Ställ in alternativen i avsnittet **mobila tidrapporter** på fliken **tidrapport** på sidan **projekthantering och redovisningsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="175cc-277">Set the options in the **Mobile timesheets** section on the **Timesheet** tab of the **Project management and accounting parameters** page.</span></span>

![Projektparametrar](media/5753b8ecccd1d8bb2b002dd538b3f762.png)

### <a name="changing-the-activities-that-are-available-for-selection-via-extensions"></a><span data-ttu-id="175cc-279">Ändra vilka aktiviteter som är tillgängliga för markering via tillägg</span><span class="sxs-lookup"><span data-stu-id="175cc-279">Changing the activities that are available for selection via extensions</span></span>

<span data-ttu-id="175cc-280">De aktiviteter som är tillgängliga för val för ett projekt fylls i via metoderna **getActivitiesForProject()** och **getActivityQuery()** i klassen **TsTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="175cc-280">The activities that are available for selection for a project are filled in via the **getActivitiesForProject()** and **getActivityQuery()** methods in the **TsTimesheetProjectService** class.</span></span> <span data-ttu-id="175cc-281">Du kan använda beslutskedja om du vill ändra det här beteendet så att det passar ditt affärsscenario för de aktiviteter som kan väljas för ett visst projekt.</span><span class="sxs-lookup"><span data-stu-id="175cc-281">You can use chain of command to change this behavior to match your business scenario for the activities that are available for selection for a specific project.</span></span>

### <a name="entering-a-default-project-category-on-timesheet-entries"></a><span data-ttu-id="175cc-282">Ange en standardkategori för projektet på tidrapportposter</span><span class="sxs-lookup"><span data-stu-id="175cc-282">Entering a default project category on timesheet entries</span></span>

<span data-ttu-id="175cc-283">Inmatning av en standardprojektkategori på tidrapportposter sker på tre nivåer.</span><span class="sxs-lookup"><span data-stu-id="175cc-283">Entry of a default project category on timesheet entries occurs at three levels.</span></span> <span data-ttu-id="175cc-284">Du kan använda beslutskedja om du vill utöka beteendet på någon av eller alla dessa nivåer för att uppnå önskat beteende.</span><span class="sxs-lookup"><span data-stu-id="175cc-284">You can use chain of command to extend the behavior at any or all of these levels to achieve the desired behavior.</span></span> <span data-ttu-id="175cc-285">Följande hierarki används:</span><span class="sxs-lookup"><span data-stu-id="175cc-285">The following hierarchy is used:</span></span>

1. <span data-ttu-id="175cc-286">Appen försöker placera standardkategorin från projektresursen.</span><span class="sxs-lookup"><span data-stu-id="175cc-286">The app tries to put the default category from the project resource.</span></span> <span data-ttu-id="175cc-287">Denna standardkategori ställs in i metoderna **getCurrentUserResource** och **getDelegatedResourcesForCurrentUser** i klassen **TSTimesheetSettingsService**.</span><span class="sxs-lookup"><span data-stu-id="175cc-287">This default category is set in the **getCurrentUserResource** and **getDelegatedResourcesForCurrentUser** methods in the **TSTimesheetSettingsService** class.</span></span>
2. <span data-ttu-id="175cc-288">Om standardkategorin inte finns på projektets resursnivå försöker programmet att hämta den från projektaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="175cc-288">If the default category isn't provided at the project resource level, the app tries to pull it from the project activity.</span></span> <span data-ttu-id="175cc-289">Denna standardkategori ställs in i metoden **getActivitiesForProject** i klassen **TSTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="175cc-289">This default category is set in the **getActivitiesForProject** method in the **TSTimesheetProjectService** class.</span></span>
3. <span data-ttu-id="175cc-290">Om standardkategorin inte finns på projektets aktivitetsnivå tas standardkategorin från projektparametrarna.</span><span class="sxs-lookup"><span data-stu-id="175cc-290">If the default category isn't provided at the project activity level, the default category it taken from the project parameters.</span></span> <span data-ttu-id="175cc-291">Denna standardkategori ställs in i metoden **getProjectDetailsbyRule** i klassen **TSTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="175cc-291">This default category is set in the **getProjectDetailsbyRule** method in the **TSTimesheetProjectService** class.</span></span>