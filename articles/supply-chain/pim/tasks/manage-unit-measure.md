---
title: Hantera måttenheter
description: Detta ämne beskriver hur du definierar en måttenhet, anger översättningar för enheten och dess beskrivning, samt definierar konverteringsregler för relaterade enheter.
author: t-benebo
ms.date: 04/09/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e13897396810507bb4b2cbb415b873eb3dd7f4e8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565530"
---
# <a name="manage-units-of-measure"></a>Hantera måttenheter

[!include [banner](../../includes/banner.md)]

Detta ämne beskriver hur du definierar en måttenhet, anger översättningar för enheten och dess beskrivning, samt definierar konverteringsregler för relaterade enheter.

## <a name="open-the-units-page"></a>Öppna enhetssidan

Om du vill skapa och arbeta med tillgängliga måttenheter i systemet går du till **Organisationsadministration \> Inställningar \> Enheter \> Enheter**.

I de återstående avsnitten i detta ämne beskrivs vad du kan göra på sidan **Enheter**.

## <a name="create-standard-units-and-conversions"></a>Skapa standardenheter och konverteringar

Om ditt system inte redan omfattar de mest använda måttenheterna för det metriska måttsystemet och/eller det amerikanska systemet (USCS) kan guiden för enhetsinställningar hjälpa dig att snabbt komma igång med grundläggande enhetsdefinitioner och konverteringar. Slutför guiden genom att välja **guiden för enhetsskapande** i åtgärdsfönstret och sedan följa instruktionerna på skärmen.

## <a name="create-or-edit-a-unit-of-measure"></a>Skapa eller redigera en måttenhet

Följ de här stegen om du vill skapa eller redigera en måttenhet.

1. Gör något av följande:

    - Om du vill redigera en befintlig enhet markerar du den i listfönstret.
    - Om du vill skapa en ny enhet väljer du **Ny** i åtgärdsfönstret.

1. Ange följande fält i den nya postrubriken:

    - **Enhet** – Ange det ID eller den symbol som ska användas för att referera till enheten i systemspråket. Detta ID eller denna symbol är vanligtvis en vanlig förkortning för enheten, till exempel för *ea* för "each" ("varje") eller *cm* för centimeter.
    - **Beskrivning** – Ange ett beskrivande namn för enheten i systemspråket. Detta är vanligtvis det fullständiga namnet på enheten, till exempel *Varje* eller *Centimeter*.

1. På snabbfliken **Allmänt** ange följande fält:<!-- KFM: confirm this:    - **Fixed unit assignment** and **Fixed unit** – These fields have an effect only if you're using the Microsoft Retail Essentials product. If the current unit can be mapped to one of the fixed units that are used by Retail Essentials, set the **Fixed unit assignment** option to *Yes*. Then select the fixed unit in the **Fixed unit** field. -->

    - **Enhetsklass** – Välj den egenskap som enheten mäter (t.ex. längd, område, massa eller kvantitet).
    - **System med enheter** – Välj det måttsystem som enheten tillhör (*Metriska enheter* eller *USA-anpassade enheter*).
    - **Basenhet** – Ange det här alternativet som *Ja* om du vill använda den aktuella enheten som basenhet för dess enhetsklass. I detta fall behöver du bara ange konverteringsfaktorn mellan basenheten och varje ytterligare enhet i enhetsklassen. Systemet kan sedan konvertera mellan alla enheter i denna enhetsklass. Därför är det enklare att ställa in konverteringar.

        Om liter till exempel är basenhet för enhetsklassen *Volym*, behöver du bara ställa in konverteringsfaktorer från exempelvis quart till liter och från pint till liter. Systemet kan sedan även konvertera från quart till pint.

        Du kan endast ha en basenhet per enhetsklass.

    - **Systemenhet** – Ange det här alternativet som *Ja* om du vill använda den aktuella enheten som antagen enhet för alla icke-specificerade mått i dess enhetsklass. Om till exempel ett fält som används för att ange en kvantitet inte tillåter att en enhet anges (om användaren inte väljer någon enhet) använder systemet den enhet som har ställts in som systemenhet för enhetsklassen *Kvantitet*. Du kan endast ha en systemenhet per enhetsklass.
    - **Decimalprecision** – Ange det antal decimaler som värden som anges för den aktuella enheten eller konverteras till ska avrundas till.

1. Klicka på **Spara** i åtgärdsfönstret.

## <a name="define-unit-translations"></a>Definiera enhetsöversättningar

Gör på följande sätt om du vill definiera översättningar av ID:t eller symbolen samt beskrivningen av en måttenhet.

1. Skapa eller välj enheten som översättningar ska skapas för.
1. Välj **Enhetstexter** i åtgärdsfönstret.

    Sidan **Enhetstexter** visas. På den här sidan definierar du översättningar av ID eller symbol för den valda enheten. Dessa översättningar kan sedan användas på externa dokument på kundspecifika eller leverantörsspecifika språk.

1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **Språk** väljer du det språk du vill översätta enhetens ID eller symbol till.
1. I fältet **Text** anger du översättningen av enhets-ID:t eller symbolen på det valda språket.
1. Klicka på **Spara** i åtgärdsfönstret.
1. Stäng sidan.
1. Välj **Översatta enhetsbeskrivningar** i **åtgärdsfönstret**.

    Sidan **Beskrivningar av den översatta enheten** visas. Du använder den här sidan när du vill definiera språkspecifika beskrivningar för den valda enheten.

1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **Språk** väljer du det språk du vill översätta enhetens beskrivning till.
1. I fältet **Beskrivning** anger du översättningen av enhetens beskrivning på det valda språket.
1. Klicka på **Spara** i åtgärdsfönstret.
1. Stäng sidan.

## <a name="define-unit-conversion-rules"></a>Definiera enhetskonverteringsregler

Följ de här stegen om du vill definiera regler för konvertering mellan måttenheter.

1. Skapa eller välj den enhet som konverteringsregler ska definieras för.
1. Välj **Enhetskonverteringar** i åtgärdsfönstret.

    Sidan **Enhetskonverteringar** visas. Du kan använda denna sida för att definiera regler för att konvertera den valda enheten till och från andra enheter i enhetsklassen.

1. Välj en av följande flikar, beroende på vilken typ av konvertering som du vill ställa in:

    - **Standardkonverteringar** – Ställ in standardkonverteringsregler för alla produkter.
    - **Konverteringar inom klass** – Ställ in produktspecifika konverteringsregler för enheter i samma enhetsklass.
    - **Konverteringar mellan klasser** – Ställ in produktspecifika konverteringsregler för enheter i flera olika enhetsklasser.

1. Gör något av följande:

    - Om du vill skapa en ny konvertering väljer du **Ny** i verktygsfältet.
    - Om du vill redigera en befintlig konvertering markerar du konverteringen i rutnätet och väljer sedan **Redigera** i verktygsfältet.

1. Ställ in följande fält i dialogrutan för listrutan som visas:

    - **Produkt** – Välj den specifika produkt som konverteringen gäller för. Detta fält är endast tillgängligt för konverteringar inom klass och mellan klasser.
    - **Formellayout** – Lämna det här fältet inställt på *Enkelt* om du vill ange en enkel konvertering som har en enda faktor. Ställ in den *Avancerat* för att ställa in en mer komplex formel. Formatet för avancerade formler varierar beroende på enhetsklassen.
    - **Från enhet** – I det här fältet visas den valda enheten. Vanligtvis ska du inte ändra värdet. (Om du ändrar värdet måste du öppna sidan **Enhetskonverteringar** för den valda enheten, detta om du vill visa den nya konverteringen när du har sparat den.)
    - **Till enhet** – Välj enheten du vill konvertera till.
    - **Avrundning** – Välj hur en del ska avrundas, baserat på det **decimalvärde** som den valda enheten har (*Till närmaste*, *Upp* eller *Ned*).
    - **Konverteringsformel** – Använd de återstående fälten högst upp i listrutans dialogruta för att ange formeln för konvertering mellan de två enheterna. Vilka fält som finns tillgängliga varierar beroende på den enhetsklass och receptlayout som du har valt.

1. Välj **OK**.
1. Stäng sidan.

> [!TIP]
> Du kan även ställa in enhetskonverteringar per produktvariant. Mer information finns i [Måttenhetskonvertering per produktvariant](../uom-conversion-per-product-variant.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
