---
title: Produktdimensioner
description: Det finns fem produktdimensioner – färg, konfiguration, storlek, stil och version. Du kombinerar produktdimensioner i dimensionsgrupper och tilldelar dimensionsgrupper till produktmallar. Kombinationerna av produktdimensioner bestämmer hur produktvarianter definieras.
author: t-benebo
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle, EcoResVersionNameLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: dc7c92287ff88fe46b5aa46e15f7af3344d11e3e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820284"
---
# <a name="product-dimensions"></a>Produktdimensioner

[!include [banner](../includes/banner.md)]

Det finns fem produktdimensioner: färg, konfiguration, storlek, stil och version. Du kombinerar produktdimensioner i dimensionsgrupper och tilldelar dimensionsgrupper till produktmallar. Kombinationerna av produktdimensioner bestämmer hur produktvarianter definieras.

Produktdimensioner är egenskaper som används för att identifiera en produktvariant. Du kan använda kombinationer av produktdimensioner för att definiera produktvarianter. Du måste definiera minst en produktdimension för en produktmall om du vill skapa en produktvariant.

## <a name="product-variants"></a>Produktvarianter

Produktvarianter kallas också för artiklar. En artikel är en materiell produkt, vilket inte är detsamma som en tjänst. Det är också möjligt att definiera en produktmall med typen Tjänst. Med typen Tjänst kan du ange produktvarianter som innehåller tjänster. Du kan till exempel ange en produktmall för konsultarbete och produktvarianter för arbete som utförs av seniorkonsulter och juniorkonsulter.

## <a name="product-dimensions"></a>Produktdimensioner

En produktvariant kan genereras baserat på produktdimensionsvärdena.

Produktdimensionsvärden för dimensionerna storlek, färg och stil kan skapas på följande platser:

- **Storlek**-sida (**produktinformationshantering \> inställning \> dimensioner och variantgrupper \> storlekar**)
- **Färg**-sida (**produktinformationshantering \> inställning \> dimensioner och variantgrupper \> Färg**)
- **stil**-sida (**produktinformationshantering \> inställning \> dimensioner och variantgrupper \> stil**)

Produktdimensionsvärden för konfigurationsdimensionen skapas vanligtvis med hjälp av antingen produktkonfigureraren eller med den dimensionsbaserade konfigureraren. 

Produktversioner skapas vanligtvis för specifika versioner medan produkten utvecklas under livscykeln. Produktversioner beskrivs mer detaljerat längre fram i det här avsnittet.

Produktdimensioner kan också skapas och underhållas på sidan **Produktdimensioner** som du öppnar från följande platser:

- Gå till **Hantering av produktinformation \> Produkter \> Produktmallar**. Välj **Produktdimensioner** i åtgärdsfönstret.
- Gå till **Produktinformationshantering \> Produkter \> Alla produkter och produktmallar**. Välj en produktmall. Välj **Produktdimensioner** i åtgärdsfönstret.
- Gå till **Produktinformationshantering \> Frisläppta produkter**. Välj en produktmall. I åtgärdsfönstret, på fliken **Produkt**, i gruppen **Produktmall**, markerar du sedan **Produktdimensioner**.

Antalet varianter som du kan skapa för en artikel begränsas av antalet möjliga produktdimensionskombinationer.

> [!TIP]
> När du använder en produkt på till exempel en orderrad väljer du produktdimensioner för att identifiera produktvarianten du vill arbeta med.

## <a name="example"></a>Exempel

Ett företag säljer jeans. Artikeln *jeans* använder produktdimensionerna för färg och storlek. Jeansen säljs i tre olika färger och i sex olika storlekar. Färgerna är blå, svart och brun. Storlekarna är XS, S, M, L, XL och XXL. Inte alla storlekar är tillgängliga i alla de tre färger. Om alla kombinationerna vore tillgängliga skulle det skapa 18 olika typer av jeans. I det här exemplet produceras bara följande nio produktvariantkombinationer.

| Färg | Storlek |
|-------|------|
| Blått  | XS   |
| Blått  | L    |
| Blått  | M    |
| Svart | M    |
| Svart | L    |
| Svart | XL   |
| Brunt | L    |
| Brunt | XL   |
| Brunt | XXL  |

## <a name="the-version-product-dimension"></a>Versionsproduktdimension

Version är en produktdimension som är avsedd att hjälpa dig underhålla och spåra flera versioner av en produkt i hela leveranskedjan. Versionsspårning är nödvändigt för att tillverkare som arbetar i en värld ska kunna krympa produktens livscykler ständigt, öka kraven på kvalitet och tillförlitlighet och öka fokus på produktsäkerhet.

Som en standardproduktdimension fungerar versionen på liknande sätt som de befintliga produktdimensionerna (storlek, stil, färg och konfiguration). Därför kan du använda den för andra funktioner, förutom att följa upp produktversioner.

### <a name="turn-on-the-version-dimension"></a><a name="enable-version-dim"></a>Aktivera versionsdimension

#### <a name="before-you-turn-on-the-version-dimension"></a>Innan du aktiverar versionsdimension

När du aktiverar versionsdimensionen kan vissa funktioner bli brutna eller sluta att fungera som förväntat om du har installerat andra lösningar som lägger till anpassningar i lagerdimensionerna. Om versionsdimensionen ska fungera fullt ut måste du kanske uppdatera dessa lösningar så att de inkluderar versionsdimensionen i deras referenser till lagerdimensionerna.

När du testar dina lösningar för att få kompatibilitet med versionsdimensionen söker du efter följande element:

1. **Funktionalitet:** alla anpassningar som involverar lagerdimensionerna måste bedömas för att de ska kunna arbeta tillsammans med versionsdimensionen.
1. **Referenser till lagerdimensionerna:** Sök efter referenser till lagerdimensioner (dvs. platser där dimensionerna uttryckligen refereras). Referenser till `InventDimId` ska användas i rutan, men sök efter referenser till formatmall eller färg. Kontrollera till exempel följande element:

    - API-anrop i utökade klasser
    - Alla referenser till specifika lagerdimensioner i tilläggskod (den här koden måste vara en växel i versionsdimensionen tillsammans med dimensionerna för format, färg och storlek.)

1. **Referenser till föråldrade API-anrop**: i dess inledning av versionsdimensionen har Microsoft försökt att göra så få API:er som möjligt för gamla. De få API:er som har gjorts inaktuella kommer att generera en varning när du aktiverar konfigurationsnyckeln **produktdimension - version**. Anrop till dessa API:er måste korrigeras i dina utökade lösningar innan du aktiverar versionsdimensionen i ett produktionssystem. Här är de versionsspecifika, gamla API:erna:

    - RetailTransactionServiceInventory::getProductRecordId
    - EcoResProductNumberIdentifiedProductVariantEntity::find
    - EGAISAlcoholProduction_RU::findByItemDim
    - PCVariantConfiguration::findByProductMasterAndDimensions

1. **Kartor:** Om några kartor använder lagerdimensionerna måste motsvarande relationskartläggning till dessa kartor uppdateras så att de inkluderar versionsdimension. I utökade modell- eller registertillägg kan du söka efter register där fälten inkluderar lagerdimensioner.
1. **Microsoft Dynamics 365 Commerce funktioner:** när den är aktiverad kommer versionsdimensionen att visas i den Commerce-specifika koden i Dynamics 365 Supply Chain Management. Versionsdimensionen stöds dock ännu inte av Commerce-kanaldatabasen eller i kassaprogrammen (POS) eller e-handelsprogram. Dessa Commerce-specifika appar stöder inte användare som säljer/levererar eller returnerar/tar emot lager efter versionsdimension. Sökfunktionerna för lagertillgänglighet kommer inte att urskilja lager per versionsdimension i Commerce-appar. Detta beteende liknar det aktuella beteendet för konfigurationsdimensionen i hela Commerce.

#### <a name="turn-on-the-version-dimension"></a>Aktivera versionsdimension

Innan du kan använda den här versionsdimension den aktiveras i ditt system. Den här uppgiften kräver administratörsbehörighet.

1. Gå till **Systemadministration \> Arbetsytor \> Funktionshantering**.
1. Aktivera funktionen med namnet *produktdimensionsversion*. (Mer information finns i [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).)
1. Sätt ditt system i [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Öppna **Systemadministration \> Inställningar \> Licenskonfiguration**.
1. På fliken **konfigurationsnycklar** expanderar **handel** och markerar kryssrutan för **produktdimension - version**.
1. Inaktivera [underhållsläge](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

### <a name="areas-where-the-version-dimension-isnt-supported"></a>Områden där versionsdimensionen inte stöds

Följande områden stöder inte versionsdimensionen (du kan fortfarande använda dessa områden, men du kan inte lägga till versionerade produkter (produkter där versionsdimensionen används) till dem). Du kan till exempel inte lägga till en version av en artikel i en leverantörskatalog. Det beror på att om du lägger till produkter med versionsdimensionen i dessa områden skulle det leda till icke-bakåtkompatibla ändringar.

- Månadsutdrag för kostnadsbärare
- Kostnadsobjekt, redovisningscache
- MCR försäljningsstatistik per artikel
- Leverantörskataloger
- EcoResProductDimensionGroupEntity

Dessutom stöder inte funktionerna för att skapa order och orderbearbetning i Commerce (t.ex. för kassa, kundtjänst och nätbutikorder) versionsdimensionen. Det finns ingen bekräftad tidslinje som för när Commerce-order kommer att förbättras för att stödja den.

### <a name="functional-characteristics-of-the-version-dimension"></a>Funktionella egenskaper för versionsdimensionen

Versionsdimensionen fungerar som de andra produktdimensionerna. På grund av dess speciella beskaffenhet och eftersom den är avsedd att underhålla och spåra flera versioner av en produkt, fungerar den emellertid lite annorlunda. Här följer några av skillnaderna och likheter:

- **Det finns ingen versionsgrupp.**

    Även om begreppet grupper finns i storlek, färg och stil (färggrupp, storleksgrupp och stilgrupp) finns det inget gruppkoncept för versionsgrupp. Med hjälp av grupper kan du fördefiniera de tillämpliga värdena så att alla färger i färggruppen, om du t.ex. tilldelar en färggrupp till en produkt. Det här konceptet gäller inte för versionsdimensionen, eftersom de versioner som en produkt tar inte är fördefinierade när produkten skapas. I stället skapas versioner under produktens livscykel, eftersom de krävs. Om produktens form, anpassning och funktion är densamma, skapar du vanligtvis en ny version i stället för en ny produkt.

- **Förslag på produktvarianter fungerar på samma sätt som för närvarande.**

    Vid förslag på produktvarianter skapas förslag för alla dimensionsvärden för versioner precis som de gör för andra dimensioner. Processen att skapa och frigöra versioner av produkter är densamma som för produkter som använder andra dimensioner. När du skapar en versionsprodukt kommer den första versionen (V1) att skapas som en produktdimension och varianterna frigörs. När produktändringarna och en ny version behövs läggs det nya versionsvärdet (V2) till och de obligatoriska varianterna frigörs. Det finns ingen förväntan att alla versioner (V1, V2, and V3) kommer att skapas i förväg för produkten.

> [!IMPORTANT]
> Om du aktiverar och använder versions dimensionen kan vissa lösningar som refererar till lagerdimensionerna sluta fungera som förväntat. Bekräfta och åtgärda problemen genom att kontakta den oberoende programvaruleverantören (ISV) för dina aktuella lösningar. Mer information finns i [Aktivera versionsdimensionen](#enable-version-dim).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]