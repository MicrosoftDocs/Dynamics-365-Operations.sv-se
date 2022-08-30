---
title: Skapa fördefinierade produktvarianter
description: Den här proceduren går igenom hur du skapar produktvarianter för en produktmall med kombinationer av produktdimensioner.
author: t-benebo
ms.date: 08/09/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart, EcoResProductVariantSuggestionsEnhanced
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a26439b8c7346cdce2b4c9804493fea94c29ac31
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335928"
---
# <a name="predefined-product-variants"></a>Fördefinierade produktvarianter

[!include [banner](../../includes/banner.md)]

## <a name="example-scenario-create-predefined-product-variants"></a>Exempelscenario: Skapa fördefinierade produktvarianter

Detta exempelscenario visar hur du skapar produktvarianter för en produktmall med hjälp av kombinationer av produktdimensioner.

### <a name="make-demo-data-available"></a>Gör demodata tillgängliga

För att följa detta scenario med hjälp av här föreslagna värden måste du ha demonstrationsdata installerade samt välja den juridiska personen *USMF*.

### <a name="step-1-create-a-product-master"></a>Steg 1: Skapa en produktmall

För att skapa en produktmall:

1. Gå till **Produktinformationshantering > Produkter > Produktmallar**.
1. Välj **Ny**.
1. Om fältet **Produktnummer** inte redan visar ett nummer anger du ett värde. Detta krävs endast om ingen nummerserie har ställts in för detta fält.
1. Ange ett namn i fältet **Produktnamn**.
1. I fältet **Produktdimensionsgrupp** väljer du produktdimensionsgruppen *SizeCol* (storlek och färg).
1. Välj **OK** om du vill skapa och öppna den nya produktmallen.

### <a name="step-2-add-product-dimensions"></a>Steg 2: Lägg till produktdimensioner

Det här exemplet visar hur du manuellt anger produktdimensioner. Du kan också välja att markera en storlek, färg eller utförandegrupp som innehåller de produktdimensionsvärden som du vill använda.

För att lägga till produktdimensioner:

1. Med din nya produktmall fortfarande öppen väljer du **Produktdimensioner** i åtgärdsfönstret.
1. Öppna fliken **Storlek** och välj sedan **Ny** i verktygsfältet för att lägga till en rad i rutnätet. Gör följande inställningar för den nya raden:
    - **Storlek:** Välj ett storleksvärde.
    - **Namn:** Ange ett namn för storleken.
1. Välj **Ny** i verktygsfältet och lägg till en andra storlek i rutnätet med ny **Storlek** och **Namn**.
1. Öppna fliken **Färger** och välj sedan **Ny** i verktygsfältet för att lägga till en rad i rutnätet. Gör följande inställningar för den nya raden:
    - **Färg:** Välj ett färgvärde.
    - **Namn:** Ange ett namn för färgen.
1. Välj **Ny** i verktygsfältet och lägg till en andra storlek i rutnätet med en ny **Färg** och ett nytt **Namn**.
1. Välj **Spara**.
1. Stäng sidan när du vill återgå till din nya produktmall.

### <a name="step-3-generate-product-variants"></a>Steg 3: Skapa produktvarianter

> [!NOTE]
> I det här avsnittet beskrivs hur du skapar produktvarianter när funktionen *Förbättringar av variantförslagssida* inte är aktiverad. I nästa avsnitt finns mer information om hur du skapar produktvarianter när den funktionen är tillgänglig.

Så här skapar du produktvarianter:

1. Med din nya produktmall fortfarande öppen väljer du **Produktvarianter** i åtgärdsfönstret.
1. Markera **Variantförslag** i åtgärdsfönstret.
1. Systemet skapar en lista med alla möjliga kombinationer av de storlekar och färger du definierat för produkten. Välj **Markera alla** i verktygsfältet.
    - I det här exemplet väljer du alla möjliga varianter. Om du bara vill använda en deluppsättning av de möjliga kombinationerna av produktdimensioner markerar du endast de kryssrutor som behövs.  
1. Markera **Skapa**.
1. Välj **Spara**.

## <a name="improved-variant-suggestions"></a>Förbättrade variantförslag

Funktionen *Förbättringar av förslagssida för varianter* förbättrar sidan **Variantförslag** i syfte att åtgärda problem med prestanda och användbarhet för företag med ett stort antal produktdimensionskombinationer. Den förbättrade processen för val av produktdimensionsvärden för vilken variantförslag skapas gör det snabbare och enklare att identifiera och frisläppa relevanta produktvarianter.

Följande förbättringar läggs till av den här funktionen:

- **Uppskjuten generering av variantförslag:** Sidan **Variantförslag** visar inte längre förslag när du öppnar den första gången. Du måste istället explicit välja vilka värden du behöver och sedan välja knappen **Föreslå** för att generera kombinationerna. Detta gör processen mer synlig och interaktiv.
- **Val av dimensionsvärden:** När du har många dimensionsvärden är du vanligtvis intresserad av att generera variantförslag som omfattar endast några av dem (till exempel när du inför en ny uppsättning färger eller utföranden). Med den förbättrade designen kan du välja de dimensionsvärden för vilka du vill skapa förslag på produktvarianter. Detta ökar relevansen för de föreslagna varianterna avsevärt och förbättrar både systemprestanda och användarproduktivitet.

### <a name="turn-the-variant-suggestions-page-improvements-feature-on-or-off"></a>Aktivera eller inaktivera funktionen för förbättrad variantförslagssida

Innan du kan använda funktionen måste den aktiveras i ditt system. Från och med version 10.0.25 av Supply Chain Management är denna funktion aktiverad som standard. Från och med version 10.0.29 version av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras. Om du kör en version som är äldre än 10.0.29 kan administratörer aktivera eller inaktivera den här funktionen genom att söka efter funktionen *Förbättringar av sidan med variantförslag* i arbetsytan [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="work-with-the-improved-variant-suggestions"></a>Arbeta med förbättrade variantförslag

Så här skapar du förslag på produktvarianter när funktionen *Förbättringar av variantförslagssida* är aktiverad:

1. Öppna eller skapa en produktmall och lägg till de produktdimensioner som krävs för den, enligt beskrivningen i föregående avsnitt.
1. Med den nya produktmallen öppen väljer du **Produktvarianter** i åtgärdsfönstret.
1. Markera **Variantförslag** i åtgärdsfönstret.
1. Välj de värden som du vill använda för respektive dimension.
1. Välj **Föreslå** i det övre verktygsfältet.
1. Systemet skapar en lista med alla möjliga kombinationer av de storlekar och färger du har valt. Markera kryssrutan för varje kombination av produktdimensioner som du vill använda på snabbfliken **Föreslagna varianter** eller välj **Markera alla** i verktygsfältet för att välja samtliga.  
1. Välj **Skapa** om du vill lägga till varianterna i den aktuella produktmallen.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
