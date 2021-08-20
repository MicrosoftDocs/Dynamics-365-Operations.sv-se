---
title: Aktivera ändringshantering för befintliga produkter
description: I det här avsnittet beskrivs hur du aktiverar ändringshantering för befintliga produkter. Det beskriver också fall där möjligheten att aktivera ändringshantering är begränsad.
author: t-benebo
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-02
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 2fd3d2e4f4c3e53913bd811728b0950c63b38bc5afe6fe5282b4cfb05f414619
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744188"
---
# <a name="enable-change-management-on-existing-products"></a>Aktivera ändringshantering för befintliga produkter

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du aktiverar ändringshantering för befintliga produkter. Det beskriver också fall där möjligheten att aktivera ändringshantering är begränsad.

När du aktiverar ändringshantering för en befintlig produkt, kan du skapa versioner av produkten och spåra ändringar som gjorts i den under hela dess livslängd. Därför kan du spåra dessa ändringar genom att använda ändringsorder. Om du vill aktivera ändringshantering måste du konvertera relevanta produkter till *tekniska artiklar* (även kallade tekniska produkter). Teknikprodukter är produkter som versioneras och hanteras med hjälp av ändringshantering. Här finns en guide som vägleder dig genom konverteringsprocessen.

## <a name="turn-on-the-feature-in-your-system"></a>Aktivera funktionen i systemet

Om du vill använda denna funktion måste du utföra följande uppgifter:

1. Aktivera konstruktionsändringshantering-funktionen och dess konfigurationsnyckel som beskrivs i [Översikt över konstruktionsändringshantering](product-engineering-overview.md).
1. Aktivera funktionen *Aktivera ändringshantering av befintliga produkter* i funktionshantering. Mer information finns i [Översikt för funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="restrictions-and-limitations"></a>Begränsningar

Alla produkttyper kan inte konverteras till alla andra typer. Följande begränsningar gäller:

- När du konverterar en produkt till en teknisk produkt, förblir den en *produkt*. Den blir inte en *produktmall*.
- När du konverterar en produktmall som har en viss dimensionsuppsättning, underhålls dessa dimensioner efter ändringen. Om du till exempel konverterar en produktmall som har storleksdimensionen behåller den storleksdimensionen.

Om du har en specifik produkt kan du därför endast ändra den till en teknisk produkt som inte spårar produktdimensionen i transaktioner (det vill säga den versionsdimension som inte används). Se de återstående delarna av detta ämne för mer information om dessa problem.

## <a name="prepare-for-conversion-by-creating-all-required-engineering-product-categories"></a>Förbered konvertering genom att skapa alla nödvändiga kategorier för tekniska produkter

En *teknisk produktkategori* måste tilldelas varje teknisk produkt. Du gör den här tilldelningen när du kör guiden **Omvandla till teknisk produkt**. Teknikproduktkategorier måste finnas för alla relevanta standardprodukter *innan* du kan konvertera dessa produkter.

Den tekniska produktkategorin utgör grunden för att skapa en teknisk produkt, och den förser en uppsättning standardvärden och principer. Den tekniska produktkategorin måste matcha den produkt som du tilldelar den. Produkttypen och dimensionsgruppen måste till exempel matcha både produkten och den tekniska produktkategorin. För mer information, se [Konstruktionsversioner och kategorier av konstruktionsprodukter](engineering-versions-product-category.md).

> [!IMPORTANT]
> Guiden **Omvandla till teknisk produkt** kan bara konvertera produkt till teknikprodukter där versionen inte spåras i transaktioner. Därför måste alternativet **Spåra version i transaktioner** ställas in *Nej* för att konstruera produktkategorier som du skapar för att konvertera befintliga produkter.

För information om hur du skapar tekniska produktkategorier finns i [Konstruktionsversioner och kategorier av konstruktionsprodukter](engineering-versions-product-category.md).

## <a name="run-the-convert-to-engineering-product-wizard"></a>Köra guiden Konvertera till teknikprodukt

Med guiden **Omvandla till teknisk produkt** hjälper dig att konvertera en eller flera befintliga produkter till tekniska produkter. Produkter omvandlas till tekniska produkter (versionerade produkter) där versionen inte spåras i transaktioner (det vill säga den versionsdimension som inte används). När konverteringen är klar kan du hantera produkterna med hjälp av teknikändringshantering.

Konverteringen är permanent. Därför kan du inte återföra det senare. 

Varje konverterad teknikprodukt kommer att fortsätta att frisläppas i samma företag som den ursprungliga produkten frisläppdes i. Emellertid kommer strukturlista (BOM) och rutter inte automatiskt att släppas till dessa företag.

Följ dessa steg för att köra guiden **Omvandla till teknisk produkt** och konvertera en produkt till en ingenjörsprodukt.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Markera kryssrutan i rutnätet för varje produkt som du vill konvertera.
1. I åtgärdsfönstret på fliken **Tekniker** i grupp **Konstruktionsändringshantering** välj **Omvandla till teknisk produkt** för att öppna guiden.
1. Den första sidan i guiden är **välkomstsidan**. Om du inte redan känner till konverteringsprocessen läser du informationen noggrant på den här sidan. När du är redo att fortsätta väljer du **nästa**.
1. På sidan **Välj detaljer för de produkter som ska konverteras** visas varje produkt som du valde innan du öppnade guiden. Inspektera listan. Använd knappar **Ny** och **Ta bort** i verktygsfältet för att lägga till eller ta bort produkter efter behov.
1. Använd följande fält högst upp i rutnätet om du vill tilldela standardvärden till varje produkt som visas. (Du kan ändra dessa värden för enskilda produkter när konverteringen är klar.) Standardvärden tilldelas inte produkter där ett relevant värde redan har tilldelats.

    - **Standardteknikkategori** – Välj en grundläggande teknisk produktkategori att tilldela till alla listade produkter. Den kategori du väljer tillämpas endast på produkter som är kompatibla med den.
    - **Standardversion** – Ange den ursprungliga produktversionen som ska tilldelas varje listad produkt. Alla tekniska produkter har minst en teknisk version.
    - **Standard livscykeltillstånd** – Välj det ursprungliga livscykeltillståndet för produkten som ska tilldelas varje listad produkt.
    - **Nuvarande strukturlista kommer att ingå i teknikprodukten** – Markera den här kryssrutan om den aktuella strukturlistan för varje listad produkt ska användas som en strukturlista för teknikprodukten.

    Mer information om inställning av produkt finns i nästa steg.

1. Granska varje produkt som listas i rutnätet och utvärdera hur väl de standardvärden som du har tilldelats gäller för den. Granska följande information för varje rad och ställ in relevanta fält:

    - **Produktnummer** – produktnummer.
    - **Produktnamn** – Produktens namn.
    - **Teknikkategori** – Välj den tekniska produktkategorin som produkten ska tillhöra när den har konverterats. Det måste redan finnas en lämplig kategori för varje produkt, vilket beskrivs i det föregående avsnittet av det här avsnittet. Du måste tilldela en kategori till varje produkt.
    - **Version** – Ange produktversionen för att tilldela produkten efter att den har konverterats. Du kan till exempel välja ett nummer som passar in i den nummerserie som din kategori redan använder. I varje konstruktionsversion lagras de tekniska relevanta data som är specifika för den versionen. För mer information, se [Konstruktionsversioner och kategorier av konstruktionsprodukter](engineering-versions-product-category.md).
    - **Produktens livscykeltillstånd** – Välj produktens livscykeltillstånd som produkten ska vara i efter att den har konverterats. I produkts livscykeltillstånd kan du kontrollera vilka transaktioner som är tillåtna för en given teknisk version. Mer information finns i [produktens livscykeltillstånd och transaktioner](product-lifecycle-state-transactions.md).
    - **Har strukturlista** – En markerad kryssruta visar att produkten har en strukturlista. Om du ställer in den här kryssrutan kan du bestämma hur du anger kryssrutan **aktuell strukturlista ska ingå i den tekniska produkten**.
    - **Nuvarande strukturlista kommer att ingå i teknikprodukten** – Markera den här kryssrutan om den aktuella strukturlistan för produkt ska användas som en strukturlista för teknikprodukten. Denna strukturlista hanteras sedan av konstruktionsändringshantering. Om produkten inte har någon strukturlista eller om du föredrar att skapa en strukturlista manuellt för den konverterade produkten senare avmarkerar du den här kryssrutan.
    - **Innehåller fel** – En markerad kryssruta anger att produktinställningen har ett eller flera fel. Till exempel kanske produkttypen eller dimensionsgruppen inte matchar kategorin. Produkter som har fel hoppas över och konverteras inte.

1. När du är klar väljer du **Validera** i verktygsfältet för att validera produktinställningarna. För varje rad uppdateras kryssrutan **Har fel** för att indikera produktens status. Justera värdena tills inställningarna för varje produkt är felfria.
1. När alla produkter har ställts in på rätt sätt väljer du **Nästa** för att fortsätta.
1. Sidan **Bekräfta val** visas antalet produkter som inte har några fel i inställningarna och därför är klara för konvertering. Här visas också antalet produkter som kommer att hoppas över på grund av fel. Om du vill köra konverteringen som ett batchjobb ställer du in batchalternativet **Kör i batch** till *Ja*.
1. Välj **Slutför** om du vill använda dina inställningar och börja konvertera produkterna till tekniska produkter.

> [!NOTE]
> Om ditt system har ställts in för att acceptera produkter manuellt innan de frisläpps måste du acceptera varje konverterad produkt genom att använda sidan **Öppna produktfrisläppningar** i lämpliga företag. För mer information, se [Granska och acceptera produkten innan du släpper den i det lokala företaget](engineering-scenarios.md#accept).
