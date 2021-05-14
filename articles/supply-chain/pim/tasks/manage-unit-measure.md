---
title: Hantera måttenheter
description: Detta ämne beskriver hur du definierar en måttenhet, anger översättningar för enheten och dess beskrivning, samt definierar konverteringsregler för relaterade enheter.
author: sorenva
ms.date: 04/09/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d36839cd8e3398225d3421bf0f268068599ca49f
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921351"
---
# <a name="manage-units-of-measure"></a><span data-ttu-id="0280d-103">Hantera måttenheter</span><span class="sxs-lookup"><span data-stu-id="0280d-103">Manage units of measure</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0280d-104">Detta ämne beskriver hur du definierar en måttenhet, anger översättningar för enheten och dess beskrivning, samt definierar konverteringsregler för relaterade enheter.</span><span class="sxs-lookup"><span data-stu-id="0280d-104">This topic describes how to define a unit of measure, provide translations for the unit and its description, and define conversion rules for related units.</span></span>

## <a name="open-the-units-page"></a><span data-ttu-id="0280d-105">Öppna enhetssidan</span><span class="sxs-lookup"><span data-stu-id="0280d-105">Open the Units page</span></span>

<span data-ttu-id="0280d-106">Om du vill skapa och arbeta med tillgängliga måttenheter i systemet går du till **Organisationsadministration \> Inställningar \> Enheter \> Enheter**.</span><span class="sxs-lookup"><span data-stu-id="0280d-106">To create and work with the units of measure that are available in your system, go to **Organization administration \> Setup \> Units \> Units**.</span></span>

<span data-ttu-id="0280d-107">I de återstående avsnitten i detta ämne beskrivs vad du kan göra på sidan **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="0280d-107">The remaining sections of this topic describe what you can do on the **Units** page.</span></span>

## <a name="create-standard-units-and-conversions"></a><span data-ttu-id="0280d-108">Skapa standardenheter och konverteringar</span><span class="sxs-lookup"><span data-stu-id="0280d-108">Create standard units and conversions</span></span>

<span data-ttu-id="0280d-109">Om ditt system inte redan omfattar de mest använda måttenheterna för det metriska måttsystemet och/eller det amerikanska systemet (USCS) kan guiden för enhetsinställningar hjälpa dig att snabbt komma igång med grundläggande enhetsdefinitioner och konverteringar.</span><span class="sxs-lookup"><span data-stu-id="0280d-109">If your system doesn't already include the most commonly used units of measure for the metric system and/or the US customary system (USCS), the unit setup wizard can help you quickly get started with basic unit definitions and conversions.</span></span> <span data-ttu-id="0280d-110">Slutför guiden genom att välja **guiden för enhetsskapande** i åtgärdsfönstret och sedan följa instruktionerna på skärmen.</span><span class="sxs-lookup"><span data-stu-id="0280d-110">To complete the wizard, select **Unit creation wizard** on the Action Pane, and then follow the on-screen instructions.</span></span>

## <a name="create-or-edit-a-unit-of-measure"></a><span data-ttu-id="0280d-111">Skapa eller redigera en måttenhet</span><span class="sxs-lookup"><span data-stu-id="0280d-111">Create or edit a unit of measure</span></span>

<span data-ttu-id="0280d-112">Följ de här stegen om du vill skapa eller redigera en måttenhet.</span><span class="sxs-lookup"><span data-stu-id="0280d-112">To create or edit a unit of measure, follow these steps.</span></span>

1. <span data-ttu-id="0280d-113">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="0280d-113">Follow one of these steps:</span></span>

    - <span data-ttu-id="0280d-114">Om du vill redigera en befintlig enhet markerar du den i listfönstret.</span><span class="sxs-lookup"><span data-stu-id="0280d-114">To edit an existing unit, select it in the list pane.</span></span>
    - <span data-ttu-id="0280d-115">Om du vill skapa en ny enhet väljer du **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0280d-115">To create a new unit, select **New** on the Action Pane.</span></span>

1. <span data-ttu-id="0280d-116">Ange följande fält i den nya postrubriken:</span><span class="sxs-lookup"><span data-stu-id="0280d-116">On the header of the record, set the following fields:</span></span>

    - <span data-ttu-id="0280d-117">**Enhet** – Ange det ID eller den symbol som ska användas för att referera till enheten i systemspråket.</span><span class="sxs-lookup"><span data-stu-id="0280d-117">**Unit** – Enter the ID or symbol to use to refer to the unit in the system language.</span></span> <span data-ttu-id="0280d-118">Detta ID eller denna symbol är vanligtvis en vanlig förkortning för enheten, till exempel för *ea* för "each" ("varje") eller *cm* för centimeter.</span><span class="sxs-lookup"><span data-stu-id="0280d-118">This ID or symbol is usually a common abbreviation for the unit, such as *ea* for each or *cm* for centimeter.</span></span>
    - <span data-ttu-id="0280d-119">**Beskrivning** – Ange ett beskrivande namn för enheten i systemspråket.</span><span class="sxs-lookup"><span data-stu-id="0280d-119">**Description** – Enter a descriptive name for the unit in the system language.</span></span> <span data-ttu-id="0280d-120">Detta är vanligtvis det fullständiga namnet på enheten, till exempel *Varje* eller *Centimeter*.</span><span class="sxs-lookup"><span data-stu-id="0280d-120">This name is usually the full name of the unit, such as *Each* or *Centimeter*.</span></span>

1. <span data-ttu-id="0280d-121">På snabbfliken **Allmänt** ange följande fält:</span><span class="sxs-lookup"><span data-stu-id="0280d-121">On the **General** FastTab, set the following fields:</span></span><!-- KFM: confirm this:    - **Fixed unit assignment** and **Fixed unit** – These fields have an effect only if you're using the Microsoft Retail Essentials product. If the current unit can be mapped to one of the fixed units that are used by Retail Essentials, set the **Fixed unit assignment** option to *Yes*. Then select the fixed unit in the **Fixed unit** field. -->

    - <span data-ttu-id="0280d-122">**Enhetsklass** – Välj den egenskap som enheten mäter (t.ex. längd, område, massa eller kvantitet).</span><span class="sxs-lookup"><span data-stu-id="0280d-122">**Unit class** – Select the property that the unit measures (such as length, area, mass, or quantity).</span></span>
    - <span data-ttu-id="0280d-123">**System med enheter** – Välj det måttsystem som enheten tillhör (*Metriska enheter* eller *USA-anpassade enheter*).</span><span class="sxs-lookup"><span data-stu-id="0280d-123">**System of units** – Select the measurement system that the unit belongs to (*Metric units* or *United States customary units*).</span></span>
    - <span data-ttu-id="0280d-124">**Basenhet** – Ange det här alternativet som *Ja* om du vill använda den aktuella enheten som basenhet för dess enhetsklass.</span><span class="sxs-lookup"><span data-stu-id="0280d-124">**Base unit** – Set this option to *Yes* to use the current unit as the base unit for its unit class.</span></span> <span data-ttu-id="0280d-125">I detta fall behöver du bara ange konverteringsfaktorn mellan basenheten och varje ytterligare enhet i enhetsklassen.</span><span class="sxs-lookup"><span data-stu-id="0280d-125">In this case, you only have to specify the conversion factor between the base unit and each additional unit in the unit class.</span></span> <span data-ttu-id="0280d-126">Systemet kan sedan konvertera mellan alla enheter i denna enhetsklass.</span><span class="sxs-lookup"><span data-stu-id="0280d-126">The system can then convert between all units in that unit class.</span></span> <span data-ttu-id="0280d-127">Därför är det enklare att ställa in konverteringar.</span><span class="sxs-lookup"><span data-stu-id="0280d-127">Therefore, it's easier to set up conversions.</span></span>

        <span data-ttu-id="0280d-128">Om liter till exempel är basenhet för enhetsklassen *Volym*, behöver du bara ställa in konverteringsfaktorer från exempelvis quart till liter och från pint till liter.</span><span class="sxs-lookup"><span data-stu-id="0280d-128">For example, if gallon is the base unit for the *Volume* unit class, you only have to set up conversion factors from quart to gallon and from pint to gallon.</span></span> <span data-ttu-id="0280d-129">Systemet kan sedan även konvertera från quart till pint.</span><span class="sxs-lookup"><span data-stu-id="0280d-129">The system can then also convert from quart to pint.</span></span>

        <span data-ttu-id="0280d-130">Du kan endast ha en basenhet per enhetsklass.</span><span class="sxs-lookup"><span data-stu-id="0280d-130">You can have only one base unit per unit class.</span></span>

    - <span data-ttu-id="0280d-131">**Systemenhet** – Ange det här alternativet som *Ja* om du vill använda den aktuella enheten som antagen enhet för alla icke-specificerade mått i dess enhetsklass.</span><span class="sxs-lookup"><span data-stu-id="0280d-131">**System unit** – Set this option to *Yes* to use the current unit as the assumed unit for all unspecified measurements in its unit class.</span></span> <span data-ttu-id="0280d-132">Om till exempel ett fält som används för att ange en kvantitet inte tillåter att en enhet anges (om användaren inte väljer någon enhet) använder systemet den enhet som har ställts in som systemenhet för enhetsklassen *Kvantitet*.</span><span class="sxs-lookup"><span data-stu-id="0280d-132">For example, if a field that is used to enter a quantity doesn't allow a unit to be specified (of if the user doesn't select a unit), the system uses the unit that is set as the system unit for the *Quantity* unit class.</span></span> <span data-ttu-id="0280d-133">Du kan endast ha en systemenhet per enhetsklass.</span><span class="sxs-lookup"><span data-stu-id="0280d-133">You can have only one system unit per unit class.</span></span>
    - <span data-ttu-id="0280d-134">**Decimalprecision** – Ange det antal decimaler som värden som anges för den aktuella enheten eller konverteras till ska avrundas till.</span><span class="sxs-lookup"><span data-stu-id="0280d-134">**Decimal precision** – Specify the number of decimal places that values that are specified for the current unit or converted to it should be rounded to.</span></span>

1. <span data-ttu-id="0280d-135">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0280d-135">On the Action Pane, select **Save**.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="0280d-136">Definiera enhetsöversättningar</span><span class="sxs-lookup"><span data-stu-id="0280d-136">Define unit translations</span></span>

<span data-ttu-id="0280d-137">Gör på följande sätt om du vill definiera översättningar av ID:t eller symbolen samt beskrivningen av en måttenhet.</span><span class="sxs-lookup"><span data-stu-id="0280d-137">To define translations for the ID or symbol and the description for a unit of measure, follow these steps.</span></span>

1. <span data-ttu-id="0280d-138">Skapa eller välj enheten som översättningar ska skapas för.</span><span class="sxs-lookup"><span data-stu-id="0280d-138">Create or select the unit to create translations for.</span></span>
1. <span data-ttu-id="0280d-139">Välj **Enhetstexter** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0280d-139">On the Action Pane, select **Unit texts**.</span></span>

    <span data-ttu-id="0280d-140">Sidan **Enhetstexter** visas.</span><span class="sxs-lookup"><span data-stu-id="0280d-140">The **Unit texts** page appears.</span></span> <span data-ttu-id="0280d-141">På den här sidan definierar du översättningar av ID eller symbol för den valda enheten.</span><span class="sxs-lookup"><span data-stu-id="0280d-141">You use this page to define translations for the ID or symbol for the selected unit.</span></span> <span data-ttu-id="0280d-142">Dessa översättningar kan sedan användas på externa dokument på kundspecifika eller leverantörsspecifika språk.</span><span class="sxs-lookup"><span data-stu-id="0280d-142">Those translations can then be used on external documents in customer-specific or vendor-specific languages.</span></span>

1. <span data-ttu-id="0280d-143">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0280d-143">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="0280d-144">I fältet **Språk** väljer du det språk du vill översätta enhetens ID eller symbol till.</span><span class="sxs-lookup"><span data-stu-id="0280d-144">In the **Language** field, select the language to translate the unit ID or symbol to.</span></span>
1. <span data-ttu-id="0280d-145">I fältet **Text** anger du översättningen av enhets-ID:t eller symbolen på det valda språket.</span><span class="sxs-lookup"><span data-stu-id="0280d-145">In the **Text** field, enter the translation of the unit ID or symbol in the selected language.</span></span>
1. <span data-ttu-id="0280d-146">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0280d-146">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="0280d-147">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0280d-147">Close the page.</span></span>
1. <span data-ttu-id="0280d-148">Välj **Översatta enhetsbeskrivningar** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="0280d-148">On the **Action Pane**, select **Translated unit descriptions**.</span></span>

    <span data-ttu-id="0280d-149">Sidan **Beskrivningar av den översatta enheten** visas.</span><span class="sxs-lookup"><span data-stu-id="0280d-149">The **Translated unit descriptions** page appears.</span></span> <span data-ttu-id="0280d-150">Du använder den här sidan när du vill definiera språkspecifika beskrivningar för den valda enheten.</span><span class="sxs-lookup"><span data-stu-id="0280d-150">You use this page to define language-specific descriptions for the selected unit.</span></span>

1. <span data-ttu-id="0280d-151">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0280d-151">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="0280d-152">I fältet **Språk** väljer du det språk du vill översätta enhetens beskrivning till.</span><span class="sxs-lookup"><span data-stu-id="0280d-152">In the **Language** field, select the language to translate the unit description to.</span></span>
1. <span data-ttu-id="0280d-153">I fältet **Beskrivning** anger du översättningen av enhetens beskrivning på det valda språket.</span><span class="sxs-lookup"><span data-stu-id="0280d-153">In the **Description** field, enter the translation of the unit description in the selected language.</span></span>
1. <span data-ttu-id="0280d-154">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0280d-154">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="0280d-155">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0280d-155">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="0280d-156">Definiera enhetskonverteringsregler</span><span class="sxs-lookup"><span data-stu-id="0280d-156">Define unit conversion rules</span></span>

<span data-ttu-id="0280d-157">Följ de här stegen om du vill definiera regler för konvertering mellan måttenheter.</span><span class="sxs-lookup"><span data-stu-id="0280d-157">To define rules for conversions between units of measure, follow these steps.</span></span>

1. <span data-ttu-id="0280d-158">Skapa eller välj den enhet som konverteringsregler ska definieras för.</span><span class="sxs-lookup"><span data-stu-id="0280d-158">Create or select the unit to define conversion rules for.</span></span>
1. <span data-ttu-id="0280d-159">Välj **Enhetskonverteringar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0280d-159">On the Action Pane, select **Unit conversions**.</span></span>

    <span data-ttu-id="0280d-160">Sidan **Enhetskonverteringar** visas.</span><span class="sxs-lookup"><span data-stu-id="0280d-160">The **Unit conversions** page appears.</span></span> <span data-ttu-id="0280d-161">Du kan använda denna sida för att definiera regler för att konvertera den valda enheten till och från andra enheter i enhetsklassen.</span><span class="sxs-lookup"><span data-stu-id="0280d-161">You use this page to define rules for converting the selected unit to and from other units in the unit class.</span></span>

1. <span data-ttu-id="0280d-162">Välj en av följande flikar, beroende på vilken typ av konvertering som du vill ställa in:</span><span class="sxs-lookup"><span data-stu-id="0280d-162">Select one of the following tabs, depending on the type of conversion that you want to set up:</span></span>

    - <span data-ttu-id="0280d-163">**Standardkonverteringar** – Ställ in standardkonverteringsregler för alla produkter.</span><span class="sxs-lookup"><span data-stu-id="0280d-163">**Standard conversions** – Set up standard conversion rules for all products.</span></span>
    - <span data-ttu-id="0280d-164">**Konverteringar inom klass** – Ställ in produktspecifika konverteringsregler för enheter i samma enhetsklass.</span><span class="sxs-lookup"><span data-stu-id="0280d-164">**Intra-class conversions** – Set up product-specific conversion rules for units in the same unit class.</span></span>
    - <span data-ttu-id="0280d-165">**Konverteringar mellan klasser** – Ställ in produktspecifika konverteringsregler för enheter i flera olika enhetsklasser.</span><span class="sxs-lookup"><span data-stu-id="0280d-165">**Inter-class conversions** – Set up product-specific conversion rules for units across unit classes.</span></span>

1. <span data-ttu-id="0280d-166">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="0280d-166">Follow one of these steps:</span></span>

    - <span data-ttu-id="0280d-167">Om du vill skapa en ny konvertering väljer du **Ny** i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="0280d-167">To create a new conversion, select **New** on the toolbar.</span></span>
    - <span data-ttu-id="0280d-168">Om du vill redigera en befintlig konvertering markerar du konverteringen i rutnätet och väljer sedan **Redigera** i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="0280d-168">To edit an existing conversion, select the conversion in the grid, and then select **Edit** on the toolbar.</span></span>

1. <span data-ttu-id="0280d-169">Ställ in följande fält i dialogrutan för listrutan som visas:</span><span class="sxs-lookup"><span data-stu-id="0280d-169">In the drop-down dialog box that appears, set the following fields:</span></span>

    - <span data-ttu-id="0280d-170">**Produkt** – Välj den specifika produkt som konverteringen gäller för.</span><span class="sxs-lookup"><span data-stu-id="0280d-170">**Product** – Select the specific product that the conversion applies to.</span></span> <span data-ttu-id="0280d-171">Detta fält är endast tillgängligt för konverteringar inom klass och mellan klasser.</span><span class="sxs-lookup"><span data-stu-id="0280d-171">This field is available only for intra-class and inter-class conversions.</span></span>
    - <span data-ttu-id="0280d-172">**Formellayout** – Lämna det här fältet inställt på *Enkelt* om du vill ange en enkel konvertering som har en enda faktor.</span><span class="sxs-lookup"><span data-stu-id="0280d-172">**Formula layout** – Leave this field set to *Simple* to specify a simple conversion that has a single factor.</span></span> <span data-ttu-id="0280d-173">Ställ in den *Avancerat* för att ställa in en mer komplex formel.</span><span class="sxs-lookup"><span data-stu-id="0280d-173">Set it to *Advanced* to set up a more complex equation.</span></span> <span data-ttu-id="0280d-174">Formatet för avancerade formler varierar beroende på enhetsklassen.</span><span class="sxs-lookup"><span data-stu-id="0280d-174">The format for advanced equations varies, depending on the unit class.</span></span>
    - <span data-ttu-id="0280d-175">**Från enhet** – I det här fältet visas den valda enheten.</span><span class="sxs-lookup"><span data-stu-id="0280d-175">**From unit** – This field shows the selected unit.</span></span> <span data-ttu-id="0280d-176">Vanligtvis ska du inte ändra värdet.</span><span class="sxs-lookup"><span data-stu-id="0280d-176">Usually, you should not change the value.</span></span> <span data-ttu-id="0280d-177">(Om du ändrar värdet måste du öppna sidan **Enhetskonverteringar** för den valda enheten, detta om du vill visa den nya konverteringen när du har sparat den.)</span><span class="sxs-lookup"><span data-stu-id="0280d-177">(If you do change the value, you must open the **Unit conversions** page for the selected unit to view your new conversion after you save it.)</span></span>
    - <span data-ttu-id="0280d-178">**Till enhet** – Välj enheten du vill konvertera till.</span><span class="sxs-lookup"><span data-stu-id="0280d-178">**To unit** – Select the unit to convert to.</span></span>
    - <span data-ttu-id="0280d-179">**Avrundning** – Välj hur en del ska avrundas, baserat på det **decimalvärde** som den valda enheten har (*Till närmaste*, *Upp* eller *Ned*).</span><span class="sxs-lookup"><span data-stu-id="0280d-179">**Rounding** – Select how fractions should be rounded, based on the **Decimal precision** value of the selected unit (*To nearest*, *Up*, or *Down*).</span></span>
    - <span data-ttu-id="0280d-180">**Konverteringsformel** – Använd de återstående fälten högst upp i listrutans dialogruta för att ange formeln för konvertering mellan de två enheterna.</span><span class="sxs-lookup"><span data-stu-id="0280d-180">**Conversion formula** – Use the remaining fields at the top of the drop-down dialog box to specify the formula for converting between the two units.</span></span> <span data-ttu-id="0280d-181">Vilka fält som finns tillgängliga varierar beroende på den enhetsklass och receptlayout som du har valt.</span><span class="sxs-lookup"><span data-stu-id="0280d-181">The available fields vary, depending on the unit class and formula layout that you've selected.</span></span>

1. <span data-ttu-id="0280d-182">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="0280d-182">Select **OK**.</span></span>
1. <span data-ttu-id="0280d-183">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0280d-183">Close the page.</span></span>

> [!TIP]
> <span data-ttu-id="0280d-184">Du kan även ställa in enhetskonverteringar per produktvariant.</span><span class="sxs-lookup"><span data-stu-id="0280d-184">You can also set up unit conversions per product variant.</span></span> <span data-ttu-id="0280d-185">Mer information finns i [Måttenhetskonvertering per produktvariant](../uom-conversion-per-product-variant.md).</span><span class="sxs-lookup"><span data-stu-id="0280d-185">For more information, see [Unit of measure conversion per product variant](../uom-conversion-per-product-variant.md).</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
